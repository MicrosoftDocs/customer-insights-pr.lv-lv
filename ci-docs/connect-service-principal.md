---
title: Savienojuma izveide ar Azure Data Lake Storage kontu, izmantojot pakalpojuma primāro nosaukumu
description: Izmantojiet Azure pakalpojuma primāro nosaukumu, lai izveidotu savienojumu ar savu Data Lake.
ms.date: 04/26/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: 776eee79c25edbd40ed119510a314f5126933c3e
ms.sourcegitcommit: a50c5e70d2baf4db41a349162fd1b1f84c3e03b6
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 05/11/2022
ms.locfileid: "8739171"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>Savienojuma izveide ar Azure Data Lake Storage kontu, izmantojot Azure pakalpojuma primāro nosaukumu

Šajā rakstā ir aplūkots, kā izveidot savienojumu Dynamics 365 Customer Insights ar Azure Data Lake Storage kontu, izmantojot Azure pakalpojuma vadītāju, nevis krātuves konta atslēgas. 

Automatizētajiem rīkiem, kas izmanto pakalpojumu Azure pakalpojumus, vienmēr jābūt ierobežotām atļaujām. Tā vietā, lai lietojumprogrammās pieteiktos kā pilnībā priviliģēts lietotājs, Azure piedāvā pakalpojuma primāros nosaukumus. Varat izmantot pakalpojumu vadītājus, lai droši [pievienotu vai rediģētu mapi Bieži lietots datu modelis kā datu avots](connect-common-data-model.md) vai [izveidotu vai atjauninātu vidi](create-environment.md).

> [!IMPORTANT]
> - Datu ezera krātuves kontam, kas izmantos pakalpojuma principālu, jābūt Gen2 un jābūt iespējotam [hierarhiskai nosaukumvietai](/azure/storage/blobs/data-lake-storage-namespace). Azure Data Lake Gen1 krātuves konti netiek atbalstīti.
> - Lai izveidotu pakalpojuma principālu, Azure abonementam ir nepieciešamas administratora atļaujas.

## <a name="create-an-azure-service-principal-for-customer-insights"></a>Azure pakalpojuma primārā nosaukuma izveide programmā Customer Insights

Pirms klienta ieskatiem tiek izveidots jauns servisa vadītājs, pārbaudiet, vai tas jau pastāv jūsu organizācijā.

### <a name="look-for-an-existing-service-principal"></a>Meklējiet esošu pakalpojuma primāro nosaukumu

1. Apmeklējiet [Azure administratora portālu](https://portal.azure.com) un piesakieties savā organizācijā.

2. No **Azure pakalpojumi** atlasiet **Azure Active Directory**.

3. Sadaļā **Pārvaldīt** atlasiet **Uzņēmuma lietojumprogrammas**.

4. Pievienojiet filtru **lietojumprogrammas ID, sāciet ar**`0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` nosaukumu vai meklējiet to `Dynamics 365 AI for Customer Insights`.

5. Ja atradīsit atbilstošu ierakstu, tas nozīmē, ka pakalpojuma primārais nosaukums jau pastāv. 
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Ekrānuzņēmums, kurā redzams esošs pakalpojuma primārais nosaukums.":::
   
6. Ja netiek atgriezti rezultāti, izveidojiet jaunu pakalpojuma primāro nosaukumu.

### <a name="create-a-new-service-principal"></a>Izveidot jaunu pakalpojuma primāro nosaukumu

1. Instalējiet jaunāko Azure Active Directory PowerShell versiju pakalpojumam Graph. Lai iegūtu papildinformāciju, skatiet [Instalēt Azure Active Directory PowerShell pakalpojumam Graph](/powershell/azure/active-directory/install-adv2).

   1. Datorā atlasiet tastatūras taustiņu Windows un meklējiet **Windows PowerShell** un atlasiet opciju **Palaist kā administratoram**.
   
   1. PowerShell logā, kas tiek atvērts, ievadiet `Install-Module AzureAD`.

2. Izveidojiet Customer Insights pakalpojuma primāro nosaukumu, izmantojot Azure AD PowerShell moduli.

   1. PowerShell logā, kas tiek atvērts, ievadiet `Connect-AzureAD -TenantId "[your Directory ID]" -AzureEnvironmentName Azure`. Aizstājiet *[savu direktorija ID]* ar faktisko Azure abonementa direktorija ID, kurā vēlaties izveidot pakalpojuma principālu. Atjaunotās vides nosaukuma parametrs `AzureEnvironmentName` nav obligāts.
  
   1. Ievadīt `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. Šī komanda izveido customer insights pakalpojuma vadītāju atlasītajā Azure abonementā. 

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Piešķirt atļaujas pakalpojuma primārajam nosaukumam, lai piekļūtu krātuves kontam

Dodieties uz Azure portālu, lai piešķirtu atļaujas tā krātuves konta pakalpojuma vadītājam, kuru vēlaties izmantot programmā Customer Insights.

1. Apmeklējiet [Azure administratora portālu](https://portal.azure.com) un piesakieties savā organizācijā.

1. Atveriet krātuves kontu, kuram vēlaties piekļūt customer insights pakalpojuma vadītājam.

1. Kreisajā rūtī atlasiet **Piekļuves vadīkla (Access control — IAM)** un pēc tam atlasiet **Pievienot** > **Pievienot lomas piešķiri**.

   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Ekrānuzņēmums, kurā redzams Azure portāls, kas pievieno lomas piešķiri.":::

1. Rūtī **Pievienot lomu piešķiri** iestatiet šādus rekvizītus:
   - Loma: **Krātuve Blob Data Contributor**
   - Piešķirt piekļuvi: **Lietotājam, grupai vai pakalpojuma primārajam nosaukumam**
   - Atlasīt dalībniekus: **Dynamics 365 AI for Customer Insights** (pakalpojumu principāls [,](#create-a-new-service-principal) kuru izveidojāt iepriekš šajā procedūrā)

1.  Atlasiet **Pārskatīšana + piešķirt**.

Lai ieviestu izmaiņas, var paiet 15 minūtes.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-customer-insights"></a>Ievadiet Azure resursa ID vai Azure abonementa informāciju Customer Insights krātuves konta pielikumā

Programmā Customer Insights varat pievienot Datu ezera krātuves kontu, lai [saglabātu izvades datus](manage-environments.md) vai [izmantotu tos kā datu avots](connect-dataverse-managed-lake.md). Šī opcija ļauj izvēlēties starp uz resursiem balstītu vai uz abonementu balstītu pieeju. Atkarībā no izvēlētās pieejas izpildiet procedūru vienā no nākamajām sadaļām.

### <a name="resource-based-storage-account-connection"></a>Uz resursu balstīta krātuves konta savienojuma virkne

1. Atveriet [Azure administratora portālu](https://portal.azure.com), piesakieties savā abonementā un atveriet krātuves kontu.

1. Kreisajā rūtī atveriet **Iestatījumi** > **Rekvizīti**.

1. Nokopējiet krātuves konta resursa ID vērtību.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Nokopējiet krātuves konta resursa ID vērtību.":::

1. Sadaļā Customer Insights ievietojiet resursa ID resursa laukā, kas parādīts krātuves konta savienojuma ekrānā.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Nokopējiet krātuves konta resursa ID vērtību.":::   

1. Lai pievienotu krātuves kontu, turpiniet ar atlikušajām customer insights darbībām.

### <a name="subscription-based-storage-account-connection"></a>Uz abonementu balstīta krātuves konta savienojuma virkne

1. Atveriet [Azure administratora portālu](https://portal.azure.com), piesakieties savā abonementā un atveriet krātuves kontu.

1. Kreisajā rūtī atveriet **Iestatījumi** > **Rekvizīti**.

1. Pārskatiet krātuves **konta abonementu**, **resursu grupu** un **nosaukumu**, lai pārliecinātos, vai programmā Customer Insights atlasāt pareizās vērtības.

1. Programmā Customer Insights, pievienojot krātuves kontu, izvēlieties atbilstošo lauku vērtības.

1. Lai pievienotu krātuves kontu, turpiniet ar atlikušajām customer insights darbībām.


[!INCLUDE [footer-include](includes/footer-banner.md)]