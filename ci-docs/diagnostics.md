---
title: Diagnostikas žurnālu eksportēšana (priekšskatījums)
description: Uzziniet, kā nosūtīt žurnālus uz monitoru Microsoft Azure.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: article
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 60b039173fd938482c782c7394420d4951c222a7
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245934"
---
# <a name="export-diagnostic-logs-preview"></a>Diagnostikas žurnālu eksportēšana (priekšskatījums)

Pārsūtiet žurnālus no Customer Insights, izmantojot Azure monitoru. Azure monitora resursu žurnāli ļauj pārraudzīt un nosūtīt žurnālus uz [Azure krātuvi](https://azure.microsoft.com/services/storage/), [Azure žurnālu analīzi](/azure/azure-monitor/logs/log-analytics-overview) vai straumēt tos uz [Azure notikumu centrmezgliem](https://azure.microsoft.com/services/event-hubs/).

Customer Insights sūta šādus notikumu žurnālus:

- **Revīzijas notikumi**
  - **APIEvent** - iespējo izmaiņu izsekošanu, Dynamics 365 Customer Insights izmantojot lietotāja saskarni.
- **Operatīvie notikumi**
  - **WorkflowEvent** - ļauj iestatīt [datu avotus](data-sources.md), [apvienot](data-unification.md), [bagātināt](enrichment-hub.md) un [eksportēt](export-destinations.md) datus uz citām sistēmām. Šīs darbības var veikt individuāli (piemēram, aktivizēt vienu eksportēšanu). Viņi var arī palaist orķestrētus (piemēram, datu atsvaidzināšana no datu avotiem, kas aktivizē apvienošanas procesu, kas piesaistīs bagātinājumus un eksportēs datus uz citu sistēmu). Papildinformāciju [skatiet workflowEvent shēmā](#workflow-event-schema).
  - **APIEvent** - nosūta visus klientu instances API zvanus uz Dynamics 365 Customer Insights. Papildinformāciju [skatiet APIEvent shēmā](#api-event-schema).

## <a name="set-up-the-diagnostic-settings"></a>Diagnostikas iestatījumu iestatīšana

### <a name="prerequisites"></a>Priekšnoteikumi

- Aktīvs [Azure abonements](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/).
- [Administratora](permissions.md#admin) atļaujas programmā Customer Insights.
- [Līdzstrādnieka un lietotāja piekļuves administratora loma](/azure/role-based-access-control/role-assignments-portal) galamērķa resursā pakalpojumā Azure. Resurss var būt Azure Data Lake Storage konts, Azure notikumu centrmezgls vai Azure žurnālu analīzes darbvieta. Šī atļauja ir nepieciešama, konfigurējot diagnostikas iestatījumus programmā Customer Insights, taču pēc veiksmīgas iestatīšanas to var mainīt.
- [Ir izpildītas galamērķa prasības](/azure/azure-monitor/platform/diagnostic-settings#destination-requirements) Azure krātuvei, Azure notikumu centrmezglam vai Azure žurnālu analīzei.
- Vismaz lasītāja **loma** resursu grupā, kurai pieder resurss.

### <a name="set-up-diagnostics-with-azure-monitor"></a>Diagnostikas iestatīšana, izmantojot Azure monitoru

1. Programmā Customer Insights dodieties uz **Administrēšanas** > **sistēma** un atlasiet **cilni Diagnostika**.

1. Atlasiet **Pievienot galamērķi**.

   :::image type="content" source="media/diagnostics-pane.png" alt-text="Diagnostikas savienojums.":::

1. Laukā Nosaukums diagnostikas galamērķim **norādiet nosaukumu**.

1. Atlasiet veidu **Resurss**(krātuves konts, notikumu centrmezgls vai žurnālu analīze).

1. Atlasiet mērķa resursa **abonementu** **, resursu grupu** un **resursu**. Skatiet rakstu [Konfigurācija mērķa resursā](#configuration-on-the-destination-resource), lai iegūtu atļauju un žurnāla informāciju.

1. Pārskatiet datu privātumu [un atbilstību](connections.md#data-privacy-and-compliance) un atlasiet **Es piekrītu**.

1. Atlasiet **Izveidot savienojumu ar sistēmu**, lai izveidotu savienojumu ar mērķa resursu. Žurnāli sāk parādīties galamērķī pēc 15 minūtēm, ja API tiek izmantots un ģenerē notikumus.

## <a name="configuration-on-the-destination-resource"></a>Konfigurācija mērķa resursā

Pamatojoties uz jūsu izvēlēto resursa veidu, automātiski tiek veiktas tālāk norādītās izmaiņas.

### <a name="storage-account"></a>Krātuves konts

Customer Insights pakalpojuma vadītājs saņem krātuves **konta līdzstrādnieka** atļauju atlasītajam resursam un izveido divus konteinerus zem atlasītās nosaukumvietas:

- `insight-logs-audit` kurā ietverti **revīzijas notikumi**
- `insight-logs-operational` kas ietver **operatīvus notikumus**

### <a name="event-hub"></a>Notikumu centrmezgls

Customer Insights pakalpojuma vadītājs saņem **Azure Notikumu centrmezglu datu īpašnieka** atļauju resursā un izveido divus notikumu centrmezglus zem atlasītās nosaukumvietas:

- `insight-logs-audit` kurā ietverti **revīzijas notikumi**
- `insight-logs-operational` kas ietver **operatīvus notikumus**

### <a name="log-analytics"></a>Žurnālu analīze

Customer Insights pakalpojuma vadītājs saņem žurnālu **analīzes līdzstrādnieka** atļauju attiecībā uz resursu. Žurnāli ir pieejami sadaļā **Žurnālu** > **tabulu** > **žurnālu pārvaldība** atlasītajā žurnālu analīzes darbvietā. Izvērsiet žurnālu **pārvaldības** risinājumu un atrodiet `CIEventsAudit` tabulas un `CIEventsOperational` tabulas.

- `CIEventsAudit` kurā ietverti **revīzijas notikumi**
- `CIEventsOperational` kas ietver **operatīvus notikumus**

**Logā Vaicājumi** izvērsiet audita **risinājumu** un atrodiet vaicājumu piemērus, kas tiek nodrošināti, meklējot `CIEvents`.

## <a name="remove-a-diagnostics-destination"></a>Diagnostikas mērķa noņemšana

1. Dodieties uz administrēšanas sistēma un atlasiet **cilni Diagnostika** > **.** **·**

1. Sarakstā atlasiet diagnostikas galamērķi.

   > [!TIP]
   > Noņemot mērķi, tiek apturēta žurnāla pārsūtīšana, bet netiek dzēsts resurss Azure abonementā. Lai izdzēstu resursu pakalpojumā Azure, atlasiet saiti **kolonnā Darbības**, lai atlasītajam resursam atvērtu Azure portālu un izdzēstu to tur. Pēc tam izdzēsiet diagnostikas mērķi.

1. **Kolonnā Darbības** atlasiet **ikonu Dzēst**.

1. Apstipriniet dzēšanu, lai noņemtu galamērķi, un pārtrauciet žurnāla pārsūtīšanu.

## <a name="log-categories-and-event-schemas"></a>Žurnālu kategorijas un notikumu shēmas

Pašlaik [tiek atbalstīti API notikumi](apis.md) un darbplūsmas notikumi, un tiek lietotas tālāk norādītās kategorijas un shēmas.
Žurnāla shēma seko Azure Monitor kopējai [shēmai](/azure/azure-monitor/platform/resource-logs-schema#top-level-common-schema).

### <a name="categories"></a>Kategorijas

Customer Insights piedāvā divas kategorijas:

- **Audita notikumi**: [API notikumi](#api-event-schema), lai izsekotu konfigurācijas izmaiņām pakalpojumā. `POST|PUT|DELETE|PATCH` operācijas ietilpst šajā kategorijā.
- **Darbības notikumi**: [API notikumi](#api-event-schema) vai [darbplūsmas notikumi](#workflow-event-schema), kas ģenerēti, izmantojot pakalpojumu.  Piemēram, `GET` darbplūsmas pieprasījumi vai izpildes notikumi.

## <a name="event-schemas"></a>Notikumu shēmas

API notikumiem un darbplūsmas notikumiem ir kopīga struktūra, taču ar dažām atšķirībām. Papildinformāciju skatiet sadaļā [API notikumu shēma](#api-event-schema) vai [darbplūsmas](#workflow-event-schema) notikumu shēma.

### <a name="api-event-schema"></a>API notikumu shēma

| Kolonna             | Datatype  | Obligāts/pēc izvēles | Apraksts       | Piemērs        |
| ----------------- | --------- | ----------------- | --------------------- | ------------------------ |
| `time`            | Laikspiedols | Obligāti          | Pasākuma laikspiedols (UTC)       | `2020-09-08T09:48:14.8050869Z`         |
| `resourceId`      | String    | Obligāti          | Tās instances resurssId, kas izstaroja notikumu         | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX`  |
| `operationName`   | String    | Obligāti          | Šī notikuma pārstāvētās operācijas nosaukums.                                                                                                                | `Workflows.GetWorkFlowStatusAsync`                                                                                                                                       |
| `category`        | String    | Obligāti          | Pasākuma žurnāla kategorija. Vai nu `Operational`, vai `Audit`. Visi POST/PUT/PATCH/DELETE HTTP pieprasījumi ir atzīmēti ar `Audit`, viss pārējais ar`Operational` | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resultType`      | String    | Obligāti          | Pasākuma statuss. `Success`, `ClientError`, `Failure`                                                                                                        |                                                                                                                                                                          |
| `resultSignature` | String    | Neobligāti          | Notikuma rezultāta statuss. Ja darbība atbilst REST API zvanam, tas ir HTTP statusa kods.        | `200`             |
| `durationMs`      | Garš      | Neobligāti          | Darbības ilgums milisekundēs.     | `133`     |
| `callerIpAddress` | String    | Neobligāti          | Zvanītāja IP adrese, ja darbība atbilst API zvanam, kas nāk no publiski pieejamas IP adreses.                                                 | `144.318.99.233`         |
| `identity`        | String    | Neobligāti          | JSON objekts, kas apraksta tā lietotāja vai lietojumprogrammas identitāti, kurš veica darbību.       | Skatiet [sadaļu Identitāte](#identity-schema).     |  
| `properties`      | String    | Neobligāti          | JSON objekts ar vairāk rekvizītiem konkrētajai notikumu kategorijai.      | Skatiet [sadaļu Rekvizīti](#api-properties-schema).    |
| `level`           | String    | Obligāti          | Notikuma smaguma pakāpe.    | `Informational`, `Warning`,, `Error`, vai `Critical`.           |
| `uri`             | String    | Neobligāti          | Absolūtais pieprasījums URI.    |               |

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
| `Authorization.RequiredRoles` | Nepieciešamās lomas, lai veiktu operāciju. `Admin` loma ir atļauta, lai veiktu visas operācijas.                                                    |
| `Claims`                      | Apgalvojumi par lietotāju vai lietotnes JSON tīmekļa marķieri (JWT). Pretenziju rekvizīti atkarībā no organizācijas un konfigurācijas Azure Active Directory atšķiras. |

#### <a name="api-properties-schema"></a>API rekvizītu shēma

[API notikumiem](apis.md) ir šādi rekvizīti.

| Kolonna                        | Apraksts                                                                                                            |
| ---------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| `properties.eventType`       | Vienmēr `ApiEvent`, atzīmējot žurnāla notikumu kā API notikumu.                                                                 |
| `properties.userAgent`       | Pārlūkprogrammas aģents, kas nosūta pieprasījumu vai `unknown`.                                                                        |
| `properties.method`          | HTTP metode:`GET/POST/PUT/PATCH/HEAD`.                                                                                |
| `properties.path`            | Pieprasījuma relatīvais ceļš.                                                                                          |
| `properties.origin`          | URI, kas norāda, no kurienes nāk atnesums vai `unknown`.                                                                  |
| `properties.operationStatus` | `Success` HTTP statusa kodam < 400 <br> `ClientError` HTTP statusa kodam < 500 <br> `Error` HTTP statusam >= 500 |
| `properties.tenantId`        | Organizācijas ID                                                                                                        |
| `properties.tenantName`      | Organizācijas nosaukums.                                                                                              |
| `properties.callerObjectId`  | Azure Active Directory Zvanītāja objektsId.                                                                         |
| `properties.instanceId`      | Customer Insights`instanceId`                                                                                         |

### <a name="workflow-event-schema"></a>Darbplūsmas notikumu shēma

Darbplūsmā ir vairākas darbības. [Iegūstiet datu avotus](data-sources.md), [apvienojiet](data-unification.md), [bagātiniet](enrichment-hub.md) un [eksportējiet](export-destinations.md) datus. Visas šīs darbības var darboties atsevišķi vai organizēt ar šādiem procesiem.

#### <a name="operation-types"></a>Darbības veidi

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
| Atribūtu pasākumi | [Segmenti un pasākumi](segments.md)      |
| Entītijas pasākumi    | [Segmenti un pasākumi](segments.md)      |
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

| Kolonna           | Datatype  | Obligāts/pēc izvēles | Apraksts                                                                                                                                                   | Piemērs                                                                                                                                                                  |
| --------------- | --------- | ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `time`          | Laikspiedols | Obligāti          | Pasākuma laika zīmogs (UTC).                                                                                                                                 | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resourceId`    | String    | Obligāti          | ResurssId no instances, kas izstaroja notikumu.                                                                                                            | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX` |
| `operationName` | String    | Obligāti          | Šī notikuma pārstāvētās operācijas nosaukums. `{OperationType}.[WorkFlow|Task][Started|Completed]`. Atsaucei skatiet [sadaļu Darbību veidi](#operation-types). | `Segmentation.WorkflowStarted`,<br> `Segmentation.TaskStarted`, <br> `Segmentation.TaskCompleted`, <br> `Segmentation.WorkflowCompleted`                                 |
| `category`      | String    | Obligāti          | Pasākuma žurnāla kategorija. Vienmēr `Operational` darbplūsmas notikumiem                                                                                           | `Operational`                                                                                                                                                            |
| `resultType`    | String    | Obligāti          | Pasākuma statuss. `Running`, `Skipped`, `Successful`, `Failure`                                                                                            |                                                                                                                                                                          |
| `durationMs`    | Garš      | Neobligāti          | Darbības ilgums milisekundēs.                                                                                                                    | `133`                                                                                                                                                                    |
| `properties`    | String    | Neobligāti          | JSON objekts ar vairāk rekvizītiem konkrētajai notikumu kategorijai.                                                                                        | Skatīt apakšsadaļu [Darbplūsmas rekvizīti](#workflow-properties-schema)                                                                                                       |
| `level`         | String    | Obligāti          | Notikuma smaguma pakāpe.                                                                                                                                  | `Informational`, `Warning` vai `Error`.                                                                                                                                   |

#### <a name="workflow-properties-schema"></a>Darbplūsmas rekvizītu shēma

Darbplūsmas notikumiem ir šādi rekvizīti.

| Kolonna              | Workflow | Uzdevums | Apraksts            |
| ------------------------------- | -------- | ---- | ----------- |
| `properties.eventType`                       | Jā      | Jā  | Vienmēr `WorkflowEvent`, atzīmējot notikumu kā darbplūsmas notikumu.                                                                                                                                                                                                |
| `properties.workflowJobId`                   | Jā      | Jā  | Darbplūsmas izpildes identifikators. Visiem darbplūsmas un uzdevumu notikumiem darbplūsmas izpildē ir vienāds `workflowJobId`.                                                                                                                                   |
| `properties.operationType`                   | Jā      | Jā  | Operācijas identifikators, skatiet sadaļu [Darbību tipi](#operation-types).                                                                                                                                                                               |
| `properties.tasksCount`                      | Jā      | Nē.   | Tikai darbplūsma. Uzdevumu skaits, ko aktivizē darbplūsma.                                                                                                                                                                                                       |
| `properties.submittedBy`                     | Jā      | Nē.   | Neobligāts. Tikai darbplūsmas notikumi. Tā Azure Active Directory [lietotāja](/azure/marketplace/find-tenant-object-id#find-user-object-id) objektsId, kurš aktivizēja darbplūsmu, skatiet arī `properties.workflowSubmissionKind`.                                   |
| `properties.workflowType`                    | Jā      | Nē.   | `full` vai `incremental` atsvaidzināt.                                                                                                                                                                                                                            |
| `properties.workflowSubmissionKind`          | Jā      | Nē.   | `OnDemand` vai `Scheduled`.                                                                                                                                                                                                                                  |
| `properties.workflowStatus`                  | Jā      | Nē.   | `Running` vai `Successful`.                                                                                                                                                                                                                                 |
| `properties.startTimestamp`                  | Jā      | Jā  | UTC laika zīmogs`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.endTimestamp`                    | Jā      | Jā  | UTC laika zīmogs`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.submittedTimestamp`              | Jā      | Jā  | UTC laika zīmogs`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.instanceId`                      | Jā      | Jā  | Customer Insights`instanceId`                                                                                                                                                                                                                              |  
| `properties.identifier`                      | Nē.       | Jā  | - OperationType = `Export`, identifikators ir eksporta konfigurācijas guid. <br> - OperācijaiType = `Enrichment`, tas ir bagātināšanas guid <br> - OperationType `Measures` un `Segmentation`, identifikators ir entītijas nosaukums. |
| `properties.friendlyName`                    | Nē.       | Jā  | Lietotājdraudzīgs eksportēšanas vai apstrādātās entītijas nosaukums.                                                                                                                                                                                           |
| `properties.error`                           | Nē.       | Jā  | Neobligāts. Kļūdas ziņojums ar papildinformāciju.                                                                                                                                                                                                                  |
| `properties.additionalInfo.Kind`             | Nē.       | Jā  | Neobligāts. Tikai OperācijaiType `Export`. Identificē eksportēšanas veidu. Papildinformāciju skatiet rakstā [Pārskats par eksporta galamērķiem](export-destinations.md).                                                                                          |
| `properties.additionalInfo.AffectedEntities` | Nē.       | Jā  | Neobligāts. Tikai OperācijaiType `Export`. Satur eksportējamo entītiju sarakstu.                                                                                                                                                            |
| `properties.additionalInfo.MessageCode`      | Nē.       | Jā  | Neobligāts. Tikai OperācijaiType `Export`. Detalizēts ziņojums par eksportu.                                                                                                                                                                                 |
| `properties.additionalInfo.entityCount`      | Nē.       | Jā  | Neobligāts. Tikai OperācijaiType `Segmentation`. Norāda kopējo dalībnieku skaitu, kas ir segmentā.                                                                                                                                                    |

[!INCLUDE [footer-include](includes/footer-banner.md)]
