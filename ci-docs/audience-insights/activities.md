---
title: Klientu darbības
description: Definējiet klientu darbības un aplūkojiet tās klientu laika skalā.
ms.date: 10/13/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: fbfa9d7e00859cc80c24b98bd2dc806f1fda7803
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596738"
---
# <a name="customer-activities"></a><span data-ttu-id="21ed7-103">Klientu darbības</span><span class="sxs-lookup"><span data-stu-id="21ed7-103">Customer activities</span></span>

<span data-ttu-id="21ed7-104">Kombinējiet klientu darbības no [dažādiem datu avotiem](data-sources.md) Dynamics 365 Customer Insights, lai izveidotu klientu laika skalu, kurā darbības ir uzskaitītas hronoloģiskā secībā.</span><span class="sxs-lookup"><span data-stu-id="21ed7-104">Combine customer activities from [various data sources](data-sources.md) in Dynamics 365 Customer Insights to create a customer timeline that lists the activities in chronological order.</span></span> <span data-ttu-id="21ed7-105">Varat iekļaut laika skalu klientu iesaistes programmās pakalpojumā Dynamics 365, izmantojot [Customer Card pievienojumprogrammu](customer-card-add-in.md) vai Power BI informācijas paneli.</span><span class="sxs-lookup"><span data-stu-id="21ed7-105">You can include the timeline in customer engagement apps in Dynamics 365 via the [Customer Card add-in](customer-card-add-in.md), or in a Power BI dashboard.</span></span>

## <a name="define-an-activity"></a><span data-ttu-id="21ed7-106">Darbības definēšana</span><span class="sxs-lookup"><span data-stu-id="21ed7-106">Define an activity</span></span>

<span data-ttu-id="21ed7-107">Datu avoti ietver entītijas ar transakciju un darbību datiem no vairākiem datu avotiem.</span><span class="sxs-lookup"><span data-stu-id="21ed7-107">Your data sources include entities with transactional and activity data from multiple data sources.</span></span> <span data-ttu-id="21ed7-108">Identificējiet šīs entītijas un atlasiet darbības, kuras vēlaties skatīt klienta laika skalā.</span><span class="sxs-lookup"><span data-stu-id="21ed7-108">Identify these entities and select the activities you want to view on the customer's timeline.</span></span> <span data-ttu-id="21ed7-109">Izvēlieties entītiju, kurā ir jūsu mērķa darbība vai darbības.</span><span class="sxs-lookup"><span data-stu-id="21ed7-109">Choose the entity that includes your target activity or activities.</span></span>

1. <span data-ttu-id="21ed7-110">Sadaļā Auditorijas ieskati skatiet **Dati** > **Darbības**.</span><span class="sxs-lookup"><span data-stu-id="21ed7-110">In audience insights, go to **Data** > **Activities**.</span></span>

1. <span data-ttu-id="21ed7-111">Atlasiet **Pievienot darbību**.</span><span class="sxs-lookup"><span data-stu-id="21ed7-111">Select **Add activity**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="21ed7-112">Entītijai ir nepieciešams vismaz viens veida **Datums** atribūts, ko iekļaut klienta laika skalā, un entītijas bez **Datuma** laukiem nevar pievienot.</span><span class="sxs-lookup"><span data-stu-id="21ed7-112">An entity must have at least one attribute of type **Date** to be included in a customer timeline and you can't add entities without **Date** fields.</span></span> <span data-ttu-id="21ed7-113">Ja netiek atrasta šāda entitīja, vadīkla **Pievienot darbību** tiek atspējota.</span><span class="sxs-lookup"><span data-stu-id="21ed7-113">The **Add activity** control is disabled if no such entity is found.</span></span>

1. <span data-ttu-id="21ed7-114">Rūtī **Pievienot darbību** iestatiet šādu lauku vērtības:</span><span class="sxs-lookup"><span data-stu-id="21ed7-114">In the **Add activity** pane, set the values for the following fields:</span></span>

   - <span data-ttu-id="21ed7-115">**Entītija**: Atlasiet entītiju, kurā ir transakciju vai darbību dati.</span><span class="sxs-lookup"><span data-stu-id="21ed7-115">**Entity**: Select an entity that includes transactional or activity data.</span></span>
   - <span data-ttu-id="21ed7-116">**Primārā atslēga**: Atlasīt lauku, kas unikāli identificē ierakstu.</span><span class="sxs-lookup"><span data-stu-id="21ed7-116">**Primary key**: Select the field that uniquely identifies a record.</span></span> <span data-ttu-id="21ed7-117">Tajā nedrīkst ietvert dublētas vērtības, tukšas vērtības vai trūkstošas vērtības.</span><span class="sxs-lookup"><span data-stu-id="21ed7-117">It shouldn't contain any duplicate values, empty values, or missing values.</span></span>
   - <span data-ttu-id="21ed7-118">**Laikspiedols**: Atlasiet lauku, kas norāda darbības sākuma laiku.</span><span class="sxs-lookup"><span data-stu-id="21ed7-118">**Timestamp**: Select the field that represents the start time of your activity.</span></span>
   - <span data-ttu-id="21ed7-119">**Notikums**: Atlasiet lauku, kas ir darbības notikums.</span><span class="sxs-lookup"><span data-stu-id="21ed7-119">**Event**: Select the field that is the event for the activity.</span></span>
   - <span data-ttu-id="21ed7-120">**Tīmekļa adrese** : Atlasiet lauku, kas norāda URL, kas nodrošina papildinformāciju par šo darbību.</span><span class="sxs-lookup"><span data-stu-id="21ed7-120">**Web address**: Select the field that represents a URL providing additional information about this activity.</span></span> <span data-ttu-id="21ed7-121">Piemēram, transakciju sistēma, kas ģenerē šo darbību.</span><span class="sxs-lookup"><span data-stu-id="21ed7-121">For example, the transactional system that sources this activity.</span></span> <span data-ttu-id="21ed7-122">Šis URL var būt jebkurš lauks no datu avota, vai arī to var būvēt kā jaunu lauku, izmantojot Power Query transformāciju.</span><span class="sxs-lookup"><span data-stu-id="21ed7-122">This URL can be any field from the data source, or it can be constructed as a new field using a Power Query transformation.</span></span> <span data-ttu-id="21ed7-123">Šie URL dati tiks saglabāti Vienotās darbības entītijā, ko var patērēt pa straumi, izmantojot API.</span><span class="sxs-lookup"><span data-stu-id="21ed7-123">This URL data will be stored in the Unified Activity entity, which can be consumed downstream using APIs.</span></span>
   - <span data-ttu-id="21ed7-124">**Detalizēta informācija**: Pēc izvēles atlasiet lauku, kas tiek pievienots papildu informācijai.</span><span class="sxs-lookup"><span data-stu-id="21ed7-124">**Details**: Optionally, select the field that is added for additional details.</span></span>
   - <span data-ttu-id="21ed7-125">**Ikona**: Pēc izvēles atlasiet ikonu, kas apzīmē šo darbību.</span><span class="sxs-lookup"><span data-stu-id="21ed7-125">**Icon**: Optionally, select the icon that represents this activity.</span></span>
   - <span data-ttu-id="21ed7-126">**Darbības tips**: Definējiet darbības tipa atsauci uz Common Data Model, kas vislabāk apraksta darbības semantisko definīciju.</span><span class="sxs-lookup"><span data-stu-id="21ed7-126">**Activity Type**: Define the activity type reference to Common Data Model that best describes the semantic definition of the activity.</span></span>

1. <span data-ttu-id="21ed7-127">Sadaļā **Relācijas iestatīšana** konfigurējiet detalizēto informāciju, lai savienotu savus darbību datus ar atbilstošo klientu.</span><span class="sxs-lookup"><span data-stu-id="21ed7-127">In the **Set up relationship** section, configure the details to connect your activity data to its corresponding customer.</span></span>

    - <span data-ttu-id="21ed7-128">**Darbības entītijas lauks**: Atlasiet lauku savā darbības entītijā, kurš tiks izmantots relācijas izveidei ar citu entītiju.</span><span class="sxs-lookup"><span data-stu-id="21ed7-128">**Activity entity field**: Select the field in your activity entity that will be used to establish a relationship with another entity.</span></span>
    - <span data-ttu-id="21ed7-129">**Klienta entītija**: Atlasiet atbilstošo avota klienta entītiju, ar kuru jūsu darbības entītijai tiks izveidota relācija.</span><span class="sxs-lookup"><span data-stu-id="21ed7-129">**Customer entity**: Select the corresponding source customer entity with which your activity entity will be in relationship.</span></span> <span data-ttu-id="21ed7-130">Var saistīt tikai tās avota klienta entītijas, kuras tiek izmantotas datu apvienošanas procesā.</span><span class="sxs-lookup"><span data-stu-id="21ed7-130">You can relate to only those source customer entities that are used in the data unification process.</span></span>
    - <span data-ttu-id="21ed7-131">**Klienta entītijas lauks**: Šajā laukā ir norādīta avota klienta entītijas primārā atslēga, kas atlasīta kartēšanas procesā.</span><span class="sxs-lookup"><span data-stu-id="21ed7-131">**Customer entity field**: This field shows the primary key of the source customer entity as selected in the map process.</span></span> <span data-ttu-id="21ed7-132">Šis primārās atslēgas lauks avota klienta entītijā tiek izmantots, lai izveidotu relāciju ar darbības entītiju.</span><span class="sxs-lookup"><span data-stu-id="21ed7-132">This primary key field in the source customer entity is used to establish a relationship with the activity entity.</span></span>
    - <span data-ttu-id="21ed7-133">**Nosaukums**: Ja relācija starp šo darbības entītiju un atlasīto avota klienta entītiju jau pastāv, relācijas nosaukums būs tikai lasāmā režīmā.</span><span class="sxs-lookup"><span data-stu-id="21ed7-133">**Name**: If a relationship between this activity entity and the selected source customer entity already exists, the relationship name will be in read-only mode.</span></span> <span data-ttu-id="21ed7-134">Ja šādas relācijas nav, tiek izveidota jauna relācija ar šeit norādīto nosaukumu.</span><span class="sxs-lookup"><span data-stu-id="21ed7-134">If there no such relationship exists, a new relationship will be created with the name provided here.</span></span>
   
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="21ed7-135">![Entītiju relācijas definēšana](media/activities-entities-define.png "Entītiju relācijas definēšana")</span><span class="sxs-lookup"><span data-stu-id="21ed7-135">![Define the entity relationship](media/activities-entities-define.png "Define the entity relationship")</span></span>

1. <span data-ttu-id="21ed7-136">Lai veiktās izmaiņas stātos spēkā, atlasiet **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="21ed7-136">Select **Save** to apply your changes.</span></span>

1. <span data-ttu-id="21ed7-137">Lapā **Darbības** atlasiet **Palaist**.</span><span class="sxs-lookup"><span data-stu-id="21ed7-137">On the **Activities** page, select **Run**.</span></span>

> [!TIP]
> <span data-ttu-id="21ed7-138">Uzdevumiem/procesiem ir [seši statusu tipi](system.md#status-types).</span><span class="sxs-lookup"><span data-stu-id="21ed7-138">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="21ed7-139">Turklāt vairums procesu [ir atkarīgi no citiem pakārtotiem procesiem](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="21ed7-139">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="21ed7-140">Varat atlasīt procesa statusu, lai skatītu detalizētu informāciju par visa uzdevuma norisi.</span><span class="sxs-lookup"><span data-stu-id="21ed7-140">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="21ed7-141">Pēc tam, kad vienam no darba uzdevumiem esat atlasījis **Skatīt detalizētu informāciju**, jūs redzēsit papildinformāciju: apstrādes laiku, pēdējās apstrādes datumu un visas kļūdas un brīdinājumus, kas saistīti ar uzdevumu.</span><span class="sxs-lookup"><span data-stu-id="21ed7-141">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="edit-an-activity"></a><span data-ttu-id="21ed7-142">Darbības rediģēšana</span><span class="sxs-lookup"><span data-stu-id="21ed7-142">Edit an activity</span></span>

1. <span data-ttu-id="21ed7-143">Sadaļā Auditorijas ieskati skatiet **Dati** > **Darbības**.</span><span class="sxs-lookup"><span data-stu-id="21ed7-143">In audience insights, go to **Data** > **Activities**.</span></span>

2. <span data-ttu-id="21ed7-144">Atlasiet darbības entītiju, kuru vēlaties rediģēt, un atlasiet **Rediģēt**.</span><span class="sxs-lookup"><span data-stu-id="21ed7-144">Select the activity entity you want to edit and select **Edit**.</span></span> <span data-ttu-id="21ed7-145">Vai arī varat novietot rādītāju virs entītijas rindas un atlasīt ikonu **Rediģēt**.</span><span class="sxs-lookup"><span data-stu-id="21ed7-145">Or, you can hover over the entity row and select the **Edit** icon.</span></span>

3. <span data-ttu-id="21ed7-146">Noklikšķiniet uz ikonas **Rediģēt**.</span><span class="sxs-lookup"><span data-stu-id="21ed7-146">Click on the **Edit** icon.</span></span>

4. <span data-ttu-id="21ed7-147">**Rediģēšanas darbības** rūtī atjauniniet vērtības un atlasiet vienumu **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="21ed7-147">In the **Edit activity** pane, update the values and select **Save**.</span></span>

5. <span data-ttu-id="21ed7-148">Lapā **Darbības** atlasiet **Palaist**.</span><span class="sxs-lookup"><span data-stu-id="21ed7-148">On the **Activities** page, select **Run**.</span></span>

## <a name="delete-an-activity"></a><span data-ttu-id="21ed7-149">Darbības dzēšana</span><span class="sxs-lookup"><span data-stu-id="21ed7-149">Delete an activity</span></span>

1. <span data-ttu-id="21ed7-150">Sadaļā Auditorijas ieskati skatiet **Dati** > **Darbības**.</span><span class="sxs-lookup"><span data-stu-id="21ed7-150">In audience insights, go to **Data** > **Activities**.</span></span>

2. <span data-ttu-id="21ed7-151">Atlasiet darbības entītiju, kuru vēlaties noņemt, un atlasiet **Dzēst**.</span><span class="sxs-lookup"><span data-stu-id="21ed7-151">Select the activity entity you want to remove and select **Delete**.</span></span> <span data-ttu-id="21ed7-152">Vai arī varat novietot rādītāju virs entītijas rindas un atlasīt ikonu **Dzēst**.</span><span class="sxs-lookup"><span data-stu-id="21ed7-152">Or, you can hover over the entity row and select the **Delete** icon.</span></span> <span data-ttu-id="21ed7-153">Turklāt vienlaikus varat atlasīt vairākas darbību entītijas, lai izdzēstu tās vienlaicīgi.</span><span class="sxs-lookup"><span data-stu-id="21ed7-153">Additionally, you can select multiple activity entities to be deleted at once.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="21ed7-154">![Entītiju attiecību rediģēšana vai dzēšana](media/activities-entities-edit-delete.png "Entītiju attiecību rediģēšana vai dzēšana")</span><span class="sxs-lookup"><span data-stu-id="21ed7-154">![Edit or delete the entity relationship](media/activities-entities-edit-delete.png "Edit or delete the entity relationship")</span></span>

3. <span data-ttu-id="21ed7-155">Atlasiet ikonu **Dzēst**.</span><span class="sxs-lookup"><span data-stu-id="21ed7-155">Select on the **Delete** icon.</span></span>

4. <span data-ttu-id="21ed7-156">Apstipriniet dzēšanu.</span><span class="sxs-lookup"><span data-stu-id="21ed7-156">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]