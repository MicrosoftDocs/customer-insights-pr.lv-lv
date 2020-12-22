---
title: Savienojuma izveide ar Azure Data Lake Storage Gen2 kontu ar pakalpojuma primāro nosaukumu
description: Izmantojiet Azure pakalpojuma primāro nosaukumu, lai savienotu auditorijas ieskatus ar savu datu ezeru, pievienojot to auditorijas ieskatiem.
ms.date: 11/24/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: c2fae278d34fa02b9168ac70dfa8dd351653245e
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644097"
---
# <a name="connect-to-an-azure-data-lake-storage-gen2-account-with-an-azure-service-principal-for-audience-insights"></a>Savienojuma izveide ar Azure Data Lake Storage Gen2 kontu ar Azure pakalpojuma primāro nosaukumu auditorijas ieskatiem

Automatizētajiem rīkiem, kas izmanto pakalpojumu Azure pakalpojumus, vienmēr jābūt ierobežotām atļaujām. Tā vietā, lai lietojumprogrammās pieteiktos kā pilnībā priviliģēts lietotājs, Azure piedāvā pakalpojuma primāros nosaukumus. Lasiet tālāk, lai uzzinātu, kā savienot auditorijas ieskatus ar Azure Data Lake Storage Gen2 kontu, izmantojot Azure pakalpojuma primāro nosaukumu, nevis krātuves konta atslēgas. 

Varat izmantot pakalpojuma primāro nosaukumu, lai droši [pievienotu vai rediģētu Common Data Model kā datu avotu](connect-common-data-model.md) vai [izveidotu jaunu vai atjauninātu esošu vidi](manage-environments.md#create-an-environment-in-an-existing-organization).

Lai izveidotu pakalpojuma primāro nosaukumu, jums ir nepieciešamas administratora atļaujas jūsu Azure abonementam.

## <a name="create-azure-service-principal-for-audience-insights"></a>Izveidot Azure pakalpojuma primāro nosaukumu auditorijas ieskatiem

Pirms izveidot jaunu pakalpojuma primāro nosaukumu auditorijas ieskatiem, pārbaudiet, vai tas jau pastāv jūsu organizācijā.

### <a name="look-for-an-existing-service-principal"></a>Meklējiet esošu pakalpojuma primāro nosaukumu

1. Apmeklējiet [Azure administratora portālu](https://portal.azure.com) un piesakieties savā organizācijā.

2. Atlasiet **Azure Active Directory** Azure pakalpojumos.

3. Sadaļā **Pārvaldīt** atlasiet **Uzņēmuma lietojumprogrammas**.

4. Meklējiet auditorijas ieskatus pirmās puses lietojumprogrammas ID `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` vai nosaukumu `Dynamics 365 AI for Customer Insights`.

5. Ja ir atrasts atbilstošs ieraksts, tas nozīmē, ka pastāv auditorijas ieskatiem paredzētā pakalpojuma primārais nosaukums. Jums nekas nav jāizveido no jauna.
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Ekrānuzņēmums, kas rāda esošo pakalpojuma primāro nosaukumu.":::
   
6. Ja netiek atgriezti rezultāti, izveidojiet jaunu pakalpojuma primāro nosaukumu.

### <a name="create-a-new-service-principal"></a>Izveidot jaunu pakalpojuma primāro nosaukumu

1. Instalējiet jaunāko **Azure Active Directory PowerShell versiju programmai Graph**. Papildinformāciju skatiet rakstā programmas [PowerShell instalēšana Azure Active Directory programmai Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).
   - Datorā atlasiet Windows taustiņu uz jūsu tastatūras un meklējiet **Windows PowerShell** un **Palaist kā administratoram**.
   
   - PowerShell logā, kas tiek atvērts, ievadiet `Install-Module AzureAD`.

2. Izveidojiet pakalpojuma primāro nosaukumu auditorijas ieskatiem, izmantojot Azure AD PowerShell Module.
   - PowerShell logā, kas tiek atvērts, ievadiet `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`. Aizstājiet "jūsu nomnieka ID" ar jūsu nomnieka faktisko ID, kurā vēlaties izveidot pakalpojuma primāro nosaukumu. Atjaunotās vides nosaukuma parametrs `AzureEnvironmentName` nav obligāts.
  
   - Ievadīt `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. Izmantojot šo komandu, tiek izveidots pakalpojuma primārais nosaukums, kas paredzēts auditorijas ieskatiem atlasītajā nomniekā.  

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Piešķirt atļaujas pakalpojuma primārajam nosaukumam, lai piekļūtu krātuves kontam

Apmeklējiet Azure portālu, lai sniegtu atļaujas krātuves konta pakalpojuma primārajam nosaukumam, ko vēlaties izmantot auditorijas ieskatos.

1. Apmeklējiet [Azure administratora portālu](https://portal.azure.com) un piesakieties savā organizācijā.

1. Atveriet krātuves kontu, kuram pakalpojuma primārajam nosaukumam jūs vēlaties iegūt piekļuvi.

1. Navigācijas rūtī atlasiet **Piekļuves vadība (IAM)** un atlasiet opciju **Pievienot** > **Pievienot lomas piešķiršanu**.
   
   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Screeshot, kas rāda Azure portālu, pievienojot lomas piešķiršanu.":::
   
1. Rūtī **Pievienot lomu piešķiršanu** iestatiet tālāk norādītos rekvizītus:
   - Loma: *Krātuve Blob Data Contributor*
   - Piešķirt piekļuvi: *Lietotājam, grupai vai pakalpojuma primārajam nosaukumam*
   - Atlasiet: *Dynamics 365 AI Customer Insights* ( [izveidotais pakalpojuma primārais nosaukums](#create-a-new-service-principal))

1.  Atlasiet vienumu **Saglabāt**.

Lai ieviestu izmaiņas, var paiet 15 minūtes.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a>Ievadiet Azure resursa ID vai Azure abonementa informāciju krātuves konta pielikumā Audience Insights.

Lai [glabātu datus par izvadiem](manage-environments.md) vai [izmantotu to kā datu avotu, pievienojiet Azure Data Lake storage kontu](connect-common-data-service-lake.md). Ja ir izvēlēta funkcija Azure Data Lake, varat izvēlēties starp uz resursiem balstītu vai uz abonementu balstītu pieeju.

Izpildiet tālāk sniegtos norādījumus, lai sniegtu nepieciešamo informāciju par izvēlēto pieeju.

### <a name="resounce-based-storage-account-connection"></a>Uz resursu balstīta krātuves konta savienojuma virkne

1. Atveriet [Azure administratora portālu](https://portal.azure.com), piesakieties savā abonementā un atveriet krātuves kontu.

1. Navigācijas rūtī ejiet uz **Iestatījumi** > **Rekvizīti**.

1. Nokopējiet krātuves konta resursa ID vērtību.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Nokopējiet krātuves konta resursa ID vērtību.":::

1. Rīkā auditorijas ieskati ievietojiet resursa ID resursu laukā, kas tiek parādīts krātuves konta savienojuma ekrānā.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Nokopējiet krātuves konta resursa ID vērtību.":::   
   
1. Turpiniet veikt atlikušās darbības auditorijas ieskatos, lai pievienotu krātuves kontu.

### <a name="subscription-based-storage-account-connection"></a>Uz abonementu balstīta krātuves konta savienojuma virkne

1. Atveriet [Azure administratora portālu](https://portal.azure.com), piesakieties savā abonementā un atveriet krātuves kontu.

1. Navigācijas rūtī ejiet uz **Iestatījumi** > **Rekvizīti**.

1. Pārskatiet **Abonements**, **Resursu grupa** un krātuves konta **Nosaukumu**, lai nodrošinātu, ka auditorijas ieskatos ir atlasītas pareizās vērtības.

1. Izmantojot auditorijas ieskatus, varat izvēlēties vērtības vai atbilstošos laukus, pievienojot krātuves kontu.

   :::image type="content" source="media/ADLS-SP-SubscriptionConnection.png" alt-text="Nokopējiet krātuves konta resursa ID vērtību.":::
   
1. Turpiniet veikt atlikušās darbības auditorijas ieskatos, lai pievienotu krātuves kontu.
