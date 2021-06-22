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
ms.openlocfilehash: e92360bb886739cfe477ce1d2eb62219228a0292
ms.sourcegitcommit: d4b4053f6ee8f60f1a214982c4726c9de84615ef
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 06/14/2021
ms.locfileid: "6245716"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a><span data-ttu-id="592be-103">Bagātiniet klientu profilus ar zīmola un interešu radniecību (priekšskatījums)</span><span class="sxs-lookup"><span data-stu-id="592be-103">Enrich customer profiles with brand and interest affinities (preview)</span></span>

<span data-ttu-id="592be-104">Izmantojiet Microsoft īpašumtiesību datus, lai bagātinātu klientu datus ar zīmola un interešu radniecību.</span><span class="sxs-lookup"><span data-stu-id="592be-104">Use Microsoft's proprietary data to enrich your customer data with brand and interest affinities.</span></span> <span data-ttu-id="592be-105">Šie apstākļi tiek noteikti, vadoties pēc datiem, kas iegūti no cilvēkiem ar līdzīgiem demogrāfiskajiem datiem līdz jūsu klientiem.</span><span class="sxs-lookup"><span data-stu-id="592be-105">These affinities are determined based on data from people with similar demographics to your customers.</span></span> <span data-ttu-id="592be-106">Šī informācija palīdz labāk izprast un segmentēt jūsu klientus, ņemot vērā viņu saistību ar noteiktiem zīmoliem un interesēm.</span><span class="sxs-lookup"><span data-stu-id="592be-106">This information helps you to better understand and segment your customers based on their affinities to specific brands and interests.</span></span>

<span data-ttu-id="592be-107">Rīkā Auditorijas ieskati ejiet uz **Dati** > **Bagātināšana**, lai [konfigurētu un skatītu bagātināšanu](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="592be-107">In audience insights, go to **Data** > **Enrichment** to [configure and view enrichments](enrichment-hub.md).</span></span>

<span data-ttu-id="592be-108">Lai konfigurētu zīmola saistību bagātināšanu, dodieties uz cilni **Atklāt** un atlasiet **Bagātināt manus datus** elementā **Zīmoli**.</span><span class="sxs-lookup"><span data-stu-id="592be-108">To configure brand affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Brands** tile.</span></span>

<span data-ttu-id="592be-109">Lai konfigurētu interešu saistību bagātināšanu, dodieties uz cilni **Atklāt** un atlasiet **Bagātināt manus datus** elementā **Intereses**.</span><span class="sxs-lookup"><span data-stu-id="592be-109">To configure interest affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Interests** tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="592be-110">![Zīmolu un interešu rūtis](media/BrandsInterest-tile-Hub.png "Zīmolu un interešu rūtis")</span><span class="sxs-lookup"><span data-stu-id="592be-110">![Brands & Interests tiles](media/BrandsInterest-tile-Hub.png "Brands & Interest tiles")</span></span>

## <a name="how-we-determine-affinities"></a><span data-ttu-id="592be-111">Kā tiek noteikta radniecība</span><span class="sxs-lookup"><span data-stu-id="592be-111">How we determine affinities</span></span>

<span data-ttu-id="592be-112">Mēs izmantojat Microsoft tiešsaistes meklēšanas datus, lai atrastu radniecību un intereses dažādos demogrāfijas segmentos (kurus nosaka pēc vecuma, dzimuma vai atrašanās vietas).</span><span class="sxs-lookup"><span data-stu-id="592be-112">We use Microsoft’s online search data to find affinities for brands and interests across various demographic segments (defined by age, gender, or location).</span></span> <span data-ttu-id="592be-113">Zīmola vai intereses tiešsaistes meklēšanas apjoms nosaka, cik daudz radniecības demogrāfiskajam segmentam ir ar šo zīmolu vai interesi, salīdzinot ar citiem segmentiem.</span><span class="sxs-lookup"><span data-stu-id="592be-113">The online search volume for a brand or interest determines how much affinity a demographic segment, compared to other segments, has to that brand or interest.</span></span>

## <a name="affinity-level-and-score"></a><span data-ttu-id="592be-114">Saistību līmenis un rezultāts</span><span class="sxs-lookup"><span data-stu-id="592be-114">Affinity level and score</span></span>

<span data-ttu-id="592be-115">Katrā bagātinātā klienta profilā mēs nodrošinām divas saistītās vērtības — saistību līmeni un saistību rezultātu.</span><span class="sxs-lookup"><span data-stu-id="592be-115">On every enriched customer profile, we provide two related values – affinity level and affinity score.</span></span> <span data-ttu-id="592be-116">Šīs vērtības palīdz noteikt, cik spēcīgas ir saistības šī profila demogrāfiskajam segmentam attiecībā uz zīmolu vai interesi salīdzinājumā ar citiem demogrāfiskajiem segmentiem.</span><span class="sxs-lookup"><span data-stu-id="592be-116">These values help you determine how strong the affinity is for that profile’s demographic segment, for a brand or interest, as compared to other demographic segments.</span></span>

<span data-ttu-id="592be-117">*Saistību līmenis* sastāv no četriem līmeņiem, un *saistību rādītājs* tiek aprēķināts pēc 100 punktu skalas, kura tiek kartēta uz saistību līmeņiem.</span><span class="sxs-lookup"><span data-stu-id="592be-117">*Affinity level* consists of four levels and *affinity score* is calculated on a 100-point scale that maps to the affinity levels.</span></span>


|<span data-ttu-id="592be-118">Saistību līmenis</span><span class="sxs-lookup"><span data-stu-id="592be-118">Affinity level</span></span> |<span data-ttu-id="592be-119">Saistības rādītājs</span><span class="sxs-lookup"><span data-stu-id="592be-119">Affinity score</span></span>  |
|---------|---------|
|<span data-ttu-id="592be-120">Ļoti augsts</span><span class="sxs-lookup"><span data-stu-id="592be-120">Very high</span></span>     | <span data-ttu-id="592be-121">85-100</span><span class="sxs-lookup"><span data-stu-id="592be-121">85-100</span></span>       |
|<span data-ttu-id="592be-122">Augsts</span><span class="sxs-lookup"><span data-stu-id="592be-122">High</span></span>     | <span data-ttu-id="592be-123">70-84</span><span class="sxs-lookup"><span data-stu-id="592be-123">70-84</span></span>        |
|<span data-ttu-id="592be-124">Vidēja</span><span class="sxs-lookup"><span data-stu-id="592be-124">Medium</span></span>     | <span data-ttu-id="592be-125">35-69</span><span class="sxs-lookup"><span data-stu-id="592be-125">35-69</span></span>        |
|<span data-ttu-id="592be-126">Zems</span><span class="sxs-lookup"><span data-stu-id="592be-126">Low</span></span>     | <span data-ttu-id="592be-127">1-34</span><span class="sxs-lookup"><span data-stu-id="592be-127">1-34</span></span>        |

<span data-ttu-id="592be-128">Atkarībā no tā, cik detalizēti vēlaties mērīt saistības, varat izmantot vai nu saistību līmeni, vai rezultātu.</span><span class="sxs-lookup"><span data-stu-id="592be-128">Depending on the granularity you would like for measuring the affinity, you can use either affinity level or score.</span></span> <span data-ttu-id="592be-129">Saistību rādītājs sniedz precīzāku vadīklu.</span><span class="sxs-lookup"><span data-stu-id="592be-129">Affinity score gives you more precise control.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="592be-130">Atbalstītās valstis/reģioni</span><span class="sxs-lookup"><span data-stu-id="592be-130">Supported countries/regions</span></span>

<span data-ttu-id="592be-131">Pašlaik tiek atbalstītas šādas valsts/reģiona opcijas: Austrālija, Kanāda (angļu valoda), Francija, Vācija, Apvienotā Karaliste vai Amerikas Savienotās Valstis (angļu valoda).</span><span class="sxs-lookup"><span data-stu-id="592be-131">We currently support the following country/region options: Australia, Canada (English), France, Germany, United Kingdom, or United States (English).</span></span>

<span data-ttu-id="592be-132">Lai atlasītu valsti, atveriet **Zīmolu papildināšanu** vai **Intereses papildināšanu** un atlasiet opciju **Mainīt** blakus **Valsts/Reģions**.</span><span class="sxs-lookup"><span data-stu-id="592be-132">To select a country, open the **Brands enrichment** or **Interest enrichment** and select **Change** next to **Country/Region**.</span></span> <span data-ttu-id="592be-133">Rūtī **Valsts/Reģiona iestatījumi** izvēlieties opciju un atlasiet **Piemērot**.</span><span class="sxs-lookup"><span data-stu-id="592be-133">In the **Country/Region settings** pane, choose an option and select **Apply**.</span></span>

### <a name="implications-related-to-country-selection"></a><span data-ttu-id="592be-134">Ar valsts atlasi saistītās sekas</span><span class="sxs-lookup"><span data-stu-id="592be-134">Implications related to country selection</span></span>

- <span data-ttu-id="592be-135">[Izvēloties savus zīmolus](#define-your-brands-or-interests), sistēma sniedz ieteikumus, kas balstīti uz atlasīto valsti vai reģionu.</span><span class="sxs-lookup"><span data-stu-id="592be-135">When [choosing your own brands](#define-your-brands-or-interests), the system provides suggestions based on the selected country or region.</span></span>

- <span data-ttu-id="592be-136">[Izvēloties nozari](#define-your-brands-or-interests), jūs iegūsiet svarīgākos zīmolus vai intereses, pamatojoties uz atlasīto valsti vai reģionu.</span><span class="sxs-lookup"><span data-stu-id="592be-136">When [choosing an industry](#define-your-brands-or-interests), you'll get the most relevant brands or interests based on the selected country or region.</span></span>

- <span data-ttu-id="592be-137">[Bagātinot profilus](#refresh-enrichment), mēs bagātināsim visus klientu profilus, attiecībā uz kuriem mēs iegūstam datus par atlasītajiem zīmoliem un interesēm.</span><span class="sxs-lookup"><span data-stu-id="592be-137">When [enriching profiles](#refresh-enrichment), we'll enrich all customer profiles for which we get data for the selected brands and interests.</span></span> <span data-ttu-id="592be-138">Ieskaitot profilus, kas nav atlasītajā valstī vai reģionā.</span><span class="sxs-lookup"><span data-stu-id="592be-138">Including profiles that are not in the selected country or region.</span></span> <span data-ttu-id="592be-139">Piemēram, ja atlasāt Vāciju, mēs bagātināsim profilus, kuri atrodas ASV, ja mums būs pieejami dati par atlasītajiem zīmoliem un interesēm ASV.</span><span class="sxs-lookup"><span data-stu-id="592be-139">For example, if you selected Germany, we'll enrich profiles located in the United States if we have data available for the selected brands and interests in the US.</span></span>

## <a name="configure-enrichment"></a><span data-ttu-id="592be-140">Konfigurēt bagātināšanu</span><span class="sxs-lookup"><span data-stu-id="592be-140">Configure Enrichment</span></span>

<span data-ttu-id="592be-141">Vadītā pieredze palīdz bagātinājumu konfigurēšanas laikā.</span><span class="sxs-lookup"><span data-stu-id="592be-141">A guided experience helps you through the configuration of the enrichments.</span></span> 

### <a name="define-your-brands-or-interests"></a><span data-ttu-id="592be-142">Definēt zīmolus vai intereses</span><span class="sxs-lookup"><span data-stu-id="592be-142">Define your brands or interests</span></span>

<span data-ttu-id="592be-143">Izmantojot vienu vai abas iespējas, izvēlieties līdz pieciem zīmoliem vai interesēm:</span><span class="sxs-lookup"><span data-stu-id="592be-143">Choose up to five brands or interests using one or both of these options:</span></span>

- <span data-ttu-id="592be-144">**Nozare**: nolaižamajā sarakstā atlasiet savu nozari un pēc tam izvēlieties kādu no šīs nozares populārākajām markām vai interesēm.</span><span class="sxs-lookup"><span data-stu-id="592be-144">**Industry**: Select your industry from the drop-down list and then choose from the top brands or interests for that industry.</span></span>
- <span data-ttu-id="592be-145">**Izvēlieties savu**: ievadiet ar organizāciju atbilstošu zīmolu vai ieinteresētību un pēc tam izvēlieties kādu no atbilstības noteikšanas ieteikumiem.</span><span class="sxs-lookup"><span data-stu-id="592be-145">**Choose your own**: Enter a brand or interest that is relevant to your organization and then choose from the matching suggestions.</span></span> <span data-ttu-id="592be-146">Ja mēs neuzskaitām zīmolu vai interesi, kuru meklējat, nosūtiet mums atsauksmi, izmantojot saiti **Ieteikt**.</span><span class="sxs-lookup"><span data-stu-id="592be-146">If we don't list a brand or interest you're looking for, send us feedback using the **Suggest** link.</span></span>

### <a name="review-enrichment-preferences"></a><span data-ttu-id="592be-147">Bagātināšanas preferenču pārskatīšana</span><span class="sxs-lookup"><span data-stu-id="592be-147">Review enrichment preferences</span></span>

<span data-ttu-id="592be-148">Pārskatiet noklusējuma bagātināšanas preferences un atjauniniet tās, kad tas ir nepieciešams.</span><span class="sxs-lookup"><span data-stu-id="592be-148">Review your default enrichment preferences and update them as needed.</span></span>

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Bagātinātā preferenču loga ekrānuzņēmums.":::

### <a name="select-entity-to-enrich"></a><span data-ttu-id="592be-150">Atlasiet bagātināmo entītiju</span><span class="sxs-lookup"><span data-stu-id="592be-150">Select entity to enrich</span></span>

<span data-ttu-id="592be-151">Atlasiet **Bagātinātā entitīja** un atlasiet datu kopu, kuru vēlaties bagātināt ar uzņēmuma datiem no Microsoft.</span><span class="sxs-lookup"><span data-stu-id="592be-151">Select **Enriched entity** and choose the data set you want to enrich with company data from the Microsoft.</span></span> <span data-ttu-id="592be-152">Varat atlasīt entītiju Klients, lai bagātinātu visus klientu profilus, vai atlasīt segmenta entītiju, lai bagātinātu tikai šajā segmentā iekļautos klientu profilus.</span><span class="sxs-lookup"><span data-stu-id="592be-152">You can select the Customer entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

### <a name="map-your-fields"></a><span data-ttu-id="592be-153">Lauku kartēšana</span><span class="sxs-lookup"><span data-stu-id="592be-153">Map your fields</span></span>

<span data-ttu-id="592be-154">Kartējiet laukus no savas vienotās klienta entītijas, lai definētu demogrāfisko segmentu, kuru sistēma vēlas, lai izmantojat jūsu klientu datu bagātināšanai.</span><span class="sxs-lookup"><span data-stu-id="592be-154">Map fields from your unified customer entity to define the demographic segment you want the system to use for enriching your customer data.</span></span> <span data-ttu-id="592be-155">Kartējiet valsti/reģionu un vismaz Dzimšanas datu vai Dzimuma atribūtus.</span><span class="sxs-lookup"><span data-stu-id="592be-155">Map Country/Region and at least Date of Birth or Gender attributes.</span></span> <span data-ttu-id="592be-156">Turklāt ir jākartē vismaz viens no atribūtiem — Pilsēta (un novads/rajons) vai pasta indekss.</span><span class="sxs-lookup"><span data-stu-id="592be-156">Additionally, you must map at least one of City (and State/Province) or Postal code.</span></span> <span data-ttu-id="592be-157">Atlasiet **Rediģēt**, lai definētu lauku kartēšanu, un atlasiet **Piemērot**, kad esat to izdarījis.</span><span class="sxs-lookup"><span data-stu-id="592be-157">Select **Edit** to define the mapping of the fields and select **Apply** when you're done.</span></span> <span data-ttu-id="592be-158">Atlasiet **Saglabāt**, lai pabeigtu lauka kartēšanu.</span><span class="sxs-lookup"><span data-stu-id="592be-158">Select **Save** to complete the field mapping.</span></span>

<span data-ttu-id="592be-159">Tiek atbalstīti šādi(-as) formāti un vērtības; vērtības nav reģistrjutīgas:</span><span class="sxs-lookup"><span data-stu-id="592be-159">The following formats and values are supported, values are not case-sensitive:</span></span>

- <span data-ttu-id="592be-160">**Dzimšanas datums** : Iesakām, lai datu uzņemšanas laikā dzimšanas datums tiek pārvērsts par DateTime tipu.</span><span class="sxs-lookup"><span data-stu-id="592be-160">**Date of Birth**: We recommend that date of birth is converted to DateTime type during data ingestion.</span></span> <span data-ttu-id="592be-161">Vai arī tā var būt virkne [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) “gggg-MM-dd” vai “gggg-MM-ddTHH:mm:ssZ” formātā.</span><span class="sxs-lookup"><span data-stu-id="592be-161">Alternatively, it can be a string in [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) format "yyyy-MM-dd" or "yyyy-MM-ddTHH:mm:ssZ".</span></span>
- <span data-ttu-id="592be-162">**Dzimums**: Vīrietis, sieviete, nezināms</span><span class="sxs-lookup"><span data-stu-id="592be-162">**Gender**: Male, Female, Unknown</span></span>
- <span data-ttu-id="592be-163">**Pasta indekss**: Piecciparu pasta indeksi ASV, standarta pasta indekss citur</span><span class="sxs-lookup"><span data-stu-id="592be-163">**Postal code**: Five-digit ZIP Codes for US, standard postal code everywhere else</span></span>
- <span data-ttu-id="592be-164">**Pilsēta** : Pilsētas nosaukums angļu valodā</span><span class="sxs-lookup"><span data-stu-id="592be-164">**City**: City name in English</span></span>
- <span data-ttu-id="592be-165">**Štats/Province**: Divu burtu saīsinājums Amerikas Savienotajās Valstīs (ASV) un Kanādā.</span><span class="sxs-lookup"><span data-stu-id="592be-165">**State/Province**: Two-letter abbreviation for the US and Canada.</span></span> <span data-ttu-id="592be-166">Divu vai trīs burtu saīsinājums Austrālijā.</span><span class="sxs-lookup"><span data-stu-id="592be-166">Two or three letter abbreviation for Australia.</span></span> <span data-ttu-id="592be-167">Nav piemērojams Francijai, Vācijai vai Apvienotajai Karalistei.</span><span class="sxs-lookup"><span data-stu-id="592be-167">Not applicable for France, Germany, or the UK.</span></span>
- <span data-ttu-id="592be-168">**Valsts/Reģions**:</span><span class="sxs-lookup"><span data-stu-id="592be-168">**Country/Region**:</span></span>

  - <span data-ttu-id="592be-169">US: Amerikas Savienotās Valstis, ASV, US, Amerika</span><span class="sxs-lookup"><span data-stu-id="592be-169">US: United States of America, United States, USA, US, America</span></span>
  - <span data-ttu-id="592be-170">CA: Kanāda, CA</span><span class="sxs-lookup"><span data-stu-id="592be-170">CA: Canada, CA</span></span>
  - <span data-ttu-id="592be-171">GB: Apvienotā Karaliste, AK, Lielbritānija, GB, Lielbritānijas un Ziemeļīrijas Apvienotā Karaliste, Lielbritānijas Apvienotā Karaliste</span><span class="sxs-lookup"><span data-stu-id="592be-171">GB: United Kingdom, UK, Great Britain, GB, United Kingdom of Great Britain and Northern Ireland, United Kingdom of Great Britain</span></span>
  - <span data-ttu-id="592be-172">AU: Austrālija, AU, Austrālijas Savienība</span><span class="sxs-lookup"><span data-stu-id="592be-172">AU: Australia, AU, Common Wealth of Australia</span></span>
  - <span data-ttu-id="592be-173">FR: Francija, FR, Francijas Republika</span><span class="sxs-lookup"><span data-stu-id="592be-173">FR: France, FR, French Republic</span></span>
  - <span data-ttu-id="592be-174">DE: Vācija, vācu valoda, Deutschland, Allemagne, DE, Vācijas Federatīvā Republika, Vācijas Republika</span><span class="sxs-lookup"><span data-stu-id="592be-174">DE: Germany, German, Deutschland, Allemagne, DE, Federal Republic of Germany, Republic of Germany</span></span>

## <a name="review-and-name-the-enrichment"></a><span data-ttu-id="592be-175">Bagātinājuma pārskatīšana un dēvēšana</span><span class="sxs-lookup"><span data-stu-id="592be-175">Review and name the enrichment</span></span>

<span data-ttu-id="592be-176">Visbeidzot, varat pārskatīt informāciju un nodrošināt bagātinājuma nosaukumu.</span><span class="sxs-lookup"><span data-stu-id="592be-176">Finally, you get to review the information and provide a name for the enrichment.</span></span>

:::image type="content" source="media/enrichment-interests-summary.png" alt-text="Interešu pārskatīšanas un dēvēšanas lapa.":::

## <a name="refresh-enrichment"></a><span data-ttu-id="592be-178">Atsvaidzināt bagātināšanu</span><span class="sxs-lookup"><span data-stu-id="592be-178">Refresh enrichment</span></span>

<span data-ttu-id="592be-179">Pēc zīmolu, interešu un demogrāfijas lauku kartēšanas palaidiet bagātināšanu.</span><span class="sxs-lookup"><span data-stu-id="592be-179">Run the enrichment after configuring brands, interests, and the field mapping for demographics.</span></span> <span data-ttu-id="592be-180">Lai sāktu procesu, atlasiet **Palaist** zīmola vai interešu konfigurācijas lapā.</span><span class="sxs-lookup"><span data-stu-id="592be-180">To start the process, select **Run** on the brand or interest configuration page.</span></span> <span data-ttu-id="592be-181">Turklāt varat ļaut sistēmai automātiski palaist bagātināšanu kā plānotas atsvaidzināšanas daļu.</span><span class="sxs-lookup"><span data-stu-id="592be-181">Additionally, you can let the system run the enrichment automatically as part of a scheduled refresh.</span></span>
<span data-ttu-id="592be-182">Atkarībā no jūsu klientu datu apjoma bagātināšanas izpilde var aizņemt vairākas minūtes.</span><span class="sxs-lookup"><span data-stu-id="592be-182">Depending on the size of your customer data, it may take several minutes for an enrichment run to complete.</span></span>

> [!TIP]
> <span data-ttu-id="592be-183">Uzdevumiem/procesiem ir [seši statusu tipi](system.md#status-types).</span><span class="sxs-lookup"><span data-stu-id="592be-183">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="592be-184">Turklāt vairums procesu [ir atkarīgi no citiem pakārtotiem procesiem](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="592be-184">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="592be-185">Varat atlasīt procesa statusu, lai skatītu detalizētu informāciju par visa uzdevuma norisi.</span><span class="sxs-lookup"><span data-stu-id="592be-185">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="592be-186">Pēc tam, kad vienam no darba uzdevumiem esat atlasījis **Skatīt detalizētu informāciju**, jūs redzēsit papildinformāciju: apstrādes laiku, pēdējās apstrādes datumu un visas ar uzdevumu saistītas kļūdas un brīdinājumus.</span><span class="sxs-lookup"><span data-stu-id="592be-186">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="592be-187">Bagātināšanas rezultāti</span><span class="sxs-lookup"><span data-stu-id="592be-187">Enrichment results</span></span>

<span data-ttu-id="592be-188">Pēc bagātināšanas procesa palaišanas dodieties uz **Manas bagātināšanas**, lai pārskatītu kopējo bagātināto klientu skaitu un zīmolu vai interešu sadalījumu bagātināto klientu profilos.</span><span class="sxs-lookup"><span data-stu-id="592be-188">After running the enrichment process, go to **My enrichments** to review the total number of enriched customers and a breakdown of brands or interests in the enriched customer profiles.</span></span>

:::image type="content" source="media/my-enrichments.png" alt-text="Rezultātu priekšskatījums pēc bagātināšanas procesa izpildes":::

<span data-ttu-id="592be-190">Pārskatiet bagātinātos datus, diagrammā atlasot **Skatīt bagātinātos datus**.</span><span class="sxs-lookup"><span data-stu-id="592be-190">Review the enriched data by selecting **View enriched data** in the chart.</span></span> <span data-ttu-id="592be-191">Zīmolu bagātinātie dati dodas uz entītiju **BrandAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="592be-191">Enriched data for brands goes to the **BrandAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="592be-192">Interešu dati atrodas entītijā **InterestAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="592be-192">Data for interests is in the **InterestAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="592be-193">Šīs entītijas ir uzskaitītas arī grupā **Bagātināšana** sadaļā **Dati** > **Entītijas**.</span><span class="sxs-lookup"><span data-stu-id="592be-193">You'll also find these entities listed in the **Enrichment** group in **Data** > **Entities**.</span></span>

## <a name="see-enrichment-data-on-the-customer-card"></a><span data-ttu-id="592be-194">Skatiet informāciju par produkta bagātināšanu klienta kartītē</span><span class="sxs-lookup"><span data-stu-id="592be-194">See enrichment data on the customer card</span></span>

<span data-ttu-id="592be-195">Zīmola un intereses radniecību var apskatīt arī atsevišķās klientu kartītēs.</span><span class="sxs-lookup"><span data-stu-id="592be-195">Brand and interest affinities can also be viewed on individual customer cards.</span></span> <span data-ttu-id="592be-196">Atveriet sadaļu **Klienti** un atlasiet klienta profilu.</span><span class="sxs-lookup"><span data-stu-id="592be-196">Go to **Customers** and select a customer profile.</span></span> <span data-ttu-id="592be-197">Klienta kartē ir atrodamas to zīmolu vai interešu diagrammas, kuras ir saistītas ar šī klienta demogrāfiskā profila lietotājiem.</span><span class="sxs-lookup"><span data-stu-id="592be-197">In the customer card, you'll find charts for the brands or interests that people in that customer's demographic profile have affinity for.</span></span>

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Klienta kartīte ar bagātinātiem datiem":::

## <a name="next-steps"></a><span data-ttu-id="592be-199">Nākamās darbības</span><span class="sxs-lookup"><span data-stu-id="592be-199">Next steps</span></span>

<span data-ttu-id="592be-200">Būvējiet virs saviem bagātinātajiem klientu datiem.</span><span class="sxs-lookup"><span data-stu-id="592be-200">Build on top of your enriched customer data.</span></span> <span data-ttu-id="592be-201">Veidojiet [segmentus](segments.md), [mērus](measures.md)un pat [eksportējiet datus](export-destinations.md), lai klientiem sniegtu personalizētas iespējas.</span><span class="sxs-lookup"><span data-stu-id="592be-201">Create [Segments](segments.md), [Measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
