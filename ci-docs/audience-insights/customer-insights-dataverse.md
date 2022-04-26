---
title: Customer Insights dati programmā Microsoft Dataverse
description: Izmantojiet Customer Insights entītijas kā tabulas programmā Microsoft Dataverse.
ms.date: 04/05/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: bbbbf2a7f5edb81ee75f6e33988cd4721134b6e7
ms.sourcegitcommit: 0363559a1af7ae16da2a96b09d6a4a8a53a8cbb8
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 04/05/2022
ms.locfileid: "8547635"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Darbs ar Customer Insights datiem programmā Microsoft Dataverse

Customer Insights nodrošina iespēju izvades entītijas padarīt pieejamas programmā [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro). Šī integrācija nodrošina vienkāršu datu koplietošanu un pielāgotu izstrādi, izmantojot zema koda/bez koda pieeju. Izvades [entītijas](#output-entities) ir pieejamas kā tabulas Dataverse vidē. Datus var izmantot jebkurai citai lietojumprogrammai, pamatojoties uz Dataverse tabulām. Šīs tabulas iespējo scenārijus, piemēram, automatizētas darbplūsmas, izmantojot Power Automate vai veidojot programmas ar Power Apps. Pašreizējā implementācija galvenokārt atbalsta uzmeklēšanas, kurās datus no pieejamajām Customer Insights entītijām var paņemt konkrētam klienta ID.

## <a name="attach-a-dataverse-environment-to-customer-insights"></a>Dataverse vides pievienošana Customer Insights

**Esoša organizācija**

Administratori var konfigurēt Customer Insights, lai [izmantotu esošu Dataverse vidi](create-environment.md), kad tie izveido Customer Insights vidi. Nodrošinot Dataverse vides URL, tas tiek piesaistīts jaunajai auditorijas ieskatu videi. Customer Insights un Dataverse vides ir jāvieso vienā reģionā. 

Ja nevēlaties izmantot esošu Dataverse vidi, sistēma nomniekā izveido jaunu vidi Customer Insights datiem. 

> [!NOTE]
> Ja jūsu organizācijas jau izmanto Dataverse savā nomniekā, ir svarīgi atcerēties, ka [Dataverse vides izveidi kontrolē administrators](/power-platform/admin/control-environment-creation). Piemēram, ja iestatāt jaunu auditorijas ieskatu vidi ar jūsu organizācijas kontu un administrators ir atspējojis izmēģinājumversijas vidi izveidi ikvienam, izņemot administratorus, jūs nevarat izveidot jaunu Dataverse izmēģinājumversijas vidi.
> 
> Pakalpojumā Customer Insights izveidotajā Dataverse izmēģinājumversijas krātuvē ir 3 GB, kas netiek rēķināts ar nomnieka kopējo noslodzi. Apmaksātiem abonementiem ir Dataverse tiesības uz 15 GB datu bāzi un 20 GB lielu failu krātuvi.

**Jauna organizācija**

Ja, iestatot Customer Insights, izveidojat jaunu organizāciju, sistēma automātiski izveido jums jaunu Dataverse vidi jūsu organizācijā.

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
|CustomerId         | Virkne        | Vienotā klienta profila ID.         |
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

Šajā tabulā ir norādīta informācija par klientu profilu dalību segmentā.

| Column        | Tipi | Apraksts                        |
|--------------------|--------------|-----------------------------|
| CustomerId        | String       | Klienta profila ID        |
| SegmentProvider      | String       | Lietotne, kas publicē segmentus. Noklusējums: ieskati auditorijā         |
| SegmentMembershipType | String       | Debitora tips šī segmenta dalības ieraksts. Atbalsta vairākus tipus, piemēram, Klients, Kontaktpersona vai Konts. Noklusējums: Debitors  |
| Segmenti       | JSON virkne  | Unikālo segmentu saraksts, kuros klienta profils ir dalībnieks      |
| msdynci_identifier  | String   | Segmenta dalības ieraksta unikālais identifikators. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| msdynci_segmentmembershipid | GUID      | Deterministisks GUID ģenerēts no`msdynci_identifier`          |
