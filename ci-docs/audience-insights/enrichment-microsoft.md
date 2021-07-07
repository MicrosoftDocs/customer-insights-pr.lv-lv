---
title: Klientu profilu bagātināšana ar Microsoft datiem
description: Izmantojiet Microsoft īpašumtiesību datus, lai bagātinātu klientu datus ar zīmola un interešu radniecību.
ms.date: 06/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 1b11c325649b91ebb47cde924227eacedae64b7a
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305165"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a><span data-ttu-id="40fe4-103">Bagātiniet klientu profilus ar zīmola un interešu radniecību (priekšskatījums)</span><span class="sxs-lookup"><span data-stu-id="40fe4-103">Enrich customer profiles with brand and interest affinities (preview)</span></span>

<span data-ttu-id="40fe4-104">Izmantojiet Microsoft īpašumtiesību datus, lai bagātinātu klientu datus ar zīmola un interešu radniecību.</span><span class="sxs-lookup"><span data-stu-id="40fe4-104">Use Microsoft's proprietary data to enrich your customer data with brand and interest affinities.</span></span> <span data-ttu-id="40fe4-105">Šīs radniecības balstās uz datiem, kas iegūti no klientiem, kuru demogrāfiskie dati ir līdzīgi jūsu klientiem.</span><span class="sxs-lookup"><span data-stu-id="40fe4-105">These affinities are based on data from people with demographics similar to your customers.</span></span> <span data-ttu-id="40fe4-106">Šī informācija palīdz labāk izprast un segmentēt jūsu klientus, ņemot vērā viņu saistību ar noteiktiem zīmoliem un interesēm.</span><span class="sxs-lookup"><span data-stu-id="40fe4-106">This information helps you to better understand and segment your customers based on their affinities to specific brands and interests.</span></span>

<span data-ttu-id="40fe4-107">Rīkā Auditorijas ieskati ejiet uz **Dati** > **Bagātināšana**, lai [konfigurētu un skatītu bagātināšanu](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="40fe4-107">In audience insights, go to **Data** > **Enrichment** to [configure and view enrichments](enrichment-hub.md).</span></span>

<span data-ttu-id="40fe4-108">Lai konfigurētu zīmola saistību bagātināšanu, dodieties uz cilni **Atklāt** un atlasiet **Bagātināt manus datus** elementā **Zīmoli**.</span><span class="sxs-lookup"><span data-stu-id="40fe4-108">To configure brand affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Brands** tile.</span></span>

<span data-ttu-id="40fe4-109">Lai konfigurētu interešu saistību bagātināšanu, dodieties uz cilni **Atklāt** un atlasiet **Bagātināt manus datus** elementā **Intereses**.</span><span class="sxs-lookup"><span data-stu-id="40fe4-109">To configure interest affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Interests** tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="40fe4-110">![Zīmolu un interešu elementi](media/BrandsInterest-tile-Hub.png "Zīmolu un interešu elementi")</span><span class="sxs-lookup"><span data-stu-id="40fe4-110">![Brands and Interests tiles](media/BrandsInterest-tile-Hub.png "Brands and Interest tiles")</span></span>

## <a name="how-we-determine-affinities"></a><span data-ttu-id="40fe4-111">Kā tiek noteikta radniecība</span><span class="sxs-lookup"><span data-stu-id="40fe4-111">How we determine affinities</span></span>

<span data-ttu-id="40fe4-112">Mēs izmantojat Microsoft tiešsaistes meklēšanas datus, lai atrastu radniecību un intereses dažādos demogrāfijas segmentos (kurus nosaka pēc vecuma, dzimuma vai atrašanās vietas).</span><span class="sxs-lookup"><span data-stu-id="40fe4-112">We use Microsoft’s online search data to find affinities for brands and interests across various demographic segments (defined by age, gender, or location).</span></span> <span data-ttu-id="40fe4-113">Zīmola vai intereses tiešsaistes meklēšanas apjoms nosaka, cik daudz radniecības demogrāfiskajam segmentam ir ar šo zīmolu vai interesi, salīdzinot ar citiem segmentiem.</span><span class="sxs-lookup"><span data-stu-id="40fe4-113">The online search volume for a brand or interest determines how much affinity a demographic segment, compared to other segments, has to that brand or interest.</span></span>

## <a name="affinity-level-and-score"></a><span data-ttu-id="40fe4-114">Saistību līmenis un rezultāts</span><span class="sxs-lookup"><span data-stu-id="40fe4-114">Affinity level and score</span></span>

<span data-ttu-id="40fe4-115">Katrā bagātinātā klienta profilā mēs nodrošinām divas saistītās vērtības: saistību līmeni un saistību rezultātu.</span><span class="sxs-lookup"><span data-stu-id="40fe4-115">On every enriched customer profile, we provide two related values: affinity level and affinity score.</span></span> <span data-ttu-id="40fe4-116">Šīs vērtības palīdz noteikt, cik spēcīgas ir saistības šī profila demogrāfiskajam segmentam attiecībā uz zīmolu vai interesi salīdzinājumā ar citiem demogrāfiskajiem segmentiem.</span><span class="sxs-lookup"><span data-stu-id="40fe4-116">These values help you determine how strong the affinity is for that profile’s demographic segment, for a brand or interest, as compared to other demographic segments.</span></span>

<span data-ttu-id="40fe4-117">*Saistību līmenis* sastāv no četriem līmeņiem, un *saistību rādītājs* tiek aprēķināts pēc 100 punktu skalas, kura tiek kartēta uz saistību līmeņiem.</span><span class="sxs-lookup"><span data-stu-id="40fe4-117">*Affinity level* consists of four levels and *affinity score* is calculated on a 100-point scale that maps to the affinity levels.</span></span>


|<span data-ttu-id="40fe4-118">Saistību līmenis</span><span class="sxs-lookup"><span data-stu-id="40fe4-118">Affinity level</span></span> |<span data-ttu-id="40fe4-119">Saistības rādītājs</span><span class="sxs-lookup"><span data-stu-id="40fe4-119">Affinity score</span></span>  |
|---------|---------|
|<span data-ttu-id="40fe4-120">Ļoti augsts</span><span class="sxs-lookup"><span data-stu-id="40fe4-120">Very high</span></span>     | <span data-ttu-id="40fe4-121">85-100</span><span class="sxs-lookup"><span data-stu-id="40fe4-121">85-100</span></span>       |
|<span data-ttu-id="40fe4-122">Augsts</span><span class="sxs-lookup"><span data-stu-id="40fe4-122">High</span></span>     | <span data-ttu-id="40fe4-123">70-84</span><span class="sxs-lookup"><span data-stu-id="40fe4-123">70-84</span></span>        |
|<span data-ttu-id="40fe4-124">Vidēja</span><span class="sxs-lookup"><span data-stu-id="40fe4-124">Medium</span></span>     | <span data-ttu-id="40fe4-125">35-69</span><span class="sxs-lookup"><span data-stu-id="40fe4-125">35-69</span></span>        |
|<span data-ttu-id="40fe4-126">Zems</span><span class="sxs-lookup"><span data-stu-id="40fe4-126">Low</span></span>     | <span data-ttu-id="40fe4-127">1-34</span><span class="sxs-lookup"><span data-stu-id="40fe4-127">1-34</span></span>        |

<span data-ttu-id="40fe4-128">Atkarībā no tā, cik detalizēti vēlaties mērīt saistības, varat izmantot vai nu saistību līmeni, vai rezultātu.</span><span class="sxs-lookup"><span data-stu-id="40fe4-128">Depending on the granularity you would like for measuring the affinity, you can use either affinity level or score.</span></span> <span data-ttu-id="40fe4-129">Saistību rādītājs sniedz precīzāku vadīklu.</span><span class="sxs-lookup"><span data-stu-id="40fe4-129">Affinity score gives you more precise control.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="40fe4-130">Atbalstītās valstis/reģioni</span><span class="sxs-lookup"><span data-stu-id="40fe4-130">Supported countries/regions</span></span>

<span data-ttu-id="40fe4-131">Pašlaik tiek atbalstītas šādas valsts/reģiona opcijas: Austrālija, Kanāda (angļu valoda), Francija, Vācija, Apvienotā Karaliste vai Amerikas Savienotās Valstis (angļu valoda).</span><span class="sxs-lookup"><span data-stu-id="40fe4-131">We currently support the following country/region options: Australia, Canada (English), France, Germany, United Kingdom, or United States (English).</span></span>

<span data-ttu-id="40fe4-132">Lai atlasītu valsti vai reģionu, atveriet sadaļu **Zīmolu bagātināšana** vai **Interešu bagātināšana** un atlasiet **Mainīt** opciju pie **Valsts/Reģiona**.</span><span class="sxs-lookup"><span data-stu-id="40fe4-132">To select a country or region, open **Brands enrichment** or **Interest enrichment** and select **Change** next to **Country/Region**.</span></span> <span data-ttu-id="40fe4-133">Rūtī **Valsts/Reģiona iestatījumi** izvēlieties opciju un atlasiet **Piemērot**.</span><span class="sxs-lookup"><span data-stu-id="40fe4-133">In the **Country/Region settings** pane, choose an option and select **Apply**.</span></span>

### <a name="implications-related-to-country-selection"></a><span data-ttu-id="40fe4-134">Ar valsts atlasi saistītās sekas</span><span class="sxs-lookup"><span data-stu-id="40fe4-134">Implications related to country selection</span></span>

- <span data-ttu-id="40fe4-135">[Izvēloties savus zīmolus](#define-your-brands-or-interests), sistēma sniedz ieteikumus, kas balstīti uz atlasīto valsti vai reģionu.</span><span class="sxs-lookup"><span data-stu-id="40fe4-135">When [choosing your own brands](#define-your-brands-or-interests), the system provides suggestions based on the selected country or region.</span></span>

- <span data-ttu-id="40fe4-136">[Izvēloties nozari](#define-your-brands-or-interests), jūs iegūsiet svarīgākos zīmolus vai intereses, pamatojoties uz atlasīto valsti vai reģionu.</span><span class="sxs-lookup"><span data-stu-id="40fe4-136">When [choosing an industry](#define-your-brands-or-interests), you'll get the most relevant brands or interests based on the selected country or region.</span></span>

- <span data-ttu-id="40fe4-137">Ja [bagātināsiet profilus](#refresh-enrichment), mēs bagātināsim visus klientu profilus, no kuriem mēs iegūstam datus par atlasītajiem zīmoliem un interesēm, tostarp profilus, kuri neietilps atlasītajā valstī vai reģionā.</span><span class="sxs-lookup"><span data-stu-id="40fe4-137">When [enriching profiles](#refresh-enrichment), we'll enrich all customer profiles for which we get data for the selected brands and interests, including profiles that are not in the selected country or region.</span></span> <span data-ttu-id="40fe4-138">Piemēram, ja atlasāt Vāciju, mēs bagātināsim profilus, kuri atrodas ASV, ja mums būs pieejami dati par atlasītajiem zīmoliem un interesēm ASV.</span><span class="sxs-lookup"><span data-stu-id="40fe4-138">For example, if you selected Germany, we'll enrich profiles located in the United States if we have data available for the selected brands and interests in the US.</span></span>

## <a name="configure-enrichment"></a><span data-ttu-id="40fe4-139">Bagātināšanas konfigurēšana</span><span class="sxs-lookup"><span data-stu-id="40fe4-139">Configure enrichment</span></span>

<span data-ttu-id="40fe4-140">Vadītā pieredze palīdz bagātinājumu konfigurēšanas laikā.</span><span class="sxs-lookup"><span data-stu-id="40fe4-140">A guided experience helps you through the configuration of the enrichments.</span></span> 

### <a name="define-your-brands-or-interests"></a><span data-ttu-id="40fe4-141">Definēt zīmolus vai intereses</span><span class="sxs-lookup"><span data-stu-id="40fe4-141">Define your brands or interests</span></span>

<span data-ttu-id="40fe4-142">Izmantojot vienu vai abas iespējas, izvēlieties līdz pieciem zīmoliem vai interesēm:</span><span class="sxs-lookup"><span data-stu-id="40fe4-142">Choose up to five brands or interests using one or both of these options:</span></span>

- <span data-ttu-id="40fe4-143">**Nozare**: nolaižamajā sarakstā atlasiet savu nozari un pēc tam izvēlieties kādu no šīs nozares populārākajiem zīmoliem vai interesēm.</span><span class="sxs-lookup"><span data-stu-id="40fe4-143">**Industry**: Select your industry from the dropdown list and then choose from the top brands or interests for that industry.</span></span>
- <span data-ttu-id="40fe4-144">**Izvēlieties savu**: ievadiet ar organizāciju atbilstošu zīmolu vai ieinteresētību un pēc tam izvēlieties kādu no atbilstības noteikšanas ieteikumiem.</span><span class="sxs-lookup"><span data-stu-id="40fe4-144">**Choose your own**: Enter a brand or interest that is relevant to your organization and then choose from the matching suggestions.</span></span> <span data-ttu-id="40fe4-145">Ja mēs neuzskaitām zīmolu vai interesi, kuru meklējat, nosūtiet mums atsauksmi, izmantojot saiti **Ieteikt**.</span><span class="sxs-lookup"><span data-stu-id="40fe4-145">If we don't list a brand or interest you're looking for, send us feedback using the **Suggest** link.</span></span>

### <a name="review-enrichment-preferences"></a><span data-ttu-id="40fe4-146">Bagātināšanas preferenču pārskatīšana</span><span class="sxs-lookup"><span data-stu-id="40fe4-146">Review enrichment preferences</span></span>

<span data-ttu-id="40fe4-147">Pārskatiet noklusējuma bagātināšanas preferences un atjauniniet tās, kad tas ir nepieciešams.</span><span class="sxs-lookup"><span data-stu-id="40fe4-147">Review your default enrichment preferences and update them as needed.</span></span>

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Bagātinātā preferenču loga ekrānuzņēmums.":::

### <a name="select-entity-to-enrich"></a><span data-ttu-id="40fe4-149">Atlasiet bagātināmo entītiju</span><span class="sxs-lookup"><span data-stu-id="40fe4-149">Select entity to enrich</span></span>

<span data-ttu-id="40fe4-150">Atlasiet **Bagātinātā entitīja** un atlasiet datu kopu, kuru vēlaties bagātināt ar uzņēmuma datiem no Microsoft.</span><span class="sxs-lookup"><span data-stu-id="40fe4-150">Select **Enriched entity** and choose the data set you want to enrich with company data from the Microsoft.</span></span> <span data-ttu-id="40fe4-151">Varat atlasīt entītiju Klients, lai bagātinātu visus klientu profilus, vai atlasīt segmenta entītiju, lai bagātinātu tikai šajā segmentā iekļautos klientu profilus.</span><span class="sxs-lookup"><span data-stu-id="40fe4-151">You can select the Customer entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

### <a name="map-your-fields"></a><span data-ttu-id="40fe4-152">Lauku kartēšana</span><span class="sxs-lookup"><span data-stu-id="40fe4-152">Map your fields</span></span>

<span data-ttu-id="40fe4-153">Kartējiet laukus no savas vienotās klienta entītijas, lai definētu demogrāfisko segmentu, kuru sistēma vēlas, lai izmantojat jūsu klientu datu bagātināšanai.</span><span class="sxs-lookup"><span data-stu-id="40fe4-153">Map fields from your unified customer entity to define the demographic segment you want the system to use for enriching your customer data.</span></span> <span data-ttu-id="40fe4-154">Kartējiet valsti/reģionu un vismaz Dzimšanas datu vai Dzimuma atribūtus.</span><span class="sxs-lookup"><span data-stu-id="40fe4-154">Map Country/Region and at least Date of Birth or Gender attributes.</span></span> <span data-ttu-id="40fe4-155">Turklāt ir jākartē vismaz viens no atribūtiem — Pilsēta (un novads/rajons) vai pasta indekss.</span><span class="sxs-lookup"><span data-stu-id="40fe4-155">Additionally, you must map at least one of City (and State/Province) or Postal code.</span></span> <span data-ttu-id="40fe4-156">Atlasiet **Rediģēt**, lai definētu lauku kartēšanu, un atlasiet **Piemērot**, kad esat to izdarījis.</span><span class="sxs-lookup"><span data-stu-id="40fe4-156">Select **Edit** to define the mapping of the fields and select **Apply** when you're done.</span></span> <span data-ttu-id="40fe4-157">Atlasiet **Saglabāt**, lai pabeigtu lauka kartēšanu.</span><span class="sxs-lookup"><span data-stu-id="40fe4-157">Select **Save** to complete the field mapping.</span></span>

<span data-ttu-id="40fe4-158">Tiek atbalstīti šādi(-as) formāti un vērtības (vērtības nav reģistrjutīgas):</span><span class="sxs-lookup"><span data-stu-id="40fe4-158">The following formats and values are supported (values are not case-sensitive):</span></span>

- <span data-ttu-id="40fe4-159">**Dzimšanas datums** : Iesakām, lai datu pievienošanas laikā dzimšanas datums tiek pārvērsts par DateTime tipu.</span><span class="sxs-lookup"><span data-stu-id="40fe4-159">**Date of Birth**: We recommend that date of birth is converted to DateTime type during data ingestion.</span></span> <span data-ttu-id="40fe4-160">Vai arī tā var būt virkne [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) formātā “yyyy-MM-dd” vai “yyyy-MM-ddTHH:mm:ss”.</span><span class="sxs-lookup"><span data-stu-id="40fe4-160">Alternatively, it can be a string in [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) format "yyyy-MM-dd" or "yyyy-MM-ddTHH:mm:ss".</span></span>
- <span data-ttu-id="40fe4-161">**Dzimums**: Vīrietis, sieviete, nezināms.</span><span class="sxs-lookup"><span data-stu-id="40fe4-161">**Gender**: Male, Female, Unknown.</span></span>
- <span data-ttu-id="40fe4-162">**Pasta indekss**: Piecciparu pasta indeksi Amerikas Savienotajās Valstīs, standarta pasta indekss, ko izmanto citur.</span><span class="sxs-lookup"><span data-stu-id="40fe4-162">**Postal code**: Five-digit ZIP codes for United States, standard postal code everywhere else.</span></span>
- <span data-ttu-id="40fe4-163">**Pilsēta**: Pilsētas nosaukums angļu valodā.</span><span class="sxs-lookup"><span data-stu-id="40fe4-163">**City**: City name in English.</span></span>
- <span data-ttu-id="40fe4-164">**Štats/Province**: Divu burtu saīsinājums Amerikas Savienotajās Valstīs (ASV) un Kanādā.</span><span class="sxs-lookup"><span data-stu-id="40fe4-164">**State/Province**: Two-letter abbreviation for the US and Canada.</span></span> <span data-ttu-id="40fe4-165">Divu vai trīs burtu saīsinājums Austrālijā.</span><span class="sxs-lookup"><span data-stu-id="40fe4-165">Two- or three-letter abbreviation for Australia.</span></span> <span data-ttu-id="40fe4-166">Nav piemērojams Francijai, Vācijai vai Apvienotajai Karalistei.</span><span class="sxs-lookup"><span data-stu-id="40fe4-166">Not applicable for France, Germany, or the UK.</span></span>
- <span data-ttu-id="40fe4-167">**Valsts/Reģions**:</span><span class="sxs-lookup"><span data-stu-id="40fe4-167">**Country/Region**:</span></span>

  - <span data-ttu-id="40fe4-168">US: Amerikas Savienotās Valstis, ASV, US, Amerika</span><span class="sxs-lookup"><span data-stu-id="40fe4-168">US: United States of America, United States, USA, US, America</span></span>
  - <span data-ttu-id="40fe4-169">CA: Kanāda, CA</span><span class="sxs-lookup"><span data-stu-id="40fe4-169">CA: Canada, CA</span></span>
  - <span data-ttu-id="40fe4-170">GB: Apvienotā Karaliste, AK, Lielbritānija, GB, Lielbritānijas un Ziemeļīrijas Apvienotā Karaliste, Lielbritānijas Apvienotā Karaliste</span><span class="sxs-lookup"><span data-stu-id="40fe4-170">GB: United Kingdom, UK, Great Britain, GB, United Kingdom of Great Britain and Northern Ireland, United Kingdom of Great Britain</span></span>
  - <span data-ttu-id="40fe4-171">AU: Austrālijā, AU, Austrālijas Savienība</span><span class="sxs-lookup"><span data-stu-id="40fe4-171">AU: Australia, AU, Commonwealth of Australia</span></span>
  - <span data-ttu-id="40fe4-172">FR: Francija, FR, Francijas Republika</span><span class="sxs-lookup"><span data-stu-id="40fe4-172">FR: France, FR, French Republic</span></span>
  - <span data-ttu-id="40fe4-173">DE: Vācija, vācu valoda, Deutschland, Allemagne, DE, Vācijas Federatīvā Republika, Vācijas Republika</span><span class="sxs-lookup"><span data-stu-id="40fe4-173">DE: Germany, German, Deutschland, Allemagne, DE, Federal Republic of Germany, Republic of Germany</span></span>

## <a name="review-and-name-the-enrichment"></a><span data-ttu-id="40fe4-174">Bagātinājuma pārskatīšana un dēvēšana</span><span class="sxs-lookup"><span data-stu-id="40fe4-174">Review and name the enrichment</span></span>

<span data-ttu-id="40fe4-175">Visbeidzot, varat pārskatīt informāciju un nodrošināt bagātinājuma nosaukumu.</span><span class="sxs-lookup"><span data-stu-id="40fe4-175">Finally, you get to review the information and provide a name for the enrichment.</span></span>

:::image type="content" source="media/enrichment-interests-summary.png" alt-text="Interešu pārskatīšanas un dēvēšanas lapa.":::

## <a name="refresh-enrichment"></a><span data-ttu-id="40fe4-177">Atsvaidzināt bagātināšanu</span><span class="sxs-lookup"><span data-stu-id="40fe4-177">Refresh enrichment</span></span>

<span data-ttu-id="40fe4-178">Pēc zīmolu, interešu un demogrāfijas lauku kartēšanas palaidiet bagātināšanu.</span><span class="sxs-lookup"><span data-stu-id="40fe4-178">Run the enrichment after configuring brands, interests, and the field mapping for demographics.</span></span> <span data-ttu-id="40fe4-179">Lai sāktu procesu, atlasiet **Palaist** zīmola vai interešu konfigurācijas lapā.</span><span class="sxs-lookup"><span data-stu-id="40fe4-179">To start the process, select **Run** on the brand or interest configuration page.</span></span> <span data-ttu-id="40fe4-180">Turklāt varat ļaut sistēmai automātiski palaist bagātināšanu kā plānotas atsvaidzināšanas daļu.</span><span class="sxs-lookup"><span data-stu-id="40fe4-180">Additionally, you can let the system run the enrichment automatically as part of a scheduled refresh.</span></span>

<span data-ttu-id="40fe4-181">Atkarībā no jūsu klientu datu apjoma bagātināšanas izpilde var aizņemt vairākas minūtes.</span><span class="sxs-lookup"><span data-stu-id="40fe4-181">Depending on the size of your customer data, it may take several minutes for an enrichment run to complete.</span></span>

> [!TIP]
> <span data-ttu-id="40fe4-182">Uzdevumiem/procesiem ir [seši statusu tipi](system.md#status-types).</span><span class="sxs-lookup"><span data-stu-id="40fe4-182">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="40fe4-183">Turklāt vairums procesu [ir atkarīgi no citiem pakārtotiem procesiem](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="40fe4-183">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="40fe4-184">Varat atlasīt procesa statusu, lai skatītu detalizētu informāciju par visa uzdevuma norisi.</span><span class="sxs-lookup"><span data-stu-id="40fe4-184">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="40fe4-185">Atlasot opciju **Skatīt detalizētu informāciju** par kādu no uzdevumiem, jums tiks sniegta papildinformācija: apstrādes laiks, pēdējās apstrādes datums un visas ar uzdevumu saistītās kļūdas un brīdinājumi.</span><span class="sxs-lookup"><span data-stu-id="40fe4-185">After selecting **See details** for one of the job's tasks, you'll find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="40fe4-186">Bagātināšanas rezultāti</span><span class="sxs-lookup"><span data-stu-id="40fe4-186">Enrichment results</span></span>

<span data-ttu-id="40fe4-187">Pēc bagātināšanas procesa palaišanas dodieties uz **Manas bagātināšanas**, lai pārskatītu kopējo bagātināto klientu skaitu un zīmolu vai interešu sadalījumu bagātināto klientu profilos.</span><span class="sxs-lookup"><span data-stu-id="40fe4-187">After running the enrichment process, go to **My enrichments** to review the total number of enriched customers and a breakdown of brands or interests in the enriched customer profiles.</span></span>

:::image type="content" source="media/my-enrichments.png" alt-text="Rezultātu priekšskatījums pēc bagātināšanas procesa izpildes":::

<span data-ttu-id="40fe4-189">Pārskatiet bagātinātos datus, diagrammā atlasot **Skatīt bagātinātos datus**.</span><span class="sxs-lookup"><span data-stu-id="40fe4-189">Review the enriched data by selecting **View enriched data** in the chart.</span></span> <span data-ttu-id="40fe4-190">Zīmolu bagātinātie dati dodas uz entītiju **BrandAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="40fe4-190">Enriched data for brands goes to the **BrandAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="40fe4-191">Interešu dati atrodas entītijā **InterestAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="40fe4-191">Data for interests is in the **InterestAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="40fe4-192">Šīs entītijas ir uzskaitītas arī grupā **Bagātināšana** sadaļā **Dati** > **Entītijas**.</span><span class="sxs-lookup"><span data-stu-id="40fe4-192">You'll also find these entities listed in the **Enrichment** group in **Data** > **Entities**.</span></span>

## <a name="see-enrichment-data-on-the-customer-card"></a><span data-ttu-id="40fe4-193">Skatiet informāciju par produkta bagātināšanu klienta kartītē</span><span class="sxs-lookup"><span data-stu-id="40fe4-193">See enrichment data on the customer card</span></span>

<span data-ttu-id="40fe4-194">Zīmola un intereses radniecību var apskatīt arī atsevišķās klientu kartītēs.</span><span class="sxs-lookup"><span data-stu-id="40fe4-194">Brand and interest affinities can also be viewed on individual customer cards.</span></span> <span data-ttu-id="40fe4-195">Atveriet sadaļu **Klienti** un atlasiet klienta profilu.</span><span class="sxs-lookup"><span data-stu-id="40fe4-195">Go to **Customers** and select a customer profile.</span></span> <span data-ttu-id="40fe4-196">Klienta kartē ir atrodamas to zīmolu vai interešu diagrammas, kuras ir saistītas ar šī klienta demogrāfiskā profila lietotājiem.</span><span class="sxs-lookup"><span data-stu-id="40fe4-196">In the customer card, you'll find charts for the brands or interests that people in that customer's demographic profile have affinity for.</span></span>

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Klienta kartīte ar bagātinātiem datiem":::

## <a name="next-steps"></a><span data-ttu-id="40fe4-198">Nākamās darbības</span><span class="sxs-lookup"><span data-stu-id="40fe4-198">Next steps</span></span>

<span data-ttu-id="40fe4-199">Pilnveidojiet savus bagātinātos klientu datus.</span><span class="sxs-lookup"><span data-stu-id="40fe4-199">Build on top of your enriched customer data.</span></span> <span data-ttu-id="40fe4-200">Veidojiet [Segmentus](segments.md) un [Pasākumus](measures.md) un pat [eksportējiet datus](export-destinations.md), lai nodrošinātu klientiem personalizētu pieredzi.</span><span class="sxs-lookup"><span data-stu-id="40fe4-200">Create [Segments](segments.md) and [Measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
