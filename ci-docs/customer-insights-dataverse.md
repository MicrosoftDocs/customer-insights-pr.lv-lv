---
title: Darbs ar Customer Insights datiem programmā Microsoft Dataverse
description: Uzziniet, kā savienot Customer Insights, un Microsoft Dataverse izprotiet izvades entītijas, kas tiek eksportētas uz Dataverse.
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
ms.openlocfilehash: 9433c411a2c7eb0db137c6392578993d47be82a2
ms.sourcegitcommit: 8559ca47a22d1d7cd9be13531c2eaf0c1083942b
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 10/12/2022
ms.locfileid: "9671260"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Darbs ar Customer Insights datiem programmā Microsoft Dataverse

Customer Insights nodrošina iespēju izvades entītijas padarīt pieejamas programmā [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro). Šī integrācija nodrošina vienkāršu datu kopīgošanu un pielāgotu izstrādi, izmantojot zema koda / bez koda pieeju. Izvades [entītijas](#output-entities) ir pieejamas kā tabulas Dataverse vidē. Datus var izmantot jebkurai citai lietojumprogrammai, pamatojoties uz Dataverse tabulām. Šīs tabulas iespējo scenārijus, piemēram, automatizētas darbplūsmas, izmantojot Power Automate vai veidojot programmas ar Power Apps.

Savienojuma izveide ar Dataverse vidi ļauj [arī uzņemt datus no lokāls datu avotiem, izmantojot Power Platform datu plūsmas un vārtejas](connect-power-query.md#add-data-from-on-premises-data-sources).

## <a name="prerequisites"></a>Priekšnoteikumi

- Customer Insights un Dataverse vides ir viesojamas vienā reģionā.
- Globālajā administratora loma, kas iestatīta Dataverse vidē. Pārbaudiet, vai šī vide ir saistīta ar [Dataverse noteiktām drošības grupām,](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) un pārliecinieties, vai esat pievienots šīm drošības grupām.
- Neviena cita Customer Insights vide jau nav saistīta ar vidi, ar kuru Dataverse vēlaties izveidot savienojumu. Uzziniet, [kā noņemt esošu savienojumu ar Dataverse vidi](#remove-an-existing-connection-to-a-dataverse-environment).
- Vide, kas savienota ar vienu krātuves kontu, Microsoft Dataverse ja konfigurējat vidi, lai [izmantotu jūsu Azure Data Lake Storage](own-data-lake-storage.md).

## <a name="dataverse-storage-capacity-entitlement"></a>Dataverse Tiesības uz krātuves ietilpību

Customer Insights abonements dod jums papildu jaudu jūsu organizācijas esošajai [Dataverse krātuves ietilpībai](/power-platform/admin/capacity-storage). Pievienotā noslodze ir atkarīga no jūsu abonementā izmantoto profilu skaita.

**Piemērs:**

Pieņemot, ka saņemat 15 GB datu bāzes krātuvi un 20 GB failu krātuvi uz 100 000 klientu profiliem. Ja jūsu abonementā ir iekļauti 300 000 klientu profili, kopējā krātuves ietilpība ir 45 GB (3 x 15 GB) datu bāzes krātuve un 60 GB failu krātuve (3 x 20 GB). Līdzīgi, ja jums ir B-to-B abonements ar 30K kontiem, jūsu kopējā krātuves ietilpība ir 45 GB (3 x 15 GB) datu bāzes krātuve un 60 GB failu krātuve (3 x 20 GB).

Žurnāla noslodze jūsu organizācijai nav pieaugoša un fiksēta.

Papildinformāciju par detalizētām noslodzes pilnvarām skatiet rakstā [Dynamics 365 licencēšanas rokasgrāmata](https://go.microsoft.com/fwlink/?LinkId=866544).

## <a name="connect-a-dataverse-environment-to-customer-insights"></a>Vides savienošana Dataverse ar Customer Insights

Šī **Microsoft Dataverse** darbība ļauj savienot Customer Insights ar savu Dataverse vidi, vienlaikus [veidojot Customer Insights vidi](create-environment.md).

:::image type="content" source="media/dataverse-provisioning.png" alt-text="datu kopīgošana, izmantojot Microsoft Dataverse automātiski iespējotu jaunām vidēm.":::

1. Norādiet vietrādi URL savai Dataverse videi vai atstājiet tukšu, lai to izveidotu jums.

   > [!NOTE]
   > Pēc tam, kad ir izveidots savienojums starp Customer Insights un Dataverse, nemainiet vides organizācijas nosaukumu Dataverse. Organizācijas nosaukums tiek izmantots Dataverse vietrādī URL, un mainīts nosaukums pārtrauc savienojumu ar Customer Insights.

   [Power Platform Administratori var kontrolēt,Dataverse kurš var izveidot jaunu](/power-platform/admin/control-environment-creation) vidi. Ja mēģināt iestatīt jaunu Customer Insights vidi un nevarat to izdarīt, administrators, iespējams, ir atspējojis vides izveidi Dataverse visiem, izņemot administratorus.

1. Ja izmantojat savu Data Lake krātuves kontu:
   1. Atlasiet **Iespējot datu kopīgošanu** ar Dataverse.
   1. Ievadiet atļauju **identifikatoru**. Lai iegūtu atļaujas identifikatoru, iespējojiet [datu kopīgošanu ar Dataverse savu Azure Data Lake Storage](#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview).

## <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>Datu kopīgošanas iespējošana ar Dataverse savu Azure Data Lake Storage (priekšskatījums)

Savā [Azure Data Lake Storage kontā](own-data-lake-storage.md) pārbaudiet, vai lietotājam, kas iestata Customer Insights vidi, ir vismaz **krātuves konta konteinera krātuves Blob datu lasītāja**`customerinsights` atļaujas.

> [!NOTE]
> Datu kopīgošana ir piemērojama tikai tad, ja izmantojat savu Azure Data Lake Storage kontu. Šis iestatījums nav pieejams, ja Customer Insights vide izmanto noklusējuma Dataverse krātuvi.

### <a name="limitations"></a>Ierobežojumi

- Tikai kartēšana viens pret vienu starp Dataverse organizāciju un Azure Data Lake Storage kontu. Dataverse Kad organizācija ir savienota ar krātuves kontu, tā nevar izveidot savienojumu ar citu krātuves kontu. Šis ierobežojums neļauj Dataverse aizpildīt vairākus krātuves kontus.
- Datu kopīgošana nedarbosies, ja ir nepieciešama Azure Private Link iestatīšana, lai piekļūtu jūsu Azure Data Lake Storage kontam, jo tas atrodas aiz ugunsmūra. Dataverse pašlaik neatbalsta savienojumu ar privātiem galapunktiem, izmantojot Private Link.

### <a name="set-up-security-groups-on-your-own-azure-data-lake-storage"></a>Drošības grupu iestatīšana patstāvīgi Azure Data Lake Storage

1. Savā Azure abonementā izveidojiet divas drošības grupas — vienu Reader **drošības grupu un vienu** **līdzstrādnieku** drošības grupu un iestatiet Microsoft Dataverse pakalpojumu kā īpašnieku abām drošības grupām.

1. Pārvaldiet piekļuves kontroles sarakstu (Access Control List — ACL) konteinerā `customerinsights` savā krātuves kontā, izmantojot šīs drošības grupas.
   1. Pievienojiet pakalpojumu un visas biznesa Microsoft Dataverse lietojumprogrammas, piemēram, Dynamics 365 Marketing, Dataverse lasītāja **drošības** grupai ar **tikai** lasīšanas atļaujām.
   1. Pievienojiet *tikai* lietojumprogrammu **Klientu ieskati līdzstrādnieku** drošības grupai, lai piešķirtu gan lasīšanas, gan **rakstīšanas** atļaujas profilu un ieskatu rakstīšanai.

### <a name="set-up-powershell"></a>PowerShell iestatīšana

Iestatiet PowerShell, lai izpildītu PowerShell skriptus.

1. Instalējiet jaunāko PowerShell versiju [Azure Active Directory grafikam](/powershell/azure/active-directory/install-adv2).
   1. Datorā atlasiet tastatūras taustiņu Windows un meklējiet **Windows PowerShell** un atlasiet opciju **Palaist kā administratoram**.
   1. PowerShell logā, kas tiek atvērts, ievadiet `Install-Module AzureAD`.

1. Importējiet trīs moduļus.
   1. PowerShell logā ievadiet `Install-Module -Name Az.Accounts` un izpildiet norādītās darbības.
   1. Atkārtojiet par `Install-Module -Name Az.Resources` un `Install-Module -Name Az.Storage`.

### <a name="execute-powershell-scripts-and-obtain-the-permission-identifier"></a>PowerShell skriptu izpilde un atļaujas identifikatora iegūšana

1. Lejupielādējiet divus PowerShell skriptus, kas jums jāpalaiž no mūsu inženiera [GitHub repo](https://github.com/trin-msft/byol).
   - `CreateSecurityGroups.ps1`: Nepieciešamas nomnieka administratora atļaujas.
   - `ByolSetup.ps1`: Nepieciešamas krātuves Blob datu īpašnieka atļaujas krātuves konta/konteinera līmenī. Šis skripts izveidos atļauju jums. Pēc veiksmīgas skripta palaišanas lomu piešķiršanu var noņemt manuāli.

1. Izpildiet `CreateSecurityGroups.ps1` programmā Windows PowerShell, nodrošinot Azure abonementa ID, kas satur jūsu Azure Data Lake Storage. Redaktorā atveriet PowerShell skriptu, lai pārskatītu papildinformāciju un ieviesto loģiku.

   Šis skripts jūsu Azure abonementā izveido divas drošības grupas: vienu lasītāju grupai un otru līdzstrādnieku grupai. Microsoft Dataverse pakalpojums ir abu šo drošības grupu īpašnieks.

1. Saglabājiet abas šī skripta ģenerētās drošības grupas ID vērtības, lai tās izmantotu skriptā `ByolSetup.ps1`.

   > [!NOTE]
   > Nomniekā var atspējot drošības grupas izveidi. Tādā gadījumā būtu nepieciešama manuāla iestatīšana, un jūsu Azure AD administratoram būtu jāiespējo [drošības grupas izveide](/azure/active-directory/enterprise-users/groups-self-service-management).

1. Izpildiet `ByolSetup.ps1` programmā Windows PowerShell, nodrošinot Azure abonementa ID, kurā ir jūsu Azure Data Lake Storage, krātuves konta nosaukums, resursu grupas nosaukums un lasītāja un līdzstrādnieka drošības grupas ID vērtības. Redaktorā atveriet PowerShell skriptu, lai pārskatītu papildinformāciju un ieviesto loģiku.

   Šis skripts pievieno nepieciešamo uz lomām balstīto piekļuves kontroli pakalpojumam Microsoft Dataverse un visām Dataverse biznesa lietojumprogrammām. Tas arī atjaunina piekļuves vadības sarakstu (Access Control List — ACL) konteinerā `customerinsights` drošības grupām, kas izveidotas ar skriptu `CreateSecurityGroups.ps1`. Līdzstrādnieku grupai tiek piešķirta rwx *atļauja, un lasītāju grupai tiek piešķirta* *tikai r-x* atļauja.

1. Kopējiet izvades virkni, kas izskatās šādi: `https://DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`

1. Ievadiet kopēto izvades virkni **vides konfigurācijas soļa laukā Atļauju identifikators** opcijai Microsoft Dataverse.

   :::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="Konfigurācijas opcijas, lai iespējotu datu kopīgošanu no sava Azure Data Lake Storage ar Microsoft Dataverse.":::

## <a name="remove-an-existing-connection-to-a-dataverse-environment"></a>Esoša savienojuma Dataverse ar vidi noņemšana

Veidojot savienojumu ar vidi, kļūdas ziņojums Dataverse Šī CDS organizācija jau ir pievienota **citai Customer Insights instancei**, Dataverse nozīmē, ka vide jau tiek izmantota Customer Insights vidē. Jūs varat noņemt esošo savienojumu kā globālais administrators Dataverse vidē. Izmaiņu aizpildīšana var aizņemt pāris stundas.

1. Dodieties uz [Power Apps](https://make.powerapps.com).
1. Vides atlasītājā atlasiet vidi.
1. Dodieties uz **sadaļu Risinājumi**.
1. Atinstalējiet vai dzēsiet risinājumu ar nosaukumu **Dynamics 365 Customer Insights Customer Card Add-in (priekšskatījums)**.

VAI

1. Atveriet savu Dataverse vidi.
1. Dodieties uz Papildu **iestatījumu** > **risinājumi**.
1. Atinstalējiet **risinājumu CustomerInsightsCustomerCard**.

Ja savienojuma noņemšana neizdodas atkarību dēļ, jums ir jānoņem arī atkarības. Papildinformāciju skatiet sadaļā [Atkarību](/power-platform/alm/removing-dependencies) noņemšana.

## <a name="output-entities"></a>Izvades entītijas

Dažas izvades entītijas no Customer Insights ir pieejamas kā tabulas sadaļā Dataverse. Tālāk minētās sadaļas apraksta šo tabulu paredzēto shēmu.

- [CustomerProfile](#customerprofile)
- [ContactProfile](#contactprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [Bagātināšana](#enrichment)
- [Prognoze](#prediction)
- [Segmenta dalība](#segment-membership)

### <a name="customerprofile"></a>CustomerProfile

Šajā tabulā ir iekļauts vienotais klienta profils no Customer Insights. Vienota klienta profila shēma ir atkarīga no datu apvienošanas procesā izmantotajām entītijām un atribūtiem. Klienta profila shēmā parasti ir atribūtu apakškopa no [CustomerProfile Common Data Model definīcijas](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile). Scenārijam B-to-B klienta profils satur vienotus kontus, un shēmā parasti ir ietverta atribūtu apakškopa no [konta](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/account) kopējā datu modeļa definīcijas.

### <a name="contactprofile"></a>ContactProfile

Kontaktpersonas profils satur vienotu informāciju par kontaktpersonu. Kontaktpersonas ir [personas, kas tiek kartētas uz kontu](data-unification-contacts.md) B-to-B scenārijā.

| Column                       | Tipi                | Apraksts     |
| ---------------------------- | ------------------- | --------------- |
|  Birthdate            | DateTime       |  Kontaktpersonas dzimšanas datums               |
|  Pilsēta                 | Īsziņu |  Kontaktpersonas dzīvesvietas pilsēta               |
|  KontaktpersonaId            | Īsziņu |  Kontaktpersonas profila ID               |
|  ContactProfileId     | Unikālais identifikators   |  GUID kontaktpersonai               |
|  ValstsOrreģions      | Īsziņu |  Kontaktpersonas adreses valsts/reģions               |
|  CustomerId           | Īsziņu |  Tā konta ID, uz kuru kontaktpersona ir kartēta               |
|  EntityName           | Īsziņu |  Entītija, no kuras nāk dati                |
|  FirstName            | Īsziņu |  Kontaktpersonas vārds               |
|  Dzimums               | Īsziņu |  Kontaktpersonas dzimums               |
|  ID                   | Īsziņu |  Deterministiskā GUID, kuras pamatā ir`Identifier`               |
|  Identifikators           | Īsziņu |  Kontaktpersonas profila iekšējais ID: `ContactProfile|CustomerId|ContactId`               |
|  JobTitle             | Īsziņu |  Kontaktpersonas amata nosaukums               |
|  LastName             | Īsziņu |  Kontakta uzvārds               |
|  PostalCode           | Īsziņu |  Kontaktpersonas adreses pasta indekss               |
|  PrimaryEmail         | Īsziņu |  Kontaktpersonas e-pasta adrese               |
|  PrimāraisPhone         | Īsziņu |  Kontaktpersonas tālruņa numurs               |
|  Štats vai novads      | Īsziņu |  Kontaktpersonas valsts vai province               |
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
|AlternateKeyId     | Unikālais identifikators        |  Alternatīvās atslēgas deterministiskā GUID, kuras pamatā ir`Identifier`      |
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
| ActivityTimeStamp | DateTime    | Aktivitātes laikspiedols                                                                      |
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
| BagātināšanaId | Unikālais identifikators            | Deterministisks GUID, kas ģenerēts no`Identifier` |
| Identifikators   | Īsziņu           | `EnrichmentProvider|EnrichmentType|CustomerId`         |

### <a name="prediction"></a>Prognoze

Šajā tabulā ir ietverta bagātināšanas procesa izvade.

| Column               | Tipi        | Apraksts                                          |
|----------------------|-------------|------------------------------------------------------|
| CustomerId           | Īsziņu      | Klienta profila ID                                  |
| ModelProvider        | Īsziņu      | Modeļa nodrošinātāja nosaukums                                      |
| Modelis                | Īsziņu      | Modeļa nosaukums                                                |
| Vērtības               | Īsziņu | Modeļa radītais atribūtu saraksts |
| PrognozeId | Unikālais identifikators       | Deterministisks GUID, kas ģenerēts no`Identifier` |
| Identifikators   | Īsziņu      |  `Model|ModelProvider|CustomerId`                      |

### <a name="segment-membership"></a>Segmenta dalība

Šajā tabulā ir iekļauta informācija par klientu profilu segmentu dalību.

| Column        | Tipi | Apraksts                        |
|--------------------|--------------|-----------------------------|
| CustomerId        | Īsziņu       | Klienta profila ID        |
| Segmenta nodrošinātājs      | Īsziņu       | Lietotne, kas publicē segmentus.      |
| SegmentMembershipType | Īsziņu       | Klienta tips šim segmenta dalības ierakstam. Atbalsta vairākus tipus, piemēram, Klients, Kontaktpersona vai Konts. Noklusējums: Klients  |
| Segmenti       | Īsziņu  | Unikālo segmentu saraksts, kuros klienta profils ir      |
| Identifikators  | Īsziņu   | Segmenta dalības ieraksta unikālais identifikators. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| SegmentMembershipId | Unikālais identifikators      | Deterministisks GUID, kas ģenerēts no`Identifier`          |

[!INCLUDE [footer-include](includes/footer-banner.md)]
