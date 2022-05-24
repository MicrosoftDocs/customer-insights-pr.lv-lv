---
title: Vižu izveide un pārvaldība
description: Uzziniet, kā pierakstīties pakalpojumā un kā pārvaldīt vides.
ms.date: 03/28/2022
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: adkuppa
ms.author: adkuppa
manager: shellyha
searchScope:
- ci-system-about
- customerInsights
ms.openlocfilehash: 599cbaf4e19c3a7331e92bfc54c701fefe6c69b3
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741050"
---
# <a name="manage-environments"></a>Pārvaldīt vides

## <a name="switch-environments"></a>Pārslēgt vides

Lai mainītu vides, lapas augšējā labajā stūrī atlasiet vadīklu **Vide**.

:::image type="content" source="media/home-page-environment-switcher.png" alt-text="Vadīklas ekrānuzņēmums, lai pārslēgtu vides.":::

Administratori var [izveidot](create-environment.md) un pārvaldīt vides.

## <a name="edit-an-existing-environment"></a>Esošas vides rediģēšana

Jūs varat rediģēt dažas esošās vides detaļas.

1.  Programmas galvenē atlasiet **Vides** atlasītāju.

2.  Atlasiet **Rediģēt** ikonu.

3. Lodziņā **Rediģēt vidi** varat atjaunināt vides iestatījumus.

Papildinformāciju par vides iestatījumiem skatiet sadaļā [Jaunas vides izveide](create-environment.md).

## <a name="connect-to-microsoft-dataverse"></a>Izveidot savienojumu ar Microsoft Dataverse
   
Šī **Microsoft Dataverse** darbība ļauj izveidot Customer Insights savienojumu ar savu Dataverse vidi. 

Nodrošiniet savu Microsoft Dataverse vidi datu (profilu un ieskatu) kopīgošanai ar biznesa lietojumprogrammām, kuru pamatā ir Dataverse, piemēram, Dynamics 365 Marketing vai modeļa vadītas lietojumprogrammas programmā Power Apps.

Lai izmantotu [standarta prognožu modeļus](predictions-overview.md#out-of-box-models), konfigurējiet datu kopīgošanu ar Dataverse. Varat arī iespējot datu inaktivizēšanu no lokāls avotiem, norādot Microsoft Dataverse jūsu organizācijas administrējamo vides URL.

Iespējojot datu kopīgošanu, Microsoft Dataverse atzīmējot izvēles rūtiņu Datu kopīgošana, tiks izraisīta vienreizēja pilnīga datu avotu un visu citu procesu atsvaidzināšana.

> [!IMPORTANT]
> 1. Customer Insights, un, Dataverse lai iespējotu datu kopīgošanu, tam jāatrodas vienā reģionā.
> 1. Vidē ir jābūt globāla administratora lomai Dataverse. Pārbaudiet, vai šī [Dataverse vide ir saistīta ar](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) noteiktām drošības grupām, un pārliecinieties, vai esat pievienots šīm drošības grupām.
> 1. Ar šo vidi jau nav saistīta Dataverse neviena esoša Customer Insights vide. Uzziniet, [kā noņemt esošu savienojumu ar Dataverse vidi](#remove-an-existing-connection-to-a-dataverse-environment).

:::image type="content" source="media/dataverse-enable-datasharing.png" alt-text="Konfigurēšanas opcijas, lai iespējotu datu kopīgošanu ar Microsoft Dataverse.":::

### <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>Iespējot datu kopīgošanu ar Dataverse savu (Azure Data Lake Storage Priekšskatījums)

Ja jūsu vide ir konfigurēta, lai izmantotu savu, Azure Data Lake Storage lai glabātu Customer Insights datus, datu kopīgošanas Microsoft Dataverse iespējošanai ir nepieciešama papildu konfigurācija.

1. Izveidojiet savā Azure abonementā divas drošības grupas - vienu **Reader** drošības grupu un vienu **līdzstrādnieku** drošības grupu un iestatiet Microsoft Dataverse pakalpojumu kā īpašnieku abām drošības grupām.
2. Pārvaldiet piekļuves kontroles sarakstu (ACL) krātuves konta konteinerā CustomerInsights, izmantojot šīs drošības grupas. Microsoft Dataverse Pievienojiet pakalpojumu un visas Dataverse biznesa lietojumprogrammas, piemēram, Dynamics 365 Marketing **, drošības grupai Reader** ar **tikai** lasāmām atļaujām. Pievienojiet *līdzstrādnieku* drošības grupai tikai **Customer Insights lietojumprogrammu**, lai piešķirtu gan lasīšanas, gan **rakstīšanas** atļaujas profilu un ieskatu rakstīšanai.
   
#### <a name="prerequisites"></a>Priekšnoteikumi

Lai izpildītu PowerShell skriptus, ir jāimportē šādi trīs moduļi. 

1. Instalējiet jaunāko PowerShell for Graph [Azure Active Directory versiju](/powershell/azure/active-directory/install-adv2).
   1. Datorā atlasiet tastatūras taustiņu Windows un meklējiet **Windows PowerShell** un atlasiet opciju **Palaist kā administratoram**.
   1. PowerShell logā, kas tiek atvērts, ievadiet `Install-Module AzureAD`.
2. Importēt trīs moduļus.
    1. PowerShell logā ievadiet `Install-Module -Name Az.Accounts` un izpildiet darbības. 
    1. `Install-Module -Name Az.Resources` Atkārtojiet un `Install-Module -Name Az.Storage`.

#### <a name="configuration-steps"></a>Konfigurēšanas darbības

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
        - Izpildiet šo PowerShell skriptu sistēmā Windows PowerShell, norādot Azure abonementa ID, kurā ir jūsu Azure Data Lake Storage, krātuves konta nosaukums, resursu grupas nosaukums un Reader un Contributor drošības grupas ID vērtības. Atveriet PowerShell skriptu redaktorā, lai pārskatītu papildinformāciju un ieviesto loģiku.
        - Kopējiet izvades virkni pēc veiksmīgas skripta palaišanas. Izvades virkne izskatās šādi: `https: //DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`
        
2. Ievadiet izvades virkni, kas kopēta no augšas, **vides konfigurācijas soļa** atļaujas identifikatora Microsoft Dataverse laukā.

:::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="Konfigurācijas opcijas, lai iespējotu datu kopīgošanu no sava ar Azure Data Lake Storage Microsoft Dataverse.":::

Customer Insights neatbalsta šādus datu kopīgošanas scenārijus:
- Ja iespējosit datu kopīgošanu ar Dataverse, jūs nevarēsit [izveidot paredzamas vai trūkstošas vērtības entītijā](predictions.md).
- Ja iespējosit datu kopīgošanu ar Dataverse, customer insights vidē nevarēsit skatīt nevienu papildu PowerBI Embedded atskaiti.

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

## <a name="copy-the-environment-configuration"></a>Izveidojiet vides konfigurācijas kopiju

Kā administrators varat izvēlēties kopēt konfigurāciju no esošas vides, kad izveidojat jaunu. 

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Vides iestatījumos redzamo iestatījumu opciju ekrānuzņēmums.":::

Jūs redzēsiet sarakstu, kurā ir visas jūsu organizācijā pieejamās vides, no kurām varat kopēt datus.

Tiek kopēti tālāk norādītie konfigurācijas iestatījumi.

- Ievadītie/importētie datu avoti
- Datu apvienošanas konfigurācija
- Segmenti
- Mērījumi
- Attiecības
- Darbības
- Meklēšanas un filtrēšanas rādītājs
- Eksportēšanas galamērķi
- Plānotā atsvaidzināšana
- Bagātinājumi
- Modeļu pārvaldība
- Lomu piešķiršana

## <a name="set-up-a-copied-environment"></a>Kopētas vides iestatīšana

Kopējot vides konfigurāciju, šādi dati netiek *kopēti*:

- Klientu profili.
- Datu avota akreditācijas dati. Jums būs jāsniedz akreditācijas dati katram datu avotam un manuāli jāatsvaidzina datu avoti.
- Datu avoti no mapes Common Data Model un Dataverse pārvaldītā data lake. Šos datu avotus ir jāizveido manuāli, izmantojot tādu pašu nosaukumu kā avota vidē.
- Savienojuma noslēpumi, ko izmanto eksportam un bagātināšanai. Jums ir atkārtoti jāautentificē savienojumi un pēc tam atkārtoti jāaktivizē bagātināšana un eksports. 

Kopējot vidi, tiks parādīts apstiprinājuma ziņojums par to, ka ir izveidota jauna vide. Atlasiet **Doties uz datu avotiem**, lai skatītu datu avotu sarakstu.

Visiem datu avotiem būs redzams statuss **Nepieciešami akreditācijas dati**. Rediģējiet datu avotus un ievadiet akreditācijas datus, lai tos atsvaidzinātu.

:::image type="content" source="media/data-sources-copied.png" alt-text="Kopēto un autentifikācijai nepieciešamo datu avotu saraksts.":::

Pēc datu avotu atsvaidzināšanas dodieties uz **Dati** > **Apvienot**. Šeit atradīsit avota vides iestatījumus. Rediģējiet tos pēc nepieciešamības vai atlasiet **Izpildīt**, lai sāktu datu unificēšanas procesu un izveidotu unificētu klienta entītiju.

Kad datu unificēšana ir pabeigta, dodieties uz **Pasākumi** un **Segmenti**, lai atsvaidzinātu arī tos.

Pirms eksportēšanas un bagātināšanas atkārtotas aktivizēšanas dodieties uz **Administrēšanas** > **savienojumi**, lai atkārtoti apstiprinātu savienojumus jaunajā vidē.

## <a name="change-the-owner-of-an-environment"></a>Vides īpašnieka maiņa

Lai gan vairākiem lietotājiem programmā Customer Insights var būt administratora atļaujas, tikai viens lietotājs ir vides īpašnieks. Pēc noklusējuma administrators sākotnēji izveido vidi. Kā vides administrators varat piešķirt īpašumtiesības citam lietotājam ar administratora atļaujām.

1. Programmas galvenē atlasiet **Vides** atlasītāju.

1. Atlasiet **Rediģēt** ikonu.

1. **Lodziņā Vides rediģēšana** dodieties uz soli **Pamatinformācija**.

1. Laukā **Mainīt vides** īpašnieku izvēlieties jauno vides īpašnieku.  

1. Atlasiet **Pārskatīšana un pabeigšana**, pēc tam **Atjauniniet**, lai lietotu izmaiņas. 

## <a name="claim-ownership-of-an-environment"></a>Pieprasīt īpašumtiesības uz vidi

Ja vides īpašnieks pamet organizāciju vai viņa lietotāja konts tiek izdzēsts, videi nebūs īpašnieka. Lietotājs ar administratora atļaujām var pieprasīt īpašumtiesības un kļūt par jauno īpašnieku. Viņi var turpināt piederēt videi vai [mainīt īpašumtiesības uz citu administratoru](#change-the-owner-of-an-environment). 

Lai pieprasītu īpašumtiesības, atlasiet **pogu Uzņemties īpašumtiesības**, kas tiek rādīta katras Customer Insights lapas augšdaļā, kad sākotnējais īpašnieks pameta organizāciju.

## <a name="reset-an-existing-environment"></a>Esošās vides atiestatīšana

Kā vides īpašnieks varat atiestatīt vidi tukšā stāvoklī, ja vēlaties izdzēst visas konfigurācijas un noņemt uzņemtos datus.

1.  Programmas galvenē atlasiet **Vides** atlasītāju. 

2.  Atlasiet vidi, kuru vēlaties atiestatīt, un atlasiet daudzpunkti (**...**). 

3. Izvēlieties opciju **Atiestatīt**. 

4.  Lai apstiprinātu dzēšanu, ievadiet vides nosaukumu un atlasiet **Atiestatīt**.

## <a name="delete-an-existing-environment"></a>Esošas vides dzēšana

Kā vides īpašnieks varat izdzēst administrēto vidi.

1.  Programmas galvenē atlasiet **Vides** atlasītāju.

2.  Atlasiet vidi, kuru vēlaties atiestatīt, un atlasiet daudzpunkti (**...**). 

3. Izvēlieties opciju **Dzēst**. 

4.  Lai apstiprinātu dzēšanu, ievadiet vides nosaukumu un atlasiet **Dzēst**.

> [!NOTE]
> Dzēšot vidi, saistība ar vidi netiek noņemta Dataverse . Uzziniet, [kā noņemt esošu savienojumu ar Dataverse vidi](#remove-an-existing-connection-to-a-dataverse-environment).


[!INCLUDE [footer-include](includes/footer-banner.md)]
