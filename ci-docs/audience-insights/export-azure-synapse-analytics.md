---
title: Customer Insights datu eksportēšana uz Azure Synapse Analytics
description: Uzziniet, kā konfigurēt savienojumu un eksportēt uz Azure Synapse Analytics.
ms.date: 04/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 822082d661863e737ea3d3a749a6c878db766967
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 05/04/2021
ms.locfileid: "5977386"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a><span data-ttu-id="0ce82-103">Eksportēt datus uz Azure Synapse Analytics (priekšskatījums)</span><span class="sxs-lookup"><span data-stu-id="0ce82-103">Export data to Azure Synapse Analytics (Preview)</span></span>

<span data-ttu-id="0ce82-104">Azure Synapse ir analīzes pakalpojums, kas paātrina laiku, lai gūtu ieskatu datu noliktavās un lielās datu sistēmās.</span><span class="sxs-lookup"><span data-stu-id="0ce82-104">Azure Synapse is an analytics service that accelerates time to insight across data warehouses and big data systems.</span></span> <span data-ttu-id="0ce82-105">Jūs varat uzņemt un izmantot Customer Insights datus programmā [Azure Synapse](/azure/synapse-analytics/overview-what-is).</span><span class="sxs-lookup"><span data-stu-id="0ce82-105">You can ingest and use your Customer Insights data in [Azure Synapse](/azure/synapse-analytics/overview-what-is).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="0ce82-106">Priekšnosacījumi</span><span class="sxs-lookup"><span data-stu-id="0ce82-106">Prerequisites</span></span>

<span data-ttu-id="0ce82-107">Lai konfigurētu savienojumu no Customer Insights uz Azure Synapse, ir jāizpilda tālāk sniegtie priekšnosacījumi. </span><span class="sxs-lookup"><span data-stu-id="0ce82-107">The following prerequisites must be met to configure the connection from Customer Insights to Azure Synapse.</span></span>

> [!NOTE]
> <span data-ttu-id="0ce82-108">Noteikti iestatiet visas **lomu piešķires**, kā aprakstīts.</span><span class="sxs-lookup"><span data-stu-id="0ce82-108">Make sure to set all **role assignments** as described.</span></span>  

## <a name="prerequisites-in-customer-insights"></a><span data-ttu-id="0ce82-109">Customer Insights priekšnosacījumi</span><span class="sxs-lookup"><span data-stu-id="0ce82-109">Prerequisites in Customer Insights</span></span>

* <span data-ttu-id="0ce82-110">Auditorijas ieskatos jums ir **Administratora** loma.</span><span class="sxs-lookup"><span data-stu-id="0ce82-110">You have an **Administrator** role in audience insights.</span></span> <span data-ttu-id="0ce82-111">Papildinformācija par [lietotāju atļauju iestatīšanu auditorijas ieskatos](permissions.md#assign-roles-and-permissions)</span><span class="sxs-lookup"><span data-stu-id="0ce82-111">Learn more about [setting user permissions in audience insights](permissions.md#assign-roles-and-permissions)</span></span>

<span data-ttu-id="0ce82-112">Azure:</span><span class="sxs-lookup"><span data-stu-id="0ce82-112">In Azure:</span></span> 

- <span data-ttu-id="0ce82-113">Aktīvs Azure abonements.</span><span class="sxs-lookup"><span data-stu-id="0ce82-113">An active Azure subscription.</span></span>

- <span data-ttu-id="0ce82-114">Ja izmantojat jaunu Azure Data Lake Storage Gen2 kontu, *pakalpojuma vadītājam auditorijas ieskatiem* ir nepieciešamas **Krātuves BLOB datu līdzdalībnieku** atļaujas.</span><span class="sxs-lookup"><span data-stu-id="0ce82-114">If using a new Azure Data Lake Storage Gen2 account, the *service principal for audience insights* needs **Storage Blob Data Contributor** permissions.</span></span> <span data-ttu-id="0ce82-115">Uzziniet vairāk [par to, kā izveidot Azure Data Lake Storage Gen2 kontu savienojumu ar Azure pakalpojumu vadītāju auditorijas ieskatiem](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="0ce82-115">Learn more on [connecting to an Azure Data Lake Storage Gen2 account with Azure service principal for audience insights](connect-service-principal.md).</span></span> <span data-ttu-id="0ce82-116">The Data Lake Storage Gen2 **jābūt** iespējotai [hierarhiskajai nosaukumvietai](/azure/storage/blobs/data-lake-storage-namespace).</span><span class="sxs-lookup"><span data-stu-id="0ce82-116">The Data Lake Storage Gen2 **must have** [hierarchical namespace](/azure/storage/blobs/data-lake-storage-namespace) enabled.</span></span>

- <span data-ttu-id="0ce82-117">Resursu grupā, kas atrodas Azure Synapse darbvietā, *servisa vadītājam* un *auditorijas ieskatu lietotājam* ir jāpiešķir vismaz **Lasītāja** atļaujas.</span><span class="sxs-lookup"><span data-stu-id="0ce82-117">On the resource group the Azure Synapse workspace is located, the *service principal* and the *user for audience insights* needs to be assigned at least **Reader** permissions.</span></span> <span data-ttu-id="0ce82-118">Papildinformāciju skatiet sadaļā [Azure lomu piešķiršana, izmantojot Azure portālu](/azure/role-based-access-control/role-assignments-portal).</span><span class="sxs-lookup"><span data-stu-id="0ce82-118">For more information, see [Assign Azure roles using the Azure portal](/azure/role-based-access-control/role-assignments-portal).</span></span>

- <span data-ttu-id="0ce82-119">*Lietotājam* ir nepieciešamas **Blob datu līdzdalībā glabātavas** atļaujas Azure Data Lake Storage Gen2 kontā, kur šie dati atrodas un ir saistīti ar šo Azure Synapse darbvietu.</span><span class="sxs-lookup"><span data-stu-id="0ce82-119">The *user* needs **Storage Blob Data Contributor** permissions on the Azure Data Lake Storage Gen2 account where the data is located and linked to the Azure Synapse workspace.</span></span> <span data-ttu-id="0ce82-120">Uzziniet vairāk par [Azure portāla izmantošanas iespēju, lai piešķirtu Azure lomu piekļuvei BLOB un rindas datiem](/azure/storage/common/storage-auth-aad-rbac-portal) un [Krātuves Blob datu līdzdalības atļaujām](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span><span class="sxs-lookup"><span data-stu-id="0ce82-120">Learn more about [using the Azure portal to assign an Azure role for access to blob and queue data](/azure/storage/common/storage-auth-aad-rbac-portal) and [Storage Blob Data Contributor permissions](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span></span>

- <span data-ttu-id="0ce82-121">*[Azure Synapse darbvietas pārvaldītajai identitātei](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* ir nepieciešamas **Storage Blob datu līdzdalības** atļaujas Azure Data Lake Storage Gen2 kontā, kur atrodas dati un ir saistīti ar Azure Synapse darbvietu.</span><span class="sxs-lookup"><span data-stu-id="0ce82-121">The *[Azure Synapse workspace managed identity](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* needs **Storage Blob Data Contributor** permissions on the Azure Data Lake Storage Gen2 account where the data is located and linked to the Azure Synapse workspace.</span></span> <span data-ttu-id="0ce82-122">Uzziniet vairāk par [Azure portāla izmantošanas iespēju, lai piešķirtu Azure lomu piekļuvei BLOB un rindas datiem](/azure/storage/common/storage-auth-aad-rbac-portal) un [Krātuves Blob datu līdzdalības atļaujām](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span><span class="sxs-lookup"><span data-stu-id="0ce82-122">Learn more on [using the Azure portal to assign an Azure role for access to blob and queue data](/azure/storage/common/storage-auth-aad-rbac-portal) and [Storage Blob Data Contributor permissions](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span></span>

- <span data-ttu-id="0ce82-123">Darbvietā Azure Synapse *servisa vadītājam auditorijas ieskatiem* ir jāpiešķir **Synapse administratora** loma.</span><span class="sxs-lookup"><span data-stu-id="0ce82-123">On the Azure Synapse workspace, the *service principal for audience insights* needs **Synapse Administrator** role assigned.</span></span> <span data-ttu-id="0ce82-124">Papildinformāciju skatiet rakstā [Kā iestatīt piekļuves vadīklu jūsu Synapse darbvietai](/azure/synapse-analytics/security/how-to-set-up-access-control).</span><span class="sxs-lookup"><span data-stu-id="0ce82-124">For more information, see [How to set up access control for your Synapse workspace](/azure/synapse-analytics/security/how-to-set-up-access-control).</span></span>

## <a name="set-up-the-connection-and-export-to-azure-synapse"></a><span data-ttu-id="0ce82-125">Savienojuma izveide un eksportēšana Azure Synapse</span><span class="sxs-lookup"><span data-stu-id="0ce82-125">Set up the connection and export to Azure Synapse</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="0ce82-126">Savienojuma konfigurēšana</span><span class="sxs-lookup"><span data-stu-id="0ce82-126">Configure a connection</span></span>

1. <span data-ttu-id="0ce82-127">Dodieties uz **Administrators** > **Savienojumi**.</span><span class="sxs-lookup"><span data-stu-id="0ce82-127">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="0ce82-128">Atlasiet **Pievienot savienojumu** un atlasiet **Azure Synapse Analytics** vai atlasiet vienumu **Iestatīt** rūtī **Azure Synapse Analytics**, lai konfigurētu savienojumu.</span><span class="sxs-lookup"><span data-stu-id="0ce82-128">Select **Add connection** and choose **Azure Synapse Analytics** or select the **Set up** on the **Azure Synapse Analytics** tile to configure the connection.</span></span>

1. <span data-ttu-id="0ce82-129">Laukā Parādāmais nosaukums piešķiriet savienojumam atpazīstamu nosaukumu.</span><span class="sxs-lookup"><span data-stu-id="0ce82-129">Give your connection a recognizable name in the Display name field.</span></span> <span data-ttu-id="0ce82-130">Parādāmais nosaukums un nosaukuma veids raksturo šo savienojumu.</span><span class="sxs-lookup"><span data-stu-id="0ce82-130">The name and the type of the connection describes this connection.</span></span> <span data-ttu-id="0ce82-131">Ir ieteicams izvēlēties nosaukumu, kas paskaidro savienojuma nolūku.</span><span class="sxs-lookup"><span data-stu-id="0ce82-131">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="0ce82-132">Izvēlieties, kurš var izmantot šo savienojumu.</span><span class="sxs-lookup"><span data-stu-id="0ce82-132">Choose who can use this connection.</span></span> <span data-ttu-id="0ce82-133">Ja nesāksit nekādas darbības, noklusējums būs Administratori.</span><span class="sxs-lookup"><span data-stu-id="0ce82-133">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="0ce82-134">Papildinformāciju skatiet rakstā [Atļaut līdzstrādniekiem izmantot savienojumu eksportam](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="0ce82-134">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="0ce82-135">Atlasiet vai meklējiet abonementu, kurā vēlaties izmantot Customer Insights datus.</span><span class="sxs-lookup"><span data-stu-id="0ce82-135">Select or search for the subscription you want to use the Customer Insights data in.</span></span> <span data-ttu-id="0ce82-136">Līdzko ir atlasīts abonements, varat arī atlasīt **Darbvieta**, **Krātuves konts** un **Konteiners**.</span><span class="sxs-lookup"><span data-stu-id="0ce82-136">As soon as a subscription is selected, you can also select **Workspace**, **Storage account**, and **Container**.</span></span>

1. <span data-ttu-id="0ce82-137">Lai saglabātu savienojumu, atlasiet **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="0ce82-137">Select **Save** to save the connection.</span></span>

### <a name="configure-an-export"></a><span data-ttu-id="0ce82-138">Eksporta konfigurēšana</span><span class="sxs-lookup"><span data-stu-id="0ce82-138">Configure an export</span></span>

<span data-ttu-id="0ce82-139">Šo eksportu varat konfigurēt, ja jums ir piekļuve šā veida pieslēgumam.</span><span class="sxs-lookup"><span data-stu-id="0ce82-139">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="0ce82-140">Papildinformāciju skatiet rakstā [atļaujas, kas nepieciešamas eksporta konfigurēšanai](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="0ce82-140">For more information, see [permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="0ce82-141">Pārejiet uz **Dati** > **Eksportēšana**.</span><span class="sxs-lookup"><span data-stu-id="0ce82-141">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="0ce82-142">Lai izveidotu jaunu eksportu, atlasiet **Pievienot eksportu**.</span><span class="sxs-lookup"><span data-stu-id="0ce82-142">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="0ce82-143">Laukā **Savienošana eksportam** atlasiet savienojumu no sadaļas **Azure Synapse Analytics**.</span><span class="sxs-lookup"><span data-stu-id="0ce82-143">In the **Connection for export** field, choose a connection from the **Azure Synapse Analytics** section.</span></span> <span data-ttu-id="0ce82-144">Ja šis sadaļas nosaukums nav redzams, šāda veida [savienojumi](connections.md) jums nav pieejami.</span><span class="sxs-lookup"><span data-stu-id="0ce82-144">If you don't see this section name, there are no [connections](connections.md) of this type available to you.</span></span>

1. <span data-ttu-id="0ce82-145">Norādiet atpazīstamu eksportēšanas **Parādāmo nosaukumu** un **Datu bāzes nosaukumu**.</span><span class="sxs-lookup"><span data-stu-id="0ce82-145">Provide a recognizable **Display name** for your export and a **Database name**.</span></span>

1. <span data-ttu-id="0ce82-146">Atlasiet entītijas, kuras vēlaties eksportēt uz Azure Synapse Analytics.</span><span class="sxs-lookup"><span data-stu-id="0ce82-146">Select which entities you want to export to Azure Synapse Analytics.</span></span>

1. <span data-ttu-id="0ce82-147">Atlasiet vienumu **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="0ce82-147">Select **Save**.</span></span>

<span data-ttu-id="0ce82-148">Eksporta saglabāšana automātiski nepalaiž eksportu.</span><span class="sxs-lookup"><span data-stu-id="0ce82-148">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="0ce82-149">Eksports tiek palaists ar katru [plānoto atsvaidzināšanu](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="0ce82-149">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="0ce82-150">Varat arī [eksportēt datus pēc pieprasījuma](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="0ce82-150">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span>

### <a name="update-an-export"></a><span data-ttu-id="0ce82-151">Eksportēšanas atjaunināšana</span><span class="sxs-lookup"><span data-stu-id="0ce82-151">Update an export</span></span>

1. <span data-ttu-id="0ce82-152">Pārejiet uz **Dati** > **Eksportēšana**.</span><span class="sxs-lookup"><span data-stu-id="0ce82-152">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="0ce82-153">Atlasīt **Rediģēt** atjaunināmajam eksporta vienumam.</span><span class="sxs-lookup"><span data-stu-id="0ce82-153">Select **Edit** on the export you want to update.</span></span>

   - <span data-ttu-id="0ce82-154">**Pievienot** vai **Noņemt** entītijas no atlases.</span><span class="sxs-lookup"><span data-stu-id="0ce82-154">**Add** or **Remove** entities from the selection.</span></span> <span data-ttu-id="0ce82-155">Ja entītijas tiek noņemtas no atlases, tās netiek dzēstas no Synapse Analytics datu bāzes.</span><span class="sxs-lookup"><span data-stu-id="0ce82-155">If entities are removed from the selection, they aren't deleted from the Synapse Analytics database.</span></span> <span data-ttu-id="0ce82-156">Tomēr turpmākas datu atsvaidzināšanas gadījumā šajā datu bāzē noņemtās entītijas netiks atjauninātas.</span><span class="sxs-lookup"><span data-stu-id="0ce82-156">However, future data refreshes won't update the removed entities in that database.</span></span>

   - <span data-ttu-id="0ce82-157">**Mainot datu bāzes nosaukumu**, tiek izveidota jauna Synapse Analytics datu bāze.</span><span class="sxs-lookup"><span data-stu-id="0ce82-157">**Changing the Database Name** creates a new Synapse Analytics database.</span></span> <span data-ttu-id="0ce82-158">Datu bāze ar nosaukumu, kas tika konfigurētsa iepriekš, vairs nesaņems atjauninājumus tālākajos laidienos.</span><span class="sxs-lookup"><span data-stu-id="0ce82-158">The database with the name that was configured before won't receive any updates in future refreshes.</span></span>
