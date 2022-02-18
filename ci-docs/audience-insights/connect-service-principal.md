---
title: Savienojuma izveide ar Azure Data Lake Storage kontu, izmantojot pakalpojuma primāro nosaukumu
description: Izmantojiet Azure pakalpojuma primāro nosaukumu, lai izveidotu savienojumu ar savu Data Lake.
ms.date: 12/06/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 1af01e5579f85d7c8bc8976a003f53ef2dd280d1
ms.sourcegitcommit: b7189b8621e66ee738e4164d4b3ce2af0def3f51
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 02/03/2022
ms.locfileid: "8088156"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>Savienojuma izveide ar Azure Data Lake Storage kontu, izmantojot Azure pakalpojuma primāro nosaukumu

Šajā rakstā ir aprakstīts, kā izveidot savienojumu Dynamics 365 Customer Insights ar kontu, Azure Data Lake Storage izmantojot Azure pakalpojuma pamatsummu, nevis krātuves konta atslēgas. 

Automatizētajiem rīkiem, kas izmanto pakalpojumu Azure pakalpojumus, vienmēr jābūt ierobežotām atļaujām. Tā vietā, lai lietojumprogrammās pieteiktos kā pilnībā priviliģēts lietotājs, Azure piedāvā pakalpojuma primāros nosaukumus. Varat izmantot pakalpojumu vadītājus, lai droši [pievienotu vai rediģētu common data model mapi kā datu avots](connect-common-data-model.md) vai [izveidotu vai atjauninātu vidi](create-environment.md).

> [!IMPORTANT]
> - Datu ezera krātuves kontam, kas izmantos pakalpojuma pamatsummu, jābūt Gen2 un jābūt [iespējotam hierarhiskai nosaukumvietai](/azure/storage/blobs/data-lake-storage-namespace). Azure Data Lake Gen1 krātuves konti netiek atbalstīti.
> - Lai izveidotu pakalpojuma vadītāju, Azure abonementam ir nepieciešamas administratora atļaujas.

## <a name="create-an-azure-service-principal-for-customer-insights"></a>Azure pakalpojuma primārā nosaukuma izveide programmā Customer Insights

Pirms izveidot jaunu customer insights servisa vadītāju, pārbaudiet, vai tas jau pastāv jūsu organizācijā.

### <a name="look-for-an-existing-service-principal"></a>Meklējiet esošu pakalpojuma primāro nosaukumu

1. Apmeklējiet [Azure administratora portālu](https://portal.azure.com) un piesakieties savā organizācijā.

2. No **Azure pakalpojumi** atlasiet **Azure Active Directory**.

3. Sadaļā **Pārvaldīt** atlasiet **Uzņēmuma lietojumprogrammas**.

4. Meklējiet Microsoft lietojumprogrammas ID:
   - Auditorijas ieskati: `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` ar nosaukumu `Dynamics 365 AI for Customer Insights`
   - Iesaistes ieskati: `ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd` ar nosaukumu `Dynamics 365 AI for Customer Insights engagement insights`

5. Ja atradīsit atbilstošu ierakstu, tas nozīmē, ka pakalpojuma primārais nosaukums jau pastāv. 
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Ekrānuzņēmums, kurā redzams esošs pakalpojuma primārais nosaukums.":::
   
6. Ja netiek atgriezti rezultāti, izveidojiet jaunu pakalpojuma primāro nosaukumu.

>[!NOTE]
>Lai izmantotu visas Dynamics 365 Customer Insights sniegtās pilnvaras, ieteicams pievienot abas programmas pakalpojuma primārajam nosaukumam.

### <a name="create-a-new-service-principal"></a>Izveidot jaunu pakalpojuma primāro nosaukumu

1. Instalējiet jaunāko Azure Active Directory PowerShell versiju pakalpojumam Graph. Lai iegūtu papildinformāciju, skatiet [Instalēt Azure Active Directory PowerShell pakalpojumam Graph](/powershell/azure/active-directory/install-adv2).

   1. Datorā atlasiet tastatūras taustiņu Windows un meklējiet **Windows PowerShell** un atlasiet opciju **Palaist kā administratoram**.
   
   1. PowerShell logā, kas tiek atvērts, ievadiet `Install-Module AzureAD`.

2. Izveidojiet Customer Insights pakalpojuma primāro nosaukumu, izmantojot Azure AD PowerShell moduli.

   1. PowerShell logā, kas tiek atvērts, ievadiet `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`. Aizstājiet *[jūsu nomnieka ID]* ar jūsu nomnieka faktisko ID, kurā vēlaties izveidot pakalpojuma primāro nosaukumu. Atjaunotās vides nosaukuma parametrs `AzureEnvironmentName` nav obligāts.
  
   1. Ievadīt `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. Izmantojot šo komandu, tiek izveidots pakalpojuma primārais nosaukums, kas paredzēts auditorijas ieskatiem atlasītajā nomniekā. 

   1. Ievadīt `New-AzureADServicePrincipal -AppId "ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd" -DisplayName "Dynamics 365 AI for Customer Insights engagement insights"`. Izmantojot šo komandu, pakalpojuma primārais nosaukums tiek izveidots iesaistes ieskatiem atlasītajā nomniekā.

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

Lai [glabātu datus par izvadiem](manage-environments.md) vai [izmantotu to kā datu avotu, pievienojiet Azure Data Lake storage kontu](connect-common-data-service-lake.md). Šī opcija ļauj izvēlēties starp uz resursiem balstītu vai uz abonementu balstītu pieeju. Atkarībā no izvēlētās pieejas izpildiet procedūru vienā no nākamajām sadaļām.

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
