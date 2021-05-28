---
title: Uz darbībām balstīti segmenta ieteikumi.
description: Ļaujiet algoritmiskā mācīšanās jums palīdzēt atrast jaunus un aizraujošus segmentus, kas balstīti uz klientu darbību.
ms.date: 05/11/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
ms.openlocfilehash: 14d9d4f0df6b5835f21fb63447d05853ee98a757
ms.sourcegitcommit: 8341fa964365c185b65bc4b71fc0c695ea127dc0
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 05/14/2021
ms.locfileid: "6034093"
---
# <a name="suggested-segments-based-on-activity-data-preview"></a><span data-ttu-id="087ac-103">Uz darbībām balstīti segmenta ieteikumi (priekšskatījums)</span><span class="sxs-lookup"><span data-stu-id="087ac-103">Suggested segments based on activity data (preview)</span></span>

<span data-ttu-id="087ac-104">Atklājiet jūsu klientus interesējošos segmentus, balstoties uz klientu darbību datiem, kuri tiek lietoti ar Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="087ac-104">Discover interesting segments of your customers based on customer activity data that is ingested to Customer Insights.</span></span> <span data-ttu-id="087ac-105">Darbību dati ir, piemēram, transakcijas, atbalsta sarunas ilgums, iegāde vai atgriešana.</span><span class="sxs-lookup"><span data-stu-id="087ac-105">Examples of activity data are transactions, support call duration, purchases, or returns.</span></span> <span data-ttu-id="087ac-106">Lai ieteiktu segmentus, darbības dati tiek analizēti, lai noteiktu atkārtojamību, biežumu un naudas vērtību (vai ilgumu).</span><span class="sxs-lookup"><span data-stu-id="087ac-106">To suggest segments, activity data gets analyzed for recency, frequency, and monetary value (or duration).</span></span> <span data-ttu-id="087ac-107">Vai arī var ģenerēt [ieteiktos segmentus, lai uzlabotu pasākumu vai labāk saprastu atribūta ietekmi](suggested-segments.md).</span><span class="sxs-lookup"><span data-stu-id="087ac-107">Alternatively, you can generate [suggested segments to improve a measure or better understand what influences an attribute](suggested-segments.md).</span></span>

:::image type="content" source="media/suggested-segments-tab.png" alt-text="Cilne Ieteicamie segmenti, kurā parādīti segmenta ieteikumi uz darbībām un atribūtiem balstītiem segmentiem.":::

## <a name="categorize-customers-by-activity"></a><span data-ttu-id="087ac-109">Kategorizēt klientus pēc darbības</span><span class="sxs-lookup"><span data-stu-id="087ac-109">Categorize customers by activity</span></span>

<span data-ttu-id="087ac-110">Izmantojot [darbības datus](activities.md), kas pieejami programmā Customer Insights, mēs varam ģenerēt ieteikumus, kas attiecas uz klientu grupām:</span><span class="sxs-lookup"><span data-stu-id="087ac-110">With [activity data](activities.md) available in Customer Insights, we can generate suggestions that represent customer groups:</span></span>

- <span data-ttu-id="087ac-111">visaktīvākie klienti</span><span class="sxs-lookup"><span data-stu-id="087ac-111">most active customers</span></span> 
- <span data-ttu-id="087ac-112">klineti, kas visvairāk iepirkušies</span><span class="sxs-lookup"><span data-stu-id="087ac-112">customers that have made the most purchases</span></span> 
- <span data-ttu-id="087ac-113">klienti, kas ģenerēja vislielākos ieņēmumus</span><span class="sxs-lookup"><span data-stu-id="087ac-113">customers that generated the most revenue</span></span> 
- <span data-ttu-id="087ac-114">klienti, kas pēdējā laikā nav bijuši aktīvi</span><span class="sxs-lookup"><span data-stu-id="087ac-114">customers who haven’t been active lately</span></span> 
- <span data-ttu-id="087ac-115">klienti, kas bieži mijiedarbojas ar uzņēmumu</span><span class="sxs-lookup"><span data-stu-id="087ac-115">customers who frequently interact with your business</span></span>  

<span data-ttu-id="087ac-116">Ja jums ir mazumtirdzniecības uzņēmums, varat uzzināt, kuri klienti rada visvairāk ieņēmumu, un apbalvot viņus ar sīcēju.</span><span class="sxs-lookup"><span data-stu-id="087ac-116">If you have a retail business, you could find out which customers generate the most revenue and reward them with a coupon.</span></span> <span data-ttu-id="087ac-117">Varat arī identificēt gadījuma klientus un piedāvāt viņiem pievienoties apbalvojumu programmai, lai viņi biežāk apmeklētu jūsu uzņēmumu.</span><span class="sxs-lookup"><span data-stu-id="087ac-117">Or you can identify occasional customers and offer them to join a rewards program so they visit your business more often.</span></span>
<span data-ttu-id="087ac-118">Ja jūs esat veselības aprūpes uzņēmums, kas sniedz publisku veselības aprūpi un jūsu mērķis ir minimizēt atsevišķas sasācības izmaksas.</span><span class="sxs-lookup"><span data-stu-id="087ac-118">If you're in the healthcare business providing public healthcare and your goal is to minimize the expenses for individual patients.</span></span> <span data-ttu-id="087ac-119">Veids, kā to izdarīt, varētu būt samazināt periodisko vizīti, pēc iespējas nodrošinot pēc iespējas labāko rūpību pēc iespējas dažos apmeklējumos.</span><span class="sxs-lookup"><span data-stu-id="087ac-119">A way to do so could be to reduce recurring visits by providing best possible care in as few visits as possible.</span></span> <span data-ttu-id="087ac-120">Šajā gadījumā jūsu mērķis ir uzturēt zemu apmeklējuma biežumu un minimizēt periodiskās izmaksas attiecībā uz jutīgajām vietām.</span><span class="sxs-lookup"><span data-stu-id="087ac-120">In this case, your goal is to keep the visit frequency low and minimize recurring cost for the patients.</span></span> <span data-ttu-id="087ac-121">Vai arī varat identificēt ar klientiem saistītas problēmas, kam bieži ir tikšanās un augstas periodiskās izmaksas, un analizēt šos pieteikumus, lai uzlabotu indivīda uzlabošanos.</span><span class="sxs-lookup"><span data-stu-id="087ac-121">Or you can identify segments of patients who have frequent appointments and high recurring costs and analyze these cases to improve the treatment of the individual.</span></span> 

## <a name="required-data"></a><span data-ttu-id="087ac-122">Nepieciešamie dati</span><span class="sxs-lookup"><span data-stu-id="087ac-122">Required data</span></span>

<span data-ttu-id="087ac-123">Ieteikumi tiek ģenerēti, pamatojoties uz atlasītajiem ievades datiem.</span><span class="sxs-lookup"><span data-stu-id="087ac-123">Suggestions are generated based on the selected input data.</span></span> 

- <span data-ttu-id="087ac-124">Klientu profili: visi noteikta segmenta klienti vai dalībnieki.</span><span class="sxs-lookup"><span data-stu-id="087ac-124">Customer profiles: All customers or members of a specific segment.</span></span> 

- <span data-ttu-id="087ac-125">Laika periods: pagājušais mēnesis, pēdējais gads vai jebkurš pielāgots laika posms.</span><span class="sxs-lookup"><span data-stu-id="087ac-125">Time period: Last month, last year, or any custom time frame.</span></span>

- <span data-ttu-id="087ac-126">Darbības tips: pirkumi, mazumtirdzniecības transakcijas, tiešsaistes transakcijas, klientu atbalsta pieteikumi, abonementi utt.</span><span class="sxs-lookup"><span data-stu-id="087ac-126">Activity type: purchases, retail transactions, online transactions, customer support cases, subscriptions, and so on.</span></span>  

- <span data-ttu-id="087ac-127">Entītija programmā Customer Insights, kurā ir darbības dati: noteiktas darbības entītija vai UnifiedActivity entītija.</span><span class="sxs-lookup"><span data-stu-id="087ac-127">Entity in Customer Insights that contains the activity data: The UnifiedActivity entity or the entity for a specific activity.</span></span> 

- <span data-ttu-id="087ac-128">Atkarībā no jūsu uzņēmējdarbības prasībām tajā iekļaujams: resns, biežums vai naudas izteiksmē.</span><span class="sxs-lookup"><span data-stu-id="087ac-128">Dimensions to include: Recency, frequency, or monetary dimension, depending on your business requirements.</span></span>

## <a name="generate-suggested-segments"></a><span data-ttu-id="087ac-129">Izveidot ieteiktos segmentus</span><span class="sxs-lookup"><span data-stu-id="087ac-129">Generate suggested segments</span></span>

1. <span data-ttu-id="087ac-130">Ejiet uz **Segmenti**.</span><span class="sxs-lookup"><span data-stu-id="087ac-130">Go to **Segments**.</span></span>

1. <span data-ttu-id="087ac-131">Atlasiet cilni **Ieteikumi (priekšskatījums)**.</span><span class="sxs-lookup"><span data-stu-id="087ac-131">Select the **Suggestions (preview)** tab.</span></span>

1. <span data-ttu-id="087ac-132">Atlasiet **Atrast jaunus ieteikumus** un izvēlieties **Skatīt vai paredzēt klientu uzvedību**.</span><span class="sxs-lookup"><span data-stu-id="087ac-132">Select **Find new suggestions** and choose **See or anticipate customer behavior**.</span></span> <span data-ttu-id="087ac-133">Atlasiet vienumu **Sākt**, lai palaistu vadīto pieredzi.</span><span class="sxs-lookup"><span data-stu-id="087ac-133">Select **Start** to run the guided experience.</span></span>

   :::image type="content" source="media/suggested-segments-activity-wizard.png" alt-text="Konfigurēšanas vedņa pirmais solis ieteiktam segmentam, pamatojoties uz darbību.":::

1. <span data-ttu-id="087ac-135">Norādiet nepieciešamos ievades datus un atlasiet **Tālāk**.</span><span class="sxs-lookup"><span data-stu-id="087ac-135">Provide the required input data and select **Next** proceed.</span></span>

   - <span data-ttu-id="087ac-136">Izvēlieties klientus: iekļaujiet visus klientus vai noteiktu segmentu.</span><span class="sxs-lookup"><span data-stu-id="087ac-136">Choose customers: Include all customers or a specific segment.</span></span>
   - <span data-ttu-id="087ac-137">Izvēlieties darbību: atlasiet darbības tipu un entītijas, kas apraksta darbību.</span><span class="sxs-lookup"><span data-stu-id="087ac-137">Choose activity: Select the activity type and the entities that describe the activity.</span></span>
   - <span data-ttu-id="087ac-138">Preferences: iestatiet apsveramo laika periodu, ieteikumu faktorus un kartējiet atribūtus.</span><span class="sxs-lookup"><span data-stu-id="087ac-138">Preferences: Set the time period to consider, the factors for suggestions, and map the attributes.</span></span>

1. <span data-ttu-id="087ac-139">Pārskatiet savu ievadi un atlasiet opciju **Palaist**, lai palaistu modeli un ģenerētu ieteikumus.</span><span class="sxs-lookup"><span data-stu-id="087ac-139">Review your input and select **Run** to run the model and generate suggestions.</span></span>

1. <span data-ttu-id="087ac-140">Atkarībā no klientu profilu un atlasīto darbību skaita pabeigšana var ilgt dažas minūtes.</span><span class="sxs-lookup"><span data-stu-id="087ac-140">Depending on the number of customer profiles and selected activities, it can take a few minutes to complete.</span></span> 

<span data-ttu-id="087ac-141">Pēc ieteikumu ģenerēšanas tos varat filtrēt pēc kategoriju kategorijas vai vērtības, kas jūs interesē visvairāk.</span><span class="sxs-lookup"><span data-stu-id="087ac-141">After generating the suggestions, you can filter them by the dimension or value you're most interested in.</span></span> 

## <a name="view-details-of-a-suggested-segment"></a><span data-ttu-id="087ac-142">Ieteicamā segmenta detalizētas informācijas skatīšana</span><span class="sxs-lookup"><span data-stu-id="087ac-142">View details of a suggested segment</span></span>

<span data-ttu-id="087ac-143">Kad ieteikumi ir ģenerēti, tie ir uzskaitīti sadaļā **Segmenti** > **Ieteikumi (priekšskatījums)** **Uz darbībām balstīti ieteikumi**.</span><span class="sxs-lookup"><span data-stu-id="087ac-143">Once the suggestions are generated, you'll find them listed on **Segments** > **Suggestions (preview)** in the **Activity-based suggestions** section.</span></span>

:::image type="content" source="media/suggested-segments-details.png" alt-text="Izvērsta sānu rūts, kurā ir detalizēti ieteiktā segmenta dati.":::

<span data-ttu-id="087ac-145">Lai skatītu detalizētu informāciju par šo segmentu, atlasiet vienumu **Skatīt ierosinājumu** par ieteikto segmentu.</span><span class="sxs-lookup"><span data-stu-id="087ac-145">Select **See suggestion** on a suggested segment to view the details of that segment.</span></span> <span data-ttu-id="087ac-146">Sānu rūtī ir sniegta detalizēta informācija, piemēram, cik lielā mērā katrs aspekts ir salīdzināts ar mērķa grupu.</span><span class="sxs-lookup"><span data-stu-id="087ac-146">The side pane provides details like the extent of each dimension in comparison to the target group.</span></span> <span data-ttu-id="087ac-147">Turklāt tiek izcelts arī segmentā iespējamo dalībnieku skaits un atbilstošā klientu kopsummas procentuālā vērtība.</span><span class="sxs-lookup"><span data-stu-id="087ac-147">It also highlights the number of potential members in the segment and the corresponding percentage of the total customers.</span></span> <span data-ttu-id="087ac-148">Ja ierosinājumu vēlaties saglabāt kā segmentu, atlasiet opciju **Izveidot segmentu**.</span><span class="sxs-lookup"><span data-stu-id="087ac-148">If you want to keep the suggestion as a segment, select **Create segment**.</span></span>    

## <a name="save-a-suggestion-as-a-segment"></a><span data-ttu-id="087ac-149">Ieteikuma saglabāšana par segmentu</span><span class="sxs-lookup"><span data-stu-id="087ac-149">Save a suggestion as a segment</span></span>

1. <span data-ttu-id="087ac-150">Dodieties uz **Segmenti** > **Ieteikumi (priekšskatījums)**.</span><span class="sxs-lookup"><span data-stu-id="087ac-150">Go to **Segments** > **Suggestions (preview)**.</span></span>

1. <span data-ttu-id="087ac-151">Atlasiet saglabājamo segmentu.</span><span class="sxs-lookup"><span data-stu-id="087ac-151">Select the segment you want to save.</span></span> 

1. <span data-ttu-id="087ac-152">Sānu rūtī atlasiet **Izveidot segmentu**.</span><span class="sxs-lookup"><span data-stu-id="087ac-152">In the side pane, select **Create segment**.</span></span> 

1. <span data-ttu-id="087ac-153">Pēc segmenta saglabāšanas tas tiks rādīts segmentu sarakstā cilnē **Visi segmenti**. Tagad to var [atsvaidzināt vai dzēst, piemēram, kā jebkuru citu segmentu](segments.md).</span><span class="sxs-lookup"><span data-stu-id="087ac-153">After saving the segment, it will show in the list of segments on the **All segments** tab. It can now be [refreshed or deleted like any other segment](segments.md).</span></span> <span data-ttu-id="087ac-154">Segmenta detalizēto informāciju nevar rediģēt.</span><span class="sxs-lookup"><span data-stu-id="087ac-154">You can't edit the segment details.</span></span> <span data-ttu-id="087ac-155">Tomēr varat mainīt ieteikumu ievades kritērijus un ģenerēt dažādus ieteikumus.</span><span class="sxs-lookup"><span data-stu-id="087ac-155">However, you can change the input criteria for the suggestions and generate different suggestions.</span></span>

## <a name="refresh-or-edit-a-set-of-suggestions"></a><span data-ttu-id="087ac-156">Ieteikumu kopas atsvaidzināšana vai rediģēšana</span><span class="sxs-lookup"><span data-stu-id="087ac-156">Refresh or edit a set of suggestions</span></span>

1. <span data-ttu-id="087ac-157">Dodieties uz **Segmenti** > **Ieteikumi (priekšskatījums)** un meklējiet segmentu sadaļā **Uz darbībām balstīti ieteikumi**.</span><span class="sxs-lookup"><span data-stu-id="087ac-157">Go to **Segments** > **Suggestions (preview)** and look for the segment in the **Activity-based suggestions** section.</span></span>

1. <span data-ttu-id="087ac-158">Atlasiet **Atsvaidzināt ieteikumus**, lai atsvaidzinātu ieteikumus, saglabājot konfigurētos atribūtus.</span><span class="sxs-lookup"><span data-stu-id="087ac-158">Select **Refresh suggestions** to refresh the suggestions while keeping configured attributes.</span></span> <span data-ttu-id="087ac-159">Vai atlasiet vienumu **Rediģēt ieteikumus**, lai modificētu konfigurētos atribūtus.</span><span class="sxs-lookup"><span data-stu-id="087ac-159">Or select **Edit suggestions** to modify the configured attributes.</span></span> <span data-ttu-id="087ac-160">Sistēma procesu no jauna palaidiet vēlreiz, ģenerējiet segmenta ieteikumus, pamatojoties uz jaunākajiem datiem, un aizstās pašreizējos ieteikumus.</span><span class="sxs-lookup"><span data-stu-id="087ac-160">The system will rerun the process, generate segment suggestions based on the latest data, and replace the current suggestions.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
