---
title: Izveidojiet un pārvaldiet segmentus
description: Izveidojiet klientiem segmentus, lai tos grupētu, pamatojoties uz dažādiem atribūtiem.
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 550e509a24701fe5fcdeb9d54311872dc954156c
ms.sourcegitcommit: 72603fb39c4d5dbca71128815a2e1692542ea4dc
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 05/19/2021
ms.locfileid: "6064946"
---
# <a name="create-and-manage-segments"></a><span data-ttu-id="f1af2-103">Izveidojiet un pārvaldiet segmentus</span><span class="sxs-lookup"><span data-stu-id="f1af2-103">Create and manage segments</span></span>

<span data-ttu-id="f1af2-104">Definēt sarežģītus filtrus vienotā klienta entītijā unsaistītajās entītijās.</span><span class="sxs-lookup"><span data-stu-id="f1af2-104">Define complex filters around the unified customer entity and its related entities.</span></span> <span data-ttu-id="f1af2-105">Katrs segments pēc apstrādes izveido klientu ierakstu kopu, ko var eksportēt un ar kurām veikt darbības.</span><span class="sxs-lookup"><span data-stu-id="f1af2-105">Each segment, after processing, creates a set of customer records that you can export and take action on.</span></span> <span data-ttu-id="f1af2-106">Segmenti tiek pārvaldīti lapā **Segmenti**.</span><span class="sxs-lookup"><span data-stu-id="f1af2-106">Segments are managed on the **Segments** page.</span></span> 

<span data-ttu-id="f1af2-107">Šajā piemērā ir aprakstīta segmentācijas iespēja.</span><span class="sxs-lookup"><span data-stu-id="f1af2-107">The following example illustrates the segmentation capability.</span></span> <span data-ttu-id="f1af2-108">Mēs esam definējuši segmentu klientiem, kuri pēdējo 90 dienu laikā ir pasūtījuši preces vismaz 500$ vērtībā *un* ir bijuši iesaistīti aktualizēta klientu apkalpošanas zvanā.</span><span class="sxs-lookup"><span data-stu-id="f1af2-108">We've defined a segment for customers who ordered at least $500 of goods in the last 90 days *and* who were involved in a customer service call that got escalated.</span></span>

:::image type="content" source="media/segmentation-group1-2.png" alt-text="Segmenta būvēšanas UI ekrānuzņēmums, kurā ir divas grupas, kurās norādīts klienta segments.":::

## <a name="create-a-new-segment"></a><span data-ttu-id="f1af2-110">Izveidot jaunu segmentu</span><span class="sxs-lookup"><span data-stu-id="f1af2-110">Create a new segment</span></span>

<span data-ttu-id="f1af2-111">Ir vairāki jauna segmenta izveides veidi.</span><span class="sxs-lookup"><span data-stu-id="f1af2-111">There are multiple ways to create a new segment.</span></span> <span data-ttu-id="f1af2-112">Šajā sadaļā ir aprakstīts, kā izveidot *tukšu segmentu* no jauna.</span><span class="sxs-lookup"><span data-stu-id="f1af2-112">This section describes how to create a *blank segment* from scratch.</span></span> <span data-ttu-id="f1af2-113">Var arī izveidot *ātro segmentu*, balstoties uz esošām entītijām, vai izmantot algoritmiskā mācīšanās modeļus, lai iegūtu *ieteiktos segmentus*.</span><span class="sxs-lookup"><span data-stu-id="f1af2-113">You can also create a *quick segment* based on existing entities or make use of machine learning models to get *suggested segments*.</span></span> <span data-ttu-id="f1af2-114">Papildinformācija: [Pārskats par segmentiem](segments.md).</span><span class="sxs-lookup"><span data-stu-id="f1af2-114">More information: [Segments overview](segments.md).</span></span>

<span data-ttu-id="f1af2-115">Veidojot segmentu, var saglabāt melnrakstu.</span><span class="sxs-lookup"><span data-stu-id="f1af2-115">While creating a segment, you can save a draft.</span></span> <span data-ttu-id="f1af2-116">Tas tiks saglabāts kā neaktīvs segments, un to nevar aktivizēt, un tā ir pabeigta, izmantojot derīgu konfigurāciju.</span><span class="sxs-lookup"><span data-stu-id="f1af2-116">It will be saved as an inactive segment, and can't be activated it finished with a valid configuration.</span></span>

1. <span data-ttu-id="f1af2-117">Doties uz lapu **Segmenti**.</span><span class="sxs-lookup"><span data-stu-id="f1af2-117">Go to the **Segments** page.</span></span>

1. <span data-ttu-id="f1af2-118">Atlasiet **Jauns** > **Tukšs segments**.</span><span class="sxs-lookup"><span data-stu-id="f1af2-118">Select **New** > **Blank segment**.</span></span>

1. <span data-ttu-id="f1af2-119">**Jaunā segmenta** rūtī izvēlieties segmenta tipu:</span><span class="sxs-lookup"><span data-stu-id="f1af2-119">In the **New segment** pane, choose a segment type:</span></span>

   - <span data-ttu-id="f1af2-120">**Dinamiski segmenti** [tiek atsvaidzināti](segments.md#refresh-segments) pēc periodiska grafika.</span><span class="sxs-lookup"><span data-stu-id="f1af2-120">**Dynamic segments** [refresh](segments.md#refresh-segments) on a recurring schedule.</span></span>
   - <span data-ttu-id="f1af2-121">**Statiskie segmenti** tiek rādīti vienreiz, tos izveidojot.</span><span class="sxs-lookup"><span data-stu-id="f1af2-121">**Static segments** run once when you create it.</span></span>

1. <span data-ttu-id="f1af2-122">Norādiet segmenta **Izvades entītijas nosaukumu**.</span><span class="sxs-lookup"><span data-stu-id="f1af2-122">Provide an **Output entity name** for the segment.</span></span> <span data-ttu-id="f1af2-123">Ja vēlaties, norādiet parādāmo nosaukumu un aprakstu, kas palīdz identificēt segmentu.</span><span class="sxs-lookup"><span data-stu-id="f1af2-123">Optionally, provide a display name, and a description that helps identifying the segment.</span></span>

1. <span data-ttu-id="f1af2-124">Noklikšķiniet uz **Tālāk**, lai piekļūtu lapai **Segmenta veidotājs**, kurā definējat grupu.</span><span class="sxs-lookup"><span data-stu-id="f1af2-124">Select **Next** to get to the **Segment builder** page where you define a group.</span></span> <span data-ttu-id="f1af2-125">Grupa ir klientu kopa.</span><span class="sxs-lookup"><span data-stu-id="f1af2-125">A group is a set of customers.</span></span>

1. <span data-ttu-id="f1af2-126">Izvēlieties entītiju, kurā iekļauts atribūts, pēc kura vēlaties segmentēt.</span><span class="sxs-lookup"><span data-stu-id="f1af2-126">Choose the entity that includes the attribute you want to segment by.</span></span>

1. <span data-ttu-id="f1af2-127">Atlasiet atribūtu, pēc kura segmentēt.</span><span class="sxs-lookup"><span data-stu-id="f1af2-127">Choose the attribute to segment by.</span></span> <span data-ttu-id="f1af2-128">Šim atribūtam var būt viens no četriem vērtību veidiem: skaitlis, virkne, datums vai Būla vērtība.</span><span class="sxs-lookup"><span data-stu-id="f1af2-128">This attribute can have one of four value types: numerical, string, date, or Boolean.</span></span>

1. <span data-ttu-id="f1af2-129">Izvēlieties operatoru un vērtību atlasītajam atribūtam.</span><span class="sxs-lookup"><span data-stu-id="f1af2-129">Choose an operator and a value for the selected attribute.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f1af2-130">![Pielāgots grupas filtrs](media/customer-group-numbers.png "Klientu grupas filtrs")</span><span class="sxs-lookup"><span data-stu-id="f1af2-130">![Custom group filter](media/customer-group-numbers.png "Customer group filter")</span></span>

   |<span data-ttu-id="f1af2-131">Skaitlis</span><span class="sxs-lookup"><span data-stu-id="f1af2-131">Number</span></span> |<span data-ttu-id="f1af2-132">Definīcija</span><span class="sxs-lookup"><span data-stu-id="f1af2-132">Definition</span></span>  |
   |---------|---------|
   |<span data-ttu-id="f1af2-133">1</span><span class="sxs-lookup"><span data-stu-id="f1af2-133">1</span></span>     |<span data-ttu-id="f1af2-134">Elements</span><span class="sxs-lookup"><span data-stu-id="f1af2-134">Entity</span></span>          |
   |<span data-ttu-id="f1af2-135">2</span><span class="sxs-lookup"><span data-stu-id="f1af2-135">2</span></span>     |<span data-ttu-id="f1af2-136">Atribūts</span><span class="sxs-lookup"><span data-stu-id="f1af2-136">Attribute</span></span>          |
   |<span data-ttu-id="f1af2-137">3</span><span class="sxs-lookup"><span data-stu-id="f1af2-137">3</span></span>    |<span data-ttu-id="f1af2-138">Operators</span><span class="sxs-lookup"><span data-stu-id="f1af2-138">Operator</span></span>         |
   |<span data-ttu-id="f1af2-139">4</span><span class="sxs-lookup"><span data-stu-id="f1af2-139">4</span></span>    |<span data-ttu-id="f1af2-140">Vērtība</span><span class="sxs-lookup"><span data-stu-id="f1af2-140">Value</span></span>         |

   1. <span data-ttu-id="f1af2-141">Lai grupai pievienotu papildu nosacījumus, varat izmantot divus loģiskos operatorus:</span><span class="sxs-lookup"><span data-stu-id="f1af2-141">To add more conditions to a group, you can use two logical operators:</span></span>

      - <span data-ttu-id="f1af2-142">**UN** operators: Ir jāizpilda abi nosacījumi kā daļa no segmentācijas procesa.</span><span class="sxs-lookup"><span data-stu-id="f1af2-142">**AND** operator: Both conditions must be met as part of the segmentation process.</span></span> <span data-ttu-id="f1af2-143">Šī opcija ir visnoderīgākā, kad definējat nosacījumus dažādās entītijās.</span><span class="sxs-lookup"><span data-stu-id="f1af2-143">This option is most useful when you define conditions across different entities.</span></span>

      - <span data-ttu-id="f1af2-144">**Vai** operators: Viens vai otrs no nosacījumiem ir jāizpilda kā segmentācijas procesa daļa.</span><span class="sxs-lookup"><span data-stu-id="f1af2-144">**OR** operator: Either one of the conditions needs to be met as part of the segmentation process.</span></span> <span data-ttu-id="f1af2-145">Šī opcija ir visnoderīgākā, kad definējat vairākus nosacījumus vienai entītijai.</span><span class="sxs-lookup"><span data-stu-id="f1af2-145">This option is most useful when you define multiple conditions for the same entity.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="f1af2-146">![VAI operators, ja kāds no nosacījumiem ir jāizpilda](media/segmentation-either-condition.png "VAI operators, ja kāds no nosacījumiem ir jāizpilda")</span><span class="sxs-lookup"><span data-stu-id="f1af2-146">![OR operator where either condition needs to be met](media/segmentation-either-condition.png "OR operator where either condition needs to be met")</span></span>

      <span data-ttu-id="f1af2-147">Pašlaik ir iespējams ligzdot **VAI** operatoru, izmantojot operatoru **UN**, bet ne otrādi.</span><span class="sxs-lookup"><span data-stu-id="f1af2-147">It's currently possible to nest an **OR** operator under an **AND** operator, but not the other way around.</span></span>

   1. <span data-ttu-id="f1af2-148">Katra grupa atbilst klientu kopai.</span><span class="sxs-lookup"><span data-stu-id="f1af2-148">Each group matches set of customers.</span></span> <span data-ttu-id="f1af2-149">Grupas var apvienot, lai iekļautu biznesa pieteikumam nepieciešamos klientus.</span><span class="sxs-lookup"><span data-stu-id="f1af2-149">You can combine groups to include the customers required for your business case.</span></span>    
   <span data-ttu-id="f1af2-150">Atlasiet **Pievienot grupu**.</span><span class="sxs-lookup"><span data-stu-id="f1af2-150">Select **Add Group**.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="f1af2-151">![Klientu grupu pievienošanas grupa](media/customer-group-add-group.png "Klientu grupu pievienošanas grupa")</span><span class="sxs-lookup"><span data-stu-id="f1af2-151">![Customer group add group](media/customer-group-add-group.png "Customer group add group")</span></span>

   1. <span data-ttu-id="f1af2-152">Atlasiet kādu no iestatītajiem operatoriem: **Apvienošana**, **Krustpunkts** vai **Izņemot**.</span><span class="sxs-lookup"><span data-stu-id="f1af2-152">Select one of the set operators: **Union**, **Intersect**, or **Except**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f1af2-153">![Klientu grupu pievienošanas apvienošana](media/customer-group-union.png "Klientu grupu pievienošanas apvienošana")</span><span class="sxs-lookup"><span data-stu-id="f1af2-153">![Customer group add union](media/customer-group-union.png "Customer group add union")</span></span>

   - <span data-ttu-id="f1af2-154">**Apvienot** apvieno divas grupas.</span><span class="sxs-lookup"><span data-stu-id="f1af2-154">**Union** unites the two groups.</span></span>

   - <span data-ttu-id="f1af2-155">**Izveidot krustpunktu** pārklāj divas grupas.</span><span class="sxs-lookup"><span data-stu-id="f1af2-155">**Intersect** overlaps the two groups.</span></span> <span data-ttu-id="f1af2-156">Vienotajā grupā tiek saglabāti tikai tie dati, kas ir *kopēji* abām grupām.</span><span class="sxs-lookup"><span data-stu-id="f1af2-156">Only data that *is common* to both groups is retained in the unified group.</span></span>

   - <span data-ttu-id="f1af2-157">**Izņemot** apvieno divas grupas.</span><span class="sxs-lookup"><span data-stu-id="f1af2-157">**Except** combines the two groups.</span></span> <span data-ttu-id="f1af2-158">Tiek saglabāti tikai A grupas dati, kas *nav kopēji* B grupas datiem.</span><span class="sxs-lookup"><span data-stu-id="f1af2-158">Only data in group A that *is not common* to data in group B is retained.</span></span>

1. <span data-ttu-id="f1af2-159">Ja entītija ir savienota ar vienotā klienta entītiju, izmantojot [relācijas](relationships.md), ir jādefinē relāciju ceļš, lai izveidotu derīgu segmentu.</span><span class="sxs-lookup"><span data-stu-id="f1af2-159">If the entity is connected to the unified customer entity through [relationships](relationships.md), you need to define the relationship path to create a valid segment.</span></span> <span data-ttu-id="f1af2-160">Pievienojiet entītijas no attiecību ceļa, līdz varat nolaižamajā sarakstā atlasīt entitīju **Klients: CustomerInsights**.</span><span class="sxs-lookup"><span data-stu-id="f1af2-160">Add the entities from the relationship path until you can select the **Customer:CustomerInsights** entity from the dropdown.</span></span> <span data-ttu-id="f1af2-161">Pēc tam katrai darbībai izvēlieties **Visi ieraksti**.</span><span class="sxs-lookup"><span data-stu-id="f1af2-161">Then, choose **All records** for each step.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f1af2-162">![Relāciju ceļš segmenta izveides laikā](media/segments-multiple-relationships.png "Relāciju ceļš segmenta izveides laikā")</span><span class="sxs-lookup"><span data-stu-id="f1af2-162">![Relationship path during segment creation](media/segments-multiple-relationships.png "Relationship path during segment creation")</span></span>

1. <span data-ttu-id="f1af2-163">Pēc noklusējuma segmenti ģenerē izvades entītiju, kurā ir visi klientu profilu atribūti, kas atbilst definētajiem filtriem.</span><span class="sxs-lookup"><span data-stu-id="f1af2-163">By default, segments generate an output entity that contains all attributes of customer profiles which match the defined filters.</span></span> <span data-ttu-id="f1af2-164">Ja segments ir balstīts uz citām entītijām, nevis entītiju *Klients*, izvades entītijai var pievienot papildu atribūtus no šīm entītijām.</span><span class="sxs-lookup"><span data-stu-id="f1af2-164">If a segment is based on other entities than the *Customer* entity, you can add more attributes from these entities to the output entity.</span></span> <span data-ttu-id="f1af2-165">Atlasiet **Projekta atribūtus**, lai izvēlētos atribūtus, kas tiks pievienoti izvades entītijai.</span><span class="sxs-lookup"><span data-stu-id="f1af2-165">Select **Project attributes** to choose the attributes that will be appended to the output entity.</span></span>  
  
   <span data-ttu-id="f1af2-166">Piemērs. Segments tiek veidots, pamatojoties uz entītiju, kurā ir ietverti ar entītiju *Klients* saistīti klienta darbības dati.</span><span class="sxs-lookup"><span data-stu-id="f1af2-166">Example: A segment is based on an entity that contains customer activity data which is related to the *Customer* entity.</span></span> <span data-ttu-id="f1af2-167">Segments meklē visus klientus, kas pēdējo 60 dienu laikā zvanījuši palīdzības dienestam.</span><span class="sxs-lookup"><span data-stu-id="f1af2-167">The segment looks for all customers that called the help desk in the last 60 days.</span></span> <span data-ttu-id="f1af2-168">Varat izvēlēties, vai izvades entītijā pievienot sarunas ilgumu un zvanu skaitu visiem atbilstošajiem klientu ierakstiem.</span><span class="sxs-lookup"><span data-stu-id="f1af2-168">You can choose to append the call duration and the number of calls to all matching customer records in the output entity.</span></span> <span data-ttu-id="f1af2-169">Šī informācija var būt noderīga lai nosūtītu e-pasta ziņojumu ar noderīgām saitēm uz tiešsaistes palīdzības rakstiem un bieži uzdotajiem jautājumiem tiem klientiem, kuri zvanījuši bieži.</span><span class="sxs-lookup"><span data-stu-id="f1af2-169">This information might be useful to send an email with helpful links to online help articles and FAQs to customers who called frequently.</span></span>

   > [!NOTE]
   > - <span data-ttu-id="f1af2-170">Plānotie atribūti darbojas tikai entītijām, kurām ir attiecības viens pret daudziem ar klienta entītiju.</span><span class="sxs-lookup"><span data-stu-id="f1af2-170">Projected attributes only work for entities that have a one-to-many relationship with the customer entity.</span></span> <span data-ttu-id="f1af2-171">Piemēram, vienam klientam var būt vairāki abonementi.</span><span class="sxs-lookup"><span data-stu-id="f1af2-171">For example, one customer can have multiple subscriptions.</span></span>
   > - <span data-ttu-id="f1af2-172">Projekta atribūtus var izveidot tikai no entītijas, kas tiek izmantota katrā veidotā segmenta vaicājuma grupā.</span><span class="sxs-lookup"><span data-stu-id="f1af2-172">You can only project attributes from an entity that is used in every group of segment query you are building.</span></span>
   > - <span data-ttu-id="f1af2-173">Plānotie atribūti tiek faktorizēti, izmantojot kopas operatorus.</span><span class="sxs-lookup"><span data-stu-id="f1af2-173">Projected attributes are factored in when using set operators.</span></span>

1. <span data-ttu-id="f1af2-174">Lai saglabātu segmentu, atlasiet **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="f1af2-174">Select **Save** to save your segment.</span></span> <span data-ttu-id="f1af2-175">Jūsu segments tiks saglabāts un apstrādāts, ja visas prasības ir validētas.</span><span class="sxs-lookup"><span data-stu-id="f1af2-175">Your segment will be saved and processed if all requirements are validated.</span></span> <span data-ttu-id="f1af2-176">Pretējā gadījumā tas tiks saglabāts kā melnraksts.</span><span class="sxs-lookup"><span data-stu-id="f1af2-176">Otherwise, it will be saved as a draft.</span></span>

1. <span data-ttu-id="f1af2-177">Atlasiet **Atgriezties pie segmentiem**, lai atgrieztos pie **Segmentu** lapas.</span><span class="sxs-lookup"><span data-stu-id="f1af2-177">Select **Back to segments** to go back to the **Segments** page.</span></span>



## <a name="quick-segments"></a><span data-ttu-id="f1af2-178">Ātrie segmenti</span><span class="sxs-lookup"><span data-stu-id="f1af2-178">Quick segments</span></span>

<span data-ttu-id="f1af2-179">Izmantojot ātros segmentus, varat ātri izveidot vienkāršus segmentus, izmantojot vienu operatoru, lai gūtu ātrākus ieskatus.</span><span class="sxs-lookup"><span data-stu-id="f1af2-179">Quick segments let you build simple segments with a single operator quickly for faster insights.</span></span>

1. <span data-ttu-id="f1af2-180">**Segmentu** lapā atlasiet **Jauns** > **Izveidot no**.</span><span class="sxs-lookup"><span data-stu-id="f1af2-180">On the **Segments** page, select **New** > **Create from**.</span></span>

   - <span data-ttu-id="f1af2-181">Atlasiet opciju **Profili**, lai izveidotu segmentu, kura pamatā ir *vienotā klienta* entītija.</span><span class="sxs-lookup"><span data-stu-id="f1af2-181">Select the **Profiles** option to build a segment that is based on the *unified customer* entity.</span></span>
   - <span data-ttu-id="f1af2-182">Atlasiet opciju **Pasākumi**, lai izveidotu segmentu ap iepriekš izveidotajiem pasākumiem.</span><span class="sxs-lookup"><span data-stu-id="f1af2-182">Select the **Measures** option to build a segment around  measures you have previously created.</span></span>
   - <span data-ttu-id="f1af2-183">Atlasiet opciju **Informācijas apkopošana**, lai izveidotu segmentu ap vienu no izvades entitījām, kuras izveidojāt, izmantojot iespēju **Prognozes** vai **Pielāgotie modeļi**.</span><span class="sxs-lookup"><span data-stu-id="f1af2-183">Select the **Intelligence** option to build a segment around one of the output entities you generated using either the **Predictions** or **Custom Models** capabilities.</span></span>

2. <span data-ttu-id="f1af2-184">Dialoglodziņā **Jauns ātrais segments** atlasiet atribūtu no nolaižamā saraksta **Lauks**.</span><span class="sxs-lookup"><span data-stu-id="f1af2-184">In the **New quick segment** dialog box, select an attribute from the **Field** dropdown.</span></span>

3. <span data-ttu-id="f1af2-185">Sistēma sniegs papildu ieskatus, kas palīdz izveidot labākus klientu segmentus.</span><span class="sxs-lookup"><span data-stu-id="f1af2-185">The system will provide some additional insights that help you create better segments of your customers.</span></span>
   - <span data-ttu-id="f1af2-186">Attiecībā uz kategoriju laukiem mēs parādīsim 10 lielāko klientu skaitu.</span><span class="sxs-lookup"><span data-stu-id="f1af2-186">For categorical fields, we'll show 10 top customer counts.</span></span> <span data-ttu-id="f1af2-187">Izvēlieties **Vērtība** un atlasiet **Pārskatīt**.</span><span class="sxs-lookup"><span data-stu-id="f1af2-187">Choose a **Value** and select **Review**.</span></span>

   - <span data-ttu-id="f1af2-188">Skaitliskam atribūtam sistēma parādīs, kāda atribūta vērtība atbilst katra klienta procentīlei.</span><span class="sxs-lookup"><span data-stu-id="f1af2-188">For a numerical attribute, the system will show what attribute value falls under each customer's percentile.</span></span> <span data-ttu-id="f1af2-189">Izvēlieties **Operators** un **Vērtība** un pēc tam atlasiet vienumu **Pārskatīt**.</span><span class="sxs-lookup"><span data-stu-id="f1af2-189">Choose an **Operator** and a **Value**, then select **Review**.</span></span>

4. <span data-ttu-id="f1af2-190">Sistēma nodrošinās jūs ar **Aptuveniem segmenta izmēriem**.</span><span class="sxs-lookup"><span data-stu-id="f1af2-190">The system will provide you with an **Estimated segment size**.</span></span> <span data-ttu-id="f1af2-191">Varat izvēlēties, vai ģenerēt definēto segmentu, vai arī to vispirms pārskatīt, lai iegūtu citu segmenta lielumu.</span><span class="sxs-lookup"><span data-stu-id="f1af2-191">You can choose whether to generate the segment you've defined, or first revisit it to get a different segment size.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="f1af2-192">![Ātrā segmenta nosaukums un novērtējums](media/quick-segment-name.png "Ātrā segmenta nosaukums un novērtējums")</span><span class="sxs-lookup"><span data-stu-id="f1af2-192">![Name and estimation for a quick segment](media/quick-segment-name.png "Name and estimation for a quick segment")</span></span>

5. <span data-ttu-id="f1af2-193">Norādiet segmenta **Nosaukumu**.</span><span class="sxs-lookup"><span data-stu-id="f1af2-193">Provide a **Name** for your segment.</span></span> <span data-ttu-id="f1af2-194">Vai ari norādiet **Parādāmo vārdu**.</span><span class="sxs-lookup"><span data-stu-id="f1af2-194">Optionally, provide a **Display name**.</span></span>

6. <span data-ttu-id="f1af2-195">Lai izveidotu segmentu, atlasiet opciju **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="f1af2-195">Select **Save** to create your segment.</span></span>

7. <span data-ttu-id="f1af2-196">Pēc tam, kad segments ir pabeidzis apstrādi, to var apskatīt tāpat kā jebkuru citu izveidoto segmentu.</span><span class="sxs-lookup"><span data-stu-id="f1af2-196">After the segment has finished processing, you can view it like any other segment you've created.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f1af2-197">Nākamās darbības</span><span class="sxs-lookup"><span data-stu-id="f1af2-197">Next steps</span></span>

<span data-ttu-id="f1af2-198">[Eksportējiet segmentu](export-destinations.md) un izpētiet [Klienta karti](customer-card-add-in.md) un [Savienotājus](export-power-bi.md), lai gūtu ieskatu klientu līmenī.</span><span class="sxs-lookup"><span data-stu-id="f1af2-198">[Export a segment](export-destinations.md) and explore the [Customer Card](customer-card-add-in.md) and [Connectors](export-power-bi.md) to get insights on the customer level.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
