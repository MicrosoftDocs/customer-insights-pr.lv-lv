---
title: Darbs ar Customer Insights datiem programmā Microsoft Dataverse
description: Uzziniet, kā izveidot savienojumu ar Customer Insights Microsoft Dataverse un izprast izvades entītijas, uz kurām tiek eksportētas Dataverse.
ms.date: 08/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: dfa63110fc5291f2b63aebf588d6fdd20ed4ab67
ms.sourcegitcommit: 134aac66e3e0b77b2e96a595d6acbb91bf9afda2
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 09/07/2022
ms.locfileid: "9424318"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Darbs ar Customer Insights datiem programmā Microsoft Dataverse

Customer Insights nodrošina iespēju izvades entītijas padarīt pieejamas programmā [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro). Šī integrācija nodrošina vieglu datu koplietošanu un pielāgotu izstrādi, izmantojot zema koda / bez koda pieeju. Izvades [entītijas](#output-entities) ir pieejamas kā tabulas Dataverse vidē. Datus var izmantot jebkurai citai lietojumprogrammai, kuras pamatā Dataverse ir tabulas. Šajās tabulās ir iespējoti tādi scenāriji kā automatizētas darbplūsmas, izmantojot Power Automate vai veidojot programmas ar Power Apps.

Savienojuma izveide ar jūsu Dataverse vidi arī ļauj [uzņemt datus no lokāls datu avotiem, izmantojot Power Platform datu plūsmas un vārtejas](connect-power-query.md#add-data-from-on-premises-data-sources).

## <a name="prerequisites"></a>Priekšnoteikumi

- Customer Insights un Dataverse vides ir jāmitina vienā un tajā pašā reģionā.
- Globāla administratora loma, kas iestatīta Dataverse vidē. Pārbaudiet, vai šī [Dataverse vide ir saistīta ar](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) noteiktām drošības grupām, un pārliecinieties, vai esat pievienots šīm drošības grupām.
- Neviena cita Customer Insights vide jau nav saistīta ar vidi, Dataverse ar kuru vēlaties izveidot savienojumu. Uzziniet, [kā noņemt esošu savienojumu ar Dataverse vidi](#remove-an-existing-connection-to-a-dataverse-environment).
- Vide Microsoft Dataverse, kas savienota ar vienu krātuves kontu, ja konfigurējat vidi, lai [izmantotu savu Azure Data Lake Storage](own-data-lake-storage.md).

## <a name="dataverse-storage-capacity-entitlement"></a>Dataverse tiesības uz uzglabāšanas ietilpību

Customer Insights abonements dod jums papildu noslodzi jūsu organizācijas esošajai [Dataverse krātuves ietilpībai](/power-platform/admin/capacity-storage). Pievienotā noslodze ir atkarīga no profilu skaita, ko izmanto jūsu abonements.

**Piemērs:**

Pieņemot, ka saņemat 15 GB datu bāzes krātuvi un 20 GB failu krātuvi uz 100 000 klientu profiliem. Ja abonementā ir iekļauti 300 000 klientu profilu, kopējā krātuves ietilpība ir 45 GB (3 x 15 GB) datu bāzes krātuve un 60 GB failu krātuve (3 x 20 GB). Līdzīgi, ja jums ir B-to-B abonements ar 30K kontiem, jūsu kopējā krātuves ietilpība ir 45 GB (3 x 15 GB) datu bāzes krātuve un 60 GB failu krātuve (3 x 20 GB).

Žurnāla noslodze nav pakāpeniska un fiksēta jūsu organizācijai.

Papildinformāciju par detalizētām noslodzes pilnvarām skatiet rakstā [Dynamics 365 licencēšanas rokasgrāmata](https://go.microsoft.com/fwlink/?LinkId=866544).

## <a name="connect-a-dataverse-environment-to-customer-insights"></a>Vides savienošana ar Dataverse Customer Insights

Šī **Microsoft Dataverse** darbība ļauj savienot Customer Insights ar savu Dataverse vidi, vienlaikus [izveidojot Customer Insights vidi](create-environment.md).

:::image type="content" source="media/dataverse-provisioning.png" alt-text="datu koplietošana, izmantojot Microsoft Dataverse automātisko iespējošanu jaunām vidēm.":::

1. Norādiet vietrādi URL savā Dataverse vidē vai atstājiet tukšu, lai tāds tiktu izveidots jūsu vietā.

   > [!NOTE]
   > Pēc savienojuma izveidošanas starp Customer Insights un Dataverse, nemainiet vides organizācijas nosaukumu Dataverse. Organizācijas nosaukums tiek izmantots vietrādī URL, Dataverse un mainīts nosaukums pārtrauc savienojumu ar Customer Insights.

   [Power Platform administratori var kontrolēt, kurš var izveidot jaunu Dataverse vidi](/power-platform/admin/control-environment-creation). Ja mēģināt iestatīt jaunu Customer Insights vidi un nevarat, administrators, iespējams, ir atspējojis vides izveidi Dataverse visiem, izņemot administratorus.

1. Ja izmantojat savu Datu ezera krātuves kontu:
   1. Atlasiet **Iespējot datu koplietošanu** ar Dataverse.
   1. **Ievadiet atļauju identifikatoru**. Lai iegūtu atļaujas identifikatoru, [iespējojiet datu koplietošanu ar Dataverse savu Azure Data Lake Storage](#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview).

## <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>Datu koplietošanas iespējošana ar Dataverse savu Azure Data Lake Storage (priekšskatījums)

[Savā Azure Data Lake Storage kontā](own-data-lake-storage.md) pārbaudiet, vai lietotājam, kurš iestata Customer Insights vidi, krātuves kontā esošajā konteinerā ir vismaz **krātuves** Blob datu lasītāja`customerinsights` atļaujas.

### <a name="limitations"></a>Ierobežojumi

- Tikai viens pret vienu kartēšana starp Dataverse organizāciju un Azure Data Lake Storage kontu. Kad organizācija ir Dataverse savienota ar krātuves kontu, tā nevar izveidot savienojumu ar citu krātuves kontu. Šis ierobežojums neļauj Dataverse aizpildīt vairākus krātuves kontus.
- Datu kopīgošana nedarbosies, ja, lai piekļūtu jūsu Azure Data Lake Storage kontam, ir nepieciešama Azure privātās saites iestatīšana, jo tas atrodas aiz ugunsmūra. Dataverse pašlaik neatbalsta savienojumu ar privātiem galapunktiem, izmantojot Private Link.

### <a name="set-up-security-groups-on-your-own-azure-data-lake-storage"></a>Drošības grupu iestatīšana patstāvīgi Azure Data Lake Storage

1. Izveidojiet savā Azure abonementā divas drošības grupas — vienu **Reader** drošības grupu un vienu **līdzstrādnieku** drošības grupu un iestatiet Microsoft Dataverse pakalpojumu kā īpašnieku abām drošības grupām.

1. Pārvaldiet piekļuves kontroles sarakstu (Access Control List — ACL) savā krātuves konta konteinerā, `customerinsights` izmantojot šīs drošības grupas.
   1. Microsoft Dataverse Pievienojiet pakalpojumu un visas Dataverse biznesa lietojumprogrammas, piemēram, Dynamics 365 Marketing, **drošības grupai Reader**, izmantojot **tikai** lasīšanas atļaujas.
   1. Pievienojiet *tikai* lietojumprogrammu Customer Insights līdzstrādnieku **drošības** grupai, lai piešķirtu gan lasīšanas, gan **rakstīšanas** atļaujas profilu un ieskatu rakstīšanai.

### <a name="set-up-powershell"></a>PowerShell iestatīšana

Iestatiet PowerShell, lai izpildītu PowerShell skriptus.

1. Instalējiet jaunāko PowerShell for Graph [Azure Active Directory versiju](/powershell/azure/active-directory/install-adv2).
   1. Datorā atlasiet tastatūras taustiņu Windows un meklējiet **Windows PowerShell** un atlasiet opciju **Palaist kā administratoram**.
   1. PowerShell logā, kas tiek atvērts, ievadiet `Install-Module AzureAD`.

1. Importējiet trīs moduļus.
   1. PowerShell logā ievadiet `Install-Module -Name Az.Accounts` un izpildiet norādītās darbības.
   1. Atkārtojiet par `Install-Module -Name Az.Resources` un `Install-Module -Name Az.Storage`.

### <a name="execute-powershell-scripts-and-obtain-the-permission-identifier"></a>PowerShell skriptu izpilde un atļaujas identifikatora iegūšana

1. Lejupielādējiet divus PowerShell skriptus, kas jums jādarbina no mūsu inženiera [GitHub repo](https://github.com/trin-msft/byol).
   - `CreateSecurityGroups.ps1`: Nepieciešamas nomnieka administratora atļaujas.
   - `ByolSetup.ps1`: Nepieciešama krātuves Blob datu īpašnieka atļauja krātuves konta/konteinera līmenī. Šis skripts izveidos jums atļauju. Pēc veiksmīgas skripta palaišanas jūsu lomas piešķiršanu var noņemt manuāli.

1. Izpildiet `CreateSecurityGroups.ps1` programmā Windows PowerShell, norādot Azure abonementa ID, kas satur jūsu Azure Data Lake Storage. Redaktorā atveriet PowerShell skriptu, lai pārskatītu papildinformāciju un īstenoto loģiku.

   Ar šo skriptu jūsu Azure abonementā tiek izveidotas divas drošības grupas: viena grupai Lasītājs un otra — līdzstrādnieku grupai. Microsoft Dataverse pakalpojums ir īpašnieks abām šīm drošības grupām.

1. Saglabājiet abas drošības grupas ID vērtības, ko ģenerē šis skripts `ByolSetup.ps1`, lai tās izmantotu skriptā.

   > [!NOTE]
   > Nomniekā var atspējot drošības grupas izveidi. Tādā gadījumā būtu nepieciešama manuāla iestatīšana, un administratoram Azure AD būtu jāiespējo [drošības grupas izveide](/azure/active-directory/enterprise-users/groups-self-service-management).

1. Izpildiet `ByolSetup.ps1` programmā Windows PowerShell, norādot Azure abonementa ID, kurā ir jūsu Azure Data Lake Storage, krātuves konta nosaukums, resursu grupas nosaukums un lasītāja un līdzstrādnieka drošības grupas ID vērtības. Redaktorā atveriet PowerShell skriptu, lai pārskatītu papildinformāciju un īstenoto loģiku.

   Šis skripts pievieno nepieciešamo uz lomām balstīto piekļuves kontroli pakalpojumam Microsoft Dataverse un visām Dataverse biznesa lietojumprogrammām. Tas arī atjaunina piekļuves kontroles sarakstu (Access Control List — ACL) konteinerā `customerinsights` drošības grupām, kas izveidotas ar skriptu `CreateSecurityGroups.ps1`. Līdzstrādnieku grupai tiek piešķirta *rwx* atļauja, un lasītāju grupai tiek piešķirta *tikai r-x* atļauja.

1. Kopējiet izvades virkni, kas izskatās šādi: `https://DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`

1. Ievadiet kopēto izvades virkni **vides konfigurācijas darbības laukā Atļauju identifikators** Microsoft Dataverse.

   :::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="Konfigurācijas opcijas, lai iespējotu datu koplietošanu no sava Azure Data Lake Storage ar Microsoft Dataverse.":::

## <a name="remove-an-existing-connection-to-a-dataverse-environment"></a>Esoša savienojuma ar Dataverse vidi noņemšana

Izveidojot savienojumu ar Dataverse vidi, kļūdas ziņojums **Šī CDS organizācija jau ir pievienota citai Customer Insights instancei**, nozīmē, ka Dataverse vide jau tiek izmantota Customer Insights vidē. Esošo savienojumu var noņemt kā globālu vides administratoru Dataverse. Izmaiņu aizpildīšana var aizņemt pāris stundas.

1. Dodieties uz [Power Apps](https://make.powerapps.com).
1. Atlasiet vidi no vides atlasītāja.
1. Dodieties uz **sadaļu Risinājumi**.
1. Atinstalējiet vai dzēsiet risinājumu ar nosaukumu **Dynamics 365 Customer Insights Klienta kartes pievienojumprogramma (priekšskatījums)**.

VAI

1. Atveriet savu Dataverse vidi.
1. Dodieties uz **Papildu iestatījumu** > **risinājumi**.
1. Atinstalējiet **CustomerInsightsCustomerCard** risinājumu.

Ja savienojuma noņemšana neizdodas atkarību dēļ, ir jānoņem arī atkarības. Papildinformāciju skatiet sadaļā [Atkarību](/power-platform/alm/removing-dependencies) noņemšana.

## <a name="output-entities"></a>Izvades entītijas

Dažas Customer Insights izvades entītijas ir pieejamas kā tabulas .Dataverse Tālāk minētās sadaļas apraksta šo tabulu paredzēto shēmu.

- [CustomerProfile](#customerprofile)
- [ContactProfile](#contactprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [Bagātināšana](#enrichment)
- [Prognoze](#prediction)
- [Dalība segmentā](#segment-membership)

### <a name="customerprofile"></a>CustomerProfile

Šajā tabulā ir iekļauts vienotais klienta profils no Customer Insights. Vienota klienta profila shēma ir atkarīga no entītijām un atribūtiem, kas tiek izmantoti datu apvienošanas procesā. Klienta profila shēmā parasti ir atribūtu apakškopa no [CustomerProfile Common Data Model definīcijas](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile). B-to-B scenārijam klienta profils satur vienotus kontus, un shēmā parasti ir ietverta atribūtu apakškopa no [konta](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/account) definīcijas Common Data Model.

### <a name="contactprofile"></a>ContactProfile

ContactProfile satur vienotu informāciju par kontaktpersonu. Kontaktpersonas ir [personas, kas tiek kartētas uz kontu](data-unification-contacts.md) B-to-B scenārijā.

| Column                       | Tipi                | Apraksts     |
| ---------------------------- | ------------------- | --------------- |
|  Birthdate            | DateTime       |  Kontaktpersonas dzimšanas datums               |
|  Pilsēta                 | Īsziņu |  Kontaktpersonas adreses pilsēta               |
|  ContactId            | Īsziņu |  Kontaktpersonas profila ID               |
|  ContactProfileId     | Unikālais identifikators   |  Kontaktpersonas GUID               |
|  Valsts vaireģions      | Īsziņu |  Kontaktadreses valsts/reģions               |
|  CustomerId           | Īsziņu |  Tā konta ID, uz kuru kontaktpersona ir kartēta               |
|  EntityName           | Īsziņu |  Uzņēmums, no kura iegūti dati                |
|  FirstName            | Īsziņu |  Kontakta vārds               |
|  Dzimums               | Īsziņu |  Kontaktpersonas dzimums               |
|  ID                   | Īsziņu |  Deterministisks GUID, pamatojoties uz`Identifier`               |
|  Identifikators           | Īsziņu |  Kontaktpersonas profila iekšējais ID: `ContactProfile|CustomerId|ContactId`               |
|  JobTitle             | Īsziņu |  Kontaktpersonas amata nosaukums               |
|  LastName             | Īsziņu |  Kontaktpersonas uzvārds               |
|  PostalCode           | Īsziņu |  Kontaktpersonas adreses pasta indekss               |
|  PrimaryEmail         | Īsziņu |  Kontaktpersonas e-pasta adrese               |
|  Primārais tālrunis         | Īsziņu |  Kontaktpersonas tālruņa numurs               |
|  Štats vai novads      | Īsziņu |  Kontaktadreses štats vai province               |
|  StreetAddress        | Īsziņu |  Kontaktadreses iela               |

### <a name="alternatekey"></a>AlternateKey

AlternateKey tabulā ir ietvertas entītiju atslēgas, kas piedalījās apvienošanas procesā.

|Column  |Tipi  |Apraksts  |
|---------|---------|---------|
|DataSourceName    |Īsziņu         | Datu avota nosaukums. Piemērs: `datasource5`        |
|EntityName        | Īsziņu        | Entītijas nosaukums programmā Customer Insights. Piemērs: `contact1`        |
|AlternateValue    |Īsziņu         |Alternatīvais ID, kas tiek kartēts uz klienta ID. Piemērs: `cntid_1078`         |
|KeyRing           | Īsziņu        | JSON vērtība  </br> Paraugs: [{"dataSourceName":" datasource5 ",</br>"entityName":" contact1",</br>"preferredKey":" cntid_1078",</br>"taustiņi":[" cntid_1078"]}]       |
|CustomerId         | Īsziņu        | Vienotā klienta profila ID.         |
|AlternateKeyId     | Unikālais identifikators        |  AlternateKey deterministisks GUID, pamatojoties uz`Identifier`      |
|Identifikators |   Īsziņu      |   `DataSourceName|EntityName|AlternateValue`  </br> Paraugs: `testdatasource|contact1|cntid_1078`    |

### <a name="unifiedactivity"></a>UnifiedActivity

Šajā tabulā ir ietvertas lietotāju darbības, kas ir pieejamas programmā Customer Insights.

| Column            | Tipi        | Apraksts                                                                              |
|-------------------|-------------|------------------------------------------------------------------------------------------|
| CustomerId        | Īsziņu      | Klienta profila ID                                                                      |
| ActivityId        | Īsziņu      | Klienta darbības iekšējais ID (primārā atslēga)                                       |
| SourceEntityName  | Īsziņu      | Avota entītijas nosaukums                                                                |
| SourceActivityId  | Īsziņu      | Avota entītijas primārā atslēga                                                       |
| ActivityType      | Īsziņu      | Semantiskās darbības tips vai pielāgotas darbības nosaukums                                        |
| ActivityTimeStamp | DateTime    | Aktivitātes laika zīmogs                                                                      |
| Amats             | Īsziņu      | Darbības pārraudzības nosaukums                                                               |
| Apraksts       | Īsziņu      | Darbības apraksts                                                                     |
| Vietrādis URL               | Īsziņu      | Saite uz ārēju URL, kas raksturīgs darbībai                                         |
| SemanticData      | Īsziņu | Ietver sarakstu ar galvenajiem vērtību pāriem semantiskās kartēšanas laukiem, kas raksturīgi darbības tipam |
| RangeIndex        | Īsziņu      | Unix laikspiedols, kas tiek izmantots darbību laika skalas un efektīva diapazona vaicājumu kārtošanai |
| UnifiedActivityId   | Unikālais identifikators | Klienta darbības iekšējais ID (ActivityId) |

### <a name="customermeasure"></a>CustomerMeasure

Šajā tabulā ir ietverti uz klienta atribūtiem balstītu pasākumu izvades dati.

| Column             | Tipi             | Apraksts                 |
|--------------------|------------------|-----------------------------|
| CustomerId         | Īsziņu           | Klienta profila ID        |
| Mērījumi           | Īsziņu      | Ietver sarakstu ar konkrētā klienta nosaukuma un vērtību mērvienību pamatvērtību pāriem |
| Identifikators | Īsziņu           | `Customer_Measure|CustomerId` |
| CustomerMeasureId | Unikālais identifikators     | Klienta profila ID |

### <a name="enrichment"></a>Bagātināšana

Šajā tabulā ir ietverta bagātināšanas procesa izvade.

| Column               | Tipi             |  Apraksts                                          |
|----------------------|------------------|------------------------------------------------------|
| CustomerId           | Īsziņu           | Klienta profila ID                                 |
| EnrichmentProvider   | Īsziņu           | Bagātinājuma nodrošinātāja nosaukums                                  |
| EnrichmentType       | Īsziņu           | Bagātinājuma tips                                      |
| Vērtības               | Īsziņu      | Bagātinātā procesa radītais atribūtu saraksts |
| EnrichmentId | Unikālais identifikators            | Deterministisks GUID, kas ģenerēts no`Identifier` |
| Identifikators   | Īsziņu           | `EnrichmentProvider|EnrichmentType|CustomerId`         |

### <a name="prediction"></a>Prognoze

Šajā tabulā ir ietverta bagātināšanas procesa izvade.

| Column               | Tipi        | Apraksts                                          |
|----------------------|-------------|------------------------------------------------------|
| CustomerId           | Īsziņu      | Klienta profila ID                                  |
| ModelProvider        | Īsziņu      | Modeļa nodrošinātāja nosaukums                                      |
| Modelis                | Īsziņu      | Modeļa nosaukums                                                |
| Vērtības               | Īsziņu | Modeļa radītais atribūtu saraksts |
| PredictionId | Unikālais identifikators       | Deterministisks GUID, kas ģenerēts no`Identifier` |
| Identifikators   | Īsziņu      |  `Model|ModelProvider|CustomerId`                      |

### <a name="segment-membership"></a>Dalība segmentā

Šajā tabulā ir segmenta dalības informācija par klientu profiliem.

| Column        | Tipi | Apraksts                        |
|--------------------|--------------|-----------------------------|
| CustomerId        | Īsziņu       | Klienta profila ID        |
| SegmentProvider      | Īsziņu       | Lietotne, kas publicē segmentus.      |
| SegmentsMembershipType | Īsziņu       | Klienta tips šim segmenta dalības ierakstam. Atbalsta vairākus veidus, piemēram, Klientu, Kontaktpersonu vai Kontu. Noklusējums: Klients  |
| Segmenti       | Īsziņu  | Unikālo segmentu saraksts, kuros klienta profils ir dalībnieks      |
| Identifikators  | Īsziņu   | Segmenta dalības ieraksta unikālais identifikators. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| SegmentMembershipId | Unikālais identifikators      | Deterministisks GUID, kas ģenerēts no`Identifier`          |

[!INCLUDE [footer-include](includes/footer-banner.md)]
