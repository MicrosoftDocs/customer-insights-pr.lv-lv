---
title: Galamērķu eksportēšana
description: Eksportēt datus un pārvaldīt eksportēšanas galamērķus.
ms.date: 07/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 9032d99357db86e66588eda544211a5f8eb2f23b
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643872"
---
# <a name="export-destinations-preview"></a><span data-ttu-id="00a75-103">Galamērķu eksportēšana (priekšskatījums)</span><span class="sxs-lookup"><span data-stu-id="00a75-103">Export destinations (preview)</span></span>

<span data-ttu-id="00a75-104">Lapā **Eksportēšanas galamērķi** tiek parādītas visas jūsu iestatītās datu eksportēšanas vietas.</span><span class="sxs-lookup"><span data-stu-id="00a75-104">The **Export destinations** page shows you all locations you've set up to export data to.</span></span> <span data-ttu-id="00a75-105">Eksportēšanai var pievienot arī jaunus adresātus.</span><span class="sxs-lookup"><span data-stu-id="00a75-105">You can also add new destinations for export.</span></span> <span data-ttu-id="00a75-106">Turklāt tajā ir redzama pašlaik pieejamo opciju eksportēšana.</span><span class="sxs-lookup"><span data-stu-id="00a75-106">Additionally, it shows export currently available options.</span></span> <span data-ttu-id="00a75-107">Saņemiet īsu pārskatu, aprakstu un uzziniet, ko varat darīt ar katru paplašināmības opciju.</span><span class="sxs-lookup"><span data-stu-id="00a75-107">Get a quick overview, description, and find out what you can do with each extensibility option.</span></span> <span data-ttu-id="00a75-108">Eksportējiet vienotos profilus, mērvienības un segmentus uz atbalstītajām programmām, kas ir saistošas jūsu uzņēmumam.</span><span class="sxs-lookup"><span data-stu-id="00a75-108">Export unified profiles, measures, and segments to supported apps relevant for your business.</span></span>

<span data-ttu-id="00a75-109">Dodieties uz **Administrators** > **Eksportēšanas galamērķi**, lai atrastu šādas paplašināšanas opcijas:</span><span class="sxs-lookup"><span data-stu-id="00a75-109">Go to **Admin** > **Export destinations** to find the following extensibility options:</span></span>

- [<span data-ttu-id="00a75-110">Dynamics 365 klienta kartes pievienojumprogramma</span><span class="sxs-lookup"><span data-stu-id="00a75-110">Dynamics 365 Customer Card Add-in</span></span>](customer-card-add-in.md)
- [<span data-ttu-id="00a75-111">Facebook Reklāmu pārvaldnieka savienotājs</span><span class="sxs-lookup"><span data-stu-id="00a75-111">Facebook Ads Manager connector</span></span>](export-facebook.md)
- [<span data-ttu-id="00a75-112">Power Automate savienotājs</span><span class="sxs-lookup"><span data-stu-id="00a75-112">Power Automate connector</span></span>](export-power-automate.md)
- [<span data-ttu-id="00a75-113">Power Apps savienotājs</span><span class="sxs-lookup"><span data-stu-id="00a75-113">Power Apps connector</span></span>](export-power-apps.md)
- [<span data-ttu-id="00a75-114">Power BI savienotājs</span><span class="sxs-lookup"><span data-stu-id="00a75-114">Power BI connector</span></span>](export-power-bi.md)
- [<span data-ttu-id="00a75-115">DotDigital</span><span class="sxs-lookup"><span data-stu-id="00a75-115">DotDigital</span></span>](export-dotdigital.md)
- [<span data-ttu-id="00a75-116">Dynamics 365 Sales</span><span class="sxs-lookup"><span data-stu-id="00a75-116">Dynamics 365 Sales</span></span>](export-dynamics365-sales.md)
- [<span data-ttu-id="00a75-117">Dynamics 365 Marketing</span><span class="sxs-lookup"><span data-stu-id="00a75-117">Dynamics 365 Marketing</span></span>](export-dynamics365-marketing.md)
- [<span data-ttu-id="00a75-118">Azure Blob krātuve</span><span class="sxs-lookup"><span data-stu-id="00a75-118">Azure Blob Storage</span></span>](export-azure-blob-storage.md)
- [<span data-ttu-id="00a75-119">LiveRamp&reg; savienotājs</span><span class="sxs-lookup"><span data-stu-id="00a75-119">LiveRamp&reg; connector</span></span>](export-liveramp.md)
- [<span data-ttu-id="00a75-120">Bots pakalpojumam Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="00a75-120">Bot for Microsoft Teams</span></span>](export-teams-bot.md)
- [<span data-ttu-id="00a75-121">MailChimp</span><span class="sxs-lookup"><span data-stu-id="00a75-121">Mailchimp</span></span>](export-mailchimp.md)
- [<span data-ttu-id="00a75-122">Customer Insights API</span><span class="sxs-lookup"><span data-stu-id="00a75-122">Customer Insights API</span></span>](apis.md)

## <a name="add-a-new-export-destination"></a><span data-ttu-id="00a75-123">Jaunu eksportēšanas galamērķu pievienošana</span><span class="sxs-lookup"><span data-stu-id="00a75-123">Add a new export destination</span></span>

<span data-ttu-id="00a75-124">Lai pievienotu eksportēšanas galamērķus, jums ir [administratora atļaujas](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="00a75-124">To add export destinations, you have [administrator permissions](permissions.md).</span></span> <span data-ttu-id="00a75-125">Ja eksportējat uz Microsoft pakalpojumiem, mēs pieņemam, ka abi pakalpojumi atrodas vienā un tajā pašā organizācijā.</span><span class="sxs-lookup"><span data-stu-id="00a75-125">If you export to Microsoft services, we assume both services are in the same organization.</span></span>

1. <span data-ttu-id="00a75-126">Dodieties uz sadaļu **Administrators** > **Eksportēšanas galamērķi**.</span><span class="sxs-lookup"><span data-stu-id="00a75-126">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="00a75-127">Pārslēdzieties uz cilni **Mani eksportēšanas galamērķi**.</span><span class="sxs-lookup"><span data-stu-id="00a75-127">Switch to the **My export destinations** tab.</span></span>

1. <span data-ttu-id="00a75-128">Atlasiet **Pievienot galamērķi**, lai izveidotu jaunu eksportēšanas galamērķi.</span><span class="sxs-lookup"><span data-stu-id="00a75-128">Select **Add destination** to create a new export destination.</span></span>

1. <span data-ttu-id="00a75-129">Rūts **Pievienot galamērķi** nolaižamajā sarakstā atlasiet eksportēšanas galamērķa **Tipu**.</span><span class="sxs-lookup"><span data-stu-id="00a75-129">In the **Add destination** pane, select the **Type** of export destination in the drop-down.</span></span>

1. <span data-ttu-id="00a75-130">Norādiet nepieciešamo informāciju un atlasiet **Tālāk**, lai izveidotu eksportēšanas galamērķi.</span><span class="sxs-lookup"><span data-stu-id="00a75-130">Provide the required details and select **Next** to create the export destination.</span></span>

<span data-ttu-id="00a75-131">Cilnes elementā **Iestatīt** var atlasīt arī **Atklāt**.</span><span class="sxs-lookup"><span data-stu-id="00a75-131">You can also select **Set up** on a tile on the **Discover** tab.</span></span>

## <a name="view-export-destinations"></a><span data-ttu-id="00a75-132">Skatīt eksportēšanas galamērķus</span><span class="sxs-lookup"><span data-stu-id="00a75-132">View Export destinations</span></span>

<span data-ttu-id="00a75-133">Pēc eksportēšanas galamērķu izveides tie ir atrodami tabulā **Mani eksportēšanas galamērķi**. Šajā tabulā ir trīs kolonnas:</span><span class="sxs-lookup"><span data-stu-id="00a75-133">After creating export destinations, you'll find them in a table on the **My export destinations** tab. This table has three columns:</span></span>

- <span data-ttu-id="00a75-134">**Parādāmais nosaukums**: Nosaukums, ko ievadījāt, veidojot galamērķi.</span><span class="sxs-lookup"><span data-stu-id="00a75-134">**Display name**: The name you entered when creating the destination.</span></span>
- <span data-ttu-id="00a75-135">**Tips**: Eksportēšanas galamērķa tips, ko iestatījāt, izveidojot galamērķi.</span><span class="sxs-lookup"><span data-stu-id="00a75-135">**Type**: The export destination type you set when creating the destination.</span></span>
- <span data-ttu-id="00a75-136">**Izveidots**: Datums, kad izveidojāt galamērķi.</span><span class="sxs-lookup"><span data-stu-id="00a75-136">**Created**: The date you created the destination.</span></span>

## <a name="edit-an-export-destination"></a><span data-ttu-id="00a75-137">Eksportēšanas galamērķa rediģēšana</span><span class="sxs-lookup"><span data-stu-id="00a75-137">Edit an export destination</span></span>

1. <span data-ttu-id="00a75-138">Atlasiet eksportēšanas galamērķa vertikālo elipsi, ko vēlaties rediģēt.</span><span class="sxs-lookup"><span data-stu-id="00a75-138">Select the vertical ellipsis for the Export destination you want to edit.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="00a75-139">![Vertikālā elipse](media/export-destinations-page-ellipsis.png "Vertikālā elipse")</span><span class="sxs-lookup"><span data-stu-id="00a75-139">![Vertical ellipsis](media/export-destinations-page-ellipsis.png "Vertical ellipsis")</span></span>

1. <span data-ttu-id="00a75-140">Nolaižamajā izvēlnē atlasiet **Rediģēt**.</span><span class="sxs-lookup"><span data-stu-id="00a75-140">Select **Edit** from the dropdown menu.</span></span>

1. <span data-ttu-id="00a75-141">Mainiet vērtības, kurām nepieciešama atjaunināšana, un atlasiet **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="00a75-141">Change the values that require update and select **Save**.</span></span>

## <a name="export-data-on-demand"></a><span data-ttu-id="00a75-142">Datu eksportēšana pēc pieprasījuma</span><span class="sxs-lookup"><span data-stu-id="00a75-142">Export data on demand</span></span>

<span data-ttu-id="00a75-143">Pēc eksportēšanas galamērķa savienotāja konfigurēšanas eksportēšanas darbības notiks ar katru [plānoto atsvaidzināšanu](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="00a75-143">After configuring a connector for an export destination, exports will run with every [scheduled refresh](system.md#schedule-tab).</span></span>

<span data-ttu-id="00a75-144">Lai eksportētu datus, negaidot plānoto atsvaidzināšanu, cilnē **Mani eksportēšanas galamērķi** atlasiet **Administrators** > **Eksportēšanas galamērķi**.</span><span class="sxs-lookup"><span data-stu-id="00a75-144">To export data without waiting for a scheduled refresh, go the **My export destinations** tab on **Admin** > **Export destinations**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="00a75-145">![Vertikālā elipse](media/export-destinations-page-ellipsis.png "Vertikālā elipse")</span><span class="sxs-lookup"><span data-stu-id="00a75-145">![Vertical ellipsis](media/export-destinations-page-ellipsis.png "Vertical ellipsis")</span></span>

- <span data-ttu-id="00a75-146">Atlasiet opciju **Eksportēt** virs saraksta, lai vienlaikus izpildītu eksportēšanu uz visiem eksportēšanas galamērķiem.</span><span class="sxs-lookup"><span data-stu-id="00a75-146">Select **Export** above the list to run the export to all export destinations simultaneously.</span></span>
- <span data-ttu-id="00a75-147">Pēc saraksta elementa atlasiet daudzpunkti (...) un pēc tam izvēlieties opciju **Eksportēt**, lai izpildītu eksportēšanu atsevišķam eksportēšanas galamērķim.</span><span class="sxs-lookup"><span data-stu-id="00a75-147">Select the ellipsis (...) after a list item and then choose the **Export** option to run the export for a single export destination.</span></span>

## <a name="remove-an-export-destination"></a><span data-ttu-id="00a75-148">Eksportēšanas galamērķa noņemšana</span><span class="sxs-lookup"><span data-stu-id="00a75-148">Remove an Export destination</span></span>

<span data-ttu-id="00a75-149">Lai noņemtu eksportēšanas galamērķi, sāciet no galvenās **eksportēšanas galamērķu** lapas.</span><span class="sxs-lookup"><span data-stu-id="00a75-149">To remove an Export destination, start from the main **Export destinations** page.</span></span>

1. <span data-ttu-id="00a75-150">Atlasiet eksportēšanas galamērķa vertikālo elipsi, ko vēlaties noņemt.</span><span class="sxs-lookup"><span data-stu-id="00a75-150">Select the vertical ellipsis for the Export destination you want to remove.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="00a75-151">![Vertikālā elipse](media/export-destinations-page-ellipsis.png "Vertikālā elipse")</span><span class="sxs-lookup"><span data-stu-id="00a75-151">![Vertical ellipsis](media/export-destinations-page-ellipsis.png "Vertical ellipsis")</span></span>

2. <span data-ttu-id="00a75-152">Atlasiet **Noņemt** nolaižamajā izvēlnē.</span><span class="sxs-lookup"><span data-stu-id="00a75-152">Select **Remove** from the dropdown menu.</span></span>

3. <span data-ttu-id="00a75-153">Apstipriniet noņemšanu, apstiprinājuma ekrānā atlasot pogu **Noņemt**.</span><span class="sxs-lookup"><span data-stu-id="00a75-153">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>
