---
title: Revīzija Dynamics 365 Customer Insights ar Azure monitoru
description: Uzziniet, kā nosūtīt žurnālus monitoram Microsoft Azure.
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
ms.openlocfilehash: 15ae772617efa4c64cf79d0bac10a0c3cb28ca30
ms.sourcegitcommit: a92bf5985263240fd07bad98d8e119b88cf2c9d9
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 05/26/2022
ms.locfileid: "8807590"
---
# <a name="log-forwarding-in-dynamics-365-customer-insights-with-azure-monitor-preview"></a>Pieteikšanās pārsūtīšanai Dynamics 365 Customer Insights, izmantojot Azure Monitor (Preview)

Dynamics 365 Customer Insights nodrošina tiešu integrāciju ar Azure Monitor. Azure Monitor resursu žurnāli ļauj pārraudzīt un nosūtīt žurnālus uz [Azure Storage](https://azure.microsoft.com/services/storage/), [Azure Log Analytics](/azure/azure-monitor/logs/log-analytics-overview) vai straumēt tos uz [Azure Event Hubs](https://azure.microsoft.com/services/event-hubs/).

Customer Insights tiek nosūtīti šādi notikumu žurnāli:

- **Audita notikumi**
  - **APIEvent** - ļauj veikt izmaiņu izsekošanu, izmantojot lietotāja interfeisu Dynamics 365 Customer Insights.
- **Operatīvie notikumi**
  - **WorkflowEvent** — darbplūsma ļauj iestatīt [datu avotus](data-sources.md), [apvienot](data-unification.md), [bagātināt](enrichment-hub.md) un visbeidzot [eksportēt](export-destinations.md) datus citās sistēmās. Visas šīs darbības var veikt atsevišķi (piemēram, izraisīt vienu eksportu). Var arī palaist orķestrētu (piemēram, datu atsvaidzināšanu no datu avotiem, kas izraisa apvienošanās procesu, kas ievelk bagātinājumus un pēc tam eksportēs datus citā sistēmā). Papildinformāciju [skatiet WorkflowEvent Schema](#workflow-event-schema).
  - **APIEvent** - visi API zvani uz klientu instanci uz Dynamics 365 Customer Insights. Papildinformāciju [skatiet APIEvent shēmā](#api-event-schema).

## <a name="set-up-the-diagnostic-settings"></a>Diagnostikas iestatījumu iestatīšana

### <a name="prerequisites"></a>Priekšnoteikumi

Lai konfigurētu diagnostiku customer insights, ir jāizpilda šādi priekšnosacījumi:

- Jums ir aktīvs [Azure abonements](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/).
- Jums ir [administratora](permissions.md#admin) atļaujas customer insights.
- Mērķa resursā **Azure ir līdzstrādnieka** un **lietotāja piekļuves administratora** loma. Resurss var būt Azure Data Lake Storage konts, Azure Notikumu centrmezgls vai Azure Log Analytics darbvieta. Papildinformāciju skatiet rakstā [Azure lomu piešķires pievienošana vai noņemšana, izmantojot Azure portālu](/azure/role-based-access-control/role-assignments-portal). Šī atļauja ir nepieciešama, konfigurējot diagnostikas iestatījumus customer insights, to var mainīt pēc veiksmīgas iestatīšanas.
- [Mērķa prasības](/azure/azure-monitor/platform/diagnostic-settings#destination-requirements) Azure Storage, Azure Event Hub vai Azure Log Analytics izpildīts.
- Resursu grupā, kurai pieder resurss **, ir vismaz lasītāja** loma.

### <a name="set-up-diagnostics-with-azure-monitor"></a>Diagnostikas iestatīšana, izmantojot Azure monitoru

1. Sadaļā Customer Insights atlasiet **Sistēmas** > **diagnostika**, lai skatītu diagnostikas mērķus, kas konfigurēti šajā gadījumā.

1. Atlasiet **Pievienot mērķi**.

   > [!div class="mx-imgBorder"]
   > ![Diagnostikas savienojums](media/diagnostics-pane.png "Diagnostikas savienojums")

1. Norādiet nosaukumu **laukā Diagnostikas mērķa** nosaukums.

1. **Izvēlieties Azure abonementa nomnieku** ar mērķa resursu un atlasiet **Pieteikties**.

1. Atlasiet resursa **tipu** (Krātuves konts, notikumu centrmezgls vai žurnāla analīze).

1. **Atlasiet mērķa resursa abonementu**.

1. **Atlasiet mērķa resursa resursu grupu**.

1. Atlasiet **resursu**.

1. Apstipriniet paziņojumu par **datu konfidencialitāti un atbilstību**.

1. Atlasiet **Izveidot savienojumu ar sistēmu**, lai izveidotu savienojumu ar mērķa resursu. Žurnāli sāk parādīties galamērķī pēc 15 minūtēm, ja API tiek izmantots un ģenerē notikumus.

### <a name="remove-a-destination"></a>Mērķa noņemšana

1. Dodieties uz **sistēmas** > **diagnostiku**.

1. Sarakstā atlasiet diagnostikas mērķi.

1. Kolonnā **Darbības** atlasiet **ikonu Dzēst**.

1. Apstipriniet dzēšanu, lai apturētu žurnāla pārsūtīšanu. Azure abonementa resurss netiks dzēsts. Varat atlasīt saiti kolonnā Darbības **,** lai atlasītajam resursam atvērtu Azure portālu un izdzēstu to tur.

## <a name="log-categories-and-event-schemas"></a>Reģistrēt kategorijas un notikumu shēmas

Pašlaik [tiek atbalstīti API notikumi](apis.md) un darbplūsmas notikumi un tiek lietotas šādas kategorijas un shēmas.
Žurnāla shēma atbilst [Azure Monitor parastajai shēmai](/azure/azure-monitor/platform/resource-logs-schema#top-level-common-schema).

### <a name="categories"></a>Kategorijas

Customer Insights piedāvā divas kategorijas:

- **Audita notikumi**: [API notikumi](#api-event-schema), lai izsekotu konfigurācijas izmaiņas pakalpojumā. `POST|PUT|DELETE|PATCH` darbības ietilpst šajā kategorijā.
- **Operatīvie notikumi**: [API notikumi](#api-event-schema) vai [darbplūsmas notikumi](#workflow-event-schema), kas ģenerēti pakalpojuma lietošanas laikā.  Piemēram, `GET` darbplūsmas pieprasījumi vai izpildes notikumi.

## <a name="configuration-on-the-destination-resource"></a>Konfigurācija mērķa resursā

Pamatojoties uz jūsu izvēlēto resursu tipu, automātiski tiks veiktas šādas darbības:

### <a name="storage-account"></a>Krātuves konts

Customer Insights pakalpojuma vadītājs saņem krātuves **konta līdzstrādnieka** atļauju atlasītajam resursam un atlasītajā nosaukumvietā izveido divus konteinerus:

- `insight-logs-audit` kas satur **audita notikumus**
- `insight-logs-operational` kas ietver **operatīvus notikumus**

### <a name="event-hub"></a>Notikumu centrmezgls

Customer Insights pakalpojuma vadītājs resursā **saņem Azure Event Hubs datu īpašnieka** atļauju un atlasītajā nosaukumvietā izveidos divus notikumu centrmezglus:

- `insight-logs-audit` kas satur **audita notikumus**
- `insight-logs-operational` kas ietver **operatīvus notikumus**

### <a name="log-analytics"></a>Žurnāla analītika

Customer Insights pakalpojuma vadītājs saņem **Log Analytics līdzstrādnieka** atļauju resursā. Žurnāli būs pieejami atlasītajā žurnāla analīzes darbvietas sadaļā **Žurnālu tabulu** > **žurnāla pārvaldība** > **.** Izvērsiet **žurnāla pārvaldības** risinājumu un atrodiet `CIEventsAudit` tabulas un `CIEventsOperational` tabulas.

- `CIEventsAudit` kas satur **audita notikumus**
- `CIEventsOperational` kas ietver **operatīvus notikumus**

**Logā Vaicājumi izvērsiet** audita **risinājumu** un atrodiet vaicājumu piemērus, kas sniegti, meklējot `CIEvents`.

## <a name="event-schemas"></a>Notikumu shēmas

API notikumiem un darbplūsmas notikumiem ir kopīga struktūra un detalizēta informācija, kur tie atšķiras, skatiet [API notikumu shēmu](#api-event-schema) vai [darbplūsmas notikumu shēmu](#workflow-event-schema).

### <a name="api-event-schema"></a>API notikumu shēma

| Kolonna             | Datatype  | Obligāts/neobligāts | Apraksts       | Piemērs        |
| ----------------- | --------- | ----------------- | --------------------- | ------------------------ |
| `time`            | Laikspiedols | Obligāti          | Pasākuma laikspiedols (UTC)       | `2020-09-08T09:48:14.8050869Z`         |
| `resourceId`      | String    | Obligāti          | Notikuma izlaidušās instances ResourceId         | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX`  |
| `operationName`   | String    | Obligāti          | Operācijas nosaukums, ko attēlo šis notikums.                                                                                                                | `Workflows.GetWorkFlowStatusAsync`                                                                                                                                       |
| `category`        | String    | Obligāti          | Notikuma žurnāla kategorija. Vai nu `Operational`, vai `Audit`. Visi POST/PUT/PATCH/DELETE HTTP pieprasījumi ir atzīmēti ar `Audit`, viss pārējais ar`Operational` | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resultType`      | String    | Obligāti          | Notikuma statuss. `Success`, `ClientError`, `Failure`                                                                                                        |                                                                                                                                                                          |
| `resultSignature` | String    | Neobligāti          | Notikuma rezultāta statuss. Ja operācija atbilst REST API izsaukumam, tas ir HTTP statusa kods.        | `200`             |
| `durationMs`      | Garš      | Neobligāti          | Operācijas ilgums milisekundēs.     | `133`     |
| `callerIpAddress` | String    | Neobligāti          | Zvanītāja IP adrese, ja operācija atbilst API izsaukumam, kas nāk no publiski pieejamas IP adreses.                                                 | `144.318.99.233`         |
| `identity`        | String    | Neobligāti          | JSON objekts, kas apraksta tā lietotāja vai lietojumprogrammas identitāti, kurš veica operāciju.       | Skatīt [sadaļu Identitāte](#identity-schema).     |  
| `properties`      | String    | Neobligāti          | JSON objekts ar vairāk rekvizītiem konkrētai notikumu kategorijai.      | Skatīt [sadaļu Rekvizīti](#api-properties-schema).    |
| `level`           | String    | Obligāti          | Notikuma smaguma pakāpe.    | `Informational`, `Warning``Error` vai `Critical`.           |
| `uri`             | String    | Neobligāti          | Absolūtais pieprasījuma URI.    |               |

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
| `Authorization.UserRole`      | Lietotājam vai lietotnei piešķirtā loma. Papildinformāciju skatiet sadaļā [Lietotāju atļaujas](permissions.md).                                     |
| `Authorization.RequiredRoles` | Nepieciešamās lomas, lai veiktu operāciju. `Admin` lomai ir atļauts veikt visas operācijas.                                                    |
| `Claims`                      | Lietotāja vai lietotnes JSON tīmekļa marķiera (JWT) pretenzijas. Pretenziju rekvizīti atšķiras atkarībā no organizācijas un konfigurācijas Azure Active Directory. |

#### <a name="api-properties-schema"></a>API rekvizītu shēma

[API notikumiem](apis.md) ir šādas īpašības.

| Kolonna                        | Apraksts                                                                                                            |
| ---------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| `properties.eventType`       | Vienmēr `ApiEvent`, atzīmējot žurnāla notikumu kā API notikumu.                                                                 |
| `properties.userAgent`       | Pārlūkprogrammas aģents nosūta pieprasījumu vai `unknown`.                                                                        |
| `properties.method`          | HTTP metode:`GET/POST/PUT/PATCH/HEAD`.                                                                                |
| `properties.path`            | Pieprasījuma relatīvais ceļš.                                                                                          |
| `properties.origin`          | URI, kas norāda, no kurienes nāk atnese vai `unknown`.                                                                  |
| `properties.operationStatus` | `Success` HTTP statusa kodam < 400 <br> `ClientError` HTTP statusa kodam < 500 <br> `Error` HTTP statusam > = 500 |
| `properties.tenantId`        | Organizācijas ID                                                                                                        |
| `properties.tenantName`      | Organizācijas nosaukums.                                                                                              |
| `properties.callerObjectId`  | Azure Active Directory Zvanītāja ObjectId.                                                                         |
| `properties.instanceId`      | Klientu ieskati`instanceId`                                                                                         |

### <a name="workflow-event-schema"></a>Darbplūsmas notikumu shēma

Darbplūsmā ir vairākas darbības. [Uzņemiet datu avotus](data-sources.md), [apvienojiet](data-unification.md), [bagātiniet](enrichment-hub.md) un [eksportējiet](export-destinations.md) datus. Visas šīs darbības var veikt atsevišķi vai organizēt ar šādiem procesiem.

#### <a name="operation-types"></a>Operāciju tipi

| OperationType     | Grupēt                                     |
| ----------------- | ----------------------------------------- |
| Norīšana         | [Datu avoti](data-sources.md)           |
| DataPreparation   | [Datu avoti](data-sources.md)           |
| Kartēt               | [Datu apvienošana](data-unification.md)   |
| Saskaņot             | [Datu apvienošana](data-unification.md)   |
| Sapludināšana             | [Datu apvienošana](data-unification.md)   |
| ProfileStore      | [Klientu profili](customer-profiles.md) |
| Meklējiet            | [Klientu profili](customer-profiles.md) |
| Darbības          | [Darbības](activities.md)                  |
| AttributeMeasures | [Segmenti un pasākumi](segments.md)      |
| EntityMeasures    | [Segmenti un pasākumi](segments.md)      |
| Mērījumi          | [Segmenti un pasākumi](segments.md)      |
| Segmentēšana      | [Segmenti un pasākumi](segments.md)      |
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
| `time`          | Laikspiedols | Obligāti          | Notikuma laikspiedols (UTC).                                                                                                                                 | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resourceId`    | String    | Obligāti          | Notikuma izstarotās instances ResourceId.                                                                                                            | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX` |
| `operationName` | String    | Obligāti          | Operācijas nosaukums, ko attēlo šis notikums. `{OperationType}.[WorkFlow|Task][Started|Completed]`. Atsaucei skatiet [operāciju tipus](#operation-types). | `Segmentation.WorkflowStarted`,<br> `Segmentation.TaskStarted`, <br> `Segmentation.TaskCompleted`, <br> `Segmentation.WorkflowCompleted`                                 |
| `category`      | String    | Obligāti          | Notikuma žurnāla kategorija. Vienmēr `Operational` darbplūsmas notikumiem                                                                                           | `Operational`                                                                                                                                                            |
| `resultType`    | String    | Obligāti          | Notikuma statuss. `Running`, `Skipped`, `Successful`, `Failure`                                                                                            |                                                                                                                                                                          |
| `durationMs`    | Garš      | Neobligāti          | Operācijas ilgums milisekundēs.                                                                                                                    | `133`                                                                                                                                                                    |
| `properties`    | String    | Neobligāti          | JSON objekts ar vairāk rekvizītiem konkrētai notikumu kategorijai.                                                                                        | Skatīt apakšsadaļu [Darbplūsmas rekvizīti](#workflow-properties-schema)                                                                                                       |
| `level`         | String    | Obligāti          | Notikuma smaguma pakāpe.                                                                                                                                  | `Informational`, `Warning` vai `Error`.                                                                                                                                   |
|                 |

#### <a name="workflow-properties-schema"></a>Darbplūsmas rekvizītu shēma

Darbplūsmas notikumiem ir šādi rekvizīti.

| Kolonna              | Workflow | Uzdevums | Apraksts            |
| ------------------------------- | -------- | ---- | ----------- |
| `properties.eventType`                       | Jā      | Jā  | Vienmēr `WorkflowEvent`, atzīmējot notikumu kā darbplūsmas notikumu.                                                                                                                                                                                                |
| `properties.workflowJobId`                   | Jā      | Jā  | Darbplūsmas izpildes identifikators. Visiem darbplūsmas un uzdevumu notikumiem darbplūsmas izpildē ir viens un tas pats `workflowJobId`.                                                                                                                                   |
| `properties.operationType`                   | Jā      | Jā  | Operācijas identifikators, skatiet [operāciju tipus](#operation-types).                                                                                                                                                                               |
| `properties.tasksCount`                      | Jā      | Nē.   | Tikai darbplūsma. Darbplūsmas izraisīto uzdevumu skaits.                                                                                                                                                                                                       |
| `properties.submittedBy`                     | Jā      | Nē.   | Neobligāts. Tikai darbplūsmas notikumi. Tā Azure Active Directory [lietotāja](/azure/marketplace/find-tenant-object-id#find-user-object-id) objectId, kurš aktivizēja darbplūsmu, skatiet arī `properties.workflowSubmissionKind`.                                   |
| `properties.workflowType`                    | Jā      | Nē.   | `full` vai `incremental` atsvaidziniet.                                                                                                                                                                                                                            |
| `properties.workflowSubmissionKind`          | Jā      | Nē.   | `OnDemand` vai `Scheduled`.                                                                                                                                                                                                                                  |
| `properties.workflowStatus`                  | Jā      | Nē.   | `Running` vai `Successful`.                                                                                                                                                                                                                                 |
| `properties.startTimestamp`                  | Jā      | Jā  | UTC laikspiedols`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.endTimestamp`                    | Jā      | Jā  | UTC laikspiedols`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.submittedTimestamp`              | Jā      | Jā  | UTC laikspiedols`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.instanceId`                      | Jā      | Jā  | Klientu ieskati`instanceId`                                                                                                                                                                                                                              |  
| `properties.identifier`                      | Nē.       | Jā  | - OperationType = `Export` identifikators ir eksporta konfigurācijas GUID. <br> - OperationType = `Enrichment`, tas ir bagātināšanas guid <br> - OperationType `Measures` un `Segmentation` identifikators ir entītijas nosaukums. |
| `properties.friendlyName`                    | Nē.       | Jā  | Lietotājam draudzīgs eksporta vai apstrādājamās entītijas nosaukums.                                                                                                                                                                                           |
| `properties.error`                           | Nē.       | Jā  | Neobligāts. Kļūdas ziņojums ar papildinformāciju.                                                                                                                                                                                                                  |
| `properties.additionalInfo.Kind`             | Nē.       | Jā  | Neobligāts. Tikai OperationType `Export`. Identificē eksporta tipu. Plašāku informāciju skatiet [pārskatā par eksporta galamērķiem](export-destinations.md).                                                                                          |
| `properties.additionalInfo.AffectedEntities` | Nē.       | Jā  | Neobligāts. Tikai OperationType `Export`. Satur eksportēto konfigurēto entītiju sarakstu.                                                                                                                                                            |
| `properties.additionalInfo.MessageCode`      | Nē.       | Jā  | Neobligāts. Tikai OperationType `Export`. Detalizēts ziņojums par eksportu.                                                                                                                                                                                 |
| `properties.additionalInfo.entityCount`      | Nē.       | Jā  | Neobligāts. Tikai OperationType `Segmentation`. Norāda segmenta dalībnieku kopskaitu.                                                                                                                                                    |
