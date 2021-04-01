---
title: Datu paņemšana, izmantojot Power Query savienotāju
description: Savienotāji datu avotiem, pamatojoties uz Power Query.
ms.date: 09/29/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.openlocfilehash: b9a1b30e37c3792aa7bdfcfc177da9e8a32c324d
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596922"
---
# <a name="connect-to-a-power-query-data-source"></a><span data-ttu-id="029f5-103">Savienojuma izveide ar Power Query datu avotu</span><span class="sxs-lookup"><span data-stu-id="029f5-103">Connect to a Power Query data source</span></span>

<span data-ttu-id="029f5-104">Power Query piedāvā plašu savienotāju kopu datu uzņemšanai.</span><span class="sxs-lookup"><span data-stu-id="029f5-104">Power Query offers a broad set of connectors to ingest data.</span></span> <span data-ttu-id="029f5-105">Vairumu no šiem savienotājiem atbalsta Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="029f5-105">Most of these connectors are supported by Dynamics 365 Customer Insights.</span></span> <span data-ttu-id="029f5-106">Datu avotu pievienošanā, pamatojoties uz Power Query savienotājiem, kopumā tiek izpildītas nākamajā sadaļā izklāstītās darbības.</span><span class="sxs-lookup"><span data-stu-id="029f5-106">Adding data sources based on Power Query connectors generally follows the steps outlined in the next section.</span></span> <span data-ttu-id="029f5-107">Taču atkarībā no savienotāja, kuru izmantojat, var būt nepieciešama atšķirīga informācija.</span><span class="sxs-lookup"><span data-stu-id="029f5-107">However, depending on the connector you use, different information is required.</span></span> <span data-ttu-id="029f5-108">Lai iegūtu papildinformāciju, skatiet dokumentus par atsevišķiem savienotājiem [Power Query savienotāja atsaucē](/power-query/connectors/).</span><span class="sxs-lookup"><span data-stu-id="029f5-108">For more information, see the documentation about individual connectors in the [Power Query connector reference](/power-query/connectors/).</span></span>

## <a name="create-a-new-data-source"></a><span data-ttu-id="029f5-109">Jauna datu avota izveide</span><span class="sxs-lookup"><span data-stu-id="029f5-109">Create a new data source</span></span>

1. <span data-ttu-id="029f5-110">Sadaļā Auditorijas ieskati skatiet **Dati** > **Datu avoti**.</span><span class="sxs-lookup"><span data-stu-id="029f5-110">In audience insights, go to **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="029f5-111">Atlasiet **Pievienot datu avotu**.</span><span class="sxs-lookup"><span data-stu-id="029f5-111">Select **Add data source**.</span></span>

1. <span data-ttu-id="029f5-112">Atlasiet **Datu importēšanas** metodi, pēc tam atlasiet **Tālāk**.</span><span class="sxs-lookup"><span data-stu-id="029f5-112">Choose the **Import data** method and select **Next**.</span></span>

1. <span data-ttu-id="029f5-113">Sniedziet datu avota **Nosaukmu** un atlasiet **Tālāk**, lai izveidotu datu avotu.</span><span class="sxs-lookup"><span data-stu-id="029f5-113">Provide a **Name** for the data source, and select **Next** to create the data source.</span></span> <span data-ttu-id="029f5-114">Nosaukuma vadlīnijas:</span><span class="sxs-lookup"><span data-stu-id="029f5-114">Name guidelines:</span></span> 
   - <span data-ttu-id="029f5-115">Sāciet ar burtu.</span><span class="sxs-lookup"><span data-stu-id="029f5-115">Start with a letter.</span></span>
   - <span data-ttu-id="029f5-116">Izmantojiet tikai burtus un ciparus.</span><span class="sxs-lookup"><span data-stu-id="029f5-116">Use letters and numbers only.</span></span> <span data-ttu-id="029f5-117">Speciālās rakstzīmes un atstarpes nav atļautas.</span><span class="sxs-lookup"><span data-stu-id="029f5-117">Special characters and spaces are not allowed.</span></span>
   - <span data-ttu-id="029f5-118">Izmantojiet no 3 līdz 64 rakstzīmēm.</span><span class="sxs-lookup"><span data-stu-id="029f5-118">Use between 3 and 64 characters.</span></span>

1. <span data-ttu-id="029f5-119">Izvēlieties vienu no [pieejamiem savienotājiem](#available-power-query-data-sources).</span><span class="sxs-lookup"><span data-stu-id="029f5-119">Choose one of the [available connectors](#available-power-query-data-sources).</span></span> <span data-ttu-id="029f5-120">Šajā piemērā esam atlasījuši savienotāju **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="029f5-120">For this example, we select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="029f5-121">Ievadiet nepieciešamo informāciju sadaļā **Savienojuma iestatījumi** attiecībā uz atlasīto savienotāju un atlasiet **Tālāk**, lai skatītu datu priekšskatījumu.</span><span class="sxs-lookup"><span data-stu-id="029f5-121">Enter the required details in the **Connection settings** for the selected connector and select **Next** to see a preview of the data.</span></span>

1. <span data-ttu-id="029f5-122">Atlasiet **Pārveidot datus**.</span><span class="sxs-lookup"><span data-stu-id="029f5-122">Select **Transform data**.</span></span> <span data-ttu-id="029f5-123">Šajā darbībā jūs pievienosiet entītijas savam datu avotam.</span><span class="sxs-lookup"><span data-stu-id="029f5-123">In this step, you'll add entities to your data source.</span></span> <span data-ttu-id="029f5-124">Entitījas ir datu kopas.</span><span class="sxs-lookup"><span data-stu-id="029f5-124">Entities are datasets.</span></span> <span data-ttu-id="029f5-125">Ja jums ir datu bāze, kurā ir ietvertas vairākas datu kopas, katra datu kopa ir entītija.</span><span class="sxs-lookup"><span data-stu-id="029f5-125">If you have a database that includes multiple datasets, each dataset is its own entity.</span></span>

1. <span data-ttu-id="029f5-126">Dialoglodziņā **Power Query — rediģēt vaicājumus** ļauj pārskatīt un precizēt datus.</span><span class="sxs-lookup"><span data-stu-id="029f5-126">The **Power Query - Edit queries** dialog lets you review and refine the data.</span></span> <span data-ttu-id="029f5-127">Entītijas, kuras sistēma identificēja jūsu atlasītajā datu avotā, tiek rādītas kreisajā rūtī.</span><span class="sxs-lookup"><span data-stu-id="029f5-127">The entities that the systems identified in your selected data source appear in the left pane.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="029f5-128">![Vaicājumu rediģēšanas dialoglodziņš](media/data-manager-configure-edit-queries.png "Vaicājumu rediģēšanas dialoglodziņš")</span><span class="sxs-lookup"><span data-stu-id="029f5-128">![Edit queries dialog](media/data-manager-configure-edit-queries.png "Edit queries dialog")</span></span>

1. <span data-ttu-id="029f5-129">Varat arī transformēt savus datus.</span><span class="sxs-lookup"><span data-stu-id="029f5-129">You can also transform your data.</span></span> <span data-ttu-id="029f5-130">Atlasiet entītiju, ko vēlaties rediģēt vai transformēt.</span><span class="sxs-lookup"><span data-stu-id="029f5-130">Select an entity to edit or transform.</span></span> <span data-ttu-id="029f5-131">Izmantojiet Power Query loga opcijas, lai lietotu izmaiņas.</span><span class="sxs-lookup"><span data-stu-id="029f5-131">Use the options in the Power Query window to apply transformations.</span></span> <span data-ttu-id="029f5-132">Visas izmaiņas ir uzskaitītas sadaļā **Lietotās darbības**.</span><span class="sxs-lookup"><span data-stu-id="029f5-132">Each transformation gets listed under **Applied steps**.</span></span> <span data-ttu-id="029f5-133">Power Query nodrošina daudzas iepriekš izveidotas izmaiņu opcijas.</span><span class="sxs-lookup"><span data-stu-id="029f5-133">Power Query provides numerous pre-built transformation options.</span></span> <span data-ttu-id="029f5-134">Papildinformāciju skatiet sadaļā [Power Query izmaiņas](/power-query/power-query-what-is-power-query#transformations).</span><span class="sxs-lookup"><span data-stu-id="029f5-134">For more information, see [Power Query Transformations](/power-query/power-query-what-is-power-query#transformations).</span></span>

1. <span data-ttu-id="029f5-135">Saviem datu avotiem varat pievienotu papildu entītijas, dialoglodziņā **Vaicājumu rediģēšana** atlasot **Iegūt datus**.</span><span class="sxs-lookup"><span data-stu-id="029f5-135">You can add additional entities to your data source by selecting **Get data** in the **Edit queries** dialog.</span></span>

   <span data-ttu-id="029f5-136">Ir ieteicams veikt tālāk norādītās transformācijas:</span><span class="sxs-lookup"><span data-stu-id="029f5-136">These transformations are highly recommended:</span></span>

   - <span data-ttu-id="029f5-137">Ja uzņemat datus no CSV faila, pirmajā rindā bieži vien ir galvenes.</span><span class="sxs-lookup"><span data-stu-id="029f5-137">If you're ingesting data from a CSV file, the first row often contains headers.</span></span> <span data-ttu-id="029f5-138">Dodieties uz **Mainīt tabulu** un atlasiet **Izmantot galvenes kā pirmo rindu**.</span><span class="sxs-lookup"><span data-stu-id="029f5-138">Go to **Transform table** and select **Use headers as first row**.</span></span>
   - <span data-ttu-id="029f5-139">Pārliecinieties, ka datu veids ir iestatīts atbilstoši.</span><span class="sxs-lookup"><span data-stu-id="029f5-139">Ensure the data type is set appropriately.</span></span>

1. <span data-ttu-id="029f5-140">Power Query loga apakšējā labajā stūrī atlasiet **Saglabāt**, lai saglabātu izmaiņas.</span><span class="sxs-lookup"><span data-stu-id="029f5-140">Select **Save** at the bottom of the Power Query window to save the transformations.</span></span> <span data-ttu-id="029f5-141">Pēc saglabāšanas jūsu datu avots atradīsies sadaļā **Dati** > **Datu avoti**.</span><span class="sxs-lookup"><span data-stu-id="029f5-141">After saving, you'll find your data source on **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="029f5-142">Lapā **Datu avoti** redzēsit, ka jaunā datu avota statuss ir **Atsvaidzina**.</span><span class="sxs-lookup"><span data-stu-id="029f5-142">On the **Data sources** page, you'll notice the new data source is in **Refreshing** status.</span></span>

## <a name="available-power-query-data-sources"></a><span data-ttu-id="029f5-143">Pieejamie Power Query datu avoti</span><span class="sxs-lookup"><span data-stu-id="029f5-143">Available Power Query data sources</span></span>

<span data-ttu-id="029f5-144">Informāciju par jaunākajiem savienotājiem, kurus varat atlasīt datu importēšanai uz Customer Insights skatiet [Power Query savienotāja atsaucē](/power-query/connectors/).</span><span class="sxs-lookup"><span data-stu-id="029f5-144">See the [Power Query connector reference](/power-query/connectors/) for an up-to-date list of connectors that you can select to import data to Customer Insights.</span></span> 

<span data-ttu-id="029f5-145">Savienotāji ar atzīmi kolonnā **Customer Insights (Dataflows)** ir pieejami, lai izveidotu jaunus datu avotus, pamatojoties uz Power Query.</span><span class="sxs-lookup"><span data-stu-id="029f5-145">Connectors with a checkmark in the **Customer Insights (Dataflows)** column are available to create new data sources based on Power Query.</span></span> <span data-ttu-id="029f5-146">Pārskatiet konkrētā savienotāja dokumentāciju, lai uzzinātu vairāk par tā priekšnosacījumiem, ierobežojumiem un citu informāciju.</span><span class="sxs-lookup"><span data-stu-id="029f5-146">Review the documentation of a specific connector to learn more about its prerequisites, limitations, and other details.</span></span>

## <a name="edit-power-query-data-sources"></a><span data-ttu-id="029f5-147">Power Query datu avotu rediģēšana</span><span class="sxs-lookup"><span data-stu-id="029f5-147">Edit Power Query data sources</span></span>

> [!NOTE]
> <span data-ttu-id="029f5-148">Iespējams, nevarēs veikt izmaiņas datu avotos, kuri pašlaik tiek izmantoti kādā no programmas procesiem (piemēram, *segmentēšana*, *atbilstības noteikšana* vai *sapludināšana*).</span><span class="sxs-lookup"><span data-stu-id="029f5-148">It might not be possible to make changes to data sources that are currently being used in one of the app's processes (*segmentation*, *match*, or *merge*, for example).</span></span> 
>
> <span data-ttu-id="029f5-149">Izmantojot lapu **Iestatījumi**, varat izsekot katra aktīvā procesa norisei.</span><span class="sxs-lookup"><span data-stu-id="029f5-149">Using the **Settings** page, you can track the progress of each of the active processes.</span></span> <span data-ttu-id="029f5-150">Kad process ir pabeigts, varat atgriezties lapā **Datu avoti** un veikt vajadzīgās izmaiņas.</span><span class="sxs-lookup"><span data-stu-id="029f5-150">When a process completes, you can return to the **Data Sources** page and make your changes.</span></span>

1. <span data-ttu-id="029f5-151">Sadaļā Auditorijas ieskati skatiet **Dati** > **Datu avoti**.</span><span class="sxs-lookup"><span data-stu-id="029f5-151">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="029f5-152">Atlasiet vertikālo daudzpunkti blakus maināmajam datu avotam un nolaižamajā izvēlnē atlasiet **Rediģēt**.</span><span class="sxs-lookup"><span data-stu-id="029f5-152">Select the vertical ellipsis next to the data source you want to change and select **Edit** from the drop-down menu.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="029f5-153">![Rediģēšanas opcija](media/edit-option-data-sources.png "Rediģēšanas opcija")</span><span class="sxs-lookup"><span data-stu-id="029f5-153">![Edit option](media/edit-option-data-sources.png "Edit option")</span></span>

3. <span data-ttu-id="029f5-154">Piemērojiet veiktās izmaiņas un transformācijas dialoglodziņā **Power Query — izmaiņu rediģēšana**, kā aprakstīts sadaļā [Jauna datu avota izveide](#create-a-new-data-source).</span><span class="sxs-lookup"><span data-stu-id="029f5-154">Apply your changes and transformations in the **Power Query - Edit queries** dialog as described in the [Create a new data source](#create-a-new-data-source) section.</span></span>

4. <span data-ttu-id="029f5-155">Lai saglabātu izmaiņas, pēc rediģēšanas pabeigšanas Power Query atlasiet **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="029f5-155">Select **Save** in Power Query after completing your edits to save your changes.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]