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
ms.openlocfilehash: 1e629cd218b104b115f74f59a53a14e9d60fcc8a
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741374"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Darbs ar Customer Insights datiem programmā Microsoft Dataverse

Customer Insights nodrošina iespēju izvades entītijas padarīt pieejamas programmā [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro). Šī integrācija nodrošina ērtu datu koplietošanu un pielāgotu izstrādi, izmantojot zema koda/bez koda pieeju. Izvades [entītijas](#output-entities) ir pieejamas kā tabulas vidē Dataverse. Datus var izmantot jebkurai citai lietojumprogrammai, pamatojoties uz tabulām Dataverse. Šīs tabulas iespējo tādus scenārijus kā automatizētas darbplūsmas, izmantojot Power Automate vai veidojot programmas ar Power Apps. Pašreizējā ieviešana galvenokārt atbalsta uzmeklēšanu, kur pieejamo Customer Insights entītiju datus var iegūt par noteiktu klienta ID.

## <a name="attach-a-dataverse-environment-to-customer-insights"></a>Dataverse vides pievienošana Customer Insights

**Esošā organizācija**

Administratori var konfigurēt Customer Insights, lai [izmantotu esošu Dataverse vidi](create-environment.md), veidojot Customer Insights vidi. Nodrošinot vietrādi URL Dataverse videi, tas tiek pievienots viņu jaunajai Customer Insights videi. Klientu ieskatiem un Dataverse vidēm jābūt viesotām vienā reģionā. 

Ja nevēlaties izmantot esošu Dataverse vidi, sistēma nomniekā izveido jaunu vidi Customer Insights datiem. 

> [!NOTE]
> Ja jūsu organizācijas jau izmanto Dataverse savā nomniekā, ir svarīgi atcerēties, ka [Dataverse vides izveidi kontrolē administrators](/power-platform/admin/control-environment-creation). Piemēram, ja iestatāt jaunu Customer Insights vidi ar savu organizācijas kontu un administrators ir atspējojis izmēģinājuma vides izveidi Dataverse visiem, izņemot administratorus, nevar izveidot jaunu izmēģinājuma vidi, nevar izveidot jaunu izmēģinājuma vidi.
> 
> Pakalpojumā Customer Insights izveidotajā Dataverse izmēģinājumversijas krātuvē ir 3 GB, kas netiek rēķināts ar nomnieka kopējo noslodzi. Apmaksātiem abonementiem ir Dataverse tiesības uz 15 GB datu bāzi un 20 GB lielu failu krātuvi.

**Jauna organizācija**

Ja, iestatot Customer Insights, izveidojat jaunu organizāciju, sistēma automātiski izveido jaunu Dataverse vidi jūsu organizācijā.

## <a name="output-entities"></a>Izvades entītijas

Dažas Customer Insights izvades entītijas ir pieejamas kā tabulas programmā Dataverse. Tālāk minētās sadaļas apraksta šo tabulu paredzēto shēmu.

- [CustomerProfile](#customerprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [Bagātināšana](#enrichment)
- [Prognoze](#prediction)
- [Segmenta dalība](#segment-membership)


### <a name="customerprofile"></a>CustomerProfile

Šajā tabulā ir iekļauts vienotais klienta profils no Customer Insights. Vienota klienta profila shēma ir atkarīga no entītijām un atribūtiem, kas izmantoti datu apvienošanas procesā. Klienta profila shēmā parasti ir atribūtu apakškopa no [CustomerProfile Common Data Model definīcijas](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile).

### <a name="alternatekey"></a>AlternateKey

AlternateKey tabulā ir ietvertas entītiju atslēgas, kas piedalījās apvienošanas procesā.

|Kolonna  |Tips  |Apraksts  |
|---------|---------|---------|
|DataSourceName    |String         | Datu avota nosaukums. Piemērs: `datasource5`        |
|EntityName        | String        | Entītijas nosaukums customer insights. Piemērs: `contact1`        |
|AlternateValue    |String         |Alternatīvais ID, kas tiek kartēts uz klienta ID. Piemērs: `cntid_1078`         |
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

### <a name="segment-membership"></a>Segmenta dalība

Šajā tabulā ir ietverta informācija par segmenta dalību debitoru profilos.

| Column        | Tipi | Apraksts                        |
|--------------------|--------------|-----------------------------|
| CustomerId        | String       | Klienta profila ID        |
| SegmentProvider      | String       | Lietotne, kas publicē segmentus.      |
| SegmentamembershipType | String       | Šī segmenta dalības ieraksta debitora tips. Atbalsta vairākus tipus, piemēram, Klientu, Kontaktpersonu vai Uzņēmumu. Noklusējums: debitors  |
| Segmenti       | JSON virkne  | Unikālo segmentu saraksts, kuros dalībnieks ir klienta profils      |
| msdynci_identifier  | String   | Segmenta dalības ieraksta unikālais identifikators. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| msdynci_segmentmembershipid | GUID      | Deterministiska GUID, kas ģenerēta no`msdynci_identifier`          |
