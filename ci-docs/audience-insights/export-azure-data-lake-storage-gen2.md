---
title: Customer Insights datu eksportēšana uz Azure Data Lake Storage Gen2
description: Uzziniet, kā konfigurēt savienojumu ar Azure Data Lake Storage Gen2.
ms.date: 02/04/2021
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b00c3d6178150cbc93fe800779f094809d4dc67b
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477188"
---
# <a name="connector-for-azure-data-lake-storage-gen2-preview"></a><span data-ttu-id="80b1f-103">Savienotājs ar Azure Data Lake Storage Gen2 (priekšskatījums)</span><span class="sxs-lookup"><span data-stu-id="80b1f-103">Connector for Azure Data Lake Storage Gen2 (preview)</span></span>

<span data-ttu-id="80b1f-104">Glabājiet Customer Insights datus pakalpojumā Azure Data Lake Storage Gen2 vai izmantojiet pakalpojumu, lai pārsūtītu datus uz citām programmām.</span><span class="sxs-lookup"><span data-stu-id="80b1f-104">Store your Customer Insights data in Azure Data Lake Storage Gen2 or use it to transfer your data to other applications.</span></span>

## <a name="configure-the-connector-for-azure-data-lake-storage-gen2"></a><span data-ttu-id="80b1f-105">Savienotāja konfigurēšana Azure Data Lake Storage Gen2</span><span class="sxs-lookup"><span data-stu-id="80b1f-105">Configure the connector for Azure Data Lake Storage Gen2</span></span>

1. <span data-ttu-id="80b1f-106">Sadaļā Auditorijas ieskati ejiet uz **Administrators** > **Eksportēšanas galamērķi**.</span><span class="sxs-lookup"><span data-stu-id="80b1f-106">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="80b1f-107">Sadaļā **Azure Data Lake Storage Gen2** atlasiet vienumu **Iestatīt**.</span><span class="sxs-lookup"><span data-stu-id="80b1f-107">Under **Azure Data Lake Storage Gen2**, select **Set up**.</span></span>

1. <span data-ttu-id="80b1f-108">Laukā **Parādāmais nosaukums** piešķiriet galamērķim atpazīstamu nosaukumu.</span><span class="sxs-lookup"><span data-stu-id="80b1f-108">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="80b1f-109">Ievadiet **Uzņēmuma nosaukumu**, **Uzņēmuma atslēgu** un **Konteineru** jūsu Azure Data Lake Storage Gen2.</span><span class="sxs-lookup"><span data-stu-id="80b1f-109">Enter **Account name**, **Account key**, and **Container** for your Azure Data Lake Storage Gen2.</span></span>
    - <span data-ttu-id="80b1f-110">Informāciju par to, kā izveidot krātuves kontu, ko izmantot ar Azure Data Lake Storage Gen2, skatiet [Krātuves konta izveide](https://docs.microsoft.com/azure/storage/blobs/create-data-lake-storage-account).</span><span class="sxs-lookup"><span data-stu-id="80b1f-110">To learn how to create a storage account to use with Azure Data Lake Storage Gen2, see [Create storage account](https://docs.microsoft.com/azure/storage/blobs/create-data-lake-storage-account).</span></span> 
    - <span data-ttu-id="80b1f-111">Papildinformāciju, kā atrast Azure Data Lake Gen2 krātuves konta nosaukumu un konta atslēgu, skatiet sadaļā [Krātuves konta iestatījumu pārvaldība Azure portālā](https://docs.microsoft.com/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="80b1f-111">To learn more about how to find the Azure Data Lake Gen2 storage account name and account key, see [Manage storage account settings in the Azure portal](https://docs.microsoft.com/azure/storage/common/storage-account-manage).</span></span>

1. <span data-ttu-id="80b1f-112">Atlasiet **Tālāk**.</span><span class="sxs-lookup"><span data-stu-id="80b1f-112">Select **Next**.</span></span>

1. <span data-ttu-id="80b1f-113">Atzīmējiet lodziņu blakus visām entītijām, ko vēlaties eksportēt šajā galamērķī.</span><span class="sxs-lookup"><span data-stu-id="80b1f-113">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="80b1f-114">Atlasiet vienumu **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="80b1f-114">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="80b1f-115">Datu eksportēšana</span><span class="sxs-lookup"><span data-stu-id="80b1f-115">Export the data</span></span>

<span data-ttu-id="80b1f-116">Datus var [eksportēt pēc pieprasījuma](export-destinations.md#export-data-on-demand).</span><span class="sxs-lookup"><span data-stu-id="80b1f-116">You can [export data on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="80b1f-117">Eksportēšana arī tiks palaista ar katru [plānoto atsvaidzināšanu](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="80b1f-117">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
