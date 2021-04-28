---
title: Customer Insights datu eksportēšana uz Azure Data Lake Storage Gen2
description: Uzziniet, kā konfigurēt savienojumu ar Azure Data Lake Storage Gen2.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: f431b707e1d65ffe47f8b3aa1c52abaa964e871a
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760060"
---
# <a name="set-up-the-connection-to-azure-data-lake-storage-gen2-preview"></a><span data-ttu-id="8e2f1-103">Iestatiet savienojumu ar Azure Data Lake Storage Gen2 (priekšskatījums)</span><span class="sxs-lookup"><span data-stu-id="8e2f1-103">Set up the connection to Azure Data Lake Storage Gen2 (preview)</span></span>

1. <span data-ttu-id="8e2f1-104">Dodieties uz **Administrators** > **Savienojumi**.</span><span class="sxs-lookup"><span data-stu-id="8e2f1-104">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="8e2f1-105">Atlasiet vienumu **Pievienot savienojumu** un atlasiet **Azure Data Lake Gen 2**, lai konfigurētu savienojumu.</span><span class="sxs-lookup"><span data-stu-id="8e2f1-105">Select **Add connection** and choose **Azure Data Lake Gen 2** to configure the connection.</span></span>

1. <span data-ttu-id="8e2f1-106">Laukā **Parādāmais nosaukums** piešķiriet savienojumam atpazīstamu nosaukumu.</span><span class="sxs-lookup"><span data-stu-id="8e2f1-106">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="8e2f1-107">Parādāmais nosaukums un nosaukuma veids raksturo šo savienojumu.</span><span class="sxs-lookup"><span data-stu-id="8e2f1-107">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="8e2f1-108">Ir ieteicams izvēlēties nosaukumu, kas paskaidro savienojuma nolūku.</span><span class="sxs-lookup"><span data-stu-id="8e2f1-108">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="8e2f1-109">Izvēlieties, kurš var izmantot šo savienojumu.</span><span class="sxs-lookup"><span data-stu-id="8e2f1-109">Choose who can use this connection.</span></span> <span data-ttu-id="8e2f1-110">Ja nesāksit nekādas darbības, noklusējums būs Administratori.</span><span class="sxs-lookup"><span data-stu-id="8e2f1-110">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="8e2f1-111">Papildinformāciju skatiet rakstā [Atļaut līdzstrādniekiem izmantot savienojumu eksportam](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="8e2f1-111">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="8e2f1-112">Ievadiet **Uzņēmuma nosaukumu**, **Uzņēmuma atslēgu** un **Konteineru** jūsu Azure Data Lake Storage Gen2.</span><span class="sxs-lookup"><span data-stu-id="8e2f1-112">Enter **Account name**, **Account key**, and **Container** for your Azure Data Lake Storage Gen2.</span></span>
    - <span data-ttu-id="8e2f1-113">Informāciju par to, kā izveidot krātuves kontu, ko izmantot ar Azure Data Lake Storage Gen2, skatiet [Krātuves konta izveide](/azure/storage/blobs/create-data-lake-storage-account).</span><span class="sxs-lookup"><span data-stu-id="8e2f1-113">To learn how to create a storage account to use with Azure Data Lake Storage Gen2, see [Create storage account](/azure/storage/blobs/create-data-lake-storage-account).</span></span> 
    - <span data-ttu-id="8e2f1-114">Papildinformāciju par Azure Data Lake Gen2 glabāšanas konta nosaukumu un konta atslēgu skatiet rakstā [Krātuves konta iestatījumu pārvaldība Azure portālā](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="8e2f1-114">To learn more about Azure Data Lake Gen2 storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

1. <span data-ttu-id="8e2f1-115">Lai pabeigtu savienošanu, atlasiet **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="8e2f1-115">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="8e2f1-116">Eksporta konfigurēšana</span><span class="sxs-lookup"><span data-stu-id="8e2f1-116">Configure an export</span></span>

<span data-ttu-id="8e2f1-117">Šo eksportu varat konfigurēt, ja jums ir piekļuve šā veida pieslēgumam.</span><span class="sxs-lookup"><span data-stu-id="8e2f1-117">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="8e2f1-118">Papildinformāciju skatiet rakstā [Atļaujas, kas nepieciešamas eksporta konfigurēšanai](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="8e2f1-118">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="8e2f1-119">Pārejiet uz **Dati** > **Eksportēšana**.</span><span class="sxs-lookup"><span data-stu-id="8e2f1-119">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="8e2f1-120">Lai izveidotu jaunu eksportu, atlasiet **Pievienot eksportu**.</span><span class="sxs-lookup"><span data-stu-id="8e2f1-120">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="8e2f1-121">Laukā **Savienošana eksportam** atlasiet savienojumu no sadaļas **Azure Data Lake**.</span><span class="sxs-lookup"><span data-stu-id="8e2f1-121">In the **Connection for export** field, choose a connection from the **Azure Data Lake** section.</span></span> <span data-ttu-id="8e2f1-122">Ja šis sadaļas nosaukums nav redzams, šāda veida savienojumi jums nav pieejami.</span><span class="sxs-lookup"><span data-stu-id="8e2f1-122">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="8e2f1-123">Atzīmējiet lodziņu blakus visām entītijām, ko vēlaties eksportēt šajā galamērķī.</span><span class="sxs-lookup"><span data-stu-id="8e2f1-123">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="8e2f1-124">Atlasiet vienumu **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="8e2f1-124">Select **Save**.</span></span>

<span data-ttu-id="8e2f1-125">Eksporta saglabāšana automātiski nepalaiž eksportu.</span><span class="sxs-lookup"><span data-stu-id="8e2f1-125">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="8e2f1-126">Eksports tiek palaists ar katru [plānoto atsvaidzināšanu](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="8e2f1-126">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="8e2f1-127">Varat arī [eksportēt datus pēc pieprasījuma](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="8e2f1-127">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

<span data-ttu-id="8e2f1-128">Eksportētie dati tiek glabāti jūsu konfigurētajā Azure Data Lake Gen 2 krātuves konteinerā.</span><span class="sxs-lookup"><span data-stu-id="8e2f1-128">Exported data is stored in the Azure Data Lake Gen 2 storage container you configured.</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
