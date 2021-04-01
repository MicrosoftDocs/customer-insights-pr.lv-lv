---
title: Izveidojiet un pārvaldiet segmentus
description: Izveidojiet klientiem segmentus, lai tos grupētu, pamatojoties uz dažādiem atribūtiem.
ms.date: 03/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 4a6e8a3216a2c0738d60247054afa9fc18412f55
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597061"
---
# <a name="create-and-manage-segments"></a><span data-ttu-id="17ac0-103">Izveidojiet un pārvaldiet segmentus</span><span class="sxs-lookup"><span data-stu-id="17ac0-103">Create and manage segments</span></span>

<span data-ttu-id="17ac0-104">Segmenti jums ļauj sagrupēt klientus, pamatojoties uz demogrāfiskajiem, transakciju vai uzvedības atribūtiem.</span><span class="sxs-lookup"><span data-stu-id="17ac0-104">Segments let you group your customers based on demographic, transactional, or behavioral attributes.</span></span> <span data-ttu-id="17ac0-105">Lai sasniegtu uzņēmuma mērķus, var izmantot segmentus, lai mērķētu reklāmas kampaņas, pārdošanas darbības un klientu atbalsta darbības.</span><span class="sxs-lookup"><span data-stu-id="17ac0-105">You can use segments to target promotional campaigns, sales activities, and customer support actions to achieve your business goals.</span></span>

<span data-ttu-id="17ac0-106">Varat definēt sarežģītus filtrus ap klienta profila entītiju un to saistītajām entītijām.</span><span class="sxs-lookup"><span data-stu-id="17ac0-106">You can define complex filters around the Customer Profile entity and its related entities.</span></span> <span data-ttu-id="17ac0-107">Katrs segments pēc apstrādes izveido klientu ierakstu kopu, ko var eksportēt un ar kurām veikt darbības.</span><span class="sxs-lookup"><span data-stu-id="17ac0-107">Each segment, after processing, creates a set of customer records that you can export and take action on.</span></span> <span data-ttu-id="17ac0-108">Ir [spēkā noteikti pakalpojuma ierobežojumi](service-limits.md).</span><span class="sxs-lookup"><span data-stu-id="17ac0-108">Some [service limits](service-limits.md) apply.</span></span>

<span data-ttu-id="17ac0-109">Ja vien nav norādīts citādi, visi segmenti ir **dinamiski segmenti**, kas tiek atsvaidzināti periodiskā grafikā.</span><span class="sxs-lookup"><span data-stu-id="17ac0-109">Unless stated otherwise, all segments are **Dynamic segments**, which are refreshed on a recurring schedule.</span></span>

<span data-ttu-id="17ac0-110">Šajā piemērā ir aprakstīta segmentācijas iespēja.</span><span class="sxs-lookup"><span data-stu-id="17ac0-110">The following example illustrates the segmentation capability.</span></span> <span data-ttu-id="17ac0-111">Mēs esam definējuši segmentu klientiem, kuri pēdējo 90 dienu laikā ir pasūtījuši preces vismaz 500$ vērtībā *un* ir bijuši iesaistīti aktualizēta klientu apkalpošanas zvanā.</span><span class="sxs-lookup"><span data-stu-id="17ac0-111">We've defined a segment for customers who ordered at least $500 of goods in the last 90 days *and* who were involved in a customer service call that got escalated.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="17ac0-112">![Vairākas grupas](media/segmentation-group1-2.png "Vairākas grupas")</span><span class="sxs-lookup"><span data-stu-id="17ac0-112">![Multiple groups](media/segmentation-group1-2.png "Multiple groups")</span></span>

## <a name="create-a-new-segment"></a><span data-ttu-id="17ac0-113">Izveidot jaunu segmentu</span><span class="sxs-lookup"><span data-stu-id="17ac0-113">Create a new segment</span></span>

<span data-ttu-id="17ac0-114">Segmenti tiek pārvaldīti lapā **Segmenti**.</span><span class="sxs-lookup"><span data-stu-id="17ac0-114">Segments are managed on the **Segments** page.</span></span>

1. <span data-ttu-id="17ac0-115">Sadaļā Auditorijas ieskati ejiet uz lapu **Segmenti**.</span><span class="sxs-lookup"><span data-stu-id="17ac0-115">In audience insights, go to the **Segments** page.</span></span>

1. <span data-ttu-id="17ac0-116">Atlasiet **Jauns** > **Tukšs segments**.</span><span class="sxs-lookup"><span data-stu-id="17ac0-116">Select **New** > **Blank segment**.</span></span>

1. <span data-ttu-id="17ac0-117">Rūtī **Jauns segments** izvēlieties segmenta tipu un ievadiet **nosaukumu**.</span><span class="sxs-lookup"><span data-stu-id="17ac0-117">In the **New segment** pane, choose a segment type and provide a **Name**.</span></span>

   <span data-ttu-id="17ac0-118">Ja vēlaties, norādiet parādāmo nosaukumu un aprakstu, kas palīdz identificēt segmentu.</span><span class="sxs-lookup"><span data-stu-id="17ac0-118">Optionally, provide a display name, and a description that helps identifying the segment.</span></span>

1. <span data-ttu-id="17ac0-119">Noklikšķiniet uz **Tālāk**, lai piekļūtu lapai **Segmenta veidotājs**, kurā definējat grupu.</span><span class="sxs-lookup"><span data-stu-id="17ac0-119">Select **Next** to get to the **Segment builder** page where you define a group.</span></span> <span data-ttu-id="17ac0-120">Grupa ir klientu kopa.</span><span class="sxs-lookup"><span data-stu-id="17ac0-120">A group is a set of customers.</span></span>

1. <span data-ttu-id="17ac0-121">Izvēlieties entītiju, kurā iekļauts atribūts, pēc kura vēlaties segmentēt.</span><span class="sxs-lookup"><span data-stu-id="17ac0-121">Choose the entity that includes the attribute you want to segment by.</span></span>

1. <span data-ttu-id="17ac0-122">Atlasiet atribūtu, pēc kura segmentēt.</span><span class="sxs-lookup"><span data-stu-id="17ac0-122">Choose the attribute to segment by.</span></span> <span data-ttu-id="17ac0-123">Šim atribūtam var būt viens no četriem vērtību veidiem: skaitlis, virkne, datums vai Būla vērtība.</span><span class="sxs-lookup"><span data-stu-id="17ac0-123">This attribute can have one of four value types: numerical, string, date, or Boolean.</span></span>

1. <span data-ttu-id="17ac0-124">Izvēlieties operatoru un vērtību atlasītajam atribūtam.</span><span class="sxs-lookup"><span data-stu-id="17ac0-124">Choose an operator and a value for the selected attribute.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="17ac0-125">![Pielāgots grupas filtrs](media/customer-group-numbers.png "Klientu grupas filtrs")</span><span class="sxs-lookup"><span data-stu-id="17ac0-125">![Custom group filter](media/customer-group-numbers.png "Customer group filter")</span></span>

   |<span data-ttu-id="17ac0-126">Numurs</span><span class="sxs-lookup"><span data-stu-id="17ac0-126">Number</span></span> |<span data-ttu-id="17ac0-127">Definīcija</span><span class="sxs-lookup"><span data-stu-id="17ac0-127">Definition</span></span>  |
   |---------|---------|
   |<span data-ttu-id="17ac0-128">1</span><span class="sxs-lookup"><span data-stu-id="17ac0-128">1</span></span>     |<span data-ttu-id="17ac0-129">Entītija</span><span class="sxs-lookup"><span data-stu-id="17ac0-129">Entity</span></span>          |
   |<span data-ttu-id="17ac0-130">2</span><span class="sxs-lookup"><span data-stu-id="17ac0-130">2</span></span>     |<span data-ttu-id="17ac0-131">Atribūts</span><span class="sxs-lookup"><span data-stu-id="17ac0-131">Attribute</span></span>          |
   |<span data-ttu-id="17ac0-132">3</span><span class="sxs-lookup"><span data-stu-id="17ac0-132">3</span></span>    |<span data-ttu-id="17ac0-133">Operators</span><span class="sxs-lookup"><span data-stu-id="17ac0-133">Operator</span></span>         |
   |<span data-ttu-id="17ac0-134">4</span><span class="sxs-lookup"><span data-stu-id="17ac0-134">4</span></span>    |<span data-ttu-id="17ac0-135">Vērtība</span><span class="sxs-lookup"><span data-stu-id="17ac0-135">Value</span></span>         |

8. <span data-ttu-id="17ac0-136">Ja entītija ir savienota ar vienotā klienta entītiju, izmantojot [relācijas](relationships.md), ir jādefinē relāciju ceļš, lai izveidotu derīgu segmentu.</span><span class="sxs-lookup"><span data-stu-id="17ac0-136">If the entity is connected to the unified customer entity through [relationships](relationships.md), you need to define the relationship path to create a valid segment.</span></span> <span data-ttu-id="17ac0-137">Pievienojiet entītijas no attiecību ceļa, līdz varat nolaižamajā sarakstā atlasīt entitīju **Klients: CustomerInsights**.</span><span class="sxs-lookup"><span data-stu-id="17ac0-137">Add the entities from the relationship path until you can select the **Customer:CustomerInsights** entity from the dropdown.</span></span> <span data-ttu-id="17ac0-138">Pēc tam katram nosacījumam izvēlieties **Visi ieraksti**.</span><span class="sxs-lookup"><span data-stu-id="17ac0-138">Then, choose **All records** for each condition.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="17ac0-139">![Relāciju ceļš segmenta izveides laikā](media/segments-multiple-relationships.png "Relāciju ceļš segmenta izveides laikā")</span><span class="sxs-lookup"><span data-stu-id="17ac0-139">![Relationship path during segment creation](media/segments-multiple-relationships.png "Relationship path during segment creation")</span></span>

1. <span data-ttu-id="17ac0-140">Pēc noklusējuma segmenti ģenerē izvades entītiju, kurā ir visi klientu profilu atribūti, kas atbilst definētajiem filtriem.</span><span class="sxs-lookup"><span data-stu-id="17ac0-140">By default, segments generate an output entity that contains all attributes of customer profiles which match the defined filters.</span></span> <span data-ttu-id="17ac0-141">Ja segments ir balstīts uz citām entītijām, nevis entītiju *Klients*, izvades entītijai var pievienot papildu atribūtus no šīm entītijām.</span><span class="sxs-lookup"><span data-stu-id="17ac0-141">If a segment is based on other entities than the *Customer* entity, you can add more attributes from these entities to the output entity.</span></span> <span data-ttu-id="17ac0-142">Atlasiet **Projekta atribūtus**, lai izvēlētos atribūtus, kas tiks pievienoti izvades entītijai.</span><span class="sxs-lookup"><span data-stu-id="17ac0-142">Select **Project attributes** to choose the attributes that will be appended to the output entity.</span></span>  

   
   <span data-ttu-id="17ac0-143">Piemērs. Segments tiek veidots, pamatojoties uz entītiju, kurā ir ietverti ar entītiju *Klients* saistīti klienta darbības dati.</span><span class="sxs-lookup"><span data-stu-id="17ac0-143">Example: A segment is based on an entity that contains customer activity data which is related to the *Customer* entity.</span></span> <span data-ttu-id="17ac0-144">Segments meklē visus klientus, kas pēdējo 60 dienu laikā zvanījuši palīdzības dienestam.</span><span class="sxs-lookup"><span data-stu-id="17ac0-144">The segment looks for all customers that called the help desk in the last 60 days.</span></span> <span data-ttu-id="17ac0-145">Varat izvēlēties, vai izvades entītijā pievienot sarunas ilgumu un zvanu skaitu visiem atbilstošajiem klientu ierakstiem.</span><span class="sxs-lookup"><span data-stu-id="17ac0-145">You can choose to append the call duration and the number of calls to all matching customer records in the output entity.</span></span> <span data-ttu-id="17ac0-146">Šī informācija var būt noderīga lai nosūtītu e-pasta ziņojumu ar noderīgām saitēm uz tiešsaistes palīdzības rakstiem un bieži uzdotajiem jautājumiem tiem klientiem, kuri zvanījuši bieži.</span><span class="sxs-lookup"><span data-stu-id="17ac0-146">This information might be useful to send an email with helpful links to online help articles and FAQs to customers who called frequently.</span></span>

1. <span data-ttu-id="17ac0-147">Lai saglabātu segmentu, atlasiet **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="17ac0-147">Select **Save** to save your segment.</span></span> <span data-ttu-id="17ac0-148">Jūsu segments tiks saglabāts un apstrādāts, ja visas prasības ir validētas.</span><span class="sxs-lookup"><span data-stu-id="17ac0-148">Your segment will be saved and processed if all requirements are validated.</span></span> <span data-ttu-id="17ac0-149">Pretējā gadījumā tas tiks saglabāts kā melnraksts.</span><span class="sxs-lookup"><span data-stu-id="17ac0-149">Otherwise, it will be saved as a draft.</span></span>

1. <span data-ttu-id="17ac0-150">Atlasiet **Atgriezties pie segmentiem**, lai atgrieztos pie **Segmentu** lapas.</span><span class="sxs-lookup"><span data-stu-id="17ac0-150">Select **Back to segments** to go back to the **Segments** page.</span></span>

## <a name="manage-existing-segments"></a><span data-ttu-id="17ac0-151">Esošo segmentu pārvaldība</span><span class="sxs-lookup"><span data-stu-id="17ac0-151">Manage existing segments</span></span>

<span data-ttu-id="17ac0-152">Lapā **Segmenti** var apskatīt visus saglabātos segmentus un pārvaldīt tos.</span><span class="sxs-lookup"><span data-stu-id="17ac0-152">On the **Segments** page, you can view all your saved segments and manage them.</span></span>

<span data-ttu-id="17ac0-153">Katru segmentu apzīmē rinda, kurā ir iekļauta papildu informācija par segmentu.</span><span class="sxs-lookup"><span data-stu-id="17ac0-153">Each segment is represented by a row that includes additional information about the segment.</span></span>

<span data-ttu-id="17ac0-154">Segmentus var kārtot kolonnā, atlasot kolonnas virsrakstu.</span><span class="sxs-lookup"><span data-stu-id="17ac0-154">You can sort the segments in a column by selecting the column heading.</span></span>

<span data-ttu-id="17ac0-155">Lai filtrētu segmentus, labajā augšējā stūrī atlasiet lodziņu **Meklēt**.</span><span class="sxs-lookup"><span data-stu-id="17ac0-155">Use the **Search** box in the top-right corner to filter the segments.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="17ac0-156">![Esoša segmenta pārvaldīšanas opcijas](media/segments-selected-segment.png "Esoša segmenta pārvaldīšanas opcijas")</span><span class="sxs-lookup"><span data-stu-id="17ac0-156">![Options to manage an existing segment](media/segments-selected-segment.png "Options to manage an existing segment")</span></span>

<span data-ttu-id="17ac0-157">Kad atlasāt segmentu, ir pieejamas tālāk norādītās darbības:</span><span class="sxs-lookup"><span data-stu-id="17ac0-157">The following action are available when you select a segment:</span></span>

- <span data-ttu-id="17ac0-158">**Skatīt** segmenta informāciju, tostarp segmenta dalībnieku skaita tendences priekšskatījumu.</span><span class="sxs-lookup"><span data-stu-id="17ac0-158">**View** the segment details, including member count trend a preview of segment members.</span></span>
- <span data-ttu-id="17ac0-159">**Rediģēt** segmentu, lai mainītu tā rekvizītus.</span><span class="sxs-lookup"><span data-stu-id="17ac0-159">**Edit** the segment to change its properties.</span></span>
- <span data-ttu-id="17ac0-160">**Izveidot dublikātu** segmentam.</span><span class="sxs-lookup"><span data-stu-id="17ac0-160">**Create duplicate** of a segment.</span></span> <span data-ttu-id="17ac0-161">Varat izvēlēties rediģēt tā rekvizītus uzreiz vai vienkārši saglabāt dublikātu.</span><span class="sxs-lookup"><span data-stu-id="17ac0-161">You can choose to edit its properties right away or simply save the duplicate.</span></span>
- <span data-ttu-id="17ac0-162">**Atsvaidzināt** segmentu, lai iekļautu jaunākos datus.</span><span class="sxs-lookup"><span data-stu-id="17ac0-162">**Refresh** the segment to include the latest data.</span></span>
- <span data-ttu-id="17ac0-163">**Aktivizēt** vai **Deaktivizēt** segmentu.</span><span class="sxs-lookup"><span data-stu-id="17ac0-163">**Activate** or **Deactivate** the segment.</span></span> <span data-ttu-id="17ac0-164">Segmentiem ir divi iespējamie statusi — aktīvs vai neaktīvs.</span><span class="sxs-lookup"><span data-stu-id="17ac0-164">Segments have two possible states - active or inactive.</span></span> <span data-ttu-id="17ac0-165">Šie statusi ir noderīgi, rediģējot segmentu.</span><span class="sxs-lookup"><span data-stu-id="17ac0-165">These states come in handy when editing a segment.</span></span> <span data-ttu-id="17ac0-166">Neaktīvajiem segmentiem pastāv segmenta definīcija, taču tajā vēl nav klientu.</span><span class="sxs-lookup"><span data-stu-id="17ac0-166">For inactive segments, the segment definition exists but it doesn't contain any customers yet.</span></span> <span data-ttu-id="17ac0-167">Aktivizējot segmentu, tā statuss tiek mainīts no “neaktīvs” uz “aktīvs”, un tas sāk meklēt klientus, kas atbilst segmenta definīcijai.</span><span class="sxs-lookup"><span data-stu-id="17ac0-167">When you activate a segment, its state changes from 'inactive' to 'active" and it starts looking for customers that match the segment definition.</span></span> <span data-ttu-id="17ac0-168">Ja ir konfigurēta [plānotā atsvaidzināšana](system.md#schedule-tab), neaktīvajiem segmentiem **Statuss** ir norādīts kā **Izlaists**, kas norāda, ka atsvaidzināšana nav pat mēģināta.</span><span class="sxs-lookup"><span data-stu-id="17ac0-168">If a [scheduled refresh](system.md#schedule-tab) is configured, inactive segments have the **Status** listed as **Skipped**, indicating that a refresh wasn't even attempted.</span></span> <span data-ttu-id="17ac0-169">Ja ir aktivizēts neaktīvs segments, tas tiek atsvaidzināts un iekļauts atsvaidzināšanas grafikā.</span><span class="sxs-lookup"><span data-stu-id="17ac0-169">When an inactive segment is activated, it will refresh and will be included in scheduled refreshes.</span></span>
  <span data-ttu-id="17ac0-170">Vai arī varat izmantot funkcionalitāti **Plānot vēlāk** nolaižamajā izvēlnē **Aktivizēt/Deaktivizēt**, lai norādītu nākotnes datumu un laiku noteikta segmenta aktivizēšanai un deaktivizēšanai.</span><span class="sxs-lookup"><span data-stu-id="17ac0-170">Alternatively, you can use the **Schedule later** functionality in the **Activate/Deactivate** dropdown to specify a future date and time for activation and deactivation of a particular segment.</span></span>
- <span data-ttu-id="17ac0-171">**Pārdēvēt** segmentu.</span><span class="sxs-lookup"><span data-stu-id="17ac0-171">**Rename** the segment.</span></span>
- <span data-ttu-id="17ac0-172">**Lejupielādēt** dalībnieku sarakstu kā .CSV failu.</span><span class="sxs-lookup"><span data-stu-id="17ac0-172">**Download** the list of members as a .CSV file.</span></span>
- <span data-ttu-id="17ac0-173">Opcija **Pievienot** nosūta segmenta klientu ID sarakstu apstrādei citā programmā.</span><span class="sxs-lookup"><span data-stu-id="17ac0-173">**Add to** option sends the list of customer IDs in the segment for processing in another application.</span></span>
- <span data-ttu-id="17ac0-174">**Dzēst** segmentu.</span><span class="sxs-lookup"><span data-stu-id="17ac0-174">**Delete** the segment.</span></span>

## <a name="refresh-segments"></a><span data-ttu-id="17ac0-175">Atsvaidzināt segmentus</span><span class="sxs-lookup"><span data-stu-id="17ac0-175">Refresh segments</span></span>

<span data-ttu-id="17ac0-176">Visus segmentus uzreiz var atsvaidzināt, atlasot **Atsvaidzināt visus** lapā **Segmenti**, vai varat atsvaidzināt vienu vai vairākus segmentus, tos atlasot un izvēloties opciju **Atsvaidzināt** no piedāvātajām opcijām.</span><span class="sxs-lookup"><span data-stu-id="17ac0-176">You can refresh all segments at once by selecting **Refresh all** on the **Segments** page or you can refresh one or multiple segments when you select them and choose **Refresh** in from the options.</span></span> <span data-ttu-id="17ac0-177">Vai arī varat konfigurēt periodisku atsvaidzināšanu sadaļā **Administrators** > **Sistēma** > **Grafiks**.</span><span class="sxs-lookup"><span data-stu-id="17ac0-177">Alternatively, you can configure a recurring refresh on **Admin** > **System** > **Schedule**.</span></span>

> [!TIP]
> <span data-ttu-id="17ac0-178">Uzdevumiem/procesiem ir [seši statusu tipi](system.md#status-types).</span><span class="sxs-lookup"><span data-stu-id="17ac0-178">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="17ac0-179">Turklāt vairums procesu [ir atkarīgi no citiem pakārtotiem procesiem](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="17ac0-179">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="17ac0-180">Varat atlasīt procesa statusu, lai skatītu detalizētu informāciju par visa uzdevuma norisi.</span><span class="sxs-lookup"><span data-stu-id="17ac0-180">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="17ac0-181">Pēc tam, kad vienam no darba uzdevumiem esat atlasījis **Skatīt detalizētu informāciju**, jūs redzēsit papildinformāciju: apstrādes laiku, pēdējās apstrādes datumu un visas kļūdas un brīdinājumus, kas saistīti ar uzdevumu.</span><span class="sxs-lookup"><span data-stu-id="17ac0-181">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="download-and-export-segments"></a><span data-ttu-id="17ac0-182">Segmentu lejupielāde un eksportēšana</span><span class="sxs-lookup"><span data-stu-id="17ac0-182">Download and export segments</span></span>

<span data-ttu-id="17ac0-183">Varat lejupielādēt segmentus CSV failā vai tos eksportēt uz Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="17ac0-183">You can download your segments to a CSV file or export them to Dynamics 365 Sales.</span></span>

### <a name="download-segments-to-a-csv-file"></a><span data-ttu-id="17ac0-184">Segmentu lejupielāde CSV failā</span><span class="sxs-lookup"><span data-stu-id="17ac0-184">Download segments to a CSV file</span></span>

1. <span data-ttu-id="17ac0-185">Sadaļā Auditorijas ieskati ejiet uz lapu **Segmenti**.</span><span class="sxs-lookup"><span data-stu-id="17ac0-185">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="17ac0-186">Noteiktā segmenta elementā atlasiet daudzpunkti.</span><span class="sxs-lookup"><span data-stu-id="17ac0-186">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="17ac0-187">Nolaižamajā darbību sarakstā atlasiet **Lejupielādēt kā CSV**.</span><span class="sxs-lookup"><span data-stu-id="17ac0-187">Select **Download as CSV** from the actions drop-down list.</span></span>

### <a name="export-segments-to-dynamics-365-sales"></a><span data-ttu-id="17ac0-188">Segmentu eksportēšana programmā Dynamics 365 Sales</span><span class="sxs-lookup"><span data-stu-id="17ac0-188">Export segments to Dynamics 365 Sales</span></span>

<span data-ttu-id="17ac0-189">Pirms segmentu eksportēšanas programmā Dynamics 365 Sales, administratoram ir [jāizveido eksportēšanas galamērķis](export-destinations.md) programmai Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="17ac0-189">Before exporting segments to Dynamics 365 Sales, an admin needs to [create the export destination](export-destinations.md) for Dynamics 365 Sales.</span></span>

1. <span data-ttu-id="17ac0-190">Sadaļā Auditorijas ieskati ejiet uz lapu **Segmenti**.</span><span class="sxs-lookup"><span data-stu-id="17ac0-190">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="17ac0-191">Noteiktā segmenta elementā atlasiet daudzpunkti.</span><span class="sxs-lookup"><span data-stu-id="17ac0-191">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="17ac0-192">Darbību nolaižamajā sarakstā atlasiet **Pievienot** un atlasiet eksporta galamērķi, uz kuru vēlaties nosūtīt datus.</span><span class="sxs-lookup"><span data-stu-id="17ac0-192">Select **Add to** from the actions drop-down list and select the export destination you want to send the data to.</span></span>

## <a name="draft-mode-for-segments"></a><span data-ttu-id="17ac0-193">Melnraksta režīms segmentiem</span><span class="sxs-lookup"><span data-stu-id="17ac0-193">Draft mode for segments</span></span>

<span data-ttu-id="17ac0-194">Ja netiek izpildītas visas segmenta apstrādes prasības, segmentu var saglabāt kā melnrakstu, lai to varētu izmantot lapā **Segmenti**.</span><span class="sxs-lookup"><span data-stu-id="17ac0-194">If not all requirements to process a segment are met, you can save the segment as a draft and access it from the **Segments** page.</span></span>

<span data-ttu-id="17ac0-195">Tas tiks saglabāts kā neaktīvs segments, un to nevar aktivizēt, kamēr tas nav derīgs.</span><span class="sxs-lookup"><span data-stu-id="17ac0-195">It will be saved as an inactive segment, and can't be activated it until it's valid.</span></span>

## <a name="add-more-conditions-to-a-group"></a><span data-ttu-id="17ac0-196">Papildu nosacījumu pievienošana grupai</span><span class="sxs-lookup"><span data-stu-id="17ac0-196">Add more conditions to a group</span></span>

<span data-ttu-id="17ac0-197">Lai grupai pievienotu papildu nosacījumus, varat izmantot divus loģiskos operatorus:</span><span class="sxs-lookup"><span data-stu-id="17ac0-197">To add more conditions to a group, you can use two logical operators:</span></span>

- <span data-ttu-id="17ac0-198">**UN** operators: Ir jāizpilda abi nosacījumi kā daļa no segmentācijas procesa.</span><span class="sxs-lookup"><span data-stu-id="17ac0-198">**AND** operator: Both conditions must be met as part of the segmentation process.</span></span> <span data-ttu-id="17ac0-199">Šī opcija ir visnoderīgākā, kad definējat nosacījumus dažādās entītijās.</span><span class="sxs-lookup"><span data-stu-id="17ac0-199">This option is most useful when you define conditions across different entities.</span></span>

- <span data-ttu-id="17ac0-200">**Vai** operators: Viens vai otrs no nosacījumiem ir jāizpilda kā segmentācijas procesa daļa.</span><span class="sxs-lookup"><span data-stu-id="17ac0-200">**OR** operator: Either one of the conditions needs to be met as part of the segmentation process.</span></span> <span data-ttu-id="17ac0-201">Šī opcija ir visnoderīgākā, kad definējat vairākus nosacījumus vienai entītijai.</span><span class="sxs-lookup"><span data-stu-id="17ac0-201">This option is most useful when you define multiple conditions for the same entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="17ac0-202">![VAI operators, ja kāds no nosacījumiem ir jāizpilda](media/segmentation-either-condition.png "VAI operators, ja kāds no nosacījumiem ir jāizpilda")</span><span class="sxs-lookup"><span data-stu-id="17ac0-202">![OR operator where either condition needs to be met](media/segmentation-either-condition.png "OR operator where either condition needs to be met")</span></span>

<span data-ttu-id="17ac0-203">Pašlaik ir iespējams ligzdot **VAI** operatoru, izmantojot operatoru **UN**, bet ne otrādi.</span><span class="sxs-lookup"><span data-stu-id="17ac0-203">It's currently possible to nest an **OR** operator under an **AND** operator, but not the other way around.</span></span>

## <a name="combine-multiple-groups"></a><span data-ttu-id="17ac0-204">Vairāku grupu apvienošana</span><span class="sxs-lookup"><span data-stu-id="17ac0-204">Combine multiple groups</span></span>

<span data-ttu-id="17ac0-205">Katra grupa veido noteiktu klientu kopu.</span><span class="sxs-lookup"><span data-stu-id="17ac0-205">Each group produces a specific set of customers.</span></span> <span data-ttu-id="17ac0-206">Varat apvienot šīs grupas, lai tās iekļautu jūsu biznesa pieteikumam nepieciešamos klientus.</span><span class="sxs-lookup"><span data-stu-id="17ac0-206">You can combine these groups to include the customers required for your business case.</span></span>

1. <span data-ttu-id="17ac0-207">Sadaļā auditorijas ieskati atveriet lapu **Segmenti** un atlasiet segmentu.</span><span class="sxs-lookup"><span data-stu-id="17ac0-207">In audience insights, go to the **Segments** page and select a segment.</span></span>

2. <span data-ttu-id="17ac0-208">Atlasiet **Pievienot grupu**.</span><span class="sxs-lookup"><span data-stu-id="17ac0-208">Select **Add Group**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="17ac0-209">![Klientu grupu pievienošanas grupa](media/customer-group-add-group.png "Klientu grupu pievienošanas grupa")</span><span class="sxs-lookup"><span data-stu-id="17ac0-209">![Customer group add group](media/customer-group-add-group.png "Customer group add group")</span></span>

3. <span data-ttu-id="17ac0-210">Atlasiet vienu no tālāk minētajiem kopu operatoriem: **Savienība**, **Pārklāšanās** vai **Atskaitīšana**.</span><span class="sxs-lookup"><span data-stu-id="17ac0-210">Select one of the following set operators: **Union**, **Intersect**, or **Except**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="17ac0-211">![Klientu grupu pievienošanas apvienošana](media/customer-group-union.png "Klientu grupu pievienošanas apvienošana")</span><span class="sxs-lookup"><span data-stu-id="17ac0-211">![Customer group add union](media/customer-group-union.png "Customer group add union")</span></span>

   <span data-ttu-id="17ac0-212">Atlasiet iestatīto operatoru, lai definētu jaunu grupu.</span><span class="sxs-lookup"><span data-stu-id="17ac0-212">Select a set operator to define a new group.</span></span> <span data-ttu-id="17ac0-213">Saglabājiet dažādas grupas, lai noteiktu, kādus datus uzturēt:</span><span class="sxs-lookup"><span data-stu-id="17ac0-213">Save different groups to determine what data gets retained:</span></span>

   - <span data-ttu-id="17ac0-214">**Apvienot** apvieno divas grupas.</span><span class="sxs-lookup"><span data-stu-id="17ac0-214">**Union** unites the two groups.</span></span>

   - <span data-ttu-id="17ac0-215">**Izveidot krustpunktu** pārklāj divas grupas.</span><span class="sxs-lookup"><span data-stu-id="17ac0-215">**Intersect** overlaps the two groups.</span></span> <span data-ttu-id="17ac0-216">Vienotajā grupā tiek saglabāti tikai tie dati, kas ir *kopēji* abām grupām.</span><span class="sxs-lookup"><span data-stu-id="17ac0-216">Only data that *is common* to both groups is retained in the unified group.</span></span>

   - <span data-ttu-id="17ac0-217">**Izņemot** apvieno divas grupas.</span><span class="sxs-lookup"><span data-stu-id="17ac0-217">**Except** combines the two groups.</span></span> <span data-ttu-id="17ac0-218">Tiek saglabāti tikai A grupas dati, kas *nav kopēji* B grupas datiem.</span><span class="sxs-lookup"><span data-stu-id="17ac0-218">Only data in group A that *is not common* to data in group B is retained.</span></span>

## <a name="view-processing-history-and-segment-members"></a><span data-ttu-id="17ac0-219">Apstrādes vēstures un segmentu elementu skatīšana</span><span class="sxs-lookup"><span data-stu-id="17ac0-219">View processing history and segment members</span></span>

<span data-ttu-id="17ac0-220">Lai skatītu apkopotos datus par segmentu, pārskatot informāciju par segmentu.</span><span class="sxs-lookup"><span data-stu-id="17ac0-220">You can see consolidated data about a segment by reviewing its details.</span></span>

<span data-ttu-id="17ac0-221">Lapā **Segmenti** atlasiet segmentu, kuru vēlaties pārskatīt.</span><span class="sxs-lookup"><span data-stu-id="17ac0-221">On the **Segments** page, select the segment you want to review.</span></span>

<span data-ttu-id="17ac0-222">Lapas augšējā daļa ietver tendenču grafiku, kas vizualizē elementu skaita izmaiņas.</span><span class="sxs-lookup"><span data-stu-id="17ac0-222">The upper part of the page includes a trend graph that visualizes changes in member count.</span></span> <span data-ttu-id="17ac0-223">Norādiet uz datu punktiem, lai skatītu elementu skaitu noteiktā datumā.</span><span class="sxs-lookup"><span data-stu-id="17ac0-223">Hover over data points to see the member count on a specific date.</span></span>

<span data-ttu-id="17ac0-224">Varat atjaunināt vizualizācijas laika periodu.</span><span class="sxs-lookup"><span data-stu-id="17ac0-224">You can update the time frame of the visualization.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="17ac0-225">![Segmenta laika diapazons](media/segment-time-range.png "Segmenta laika diapazons")</span><span class="sxs-lookup"><span data-stu-id="17ac0-225">![Segment time range](media/segment-time-range.png "Segment time range")</span></span>

<span data-ttu-id="17ac0-226">Apakšējā daļa ietver segmenta elementu sarakstu.</span><span class="sxs-lookup"><span data-stu-id="17ac0-226">The lower part contains a list of the segment members.</span></span>

> [!NOTE]
> <span data-ttu-id="17ac0-227">Šajā sarakstā parādītie lauki tiek balstīti uz segmenta entītiju atribūtiem.</span><span class="sxs-lookup"><span data-stu-id="17ac0-227">Fields that appear in this list are based on the attributes of your segment's entities.</span></span>
>
><span data-ttu-id="17ac0-228">Saraksts ir atbilstošo segmenta dalībnieku priekšskatījums un parāda jūsu segmenta pirmos 100 ierakstus, lai to varētu ātri novērtēt un vajadzības gadījumā pārskatīt tā definīcijas.</span><span class="sxs-lookup"><span data-stu-id="17ac0-228">The list is a preview of the matching segment members and shows the first 100 records of your segment so that you can quickly evaluate it and review its definitions if needed.</span></span> <span data-ttu-id="17ac0-229">Lai skatītu visus atbilstošos ierakstus, ir [jāeksportē šis segments](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="17ac0-229">To see all matching records, you need to [export the segment](export-destinations.md).</span></span>

## <a name="quick-segments"></a><span data-ttu-id="17ac0-230">Ātrie segmenti</span><span class="sxs-lookup"><span data-stu-id="17ac0-230">Quick segments</span></span>

<span data-ttu-id="17ac0-231">Papildus segmenta veidotājam ir vēl viens segmentu izveides ceļš.</span><span class="sxs-lookup"><span data-stu-id="17ac0-231">In addition to the segment builder, there's another path for creating segments.</span></span> <span data-ttu-id="17ac0-232">Ātrie segmenti ļauj veidot vienkāršus segmentus (ar vienu operatoru) ātri un ar tūlītējiem ieskatiem.</span><span class="sxs-lookup"><span data-stu-id="17ac0-232">Quick segments let you build simple segments with a single operator quickly and with instant insights.</span></span>

1. <span data-ttu-id="17ac0-233">Lapā **Segmenti** atlasiet vienumu **Jauns** > **Ātri izveidot no**.</span><span class="sxs-lookup"><span data-stu-id="17ac0-233">On the **Segments** page, select **New** > **Quickly create from**.</span></span>

   - <span data-ttu-id="17ac0-234">Atlasiet opciju **Profili**, lai izveidotu segmentu, kura pamatā ir vienotā klienta entītija.</span><span class="sxs-lookup"><span data-stu-id="17ac0-234">Select the **Profiles** option to build a segment that is based on the unified Customer entity.</span></span>
   - <span data-ttu-id="17ac0-235">Atlasiet opciju **Pasākumi**, lai izveidotu segmentu ap katru klientu atribūtu tipu pasākumiem, kas iepriekš izveidoti lapā **Pasākumi**.</span><span class="sxs-lookup"><span data-stu-id="17ac0-235">Select the **Measures** option to build a segment around each of the Customer Attribute type of measures you have previously created on the **Measures** page.</span></span>
   - <span data-ttu-id="17ac0-236">Atlasiet opciju **Informācijas apkopošana**, lai izveidotu segmentu ap vienu no izvades entitījām, kuras izveidojāt, izmantojot iespēju **Prognozes** vai **Pielāgotie modeļi**.</span><span class="sxs-lookup"><span data-stu-id="17ac0-236">Select the **Intelligence** option to build a segment around one of the output entities you generated using either the **Predictions** or **Custom Models** capabilities.</span></span>

2. <span data-ttu-id="17ac0-237">Dialoglodziņā **Jauns ātrais segments** atlasiet atribūtu no nolaižamā saraksta **Lauks**.</span><span class="sxs-lookup"><span data-stu-id="17ac0-237">In the **New quick segment** dialog box, select an attribute from the **Field** dropdown.</span></span>

3. <span data-ttu-id="17ac0-238">Sistēma sniegs papildu ieskatus, kas palīdz izveidot labākus klientu segmentus.</span><span class="sxs-lookup"><span data-stu-id="17ac0-238">The system will provide some additional insights that help you create better segments of your customers.</span></span>
   - <span data-ttu-id="17ac0-239">Attiecībā uz kategoriju laukiem mēs parādīsim 10 lielāko klientu skaitu.</span><span class="sxs-lookup"><span data-stu-id="17ac0-239">For categorical fields, we'll show 10 top customer counts.</span></span> <span data-ttu-id="17ac0-240">Izvēlieties **Vērtība** un atlasiet **Pārskatīt**.</span><span class="sxs-lookup"><span data-stu-id="17ac0-240">Choose a **Value** and select **Review**.</span></span>

   - <span data-ttu-id="17ac0-241">Skaitliskam atribūtam sistēma parādīs, kāda atribūta vērtība atbilst katra klienta procentīlei.</span><span class="sxs-lookup"><span data-stu-id="17ac0-241">For a numerical attribute, the system will show what attribute value falls under each customer's percentile.</span></span> <span data-ttu-id="17ac0-242">Izvēlieties **Operators** un **Vērtība** un pēc tam atlasiet vienumu **Pārskatīt**.</span><span class="sxs-lookup"><span data-stu-id="17ac0-242">Choose an **Operator** and a **Value**, then select **Review**.</span></span>

4. <span data-ttu-id="17ac0-243">Sistēma nodrošinās jūs ar **Aptuveniem segmenta izmēriem**.</span><span class="sxs-lookup"><span data-stu-id="17ac0-243">The system will provide you with an **Estimated segment size**.</span></span> <span data-ttu-id="17ac0-244">Varat izvēlēties, vai ģenerēt definēto segmentu, vai arī to vispirms pārskatīt, lai iegūtu citu segmenta lielumu.</span><span class="sxs-lookup"><span data-stu-id="17ac0-244">You can choose whether to generate the segment you've defined, or first revisit it to get a different segment size.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="17ac0-245">![Ātrā segmenta nosaukums un novērtējums](media/quick-segment-name.png "Ātrā segmenta nosaukums un novērtējums")</span><span class="sxs-lookup"><span data-stu-id="17ac0-245">![Name and estimation for a quick segment](media/quick-segment-name.png "Name and estimation for a quick segment")</span></span>

5. <span data-ttu-id="17ac0-246">Norādiet segmenta **Nosaukumu**.</span><span class="sxs-lookup"><span data-stu-id="17ac0-246">Provide a **Name** for your segment.</span></span> <span data-ttu-id="17ac0-247">Vai ari norādiet **Parādāmo vārdu**.</span><span class="sxs-lookup"><span data-stu-id="17ac0-247">Optionally, provide a **Display name**.</span></span>

6. <span data-ttu-id="17ac0-248">Lai izveidotu segmentu, atlasiet opciju **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="17ac0-248">Select **Save** to create your segment.</span></span>

7. <span data-ttu-id="17ac0-249">Pēc tam, kad segments ir pabeidzis apstrādi, to var apskatīt tāpat kā jebkuru citu izveidoto segmentu.</span><span class="sxs-lookup"><span data-stu-id="17ac0-249">After the segment has finished processing, you can view it like any other segment you've created.</span></span>

<span data-ttu-id="17ac0-250">Tālāk norādītajiem scenārijiem ieteicams izmantot segmentu veidotāju, nevis ieteikto segmentu iespējas:</span><span class="sxs-lookup"><span data-stu-id="17ac0-250">For the following scenarios, we advise using the segment builder rather than the recommended segments capability:</span></span>

- <span data-ttu-id="17ac0-251">Segmentu izveide ar filtriem kategoriskos laukos, kuros operators ir citādāks nekā **Ir**.</span><span class="sxs-lookup"><span data-stu-id="17ac0-251">Creating segments with filters on categorical fields where the operator is different than the **Is** operator</span></span>
- <span data-ttu-id="17ac0-252">Segmentu izveide, izmantojot filtrus skaitliskos laukos kuros operators ir atšķirīgs no **Starp**, **Lielāks par** un **Mazāks par** operatoriem.</span><span class="sxs-lookup"><span data-stu-id="17ac0-252">Creating segments with filters on numerical fields where the operator is different than the **Between**, **Greater than**, and **Less than** operators</span></span>
- <span data-ttu-id="17ac0-253">Segmentu izveide ar filtriem datuma veida laukos</span><span class="sxs-lookup"><span data-stu-id="17ac0-253">Creating segments with filters on date type fields</span></span>

## <a name="next-steps"></a><span data-ttu-id="17ac0-254">Nākamās darbības</span><span class="sxs-lookup"><span data-stu-id="17ac0-254">Next steps</span></span>

<span data-ttu-id="17ac0-255">[Eksportējiet segmentu](export-destinations.md) un izpētiet [Klienta karti](customer-card-add-in.md) un [Savienotājus](export-power-bi.md), lai gūtu ieskatu klientu līmenī.</span><span class="sxs-lookup"><span data-stu-id="17ac0-255">[Export a segment](export-destinations.md) and explore the [Customer Card](customer-card-add-in.md) and [Connectors](export-power-bi.md) to get insights on the customer level.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]