---
title: Audits Dynamics 365 Customer Insights ar Azure Monitor
description: Uzziniet, kā nosūtīt žurnālus pārraugam Microsoft Azure.
ms.date: 12/14/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: article
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: d84ae8301bdf384c2484cdb1e7dd8eb75d406769
ms.sourcegitcommit: 50d32a4cab01421a5c3689af789e20857ab009c4
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 03/03/2022
ms.locfileid: "8376425"
---
# <a name="log-forwarding-in-dynamics-365-customer-insights-with-azure-monitor-preview"></a>Pieteikšanās pāradresācija, Dynamics 365 Customer Insights izmantojot Azure Monitor (Preview)

Dynamics 365 Customer Insights nodrošina tiešu integrāciju ar Azure Monitor. Azure Monitor resursu žurnāli ļauj pārraudzīt un nosūtīt žurnālus uz [Azure Storage](https://azure.microsoft.com/services/storage/), [Azure Žurnālu analīzi](/azure/azure-monitor/logs/log-analytics-overview) vai straumēt tos Azure [notikumu centrmezglos](https://azure.microsoft.com/services/event-hubs/).

Customer Insights sūta šādus notikumu žurnālus:

- **Audita notikumi**
  - **APIEvent** - ļauj mainīt izsekošanu, kas veikta, izmantojot lietotāja interfeisu Dynamics 365 Customer Insights.
- **Operatīvie notikumi**
  - **WorkflowEvent** - darbplūsma ļauj iestatīt [datu avotus](data-sources.md), [apvienot un bagātināt](data-unification.md) un [visbeidzot](enrichment-hub.md) [eksportēt](export-destinations.md) datus citās sistēmās. Visus šos pasākumus var veikt atsevišķi (piemēram, izraisīt vienu eksportu) vai organizēt (piemēram, datu atsvaidzināšanu no datu avotiem, kas izraisa apvienošanas procesu, kas piesaistīs papildu bagātināšanu un pēc tam eksportēs datus uz citu sistēmu). Plašāku informāciju skatiet [WorkflowEvent shēmā](#workflow-event-schema).
  - **APIEvent** - visi API zvani uz klientu instanci uz Dynamics 365 Customer Insights. Plašāku informāciju skatiet [APIEvent shēmā](#api-event-schema).

## <a name="set-up-the-diagnostic-settings"></a>Diagnostikas iestatījumu iestatīšana

### <a name="prerequisites"></a>Priekšnoteikumi

Lai konfigurētu diagnostiku programmā Customer Insights, ir jāizpilda šādi priekšnosacījumi:

- Jums ir aktīvs [Azure abonements](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/).
- Jums ir [administratora](permissions.md#admin) atļaujas programmā Customer Insights.
- Jums ir līdzstrādnieka **un** **lietotāja piekļuves administratora** loma Mērķa resursā pakalpojumā Azure. Resurss var būt Azure krātuves konts, Azure notikumu centrmezgls vai Azure žurnālu analīzes darbvieta. Papildinformāciju skatiet rakstā [Azure lomu piešķires pievienošana vai noņemšana, izmantojot Azure portālu](/azure/role-based-access-control/role-assignments-portal).
- [Ir izpildītas mērķa prasības](/azure/azure-monitor/platform/diagnostic-settings#destination-requirements) Azure Storage, Azure Event Hub vai Azure Log Analytics.
- Resursu grupā, **kurai pieder resurss, ir vismaz lasītāja** loma.

### <a name="set-up-diagnostics-with-azure-monitor"></a>Diagnostikas iestatīšana, izmantojot Azure Monitor

1. Sadaļā Customer Insights atlasiet **SystemDiagnostics** > **·**, lai skatītu diagnostikas galamērķus, kas konfigurēti šajā instancē.

1. Atlasiet **Pievienot mērķi**.

   > [!div class="mx-imgBorder"]
   > ![Diagnostikas savienojums](media/diagnostics-pane.png "Diagnostikas savienojums")

1. Norādiet nosaukumu **laukā Diagnostikas mērķa** nosaukums.

1. Izvēlieties **Azure abonementa nomnieku** ar mērķa resursu un atlasiet **pieteikties**.

1. Atlasiet **resursu tipu** (Krātuves konts, Notikumu centrmezgls vai žurnāla analīze).

1. Atlasiet **mērķa resursa abonementu**.

1. Atlasiet **mērķa resursa resursu grupu** Resurss.

1. Atlasiet **resursu**.

1. Apstipriniet **datu konfidencialitātes un atbilstības** paziņojumu.

1. Atlasiet **Izveidot savienojumu ar sistēmu**, lai izveidotu savienojumu ar mērķa resursu. Žurnāli sāk parādīties galamērķī pēc 15 minūtēm, ja API tiek izmantots un ģenerē notikumus.

### <a name="remove-a-destination"></a>Mērķa noņemšana

1. Dodieties uz **SystemDiagnostics** > **·**.

1. Sarakstā atlasiet diagnostikas mērķi.

1. **Kolonnā Darbības** atlasiet **ikonu Dzēst**.

1. Apstipriniet dzēšanu, lai apturētu žurnāla pāradresēšanu. Azure abonementa resurss netiks dzēsts. Kolonnā Darbības **var atlasīt saiti,** lai atlasītajam resursam atvērtu Azure portālu un izdzēstu to tur.

## <a name="log-categories-and-event-schemas"></a>Žurnālu kategorijas un notikumu shēmas

Pašlaik [tiek atbalstīti API notikumi](apis.md) un darbplūsmas notikumi, un tiek lietotas šādas kategorijas un shēmas.
Žurnāla shēma seko [Azure Monitor kopējai shēmai](/azure/azure-monitor/platform/resource-logs-schema#top-level-common-schema).

### <a name="categories"></a>Kategorijas

Customer Insights piedāvā divas kategorijas:

- **Audita notikumi**: [API notikumi](#api-event-schema), lai izsekotu konfigurācijas izmaiņas pakalpojumā. `POST|PUT|DELETE|PATCH` darbības iekļaujas šajā kategorijā.
- **Darbības notikumi**: [API notikumi](#api-event-schema) vai [darbplūsmas notikumi,](#workflow-event-schema) kas ģenerēti pakalpojuma lietošanas laikā.  Piemēram, `GET` pieprasījumi vai darbplūsmas izpildes notikumi.

## <a name="configuration-on-the-destination-resource"></a>Konfigurācija mērķa resursā

Atkarībā no jūsu izvēles par resursa tipu automātiski tiks veiktas šādas darbības:

### <a name="storage-account"></a>Krātuves konts

Customer Insights servisa direktors saņem krātuves konta līdzstrādnieka **atļauju atlasītajā resursā** un atlasītajā nosaukumvietā izveido divus konteinerus:

- `insight-logs-audit` kurā ir **audita notikumi**
- `insight-logs-operational` kas satur **operatīvus notikumus**

### <a name="event-hub"></a>Notikumu centrmezgls

Customer Insights servisa direktors saņem **Azure notikumu centrmezglu datu īpašnieka** atļauju resursā un atlasītajā nosaukumvietā izveidos divus notikumu centrmezglus:

- `insight-logs-audit` kurā ir **audita notikumi**
- `insight-logs-operational` kas satur **operatīvus notikumus**

### <a name="log-analytics"></a>Žurnālu analīze

Customer Insights servisa vadītājs saņem **žurnāla analīzes līdzstrādnieka** atļauju resursā. Žurnāli būs pieejami atlasītajā žurnālu analīzes darbvietā sadaļā **LogsTablesLog** > **·** > **Management**. Izvērsiet **žurnālu pārvaldības** risinājumu un atrodiet `CIEventsAudit` tabulas un `CIEventsOperational` tabulas.

- `CIEventsAudit` kurā ir **audita notikumi**
- `CIEventsOperational` kas satur **operatīvus notikumus**

**Logā Vaicājumi** izvērsiet **audita** risinājumu un atrodiet vaicājumu piemērus, kas tiek nodrošināti, meklējot `CIEvents`.

## <a name="event-schemas"></a>Notikumu shēmas

API notikumiem un darbplūsmas notikumiem ir kopīga struktūra un detalizēta informācija, kur tie atšķiras, skatiet [API notikumu shēmu](#api-event-schema) vai [darbplūsmas notikumu shēmu](#workflow-event-schema).

### <a name="api-event-schema"></a>API notikumu shēma

| Kolonna             | Datatype  | Obligāts/neobligāts | Apraksts       | Piemērs        |
| ----------------- | --------- | ----------------- | --------------------- | ------------------------ |
| `time`            | Laikspiedols | Obligāti          | Pasākuma laikspiedols (UTC)       | `2020-09-08T09:48:14.8050869Z`         |
| `resourceId`      | String    | Obligāti          | Notikuma izstarotās instances ResourceId         | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX`  |
| `operationName`   | String    | Obligāti          | Šajā notikumā pārstāvētās operācijas nosaukums.                                                                                                                | `Workflows.GetWorkFlowStatusAsync`                                                                                                                                       |
| `category`        | String    | Obligāti          | Notikuma žurnāla kategorija. Vai `Operational` nu vai `Audit`. Visi POST/PUT/PATCH/DELETE HTTP pieprasījumi ir atzīmēti ar `Audit`, viss pārējais ar`Operational` | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resultType`      | String    | Obligāti          | Notikuma statuss. `Success`, `ClientError`, `Failure`                                                                                                        |                                                                                                                                                                          |
| `resultSignature` | String    | Neobligāti          | Notikuma rezultāta statuss. Ja operācija atbilst REST API zvanam, tas ir HTTP statusa kods.        | `200`             |
| `durationMs`      | Garš      | Neobligāti          | Darbības ilgums milisekundēs.     | `133`     |
| `callerIpAddress` | String    | Neobligāti          | Zvanītāja IP adrese, ja darbība atbilst API zvanam, kas nāk no publiski pieejamas IP adreses.                                                 | `144.318.99.233`         |
| `identity`        | String    | Neobligāti          | JSON objekts, kas apraksta tā lietotāja vai lietojumprogrammas identitāti, kurš veica operāciju.       | Skatiet [sadaļu Identitāte](#identity-schema).     |  
| `properties`      | String    | Neobligāti          | JSON objekts ar vairāk rekvizītiem konkrētajai notikumu kategorijai.      | Skatiet [sadaļu Rekvizīti](#api-properties-schema).    |
| `level`           | String    | Obligāti          | Notikuma smaguma pakāpe.    | `Informational`, `Warning` vai `Error``Critical`.           |
| `uri`             | String    | Neobligāti          | Absolūts pieprasījums URI.    |               |

#### <a name="identity-schema"></a>Identitātes shēma

`identity` JSON objektam ir šāda struktūra

```json
{
  "Authorization" : {
    "UserRole": "Admin",
    "RequiredRoles": [
      "Contributor",
      "Viewer"
      ]
    },
  "Claims" {
    "claimNameX" : "claimValueX",
    "claimNameY" : "claimValueY"
   }
}  
```

| Kolonna                         | Apraksts                                                                                                                          |
| ----------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| `Authorization.UserRole`      | Lietotājam vai lietotnei piešķirtā loma. Papildinformāciju skatiet rakstā [Lietotāju atļaujas](permissions.md).                                     |
| `Authorization.RequiredRoles` | Operācijas veikšanai nepieciešamās lomas. `Admin` lomai ir atļauts veikt visas darbības.                                                    |
| `Claims`                      | Lietotāja vai lietotnes JSON tīmekļa pilnvaras (JWT) pretenzijas. Prasību rekvizīti atšķiras atkarībā no organizācijas un konfigurācijas Azure Active Directory. |

#### <a name="api-properties-schema"></a>API rekvizītu shēma

[API notikumiem](apis.md) ir šādi rekvizīti.

| Kolonna                        | Apraksts                                                                                                            |
| ---------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| `properties.eventType`       | Vienmēr `ApiEvent`, atzīmējot žurnāla notikumu kā API notikumu.                                                                 |
| `properties.userAgent`       | Pārlūkprogrammas aģents, kas nosūta pieprasījumu vai `unknown`.                                                                        |
| `properties.method`          | HTTP metode:`GET/POST/PUT/PATCH/HEAD`.                                                                                |
| `properties.path`            | Pieprasījuma relatīvais ceļš.                                                                                          |
| `properties.origin`          | URI, kas norāda, no kurienes nāk ienese vai `unknown`.                                                                  |
| `properties.operationStatus` | `Success` HTTP statusa kodam < 400 <br> `ClientError` HTTP statusa kodam < 500 <br> `Error` http statusa > = 500 |
| `properties.tenantId`        | Organizācijas ID                                                                                                        |
| `properties.tenantName`      | Organizācijas nosaukums.                                                                                              |
| `properties.callerObjectId`  | Azure Active Directory Zvanītāja ObjectId.                                                                         |
| `properties.instanceId`      | Klientu ieskati`instanceId`                                                                                         |

### <a name="workflow-event-schema"></a>Darbplūsmas notikumu shēma

Darbplūsmā ir vairākas darbības. [Uzņem datu avotus](data-sources.md), [apvieno,](data-unification.md)[bagātina](enrichment-hub.md) un [eksportē](export-destinations.md) datus. Visas šīs darbības var veikt atsevišķi vai organizēt ar šādiem procesiem. 

#### <a name="operation-types"></a>Operāciju tipi

| OperationType     | Grupēt                                     |
| ----------------- | ----------------------------------------- |
| Norīšana         | [Datu avoti](data-sources.md)           |
| Datu sagatavošana   | [Datu avoti](data-sources.md)           |
| Kartēt               | [Datu apvienošana](data-unification.md)   |
| Saskaņot             | [Datu apvienošana](data-unification.md)   |
| Sapludināšana             | [Datu apvienošana](data-unification.md)   |
| ProfileStore      | [Klientu profili](customer-profiles.md) |
| Meklējiet            | [Klientu profili](customer-profiles.md) |
| Darbības          | [Darbības](activities.md)                  |
| AtribūtsPasākumi | [Segmenti un mēri](segments.md)      |
| EntityMeasures    | [Segmenti un mēri](segments.md)      |
| Mērījumi          | [Segmenti un mēri](segments.md)      |
| Segmentēšana      | [Segmenti un mēri](segments.md)      |
| Bagātināšana        | [Bagātināšana](enrichment-hub.md)                                          |
| Informācija      | [Prognozes](predictions-overview.md)                                          |
| AiBuilder         | [Prognozes](predictions-overview.md)                                          |
| Ieskati          | [Prognozes](predictions-overview.md)                                          |
| Eksportēšana            | [Eksportēšanas darbības](export-destinations.md)                                          |
| ModelManagement   | [Prognozes](custom-models.md)                                           |
| Attiecības      | [Datu apvienošana](relationships.md)                                           |

#### <a name="field-description"></a>Lauka apraksts

| Kolonna           | Datatype  | Obligāts/neobligāts | Apraksts                                                                                                                                                   | Piemērs                                                                                                                                                                  |
| --------------- | --------- | ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `time`          | Laikspiedols | Obligāti          | Pasākuma laikspiedols (UTC).                                                                                                                                 | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resourceId`    | String    | Obligāti          | Notikuma izstarotās instances ResourceId.                                                                                                            | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX` |
| `operationName` | String    | Obligāti          | Šajā notikumā pārstāvētās operācijas nosaukums. `{OperationType}.[WorkFlow|Task][Started|Completed]`. Atsaucei skatiet [sadaļu Operāciju tipi](#operation-types). | `Segmentation.WorkflowStarted`,<br> `Segmentation.TaskStarted`, <br> `Segmentation.TaskCompleted`, <br> `Segmentation.WorkflowCompleted`                                 |
| `category`      | String    | Obligāti          | Notikuma žurnāla kategorija. Vienmēr `Operational` darbplūsmas notikumiem                                                                                           | `Operational`                                                                                                                                                            | 
| `resultType`    | String    | Obligāti          | Notikuma statuss. `Running`, `Skipped`, `Successful`, `Failure`                                                                                            |                                                                                                                                                                          |
| `durationMs`    | Garš      | Neobligāti          | Darbības ilgums milisekundēs.                                                                                                                    | `133`                                                                                                                                                                    |
| `properties`    | String    | Neobligāti          | JSON objekts ar vairāk rekvizītiem konkrētajai notikumu kategorijai.                                                                                        | Skatīt apakšiedaļu [Darbplūsmas rekvizīti](#workflow-properties-schema)                                                                                                       |
| `level`         | String    | Obligāti          | Notikuma smaguma pakāpe.                                                                                                                                  | `Informational`, `Warning` vai `Error`.                                                                                                                                   |
|                 |

#### <a name="workflow-properties-schema"></a>Darbplūsmas rekvizītu shēma

Darbplūsmas notikumiem ir šādi rekvizīti.

| Kolonna              | Workflow | Uzdevums | Apraksts            |
| ------------------------------- | -------- | ---- | ----------- |
| `properties.eventType`                       | Jā      | Jā  | Vienmēr `WorkflowEvent`, atzīmējot notikumu kā darbplūsmas notikumu.                                                                                                                                                                                                |
| `properties.workflowJobId`                   | Jā      | Jā  | Darbplūsmas izpildes identifikators. Visiem darbplūsmas un uzdevumu notikumiem darbplūsmas izpildē ir vienāds `workflowJobId`.                                                                                                                                   |
| `properties.operationType`                   | Jā      | Jā  | Operācijas identifikators, sk. [Operāciju tipi].(#operation-types)                                                                                                                                                                                       |
| `properties.tasksCount`                      | Jā      | Nē.   | Tikai darbplūsma. Darbplūsmas izraisīto uzdevumu skaits.                                                                                                                                                                                                       |
| `properties.submittedBy`                     | Jā      | Nē.   | Neobligāts. Tikai darbplūsmas notikumi. Tā Azure Active Directory [lietotāja](/azure/marketplace/find-tenant-object-id#find-user-object-id) objekta ID, kurš aktivizēja darbplūsmu, skatiet arī `properties.workflowSubmissionKind`.                                   |
| `properties.workflowType`                    | Jā      | Nē.   | `full` vai `incremental` atsvaidzināt.                                                                                                                                                                                                                            |
| `properties.workflowSubmissionKind`          | Jā      | Nē.   | `OnDemand` vai `Scheduled`.                                                                                                                                                                                                                                  |
| `properties.workflowStatus`                  | Jā      | Nē.   | `Running` vai `Successful`.                                                                                                                                                                                                                                 |
| `properties.startTimestamp`                  | Jā      | Jā  | UTC Timestamp`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.endTimestamp`                    | Jā      | Jā  | UTC Timestamp`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.submittedTimestamp`              | Jā      | Jā  | UTC Timestamp`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.instanceId`                      | Jā      | Jā  | Klientu ieskati`instanceId`                                                                                                                                                                                                                              |  
| `properties.identifier`                      | Nē.       | Jā  | - OperationType = `Export` identifikators ir eksporta konfigurācijas GUID. <br> - OperationType = `Enrichment`, tas ir bagātināšanas GUID <br> - OperationType `Measures` un `Segmentation`, identifikators ir entītijas nosaukums. |
| `properties.friendlyName`                    | Nē.       | Jā  | Lietotājam draudzīgs eksporta vai apstrādātās entītijas nosaukums.                                                                                                                                                                                           |
| `properties.error`                           | Nē.       | Jā  | Neobligāts. Kļūdas ziņojums ar papildinformāciju.                                                                                                                                                                                                                  |
| `properties.additionalInfo.Kind`             | Nē.       | Jā  | Neobligāts. Tikai OperationType `Export`. Identificē eksporta tipu. Plašāku informāciju skatiet [pārskatā par eksporta galamērķiem](export-destinations.md).                                                                                          |
| `properties.additionalInfo.AffectedEntities` | Nē.       | Jā  | Neobligāts. Tikai OperationType `Export`. Satur eksportēto entītiju sarakstu.                                                                                                                                                            |
| `properties.additionalInfo.MessageCode`      | Nē.       | Jā  | Neobligāts. Tikai OperationType `Export`. Detalizēts ziņojums par eksportu.                                                                                                                                                                                 |
| `properties.additionalInfo.entityCount`      | Nē.       | Jā  | Neobligāts. Tikai OperationType `Segmentation`. Norāda segmenta dalībnieku kopskaitu.                                                                                                                                                    |
