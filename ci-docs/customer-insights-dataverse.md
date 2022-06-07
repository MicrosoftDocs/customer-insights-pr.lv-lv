---
title: Darbs ar Customer Insights datiem programmā Microsoft Dataverse
description: Uzziniet, kā savienot Customer Insights un Microsoft Dataverse izprast izvades entītijas, kas tiek eksportētas uz Dataverse.
ms.date: 05/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 3848e143bc7cb2f345bc698a274b92148ef00669
ms.sourcegitcommit: f5af5613afd9c3f2f0695e2d62d225f0b504f033
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 06/01/2022
ms.locfileid: "8833685"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Darbs ar Customer Insights datiem programmā Microsoft Dataverse

Customer Insights piedāvā iespēju padarīt izvades entītijas pieejamas kā [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro). Šī integrācija nodrošina ērtu datu koplietošanu un pielāgotu izstrādi, izmantojot zema koda/bez koda pieeju. Izvades [entītijas](#output-entities) ir pieejamas kā tabulas vidē Dataverse. Datus var izmantot jebkurai citai lietojumprogrammai, pamatojoties uz tabulām Dataverse. Šīs tabulas iespējo tādus scenārijus kā automatizētas darbplūsmas, izmantojot Power Automate vai veidojot programmas ar Power Apps.

Dataverse Savienojums ar vidi ļauj arī uzņemt [datus no lokāls datu avotiem, izmantojot Power Platform datu plūsmas un vārtejas](data-sources.md#add-data-from-on-premises-data-sources).

## <a name="prerequisites"></a>Priekšnoteikumi

- Klientu ieskatiem un Dataverse vidēm jābūt viesotām vienā reģionā.
- Vidē ir jābūt globāla administratora lomai Dataverse. Pārbaudiet, vai šī [Dataverse vide ir saistīta ar](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) noteiktām drošības grupām, un pārliecinieties, vai esat pievienots šīm drošības grupām.
- Neviena cita Customer Insights vide jau nav saistīta ar vidi, Dataverse kuru vēlaties savienot. Uzziniet, [kā noņemt esošu savienojumu ar Dataverse vidi](#remove-an-existing-connection-to-a-dataverse-environment).
- Vide Microsoft Dataverse var izveidot savienojumu tikai ar vienu krātuves kontu. Tas tiek lietots tikai tad, ja konfigurējat vidi, lai [tā izmantotu savu Azure Data Lake Storage](own-data-lake-storage.md).

## <a name="connect-a-dataverse-environment-to-customer-insights"></a>Dataverse Vides savienošana ar Customer Insights

Šī **Microsoft Dataverse** darbība ļauj savienot Customer Insights ar vidi Dataverse, vienlaikus [izveidojot Customer Insights vidi](create-environment.md).

:::image type="content" source="media/dataverse-provisioning.png" alt-text="datu kopīgošana ar Microsoft Dataverse automātiski iespējotu neto jaunām vidēm.":::

Administratori var konfigurēt Customer Insights, lai izveidotu savienojumu ar esošu Dataverse vidi. Nodrošinot vietrādi URL Dataverse videi, tas tiek pievienots viņu jaunajai Customer Insights videi.

Ja nevēlaties izmantot esošu Dataverse vidi, sistēma nomniekā izveido jaunu vidi Customer Insights datiem. [Power Platform administratori var kontrolēt, kas var izveidot vides](/power-platform/admin/control-environment-creation). Ja iestatāt jaunu Customer Insights vidi un administrators ir atspējojis vides izveidi Dataverse visiem, izņemot administratorus, iespējams, nevarēsit izveidot jaunu vidi.

**Iespējojiet datu kopīgošanu**, Dataverse atzīmējot izvēles rūtiņu Datu kopīgošana.

Ja izmantojat savu Datu ezera krātuves kontu, jums ir nepieciešams **arī atļauju identifikators**. Lai iegūtu papildinformāciju par to, kā iegūt atļaujas identifikatoru, pārskatiet šo sadaļu.

## <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>Iespējot datu kopīgošanu ar Dataverse savu (Azure Data Lake Storage Priekšskatījums)

Lai iespējotu datu kopīgošanu ar Microsoft Dataverse laiku, kad vide [izmanto savu Azure Data Lake Storage kontu](own-data-lake-storage.md), ir nepieciešama papildu konfigurācija. Lietotājam, kas iestatījis Customer Insights vidi, jābūt vismaz **Krātuves** BLOB datu lasītāja *atļaujām konta konteinerā* CustomerInsights Azure Data Lake Storage.

1. Izveidojiet savā Azure abonementā divas drošības grupas - vienu **Reader** drošības grupu un vienu **līdzstrādnieku** drošības grupu un iestatiet Microsoft Dataverse pakalpojumu kā īpašnieku abām drošības grupām.
2. Pārvaldiet piekļuves kontroles sarakstu (ACL) krātuves konta konteinerā CustomerInsights, izmantojot šīs drošības grupas. Microsoft Dataverse Pievienojiet pakalpojumu un visas Dataverse biznesa lietojumprogrammas, piemēram, Dynamics 365 Marketing **, drošības grupai Reader** ar **tikai** lasāmām atļaujām. Pievienojiet *līdzstrādnieku* drošības grupai tikai **Customer Insights lietojumprogrammu**, lai piešķirtu gan lasīšanas, gan **rakstīšanas** atļaujas profilu un ieskatu rakstīšanai.

### <a name="limitations"></a>Ierobežojumi

Lietojot Dataverse ar savu Azure Data Lake Storage kontu, ir divi ierobežojumi:

- Starp organizāciju un Dataverse kontu ir viens pret vienu kartējums Azure Data Lake Storage. Dataverse Kad organizācija ir izveidojusi savienojumu ar krātuves kontu, tā nevar izveidot savienojumu ar citu krātuves kontu. Šis ierobežojums neļauj a Dataverse aizpildīt vairākus krātuves kontus.
- Datu kopīgošana nedarbosies, ja Azure Private Link iestatījums ir nepieciešams, lai piekļūtu jūsu Azure Data Lake krātuves kontam, jo tas atrodas aiz ugunsmūra. Dataverse pašlaik neatbalsta savienojumu ar privātiem galapunktiem, izmantojot privāto saiti.

### <a name="set-up-powershell"></a>PowerShell iestatīšana

Lai izpildītu PowerShell skriptus, vispirms ir attiecīgi jāiestata PowerShell.

1. Instalējiet jaunāko PowerShell for Graph [Azure Active Directory versiju](/powershell/azure/active-directory/install-adv2).
   1. Datorā atlasiet tastatūras taustiņu Windows un meklējiet **Windows PowerShell** un atlasiet opciju **Palaist kā administratoram**.
   1. PowerShell logā, kas tiek atvērts, ievadiet `Install-Module AzureAD`.
2. Importēt trīs moduļus.
    1. PowerShell logā ievadiet `Install-Module -Name Az.Accounts` un izpildiet darbības.
    1. `Install-Module -Name Az.Resources` Atkārtojiet un `Install-Module -Name Az.Storage`.

### <a name="configuration-steps"></a>Konfigurēšanas darbības

1. Lejupielādējiet divus PowerShell skriptus, kas jums jāpalaiž no mūsu inženiera [GitHub repo](https://github.com/trin-msft/byol).
    1. `CreateSecurityGroups.ps1`
       - Lai palaistu šo PowerShell skriptu, ir nepieciešamas *nomnieka administratora* atļaujas.
       - Šis PowerShell skripts jūsu Azure abonementā izveido divas drošības grupas. Viens lasītāju grupai un otrs līdzstrādnieku grupai un veiks Microsoft Dataverse pakalpojumu kā īpašnieks abām šīm drošības grupām.
       - Izpildiet šo PowerShell skriptu sistēmā Windows PowerShell, norādot Azure abonementa ID, kurā ir jūsu Azure Data Lake Storage. Atveriet PowerShell skriptu redaktorā, lai pārskatītu papildinformāciju un ieviesto loģiku.
       - Saglabāt abas drošības grupas ID vērtības, ko ģenerējis šis skripts, jo mēs tās izmantosim skriptā `ByolSetup.ps1`.

        > [!NOTE]
        > Drošības grupas izveidi nomniekam var atspējot. Šādā gadījumā būtu nepieciešama manuāla iestatīšana, un administratoram Azure AD būtu jāiespējo [drošības grupas izveide](/azure/active-directory/enterprise-users/groups-self-service-management).

    2. `ByolSetup.ps1`
        - Lai palaistu šo skriptu, krātuves BLOB datu īpašnieka atļaujas ir nepieciešamas *krātuves BLOB datu īpašnieka* atļaujas krātuves konta/konteinera līmenī, vai arī šis skripts tādu izveidos jums. Lomas piešķiri var noņemt manuāli pēc veiksmīgas skripta palaišanas.
        - Šis PowerShell skripts pievieno nepieciešamo tole bāzēto piekļuves kontroli (RBAC) pakalpojumam Microsoft Dataverse un visām Dataverse biznesa lietojumprogrammām. Tas arī atjaunina piekļuves kontroles sarakstu (ACL) konteinerā CustomerInsights drošības grupām, kas izveidotas ar skriptu `CreateSecurityGroups.ps1`. Līdzstrādnieku grupai būs *rwx* atļauja, un lasītāju grupai būs *tikai r-x* atļauja.
        - Izpildiet šo PowerShell skriptu sistēmā Windows PowerShell, norādot Azure abonementa ID, kurā ir jūsu Azure Data Lake Storage, krātuves konta nosaukums, resursu grupas nosaukums un lasītāja un līdzstrādnieku drošības grupas ID vērtības. Atveriet PowerShell skriptu redaktorā, lai pārskatītu papildinformāciju un ieviesto loģiku.
        - Kopējiet izvades virkni pēc veiksmīgas skripta palaišanas. Izvades virkne izskatās šādi: `https://DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`

2. Ievadiet izvades virkni, kas kopēta no augšas, **vides konfigurācijas soļa atļaujas identifikatora** laukā Microsoft Dataverse.

:::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="Konfigurācijas opcijas, lai iespējotu datu kopīgošanu no sava ar Azure Data Lake Storage Microsoft Dataverse.":::

### <a name="remove-an-existing-connection-to-a-dataverse-environment"></a>Esoša savienojuma Dataverse ar vidi noņemšana

Veidojot savienojumu ar Dataverse vidi, kļūdas ziņojums **Šī CDS organizācija jau ir pievienota citai Customer Insights instancei**, nozīmē, ka Dataverse vide jau tiek izmantota Customer Insights vidē. Esošo savienojumu var noņemt kā vides globālo administratoru Dataverse. Izmaiņu aizpildīšana var aizņemt pāris stundas.

1. Dodieties uz [Power Apps](https://make.powerapps.com).
1. Atlasiet vidi no vides atlasītāja.
1. Doties uz **risinājumiem**
1. Atinstalējiet vai dzēsiet risinājumu ar nosaukumu **Dynamics 365 Customer Insights Klienta kartes pievienojumprogramma (Preview)**.

VAI

1. Atveriet savu Dataverse vidi.
1. Dodieties uz **Papildu iestatījumu** > **risinājumi**.
1. Atinstalējiet **risinājumu CustomerInsightsCustomerCard**.

Ja atkarības dēļ savienojuma noņemšana neizdodas, ir jānoņem arī atkarības. Papildinformāciju skatiet sadaļā [Atkarību](/power-platform/alm/removing-dependencies) noņemšana.

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

<!--
## FAQ: Update existing environments to use Microsoft Dataverse

Between mid-May 2022 and June 13, 2022, administrators can update the environment settings with a Dataverse environment that Customer Insights can use. On June 13, 2022, your environment will be updated automatically and we'll create a Dataverse environment on your tenant for you.

1. My environment uses my own Azure Data Lake Storage account. Do I still need to update?

   If there's already a Dataverse environment configured in your environment, the update isn't required. If no Dataverse is environment configured, the **Update now** button will create a Dataverse environment and update from the Customer Insights database to a Dataverse database.

1. Will we get extra Dataverse capacity, or will the update use my existing Dataverse capacity?

   - If there's already a Dataverse environment configured in your Customer Insights environment, or connected with other Dynamics 365 or Power Apps applications, the capacity remains unchanged.
   - If the Dataverse environment is new, it will add new storage and database capacity. The capacity added varies per environment and entitlements. You'll get 3 GB for trial and sandbox environment. Production environments get 15 GB.

1. I proceeded with the update and it seems like nothing happened. Is the update complete?

   If the notification in Customer Insights doesn't show anymore, the update is complete. You can check the status of the update by reviewing your environment settings.

1. Why do I still see the banner after completing the update steps?

   It can happen due to an upgrade or refresh failure. Contact support.

1. I received a "Failed to provision Dataverse environment" error after starting the update. What happened?

   It can happen due to an upgrade or refresh failure. Contact support.
   Common causes:
    - Insufficient capacity. There's no more capacity to create more environments. For more information, see [Manage capacity action](/power-platform/admin/capacity-storage#actions-to-take-for-a-storage-capacity-deficit).
    - Region mismatch between tenant region and Customer Insights environment region in the Australia and India regions.
    - Insufficient privileges to provision Dataverse. The users starting the update needs a Dynamics 365 admin role.
    - -->
