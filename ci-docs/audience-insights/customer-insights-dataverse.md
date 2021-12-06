---
title: Customer Insights dati Microsoft Dataverse
description: Izmantojiet Customer Insights entītijas kā tabulas programmā Microsoft Dataverse.
ms.date: 11/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 6f74559b34a95ed976a4e353c2dbabe59e1a8839
ms.sourcegitcommit: 9558ff772ee6c944fcb8db4bfc8cda13b38a1bff
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 11/29/2021
ms.locfileid: "7866943"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Darbs ar Customer Insights datiem programmā Microsoft Dataverse

Customer Insights nodrošina iespēju padarīt izvades entītijas pieejamas [programmā Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro.md). Šī integrācija ļauj viegli kopīgot datus un veikt pielāgotu izstrādi, izmantojot zema koda/bez koda pieejas. Izvades entītijas būs pieejamas kā tabulas Dataverse. Šīs tabulas iespējo scenārijus, [piemēram, automatizētas darbplūsmas, izmantojot](/power-automate/getting-started) Power Automate, [modeļa vadītas programmas un](/powerapps/maker/model-driven-apps/)[audekla](/powerapps/maker/canvas-apps/) programmas, izmantojot Power Apps. Datus var izmantot jebkurai citai lietojumprogrammai, kuras pamatā ir Dataverse tabulas. Pašreizējā ieviešanas atbalsta uzmeklēšanas, kur pieejamajiem auditorijas ieskatu entītijām var tikt fetched attiecīgā klienta ID dati.

## <a name="attach-a-dataverse-environment-to-customer-insights"></a>Dataverse vides pievienošana customer insights

**Organizācijas ar esošām Dataverse vidēm**

Organizācijas, kas jau izmanto Dataverse, var [izmantot kādu no savām esošajām Dataverse vidēm, kad administrators](create-environment.md) iestata auditorijas ieskatus. Norādot URL Dataverse vidē, tas ir saistīts ar viņu jauno auditorijas ieskatu vidi. Lai nodrošinātu vislabāko iespējamo veiktspēju, Customer Insights un Dataverse vidēm ir jābūt izvietotām tajā pašā reģionā.

**Jauna organizācija**

Ja, iestatot Customer Insights, izveidosit jaunu organizāciju, automātiski iegūsit jaunu Dataverse vidi.

> [!NOTE]
> Ja jūsu organizācijas jau izmanto Dataverse savā nomniekā, ir svarīgi atcerēties, ka [Dataverse vides izveidi kontrolē administrators](/power-platform/admin/control-environment-creation.md) . Piemēram, ja iestatāt jaunu auditorijas ieskatu vidi ar savu organizācijas kontu un administrators ir atspējojis Dataverse izmēģinājuma vides izveidi visiem, izņemot administratorus, jūs nevarat izveidot jaunu izmēģinājuma vidi.
> 
> Programmā Customer Insights izveidotajām Dataverse izmēģinājuma vidēm ir 3 GB krātuve, kas netiks ieskaitīta kopējā ietilpībā, kas ir tiesīga saņemt nomnieku. Maksas abonementi saņem Dataverse tiesības uz 15 GB datu bāzei un 20 GB failu glabāšanai.

## <a name="output-entities"></a>Izvades entītijas

Dažas izvades entītijas no auditorijas ieskatiem ir pieejamas kā tabulas programmā Dataverse. Tālāk minētās sadaļas apraksta šo tabulu paredzēto shēmu.

- [CustomerProfile](#customerprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [Bagātināšana](#enrichment)
- [Prognoze](#prediction)
- [Dalība segmentā](#segment-membership)


### <a name="customerprofile"></a>CustomerProfile

Šajā tabulā ir iekļauts vienotais klienta profils no Customer Insights. Vienotā klienta profila shēma ir atkarīga no entītijām un atribūtiem, kas tiek lietoti sapludināšanas procesā. Klienta profila shēmā parasti ir atribūtu apakškopa no [CustomerProfile Common Data Model definīcijas](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile).

### <a name="alternatekey"></a>AlternateKey

AlternateKey tabulā ir ietvertas entītiju atslēgas, kas piedalījās apvienošanas procesā.

|Kolonna  |Tips  |Apraksts  |
|---------|---------|---------|
|DataSourceName    |String         | Datu avota nosaukums. Piemērs: `datasource5`        |
|EntityName        | Virkne        | Entītijas nosaukums Audience Insights. Piemērs: `contact1`        |
|AlternateValue    |Virkne         |Alternatīvais ID, kas tiek kartēts uz klienta ID. Piemērs: `cntid_1078`         |
|KeyRing           | Vairākrindiņu teksts        | JSON vērtība  </br> Paraugs: [{"dataSourceName":" datasource5 ",</br>"entityName":" contact1",</br>"preferredKey":" cntid_1078",</br>"taustiņi":[" cntid_1078"]}]       |
|CustomerId         | String        | Vienotā klienta profila ID.         |
|AlternateKeyId     | GUID         |  AlternateKey noteicošais GUID, balstoties uz msdynci_identifier       |
|msdynci_identifier |   String      |   `DataSourceName|EntityName|AlternateValue`  </br> Paraugs: `testdatasource|contact1|cntid_1078`    |

### <a name="unifiedactivity"></a>UnifiedActivity

Šajā tabulā ir ietvertas lietotāju darbības, kas ir pieejamas programmā Customer Insights.

| Kolonna            | Tips        | Apraksts                                                                              |
|-------------------|-------------|------------------------------------------------------------------------------------------|
| CustomerId        | Virkne      | Klienta profila ID                                                                      |
| ActivityId        | Virkne      | Klienta darbības iekšējais ID (primārā atslēga)                                       |
| SourceEntityName  | Virkne      | Avota entītijas nosaukums                                                                |
| SourceActivityId  | Virkne      | Avota entītijas primārā atslēga                                                       |
| ActivityType      | Virkne      | Semantiskās darbības tips vai pielāgotas darbības nosaukums                                        |
| ActivityTimeStamp | DATETIME    | Darbības laikspiedols                                                                      |
| Uzruna             | Virkne      | Darbības pārraudzības nosaukums                                                               |
| Apraksts       | Virkne      | Darbības apraksts                                                                     |
| Vietrādis URL               | Virkne      | Saite uz ārēju URL, kas raksturīgs darbībai                                         |
| SemanticData      | JSON virkne | Ietver sarakstu ar galvenajiem vērtību pāriem semantiskās kartēšanas laukiem, kas raksturīgi darbības tipam |
| RangeIndex        | String      | Unix laikspiedols, kas tiek izmantots darbību laika skalas un efektīva diapazona vaicājumu kārtošanai |
| mydynci_unifiedactivityid   | GUID | Klienta darbības iekšējais ID (ActivityId) |

### <a name="customermeasure"></a>CustomerMeasure

Šajā tabulā ir ietverti uz klienta atribūtiem balstītu pasākumu izvades dati.

| Kolonna             | Tips             | Apraksts                 |
|--------------------|------------------|-----------------------------|
| CustomerId         | Virkne           | Klienta profila ID        |
| Mērījumi           | JSON virkne      | Ietver sarakstu ar konkrētā klienta nosaukuma un vērtību mērvienību pamatvērtību pāriem | 
| msdynci_identifier | Virkne           | `Customer_Measure|CustomerId` |
| msdynci_customermeasureid | GUID      | Klienta profila ID |


### <a name="enrichment"></a>Bagātināšana

Šajā tabulā ir ietverta bagātināšanas procesa izvade.

| Kolonna               | Tips             |  Apraksts                                          |
|----------------------|------------------|------------------------------------------------------|
| CustomerId           | Virkne           | Klienta profila ID                                 |
| EnrichmentProvider   | Virkne           | Bagātinājuma nodrošinātāja nosaukums                                  |
| EnrichmentType       | Virkne           | Bagātinājuma tips                                      |
| Vērtības               | JSON virkne      | Bagātinātā procesa radītais atribūtu saraksts |
| msdynci_enrichmentid | GUID             | Noteicošais GUID, kas izveidots no msdynci_identifier |
| msdynci_identifier   | Virkne           | `EnrichmentProvider|EnrichmentType|CustomerId`         |

### <a name="prediction"></a>Prognoze

Šajā tabulā ir ietverta bagātināšanas procesa izvade.

| Kolonna               | Tips        | Apraksts                                          |
|----------------------|-------------|------------------------------------------------------|
| CustomerId           | Virkne      | Klienta profila ID                                  |
| ModelProvider        | Virkne      | Modeļa nodrošinātāja nosaukums                                      |
| Modelis                | Virkne      | Modeļa nosaukums                                                |
| Vērtības               | JSON virkne | Modeļa radītais atribūtu saraksts |
| msdynci_predictionid | GUID        | Noteicošais GUID, kas izveidots no msdynci_identifier | 
| msdynci_identifier   | String      |  `Model|ModelProvider|CustomerId`                      |

### <a name="segment-membership"></a>Dalība segmentā

Šajā tabulā ir ietverta klientu profilu segmenta dalības informācija.

| Column        | Tipi | Apraksts                        |
|--------------------|--------------|-----------------------------|
| CustomerId        | String       | Klienta profila ID        |
| SegmentProvider      | String       | Lietotne, kas publicē segmentus. Noklusējums: auditorijas ieskati         |
| SegmentMembershipType | String       | Šī segmenta dalības ieraksta debitora tips. Atbalsta vairākus veidus, piemēram, Klients, Kontaktpersona vai Konts. Noklusējums: debitors  |
| Segmenti       | JSON virkne  | Unikālo segmentu saraksts, kurā klienta profils ir      |
| msdynci_identifier  | String   | Segmenta dalības ieraksta unikālais identifikators. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| msdynci_segmentmembershipid | GUID      | Deterministisks GUID, kas ģenerēts no`msdynci_identifier`          |
