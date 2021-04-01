---
title: Customer Insights datu eksportēšana uz Azure Data Lake Storage Gen2
description: Uzziniet, kā konfigurēt savienojumu ar Azure Data Lake Storage Gen2.
ms.date: 02/04/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 7c0eef575f745efa6312d7141a6dd96607f9797e
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596647"
---
# <a name="connector-for-azure-data-lake-storage-gen2-preview"></a><span data-ttu-id="c1a9f-103">Savienotājs ar Azure Data Lake Storage Gen2 (priekšskatījums)</span><span class="sxs-lookup"><span data-stu-id="c1a9f-103">Connector for Azure Data Lake Storage Gen2 (preview)</span></span>

<span data-ttu-id="c1a9f-104">Glabājiet Customer Insights datus pakalpojumā Azure Data Lake Storage Gen2 vai izmantojiet pakalpojumu, lai pārsūtītu datus uz citām programmām.</span><span class="sxs-lookup"><span data-stu-id="c1a9f-104">Store your Customer Insights data in Azure Data Lake Storage Gen2 or use it to transfer your data to other applications.</span></span>

## <a name="configure-the-connector-for-azure-data-lake-storage-gen2"></a><span data-ttu-id="c1a9f-105">Savienotāja konfigurēšana Azure Data Lake Storage Gen2</span><span class="sxs-lookup"><span data-stu-id="c1a9f-105">Configure the connector for Azure Data Lake Storage Gen2</span></span>

1. <span data-ttu-id="c1a9f-106">Sadaļā Auditorijas ieskati ejiet uz **Administrators** > **Eksportēšanas galamērķi**.</span><span class="sxs-lookup"><span data-stu-id="c1a9f-106">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="c1a9f-107">Sadaļā **Azure Data Lake Storage Gen2** atlasiet vienumu **Iestatīt**.</span><span class="sxs-lookup"><span data-stu-id="c1a9f-107">Under **Azure Data Lake Storage Gen2**, select **Set up**.</span></span>

1. <span data-ttu-id="c1a9f-108">Laukā **Parādāmais nosaukums** piešķiriet galamērķim atpazīstamu nosaukumu.</span><span class="sxs-lookup"><span data-stu-id="c1a9f-108">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="c1a9f-109">Ievadiet **Uzņēmuma nosaukumu**, **Uzņēmuma atslēgu** un **Konteineru** jūsu Azure Data Lake Storage Gen2.</span><span class="sxs-lookup"><span data-stu-id="c1a9f-109">Enter **Account name**, **Account key**, and **Container** for your Azure Data Lake Storage Gen2.</span></span>
    - <span data-ttu-id="c1a9f-110">Informāciju par to, kā izveidot krātuves kontu, ko izmantot ar Azure Data Lake Storage Gen2, skatiet [Krātuves konta izveide](/azure/storage/blobs/create-data-lake-storage-account).</span><span class="sxs-lookup"><span data-stu-id="c1a9f-110">To learn how to create a storage account to use with Azure Data Lake Storage Gen2, see [Create storage account](/azure/storage/blobs/create-data-lake-storage-account).</span></span> 
    - <span data-ttu-id="c1a9f-111">Papildinformāciju, kā atrast Azure Data Lake Gen2 krātuves konta nosaukumu un konta atslēgu, skatiet sadaļā [Krātuves konta iestatījumu pārvaldība Azure portālā](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="c1a9f-111">To learn more about how to find the Azure Data Lake Gen2 storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

1. <span data-ttu-id="c1a9f-112">Atlasiet **Tālāk**.</span><span class="sxs-lookup"><span data-stu-id="c1a9f-112">Select **Next**.</span></span>

1. <span data-ttu-id="c1a9f-113">Atzīmējiet lodziņu blakus visām entītijām, ko vēlaties eksportēt šajā galamērķī.</span><span class="sxs-lookup"><span data-stu-id="c1a9f-113">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="c1a9f-114">Atlasiet vienumu **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="c1a9f-114">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="c1a9f-115">Datu eksportēšana</span><span class="sxs-lookup"><span data-stu-id="c1a9f-115">Export the data</span></span>

<span data-ttu-id="c1a9f-116">Datus var [eksportēt pēc pieprasījuma](export-destinations.md#export-data-on-demand).</span><span class="sxs-lookup"><span data-stu-id="c1a9f-116">You can [export data on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="c1a9f-117">Eksportēšana arī tiks palaista ar katru [plānoto atsvaidzināšanu](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="c1a9f-117">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>