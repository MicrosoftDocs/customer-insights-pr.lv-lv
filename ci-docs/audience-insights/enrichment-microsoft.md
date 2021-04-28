---
title: Klientu profilu bagātināšana ar Microsoft datiem
description: Izmantojiet Microsoft īpašumtiesību datus, lai bagātinātu klientu datus ar zīmola un interešu radniecību.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 6f19033236190547f68d2b91ec6b32074bf7912a
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896611"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a><span data-ttu-id="12220-103">Bagātiniet klientu profilus ar zīmola un interešu radniecību (priekšskatījums)</span><span class="sxs-lookup"><span data-stu-id="12220-103">Enrich customer profiles with brand and interest affinities (preview)</span></span>

<span data-ttu-id="12220-104">Izmantojiet Microsoft īpašumtiesību datus, lai bagātinātu klientu datus ar zīmola un interešu radniecību.</span><span class="sxs-lookup"><span data-stu-id="12220-104">Use Microsoft's proprietary data to enrich your customer data with brand and interest affinities.</span></span> <span data-ttu-id="12220-105">Šie apstākļi tiek noteikti, vadoties pēc datiem, kas iegūti no cilvēkiem ar līdzīgiem demogrāfiskajiem datiem līdz jūsu klientiem.</span><span class="sxs-lookup"><span data-stu-id="12220-105">These affinities are determined based on data from people with similar demographics to your customers.</span></span> <span data-ttu-id="12220-106">Šī informācija palīdz labāk izprast un segmentēt jūsu klientus, ņemot vērā viņu saistību ar noteiktiem zīmoliem un interesēm.</span><span class="sxs-lookup"><span data-stu-id="12220-106">This information helps you to better understand and segment your customers based on their affinities to specific brands and interests.</span></span>

<span data-ttu-id="12220-107">Rīkā Auditorijas ieskati ejiet uz **Dati** > **Bagātināšana**, lai [konfigurētu un skatītu bagātināšanu](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="12220-107">In audience insights, go to **Data** > **Enrichment** to [configure and view enrichments](enrichment-hub.md).</span></span>

<span data-ttu-id="12220-108">Lai konfigurētu zīmola saistību bagātināšanu, dodieties uz cilni **Atklāt** un atlasiet **Bagātināt manus datus** elementā **Zīmoli**.</span><span class="sxs-lookup"><span data-stu-id="12220-108">To configure brand affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Brands** tile.</span></span>

<span data-ttu-id="12220-109">Lai konfigurētu interešu saistību bagātināšanu, dodieties uz cilni **Atklāt** un atlasiet **Bagātināt manus datus** elementā **Intereses**.</span><span class="sxs-lookup"><span data-stu-id="12220-109">To configure interest affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Interests** tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="12220-110">![Zīmolu un interešu rūtis](media/BrandsInterest-tile-Hub.png "Zīmolu un interešu rūtis")</span><span class="sxs-lookup"><span data-stu-id="12220-110">![Brands & Interests tiles](media/BrandsInterest-tile-Hub.png "Brands & Interest tiles")</span></span>

## <a name="how-we-determine-affinities"></a><span data-ttu-id="12220-111">Kā tiek noteikta radniecība</span><span class="sxs-lookup"><span data-stu-id="12220-111">How we determine affinities</span></span>

<span data-ttu-id="12220-112">Mēs izmantojat Microsoft tiešsaistes meklēšanas datus, lai atrastu radniecību un intereses dažādos demogrāfijas segmentos (kurus nosaka pēc vecuma, dzimuma vai atrašanās vietas).</span><span class="sxs-lookup"><span data-stu-id="12220-112">We use Microsoft’s online search data to find affinities for brands and interests across various demographic segments (defined by age, gender, or location).</span></span> <span data-ttu-id="12220-113">Zīmola vai intereses tiešsaistes meklēšanas apjoms nosaka, cik daudz radniecības demogrāfiskajam segmentam ir ar šo zīmolu vai interesi, salīdzinot ar citiem segmentiem.</span><span class="sxs-lookup"><span data-stu-id="12220-113">The online search volume for a brand or interest determines how much affinity a demographic segment, compared to other segments, has to that brand or interest.</span></span> <span data-ttu-id="12220-114">zīmols vai interese.</span><span class="sxs-lookup"><span data-stu-id="12220-114">brand or interest.</span></span>

## <a name="affinity-level-and-score"></a><span data-ttu-id="12220-115">Saistību līmenis un rezultāts</span><span class="sxs-lookup"><span data-stu-id="12220-115">Affinity level and score</span></span>

<span data-ttu-id="12220-116">Katrā bagātinātā klienta profilā mēs nodrošinām divas saistītās vērtības — saistību līmeni un saistību rezultātu.</span><span class="sxs-lookup"><span data-stu-id="12220-116">On every enriched customer profile, we provide two related values – affinity level and affinity score.</span></span> <span data-ttu-id="12220-117">Šīs vērtības palīdz noteikt, cik spēcīgas ir saistības šī profila demogrāfiskajam segmentam attiecībā uz zīmolu vai interesi salīdzinājumā ar citiem demogrāfiskajiem segmentiem.</span><span class="sxs-lookup"><span data-stu-id="12220-117">These values help you determine how strong the affinity is for that profile’s demographic segment, for a brand or interest, as compared to other demographic segments.</span></span>

<span data-ttu-id="12220-118">*Saistību līmenis* sastāv no četriem līmeņiem, un *saistību rādītājs* tiek aprēķināts pēc 100 punktu skalas, kura tiek kartēta uz saistību līmeņiem.</span><span class="sxs-lookup"><span data-stu-id="12220-118">*Affinity level* consists of four levels and *affinity score* is calculated on a 100-point scale that maps to the affinity levels.</span></span>


|<span data-ttu-id="12220-119">Saistību līmenis</span><span class="sxs-lookup"><span data-stu-id="12220-119">Affinity level</span></span> |<span data-ttu-id="12220-120">Saistības rādītājs</span><span class="sxs-lookup"><span data-stu-id="12220-120">Affinity score</span></span>  |
|---------|---------|
|<span data-ttu-id="12220-121">Ļoti augsts</span><span class="sxs-lookup"><span data-stu-id="12220-121">Very high</span></span>     | <span data-ttu-id="12220-122">85-100</span><span class="sxs-lookup"><span data-stu-id="12220-122">85-100</span></span>       |
|<span data-ttu-id="12220-123">Augsts</span><span class="sxs-lookup"><span data-stu-id="12220-123">High</span></span>     | <span data-ttu-id="12220-124">70-84</span><span class="sxs-lookup"><span data-stu-id="12220-124">70-84</span></span>        |
|<span data-ttu-id="12220-125">Vidēja</span><span class="sxs-lookup"><span data-stu-id="12220-125">Medium</span></span>     | <span data-ttu-id="12220-126">35-69</span><span class="sxs-lookup"><span data-stu-id="12220-126">35-69</span></span>        |
|<span data-ttu-id="12220-127">Zems</span><span class="sxs-lookup"><span data-stu-id="12220-127">Low</span></span>     | <span data-ttu-id="12220-128">1-34</span><span class="sxs-lookup"><span data-stu-id="12220-128">1-34</span></span>        |

<span data-ttu-id="12220-129">Atkarībā no tā, cik detalizēti vēlaties mērīt saistības, varat izmantot vai nu saistību līmeni, vai rezultātu.</span><span class="sxs-lookup"><span data-stu-id="12220-129">Depending on the granularity you would like for measuring the affinity, you can use either affinity level or score.</span></span> <span data-ttu-id="12220-130">Saistību rādītājs sniedz precīzāku vadīklu.</span><span class="sxs-lookup"><span data-stu-id="12220-130">Affinity score gives you more precise control.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="12220-131">Atbalstītās valstis/reģioni</span><span class="sxs-lookup"><span data-stu-id="12220-131">Supported countries/regions</span></span>

<span data-ttu-id="12220-132">Pašlaik tiek atbalstītas šādas valsts/reģiona opcijas: Austrālija, Kanāda (angļu valoda), Francija, Vācija, Apvienotā Karaliste vai Amerikas Savienotās Valstis (angļu valoda).</span><span class="sxs-lookup"><span data-stu-id="12220-132">We currently support the following country/region options: Australia, Canada (English), France, Germany, United Kingdom, or United States (English).</span></span>

<span data-ttu-id="12220-133">Lai atlasītu valsti, atveriet **Zīmolu papildināšanu** vai **Intereses papildināšanu** un atlasiet opciju **Mainīt** blakus **Valsts/Reģions**.</span><span class="sxs-lookup"><span data-stu-id="12220-133">To select a country, open the **Brands enrichment** or **Interest enrichment** and select **Change** next to **Country/Region**.</span></span> <span data-ttu-id="12220-134">Rūtī **Valsts/Reģiona iestatījumi** izvēlieties opciju un atlasiet **Piemērot**.</span><span class="sxs-lookup"><span data-stu-id="12220-134">In the **Country/Region settings** pane, choose an option and select **Apply**.</span></span>

### <a name="implications-related-to-country-selection"></a><span data-ttu-id="12220-135">Ar valsts atlasi saistītās sekas</span><span class="sxs-lookup"><span data-stu-id="12220-135">Implications related to country selection</span></span>

- <span data-ttu-id="12220-136">[Izvēloties savus zīmolus](#define-your-brands-or-interests), sistēma sniedz ieteikumus, kas balstīti uz atlasīto valsti vai reģionu.</span><span class="sxs-lookup"><span data-stu-id="12220-136">When [choosing your own brands](#define-your-brands-or-interests), the system provides suggestions based on the selected country or region.</span></span>

- <span data-ttu-id="12220-137">[Izvēloties nozari](#define-your-brands-or-interests), jūs iegūsiet svarīgākos zīmolus vai intereses, pamatojoties uz atlasīto valsti vai reģionu.</span><span class="sxs-lookup"><span data-stu-id="12220-137">When [choosing an industry](#define-your-brands-or-interests), you'll get the most relevant brands or interests based on the selected country or region.</span></span>

- <span data-ttu-id="12220-138">[Bagātinot profilus](#refresh-enrichment), mēs bagātināsim visus klientu profilus, attiecībā uz kuriem mēs iegūstam datus par atlasītajiem zīmoliem un interesēm.</span><span class="sxs-lookup"><span data-stu-id="12220-138">When [enriching profiles](#refresh-enrichment), we'll enrich all customer profiles for which we get data for the selected brands and interests.</span></span> <span data-ttu-id="12220-139">Ieskaitot profilus, kas nav atlasītajā valstī vai reģionā.</span><span class="sxs-lookup"><span data-stu-id="12220-139">Including profiles that are not in the selected country or region.</span></span> <span data-ttu-id="12220-140">Piemēram, ja atlasāt Vāciju, mēs bagātināsim profilus, kuri atrodas ASV, ja mums būs pieejami dati par atlasītajiem zīmoliem un interesēm ASV.</span><span class="sxs-lookup"><span data-stu-id="12220-140">For example, if you selected Germany, we'll enrich profiles located in the United States if we have data available for the selected brands and interests in the US.</span></span>

## <a name="configure-enrichment"></a><span data-ttu-id="12220-141">Konfigurēt bagātināšanu</span><span class="sxs-lookup"><span data-stu-id="12220-141">Configure Enrichment</span></span>

<span data-ttu-id="12220-142">Vadītā pieredze palīdz bagātinājumu konfigurēšanas laikā.</span><span class="sxs-lookup"><span data-stu-id="12220-142">A guided experience helps you through the configuration of the enrichments.</span></span> 

### <a name="define-your-brands-or-interests"></a><span data-ttu-id="12220-143">Definēt zīmolus vai intereses</span><span class="sxs-lookup"><span data-stu-id="12220-143">Define your brands or interests</span></span>

<span data-ttu-id="12220-144">Atlasiet kādu no šīm opcijām:</span><span class="sxs-lookup"><span data-stu-id="12220-144">Select one of the following options:</span></span>

- <span data-ttu-id="12220-145">**Nozare**: Sistēma identificē galvenos zīmolus vai intereses, kas attiecas uz jūsu nozari, un bagātina jūsu klientu datus ar tiem.</span><span class="sxs-lookup"><span data-stu-id="12220-145">**Industry**: The system identifies the top brands or interests relevant to your industry and enriches your customer data with them.</span></span>
- <span data-ttu-id="12220-146">**Izvēlieties paši**: Atlasiet līdz pieciem vienumiem no zīmolu vai interešu saraksta, kuri jūsu organizācijai ir vissaistošākie.</span><span class="sxs-lookup"><span data-stu-id="12220-146">**Choose your own**: Select up to five items from the list of brands or interests that are most relevant to your organization.</span></span>

<span data-ttu-id="12220-147">Lai pievienotu zīmolu vai interesi, ievadiet to ievades apgabalā, lai saņemtu ieteikumus, pamatojoties uz atbilstības nosacījumiem.</span><span class="sxs-lookup"><span data-stu-id="12220-147">To add a brand or interest, enter it in the input area to get suggestions based on matching terms.</span></span> <span data-ttu-id="12220-148">Ja mēs neuzskaitām zīmolu vai interesi, kuru meklējat, nosūtiet mums atsauksmi, izmantojot saiti **Ieteikt**.</span><span class="sxs-lookup"><span data-stu-id="12220-148">If we don't list a brand or interest you're looking for, send us feedback using the **Suggest** link.</span></span>

### <a name="review-enrichment-preferences"></a><span data-ttu-id="12220-149">Bagātināšanas preferenču pārskatīšana</span><span class="sxs-lookup"><span data-stu-id="12220-149">Review enrichment preferences</span></span>

<span data-ttu-id="12220-150">Pārskatiet noklusējuma bagātināšanas preferences un atjauniniet tās, kad tas ir nepieciešams.</span><span class="sxs-lookup"><span data-stu-id="12220-150">Review your default enrichment preferences and update them as needed.</span></span>

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Bagātinātā preferenču loga ekrānuzņēmums.":::

### <a name="select-entity-to-enrich"></a><span data-ttu-id="12220-152">Atlasiet bagātināmo entītiju</span><span class="sxs-lookup"><span data-stu-id="12220-152">Select entity to enrich</span></span>

<span data-ttu-id="12220-153">Atlasiet **Bagātinātā entitīja** un atlasiet datu kopu, kuru vēlaties bagātināt ar uzņēmuma datiem no Microsoft.</span><span class="sxs-lookup"><span data-stu-id="12220-153">Select **Enriched entity** and choose the data set you want to enrich with company data from the Microsoft.</span></span> <span data-ttu-id="12220-154">Varat atlasīt entītiju Klients, lai bagātinātu visus klientu profilus, vai atlasīt segmenta entītiju, lai bagātinātu tikai šajā segmentā iekļautos klientu profilus.</span><span class="sxs-lookup"><span data-stu-id="12220-154">You can select the Customer entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

### <a name="map-your-fields"></a><span data-ttu-id="12220-155">Lauku kartēšana</span><span class="sxs-lookup"><span data-stu-id="12220-155">Map your fields</span></span>

<span data-ttu-id="12220-156">Kartējiet laukus no savas vienotās klienta entītijas, lai definētu demogrāfisko segmentu, kuru sistēma vēlas, lai izmantojat jūsu klientu datu bagātināšanai.</span><span class="sxs-lookup"><span data-stu-id="12220-156">Map fields from your unified customer entity to define the demographic segment you want the system to use for enriching your customer data.</span></span> <span data-ttu-id="12220-157">Kartējiet valsti/reģionu un vismaz Dzimšanas datu vai Dzimuma atribūtus.</span><span class="sxs-lookup"><span data-stu-id="12220-157">Map Country/Region and at least Date of Birth or Gender attributes.</span></span> <span data-ttu-id="12220-158">Turklāt ir jākartē vismaz viens no atribūtiem — Pilsēta (un novads/rajons) vai pasta indekss.</span><span class="sxs-lookup"><span data-stu-id="12220-158">Additionally, you must map at least one of City (and State/Province) or Postal code.</span></span> <span data-ttu-id="12220-159">Atlasiet **Rediģēt**, lai definētu lauku kartēšanu, un atlasiet **Piemērot**, kad esat to izdarījis.</span><span class="sxs-lookup"><span data-stu-id="12220-159">Select **Edit** to define the mapping of the fields and select **Apply** when you're done.</span></span> <span data-ttu-id="12220-160">Atlasiet **Saglabāt**, lai pabeigtu lauka kartēšanu.</span><span class="sxs-lookup"><span data-stu-id="12220-160">Select **Save** to complete the field mapping.</span></span>

<span data-ttu-id="12220-161">Tiek atbalstīti šādi(-as) formāti un vērtības; vērtības nav reģistrjutīgas:</span><span class="sxs-lookup"><span data-stu-id="12220-161">The following formats and values are supported, values are not case-sensitive:</span></span>

- <span data-ttu-id="12220-162">**Dzimšanas datums** : Iesakām, lai datu uzņemšanas laikā dzimšanas datums tiek pārvērsts par DateTime tipu.</span><span class="sxs-lookup"><span data-stu-id="12220-162">**Date of Birth**: We recommend that date of birth is converted to DateTime type during data ingestion.</span></span> <span data-ttu-id="12220-163">Vai arī tā var būt virkne [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) “gggg-MM-dd” vai “gggg-MM-ddTHH:mm:ssZ” formātā.</span><span class="sxs-lookup"><span data-stu-id="12220-163">Alternatively, it can be a string in [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) format "yyyy-MM-dd" or "yyyy-MM-ddTHH:mm:ssZ".</span></span>
- <span data-ttu-id="12220-164">**Dzimums**: Vīrietis, sieviete, nezināms</span><span class="sxs-lookup"><span data-stu-id="12220-164">**Gender**: Male, Female, Unknown</span></span>
- <span data-ttu-id="12220-165">**Pasta indekss**: Piecciparu pasta indeksi ASV, standarta pasta indekss citur</span><span class="sxs-lookup"><span data-stu-id="12220-165">**Postal code**: Five-digit ZIP Codes for US, standard postal code everywhere else</span></span>
- <span data-ttu-id="12220-166">**Pilsēta** : Pilsētas nosaukums angļu valodā</span><span class="sxs-lookup"><span data-stu-id="12220-166">**City**: City name in English</span></span>
- <span data-ttu-id="12220-167">**Štats/Province**: Divu burtu saīsinājums Amerikas Savienotajās Valstīs (ASV) un Kanādā.</span><span class="sxs-lookup"><span data-stu-id="12220-167">**State/Province**: Two-letter abbreviation for the US and Canada.</span></span> <span data-ttu-id="12220-168">Divu vai trīs burtu saīsinājums Austrālijā.</span><span class="sxs-lookup"><span data-stu-id="12220-168">Two or three letter abbreviation for Australia.</span></span> <span data-ttu-id="12220-169">Nav piemērojams Francijai, Vācijai vai Apvienotajai Karalistei.</span><span class="sxs-lookup"><span data-stu-id="12220-169">Not applicable for France, Germany, or the UK.</span></span>
- <span data-ttu-id="12220-170">**Valsts/Reģions**:</span><span class="sxs-lookup"><span data-stu-id="12220-170">**Country/Region**:</span></span>

  - <span data-ttu-id="12220-171">US: Amerikas Savienotās Valstis, ASV, US, Amerika</span><span class="sxs-lookup"><span data-stu-id="12220-171">US: United States of America, United States, USA, US, America</span></span>
  - <span data-ttu-id="12220-172">CA: Kanāda, CA</span><span class="sxs-lookup"><span data-stu-id="12220-172">CA: Canada, CA</span></span>
  - <span data-ttu-id="12220-173">GB: Apvienotā Karaliste, AK, Lielbritānija, GB, Lielbritānijas un Ziemeļīrijas Apvienotā Karaliste, Lielbritānijas Apvienotā Karaliste</span><span class="sxs-lookup"><span data-stu-id="12220-173">GB: United Kingdom, UK, Great Britain, GB, United Kingdom of Great Britain and Northern Ireland, United Kingdom of Great Britain</span></span>
  - <span data-ttu-id="12220-174">AU: Austrālija, AU, Austrālijas Savienība</span><span class="sxs-lookup"><span data-stu-id="12220-174">AU: Australia, AU, Common Wealth of Australia</span></span>
  - <span data-ttu-id="12220-175">FR: Francija, FR, Francijas Republika</span><span class="sxs-lookup"><span data-stu-id="12220-175">FR: France, FR, French Republic</span></span>
  - <span data-ttu-id="12220-176">DE: Vācija, vācu valoda, Deutschland, Allemagne, DE, Vācijas Federatīvā Republika, Vācijas Republika</span><span class="sxs-lookup"><span data-stu-id="12220-176">DE: Germany, German, Deutschland, Allemagne, DE, Federal Republic of Germany, Republic of Germany</span></span>

## <a name="review-and-name-the-enrichment"></a><span data-ttu-id="12220-177">Bagātinājuma pārskatīšana un dēvēšana</span><span class="sxs-lookup"><span data-stu-id="12220-177">Review and name the enrichment</span></span>

<span data-ttu-id="12220-178">Visbeidzot, varat pārskatīt informāciju un nodrošināt bagātinājuma nosaukumu.</span><span class="sxs-lookup"><span data-stu-id="12220-178">Finally, you get to review the information and provide a name for the enrichment.</span></span>

:::image type="content" source="media/enrichment-interests-summary.png" alt-text="Interešu pārskatīšanas un dēvēšanas lapa.":::

## <a name="refresh-enrichment"></a><span data-ttu-id="12220-180">Atsvaidzināt bagātināšanu</span><span class="sxs-lookup"><span data-stu-id="12220-180">Refresh enrichment</span></span>

<span data-ttu-id="12220-181">Pēc zīmolu, interešu un demogrāfijas lauku kartēšanas palaidiet bagātināšanu.</span><span class="sxs-lookup"><span data-stu-id="12220-181">Run the enrichment after configuring brands, interests, and the field mapping for demographics.</span></span> <span data-ttu-id="12220-182">Lai sāktu procesu, atlasiet **Palaist** zīmola vai interešu konfigurācijas lapā.</span><span class="sxs-lookup"><span data-stu-id="12220-182">To start the process, select **Run** on the brand or interest configuration page.</span></span> <span data-ttu-id="12220-183">Turklāt varat ļaut sistēmai automātiski palaist bagātināšanu kā plānotas atsvaidzināšanas daļu.</span><span class="sxs-lookup"><span data-stu-id="12220-183">Additionally, you can let the system run the enrichment automatically as part of a scheduled refresh.</span></span>
<span data-ttu-id="12220-184">Atkarībā no jūsu klientu datu apjoma bagātināšanas izpilde var aizņemt vairākas minūtes.</span><span class="sxs-lookup"><span data-stu-id="12220-184">Depending on the size of your customer data, it may take several minutes for an enrichment run to complete.</span></span>

> [!TIP]
> <span data-ttu-id="12220-185">Uzdevumiem/procesiem ir [seši statusu tipi](system.md#status-types).</span><span class="sxs-lookup"><span data-stu-id="12220-185">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="12220-186">Turklāt vairums procesu [ir atkarīgi no citiem pakārtotiem procesiem](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="12220-186">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="12220-187">Varat atlasīt procesa statusu, lai skatītu detalizētu informāciju par visa uzdevuma norisi.</span><span class="sxs-lookup"><span data-stu-id="12220-187">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="12220-188">Pēc tam, kad vienam no darba uzdevumiem esat atlasījis **Skatīt detalizētu informāciju**, jūs redzēsit papildinformāciju: apstrādes laiku, pēdējās apstrādes datumu un visas ar uzdevumu saistītas kļūdas un brīdinājumus.</span><span class="sxs-lookup"><span data-stu-id="12220-188">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="12220-189">Bagātināšanas rezultāti</span><span class="sxs-lookup"><span data-stu-id="12220-189">Enrichment results</span></span>

<span data-ttu-id="12220-190">Pēc bagātināšanas procesa palaišanas dodieties uz **Manas bagātināšanas**, lai pārskatītu kopējo bagātināto klientu skaitu un zīmolu vai interešu sadalījumu bagātināto klientu profilos.</span><span class="sxs-lookup"><span data-stu-id="12220-190">After running the enrichment process, go to **My enrichments** to review the total number of enriched customers and a breakdown of brands or interests in the enriched customer profiles.</span></span>

:::image type="content" source="media/my-enrichments.png" alt-text="Rezultātu priekšskatījums pēc bagātināšanas procesa izpildes":::

<span data-ttu-id="12220-192">Pārskatiet bagātinātos datus, diagrammā atlasot **Skatīt bagātinātos datus**.</span><span class="sxs-lookup"><span data-stu-id="12220-192">Review the enriched data by selecting **View enriched data** in the chart.</span></span> <span data-ttu-id="12220-193">Zīmolu bagātinātie dati dodas uz entītiju **BrandAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="12220-193">Enriched data for brands goes to the **BrandAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="12220-194">Interešu dati atrodas entītijā **InterestAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="12220-194">Data for interests is in the **InterestAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="12220-195">Šīs entītijas ir uzskaitītas arī grupā **Bagātināšana** sadaļā **Dati** > **Entītijas**.</span><span class="sxs-lookup"><span data-stu-id="12220-195">You'll also find these entities listed in the **Enrichment** group in **Data** > **Entities**.</span></span>

## <a name="see-enrichment-data-on-the-customer-card"></a><span data-ttu-id="12220-196">Skatiet informāciju par produkta bagātināšanu klienta kartītē</span><span class="sxs-lookup"><span data-stu-id="12220-196">See enrichment data on the customer card</span></span>

<span data-ttu-id="12220-197">Zīmola un intereses radniecību var apskatīt arī atsevišķās klientu kartītēs.</span><span class="sxs-lookup"><span data-stu-id="12220-197">Brand and interest affinities can also be viewed on individual customer cards.</span></span> <span data-ttu-id="12220-198">Atveriet sadaļu **Klienti** un atlasiet klienta profilu.</span><span class="sxs-lookup"><span data-stu-id="12220-198">Go to **Customers** and select a customer profile.</span></span> <span data-ttu-id="12220-199">Klienta kartē ir atrodamas to zīmolu vai interešu diagrammas, kuras ir saistītas ar šī klienta demogrāfiskā profila lietotājiem.</span><span class="sxs-lookup"><span data-stu-id="12220-199">In the customer card, you'll find charts for the brands or interests that people in that customer's demographic profile have affinity for.</span></span>

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Klienta kartīte ar bagātinātiem datiem":::

## <a name="next-steps"></a><span data-ttu-id="12220-201">Nākamās darbības</span><span class="sxs-lookup"><span data-stu-id="12220-201">Next steps</span></span>

<span data-ttu-id="12220-202">Būvējiet virs saviem bagātinātajiem klientu datiem.</span><span class="sxs-lookup"><span data-stu-id="12220-202">Build on top of your enriched customer data.</span></span> <span data-ttu-id="12220-203">Veidojiet [segmentus](segments.md), [mērus](measures.md)un pat [eksportējiet datus](export-destinations.md), lai klientiem sniegtu personalizētas iespējas.</span><span class="sxs-lookup"><span data-stu-id="12220-203">Create [Segments](segments.md), [Measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
