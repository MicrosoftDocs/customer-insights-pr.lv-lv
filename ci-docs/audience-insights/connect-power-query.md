---
title: Datu paņemšana, izmantojot Power Query savienotāju
description: Savienotāji datu avotiem, pamatojoties uz Power Query.
ms.date: 09/29/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 8a170cc5b64b4b383501021232c83948e838a0e2
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406344"
---
# <a name="connect-to-a-power-query-data-source"></a><span data-ttu-id="94d92-103">Savienojuma izveide ar Power Query datu avotu</span><span class="sxs-lookup"><span data-stu-id="94d92-103">Connect to a Power Query data source</span></span>

<span data-ttu-id="94d92-104">Power Query piedāvā plašu savienotāju kopu datu uzņemšanai.</span><span class="sxs-lookup"><span data-stu-id="94d92-104">Power Query offers a broad set of connectors to ingest data.</span></span> <span data-ttu-id="94d92-105">Vairumu no šiem savienotājiem atbalsta Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="94d92-105">Most of these connectors are supported by Dynamics 365 Customer Insights.</span></span> <span data-ttu-id="94d92-106">Datu avotu pievienošanā, pamatojoties uz Power Query savienotājiem, kopumā tiek izpildītas nākamajā sadaļā izklāstītās darbības.</span><span class="sxs-lookup"><span data-stu-id="94d92-106">Adding data sources based on Power Query connectors generally follows the steps outlined in the next section.</span></span> <span data-ttu-id="94d92-107">Taču atkarībā no savienotāja, kuru izmantojat, var būt nepieciešama atšķirīga informācija.</span><span class="sxs-lookup"><span data-stu-id="94d92-107">However, depending on the connector you use, different information is required.</span></span> <span data-ttu-id="94d92-108">Lai iegūtu papildinformāciju, skatiet dokumentus par atsevišķiem savienotājiem [Power Query savienotāja atsaucē](https://docs.microsoft.com/power-query/connectors/).</span><span class="sxs-lookup"><span data-stu-id="94d92-108">For more information, see the documentation about individual connectors in the [Power Query connector reference](https://docs.microsoft.com/power-query/connectors/).</span></span>

## <a name="create-a-new-data-source"></a><span data-ttu-id="94d92-109">Jauna datu avota izveide</span><span class="sxs-lookup"><span data-stu-id="94d92-109">Create a new data source</span></span>

1. <span data-ttu-id="94d92-110">Sadaļā Auditorijas ieskati skatiet **Dati** > **Datu avoti**.</span><span class="sxs-lookup"><span data-stu-id="94d92-110">In audience insights, go to **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="94d92-111">Atlasiet **Pievienot datu avotu**.</span><span class="sxs-lookup"><span data-stu-id="94d92-111">Select **Add data source**.</span></span>

1. <span data-ttu-id="94d92-112">Atlasiet **Datu importēšanas** metodi, pēc tam atlasiet **Tālāk**.</span><span class="sxs-lookup"><span data-stu-id="94d92-112">Choose the **Import data** method and select **Next**.</span></span>

1. <span data-ttu-id="94d92-113">Sniedziet datu avota **Nosaukmu** un atlasiet **Tālāk**, lai izveidotu datu avotu.</span><span class="sxs-lookup"><span data-stu-id="94d92-113">Provide a **Name** for the data source, and select **Next** to create the data source.</span></span>

1. <span data-ttu-id="94d92-114">Izvēlieties vienu no [pieejamiem savienotājiem](#available-power-query-data-sources).</span><span class="sxs-lookup"><span data-stu-id="94d92-114">Choose one of the [available connectors](#available-power-query-data-sources).</span></span> <span data-ttu-id="94d92-115">Šajā piemērā esam atlasījuši savienotāju **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="94d92-115">For this example, we select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="94d92-116">Ievadiet nepieciešamo informāciju sadaļā **Savienojuma iestatījumi** attiecībā uz atlasīto savienotāju un atlasiet **Tālāk**, lai skatītu datu priekšskatījumu.</span><span class="sxs-lookup"><span data-stu-id="94d92-116">Enter the required details in the **Connection settings** for the selected connector and select **Next** to see a preview of the data.</span></span>

1. <span data-ttu-id="94d92-117">Atlasiet **Pārveidot datus**.</span><span class="sxs-lookup"><span data-stu-id="94d92-117">Select **Transform data**.</span></span> <span data-ttu-id="94d92-118">Šajā darbībā jūs pievienosiet entītijas savam datu avotam.</span><span class="sxs-lookup"><span data-stu-id="94d92-118">In this step, you'll add entities to your data source.</span></span> <span data-ttu-id="94d92-119">Entitījas ir datu kopas.</span><span class="sxs-lookup"><span data-stu-id="94d92-119">Entities are datasets.</span></span> <span data-ttu-id="94d92-120">Ja jums ir datu bāze, kurā ir ietvertas vairākas datu kopas, katra datu kopa ir entītija.</span><span class="sxs-lookup"><span data-stu-id="94d92-120">If you have a database that includes multiple datasets, each dataset is its own entity.</span></span>

1. <span data-ttu-id="94d92-121">Dialoglodziņā **Power Query — rediģēt vaicājumus** ļauj pārskatīt un precizēt datus.</span><span class="sxs-lookup"><span data-stu-id="94d92-121">The **Power Query - Edit queries** dialog lets you review and refine the data.</span></span> <span data-ttu-id="94d92-122">Entītijas, kuras sistēma identificēja jūsu atlasītajā datu avotā, tiek rādītas kreisajā rūtī.</span><span class="sxs-lookup"><span data-stu-id="94d92-122">The entities that the systems identified in your selected data source appear in the left pane.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="94d92-123">![Vaicājumu rediģēšanas dialoglodziņš](media/data-manager-configure-edit-queries.png "Vaicājumu rediģēšanas dialoglodziņš")</span><span class="sxs-lookup"><span data-stu-id="94d92-123">![Edit queries dialog](media/data-manager-configure-edit-queries.png "Edit queries dialog")</span></span>

1. <span data-ttu-id="94d92-124">Varat arī transformēt savus datus.</span><span class="sxs-lookup"><span data-stu-id="94d92-124">You can also transform your data.</span></span> <span data-ttu-id="94d92-125">Atlasiet entītiju, ko vēlaties rediģēt vai transformēt.</span><span class="sxs-lookup"><span data-stu-id="94d92-125">Select an entity to edit or transform.</span></span> <span data-ttu-id="94d92-126">Izmantojiet Power Query loga opcijas, lai lietotu izmaiņas.</span><span class="sxs-lookup"><span data-stu-id="94d92-126">Use the options in the Power Query window to apply transformations.</span></span> <span data-ttu-id="94d92-127">Visas izmaiņas ir uzskaitītas sadaļā **Lietotās darbības**.</span><span class="sxs-lookup"><span data-stu-id="94d92-127">Each transformation gets listed under **Applied steps**.</span></span> <span data-ttu-id="94d92-128">Power Query nodrošina daudzas iepriekš izveidotas izmaiņu opcijas.</span><span class="sxs-lookup"><span data-stu-id="94d92-128">Power Query provides numerous pre-built transformation options.</span></span> <span data-ttu-id="94d92-129">Papildinformāciju skatiet sadaļā [Power Query izmaiņas](https://docs.microsoft.com/power-query/power-query-what-is-power-query#transformations).</span><span class="sxs-lookup"><span data-stu-id="94d92-129">For more information, see [Power Query Transformations](https://docs.microsoft.com/power-query/power-query-what-is-power-query#transformations).</span></span>

1. <span data-ttu-id="94d92-130">Saviem datu avotiem varat pievienotu papildu entītijas, dialoglodziņā **Vaicājumu rediģēšana** atlasot **Iegūt datus**.</span><span class="sxs-lookup"><span data-stu-id="94d92-130">You can add additional entities to your data source by selecting **Get data** in the **Edit queries** dialog.</span></span>

   <span data-ttu-id="94d92-131">Ir ieteicams veikt tālāk norādītās transformācijas:</span><span class="sxs-lookup"><span data-stu-id="94d92-131">These transformations are highly recommended:</span></span>

   - <span data-ttu-id="94d92-132">Ja uzņemat datus no CSV faila, pirmajā rindā bieži vien ir galvenes.</span><span class="sxs-lookup"><span data-stu-id="94d92-132">If you're ingesting data from a CSV file, the first row often contains headers.</span></span> <span data-ttu-id="94d92-133">Dodieties uz **Mainīt tabulu** un atlasiet **Izmantot galvenes kā pirmo rindu**.</span><span class="sxs-lookup"><span data-stu-id="94d92-133">Go to **Transform table** and select **Use headers as first row**.</span></span>
   - <span data-ttu-id="94d92-134">Pārliecinieties, ka datu veids ir iestatīts atbilstoši.</span><span class="sxs-lookup"><span data-stu-id="94d92-134">Ensure the data type is set appropriately.</span></span>

1. <span data-ttu-id="94d92-135">Power Query loga apakšējā labajā stūrī atlasiet **Saglabāt**, lai saglabātu izmaiņas.</span><span class="sxs-lookup"><span data-stu-id="94d92-135">Select **Save** at the bottom of the Power Query window to save the transformations.</span></span> <span data-ttu-id="94d92-136">Pēc saglabāšanas jūsu datu avots atradīsies sadaļā **Dati** > **Datu avoti**.</span><span class="sxs-lookup"><span data-stu-id="94d92-136">After saving, you'll find your data source on **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="94d92-137">Lapā **Datu avoti** redzēsit, ka jaunā datu avota statuss ir **Atsvaidzina**.</span><span class="sxs-lookup"><span data-stu-id="94d92-137">On the **Data sources** page, you'll notice the new data source is in **Refreshing** status.</span></span>

## <a name="available-power-query-data-sources"></a><span data-ttu-id="94d92-138">Pieejamie Power Query datu avoti</span><span class="sxs-lookup"><span data-stu-id="94d92-138">Available Power Query data sources</span></span>

<span data-ttu-id="94d92-139">Informāciju par jaunākajiem savienotājiem, kurus varat atlasīt datu importēšanai uz Customer Insights skatiet [Power Query savienotāja atsaucē](https://docs.microsoft.com/power-query/connectors/).</span><span class="sxs-lookup"><span data-stu-id="94d92-139">See the [Power Query connector reference](https://docs.microsoft.com/power-query/connectors/) for an up-to-date list of connectors that you can select to import data to Customer Insights.</span></span> 

<span data-ttu-id="94d92-140">Savienotāji ar atzīmi kolonnā **Customer Insights (Dataflows)** ir pieejami, lai izveidotu jaunus datu avotus, pamatojoties uz Power Query.</span><span class="sxs-lookup"><span data-stu-id="94d92-140">Connectors with a checkmark in the **Customer Insights (Dataflows)** column are available to create new data sources based on Power Query.</span></span> <span data-ttu-id="94d92-141">Pārskatiet konkrētā savienotāja dokumentāciju, lai uzzinātu vairāk par tā priekšnosacījumiem, ierobežojumiem un citu informāciju.</span><span class="sxs-lookup"><span data-stu-id="94d92-141">Review the documentation of a specific connector to learn more about its prerequisites, limitations, and other details.</span></span>

## <a name="edit-power-query-data-sources"></a><span data-ttu-id="94d92-142">Power Query datu avotu rediģēšana</span><span class="sxs-lookup"><span data-stu-id="94d92-142">Edit Power Query data sources</span></span>

> [!NOTE]
> <span data-ttu-id="94d92-143">Iespējams, nevarēs veikt izmaiņas datu avotos, kuri pašlaik tiek izmantoti kādā no programmas procesiem (piemēram, *segmentēšana*, *atbilstības noteikšana* vai *sapludināšana*).</span><span class="sxs-lookup"><span data-stu-id="94d92-143">It might not be possible to make changes to data sources that are currently being used in one of the app's processes (*segmentation*, *match*, or *merge*, for example).</span></span> 
>
> <span data-ttu-id="94d92-144">Izmantojot lapu **Iestatījumi**, varat izsekot katra aktīvā procesa norisei.</span><span class="sxs-lookup"><span data-stu-id="94d92-144">Using the **Settings** page, you can track the progress of each of the active processes.</span></span> <span data-ttu-id="94d92-145">Kad process ir pabeigts, varat atgriezties lapā **Datu avoti** un veikt vajadzīgās izmaiņas.</span><span class="sxs-lookup"><span data-stu-id="94d92-145">When a process completes, you can return to the **Data Sources** page and make your changes.</span></span>

1. <span data-ttu-id="94d92-146">Sadaļā Auditorijas ieskati skatiet **Dati** > **Datu avoti**.</span><span class="sxs-lookup"><span data-stu-id="94d92-146">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="94d92-147">Atlasiet vertikālo daudzpunkti blakus maināmajam datu avotam un nolaižamajā izvēlnē atlasiet **Rediģēt**.</span><span class="sxs-lookup"><span data-stu-id="94d92-147">Select the vertical ellipsis next to the data source you want to change and select **Edit** from the drop-down menu.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="94d92-148">![Rediģēšanas opcija](media/edit-option-data-sources.png "Rediģēšanas opcija")</span><span class="sxs-lookup"><span data-stu-id="94d92-148">![Edit option](media/edit-option-data-sources.png "Edit option")</span></span>

3. <span data-ttu-id="94d92-149">Piemērojiet veiktās izmaiņas un transformācijas dialoglodziņā **Power Query — izmaiņu rediģēšana**, kā aprakstīts sadaļā [Jauna datu avota izveide](#create-a-new-data-source).</span><span class="sxs-lookup"><span data-stu-id="94d92-149">Apply your changes and transformations in the **Power Query - Edit queries** dialog as described in the [Create a new data source](#create-a-new-data-source) section.</span></span>

4. <span data-ttu-id="94d92-150">Lai saglabātu izmaiņas, pēc rediģēšanas pabeigšanas Power Query atlasiet **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="94d92-150">Select **Save** in Power Query after completing your edits to save your changes.</span></span>
