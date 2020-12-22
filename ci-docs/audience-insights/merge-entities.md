---
title: Sapludināt entītijas datu apvienošanā
description: Sapludiniet entītijas, lai izveidotu vienotus klientu profilus.
ms.date: 04/16/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 045fd8d8f65161b91caabed2ac52494dc4fb3910
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406360"
---
# <a name="merge-entities"></a><span data-ttu-id="52c50-103">Sapludiniet entītijas</span><span class="sxs-lookup"><span data-stu-id="52c50-103">Merge entities</span></span>

<span data-ttu-id="52c50-104">Sapludināšanas posms ir pēdējais datu apvienošanas procesa posms.</span><span class="sxs-lookup"><span data-stu-id="52c50-104">The merge phase is the last phase in the data unification process.</span></span> <span data-ttu-id="52c50-105">Tā mērķis ir konfliktējošu datu saskaņošana.</span><span class="sxs-lookup"><span data-stu-id="52c50-105">Its purpose is reconciling conflicting data.</span></span> <span data-ttu-id="52c50-106">Konfliktējošo datu piemērs var būt klienta vārds, kas ir atrodams divās datu kopās, taču katrā no tām tas tiek rādīts nedaudz atšķirīgi ("Oto Bērzs" un "Otto Bērzs"), vai tālruņa numurs, kas atšķiras pēc formāta (21-480-309 un 21480309).</span><span class="sxs-lookup"><span data-stu-id="52c50-106">Examples of conflicting data could include a customer name found in two of your datasets but that shows up a little differently in each ("Grant Marshall" versus "Grant Marshal"), or a phone number that differs in format (617-803-091X versus 617803091X).</span></span> <span data-ttu-id="52c50-107">Šo konfliktējošo datu punktu sapludināšana notiek, pamatojoties uz pieeju “atribūts pēc atribūta”</span><span class="sxs-lookup"><span data-stu-id="52c50-107">Merging those conflicting data points is done on an attribute-by-attribute basis.</span></span>

<span data-ttu-id="52c50-108">Pēc [atbilstības posma](match-entities.md) pabeigšanas varat sākt sapludināšanas posmu, lapā **Apvienošana** atlasot **Sapludināt**.</span><span class="sxs-lookup"><span data-stu-id="52c50-108">After completing the [match phase](match-entities.md), you start the merge phase by selecting the **Merge** tile on the **Unify** page.</span></span>

## <a name="review-system-recommendations"></a><span data-ttu-id="52c50-109">Sistēmas ieteikumu pārskatīšana</span><span class="sxs-lookup"><span data-stu-id="52c50-109">Review system recommendations</span></span>

<span data-ttu-id="52c50-110">Lapā **Sapludināšana** varat izvēlēties un izslēgt atribūtus sapludināšanai ar vienotā klienta profila entītiju (konfigurācijas procesa rezultāts).</span><span class="sxs-lookup"><span data-stu-id="52c50-110">On the **Merge** page, you choose and exclude attributes to merge within your unified customer profile entity (the result of the configuration process).</span></span> <span data-ttu-id="52c50-111">Dažus atribūtus sistēma sapludina automātiski.</span><span class="sxs-lookup"><span data-stu-id="52c50-111">Some attributes are automatically merged by the system.</span></span>

### <a name="view-merged-attributes"></a><span data-ttu-id="52c50-112">Sapludināto atribūtu skatīšana</span><span class="sxs-lookup"><span data-stu-id="52c50-112">View merged attributes</span></span>

<span data-ttu-id="52c50-113">Lai skatītu atribūtus, kas ir iekļauti kādā no jūsu automātiski sapludinātajiem atribūtiem, atlasiet šo sapludināto atribūtu.</span><span class="sxs-lookup"><span data-stu-id="52c50-113">To view the attributes that are included in one of your automatically merged attributes, select that merged attribute.</span></span> <span data-ttu-id="52c50-114">Šie divi atribūti, kas veido sapludināto atribūtu, tiks parādīti divās jaunās rindās zem sapludinātā atribūta.</span><span class="sxs-lookup"><span data-stu-id="52c50-114">The two attributes that compose that merged attribute display in two new rows beneath the merged attribute.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="52c50-115">![Sapludinātā atribūta atlasīšana](media/configure-data-merge-profile-attributes.png "Sapludinātā atribūta atlasīšana")</span><span class="sxs-lookup"><span data-stu-id="52c50-115">![Select merged attribute](media/configure-data-merge-profile-attributes.png "Select merged attribute")</span></span>

### <a name="separate-merged-attributes"></a><span data-ttu-id="52c50-116">Sapludināto atribūtu atdalīšana</span><span class="sxs-lookup"><span data-stu-id="52c50-116">Separate merged attributes</span></span>

<span data-ttu-id="52c50-117">Lai atdalītu kādu no automātiski sapludinātajiem atribūtiem jeb noņemtu sapludināšanu, atrodiet šo atribūtu tabulā **Profila atribūti**.</span><span class="sxs-lookup"><span data-stu-id="52c50-117">To separate or unmerge any of the automatically merged attributes, find the attribute in the **Profile attributes** table.</span></span>

1. <span data-ttu-id="52c50-118">Atlasiet daudzpunktes (...) pogu.</span><span class="sxs-lookup"><span data-stu-id="52c50-118">Select the ellipsis (...) button.</span></span>
  
2. <span data-ttu-id="52c50-119">Nolaižamajā sarakstā atlasiet **Atsevišķi lauki**.</span><span class="sxs-lookup"><span data-stu-id="52c50-119">In the dropdown list, select **Separate fields**.</span></span>

### <a name="remove-merged-attributes"></a><span data-ttu-id="52c50-120">Sapludināto atribūtu noņemšana</span><span class="sxs-lookup"><span data-stu-id="52c50-120">Remove merged attributes</span></span>

<span data-ttu-id="52c50-121">Lai izslēgtu kādu atribūtu no galīgās klienta profila entītijas, atrodiet šo atribūtu tabulā **Profila atribūti**.</span><span class="sxs-lookup"><span data-stu-id="52c50-121">To exclude an attribute from the final customer profile entity, find it in the **Profile attributes** table.</span></span>

1. <span data-ttu-id="52c50-122">Atlasiet daudzpunktes (...) pogu.</span><span class="sxs-lookup"><span data-stu-id="52c50-122">Select the ellipsis (...) button.</span></span>
  
2. <span data-ttu-id="52c50-123">Nolaižamajā sarakstā atlasiet **Nesapludināt**.</span><span class="sxs-lookup"><span data-stu-id="52c50-123">In the dropdown list, select **Don't merge**.</span></span>

   <span data-ttu-id="52c50-124">Atribūts tiks pārvietots uz sadaļu **Noņemts no klienta ieraksta**.</span><span class="sxs-lookup"><span data-stu-id="52c50-124">The attribute is moved to the **Removed from customer record** section.</span></span>

## <a name="manually-add-a-merged-attribute"></a><span data-ttu-id="52c50-125">Sapludināta atribūta manuāla pievienošana</span><span class="sxs-lookup"><span data-stu-id="52c50-125">Manually add a merged attribute</span></span>

<span data-ttu-id="52c50-126">Lai pievienotu sapludinātu atribūtu, dodieties uz lapu **Sapludināšana**.</span><span class="sxs-lookup"><span data-stu-id="52c50-126">To add a merged attribute, go to the **Merge** page.</span></span>

1. <span data-ttu-id="52c50-127">Atlasiet **Pievienot sapludināto atribūtu**.</span><span class="sxs-lookup"><span data-stu-id="52c50-127">Select **Add merged attribute**.</span></span>

2. <span data-ttu-id="52c50-128">Norādiet **nosaukumu**, lai vēlāk to identificētu lapā **Sapludināšana**.</span><span class="sxs-lookup"><span data-stu-id="52c50-128">Provide a **Name** to identify it on the **Merge** page later.</span></span>

3. <span data-ttu-id="52c50-129">Varat arī norādīt **Parādāmo nosaukumu**, kas parādās vienotajā klienta profila entītijā.</span><span class="sxs-lookup"><span data-stu-id="52c50-129">Optionally, provide a **Display name** to appear in the unified Customer Profile entity.</span></span>

4. <span data-ttu-id="52c50-130">Konfigurējiet opciju **Atribūtu dublikātu atlase**, lai atlasītu atribūtus, ko vēlaties sapludināt no atbilstošajām entītijām.</span><span class="sxs-lookup"><span data-stu-id="52c50-130">Configure **Select duplicate attributes** to select the attributes that you want to merge from the matched entities.</span></span> <span data-ttu-id="52c50-131">Varat arī meklēt atribūtus.</span><span class="sxs-lookup"><span data-stu-id="52c50-131">You can also search for attributes.</span></span>

5. <span data-ttu-id="52c50-132">Iestatiet opciju **Ranžēt pēc svarīguma**, lai noteiktu, ka kādam atribūtam būs augstāka prioritāte nekā citiem atribūtiem.</span><span class="sxs-lookup"><span data-stu-id="52c50-132">Set the **Rank by importance** to prioritize one attribute above the others.</span></span> <span data-ttu-id="52c50-133">Piemēram, ja entītijā *WebAccountCSV* ir ietverti visprecīzākie dati par atribūtu *Full Names*, atlasot *WebAccountCSV*, varat noteikt, ka šai entītijai būs augstāka prioritāte nekā *ContactCSV*.</span><span class="sxs-lookup"><span data-stu-id="52c50-133">For example, if the *WebAccountCSV* entity includes the most accurate data about the *Full Names* attribute, you could prioritize this entity over *ContactCSV* by selecting *WebAccountCSV*.</span></span> <span data-ttu-id="52c50-134">Tā rezultātā, iegūstot vērtības atribūtam *Full Name*, *WebAccountCSV* tiek pārvietots uz pirmo prioritāti, bet *ContactCSV* — uz otro prioritāti.</span><span class="sxs-lookup"><span data-stu-id="52c50-134">As a result, *WebAccountCSV* moves to first priority, while *ContactCSV* moves to second priority when pulling values for the *Full Name* attribute.</span></span>

## <a name="run-your-merge"></a><span data-ttu-id="52c50-135">Sapludināšanas izpilde</span><span class="sxs-lookup"><span data-stu-id="52c50-135">Run your merge</span></span>

<span data-ttu-id="52c50-136">Neatkarīgi no tā, vai manuāli sapludināt atribūtus vai ļaujat tos sapludināt sistēmai, jūs jebkurā gadījumā varat izpildīt sapludināšanu.</span><span class="sxs-lookup"><span data-stu-id="52c50-136">Whether you manually merge attributes or let the system merge them, you can always run your merge.</span></span> <span data-ttu-id="52c50-137">Lapā **Sapludināšana** atlasiet **Izpildīt**, lai sāktu procesu.</span><span class="sxs-lookup"><span data-stu-id="52c50-137">Select **Run** on the **Merge** page to start the process.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="52c50-138">![Datu sapludināšana: saglabāšana un izpilde](media/configure-data-merge-save-run.png "Datu sapludināšana: saglabāšana un izpilde")</span><span class="sxs-lookup"><span data-stu-id="52c50-138">![Data merge Save and Run](media/configure-data-merge-save-run.png "Data merge Save and Run")</span></span>

<span data-ttu-id="52c50-139">Lai veiktu papildu izmaiņas un atkārtoti palaistu darbību, varat atcelt notiekošu sapludināšanu.</span><span class="sxs-lookup"><span data-stu-id="52c50-139">To make additional changes and rerun the step, you can cancel an in-progress merge.</span></span> <span data-ttu-id="52c50-140">Atlasiet **Atsvaidzina...** un atlasiet **Atcelt uzdevumu** blakus rūtī, kas tiek parādīta.</span><span class="sxs-lookup"><span data-stu-id="52c50-140">Select **Refreshing ...** and select **Cancel job**  in the side pane that appears.</span></span>

<span data-ttu-id="52c50-141">Pēc tam, kad teksts **Atsvaidzina...** tiek nomainīts uz **Izdevās**, sapludināšana ir pabeigta un jūsu datu pretrunas ir atrisinātas atbilstoši jūsu definētajām politikām.</span><span class="sxs-lookup"><span data-stu-id="52c50-141">After the **Refreshing ...** text changes to **Successful**, merge has completed and resolved contradictions in your data according to the policies you defined.</span></span> <span data-ttu-id="52c50-142">Sapludinātie un nesapludinātie atribūti ir iekļauti vienotā profila entītijā.</span><span class="sxs-lookup"><span data-stu-id="52c50-142">Merged and unmerged attributes are included in the unified profile entity.</span></span> <span data-ttu-id="52c50-143">Izslēgtie atribūti netiek iekļauti vienotā profila entitījā.</span><span class="sxs-lookup"><span data-stu-id="52c50-143">Excluded attributes aren't included in the unified profile entity.</span></span>

<span data-ttu-id="52c50-144">Ja tā nebija pirmā reize, kad veiksmīgi palaidāt sapludināšanu, visi pakārtotie procesi, tostarp bagātināšana, segmentācija un mērīšana, tiks atkārtoti palaista automātiski.</span><span class="sxs-lookup"><span data-stu-id="52c50-144">If it wasn't the first time you ran a merge successfully, all downstream processes, including enrichment, segmentation, and measures will rerun automatically.</span></span> <span data-ttu-id="52c50-145">Pēc visu pakārtoto procesu atkārtotas palaišanas klientu profili rādīs jebkādas jūsu veiktās izmaiņas.</span><span class="sxs-lookup"><span data-stu-id="52c50-145">After all downstream processes have been rerun, the customer profiles reflect any changes you made.</span></span>

> [!TIP]
> <span data-ttu-id="52c50-146">Uzdevumiem/procesiem ir [seši statusu tipi](system.md#status-types).</span><span class="sxs-lookup"><span data-stu-id="52c50-146">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="52c50-147">Turklāt vairums procesu [ir atkarīgi no citiem pakārtotiem procesiem](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="52c50-147">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="52c50-148">Varat atlasīt procesa statusu, lai skatītu detalizētu informāciju par visa uzdevuma norisi.</span><span class="sxs-lookup"><span data-stu-id="52c50-148">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="52c50-149">Pēc tam, kad vienam no darba uzdevumiem esat atlasījis **Skatīt detalizētu informāciju**, jūs redzēsit papildinformāciju: apstrādes laiku, pēdējās apstrādes datumu un visas kļūdas un brīdinājumus, kas saistīti ar uzdevumu.</span><span class="sxs-lookup"><span data-stu-id="52c50-149">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="52c50-150">Nākamā darbība</span><span class="sxs-lookup"><span data-stu-id="52c50-150">Next Step</span></span>

<span data-ttu-id="52c50-151">Konfigurējiet opcijas [darbības](activities.md), [bagātināšana](enrichment-microsoft-graph.md) vai [relācijas](relationships.md), lai gūtu plašāku ieskatu par saviem klientiem.</span><span class="sxs-lookup"><span data-stu-id="52c50-151">Configure [activities](activities.md), [enrichment](enrichment-microsoft-graph.md), or [relationships](relationships.md) to gain more insights about your customers.</span></span>

<span data-ttu-id="52c50-152">Ja jau esat konfigurējis darbības, bagātināšanu vai relācijas vai definējāt segmentus, tie tiek apstrādāti automātiski, lai izmantotu jaunākos klientu datus.</span><span class="sxs-lookup"><span data-stu-id="52c50-152">If you already configured activities, enrichment, or relationships, or if you defined segments, they'll be processed automatically to use the latest customer data.</span></span>


