---
title: Auditorijas ieskatu segmenti
description: Segmentu pārskats un to izveide un pārvaldība.
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 6cb7bd62bf0f61e6dc5811b20e5011e4a086c743
ms.sourcegitcommit: 84283d523a891298fca8aaf629d9f9ab2a1bc067
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 05/27/2021
ms.locfileid: "6111396"
---
# <a name="segments-overview"></a><span data-ttu-id="d04a6-103">Segmentu pārskats</span><span class="sxs-lookup"><span data-stu-id="d04a6-103">Segments overview</span></span>

<span data-ttu-id="d04a6-104">Segmenti jums ļauj sagrupēt klientus, pamatojoties uz demogrāfiskajiem, transakciju vai uzvedības atribūtiem.</span><span class="sxs-lookup"><span data-stu-id="d04a6-104">Segments let you group your customers based on demographic, transactional, or behavioral attributes.</span></span> <span data-ttu-id="d04a6-105">Lai sasniegtu uzņēmuma mērķus, var izmantot segmentus, lai mērķētu reklāmas kampaņas, pārdošanas darbības un klientu atbalsta darbības.</span><span class="sxs-lookup"><span data-stu-id="d04a6-105">You can use segments to target promotional campaigns, sales activities, and customer support actions to achieve your business goals.</span></span>

<span data-ttu-id="d04a6-106">Klientu profili, kas atbilst segmenta definīcijas filtriem, tiek saukti par segmenta *dalībniekiem*.</span><span class="sxs-lookup"><span data-stu-id="d04a6-106">Customer profiles that match the filters of a segment definition are referred as *members* of a segment.</span></span> <span data-ttu-id="d04a6-107">Ir [spēkā noteikti pakalpojuma ierobežojumi](service-limits.md).</span><span class="sxs-lookup"><span data-stu-id="d04a6-107">Some [service limits](service-limits.md) apply.</span></span>

## <a name="create-a-new-segment"></a><span data-ttu-id="d04a6-108">Izveidot jaunu segmentu</span><span class="sxs-lookup"><span data-stu-id="d04a6-108">Create a new segment</span></span>

<span data-ttu-id="d04a6-109">Ir vairāki jauna segmenta izveides veidi:</span><span class="sxs-lookup"><span data-stu-id="d04a6-109">There are multiple ways to create a new segment:</span></span> 

- <span data-ttu-id="d04a6-110">Sarežģīts segments ar segmenta būvētāju [Tukšs segments](segment-builder.md#create-a-new-segment)</span><span class="sxs-lookup"><span data-stu-id="d04a6-110">Complex segment with segment builder: [Blank segment](segment-builder.md#create-a-new-segment)</span></span>
- <span data-ttu-id="d04a6-111">Vienkārši segmenti ar vienu operatoru: [ātrais segments](segment-builder.md#quick-segments)</span><span class="sxs-lookup"><span data-stu-id="d04a6-111">Simple segments with one operator: [Quick segment](segment-builder.md#quick-segments)</span></span>
- <span data-ttu-id="d04a6-112">AI veids, kā atrast līdzīgus klientus: [līdzīgi klienti](find-similar-customer-segments.md)</span><span class="sxs-lookup"><span data-stu-id="d04a6-112">AI-powered way to find similar customers: [Similar Customers](find-similar-customer-segments.md)</span></span>
- <span data-ttu-id="d04a6-113">AI sekmēti ierosinājumi, kas balstīti uz pasākumiem vai atribūtiem: [ieteiktie segmenti pasākumu uzlabošanai](suggested-segments.md)</span><span class="sxs-lookup"><span data-stu-id="d04a6-113">AI-powered suggestions based on measures or attributes: [Suggested segments to improve measures](suggested-segments.md)</span></span>
- <span data-ttu-id="d04a6-114">Uz darbībām balstīti ieteikumi: [ieteiktie segmenti, pamatojoties uz klientu darbību](suggested-segments-activity.md)</span><span class="sxs-lookup"><span data-stu-id="d04a6-114">Suggestions based on activities: [Suggested segments based on customer activity](suggested-segments-activity.md)</span></span>

## <a name="manage-existing-segments"></a><span data-ttu-id="d04a6-115">Esošo segmentu pārvaldība</span><span class="sxs-lookup"><span data-stu-id="d04a6-115">Manage existing segments</span></span>

<span data-ttu-id="d04a6-116">Lai skatītu visus saglabātos segmentus un tos pārvaldītu, atveriet lapu **Segmenti**.</span><span class="sxs-lookup"><span data-stu-id="d04a6-116">Go to the **Segments** page, to view all your saved segments and manage them.</span></span>

<span data-ttu-id="d04a6-117">Katru segmentu apzīmē rinda, kurā ir iekļauta papildu informācija par segmentu.</span><span class="sxs-lookup"><span data-stu-id="d04a6-117">Each segment is represented by a row that includes additional information about the segment.</span></span>

:::image type="content" source="media/segments-selected-segment.png" alt-text="Atlasīts segments ar nolaižamo sarakstu ar opcijām un pieejamām opcijām.":::

<span data-ttu-id="d04a6-119">Kad atlasāt segmentu, ir pieejamas tālāk norādītās darbības:</span><span class="sxs-lookup"><span data-stu-id="d04a6-119">The following action are available when you select a segment:</span></span>

- <span data-ttu-id="d04a6-120">**Skatīt** segmenta informāciju, tostarp segmenta dalībnieku skaita tendences priekšskatījumu.</span><span class="sxs-lookup"><span data-stu-id="d04a6-120">**View** the segment details, including member count trend a preview of segment members.</span></span>
- <span data-ttu-id="d04a6-121">**Rediģēt** segmentu, lai mainītu tā rekvizītus.</span><span class="sxs-lookup"><span data-stu-id="d04a6-121">**Edit** the segment to change its properties.</span></span>
- <span data-ttu-id="d04a6-122">**Izveidot dublikātu** segmentam.</span><span class="sxs-lookup"><span data-stu-id="d04a6-122">**Create duplicate** of a segment.</span></span> <span data-ttu-id="d04a6-123">Varat izvēlēties rediģēt tā rekvizītus uzreiz vai vienkārši saglabāt dublikātu.</span><span class="sxs-lookup"><span data-stu-id="d04a6-123">You can choose to edit its properties right away or simply save the duplicate.</span></span>
- <span data-ttu-id="d04a6-124">**Atsvaidzināt** segmentu, lai iekļautu jaunākos datus.</span><span class="sxs-lookup"><span data-stu-id="d04a6-124">**Refresh** the segment to include the latest data.</span></span>
- <span data-ttu-id="d04a6-125">**Aktivizēt** vai **Deaktivizēt** segmentu.</span><span class="sxs-lookup"><span data-stu-id="d04a6-125">**Activate** or **Deactivate** the segment.</span></span> <span data-ttu-id="d04a6-126">Segmentiem ir divi iespējamie statusi — aktīvs vai neaktīvs.</span><span class="sxs-lookup"><span data-stu-id="d04a6-126">Segments have two possible states - active or inactive.</span></span> <span data-ttu-id="d04a6-127">Šie statusi ir noderīgi, rediģējot segmentu.</span><span class="sxs-lookup"><span data-stu-id="d04a6-127">These states come in handy when editing a segment.</span></span> <span data-ttu-id="d04a6-128">Neaktīvajiem segmentiem pastāv segmenta definīcija, taču tajā vēl nav klientu.</span><span class="sxs-lookup"><span data-stu-id="d04a6-128">For inactive segments, the segment definition exists but it doesn't contain any customers yet.</span></span> <span data-ttu-id="d04a6-129">Aktivizējot segmentu, tā statuss tiek mainīts no “neaktīvs” uz “aktīvs”, un tas sāk meklēt klientus, kas atbilst segmenta definīcijai.</span><span class="sxs-lookup"><span data-stu-id="d04a6-129">When you activate a segment, its state changes from 'inactive' to 'active" and it starts looking for customers that match the segment definition.</span></span> <span data-ttu-id="d04a6-130">Ja ir konfigurēta [plānotā atsvaidzināšana](system.md#schedule-tab), neaktīvajiem segmentiem **Statuss** ir norādīts kā **Izlaists**, kas norāda, ka atsvaidzināšana nav pat mēģināta.</span><span class="sxs-lookup"><span data-stu-id="d04a6-130">If a [scheduled refresh](system.md#schedule-tab) is configured, inactive segments have the **Status** listed as **Skipped**, indicating that a refresh wasn't even attempted.</span></span> <span data-ttu-id="d04a6-131">Ja ir aktivizēts neaktīvs segments, tas tiek atsvaidzināts un iekļauts atsvaidzināšanas grafikā.</span><span class="sxs-lookup"><span data-stu-id="d04a6-131">When an inactive segment is activated, it will refresh and will be included in scheduled refreshes.</span></span>
  <span data-ttu-id="d04a6-132">Vai arī varat izmantot funkcionalitāti **Plānot vēlāk** nolaižamajā izvēlnē **Aktivizēt/Deaktivizēt**, lai norādītu nākotnes datumu un laiku noteikta segmenta aktivizēšanai un deaktivizēšanai.</span><span class="sxs-lookup"><span data-stu-id="d04a6-132">Alternatively, you can use the **Schedule later** functionality in the **Activate/Deactivate** dropdown to specify a future date and time for activation and deactivation of a particular segment.</span></span>
- <span data-ttu-id="d04a6-133">**Pārdēvēt** segmentu.</span><span class="sxs-lookup"><span data-stu-id="d04a6-133">**Rename** the segment.</span></span>
- <span data-ttu-id="d04a6-134">**Lejupielādēt** dalībnieku sarakstu kā .CSV failu.</span><span class="sxs-lookup"><span data-stu-id="d04a6-134">**Download** the list of members as a .CSV file.</span></span>
- <span data-ttu-id="d04a6-135">**Pārvaldīt eksportu**, lai skatītu ar eksportu saistīto segmentu un pārvaldītu to.</span><span class="sxs-lookup"><span data-stu-id="d04a6-135">**Manage exports** to see exports related segment and manage them.</span></span> [<span data-ttu-id="d04a6-136">Uzzināt vairāk par eksportēšanu.</span><span class="sxs-lookup"><span data-stu-id="d04a6-136">Learn more about exports.</span></span>](export-destinations.md)
- <span data-ttu-id="d04a6-137">**Dzēst** segmentu.</span><span class="sxs-lookup"><span data-stu-id="d04a6-137">**Delete** the segment.</span></span>

## <a name="refresh-segments"></a><span data-ttu-id="d04a6-138">Atsvaidzināt segmentus</span><span class="sxs-lookup"><span data-stu-id="d04a6-138">Refresh segments</span></span>

<span data-ttu-id="d04a6-139">Visus segmentus uzreiz var atsvaidzināt, atlasot **Atsvaidzināt visus** lapā **Segmenti**, vai varat atsvaidzināt vienu vai vairākus segmentus, tos atlasot un izvēloties opciju **Atsvaidzināt** no piedāvātajām opcijām.</span><span class="sxs-lookup"><span data-stu-id="d04a6-139">You can refresh all segments at once by selecting **Refresh all** on the **Segments** page or you can refresh one or multiple segments when you select them and choose **Refresh** in from the options.</span></span> <span data-ttu-id="d04a6-140">Vai arī varat konfigurēt periodisku atsvaidzināšanu sadaļā **Administrators** > **Sistēma** > **Grafiks**.</span><span class="sxs-lookup"><span data-stu-id="d04a6-140">Alternatively, you can configure a recurring refresh on **Admin** > **System** > **Schedule**.</span></span>

> [!TIP]
> <span data-ttu-id="d04a6-141">Uzdevumiem/procesiem ir [seši statusu tipi](system.md#status-types).</span><span class="sxs-lookup"><span data-stu-id="d04a6-141">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="d04a6-142">Turklāt vairums procesu [ir atkarīgi no citiem pakārtotiem procesiem](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="d04a6-142">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="d04a6-143">Varat atlasīt procesa statusu, lai skatītu detalizētu informāciju par visa uzdevuma norisi.</span><span class="sxs-lookup"><span data-stu-id="d04a6-143">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="d04a6-144">Pēc tam, kad vienam no darba uzdevumiem esat atlasījis **Skatīt detalizētu informāciju**, jūs redzēsit papildinformāciju: apstrādes laiku, pēdējās apstrādes datumu un visas ar uzdevumu saistītas kļūdas un brīdinājumus.</span><span class="sxs-lookup"><span data-stu-id="d04a6-144">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="export-segments"></a><span data-ttu-id="d04a6-145">Segmentu eksportēšana</span><span class="sxs-lookup"><span data-stu-id="d04a6-145">Export segments</span></span>

<span data-ttu-id="d04a6-146">Segmentu var eksportēt no segmentu lapas vai [eksportēšanas lapas](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="d04a6-146">You can export a segment from the segments page or the [exports page](export-destinations.md).</span></span> 

1. <span data-ttu-id="d04a6-147">Doties uz lapu **Segmenti**.</span><span class="sxs-lookup"><span data-stu-id="d04a6-147">Go to the **Segments** page.</span></span>

1. <span data-ttu-id="d04a6-148">Atlasiet **Parādīt vēl [...]** eksportējamam segmentam.</span><span class="sxs-lookup"><span data-stu-id="d04a6-148">Select **Show more [...]** for the segment you want to export.</span></span>

1. <span data-ttu-id="d04a6-149">Darbību nolaižamajā sarakstā atlasiet **Pārvaldīt eksportu**.</span><span class="sxs-lookup"><span data-stu-id="d04a6-149">Select **Manage exports** from the actions drop-down list.</span></span>

1. <span data-ttu-id="d04a6-150">Tiek atvērta lapa **Segmenta eksports (priekšskatījums)**.</span><span class="sxs-lookup"><span data-stu-id="d04a6-150">The page **Exports (preview) for segment** opens.</span></span> <span data-ttu-id="d04a6-151">Var redzēt visas konfigurētās eksportēšanas darbības, kas grupēts pēc eksporta, kurā ir pašreizējais segments vai kurā tas nav iekļauts.</span><span class="sxs-lookup"><span data-stu-id="d04a6-151">You can see all configured exports grouped by by exports that contain the current segment or don't contain it.</span></span>

   1. <span data-ttu-id="d04a6-152">Lai atlasīto segmentu pievienotu eksportēšanai, sarakstā atlasiet eksportēt un atlasiet **Pievienot segmentu**.</span><span class="sxs-lookup"><span data-stu-id="d04a6-152">To add the selected segment to an export, select the export in the list and select **Add segment**.</span></span>

   1. <span data-ttu-id="d04a6-153">Lai izveidotu jaunu eksportu ar atlasīto segmentu, atlasiet **Pievienot eksportēšanu**.</span><span class="sxs-lookup"><span data-stu-id="d04a6-153">To create a new export with the selected segment, select **Add export**.</span></span> <span data-ttu-id="d04a6-154">Papildinformāciju par eksportēšanas darbību izveidi skatiet rakstā [Jaunas eksportēsanas darbības iestatīšana](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="d04a6-154">For more information about creating exports, see [Set up a new export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="d04a6-155">Atlasiet **Atpakaļ**, lai atgrieztos segmentu galvenajā lapā.</span><span class="sxs-lookup"><span data-stu-id="d04a6-155">Select **Back** to return to the main page for segments.</span></span>

## <a name="view-processing-history-and-segment-members"></a><span data-ttu-id="d04a6-156">Apstrādes vēstures un segmentu elementu skatīšana</span><span class="sxs-lookup"><span data-stu-id="d04a6-156">View processing history and segment members</span></span>

<span data-ttu-id="d04a6-157">Lai skatītu apkopotos datus par segmentu, pārskatot informāciju par segmentu.</span><span class="sxs-lookup"><span data-stu-id="d04a6-157">You can see consolidated data about a segment by reviewing its details.</span></span>

<span data-ttu-id="d04a6-158">Lapā **Segmenti** atlasiet segmentu, kuru vēlaties pārskatīt.</span><span class="sxs-lookup"><span data-stu-id="d04a6-158">On the **Segments** page, select the segment you want to review.</span></span>

<span data-ttu-id="d04a6-159">Lapas augšējā daļa ietver tendenču grafiku, kas vizualizē elementu skaita izmaiņas.</span><span class="sxs-lookup"><span data-stu-id="d04a6-159">The upper part of the page includes a trend graph that visualizes changes in member count.</span></span> <span data-ttu-id="d04a6-160">Norādiet uz datu punktiem, lai skatītu elementu skaitu noteiktā datumā.</span><span class="sxs-lookup"><span data-stu-id="d04a6-160">Hover over data points to see the member count on a specific date.</span></span>

<span data-ttu-id="d04a6-161">Varat atjaunināt vizualizācijas laika periodu.</span><span class="sxs-lookup"><span data-stu-id="d04a6-161">You can update the time frame of the visualization.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d04a6-162">![Segmenta laika diapazons](media/segment-time-range.png "Segmenta laika diapazons")</span><span class="sxs-lookup"><span data-stu-id="d04a6-162">![Segment time range](media/segment-time-range.png "Segment time range")</span></span>

<span data-ttu-id="d04a6-163">Apakšējā daļa ietver segmenta elementu sarakstu.</span><span class="sxs-lookup"><span data-stu-id="d04a6-163">The lower part contains a list of the segment members.</span></span>

> [!NOTE]
> <span data-ttu-id="d04a6-164">Šajā sarakstā parādītie lauki tiek balstīti uz segmenta entītiju atribūtiem.</span><span class="sxs-lookup"><span data-stu-id="d04a6-164">Fields that appear in this list are based on the attributes of your segment's entities.</span></span>
>
><span data-ttu-id="d04a6-165">Saraksts ir atbilstošo segmenta dalībnieku priekšskatījums un parāda jūsu segmenta pirmos 100 ierakstus, lai to varētu ātri novērtēt un vajadzības gadījumā pārskatīt tā definīcijas.</span><span class="sxs-lookup"><span data-stu-id="d04a6-165">The list is a preview of the matching segment members and shows the first 100 records of your segment so that you can quickly evaluate it and review its definitions if needed.</span></span> <span data-ttu-id="d04a6-166">Lai skatītu visus atbilstošos ierakstus, ir [jāeksportē šis segments](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="d04a6-166">To see all matching records, you need to [export the segment](export-destinations.md).</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)] 
