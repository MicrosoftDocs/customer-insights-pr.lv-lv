---
title: Sapludināt entītijas datu apvienošanā
description: Sapludiniet entītijas, lai izveidotu vienotus klientu profilus.
ms.date: 05/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 86ab3cefa70e5fab4bdb27cde363adee26efee4c
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305656"
---
# <a name="merge-entities"></a><span data-ttu-id="48f60-103">Sapludiniet entītijas</span><span class="sxs-lookup"><span data-stu-id="48f60-103">Merge entities</span></span>

<span data-ttu-id="48f60-104">Sapludināšanas posms ir pēdējais datu apvienošanas procesa posms.</span><span class="sxs-lookup"><span data-stu-id="48f60-104">The merge phase is the last phase in the data unification process.</span></span> <span data-ttu-id="48f60-105">Tā mērķis ir konfliktējošu datu saskaņošana.</span><span class="sxs-lookup"><span data-stu-id="48f60-105">Its purpose is reconciling conflicting data.</span></span> <span data-ttu-id="48f60-106">Konfliktējošo datu piemērs var būt klienta vārds, kas ir atrodams divās datu kopās, taču katrā no tām tas tiek rādīts nedaudz atšķirīgi ("Oto Bērzs" un "Otto Bērzs"), vai tālruņa numurs, kas atšķiras pēc formāta (21-480-309 un 21480309).</span><span class="sxs-lookup"><span data-stu-id="48f60-106">Examples of conflicting data could include a customer name found in two of your datasets but that shows up a little differently in each ("Grant Marshall" versus "Grant Marshal"), or a phone number that differs in format (617-803-091X versus 617803091X).</span></span> <span data-ttu-id="48f60-107">Šo konfliktējošo datu punktu sapludināšana notiek, pamatojoties uz pieeju “atribūts pēc atribūta”</span><span class="sxs-lookup"><span data-stu-id="48f60-107">Merging those conflicting data points is done on an attribute-by-attribute basis.</span></span>

:::image type="content" source="media/merge-fields-page.png" alt-text="Datu apvienošanas procesa sapludināšanas lapa, kurā redzama tabula ar sapludinātiem laukiem, kas definē vienoto klienta profilu.":::

<span data-ttu-id="48f60-109">Pēc [atbilstības posma](match-entities.md) pabeigšanas varat sākt sapludināšanas posmu, lapā **Apvienošana** atlasot **Sapludināt**.</span><span class="sxs-lookup"><span data-stu-id="48f60-109">After completing the [match phase](match-entities.md), you start the merge phase by selecting the **Merge** tile on the **Unify** page.</span></span>

## <a name="review-system-recommendations"></a><span data-ttu-id="48f60-110">Sistēmas ieteikumu pārskatīšana</span><span class="sxs-lookup"><span data-stu-id="48f60-110">Review system recommendations</span></span>

<span data-ttu-id="48f60-111">Izmantojot **Dati** > **Apvienot** > **Sapludināt**, jūs izvēlaties un izslēdzat atribūtus, kas jāsapludina jūsu vienotajā klienta profila entītijā.</span><span class="sxs-lookup"><span data-stu-id="48f60-111">On **Data** > **Unify** > **Merge**, you choose and exclude attributes to merge within your unified customer profile entity.</span></span> <span data-ttu-id="48f60-112">Vienotais klienta profils ir datu unificēšanas procesa rezultāts.</span><span class="sxs-lookup"><span data-stu-id="48f60-112">The unified customer profile is the result of the data unification process.</span></span> <span data-ttu-id="48f60-113">Dažus atribūtus sistēma sapludina automātiski.</span><span class="sxs-lookup"><span data-stu-id="48f60-113">Some attributes are automatically merged by the system.</span></span>

<span data-ttu-id="48f60-114">Lai skatītu atribūtus, kas iekļauti kādā no automātiski sapludinātajiem atribūtiem, atlasiet šo sapludināto atribūtu entītijas cilnē **Klienta lauki**.</span><span class="sxs-lookup"><span data-stu-id="48f60-114">To view the attributes that are included in one of your automatically merged attributes, select that merged attribute in the **Customer fields** tab of the table.</span></span> <span data-ttu-id="48f60-115">Šie divi atribūti, kas veido sapludināto atribūtu, tiks parādīti divās jaunās rindās zem sapludinātā atribūta.</span><span class="sxs-lookup"><span data-stu-id="48f60-115">The attributes that compose that merged attribute display in two new rows beneath the merged attribute.</span></span>

## <a name="separate-rename-exclude-and-edit-merged-fields"></a><span data-ttu-id="48f60-116">Atdalīt, pārdēvēt, izslēgt un rediģēt sapludinātos laukus</span><span class="sxs-lookup"><span data-stu-id="48f60-116">Separate, rename, exclude, and edit merged fields</span></span>

<span data-ttu-id="48f60-117">Var mainīt, kā sistēma apstrādā sapludinātos atribūtus, lai ģenerētu vienoto klienta profilu.</span><span class="sxs-lookup"><span data-stu-id="48f60-117">You can change how the system processes merged attributes to generate the unified customer profile.</span></span> <span data-ttu-id="48f60-118">Atlasiet vienumu **Rādīt vairāk** un izvēlieties, ko vēlaties mainīt.</span><span class="sxs-lookup"><span data-stu-id="48f60-118">Select **Show more** and choose what you want to change.</span></span>

:::image type="content" source="media/manage-merged-attributes.png" alt-text="Nolaižamās izvēlnes Rādīt vairāk opcijas, lai pārvaldītu sapludinātos atribūtus.":::

<span data-ttu-id="48f60-120">Papildinformāciju skatiet nākamajās sadaļās.</span><span class="sxs-lookup"><span data-stu-id="48f60-120">For more information, see the following sections.</span></span>

## <a name="separate-merged-fields"></a><span data-ttu-id="48f60-121">Atdalīt sapludinātos laukus</span><span class="sxs-lookup"><span data-stu-id="48f60-121">Separate merged fields</span></span>

<span data-ttu-id="48f60-122">Lai atdalītu sapludinātos laukus, atrodiet atribūtu tabulā.</span><span class="sxs-lookup"><span data-stu-id="48f60-122">To separate merged fields, find the attribute in the table.</span></span> <span data-ttu-id="48f60-123">Atsevišķie lauki vienotā klienta profilā tiek rādīti kā atsevišķi datu punkti.</span><span class="sxs-lookup"><span data-stu-id="48f60-123">Separated fields show as individual data points on the unified customer profile.</span></span> 

1. <span data-ttu-id="48f60-124">Atlasiet sapludināto lauku.</span><span class="sxs-lookup"><span data-stu-id="48f60-124">Select the merged field.</span></span>
  
1. <span data-ttu-id="48f60-125">Atlasiet vienumu **Rādīt vairāk** un izvēlieties **Atsevišķi lauki**.</span><span class="sxs-lookup"><span data-stu-id="48f60-125">Select **Show more** and choose **Separate fields**.</span></span>
 
1. <span data-ttu-id="48f60-126">Apstipriniet atdali.</span><span class="sxs-lookup"><span data-stu-id="48f60-126">Confirm the separation.</span></span>

1. <span data-ttu-id="48f60-127">Lai apstrādātu izmaiņas, atlasiet **Saglabāt** un **Palaist**.</span><span class="sxs-lookup"><span data-stu-id="48f60-127">Select **Save** and **Run** to process the changes.</span></span>

## <a name="rename-merged-fields"></a><span data-ttu-id="48f60-128">Sapludināto lauku pārdēvēšana</span><span class="sxs-lookup"><span data-stu-id="48f60-128">Rename merged fields</span></span>

<span data-ttu-id="48f60-129">Mainīt sapludināto atribūtu parādāmo nosaukumu.</span><span class="sxs-lookup"><span data-stu-id="48f60-129">Change the display name of merged attributes.</span></span> <span data-ttu-id="48f60-130">Izvades entītijas nosaukumu nevar mainīt.</span><span class="sxs-lookup"><span data-stu-id="48f60-130">You can't change the name of the output entity.</span></span>

1. <span data-ttu-id="48f60-131">Atlasiet sapludināto lauku.</span><span class="sxs-lookup"><span data-stu-id="48f60-131">Select the merged field.</span></span>
  
1. <span data-ttu-id="48f60-132">Atlasiet vienumu **Rādīt vairāk** un izvēlieties **Pārdēvēt**.</span><span class="sxs-lookup"><span data-stu-id="48f60-132">Select **Show more** and choose **Rename**.</span></span>

1. <span data-ttu-id="48f60-133">Apstipriniet mainīto parādāmo nosaukumu.</span><span class="sxs-lookup"><span data-stu-id="48f60-133">Confirm the changed display name.</span></span> 

1. <span data-ttu-id="48f60-134">Lai apstrādātu izmaiņas, atlasiet **Saglabāt** un **Palaist**.</span><span class="sxs-lookup"><span data-stu-id="48f60-134">Select **Save** and **Run** to process the changes.</span></span>

## <a name="exclude-merged-fields"></a><span data-ttu-id="48f60-135">Izslēgt sapludinātos laukus</span><span class="sxs-lookup"><span data-stu-id="48f60-135">Exclude merged fields</span></span>

<span data-ttu-id="48f60-136">Neiekļaut atribūtu no vienotā klienta profila.</span><span class="sxs-lookup"><span data-stu-id="48f60-136">Exclude an attribute from the unified customer profile.</span></span> <span data-ttu-id="48f60-137">Ja lauks tiek izmantots citos procesos, piemēram, segmentā, pirms lauka izslēgšanas no klienta profila, noņemiet to no šiem procesiem.</span><span class="sxs-lookup"><span data-stu-id="48f60-137">If the field is used in other processes, for example in a segment, remove it from these processes before excluding it from the customer profile.</span></span> 

1. <span data-ttu-id="48f60-138">Atlasiet sapludināto lauku.</span><span class="sxs-lookup"><span data-stu-id="48f60-138">Select the merged field.</span></span>
  
1. <span data-ttu-id="48f60-139">Atlasiet vienumu **Rādīt vairāk** un izvēlieties **Izslēgt**.</span><span class="sxs-lookup"><span data-stu-id="48f60-139">Select **Show more** and choose **Exclude**.</span></span>

1. <span data-ttu-id="48f60-140">Apstipriniet izslēgšanu.</span><span class="sxs-lookup"><span data-stu-id="48f60-140">Confirm the exclusion.</span></span>

1. <span data-ttu-id="48f60-141">Lai apstrādātu izmaiņas, atlasiet **Saglabāt** un **Palaist**.</span><span class="sxs-lookup"><span data-stu-id="48f60-141">Select **Save** and **Run** to process the changes.</span></span> 

<span data-ttu-id="48f60-142">**Sapludināšanas** lapā atlasiet **Neiekļautie lauki**, lai redzētu visu neiekļauto lauku sarakstu.</span><span class="sxs-lookup"><span data-stu-id="48f60-142">On the **Merge** page, select **Excluded fields** to see the list of all excluded fields.</span></span> <span data-ttu-id="48f60-143">Šajā rūtī varat atkal pievienot neiekļautos laukus.</span><span class="sxs-lookup"><span data-stu-id="48f60-143">This pane lets you add excluded fields back.</span></span>

## <a name="manually-combine-fields"></a><span data-ttu-id="48f60-144">Manuāli apvienot laukus</span><span class="sxs-lookup"><span data-stu-id="48f60-144">Manually combine fields</span></span>

<span data-ttu-id="48f60-145">Manuāli norādiet sapludinātu atribūtu.</span><span class="sxs-lookup"><span data-stu-id="48f60-145">Specify a merged attribute manually.</span></span> 

1. <span data-ttu-id="48f60-146">**Sapludināšanas** lapā atlasiet **Lauku apvienošana**.</span><span class="sxs-lookup"><span data-stu-id="48f60-146">On the **Merge** page, select **Combine fields**.</span></span>

1. <span data-ttu-id="48f60-147">Norādiet **Nosaukumu** un **Izvades lauka nosaukumu**.</span><span class="sxs-lookup"><span data-stu-id="48f60-147">Provide a **Name** and an **Output field name**.</span></span>

1. <span data-ttu-id="48f60-148">Izvēlieties pievienojamo lauku.</span><span class="sxs-lookup"><span data-stu-id="48f60-148">Choose a field to add.</span></span> <span data-ttu-id="48f60-149">Atlasiet **Pievienot laukus**, lai apvienotu vairāk lauku.</span><span class="sxs-lookup"><span data-stu-id="48f60-149">Select **Add fields** to combine more fields.</span></span>

1. <span data-ttu-id="48f60-150">Apstipriniet izslēgšanu.</span><span class="sxs-lookup"><span data-stu-id="48f60-150">Confirm the exclusion.</span></span>

1. <span data-ttu-id="48f60-151">Lai apstrādātu izmaiņas, atlasiet **Saglabāt** un **Palaist**.</span><span class="sxs-lookup"><span data-stu-id="48f60-151">Select **Save** and **Run** to process the changes.</span></span> 

## <a name="change-the-order-of-fields"></a><span data-ttu-id="48f60-152">Lauku secības maiņa</span><span class="sxs-lookup"><span data-stu-id="48f60-152">Change the order of fields</span></span>

<span data-ttu-id="48f60-153">Dažās entītijās ir detalizētāka informācija nekā citās.</span><span class="sxs-lookup"><span data-stu-id="48f60-153">Some entities contain more details than others.</span></span> <span data-ttu-id="48f60-154">Ja entītijā ir ietverti jaunākie dati par kādu lauku, sapludinot vērtības, par to var noteikt prioritātes citās entītijās.</span><span class="sxs-lookup"><span data-stu-id="48f60-154">If an entity includes the latest data about a field, you can prioritize it over other entities when merging values.</span></span>

1. <span data-ttu-id="48f60-155">Atlasiet sapludināto lauku.</span><span class="sxs-lookup"><span data-stu-id="48f60-155">Select the merged field.</span></span>
  
1. <span data-ttu-id="48f60-156">Atlasiet vienumu **Rādīt vairāk** un izvēlieties **Rediģēt**.</span><span class="sxs-lookup"><span data-stu-id="48f60-156">Select **Show more** and choose **Edit**.</span></span>

1. <span data-ttu-id="48f60-157">**Lauku apvienošanas** rūtī atlasiet **Pārvietot uz augšu/uz leju**, lai iestatītu secību, vai velciet un nometiet tos vēlamajā pozīcijā.</span><span class="sxs-lookup"><span data-stu-id="48f60-157">In the **Combine fields** pane, select **Move up/down** to set the order or drag and drop them in the desired position.</span></span>

1. <span data-ttu-id="48f60-158">Apstiprināt izmaiņas.</span><span class="sxs-lookup"><span data-stu-id="48f60-158">Confirm the change.</span></span>

1. <span data-ttu-id="48f60-159">Lai apstrādātu izmaiņas, atlasiet **Saglabāt** un **Palaist**.</span><span class="sxs-lookup"><span data-stu-id="48f60-159">Select **Save** and **Run** to process the changes.</span></span>

## <a name="run-your-merge"></a><span data-ttu-id="48f60-160">Sapludināšanas izpilde</span><span class="sxs-lookup"><span data-stu-id="48f60-160">Run your merge</span></span>

<span data-ttu-id="48f60-161">Neatkarīgi no tā, vai manuāli sapludināt atribūtus vai ļaujat tos sapludināt sistēmai, jūs jebkurā gadījumā varat izpildīt sapludināšanu.</span><span class="sxs-lookup"><span data-stu-id="48f60-161">Whether you manually merge attributes or let the system merge them, you can always run your merge.</span></span> <span data-ttu-id="48f60-162">Lapā **Sapludināšana** atlasiet **Izpildīt**, lai sāktu procesu.</span><span class="sxs-lookup"><span data-stu-id="48f60-162">Select **Run** on the **Merge** page to start the process.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="48f60-163">![Datu sapludināšana: saglabāšana un izpilde](media/configure-data-merge-save-run.png "Datu sapludināšana: saglabāšana un izpilde")</span><span class="sxs-lookup"><span data-stu-id="48f60-163">![Data merge Save and Run](media/configure-data-merge-save-run.png "Data merge Save and Run")</span></span>

<span data-ttu-id="48f60-164">Izvēlieties **Palaist tikai sapludināšanu**, ja vēlaties redzēt tikai vienotā klienta entītijas izvadi.</span><span class="sxs-lookup"><span data-stu-id="48f60-164">Choose **Run only Merge** if you only want to see the output reflected in the unified customer entity.</span></span> <span data-ttu-id="48f60-165">Lejupstraumes procesi tiks atsvaidzināti, kā [definēts atsvaidzināšanas grafikā](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="48f60-165">Downstream processes will be refreshed as [defined in the refresh schedule](system.md#schedule-tab).</span></span>

<span data-ttu-id="48f60-166">Izvēlieties **Palaist sapludināšanu un lejupstraumes procesus**, lai atsvaidzinātu sistēmu ar jūsu izmaiņām.</span><span class="sxs-lookup"><span data-stu-id="48f60-166">Choose **Run Merge and downstream processes** to refresh the system with your changes.</span></span> <span data-ttu-id="48f60-167">Visi procesi, tostarp bagātināšana, segmenti un pasākumi, tiks automātiski veikti atkārtoti.</span><span class="sxs-lookup"><span data-stu-id="48f60-167">All processes, including enrichment, segments, and measures will rerun automatically.</span></span> <span data-ttu-id="48f60-168">Kad visi lejupstraumes procesi ir pabeigti, klientu profili atspoguļo jūsu veiktās izmaiņas.</span><span class="sxs-lookup"><span data-stu-id="48f60-168">After all downstream processes have completed, the customer profiles reflect any changes you made.</span></span>

<span data-ttu-id="48f60-169">Lai veiktu lielākas izmaiņas un veiktu atkārtotu darbību, varat atcelt notiekošu sapludināšanu.</span><span class="sxs-lookup"><span data-stu-id="48f60-169">To make more changes and rerun the step, you can cancel an in-progress merge.</span></span> <span data-ttu-id="48f60-170">Atlasiet **Atsvaidzina...** un atlasiet **Atcelt uzdevumu** blakus rūtī, kas tiek parādīta.</span><span class="sxs-lookup"><span data-stu-id="48f60-170">Select **Refreshing ...** and select **Cancel job**  in the side pane that appears.</span></span>

> [!TIP]
> <span data-ttu-id="48f60-171">Uzdevumiem/procesiem ir [seši statusu tipi](system.md#status-types).</span><span class="sxs-lookup"><span data-stu-id="48f60-171">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="48f60-172">Turklāt vairums procesu [ir atkarīgi no citiem pakārtotiem procesiem](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="48f60-172">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="48f60-173">Varat atlasīt procesa statusu, lai skatītu detalizētu informāciju par visa uzdevuma norisi.</span><span class="sxs-lookup"><span data-stu-id="48f60-173">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="48f60-174">Pēc tam, kad vienam no darba uzdevumiem esat atlasījis **Skatīt detalizētu informāciju**, jūs redzēsit papildinformāciju: apstrādes laiku, pēdējās apstrādes datumu un visas kļūdas un brīdinājumus, kas saistīti ar uzdevumu.</span><span class="sxs-lookup"><span data-stu-id="48f60-174">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="48f60-175">Nākamā darbība</span><span class="sxs-lookup"><span data-stu-id="48f60-175">Next Step</span></span>

<span data-ttu-id="48f60-176">Konfigurējiet opcijas [darbības](activities.md), [bagātināšana](enrichment-hub.md) vai [relācijas](relationships.md), lai gūtu plašāku ieskatu par saviem klientiem.</span><span class="sxs-lookup"><span data-stu-id="48f60-176">Configure [activities](activities.md), [enrichment](enrichment-hub.md), or [relationships](relationships.md) to gain more insights about your customers.</span></span>

<span data-ttu-id="48f60-177">Ja jau esat konfigurējis darbības, bagātināšanu vai segmentus, tie tiks apstrādāti automātiski, lai izmantotu jaunākos klientu datus.</span><span class="sxs-lookup"><span data-stu-id="48f60-177">If you already configured activities, enrichment, or segments, they'll be processed automatically to use the latest customer data.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
