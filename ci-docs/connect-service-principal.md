---
title: Savienojuma izveide ar Azure Data Lake Storage kontu, izmantojot Azure pakalpojuma primāro nosaukumu
description: Izmantojiet Azure pakalpojuma primāro nosaukumu, lai izveidotu savienojumu ar savu Data Lake.
ms.date: 05/31/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: 949caa73578dbe0a511726ec045c0fd5f4621de4
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082242"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>Savienojuma izveide ar Azure Data Lake Storage kontu, izmantojot Azure pakalpojuma primāro nosaukumu

Šajā rakstā ir aprakstīts, kā izveidot savienojumu Dynamics 365 Customer Insights ar Azure Data Lake Storage kontu, izmantojot Azure pakalpojuma principālu, nevis krātuves konta atslēgas.

Automatizētajiem rīkiem, kas izmanto pakalpojumu Azure pakalpojumus, vienmēr jābūt ierobežotām atļaujām. Tā vietā, lai lietojumprogrammās pieteiktos kā pilnībā priviliģēts lietotājs, Azure piedāvā pakalpojuma primāros nosaukumus. Varat izmantot pakalpojumu principālus, lai droši [pievienotu vai rediģētu common data model mapi kā datu avots](connect-common-data-model.md) vai [izveidotu vai atjauninātu vidi](create-environment.md).

> [!IMPORTANT]
>
> - Data Lake Storage kontam, kas izmantos pakalpojuma pamatnoteikumu, ir jābūt Gen2, un tam ir jābūt [iespējotai hierarhiskai nosaukumvietai](/azure/storage/blobs/data-lake-storage-namespace). Azure Data Lake Gen1 krātuves konti netiek atbalstīti.
> - Lai izveidotu pakalpojuma vadītāju, jūsu Azure nomnieks ir nepieciešamas administratora atļaujas.

## <a name="create-an-azure-service-principal-for-customer-insights"></a>Azure pakalpojuma primārā nosaukuma izveide programmā Customer Insights

Pirms izveidojat jaunu customer insights servisa principālu, pārbaudiet, vai tas jau pastāv jūsu organizācijā.

### <a name="look-for-an-existing-service-principal"></a>Meklējiet esošu pakalpojuma primāro nosaukumu

1. Apmeklējiet [Azure administratora portālu](https://portal.azure.com) un piesakieties savā organizācijā.

2. No **Azure pakalpojumi** atlasiet **Azure Active Directory**.

3. Sadaļā **Pārvaldīt** atlasiet **Microsoft lietojumprogramma**.

4. Pievienojiet filtru lietojumprogrammas ID sākšanai **ar**`0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` nosaukumu vai meklējiet to `Dynamics 365 AI for Customer Insights`.

5. Ja atradīsit atbilstošu ierakstu, tas nozīmē, ka pakalpojuma primārais nosaukums jau pastāv.

   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Ekrānuzņēmums, kurā redzams esošs pakalpojuma primārais nosaukums.":::

6. Ja rezultāti netiek atgriezti, varat [izveidot jaunu pakalpojumu principālu](#create-a-new-service-principal). Vairumā gadījumu tas jau pastāv, un jums ir jāpiešķir tikai atļaujas, lai pakalpojuma vadītājs varētu piekļūt krātuves kontam.

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Piešķirt atļaujas pakalpojuma primārajam nosaukumam, lai piekļūtu krātuves kontam

Dodieties uz Azure portālu, lai piešķirtu atļaujas tā krātuves konta pakalpojuma vadītājam, kuru vēlaties izmantot programmā Customer Insights. Krātuves kontam vai konteineram ir jāpiešķir viena no šīm lomām:

|Akreditācijas datu|Prasības:|
|----------|------------|
|Pašlaik pieteicies lietotājs|**Loma**: krātuves Blob datu lasītājs, krātuves Blob līdzstrādnieks vai krātuves Blob īpašnieks.<br>**Līmenis**: atļaujas var piešķirt krātuves kontā vai konteinerā.</br>|
|Customer Insights servisa direktors -<br>Izmantojiet Azure Data Lake Storage kā datu avots</br>|1. opcija<ul><li>**Loma**: krātuves Blob datu lasītājs, krātuves Blob datu līdzstrādnieks vai krātuves Blob datu īpašnieks.</li><li>**Līmenis**: krātuves kontā ir jāpiešķir atļaujas.</li></ul>2 *. iespēja (nekopīgojot pakalpojuma galveno piekļuvi krātuves kontam)*<ul><li>**1**. loma: krātuves Blob datu lasītājs, krātuves Blob datu līdzstrādnieks vai krātuves Blob datu īpašnieks.</li><li>**Līmenis**: konteineram ir jāpiešķir atļaujas.</li><li>**2**. loma: krātuves Blob datu delegators.</li><li>**Līmenis**: krātuves kontā ir jāpiešķir atļaujas.</li></ul>|
|Customer Insights servisa direktors - <br>Izmantošana Azure Data Lake Storage kā izvade vai galamērķis</br>|1. opcija<ul><li>**Loma**: Krātuves Blob datu līdzstrādnieks vai krātuves Blob īpašnieks.</li><li>**Līmenis**: krātuves kontā ir jāpiešķir atļaujas.</li></ul>2 *. iespēja (nekopīgojot pakalpojuma galveno piekļuvi krātuves kontam)*<ul><li>**Loma**: Krātuves Blob datu līdzstrādnieks vai krātuves Blob īpašnieks.</li><li>**Līmenis**: konteineram ir jāpiešķir atļaujas.</li><li>**2**. loma: Krātuves lodes delegators.</li><li>**Līmenis**: krātuves kontā ir jāpiešķir atļaujas.</li></ul>|

1. Apmeklējiet [Azure administratora portālu](https://portal.azure.com) un piesakieties savā organizācijā.

1. Atveriet krātuves kontu, kuram vēlaties piekļūt Customer Insights pakalpojumu principālam.

1. Kreisajā rūtī atlasiet **Piekļuves vadīkla (Access control — IAM)** un pēc tam atlasiet **Pievienot** > **Pievienot lomas piešķiri**.

   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Ekrānuzņēmums, kurā redzams Azure portāls, kas pievieno lomas piešķiri.":::

1. Rūtī **Pievienot lomu piešķiri** iestatiet šādus rekvizītus:
   - Loma: krātuves Blob datu lasītājs, krātuves Blob līdzstrādnieks vai krātuves Blob īpašnieks, pamatojoties uz iepriekš uzskaitītajiem akreditācijas datiem.
   - Piešķirt piekļuvi: **Lietotājam, grupai vai pakalpojuma primārajam nosaukumam**
   - Atlasīt dalībniekus: **Dynamics 365 AI for Customer Insights** ([pakalpojuma vadītājs,](#create-a-new-service-principal) kuru uzmeklējāt iepriekš šajā procedūrā)

1. Atlasiet **Pārskatīt + piešķirt**.

Lai ieviestu izmaiņas, var paiet 15 minūtes.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-customer-insights"></a>Ievadiet Azure resursa ID vai Azure abonementa informāciju krātuves konta pielikumā Customer Insights

Programmā Customer Insights varat pievienot Datu ezera krātuves kontu, lai [saglabātu izvades datus](manage-environments.md) vai [izmantotu tos kā datu avots](connect-dataverse-managed-lake.md). Šī opcija ļauj izvēlēties starp uz resursiem balstītu vai uz abonementu balstītu pieeju. Atkarībā no izvēlētās pieejas izpildiet procedūru vienā no nākamajām sadaļām.

### <a name="resource-based-storage-account-connection"></a>Uz resursu balstīta krātuves konta savienojuma virkne

1. Atveriet [Azure administratora portālu](https://portal.azure.com), piesakieties savā abonementā un atveriet krātuves kontu.

1. Kreisajā rūtī dodieties uz **Iestatījumu** > **galapunkti**.

1. Nokopējiet krātuves konta resursa ID vērtību.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Nokopējiet krātuves konta resursa ID vērtību.":::

1. Programmā Customer Insights ievietojiet resursa ID resursa laukā, kas tiek parādīts krātuves konta savienojuma ekrānā.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Nokopējiet krātuves konta resursa ID vērtību.":::   

1. Turpiniet ar pārējām Customer Insights darbībām, lai pievienotu krātuves kontu.

### <a name="subscription-based-storage-account-connection"></a>Uz abonementu balstīta krātuves konta savienojuma virkne

1. Atveriet [Azure administratora portālu](https://portal.azure.com), piesakieties savā abonementā un atveriet krātuves kontu.

1. Kreisajā rūtī atveriet **Iestatījumi** > **Rekvizīti**.

1. Pārskatiet **abonementu**, **resursu grupu** un **krātuves konta nosaukumu**, lai programmā Customer Insights atlasītu pareizās vērtības.

1. Programmā Customer Insights izvēlieties atbilstošo lauku vērtības, pievienojot krātuves kontu.

1. Turpiniet ar pārējām Customer Insights darbībām, lai pievienotu krātuves kontu.

### <a name="create-a-new-service-principal"></a>Izveidot jaunu pakalpojuma primāro nosaukumu

1. Instalējiet jaunāko Azure Active Directory PowerShell versiju pakalpojumam Graph. Lai iegūtu papildinformāciju, skatiet [Instalēt Azure Active Directory PowerShell pakalpojumam Graph](/powershell/azure/active-directory/install-adv2).

   1. Datorā nospiediet tastatūras Windows taustiņu un meklējiet **Windows PowerShell** un atlasiet **Palaist kā administratoram**.

   1. PowerShell logā, kas tiek atvērts, ievadiet `Install-Module AzureAD`.

2. Izveidojiet Customer Insights pakalpojuma primāro nosaukumu, izmantojot Azure AD PowerShell moduli.

   1. PowerShell logā, kas tiek atvērts, ievadiet `Connect-AzureAD -TenantId "[your Directory ID]" -AzureEnvironmentName Azure`. Aizstājiet *[savu direktorija ID]* ar faktisko direktorija ID savā Azure abonementā, kur vēlaties izveidot pakalpojuma vadītāju. Atjaunotās vides nosaukuma parametrs `AzureEnvironmentName` nav obligāts.
  
   1. Ievadīt `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. Šī komanda izveido customer insights pakalpojuma principālu atlasītajā Azure abonementā.

[!INCLUDE [footer-include](includes/footer-banner.md)]
