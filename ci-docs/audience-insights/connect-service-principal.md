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
# <a name="connect-to-an-azure-data-lake-storage-gen2-account-with-an-azure-service-principal-for-audience-insights"></a><span data-ttu-id="29865-103">Savienojuma izveide ar Azure Data Lake Storage Gen2 kontu ar Azure pakalpojuma primāro nosaukumu auditorijas ieskatiem</span><span class="sxs-lookup"><span data-stu-id="29865-103">Connect to an Azure Data Lake Storage Gen2 account with an Azure service principal for audience insights</span></span>

<span data-ttu-id="29865-104">Automatizētajiem rīkiem, kas izmanto pakalpojumu Azure pakalpojumus, vienmēr jābūt ierobežotām atļaujām.</span><span class="sxs-lookup"><span data-stu-id="29865-104">Automated tools that use Azure services should always have restricted permissions.</span></span> <span data-ttu-id="29865-105">Tā vietā, lai lietojumprogrammās pieteiktos kā pilnībā priviliģēts lietotājs, Azure piedāvā pakalpojuma primāros nosaukumus.</span><span class="sxs-lookup"><span data-stu-id="29865-105">Instead of having applications sign in as a fully privileged user, Azure offers service principals.</span></span> <span data-ttu-id="29865-106">Lasiet tālāk, lai uzzinātu, kā savienot auditorijas ieskatus ar Azure Data Lake Storage Gen2 kontu, izmantojot Azure pakalpojuma primāro nosaukumu, nevis krātuves konta atslēgas.</span><span class="sxs-lookup"><span data-stu-id="29865-106">Read on to learn how to connect audience insights with an Azure Data Lake Storage Gen2 account using an Azure service principal instead of storage account keys.</span></span> 

<span data-ttu-id="29865-107">Varat izmantot pakalpojuma primāro nosaukumu, lai droši [pievienotu vai rediģētu Common Data Model kā datu avotu](connect-common-data-model.md) vai [izveidotu jaunu vai atjauninātu esošu vidi](manage-environments.md#create-an-environment-in-an-existing-organization).</span><span class="sxs-lookup"><span data-stu-id="29865-107">You can use the service principal to securely [add or edit a Common Data Model folder as a data source](connect-common-data-model.md) or [create a new or update an existing environment](manage-environments.md#create-an-environment-in-an-existing-organization).</span></span>

<span data-ttu-id="29865-108">Lai izveidotu pakalpojuma primāro nosaukumu, jums ir nepieciešamas administratora atļaujas jūsu Azure abonementam.</span><span class="sxs-lookup"><span data-stu-id="29865-108">You need admin permissions for your Azure subscription to create the service principal.</span></span>

## <a name="create-azure-service-principal-for-audience-insights"></a><span data-ttu-id="29865-109">Izveidot Azure pakalpojuma primāro nosaukumu auditorijas ieskatiem</span><span class="sxs-lookup"><span data-stu-id="29865-109">Create Azure service principal for audience insights</span></span>

<span data-ttu-id="29865-110">Pirms izveidot jaunu pakalpojuma primāro nosaukumu auditorijas ieskatiem, pārbaudiet, vai tas jau pastāv jūsu organizācijā.</span><span class="sxs-lookup"><span data-stu-id="29865-110">Before creating a new service principal for audience insights, check if it already exists in your organization.</span></span>

### <a name="look-for-an-existing-service-principal"></a><span data-ttu-id="29865-111">Meklējiet esošu pakalpojuma primāro nosaukumu</span><span class="sxs-lookup"><span data-stu-id="29865-111">Look for an existing service principal</span></span>

1. <span data-ttu-id="29865-112">Apmeklējiet [Azure administratora portālu](https://portal.azure.com) un piesakieties savā organizācijā.</span><span class="sxs-lookup"><span data-stu-id="29865-112">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

2. <span data-ttu-id="29865-113">Atlasiet **Azure Active Directory** Azure pakalpojumos.</span><span class="sxs-lookup"><span data-stu-id="29865-113">Select **Azure Active Directory** from the Azure services.</span></span>

3. <span data-ttu-id="29865-114">Sadaļā **Pārvaldīt** atlasiet **Uzņēmuma lietojumprogrammas**.</span><span class="sxs-lookup"><span data-stu-id="29865-114">Under **Manage**, select **Enterprise Applications**.</span></span>

4. <span data-ttu-id="29865-115">Meklējiet auditorijas ieskatus pirmās puses lietojumprogrammas ID `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` vai nosaukumu `Dynamics 365 AI for Customer Insights`.</span><span class="sxs-lookup"><span data-stu-id="29865-115">Search for the audience insights first party application ID `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` or the name `Dynamics 365 AI for Customer Insights`.</span></span>

5. <span data-ttu-id="29865-116">Ja ir atrasts atbilstošs ieraksts, tas nozīmē, ka pastāv auditorijas ieskatiem paredzētā pakalpojuma primārais nosaukums.</span><span class="sxs-lookup"><span data-stu-id="29865-116">If you find a matching record, it means that the service principal for audience insights exists.</span></span> <span data-ttu-id="29865-117">Jums nekas nav jāizveido no jauna.</span><span class="sxs-lookup"><span data-stu-id="29865-117">You don't need to create it again.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Ekrānuzņēmums, kas rāda esošo pakalpojuma primāro nosaukumu.":::
   
6. <span data-ttu-id="29865-119">Ja netiek atgriezti rezultāti, izveidojiet jaunu pakalpojuma primāro nosaukumu.</span><span class="sxs-lookup"><span data-stu-id="29865-119">If no results are returned, create a new service principal.</span></span>

### <a name="create-a-new-service-principal"></a><span data-ttu-id="29865-120">Izveidot jaunu pakalpojuma primāro nosaukumu</span><span class="sxs-lookup"><span data-stu-id="29865-120">Create a new service principal</span></span>

1. <span data-ttu-id="29865-121">Instalējiet jaunāko **Azure Active Directory PowerShell versiju programmai Graph**.</span><span class="sxs-lookup"><span data-stu-id="29865-121">Install the latest version of the **Azure Active Directory PowerShell for Graph**.</span></span> <span data-ttu-id="29865-122">Papildinformāciju skatiet rakstā programmas [PowerShell instalēšana Azure Active Directory programmai Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).</span><span class="sxs-lookup"><span data-stu-id="29865-122">For more information, see [Install Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).</span></span>
   - <span data-ttu-id="29865-123">Datorā atlasiet Windows taustiņu uz jūsu tastatūras un meklējiet **Windows PowerShell** un **Palaist kā administratoram**.</span><span class="sxs-lookup"><span data-stu-id="29865-123">On your PC, select the Windows key on your keyboard and search for **Windows PowerShell** and **Run as Administrator**.</span></span>
   
   - <span data-ttu-id="29865-124">PowerShell logā, kas tiek atvērts, ievadiet `Install-Module AzureAD`.</span><span class="sxs-lookup"><span data-stu-id="29865-124">In the PowerShell window that opens, enter `Install-Module AzureAD`.</span></span>

2. <span data-ttu-id="29865-125">Izveidojiet pakalpojuma primāro nosaukumu auditorijas ieskatiem, izmantojot Azure AD PowerShell Module.</span><span class="sxs-lookup"><span data-stu-id="29865-125">Create the  service principal for audience insights with the Azure AD PowerShell Module.</span></span>
   - <span data-ttu-id="29865-126">PowerShell logā, kas tiek atvērts, ievadiet `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`.</span><span class="sxs-lookup"><span data-stu-id="29865-126">In the PowerShell window, enter `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`.</span></span> <span data-ttu-id="29865-127">Aizstājiet "jūsu nomnieka ID" ar jūsu nomnieka faktisko ID, kurā vēlaties izveidot pakalpojuma primāro nosaukumu.</span><span class="sxs-lookup"><span data-stu-id="29865-127">Replace “your tenant ID” with the actual ID of your tenant where you want to create the service principal.</span></span> <span data-ttu-id="29865-128">Atjaunotās vides nosaukuma parametrs `AzureEnvironmentName` nav obligāts.</span><span class="sxs-lookup"><span data-stu-id="29865-128">The environment name parameter `AzureEnvironmentName` is optional.</span></span>
  
   - <span data-ttu-id="29865-129">Ievadīt `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`.</span><span class="sxs-lookup"><span data-stu-id="29865-129">Enter `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`.</span></span> <span data-ttu-id="29865-130">Izmantojot šo komandu, tiek izveidots pakalpojuma primārais nosaukums, kas paredzēts auditorijas ieskatiem atlasītajā nomniekā.</span><span class="sxs-lookup"><span data-stu-id="29865-130">This command creates the service principal for audience insights on the selected tenant.</span></span>  

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a><span data-ttu-id="29865-131">Piešķirt atļaujas pakalpojuma primārajam nosaukumam, lai piekļūtu krātuves kontam</span><span class="sxs-lookup"><span data-stu-id="29865-131">Grant permissions to the service principal to access the storage account</span></span>

<span data-ttu-id="29865-132">Apmeklējiet Azure portālu, lai sniegtu atļaujas krātuves konta pakalpojuma primārajam nosaukumam, ko vēlaties izmantot auditorijas ieskatos.</span><span class="sxs-lookup"><span data-stu-id="29865-132">Go to the Azure portal to grant permissions to the service principal for the storage account you want to use in audience insights.</span></span>

1. <span data-ttu-id="29865-133">Apmeklējiet [Azure administratora portālu](https://portal.azure.com) un piesakieties savā organizācijā.</span><span class="sxs-lookup"><span data-stu-id="29865-133">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

1. <span data-ttu-id="29865-134">Atveriet krātuves kontu, kuram pakalpojuma primārajam nosaukumam jūs vēlaties iegūt piekļuvi.</span><span class="sxs-lookup"><span data-stu-id="29865-134">Open the storage account you want the service principal for audience insights to have access to.</span></span>

1. <span data-ttu-id="29865-135">Navigācijas rūtī atlasiet **Piekļuves vadība (IAM)** un atlasiet opciju **Pievienot** > **Pievienot lomas piešķiršanu**.</span><span class="sxs-lookup"><span data-stu-id="29865-135">Select **Access control (IAM)** from the navigation pane and select **Add** > **Add role assignment**.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Screeshot, kas rāda Azure portālu, pievienojot lomas piešķiršanu.":::
   
1. <span data-ttu-id="29865-137">Rūtī **Pievienot lomu piešķiršanu** iestatiet tālāk norādītos rekvizītus:</span><span class="sxs-lookup"><span data-stu-id="29865-137">In the **Add role assignment** pane, set the following properties:</span></span>
   - <span data-ttu-id="29865-138">Loma: *Krātuve Blob Data Contributor*</span><span class="sxs-lookup"><span data-stu-id="29865-138">Role: *Storage Blob Data Contributor*</span></span>
   - <span data-ttu-id="29865-139">Piešķirt piekļuvi: *Lietotājam, grupai vai pakalpojuma primārajam nosaukumam*</span><span class="sxs-lookup"><span data-stu-id="29865-139">Assign access to: *User, group, or service principal*</span></span>
   - <span data-ttu-id="29865-140">Atlasiet: *Dynamics 365 AI Customer Insights* ( [izveidotais pakalpojuma primārais nosaukums](#create-a-new-service-principal))</span><span class="sxs-lookup"><span data-stu-id="29865-140">Select: *Dynamics 365 AI for Customer Insights* (the [service principal you created](#create-a-new-service-principal))</span></span>

1.  <span data-ttu-id="29865-141">Atlasiet vienumu **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="29865-141">Select **Save**.</span></span>

<span data-ttu-id="29865-142">Lai ieviestu izmaiņas, var paiet 15 minūtes.</span><span class="sxs-lookup"><span data-stu-id="29865-142">It can take up to 15 minutes to propagate the changes.</span></span>

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a><span data-ttu-id="29865-143">Ievadiet Azure resursa ID vai Azure abonementa informāciju krātuves konta pielikumā Audience Insights.</span><span class="sxs-lookup"><span data-stu-id="29865-143">Enter the Azure Resource ID or the Azure Subscription details in the storage account attachment to Audience Insights.</span></span>

<span data-ttu-id="29865-144">Lai [glabātu datus par izvadiem](manage-environments.md) vai [izmantotu to kā datu avotu, pievienojiet Azure Data Lake storage kontu](connect-common-data-service-lake.md).</span><span class="sxs-lookup"><span data-stu-id="29865-144">Attach an Azure Data Lake storage account in audience insights to [store output data](manage-environments.md) or [use it as a data source](connect-common-data-service-lake.md).</span></span> <span data-ttu-id="29865-145">Ja ir izvēlēta funkcija Azure Data Lake, varat izvēlēties starp uz resursiem balstītu vai uz abonementu balstītu pieeju.</span><span class="sxs-lookup"><span data-stu-id="29865-145">Choosing the Azure Data Lake option lets you choose between a resource-based or a subscription-based based approach.</span></span>

<span data-ttu-id="29865-146">Izpildiet tālāk sniegtos norādījumus, lai sniegtu nepieciešamo informāciju par izvēlēto pieeju.</span><span class="sxs-lookup"><span data-stu-id="29865-146">Follow the below steps to provide the required information on the selected approach.</span></span>

### <a name="resounce-based-storage-account-connection"></a><span data-ttu-id="29865-147">Uz resursu balstīta krātuves konta savienojuma virkne</span><span class="sxs-lookup"><span data-stu-id="29865-147">Resounce-based storage account connection</span></span>

1. <span data-ttu-id="29865-148">Atveriet [Azure administratora portālu](https://portal.azure.com), piesakieties savā abonementā un atveriet krātuves kontu.</span><span class="sxs-lookup"><span data-stu-id="29865-148">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="29865-149">Navigācijas rūtī ejiet uz **Iestatījumi** > **Rekvizīti**.</span><span class="sxs-lookup"><span data-stu-id="29865-149">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="29865-150">Nokopējiet krātuves konta resursa ID vērtību.</span><span class="sxs-lookup"><span data-stu-id="29865-150">Copy the storage account resource ID value.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Nokopējiet krātuves konta resursa ID vērtību.":::

1. <span data-ttu-id="29865-152">Rīkā auditorijas ieskati ievietojiet resursa ID resursu laukā, kas tiek parādīts krātuves konta savienojuma ekrānā.</span><span class="sxs-lookup"><span data-stu-id="29865-152">In audience insights, insert the resource ID in the resource field displayed in the storage account connection screen.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Nokopējiet krātuves konta resursa ID vērtību.":::   
   
1. <span data-ttu-id="29865-154">Turpiniet veikt atlikušās darbības auditorijas ieskatos, lai pievienotu krātuves kontu.</span><span class="sxs-lookup"><span data-stu-id="29865-154">Continue with the remaining steps in audience insights to attach the storage account.</span></span>

### <a name="subscription-based-storage-account-connection"></a><span data-ttu-id="29865-155">Uz abonementu balstīta krātuves konta savienojuma virkne</span><span class="sxs-lookup"><span data-stu-id="29865-155">Subscription-based storage account connection</span></span>

1. <span data-ttu-id="29865-156">Atveriet [Azure administratora portālu](https://portal.azure.com), piesakieties savā abonementā un atveriet krātuves kontu.</span><span class="sxs-lookup"><span data-stu-id="29865-156">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="29865-157">Navigācijas rūtī ejiet uz **Iestatījumi** > **Rekvizīti**.</span><span class="sxs-lookup"><span data-stu-id="29865-157">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="29865-158">Pārskatiet **Abonements**, **Resursu grupa** un krātuves konta **Nosaukumu**, lai nodrošinātu, ka auditorijas ieskatos ir atlasītas pareizās vērtības.</span><span class="sxs-lookup"><span data-stu-id="29865-158">Review the **Subscription**, **Resource group**, and the **Name** of the storage account to make sure you select the right values in audience insights.</span></span>

1. <span data-ttu-id="29865-159">Izmantojot auditorijas ieskatus, varat izvēlēties vērtības vai atbilstošos laukus, pievienojot krātuves kontu.</span><span class="sxs-lookup"><span data-stu-id="29865-159">In audience insights, choose the values or for the corresponding fields when attaching the storage account.</span></span>

   :::image type="content" source="media/ADLS-SP-SubscriptionConnection.png" alt-text="Nokopējiet krātuves konta resursa ID vērtību.":::
   
1. <span data-ttu-id="29865-161">Turpiniet veikt atlikušās darbības auditorijas ieskatos, lai pievienotu krātuves kontu.</span><span class="sxs-lookup"><span data-stu-id="29865-161">Continue with the remaining steps in audience insights to attach the storage account.</span></span>
