---
title: Klientu darbības
description: Definējiet klientu darbības un aplūkojiet tās klientu laika skalā.
ms.date: 04/07/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: 342aeb33f652d5d60cd25e13969766954bf56370
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304935"
---
# <a name="customer-activities"></a><span data-ttu-id="16d16-103">Klientu darbības</span><span class="sxs-lookup"><span data-stu-id="16d16-103">Customer activities</span></span>

<span data-ttu-id="16d16-104">Apvienojiet klientu darbības no [dažādiem datu avotiem](data-sources.md) risinājumā Dynamics 365 Customer Insights, lai izveidotu laika skalu, kurā hronoloǵiski uzskaitītas darbības.</span><span class="sxs-lookup"><span data-stu-id="16d16-104">Combine customer activities from [various data sources](data-sources.md) in Dynamics 365 Customer Insights to create a timeline that lists the activities chronologically.</span></span> <span data-ttu-id="16d16-105">Iekļaujiet laika skalu Dynamics 365 programmās, izmantojot risinājumu [Klienta kartes pievienojumprogramma](customer-card-add-in.md) vai Power BI informācijas panelī.</span><span class="sxs-lookup"><span data-stu-id="16d16-105">Include the timeline in Dynamics 365 apps with the [Customer Card add-in](customer-card-add-in.md) solution, or in a Power BI dashboard.</span></span>

## <a name="define-an-activity"></a><span data-ttu-id="16d16-106">Darbības definēšana</span><span class="sxs-lookup"><span data-stu-id="16d16-106">Define an activity</span></span>

<span data-ttu-id="16d16-107">Datu avoti var ietvert entītijas ar transakciju un darbību datiem no vairākiem datu avotiem.</span><span class="sxs-lookup"><span data-stu-id="16d16-107">Your data sources can include entities with transactional and activity data from multiple data sources.</span></span> <span data-ttu-id="16d16-108">Identificējiet šīs entītijas un atlasiet darbības, kuras vēlaties skatīt klienta laika skalā.</span><span class="sxs-lookup"><span data-stu-id="16d16-108">Identify these entities and select the activities you want to view on the customer's timeline.</span></span> <span data-ttu-id="16d16-109">Izvēlieties entītiju, kurā ir jūsu mērķa darbība vai darbības.</span><span class="sxs-lookup"><span data-stu-id="16d16-109">Choose the entity that includes your target activity or activities.</span></span>

> [!NOTE]
> <span data-ttu-id="16d16-110">Entītijai ir nepieciešams vismaz viens veida **Datums** atribūts, ko iekļaut klienta laika skalā, un entītijas bez **Datuma** laukiem nevar pievienot.</span><span class="sxs-lookup"><span data-stu-id="16d16-110">An entity must have at least one attribute of type **Date** to be included in a customer timeline and you can't add entities without **Date** fields.</span></span> <span data-ttu-id="16d16-111">Ja netiek atrasta šāda entitīja, vadīkla **Pievienot darbību** tiek atspējota.</span><span class="sxs-lookup"><span data-stu-id="16d16-111">The **Add activity** control is disabled if no such entity is found.</span></span>

1. <span data-ttu-id="16d16-112">Sadaļā Auditorijas ieskati skatiet **Dati** > **Darbības**.</span><span class="sxs-lookup"><span data-stu-id="16d16-112">In audience insights, go to **Data** > **Activities**.</span></span>

1. <span data-ttu-id="16d16-113">Atlasiet **Pievienot darbību**, lai sāktu vadīti iestatīt darbību.</span><span class="sxs-lookup"><span data-stu-id="16d16-113">Select **Add activity** to start the guided experience for the activity setup process.</span></span>

1. <span data-ttu-id="16d16-114">Darbībā **Darbības dati** iestatiet šādu lauku vērtības:</span><span class="sxs-lookup"><span data-stu-id="16d16-114">In the **Activity data** step, set the values for the following fields:</span></span>

   - <span data-ttu-id="16d16-115">**Darbības nosaukums**: Atlasiet savas darbības nosaukumu.</span><span class="sxs-lookup"><span data-stu-id="16d16-115">**Activity name**: Select a name for your activity.</span></span>
   - <span data-ttu-id="16d16-116">**Entītija**: Atlasiet entītiju, kurā ir transakciju vai darbību dati.</span><span class="sxs-lookup"><span data-stu-id="16d16-116">**Entity**: Select an entity that includes transactional or activity data.</span></span>
   - <span data-ttu-id="16d16-117">**Primārā atslēga**: Atlasīt lauku, kas unikāli identificē ierakstu.</span><span class="sxs-lookup"><span data-stu-id="16d16-117">**Primary key**: Select the field that uniquely identifies a record.</span></span> <span data-ttu-id="16d16-118">Tajā nedrīkst ietvert dublētas vērtības, tukšas vērtības vai trūkstošas vērtības.</span><span class="sxs-lookup"><span data-stu-id="16d16-118">It shouldn't contain any duplicate values, empty values, or missing values.</span></span>

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="Iestatiet darbības datus ar nosaukumu, entītiju un primāro atslēgu.":::

1. <span data-ttu-id="16d16-120">Lai pārietu uz nākamo darbību, atlasiet **Tālāk**.</span><span class="sxs-lookup"><span data-stu-id="16d16-120">Select **Next** to go to the next step.</span></span>

1. <span data-ttu-id="16d16-121">Darbībā **Attiecības** konfigurējiet informāciju, lai savienotu savas aktivitātes datus ar tai atbilstošo klientu.</span><span class="sxs-lookup"><span data-stu-id="16d16-121">In the **Relationship** step, configure the details to connect your activity data to its corresponding customer.</span></span> <span data-ttu-id="16d16-122">Šajā darbībā tiek vizualizēts entitīju savienojums.</span><span class="sxs-lookup"><span data-stu-id="16d16-122">This step visualizes the connection between entities.</span></span>  

   - <span data-ttu-id="16d16-123">**Pirmais**: Ārējs darbību entitījas lauks, kuru izmantos, lai izveidotu relāciju ar citu entitīju.</span><span class="sxs-lookup"><span data-stu-id="16d16-123">**First**: Foreign field in your activity entity that will be used to establish a relationship with another entity.</span></span>
   - <span data-ttu-id="16d16-124">**Otrais**: Atbilstošā avota klienta entitīja, ar kuru jūsu entitījai būs relācija.</span><span class="sxs-lookup"><span data-stu-id="16d16-124">**Second**: Corresponding source customer entity with which your activity entity will be in relationship.</span></span> <span data-ttu-id="16d16-125">Ir iespējams izveidot relāciju tikai ar avota klientu entitījām, kuras tiek izmantotas datu apvienošanas procesā.</span><span class="sxs-lookup"><span data-stu-id="16d16-125">You can only relate to source customer entities that are used in the data unification process.</span></span>
   - <span data-ttu-id="16d16-126">**Trešā**: Ja jau pastāv relācija starp šo darbības entitīju un atlasīto avota klienta entitīju, relācijas nosaukums būs tikai lasāmā režīmā.</span><span class="sxs-lookup"><span data-stu-id="16d16-126">**Third**: If a relationship between this activity entity and the selected source customer entity already exists, the relationship name will be in read-only mode.</span></span> <span data-ttu-id="16d16-127">Ja šāda relācija nepastāv, tiks izveidota jauna relācija ar šajā lodziņā sniegto nosaukumu.</span><span class="sxs-lookup"><span data-stu-id="16d16-127">If no such relationship exists, a new relationship will be created with the name you provide in this box.</span></span>

   :::image type="content" source="media/Activity_Wizard2.PNG" alt-text="Entītiju relācijas definēšana.":::

1. <span data-ttu-id="16d16-129">Lai pārietu uz nākamo darbību, atlasiet **Tālāk**.</span><span class="sxs-lookup"><span data-stu-id="16d16-129">Select **Next** to go to the next step.</span></span> 

1. <span data-ttu-id="16d16-130">Darbībā **Darbību apvienošana** atlasiet darbības nosaukumu un savas darbības sākuma laiku.</span><span class="sxs-lookup"><span data-stu-id="16d16-130">In the **Activity unification** step, choose the activity event and the start time of your activity.</span></span> 
   - <span data-ttu-id="16d16-131">**Obligātie lauki**</span><span class="sxs-lookup"><span data-stu-id="16d16-131">**Required fields**</span></span>
      - <span data-ttu-id="16d16-132">**Notikuma darbība**: Lauks, kas ir šīs darbības notikums.</span><span class="sxs-lookup"><span data-stu-id="16d16-132">**Event activity**: Field that is the event for this activity.</span></span>
      - <span data-ttu-id="16d16-133">**Laikspiedols**: Lauks, kas norāda uz darbības sākuma laiku.</span><span class="sxs-lookup"><span data-stu-id="16d16-133">**Timestamp**: Field that represents the start time of your activity.</span></span>

   - <span data-ttu-id="16d16-134">**Neobligātie lauki**</span><span class="sxs-lookup"><span data-stu-id="16d16-134">**Optional fields**</span></span>
      - <span data-ttu-id="16d16-135">**Papildu informācija**: Lauks ar atbilstošu informāciju par šo darbību.</span><span class="sxs-lookup"><span data-stu-id="16d16-135">**Additional detail**: Field with relevant information for this activity.</span></span>
      - <span data-ttu-id="16d16-136">**Ikona**: Ikona, kas vislabāk atbilst šim darbības tipam.</span><span class="sxs-lookup"><span data-stu-id="16d16-136">**Icon**: Icon that best represents this activity type.</span></span>
      - <span data-ttu-id="16d16-137">**Tīmekļa adrese**: Lauks, kurā ir vietrādis URL ar informāciju par šo darbību.</span><span class="sxs-lookup"><span data-stu-id="16d16-137">**Web address**: Field containing a URL with information about this activity.</span></span> <span data-ttu-id="16d16-138">Piemēram, transakciju sistēma, kas ģenerē šo darbību.</span><span class="sxs-lookup"><span data-stu-id="16d16-138">For example, the transactional system that sources this activity.</span></span> <span data-ttu-id="16d16-139">Šis URL var būt jebkurš lauks no datu avota, vai arī to var būvēt kā jaunu lauku, izmantojot Power Query transformāciju.</span><span class="sxs-lookup"><span data-stu-id="16d16-139">This URL can be any field from the data source, or it can be constructed as a new field using a Power Query transformation.</span></span> <span data-ttu-id="16d16-140">URL dati tiks glabāti entitījā *Apvienotās darbības*, kuru var patērēt lejupstraumē, izmantojot [API](apis.md).</span><span class="sxs-lookup"><span data-stu-id="16d16-140">The URL data will be stored in the *Unified Activity* entity, which can be consumed downstream using [APIs](apis.md).</span></span>
   
   :::image type="content" source="media/Activity_Wizard3.PNG" alt-text="Norādiet klienta darbības datus apvienoto darbību entitījā.":::

1. <span data-ttu-id="16d16-142">Lai pārietu uz nākamo darbību, atlasiet **Tālāk**.</span><span class="sxs-lookup"><span data-stu-id="16d16-142">Select **Next** to move to the next step.</span></span> <span data-ttu-id="16d16-143">Varat atlasīt **Pabeigt un pārskatīt**, lai saglabātu darbību ar darbības veidu iestatītu uz **Cita**.</span><span class="sxs-lookup"><span data-stu-id="16d16-143">You can select **Finish and review** to save the activity now with the activity type set to **Other**.</span></span> 

1. <span data-ttu-id="16d16-144">Darbībā **Darbības veids** izvēlieties darbības veidu un, ja vēlaties, atlasiet, vai vēlaties semantiski kartēt dažus darbību veidus, kurus izmantot citos Customer Insights apgabalos.</span><span class="sxs-lookup"><span data-stu-id="16d16-144">In the **Activity Type** step, choose the activity type and optionally select if you want to semantically map some of the activity types for use in other areas of Customer Insights.</span></span> <span data-ttu-id="16d16-145">Pašlaik *Abonements* un *SalesOrderLine* darbību veidi var tikt kartēti semantiski pēc tam, kad ir saņemta piekrišana kartēt laukus.</span><span class="sxs-lookup"><span data-stu-id="16d16-145">Currently, *Subscription* and *SalesOrderLine* activity types can be semantically mapped after agreeing to map the fields.</span></span> <span data-ttu-id="16d16-146">Ja jaunajai darbībai nav atbilstoša darbības veida, varat atlasīt *Cita* vai *Izveidot jaunu*, lai izveidotu pielāgotu darbības veidu.</span><span class="sxs-lookup"><span data-stu-id="16d16-146">If an activity type isn't relevant for the new activity, you can choose *Other* or *Create new* for a custom activity type.</span></span>

1. <span data-ttu-id="16d16-147">Lai pārietu uz nākamo darbību, atlasiet **Tālāk**.</span><span class="sxs-lookup"><span data-stu-id="16d16-147">Select **Next** to move to the next step.</span></span> 

1. <span data-ttu-id="16d16-148">Darbībā **Pārskatīt** pārbaudies savu atlasi.</span><span class="sxs-lookup"><span data-stu-id="16d16-148">In the **Review** step, verify your selections.</span></span> <span data-ttu-id="16d16-149">Atgriezieties pie iepriekšējām darbībām un, ja nepieciešams, atjauniniet informāciju.</span><span class="sxs-lookup"><span data-stu-id="16d16-149">Go back to any of the previous steps and update the information if necessary.</span></span>

   :::image type="content" source="media/Activity_Wizard5.PNG" alt-text="Pārskatiet darbībai norādītos laukus.":::
   
1. <span data-ttu-id="16d16-151">Atlasiet **Saglabāt darbību**, lai piemērotu izmaiņas, un atlasiet **Gatavs**, lai atgrieztos **Dati** > **Darbības**.</span><span class="sxs-lookup"><span data-stu-id="16d16-151">Select **Save activity** to apply your changes and select **Done** to go back to **Data** > **Activities**.</span></span> <span data-ttu-id="16d16-152">Šeit ir redzams, kuras darbības tiek rādītas laika skalā.</span><span class="sxs-lookup"><span data-stu-id="16d16-152">Here you see which activities are set to show in the timeline.</span></span> 

1. <span data-ttu-id="16d16-153">Lapā **Darbības** atlasiet **Palaist**, lai apstrādātu darbību.</span><span class="sxs-lookup"><span data-stu-id="16d16-153">On the **Activities** page, select **Run** to process the activity.</span></span> 

> [!TIP]
> <span data-ttu-id="16d16-154">Uzdevumiem/procesiem ir [seši statusu tipi](system.md#status-types).</span><span class="sxs-lookup"><span data-stu-id="16d16-154">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="16d16-155">Turklāt vairums procesu [ir atkarīgi no citiem pakārtotiem procesiem](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="16d16-155">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="16d16-156">Varat atlasīt procesa statusu, lai skatītu detalizētu informāciju par visa uzdevuma norisi.</span><span class="sxs-lookup"><span data-stu-id="16d16-156">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="16d16-157">Pēc tam, kad vienam no darba uzdevumiem esat atlasījis **Skatīt detalizētu informāciju**, jūs redzēsit papildinformāciju: apstrādes laiku, pēdējās apstrādes datumu un visas ar uzdevumu saistītas kļūdas un brīdinājumus.</span><span class="sxs-lookup"><span data-stu-id="16d16-157">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>


## <a name="manage-existing-activities"></a><span data-ttu-id="16d16-158">Esošo darbību pārvaldība</span><span class="sxs-lookup"><span data-stu-id="16d16-158">Manage existing activities</span></span>

<span data-ttu-id="16d16-159">Lapā **Dati** > **Darbības** varat skatīt visas saglabātās darbības un tās pārvaldīt.</span><span class="sxs-lookup"><span data-stu-id="16d16-159">On **Data** > **Activities**, you can view all your saved activities, and manage them.</span></span> <span data-ttu-id="16d16-160">Katru darbību uzrāda rinda, kurā ir iekļauta arī informācija par avotu, entitīju un darbības veidu.</span><span class="sxs-lookup"><span data-stu-id="16d16-160">Each activity is represented by a row that also includes details about the source, the entity, and the activity type.</span></span>

<span data-ttu-id="16d16-161">Atlasot darbību ir pieejamas šādas darbības.</span><span class="sxs-lookup"><span data-stu-id="16d16-161">The following actions are available when you select an activity.</span></span> 

- <span data-ttu-id="16d16-162">**Rediģēt**: Priekšstatījuma darbībā atver darbības iestatīšanu.</span><span class="sxs-lookup"><span data-stu-id="16d16-162">**Edit**: Opens the activity setup on the review step.</span></span> <span data-ttu-id="16d16-163">Šajā darbībā varat mainīt jebkuru vai visas konfigurācijas.</span><span class="sxs-lookup"><span data-stu-id="16d16-163">You can change any or all of the current configuration from this step.</span></span> <span data-ttu-id="16d16-164">Pēc konfigurācijas maiņas atlasiet **Saglabāt darbību** un **Palaist**, lai apstrādātu izmaiņas.</span><span class="sxs-lookup"><span data-stu-id="16d16-164">After changing the configuration, select **Save activity** and then select **Run** to process the changes.</span></span>

- <span data-ttu-id="16d16-165">**Pārdēvēt**: Atver dialogu, kurā var ievadīt citu atlasītās darbības nosaukumu.</span><span class="sxs-lookup"><span data-stu-id="16d16-165">**Rename**: Opens a dialog where you can enter a different name for the selected activity.</span></span> <span data-ttu-id="16d16-166">Lai veiktās izmaiņas stātos spēkā, atlasiet **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="16d16-166">Select **Save** to apply your changes.</span></span>

- <span data-ttu-id="16d16-167">**Dzēst**: Atver dialoglodziņu, kurā var apstriprināt atlasītās darbības dzēšanu.</span><span class="sxs-lookup"><span data-stu-id="16d16-167">**Delete**: Opens a dialog to confirm the deletion of the selected activity.</span></span> <span data-ttu-id="16d16-168">Varat vienlaikus arī dzēst vairāk nekā vienu darbību, atlasot darbības un pēc tam noklikšķinot uz dzēšanas ikonas.</span><span class="sxs-lookup"><span data-stu-id="16d16-168">You can also delete more than one activity at once by selecting the activities and then selecting the delete icon.</span></span> <span data-ttu-id="16d16-169">Lai apstiprinātu dzēšanu, atlasiet **Dzēst**.</span><span class="sxs-lookup"><span data-stu-id="16d16-169">Select **Delete** to confirm the deletion.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
