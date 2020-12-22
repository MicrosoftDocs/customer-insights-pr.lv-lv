---
title: Mēru izveide un rediģēšana
description: Definējiet ar klientiem saistītus mērus, lai analizētu un atspoguļotu noteiktu uzņēmējdarbības jomu veiktspēju.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: wameng
manager: shellyha
ms.openlocfilehash: 0e214a6eb66abd27f7292db3ce2c2a6e16a8ff33
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406363"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="a6c17-103">Definējiet un pārvaldiet mērus</span><span class="sxs-lookup"><span data-stu-id="a6c17-103">Define and manage measures</span></span>

<span data-ttu-id="a6c17-104">**Mēri** attiecas uz izpildes pamatrādītājiem (KPI), kas atspoguļo noteiktu uzņēmējdarbības jomu veiktspēju un darbības efektivitāti.</span><span class="sxs-lookup"><span data-stu-id="a6c17-104">**Measures** represent key performance indicators (KPIs) that reflect the performance and health of specific business areas.</span></span> <span data-ttu-id="a6c17-105">Auditorijas ieskati nodrošina intuitīvu pieredzi dažādu tipu pasākumu veidošanā, izmantojot vaicājumu veidotāju, kuram nav nepieciešams manuāli piešķirt kodeksu vai validēt pasākumus.</span><span class="sxs-lookup"><span data-stu-id="a6c17-105">Audience insights provides an intuitive experience for building different types of measures, using a query builder that doesn't require you to code or validate your measures manually.</span></span> <span data-ttu-id="a6c17-106">Varat izsekot savus uzņēmējdarbības mērus **sākumlapā**, skatīt konkrētu klientu mērus **klienta kartē** un izmantot mērus klientu segmentu definēšanai lapā **Segmenti**.</span><span class="sxs-lookup"><span data-stu-id="a6c17-106">You can track your business measures on the **Home** page, see measures for specific customers on the **Customer Card**, and use measures to define customer segments on the **Segments** page.</span></span>

## <a name="create-a-measure"></a><span data-ttu-id="a6c17-107">Mēra izveide</span><span class="sxs-lookup"><span data-stu-id="a6c17-107">Create a measure</span></span>

<span data-ttu-id="a6c17-108">Šajā sadaļā ir izklāstīts, kā izveidot mērus no jauna.</span><span class="sxs-lookup"><span data-stu-id="a6c17-108">This section walks you through creating a measure from scratch.</span></span> <span data-ttu-id="a6c17-109">Varat izveidot mērus, izmantojot datus no vairākiem datu avotiem, kas ir saistīti, izmantojot entītiju Klients.</span><span class="sxs-lookup"><span data-stu-id="a6c17-109">You can build measures with data from multiple data sources that are connected through the Customer entity.</span></span> <span data-ttu-id="a6c17-110">Ir [spēkā noteikti pakalpojuma ierobežojumi](service-limits.md).</span><span class="sxs-lookup"><span data-stu-id="a6c17-110">Some [service limits](service-limits.md) apply.</span></span>

1. <span data-ttu-id="a6c17-111">Sadaļā Auditorijas ieskati ejiet uz **Mēri**.</span><span class="sxs-lookup"><span data-stu-id="a6c17-111">In audience insights, go to **Measures**.</span></span>

2. <span data-ttu-id="a6c17-112">Atlasiet **Jauns mērs**.</span><span class="sxs-lookup"><span data-stu-id="a6c17-112">Select **New measure**.</span></span>

3. <span data-ttu-id="a6c17-113">Izvēlieties mēra **tipu**.</span><span class="sxs-lookup"><span data-stu-id="a6c17-113">Choose the measure **Type**:</span></span>

   - <span data-ttu-id="a6c17-114">**Klienta atribūts**: katram klientam ir viens lauks, kurā norādīts klienta rezultāts, vērtība vai statuss.</span><span class="sxs-lookup"><span data-stu-id="a6c17-114">**Customer attribute**: A single field per customer that reflects a score, value, or state for the customer.</span></span> <span data-ttu-id="a6c17-115">Klienta atribūti tiek izveidoti kā atribūti jaunā sistēmas ģenerētajā entītijā, ko sauc **Customer_Measure**.</span><span class="sxs-lookup"><span data-stu-id="a6c17-115">Customer attributes are created as attributes in a new system-generated entity called **Customer_Measure**.</span></span>

   - <span data-ttu-id="a6c17-116">**Klienta mērs**: ieskati par klienta rīcību ar sadalījumu pēc atlasītajām dimensijām.</span><span class="sxs-lookup"><span data-stu-id="a6c17-116">**Customer measure**: Insights on customer behavior with breakdown by selected dimensions.</span></span> <span data-ttu-id="a6c17-117">Katram mēram tiek ģenerēta jauna entītija, iespējams, ar vairākiem ierakstiem katram klientam.</span><span class="sxs-lookup"><span data-stu-id="a6c17-117">A new entity is generated for each measure, potentially with multiple records per customer.</span></span>

   - <span data-ttu-id="a6c17-118">**Uzņēmuma mērs**: izsekojiet sava uzņēmuma veiktspējai un darbības efektivitātei.</span><span class="sxs-lookup"><span data-stu-id="a6c17-118">**Business measure**: Tracks your business performance and health of the business.</span></span> <span data-ttu-id="a6c17-119">Uzņēmuma mēriem var būt divas dažādas izvades: skaitliska izvade, kas tiek parādīta **sākumlapā**, vai jauna entītija, kas atrodama lapā **Entītijas**.</span><span class="sxs-lookup"><span data-stu-id="a6c17-119">Business measures can have two different outputs: a numeric output that shows on the **Home** page or a new entity that you find on the **Entities** page.</span></span>

4. <span data-ttu-id="a6c17-120">Norādiet **nosaukumu** (varat norādīt arī **parādāmo nosaukumu**), pēc tam atlasiet **Tālāk**.</span><span class="sxs-lookup"><span data-stu-id="a6c17-120">Provide a **Name** and an optional **Display name**, then select **Next**.</span></span>

5. <span data-ttu-id="a6c17-121">Sadaļā **Entītijas** atlasiet pirmo ierakstu nolaižamajā sarakstā.</span><span class="sxs-lookup"><span data-stu-id="a6c17-121">In the **Entities** section, select the first entity from the drop-down list.</span></span> <span data-ttu-id="a6c17-122">Šajā brīdī jums ir jāizlemj, vai mēra definēšanai ir nepieciešamas papildu entītijas.</span><span class="sxs-lookup"><span data-stu-id="a6c17-122">At this point, you should decide whether additional entities are needed as part of your measure definition.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a6c17-123">![Mēra definēšana](media/measure-definition.png "Mēra definīcija")</span><span class="sxs-lookup"><span data-stu-id="a6c17-123">![Measure definition](media/measure-definition.png "Measure definition")</span></span>

   <span data-ttu-id="a6c17-124">Lai pievienotu papildu entītijas, atlasiet **Pievienot entītiju** un atlasiet entītijas, ko vēlaties izmantot šim mēram.</span><span class="sxs-lookup"><span data-stu-id="a6c17-124">To add more entities, select **Add entity** and select entities you want to use for the measure.</span></span>

   > [!NOTE]
   > <span data-ttu-id="a6c17-125">Varat atlasīt tikai tās entītijas, kurām ir relācijas ar jūsu sākuma entītiju.</span><span class="sxs-lookup"><span data-stu-id="a6c17-125">You can select only entities that have relationships to your starting entity.</span></span> <span data-ttu-id="a6c17-126">Papildinformāciju par relāciju definēšanu skatiet rakstā [Relācijas](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="a6c17-126">For more information about defining relationships, see [Relationships](relationships.md).</span></span>

6. <span data-ttu-id="a6c17-127">Varat arī konfigurēt mainīgos.</span><span class="sxs-lookup"><span data-stu-id="a6c17-127">Optionally, you can configure variables.</span></span> <span data-ttu-id="a6c17-128">Sadaļā **Mainīgie** atlasiet **Jauns mainīgais**.</span><span class="sxs-lookup"><span data-stu-id="a6c17-128">In the **Variables** section, select **New variable**.</span></span>

   <span data-ttu-id="a6c17-129">Mainīgie ir aprēķini, kas tiek veikti katram no atlasītajiem ierakstiem.</span><span class="sxs-lookup"><span data-stu-id="a6c17-129">Variables are calculations that are made on each of your selected records.</span></span> <span data-ttu-id="a6c17-130">Piemēram, summējot pārdošanas punktu (POS) un pārdošanu tiešsaistē katram jūsu klienta ierakstam.</span><span class="sxs-lookup"><span data-stu-id="a6c17-130">For example, summing point-of-sale (POS) and online sales for each of your customers' records.</span></span>

7. <span data-ttu-id="a6c17-131">Norādiet mainīgā **Nosaukumu**.</span><span class="sxs-lookup"><span data-stu-id="a6c17-131">Provide a **Name** for the variable.</span></span>

8. <span data-ttu-id="a6c17-132">Apgabalā **Izteiksme** izvēlieties lauku, ar kuru sākt aprēķinu.</span><span class="sxs-lookup"><span data-stu-id="a6c17-132">In the **Expression** area, choose a field to begin your calculation with.</span></span>

9. <span data-ttu-id="a6c17-133">Izteiksmes nosaukumu ierakstiet apgabalā **Izteiksme** un izvēlieties papildu laukus iekļaušanai aprēķinā.</span><span class="sxs-lookup"><span data-stu-id="a6c17-133">Type an expression in the **Expression** area while choosing more fields to be included in your calculation.</span></span>

   > [!NOTE]
   > <span data-ttu-id="a6c17-134">Pašlaik tiek atbalstītas tikai aritmētiskas izteiksmes.</span><span class="sxs-lookup"><span data-stu-id="a6c17-134">Currently, only arithmetic expressions are supported.</span></span> <span data-ttu-id="a6c17-135">Turklāt mainīgo aprēķins netiek atbalstīts entītijām no atšķirīgiem [entītiju ceļiem](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="a6c17-135">Additionally, variable calculation isn't supported for entities from different [entity paths](relationships.md).</span></span>

10. <span data-ttu-id="a6c17-136">Atlasiet **Gatavs**.</span><span class="sxs-lookup"><span data-stu-id="a6c17-136">Select **Done**.</span></span>

11. <span data-ttu-id="a6c17-137">Sadaļā **Mēra definēšana** ir jānosaka, kā jūsu izvēlētās entītijas un aprēķinātie mainīgie tiks apkopoti jaunā mēra entītijā vai atribūtā.</span><span class="sxs-lookup"><span data-stu-id="a6c17-137">In the **Measure definition** section, you'll define how your chosen entities and calculated variables are aggregated in a new measure entity or attribute.</span></span>

12. <span data-ttu-id="a6c17-138">Atlasiet **Jauna dimensija**.</span><span class="sxs-lookup"><span data-stu-id="a6c17-138">Select **New dimension**.</span></span> <span data-ttu-id="a6c17-139">Dimensiju var uzskatīt par *grupu pēc* funkcijas.</span><span class="sxs-lookup"><span data-stu-id="a6c17-139">You can think of a dimension as a *group by* function.</span></span> <span data-ttu-id="a6c17-140">Mēra entītijas vai atribūta datu izvade tiks grupēta pēc visām jūsu definētajām dimensijām.</span><span class="sxs-lookup"><span data-stu-id="a6c17-140">The data output of your Measure entity or attribute will be grouped by all of your defined dimensions.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="a6c17-141">![Apkopojuma cikla izvēle](media/measures-businessreport-measure-definition2.png "Apkopojuma cikla izvēle")</span><span class="sxs-lookup"><span data-stu-id="a6c17-141">![Choose aggregate cycle](media/measures-businessreport-measure-definition2.png "Choose aggregate cycle")</span></span>

    <span data-ttu-id="a6c17-142">Definējot dimensijas, atlasiet vai ievadiet tālāk norādītos informāciju.</span><span class="sxs-lookup"><span data-stu-id="a6c17-142">Select or enter the following information as part of your dimension's definition:</span></span>

    - <span data-ttu-id="a6c17-143">**Entītija**: Ja definējat mēra entītiju, tajā ir jābūt vismaz vienam atribūtam.</span><span class="sxs-lookup"><span data-stu-id="a6c17-143">**Entity**: If you define a Measure entity, it should include at least one attribute.</span></span> <span data-ttu-id="a6c17-144">Ja definējat mēra atribūtu, pēc noklusējuma tajā būs tikai viens atribūts.</span><span class="sxs-lookup"><span data-stu-id="a6c17-144">If you define a Measure attribute, it will include only one attribute by default.</span></span> <span data-ttu-id="a6c17-145">Šī atlase ir paredzēta, lai izvēlētos entītiju, kurā ir ietverts šis atribūts.</span><span class="sxs-lookup"><span data-stu-id="a6c17-145">This selection is about choosing the entity that includes that attribute.</span></span>
    - <span data-ttu-id="a6c17-146">**Lauks**: Izvēlieties konkrētu atribūtu, kas tiks iekļauts mēra entītijā, vai atribūtā.</span><span class="sxs-lookup"><span data-stu-id="a6c17-146">**Field**: Choose the specific attribute to be included either in your Measure entity or attribute.</span></span>
    - <span data-ttu-id="a6c17-147">**Intervāls**: Izvēlieties, vai dati tiks apkopoti reizi dienā, mēnesī vai gadā.</span><span class="sxs-lookup"><span data-stu-id="a6c17-147">**Bucket**: Choose whether you want to aggregate data on a daily, monthly, or annual basis.</span></span> <span data-ttu-id="a6c17-148">Tā ir obligāta atlase tikai tad, ja atlasījāt datuma veida atribūtu.</span><span class="sxs-lookup"><span data-stu-id="a6c17-148">It's a required selection only if you've selected a Date type attribute.</span></span>
    - <span data-ttu-id="a6c17-149">**Kā**: definē jaunā lauka nosaukumu.</span><span class="sxs-lookup"><span data-stu-id="a6c17-149">**As**: Defines the name of your new field.</span></span>
    - <span data-ttu-id="a6c17-150">**Parādāmais nosaukums**: Definē lauka parādāmo nosaukumu.</span><span class="sxs-lookup"><span data-stu-id="a6c17-150">**Display name**: Defines the display name of your field.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a6c17-151">Jūsu uzņēmuma mērs tiks saglabāts kā viena skaitļa entītija, un tas tiks parādīts **sākumlapā**, ja vien savam mēram nepievienosiet papildu dimensijas.</span><span class="sxs-lookup"><span data-stu-id="a6c17-151">Your business measure will be saved as a single-number entity and will appear on the **Home** page unless you add more dimensions to your measure.</span></span> <span data-ttu-id="a6c17-152">Pēc papildu dimensiju pievienošanas šis mērs *netiks* parādīts **sākumlapā**.</span><span class="sxs-lookup"><span data-stu-id="a6c17-152">After adding more dimensions, the measure will *not* show up on the **Home** page.</span></span>

13. <span data-ttu-id="a6c17-153">Varat arī pievienot apkopošanas funkcijas.</span><span class="sxs-lookup"><span data-stu-id="a6c17-153">Optionally, add aggregation functions.</span></span> <span data-ttu-id="a6c17-154">Jebkuras veiktās apkopošanas rezultātā tiek iegūta jauna vērtība mēra entītijā vai atribūtā.</span><span class="sxs-lookup"><span data-stu-id="a6c17-154">Any aggregation that you create results in a new value within your Measures entity or attribute.</span></span> <span data-ttu-id="a6c17-155">Atbalstītās apkopošanas funkcijas: **Min**, **Max**, **Average**, **Median**, **Sum**, **Count Unique**, **First** (tiek izmantots pirmais dimensijas vērtības ieraksts) un **Last** (tiek izmantots pēdējais dimensijas vērtībai pievienotais ieraksts).</span><span class="sxs-lookup"><span data-stu-id="a6c17-155">Supported aggregation functions are: **Min**, **Max**, **Average**, **Median**, **Sum**, **Count Unique**, **First** (takes the first record of a dimension value), and **Last** (takes the last record added to a dimension value).</span></span>

14. <span data-ttu-id="a6c17-156">Atlasiet **Saglabāt**, lai lietotu izmaiņas mēram.</span><span class="sxs-lookup"><span data-stu-id="a6c17-156">Select **Save** to apply your changes to the measure.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="a6c17-157">Pārvaldiet savus mērus</span><span class="sxs-lookup"><span data-stu-id="a6c17-157">Manage your measures</span></span>

<span data-ttu-id="a6c17-158">Kad esat izveidojis vismaz vienu pasākumu, lapā **Mēri** tiks atainots pasākumu saraksts.</span><span class="sxs-lookup"><span data-stu-id="a6c17-158">After creating at least one measure, you'll see a list of measures on the **Measures** page.</span></span>

<span data-ttu-id="a6c17-159">Jūs atradīsiet informāciju par mēra tipu, izveidotāju, izveidošanas datumu un laiku, pēdējās rediģēšanas datumu un laiku, statusu (vai mērs ir aktīvs, neaktīvs vai neveiksmīgs) un pēdējās atsvaidzināšanas datumu un laiku.</span><span class="sxs-lookup"><span data-stu-id="a6c17-159">You'll find information about the measure type, the creator, creation date and time, last edit date and time, status (whether the measure is active, inactive, or failed), and last refresh date and time.</span></span> <span data-ttu-id="a6c17-160">Atlasot mēru no saraksta, varat redzēt tā izvades priekšskatījumu.</span><span class="sxs-lookup"><span data-stu-id="a6c17-160">When you select a measure from the list, you can see a preview of its output.</span></span>

<span data-ttu-id="a6c17-161">Lai vienlaikus atsvaidzinātu visus mērus, atlasiet **Atsvaidzināt visu**, neatlasot noteiktu mēru.</span><span class="sxs-lookup"><span data-stu-id="a6c17-161">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a6c17-162">![Darbības, lai pārvaldītu atsevišķus mērus](media/measure-actions.png "Darbības, lai pārvaldītu atsevišķus mērus")</span><span class="sxs-lookup"><span data-stu-id="a6c17-162">![Actions to manage single measures](media/measure-actions.png "Actions to manage single measures")</span></span>

<span data-ttu-id="a6c17-163">Varat arī atlasīt mēru no saraksta un izpildīt vienu no šīm darbībām:</span><span class="sxs-lookup"><span data-stu-id="a6c17-163">Alternatively, select a measure from the list and perform one of the following actions:</span></span>

- <span data-ttu-id="a6c17-164">Atlasiet mēra nosaukumu, lai skatītu tā detalizētu informāciju.</span><span class="sxs-lookup"><span data-stu-id="a6c17-164">Select the measure name to see its details.</span></span>
- <span data-ttu-id="a6c17-165">**Rediģējiet** mēra konfigurāciju.</span><span class="sxs-lookup"><span data-stu-id="a6c17-165">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="a6c17-166">**Pārdēvējiet** mēru. </span><span class="sxs-lookup"><span data-stu-id="a6c17-166">**Rename** the measure.</span></span>
- <span data-ttu-id="a6c17-167">**Dzēsiet** mēru.</span><span class="sxs-lookup"><span data-stu-id="a6c17-167">**Delete** the measure.</span></span>
- <span data-ttu-id="a6c17-168">Atlasiet daudzpunkti (...) un pēc tam **Atsvaidziniet**, lai sāktu mēra atsvaidzināšanas procesu.</span><span class="sxs-lookup"><span data-stu-id="a6c17-168">Select the ellipsis (...) and then **Refresh** to start the refresh process for the measure.</span></span>
- <span data-ttu-id="a6c17-169">Atlasiet daudzpunkti (...) un pēc tam **Lejupielādēt**, lai iegūtu mēra .CSV failu.</span><span class="sxs-lookup"><span data-stu-id="a6c17-169">Select the ellipsis (...) and then **Download** to get a .CSV file of the measure.</span></span>

> [!TIP]
> <span data-ttu-id="a6c17-170">Uzdevumiem/procesiem ir [seši statusu tipi](system.md#status-types).</span><span class="sxs-lookup"><span data-stu-id="a6c17-170">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="a6c17-171">Turklāt vairums procesu [ir atkarīgi no citiem pakārtotiem procesiem](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="a6c17-171">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="a6c17-172">Varat atlasīt procesa statusu, lai skatītu detalizētu informāciju par visa uzdevuma norisi.</span><span class="sxs-lookup"><span data-stu-id="a6c17-172">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="a6c17-173">Pēc tam, kad vienam no darba uzdevumiem esat atlasījis **Skatīt detalizētu informāciju**, jūs redzēsit papildinformāciju: apstrādes laiku, pēdējās apstrādes datumu un visas kļūdas un brīdinājumus, kas saistīti ar uzdevumu.</span><span class="sxs-lookup"><span data-stu-id="a6c17-173">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="a6c17-174">Nākamā darbība</span><span class="sxs-lookup"><span data-stu-id="a6c17-174">Next step</span></span>

<span data-ttu-id="a6c17-175">Esošos mērus varat izmantot, lai izveidotu savu pirmo klientu segmentu lapā **Segmenti**.</span><span class="sxs-lookup"><span data-stu-id="a6c17-175">You cam use existing measures to create your first customer segment on the **Segments** page.</span></span> <span data-ttu-id="a6c17-176">Papildinformāciju skatiet rakstā [Segmenti](segments.md).</span><span class="sxs-lookup"><span data-stu-id="a6c17-176">For more information, see [Segments](segments.md).</span></span>
