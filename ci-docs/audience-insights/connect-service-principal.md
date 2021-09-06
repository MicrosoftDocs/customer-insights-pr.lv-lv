---
title: Savienojuma izveide ar Azure Data Lake Storage kontu, izmantojot pakalpojuma primāro nosaukumu
description: Izmantojiet Azure pakalpojuma primāro nosaukumu, lai izveidotu savienojumu ar savu Data Lake.
ms.date: 07/23/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 845d1f55eb99f2adf9b437124addec4f6d016fec
ms.sourcegitcommit: 1c396394470df8e68c2fafe3106567536ff87194
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 08/30/2021
ms.locfileid: "7461157"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>Savienojuma izveide ar Azure Data Lake Storage kontu, izmantojot Azure pakalpojuma primāro nosaukumu
<!--note from editor: The Cloud Style Guide would have us just use "Azure Data Lake Storage" to mean the current version, unless the old version (Gen1) is mentioned. I've followed this guidance, even though it seems that our docs and Azure docs are all over the map on this.-->
Automatizētajiem rīkiem, kas izmanto pakalpojumu Azure pakalpojumus, vienmēr jābūt ierobežotām atļaujām. Tā vietā, lai lietojumprogrammās pieteiktos kā pilnībā priviliģēts lietotājs, Azure piedāvā pakalpojuma primāros nosaukumus. Lasiet tālāk, lai uzzinātu, kā savienot Dynamics 365 Customer Insights ar Azure Data Lake Storage kontu, izmantojot Azure pakalpojuma primāro nosaukumu, nevis krātuves konta atslēgas. 

Varat izmantot pakalpojuma primāro nosaukumu, lai droši [pievienotu vai rediģētu Common Data Model mapi kā datu avotu](connect-common-data-model.md) vai [izveidotu vai atjauninātu vidi](get-started-paid.md).<!--note from editor: Suggested. Or it could be ", or create a new environment or update an existing one". I think "new" is implied with "create". The comma is necessary.-->

> [!IMPORTANT]
> - Data Lake Storage konts, kas izmantos<!--note from editor: Suggested. Or perhaps it could be "The Data Lake Storage account to which you want to give access to the service principal..."--> pakalpojuma primāro nosaukumu ir jābūt [iespējotai hierarhiskai nosaukumvietai](/azure/storage/blobs/data-lake-storage-namespace).
> - Lai izveidotu pakalpojuma primāro nosaukumu, jums ir nepieciešamas administratora atļaujas jūsu Azure abonementam.

## <a name="create-an-azure-service-principal-for-customer-insights"></a>Azure pakalpojuma primārā nosaukuma izveide programmā Customer Insights

Pirms jauna pakalpojuma primārā nosaukuma izveides auditorijas ieskatiem vai ieskatiem par piesaisti pārbaudiet, vai tas jau pastāv organizācijā.

### <a name="look-for-an-existing-service-principal"></a>Meklējiet esošu pakalpojuma primāro nosaukumu

1. Apmeklējiet [Azure administratora portālu](https://portal.azure.com) un piesakieties savā organizācijā.

2. No **Azure pakalpojumi** atlasiet **Azure Active Directory**.

3. Sadaļā **Pārvaldīt** atlasiet **Uzņēmuma lietojumprogrammas**.

4. Meklēt Microsoft<!--note from editor: Via Microsoft Writing Style Guide.--> programmas ID:
   - Auditorijas ieskati: `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` ar nosaukumu `Dynamics 365 AI for Customer Insights`
   - Iesaistes ieskati: `ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd` ar nosaukumu `Dynamics 365 AI for Customer Insights engagement insights`

5. Ja atradīsit atbilstošu ierakstu, tas nozīmē, ka pakalpojuma primārais nosaukums jau pastāv. 
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Ekrānuzņēmums, kurā redzams esošs pakalpojuma primārais nosaukums.":::
   
6. Ja netiek atgriezti rezultāti, izveidojiet jaunu pakalpojuma primāro nosaukumu.

>[!NOTE]
>Lai izmantotu visas Dynamics 365 Customer Insights sniegtās pilnvaras, ieteicams pievienot abas programmas pakalpojuma primārajam nosaukumam.<!--note from editor: Using the note format is suggested, just so this doesn't get lost by being tucked up in the step.-->

### <a name="create-a-new-service-principal"></a>Izveidot jaunu pakalpojuma primāro nosaukumu
<!--note from editor: Some general formatting notes: The MWSG wants bold for text the user enters (in addition to UI strings and the settings users select), but there's plenty of precedent for using code format for entering text in PowerShell so I didn't change that. Note that italic should be used for placeholders, but not much else.-->
1. Instalējiet jaunāko Azure Active Directory PowerShell versiju pakalpojumam Graph. Lai iegūtu papildinformāciju, skatiet [Instalēt Azure Active Directory PowerShell pakalpojumam Graph](/powershell/azure/active-directory/install-adv2).

   1. Datorā atlasiet tastatūras taustiņu Windows un meklējiet **Windows PowerShell** un atlasiet opciju **Palaist kā administratoram**.<!--note from editor: Or should this be something like "search for **Windows PowerShell** and, if asked, select **Run as administrator**."?-->
   
   1. PowerShell logā, kas tiek atvērts, ievadiet `Install-Module AzureAD`.

2. Izveidojiet Customer Insights pakalpojuma primāro nosaukumu, izmantojot Azure AD PowerShell moduli.

   1. PowerShell logā, kas tiek atvērts, ievadiet `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`. Aizvietojiet *"[jūsu nomnieka ID]"*<!--note from editor: Edit okay? Or should the quotation marks stay in the command line, in which case it would be "Replace *[your tenant ID]* --> ar nomnieka faktisko ID, kur vēlaties izveidot pakalpojuma primāro nosaukumu. Atjaunotās vides nosaukuma parametrs `AzureEnvironmentName` nav obligāts.
  
   1. Ievadīt `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. Izmantojot šo komandu, tiek izveidots pakalpojuma primārais nosaukums, kas paredzēts auditorijas ieskatiem atlasītajā nomniekā. 

   1. Ievadīt `New-AzureADServicePrincipal -AppId "ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd" -DisplayName "Dynamics 365 AI for Customer Insights engagement insights"`. Izmantojot šo komandu, pakalpojuma primārais nosaukums tiek izveidots iesaistes ieskatiem<!--note from editor: Edit okay?--> atlasītajā nomniekā.

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Piešķirt atļaujas pakalpojuma primārajam nosaukumam, lai piekļūtu krātuves kontam

Apmeklējiet Azure portālu, lai sniegtu atļaujas krātuves konta pakalpojuma primārajam nosaukumam, ko vēlaties izmantot auditorijas ieskatos.

1. Apmeklējiet [Azure administratora portālu](https://portal.azure.com) un piesakieties savā organizācijā.

1. Atveriet krātuves kontu, kuram pakalpojuma primārajam nosaukumam jūs vēlaties iegūt piekļuvi.

1. Kreisajā rūtī atlasiet **Piekļuves vadīkla (Access control — IAM)** un pēc tam atlasiet **Pievienot** > **Pievienot lomas piešķiri**.

   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Ekrānuzņēmums, kurā redzams Azure portāls, kas pievieno lomas piešķiri.":::

1. Rūtī **Pievienot lomu piešķiri** iestatiet šādus rekvizītus:
   - Loma: **Krātuve Blob Data Contributor**
   - Piešķirt piekļuvi: **Lietotājam, grupai vai pakalpojuma primārajam nosaukumam**
   - Atlasiet: **Dynamics 365 AI for Customer Insights** un **Dynamics 365 AI for Customer Insights piesaistes ieskati** (divi [pakalpojuma primārie nosaukumi](#create-a-new-service-principal) , ko izveidojāt iepriekš šajā procedūrā)

1.  Atlasiet vienumu **Saglabāt**.

Lai ieviestu izmaiņas, var paiet 15 minūtes.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a>Ievadiet Azure resursa ID vai Azure abonementa informāciju krātuves konta pielikumā auditorijas ieskatiem

Varat<!--note from editor: Edit suggested only if this section is optional.--> pievienot Data Lake Storage kontu auditorijas ieskatos, lai [glabātu datus par izvadiem](manage-environments.md) vai [izmantotu to kā datu avotu](connect-common-data-service-lake.md). Šī opcija ļauj izvēlēties starp uz resursiem balstītu vai uz abonementu balstītu pieeju. Atkarībā no izvēlētās pieejas izpildiet procedūru vienā no nākamajām sadaļām.<!--note from editor: Suggested.-->

### <a name="resource-based-storage-account-connection"></a>Uz resursu balstīta krātuves konta savienojuma virkne

1. Atveriet [Azure administratora portālu](https://portal.azure.com), piesakieties savā abonementā un atveriet krātuves kontu.

1. Kreisajā rūtī atveriet **Iestatījumi** > **Rekvizīti**.

1. Nokopējiet krātuves konta resursa ID vērtību.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Nokopējiet krātuves konta resursa ID vērtību.":::

1. Auditorijas ieskatos ievietojiet resursa ID resursu laukā, kas tiek rādīts krātuves konta savienojuma ekrānā.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Nokopējiet krātuves konta resursa ID vērtību.":::   

1. Turpiniet veikt atlikušās darbības auditorijas ieskatos, lai pievienotu krātuves kontu.

### <a name="subscription-based-storage-account-connection"></a>Uz abonementu balstīta krātuves konta savienojuma virkne

1. Atveriet [Azure administratora portālu](https://portal.azure.com), piesakieties savā abonementā un atveriet krātuves kontu.

1. Kreisajā rūtī atveriet **Iestatījumi** > **Rekvizīti**.

1. Pārskatiet **Abonements**, **Resursu grupa** un krātuves konta **Nosaukumu**, lai nodrošinātu, ka auditorijas ieskatos ir atlasītas pareizās vērtības.

1. Pievienojot krātuves kontu, auditorijas ieskatos izvēlieties atbilstošo lauku vērtības.

1. Turpiniet veikt atlikušās darbības auditorijas ieskatos, lai pievienotu krātuves kontu.


[!INCLUDE[footer-include](../includes/footer-banner.md)]