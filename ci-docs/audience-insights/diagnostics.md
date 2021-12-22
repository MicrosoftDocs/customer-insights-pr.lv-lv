---
title: Revīzija Dynamics 365 Customer Insights ar Azure monitoru
description: Uzziniet, kā nosūtīt žurnālus Microsoft Azure monitoram.
ms.date: 12/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: article
author: brndkfr
ms.author: bkief
manager: shellyha
ms.openlocfilehash: d962c359d70a068fcf939b61e340f86de088b419
ms.sourcegitcommit: 0c3c473e0220de9ee3c1f1ee1825de0b3b3663c3
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 12/14/2021
ms.locfileid: "7920871"
---
# <a name="log-forwarding-in-dynamics-365-customer-insights-with-azure-monitor-preview"></a>Pieteikšanās pāradresēšanai, Dynamics 365 Customer Insights izmantojot Azure monitoru (Preview)

Dynamics 365 Customer Insights nodrošina tiešu integrāciju ar Azure monitoru. Azure Monitor resursu žurnāli ļauj pārraudzīt un nosūtīt žurnālus uz [Azure Storage, Azure Log Analytics vai](https://azure.microsoft.com/services/storage/)[straumēt](/azure/azure-monitor/logs/log-analytics-overview) [tos Azure notikumu centrmezglos](https://azure.microsoft.com/services/event-hubs/).

Customer Insights nosūta šādus notikumu žurnālus:

- **Revīzijas notikumi**
  - **APIEvent** - ļauj mainīt izsekošanu, izmantojot Dynamics 365 Customer Insights UI.
- **Operatīvie notikumi**
  - **WorkflowEvent** - Darbplūsma ļauj iestatīt datu avotus, apvienot un bagātināt un visbeidzot [eksportēt datus citās](data-sources.md)[...](data-unification.md)[...](enrichment-hub.md)[sistēmās](export-destinations.md). Visus šos posmus var veikt atsevišķi (piemēram, izraisīt vienu eksportu) vai organizēt (piemēram, datu atsvaidzināšanu no datu avotiem, kas izraisa apvienošanas procesu, kurš pievilks papildu bagātināšanu un pēc tam, kad tas būs veikts, eksportējot datus citā sistēmā). Plašāku informāciju skatiet [WorkflowEvent shēmā](#workflow-event-schema).
  - **APIEvent** - visi API izsaukumi uz klientu instanci uz Dynamics 365 Customer Insights. Plašāku informāciju skatiet [APIEvent shēmā](#api-event-schema).

## <a name="set-up-the-diagnostic-settings"></a>Diagnostikas iestatījumu iestatīšana

### <a name="prerequisites"></a>Priekšnoteikumi

Lai konfigurētu diagnostiku programmā Customer Insights, ir jāizpilda šādi priekšnosacījumi:

- Jums ir aktīvs [Azure abonements](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/).
- Jums ir [administratora atļaujas programmā Customer](permissions.md#administrator) Insights.
- **Azure mērķa** **resursā ir loma Līdzstrādnieks un Lietotāja piekļuves** administrators. Resurss var būt Azure krātuves konts, Azure notikumu centrmezgls vai Azure žurnālu analīzes darbvieta. Papildinformāciju skatiet rakstā [Azure lomu piešķires pievienošana vai noņemšana, izmantojot Azure portālu](/azure/role-based-access-control/role-assignments-portal).
- [Destination requirements](/azure/azure-monitor/platform/diagnostic-settings#destination-requirements) for Azure Storage, Azure Event Hub vai Azure Log Analytics atbilst.
- Resursu grupā, kurai pieder resurss, ir vismaz **loma** Lasītājs.

### <a name="set-up-diagnostics-with-azure-monitor"></a>Diagnostikas iestatīšana, izmantojot Azure monitoru

1. Sadaļā Customer Insights atlasiet **Sistēmas** > **diagnostika,** lai skatītu diagnostikas adresātus, kas konfigurēti šajā instancē.

1. Atlasiet **Pievienot mērķi**.

   > [!div class="mx-imgBorder"]
   > ![Diagnostikas savienojums](media/diagnostics-pane.png "Diagnostikas savienojums")

1. Norādiet nosaukumu **diagnostikas mērķa** laukā Nosaukums.

1. Izvēlieties **Azure** abonementa nomnieku ar mērķa resursu un atlasiet **Pieteikties**.

1. Atlasiet **resursa tipu** (Krātuves konts, Notikumu centrmezgls vai žurnāla analīze).

1. Atlasiet **mērķa** resursa abonementu.

1. Atlasiet **mērķa resursa resursu** grupu.

1. Atlasiet **resursu**.

1. Apstipriniet paziņojumu par **datu konfidencialitāti un** atbilstību.

1. Atlasiet **Izveidot savienojumu ar** sistēmu, lai izveidotu savienojumu ar mērķa resursu. Žurnāli galamērķī sāk parādīties pēc 15 minūtēm, ja API tiek izmantots un ģenerē notikumus.

### <a name="remove-a-destination"></a>Mērķa noņemšana

1. Dodieties uz **sistēmas** > **diagnostika**.

1. Sarakstā atlasiet diagnostikas mērķi.

1. Kolonnā **Darbības** atlasiet **ikonu** Dzēst.

1. Apstipriniet dzēšanu, lai apturētu žurnāla pāradresēšanu. Azure abonementa resurss netiks dzēsts. Varat atlasīt saiti **kolonnā** Darbības, lai atlasītajam resursam atvērtu Azure portālu un izdzēstu to tur.

## <a name="log-categories-and-event-schemas"></a>Žurnāla kategorijas un notikumu shēmas

Pašlaik [tiek atbalstīti API notikumi](apis.md) un darbplūsmas notikumi, un tiek piemērotas šādas kategorijas un shēmas.
Žurnāla shēma atbilst [Azure monitora kopējai shēmai](/azure/azure-monitor/platform/resource-logs-schema#top-level-common-schema).

### <a name="categories"></a>Kategorijas

Customer Insights piedāvā divas kategorijas:

- **Audita notikumi** : [API](#api-event-schema) notikumi, lai izsekotu konfigurācijas izmaiņas pakalpojumā. `POST|PUT|DELETE|PATCH` darbības ietilpst šajā kategorijā.
- **Darbības notikumi** : [API notikumi](#api-event-schema) vai [darbplūsmas notikumi](#workflow-event-schema), kas ģenerēti pakalpojuma izmantošanas laikā.  Piemēram, `GET` pieprasījumi vai darbplūsmas izpildes notikumi.

## <a name="configuration-on-the-destination-resource"></a>Konfigurācija mērķa resursā

Pamatojoties uz jūsu izvēli par resursa tipu, automātiski tiks piemērotas šādas darbības:

### <a name="storage-account"></a>Krātuves konts

Customer Insights servisa principāls **saņem krātuves konta līdzstrādnieka** atļauju atlasītajā resursā un izveido divus konteinerus zem atlasītās nosaukumvietas:

- `insight-logs-audit` kas satur **audita notikumus**
- `insight-logs-operational` kas satur **operatīvus notikumus**

### <a name="event-hub"></a>Notikumu centrmezgls

Customer Insights pakalpojuma vadītājs saņem **Azure notikumu centrmezglu datu īpašnieka** atļauju resursā un izveidos divus notikumu centrmezglus zem atlasītās nosaukumvietas:

- `insight-logs-audit` kas satur **audita notikumus**
- `insight-logs-operational` kas satur **operatīvus notikumus**

### <a name="log-analytics"></a>Žurnāla analīze

Customer Insights pakalpojuma vadītājs saņem **Žurnāla analīzes līdzstrādnieka** atļauju resursā. Žurnāli būs pieejami **sadaļā Žurnālu tabulu žurnāla pārvaldība atlasītajā žurnāla analīzes** > **·** > **darbvietā**. Izvērsiet **žurnāla pārvaldības risinājumu un atrodiet tabulas**`CIEventsAudit``CIEventsOperational` un.

- `CIEventsAudit` kas satur **audita notikumus**
- `CIEventsOperational` kas satur **operatīvus notikumus**

Logā **Vaicājumi** izvērsiet **audita risinājumu un atrodiet meklēšanas sniegto vaicājumu**`CIEvents` piemēru.

## <a name="event-schemas"></a>Notikumu shēmas

API notikumiem un darbplūsmas notikumiem ir kopīga struktūra un detalizēta informācija par to, kur tie atšķiras, skatiet [API notikumu shēmu vai](#api-event-schema)[darbplūsmas notikumu shēmu](#workflow-event-schema).

### <a name="api-event-schema"></a>API notikumu shēma

| Kolonna             | Datatype  | Obligāts/Neobligāts | Apraksts       | Piemērs        |
| ----------------- | --------- | ----------------- | --------------------- | ------------------------ |
| `time`            | Laikspiedols | Obligāti          | Pasākuma laikspiedols (UTC)       | `2020-09-08T09:48:14.8050869Z`         |
| `resourceId`      | String    | Obligāti          | Notikuma emitā instances resourceId         | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX`  |
| `operationName`   | String    | Obligāti          | Šī notikuma atveidotās operācijas nosaukums.                                                                                                                | `Workflows.GetWorkFlowStatusAsync`                                                                                                                                       |
| `category`        | String    | Obligāti          | Notikuma žurnāla kategorija. Vai nu `Operational` vai `Audit`. Visi POST/PUT/PATCH/DELETE HTTP pieprasījumi ir atzīmēti ar `Audit`, viss pārējais ar`Operational` | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resultType`      | String    | Obligāti          | Notikuma statuss. `Success`, `ClientError`, `Failure`                                                                                                        |                                                                                                                                                                          |
| `resultSignature` | String    | Neobligāti          | Notikuma rezultāta statuss. Ja operācija atbilst REST API zvanam, tas ir HTTP statusa kods.        | `200`             |
| `durationMs`      | Garš      | Neobligāti          | Darbības ilgums milisekundēs.     | `133`     |
| `callerIpAddress` | String    | Neobligāti          | Zvanītāja IP adrese, ja darbība atbilst API zvanam, kas nāk no publiski pieejamas IP adreses.                                                 | `144.318.99.233`         |
| `identity`        | String    | Neobligāti          | JSON objekts, kas apraksta tā lietotāja vai lietojumprogrammas identitāti, kurš veica operāciju.       | Skatīt [sadaļu](#identity-schema) Identitāte.     |  |
| `properties`      | String    | Neobligāti          | JSON objekts ar vairāk rekvizītiem konkrētajai notikumu kategorijai.      | Skatiet [sadaļu](#api-properties-schema) Rekvizīti.    |
| `level`           | String    | Obligāti          | Notikuma smaguma pakāpe.    | `Informational``Warning`, `Error` vai `Critical`.           |
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
| `Authorization.UserRole`      | Lietotājam vai lietotnei piešķirtā loma. Plašāku informāciju skatiet [user permissions](permissions.md).                                     |
| `Authorization.RequiredRoles` | Nepieciešamās lomas, lai veiktu operāciju. `Admin` lomai ir atļauts veikt visas operācijas.                                                    |
| `Claims`                      | Lietotāja vai lietotnes JSON tīmekļa žetona (JWT) pretenzijas. Pretenzijas rekvizīti atšķiras atkarībā no organizācijas un Azure Active Directory konfigurācijas. |

#### <a name="api-properties-schema"></a>API rekvizītu shēma

[API notikumiem](apis.md) ir šādi rekvizīti.

| Kolonna                        | Apraksts                                                                                                            |
| ---------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| `properties.eventType`       | Vienmēr `ApiEvent`, atzīmējot žurnāla notikumu kā API notikumu.                                                                 |
| `properties.userAgent`       | Pārlūkprogrammas aģents, kas nosūta pieprasījumu vai `unknown`.                                                                        |
| `properties.method`          | HTTP metode:`GET/POST/PUT/PATCH/HEAD`.                                                                                |
| `properties.path`            | Pieprasījuma relatīvais ceļš.                                                                                          |
| `properties.origin`          | URI, kas norāda, no kurienes nāk ienese `unknown` vai.                                                                  |
| `properties.operationStatus` | `Success` HTTP statusa kodam < 400 <br> `ClientError` HTTP statusa kodam < 500 <br> `Error` HTTP statusam > = 500 |
| `properties.tenantId`        | Organizācijas ID                                                                                                        |
| `properties.tenantName`      | Organizācijas nosaukums.                                                                                              |
| `properties.callerObjectId`  | Azure Active Directory Zvanītāja ObjectId.                                                                         |
| `properties.instanceId`      | Klientu ieskati`instanceId`                                                                                         |

### <a name="workflow-event-schema"></a>Darbplūsmas notikumu shēma

Darbplūsmā ir vairākas darbības. [Uzņemt datu avotus](data-sources.md), [apvienot](data-unification.md), [bagātināt](enrichment-hub.md) un [eksportēt](export-destinations.md) datus. Visas šīs darbības var veikt individuāli vai organizēt ar šādiem procesiem. 

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
| Atribūtu pasākumi | [Segmenti un mēri](segments.md)      |
| Entītiju mērījumi    | [Segmenti un mēri](segments.md)      |
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

| Kolonna           | Datatype  | Obligāts/Neobligāts | Apraksts                                                                                                                                                   | Piemērs                                                                                                                                                                  |
| --------------- | --------- | ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `time`          | Laikspiedols | Obligāti          | Notikuma laikspiedols (UTC).                                                                                                                                 | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resourceId`    | String    | Obligāti          | Notikuma emitā instances resourceId.                                                                                                            | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX` |
| `operationName` | String    | Obligāti          | Šī notikuma atveidotās operācijas nosaukums. `{OperationType}.[WorkFlow|Task][Started|Completed]`. Atsauci skatiet [operāciju](#operation-types) tipi. | `Segmentation.WorkflowStarted`,<br> `Segmentation.TaskStarted`, <br> `Segmentation.TaskCompleted`, <br> `Segmentation.WorkflowCompleted`                                 |
| `category`      | String    | Obligāti          | Notikuma žurnāla kategorija. Vienmēr `Operational` darbplūsmas notikumiem                                                                                           | `Operational`                                                                                                                                                            | 
| `resultType`    | String    | Obligāti          | Notikuma statuss. `Running`, `Skipped`, `Successful`, `Failure`                                                                                            |                                                                                                                                                                          |
| `durationMs`    | Garš      | Neobligāti          | Darbības ilgums milisekundēs.                                                                                                                    | `133`                                                                                                                                                                    |
| `properties`    | String    | Neobligāti          | JSON objekts ar vairāk rekvizītiem konkrētajai notikumu kategorijai.                                                                                        | Skatīt apakšsadaļas [Darbplūsmas rekvizīti](#workflow-properties-schema)                                                                                                       |
| `level`         | String    | Obligāti          | Notikuma smaguma pakāpe.                                                                                                                                  | `Informational`, `Warning` vai `Error`.                                                                                                                                   |
|                 |

#### <a name="workflow-properties-schema"></a>Darbplūsmas rekvizītu shēma

Darbplūsmas notikumiem ir šādi rekvizīti.

| Kolonna              | Workflow | Uzdevums | Apraksts            |
| ------------------------------- | -------- | ---- | ----------- |
| `properties.eventType`                       | Jā      | Jā  | Vienmēr `WorkflowEvent`, atzīmējot notikumu kā darbplūsmas notikumu.                                                                                                                                                                                                |
| `properties.workflowJobId`                   | Jā      | Jā  | Darbplūsmas izpildes identifikators. Visiem darbplūsmas un uzdevumu notikumiem darbplūsmas izpildē ir vienāds `workflowJobId`.                                                                                                                                   |
| `properties.operationType`                   | Jā      | Jā  | Operācijas identifikators, sk. [Operāciju tipi]. (#operation veidi)                                                                                                                                                                                       |
| `properties.tasksCount`                      | Jā      | Nē.   | Tikai darbplūsma. Darbplūsmas uzdevumu skaits.                                                                                                                                                                                                       |
| `properties.submittedBy`                     | Jā      | Nē.   | Neobligāts. Tikai darbplūsmas notikumi. Tā Azure Active Directory [lietotāja objectId,](/azure/marketplace/find-tenant-object-id#find-user-object-id) kurš izraisīja darbplūsmu, skatiet arī `properties.workflowSubmissionKind`.                                   |
| `properties.workflowType`                    | Jā      | Nē.   | `full` vai `incremental` atsvaidzināt.                                                                                                                                                                                                                            |
| `properties.workflowSubmissionKind`          | Jā      | Nē.   | `OnDemand` vai `Scheduled`.                                                                                                                                                                                                                                  |
| `properties.workflowStatus`                  | Jā      | Nē.   | `Running` vai `Successful`.                                                                                                                                                                                                                                 |
| `properties.startTimestamp`                  | Jā      | Jā  | UTC laikspiedols`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.endTimestamp`                    | Jā      | Jā  | UTC laikspiedols`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.submittedTimestamp`              | Jā      | Jā  | UTC laikspiedols`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.instanceId`                      | Jā      | Jā  | Klientu ieskati`instanceId`                                                                                                                                                                                                                              |  |
| `properties.identifier`                      | Nē.       | Jā  | - Operācijai OperationType = `Export` identifikators ir eksporta konfigurācijas GUID. <br> - OperationType = `Enrichment` tas ir bagātināšanas GUID <br> - Operācijai OperationType `Measures` un `Segmentation` identifikators ir entītijas nosaukums. |
| `properties.friendlyName`                    | Nē.       | Jā  | Lietotājam draudzīgs eksportētāja vai apstrādātās entītijas nosaukums.                                                                                                                                                                                           |
| `properties.error`                           | Nē.       | Jā  | Neobligāts. Kļūdas ziņojums ar papildinformāciju.                                                                                                                                                                                                                  |
| `properties.additionalInfo.Kind`             | Nē.       | Jā  | Neobligāts. `Export` Tikai operationType. Identificē eksporta veidu. Plašāku informāciju skatiet [pārskatā par eksporta galamērķiem](export-destinations.md).                                                                                          |
| `properties.additionalInfo.AffectedEntities` | Nē.       | Jā  | Neobligāts. `Export` Tikai operationType. Satur eksportēto konfigurēto entītiju sarakstu.                                                                                                                                                            |
| `properties.additionalInfo.MessageCode`      | Nē.       | Jā  | Neobligāts. `Export` Tikai operationType. Detalizēts ziņojums par eksportu.                                                                                                                                                                                 |
| `properties.additionalInfo.entityCount`      | Nē.       | Jā  | Neobligāts. `Segmentation` Tikai operationType. Norāda segmenta dalībnieku kopskaitu.                                                                                                                                                    |
