---
title: Savienojuma izveide ar Azure Data Lake Storage Gen2 kontu ar pakalpojuma primāro nosaukumu
description: Izmantojiet Azure pakalpojuma primāro nosaukumu, lai savienotu auditorijas ieskatus ar savu data lake, pievienojot to auditorijas ieskatiem.
ms.date: 02/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: eebbac1370a847869d98beaf70db49b809d762e7
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267731"
---
# <a name="connect-to-an-azure-data-lake-storage-gen2-account-with-an-azure-service-principal-for-audience-insights"></a><span data-ttu-id="ad44e-103">Savienojuma izveide ar Azure Data Lake Storage Gen2 kontu ar Azure pakalpojuma primāro nosaukumu auditorijas ieskatiem</span><span class="sxs-lookup"><span data-stu-id="ad44e-103">Connect to an Azure Data Lake Storage Gen2 account with an Azure service principal for audience insights</span></span>

<span data-ttu-id="ad44e-104">Automatizētajiem rīkiem, kas izmanto pakalpojumu Azure pakalpojumus, vienmēr jābūt ierobežotām atļaujām.</span><span class="sxs-lookup"><span data-stu-id="ad44e-104">Automated tools that use Azure services should always have restricted permissions.</span></span> <span data-ttu-id="ad44e-105">Tā vietā, lai lietojumprogrammās pieteiktos kā pilnībā priviliģēts lietotājs, Azure piedāvā pakalpojuma primāros nosaukumus.</span><span class="sxs-lookup"><span data-stu-id="ad44e-105">Instead of having applications sign in as a fully privileged user, Azure offers service principals.</span></span> <span data-ttu-id="ad44e-106">Lasiet tālāk, lai uzzinātu, kā savienot auditorijas ieskatus ar Azure Data Lake Storage Gen2 kontu, izmantojot Azure pakalpojuma primāro nosaukumu, nevis krātuves konta atslēgas.</span><span class="sxs-lookup"><span data-stu-id="ad44e-106">Read on to learn how to connect audience insights with an Azure Data Lake Storage Gen2 account using an Azure service principal instead of storage account keys.</span></span> 

<span data-ttu-id="ad44e-107">Varat izmantot pakalpojuma primāro nosaukumu, lai droši [pievienotu vai rediģētu Common Data Model kā datu avotu](connect-common-data-model.md) vai [izveidotu jaunu vai atjauninātu esošu vidi](manage-environments.md#create-an-environment-in-an-existing-organization).</span><span class="sxs-lookup"><span data-stu-id="ad44e-107">You can use the service principal to securely [add or edit a Common Data Model folder as a data source](connect-common-data-model.md) or [create a new or update an existing environment](manage-environments.md#create-an-environment-in-an-existing-organization).</span></span>

> [!IMPORTANT]
> - <span data-ttu-id="ad44e-108">Azure Data Lake Gen2 krātuves kontam, kas plāno izmantot pakalpojuma primāro nosaukumu, ir jābūt [iespējotai Hierarhiskai nosaukuma vietai (HNS)](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-namespace).</span><span class="sxs-lookup"><span data-stu-id="ad44e-108">The Azure Data Lake Gen2 storage account that intends to use the service principal must have [Hierarchical Name Space (HNS) enabled](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-namespace).</span></span>
> - <span data-ttu-id="ad44e-109">Lai izveidotu pakalpojuma primāro nosaukumu, jums ir nepieciešamas administratora atļaujas jūsu Azure abonementam.</span><span class="sxs-lookup"><span data-stu-id="ad44e-109">You need admin permissions for your Azure subscription to create the service principal.</span></span>

## <a name="create-azure-service-principal-for-audience-insights"></a><span data-ttu-id="ad44e-110">Izveidot Azure pakalpojuma primāro nosaukumu auditorijas ieskatiem</span><span class="sxs-lookup"><span data-stu-id="ad44e-110">Create Azure service principal for audience insights</span></span>

<span data-ttu-id="ad44e-111">Pirms izveidot jaunu pakalpojuma primāro nosaukumu auditorijas ieskatiem, pārbaudiet, vai tas jau pastāv jūsu organizācijā.</span><span class="sxs-lookup"><span data-stu-id="ad44e-111">Before creating a new service principal for audience insights, check if it already exists in your organization.</span></span>

### <a name="look-for-an-existing-service-principal"></a><span data-ttu-id="ad44e-112">Meklējiet esošu pakalpojuma primāro nosaukumu</span><span class="sxs-lookup"><span data-stu-id="ad44e-112">Look for an existing service principal</span></span>

1. <span data-ttu-id="ad44e-113">Apmeklējiet [Azure administratora portālu](https://portal.azure.com) un piesakieties savā organizācijā.</span><span class="sxs-lookup"><span data-stu-id="ad44e-113">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

2. <span data-ttu-id="ad44e-114">Atlasiet **Azure Active Directory** Azure pakalpojumos.</span><span class="sxs-lookup"><span data-stu-id="ad44e-114">Select **Azure Active Directory** from the Azure services.</span></span>

3. <span data-ttu-id="ad44e-115">Sadaļā **Pārvaldīt** atlasiet **Uzņēmuma lietojumprogrammas**.</span><span class="sxs-lookup"><span data-stu-id="ad44e-115">Under **Manage**, select **Enterprise Applications**.</span></span>

4. <span data-ttu-id="ad44e-116">Meklējiet auditorijas ieskatus pirmās puses lietojumprogrammas ID `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` vai nosaukumu `Dynamics 365 AI for Customer Insights`.</span><span class="sxs-lookup"><span data-stu-id="ad44e-116">Search for the audience insights first party application ID `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` or the name `Dynamics 365 AI for Customer Insights`.</span></span>

5. <span data-ttu-id="ad44e-117">Ja ir atrasts atbilstošs ieraksts, tas nozīmē, ka pastāv auditorijas ieskatiem paredzētā pakalpojuma primārais nosaukums.</span><span class="sxs-lookup"><span data-stu-id="ad44e-117">If you find a matching record, it means that the service principal for audience insights exists.</span></span> <span data-ttu-id="ad44e-118">Jums nekas nav jāizveido no jauna.</span><span class="sxs-lookup"><span data-stu-id="ad44e-118">You don't need to create it again.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Ekrānuzņēmums, kas rāda esošo pakalpojuma primāro nosaukumu.":::
   
6. <span data-ttu-id="ad44e-120">Ja netiek atgriezti rezultāti, izveidojiet jaunu pakalpojuma primāro nosaukumu.</span><span class="sxs-lookup"><span data-stu-id="ad44e-120">If no results are returned, create a new service principal.</span></span>

### <a name="create-a-new-service-principal"></a><span data-ttu-id="ad44e-121">Izveidot jaunu pakalpojuma primāro nosaukumu</span><span class="sxs-lookup"><span data-stu-id="ad44e-121">Create a new service principal</span></span>

1. <span data-ttu-id="ad44e-122">Instalējiet jaunāko **Azure Active Directory PowerShell versiju programmai Graph**.</span><span class="sxs-lookup"><span data-stu-id="ad44e-122">Install the latest version of the **Azure Active Directory PowerShell for Graph**.</span></span> <span data-ttu-id="ad44e-123">Papildinformāciju skatiet rakstā programmas [PowerShell instalēšana Azure Active Directory programmai Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).</span><span class="sxs-lookup"><span data-stu-id="ad44e-123">For more information, see [Install Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).</span></span>
   - <span data-ttu-id="ad44e-124">Datorā atlasiet Windows taustiņu uz jūsu tastatūras un meklējiet **Windows PowerShell** un **Palaist kā administratoram**.</span><span class="sxs-lookup"><span data-stu-id="ad44e-124">On your PC, select the Windows key on your keyboard and search for **Windows PowerShell** and **Run as Administrator**.</span></span>
   
   - <span data-ttu-id="ad44e-125">PowerShell logā, kas tiek atvērts, ievadiet `Install-Module AzureAD`.</span><span class="sxs-lookup"><span data-stu-id="ad44e-125">In the PowerShell window that opens, enter `Install-Module AzureAD`.</span></span>

2. <span data-ttu-id="ad44e-126">Izveidojiet pakalpojuma primāro nosaukumu auditorijas ieskatiem, izmantojot Azure AD PowerShell Module.</span><span class="sxs-lookup"><span data-stu-id="ad44e-126">Create the  service principal for audience insights with the Azure AD PowerShell Module.</span></span>
   - <span data-ttu-id="ad44e-127">PowerShell logā, kas tiek atvērts, ievadiet `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`.</span><span class="sxs-lookup"><span data-stu-id="ad44e-127">In the PowerShell window, enter `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`.</span></span> <span data-ttu-id="ad44e-128">Aizstājiet "jūsu nomnieka ID" ar jūsu nomnieka faktisko ID, kurā vēlaties izveidot pakalpojuma primāro nosaukumu.</span><span class="sxs-lookup"><span data-stu-id="ad44e-128">Replace “your tenant ID” with the actual ID of your tenant where you want to create the service principal.</span></span> <span data-ttu-id="ad44e-129">Atjaunotās vides nosaukuma parametrs `AzureEnvironmentName` nav obligāts.</span><span class="sxs-lookup"><span data-stu-id="ad44e-129">The environment name parameter `AzureEnvironmentName` is optional.</span></span>
  
   - <span data-ttu-id="ad44e-130">Ievadīt `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`.</span><span class="sxs-lookup"><span data-stu-id="ad44e-130">Enter `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`.</span></span> <span data-ttu-id="ad44e-131">Izmantojot šo komandu, tiek izveidots pakalpojuma primārais nosaukums, kas paredzēts auditorijas ieskatiem atlasītajā nomniekā.</span><span class="sxs-lookup"><span data-stu-id="ad44e-131">This command creates the service principal for audience insights on the selected tenant.</span></span>  

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a><span data-ttu-id="ad44e-132">Piešķirt atļaujas pakalpojuma primārajam nosaukumam, lai piekļūtu krātuves kontam</span><span class="sxs-lookup"><span data-stu-id="ad44e-132">Grant permissions to the service principal to access the storage account</span></span>

<span data-ttu-id="ad44e-133">Apmeklējiet Azure portālu, lai sniegtu atļaujas krātuves konta pakalpojuma primārajam nosaukumam, ko vēlaties izmantot auditorijas ieskatos.</span><span class="sxs-lookup"><span data-stu-id="ad44e-133">Go to the Azure portal to grant permissions to the service principal for the storage account you want to use in audience insights.</span></span>

1. <span data-ttu-id="ad44e-134">Apmeklējiet [Azure administratora portālu](https://portal.azure.com) un piesakieties savā organizācijā.</span><span class="sxs-lookup"><span data-stu-id="ad44e-134">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

1. <span data-ttu-id="ad44e-135">Atveriet krātuves kontu, kuram pakalpojuma primārajam nosaukumam jūs vēlaties iegūt piekļuvi.</span><span class="sxs-lookup"><span data-stu-id="ad44e-135">Open the storage account you want the service principal for audience insights to have access to.</span></span>

1. <span data-ttu-id="ad44e-136">Navigācijas rūtī atlasiet **Piekļuves vadība (IAM)** un atlasiet opciju **Pievienot** > **Pievienot lomas piešķiršanu**.</span><span class="sxs-lookup"><span data-stu-id="ad44e-136">Select **Access control (IAM)** from the navigation pane and select **Add** > **Add role assignment**.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Screeshot, kas rāda Azure portālu, pievienojot lomas piešķiršanu.":::
   
1. <span data-ttu-id="ad44e-138">Rūtī **Pievienot lomu piešķiršanu** iestatiet tālāk norādītos rekvizītus:</span><span class="sxs-lookup"><span data-stu-id="ad44e-138">In the **Add role assignment** pane, set the following properties:</span></span>
   - <span data-ttu-id="ad44e-139">Loma: *Krātuve Blob Data Contributor*</span><span class="sxs-lookup"><span data-stu-id="ad44e-139">Role: *Storage Blob Data Contributor*</span></span>
   - <span data-ttu-id="ad44e-140">Piešķirt piekļuvi: *Lietotājam, grupai vai pakalpojuma primārajam nosaukumam*</span><span class="sxs-lookup"><span data-stu-id="ad44e-140">Assign access to: *User, group, or service principal*</span></span>
   - <span data-ttu-id="ad44e-141">Atlasiet: *Dynamics 365 AI Customer Insights* ( [izveidotais pakalpojuma primārais nosaukums](#create-a-new-service-principal))</span><span class="sxs-lookup"><span data-stu-id="ad44e-141">Select: *Dynamics 365 AI for Customer Insights* (the [service principal you created](#create-a-new-service-principal))</span></span>

1.  <span data-ttu-id="ad44e-142">Atlasiet vienumu **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="ad44e-142">Select **Save**.</span></span>

<span data-ttu-id="ad44e-143">Lai ieviestu izmaiņas, var paiet 15 minūtes.</span><span class="sxs-lookup"><span data-stu-id="ad44e-143">It can take up to 15 minutes to propagate the changes.</span></span>

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a><span data-ttu-id="ad44e-144">Ievadiet Azure resursa ID vai Azure abonementa informāciju krātuves konta pielikumā Audience Insights.</span><span class="sxs-lookup"><span data-stu-id="ad44e-144">Enter the Azure Resource ID or the Azure Subscription details in the storage account attachment to Audience Insights.</span></span>

<span data-ttu-id="ad44e-145">Lai [glabātu datus par izvadiem](manage-environments.md) vai [izmantotu to kā datu avotu, pievienojiet Azure Data Lake storage kontu](connect-common-data-service-lake.md).</span><span class="sxs-lookup"><span data-stu-id="ad44e-145">Attach an Azure Data Lake storage account in audience insights to [store output data](manage-environments.md) or [use it as a data source](connect-common-data-service-lake.md).</span></span> <span data-ttu-id="ad44e-146">Ja ir izvēlēta funkcija Azure Data Lake, varat izvēlēties starp uz resursiem balstītu vai uz abonementu balstītu pieeju.</span><span class="sxs-lookup"><span data-stu-id="ad44e-146">Choosing the Azure Data Lake option lets you choose between a resource-based or a subscription-based based approach.</span></span>

<span data-ttu-id="ad44e-147">Izpildiet tālāk sniegtos norādījumus, lai sniegtu nepieciešamo informāciju par izvēlēto pieeju.</span><span class="sxs-lookup"><span data-stu-id="ad44e-147">Follow the below steps to provide the required information on the selected approach.</span></span>

### <a name="resource-based-storage-account-connection"></a><span data-ttu-id="ad44e-148">Uz resursu balstīta krātuves konta savienojuma virkne</span><span class="sxs-lookup"><span data-stu-id="ad44e-148">Resource-based storage account connection</span></span>

1. <span data-ttu-id="ad44e-149">Atveriet [Azure administratora portālu](https://portal.azure.com), piesakieties savā abonementā un atveriet krātuves kontu.</span><span class="sxs-lookup"><span data-stu-id="ad44e-149">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="ad44e-150">Navigācijas rūtī ejiet uz **Iestatījumi** > **Rekvizīti**.</span><span class="sxs-lookup"><span data-stu-id="ad44e-150">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="ad44e-151">Nokopējiet krātuves konta resursa ID vērtību.</span><span class="sxs-lookup"><span data-stu-id="ad44e-151">Copy the storage account resource ID value.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Nokopējiet krātuves konta resursa ID vērtību.":::

1. <span data-ttu-id="ad44e-153">Rīkā auditorijas ieskati ievietojiet resursa ID resursu laukā, kas tiek parādīts krātuves konta savienojuma ekrānā.</span><span class="sxs-lookup"><span data-stu-id="ad44e-153">In audience insights, insert the resource ID in the resource field displayed in the storage account connection screen.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Nokopējiet krātuves konta resursa ID vērtību.":::   
   
1. <span data-ttu-id="ad44e-155">Turpiniet veikt atlikušās darbības auditorijas ieskatos, lai pievienotu krātuves kontu.</span><span class="sxs-lookup"><span data-stu-id="ad44e-155">Continue with the remaining steps in audience insights to attach the storage account.</span></span>

### <a name="subscription-based-storage-account-connection"></a><span data-ttu-id="ad44e-156">Uz abonementu balstīta krātuves konta savienojuma virkne</span><span class="sxs-lookup"><span data-stu-id="ad44e-156">Subscription-based storage account connection</span></span>

1. <span data-ttu-id="ad44e-157">Atveriet [Azure administratora portālu](https://portal.azure.com), piesakieties savā abonementā un atveriet krātuves kontu.</span><span class="sxs-lookup"><span data-stu-id="ad44e-157">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="ad44e-158">Navigācijas rūtī ejiet uz **Iestatījumi** > **Rekvizīti**.</span><span class="sxs-lookup"><span data-stu-id="ad44e-158">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="ad44e-159">Pārskatiet **Abonements**, **Resursu grupa** un krātuves konta **Nosaukumu**, lai nodrošinātu, ka auditorijas ieskatos ir atlasītas pareizās vērtības.</span><span class="sxs-lookup"><span data-stu-id="ad44e-159">Review the **Subscription**, **Resource group**, and the **Name** of the storage account to make sure you select the right values in audience insights.</span></span>

1. <span data-ttu-id="ad44e-160">Izmantojot auditorijas ieskatus, varat izvēlēties vērtības vai atbilstošos laukus, pievienojot krātuves kontu.</span><span class="sxs-lookup"><span data-stu-id="ad44e-160">In audience insights, choose the values or for the corresponding fields when attaching the storage account.</span></span>
   
1. <span data-ttu-id="ad44e-161">Turpiniet veikt atlikušās darbības auditorijas ieskatos, lai pievienotu krātuves kontu.</span><span class="sxs-lookup"><span data-stu-id="ad44e-161">Continue with the remaining steps in audience insights to attach the storage account.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]