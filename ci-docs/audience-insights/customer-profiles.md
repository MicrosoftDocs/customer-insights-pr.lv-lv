---
title: Klientu profilu skatīšana
description: Iegūstiet kombinētu skatu ar jūsu apvienotajiem klientu datiem.
ms.date: 12/01/2020
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 13308c2f40cda0d7e813b4d94ab47d53b5ce2115
ms.sourcegitcommit: a6e7df90d61450e00886753eb5db116f2f35bb6c
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 12/01/2020
ms.locfileid: "4653899"
---
# <a name="customer-profiles"></a><span data-ttu-id="8e5af-103">Klientu profili</span><span class="sxs-lookup"><span data-stu-id="8e5af-103">Customer profiles</span></span>

<span data-ttu-id="8e5af-104">Lapā **Klienti** tiek parādīts apvienots klientu skatījums, pamatojoties uz profila datiem, kas apkopoti no [visiem datu avotiem](data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="8e5af-104">The **Customers** page shows a combined view of your customers, based on profile data gathered from [all data sources](data-sources.md).</span></span> <span data-ttu-id="8e5af-105">Klientu profili ir pieejami, kad [izveidojat vienotu klienta entītiju](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="8e5af-105">Customer profiles are available once you [create the unified Customer entity](data-unification.md).</span></span> <span data-ttu-id="8e5af-106">Pārliecinieties, vai esat pabeidzis datu apvienošanas procesu, lai iegūtu plašākus klientu skatus.</span><span class="sxs-lookup"><span data-stu-id="8e5af-106">Make sure you complete the data unification process to get richer views of your customers.</span></span> <span data-ttu-id="8e5af-107">Šī lapa arī sniedz iespēju meklēt klientus.</span><span class="sxs-lookup"><span data-stu-id="8e5af-107">The page also lets you search for customers.</span></span>

<span data-ttu-id="8e5af-108">Klienti var būt personas vai organizācijas (priekšskatījums).</span><span class="sxs-lookup"><span data-stu-id="8e5af-108">Customers can be individuals or organizations (preview).</span></span> <span data-ttu-id="8e5af-109">Katram klientam vai organizācijas profilam tiek piešķirts elements.</span><span class="sxs-lookup"><span data-stu-id="8e5af-109">Each customer or organization profile is represented by a tile.</span></span> <span data-ttu-id="8e5af-110">Atlasiet elementu, lai skatītu papildinformāciju par noteiktu klientu vai organizāciju.</span><span class="sxs-lookup"><span data-stu-id="8e5af-110">Select a tile to see additional information on that specific customer or organization.</span></span> <span data-ttu-id="8e5af-111">Lapas apakšdaļā izmantojiet lappušu numerācijas vadīklas, lai skatītu papildu ierakstus.</span><span class="sxs-lookup"><span data-stu-id="8e5af-111">Use the pagination controls at the bottom of the page to see additional records.</span></span>

> [!div class="mx-imgBorder"] 
> <span data-ttu-id="8e5af-112">![B2C klienta profils](media/profiles-customers.png "B2C klienta profili")</span><span class="sxs-lookup"><span data-stu-id="8e5af-112">![B2C customer profiles](media/profiles-customers.png "B2C customer profiles")</span></span>

<span data-ttu-id="8e5af-113">Organizācijas (priekšskatījums)</span><span class="sxs-lookup"><span data-stu-id="8e5af-113">Organizations (Preview)</span></span>
> [!div class="mx-imgBorder"] 
> <span data-ttu-id="8e5af-114">![B2B klienta profils](media/profile-customers-b2b.png "B2B klienta profili")</span><span class="sxs-lookup"><span data-stu-id="8e5af-114">![B2B customer profiles](media/profile-customers-b2b.png "B2B customer profiles")</span></span>

> [!NOTE]
> <span data-ttu-id="8e5af-115">Ja, navigācijas rūtī atlasot **Klienti**, neredzat rūtis, jūsu administratoram ir [jādefinē vismaz viens meklējams atribūts](search-filter-index.md) **Meklēšanas un filtrēšanas indeksā**.</span><span class="sxs-lookup"><span data-stu-id="8e5af-115">If you can't see the tiles when you select **Customers** in navigation, your administrator needs to [define at least one searchable attribute](search-filter-index.md) on the **Search & filter index**.</span></span>

## <a name="search-for-customers"></a><span data-ttu-id="8e5af-116">Meklēt klientus</span><span class="sxs-lookup"><span data-stu-id="8e5af-116">Search for customers</span></span>

<span data-ttu-id="8e5af-117">Meklējiet klientus, meklēšanas lodziņā ievadot vārdu vai citu atribūtu.</span><span class="sxs-lookup"><span data-stu-id="8e5af-117">Search for customers by entering a name or some other attribute in the search box.</span></span> <span data-ttu-id="8e5af-118">Meklēšana darbojas tikai klienta profila entītijā, kas ir izveidota datu apvienošanas procesā.</span><span class="sxs-lookup"><span data-stu-id="8e5af-118">The search only works within the Customer Profile entity created during the data unification process.</span></span>

<span data-ttu-id="8e5af-119">Kā administrators varat konfigurēt meklēšanas atribūtus, izmantojot **Meklēšanas un filtrēšanas rādītāja** lapu.</span><span class="sxs-lookup"><span data-stu-id="8e5af-119">As an admin, you can configure the searchable attributes using the **Search & filter index** page.</span></span> <span data-ttu-id="8e5af-120">Papildinformāciju skatiet sadaļā [Pārvaldīt meklēšanas un filtra rādītāju](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="8e5af-120">For more information, see [Manage search & filter index](search-filter-index.md).</span></span>

## <a name="filter-customers"></a><span data-ttu-id="8e5af-121">Filtrēt klientus</span><span class="sxs-lookup"><span data-stu-id="8e5af-121">Filter customers</span></span>

<span data-ttu-id="8e5af-122">Klientus var filtrēt pēc Klienta profila entītijas laukiem.</span><span class="sxs-lookup"><span data-stu-id="8e5af-122">You can filter customers by the Customer Profile entity fields.</span></span> <span data-ttu-id="8e5af-123">Līdzīgi meklēšanai — jūsu administratoram vispirms ir jādefinē lauki kā filtrējami, izmantojot lapu **Meklēšanas un filtra rādītājs**.</span><span class="sxs-lookup"><span data-stu-id="8e5af-123">Similar to search, your admin will first need to define the fields as filterable using the **Search & filter index** page.</span></span>

1. <span data-ttu-id="8e5af-124">Lapā **Klienti** atlasiet **Filtrs**.</span><span class="sxs-lookup"><span data-stu-id="8e5af-124">Select **Filter** on the **Customers** page.</span></span>

2. <span data-ttu-id="8e5af-125">Atzīmējiet lodziņus blakus atribūtiem, pēc kuriem vēlaties filtrēt klientus.</span><span class="sxs-lookup"><span data-stu-id="8e5af-125">Check the boxes next to the attributes you want to filter customers by.</span></span>

   > [!div class="mx-imgBorder"] 
   > <span data-ttu-id="8e5af-126">![Klientu profili](media/profiles-customers3.png "Klientu profili")</span><span class="sxs-lookup"><span data-stu-id="8e5af-126">![Customer profiles](media/profiles-customers3.png "Customer profiles")</span></span>

3. <span data-ttu-id="8e5af-127">Noņemiet filtrus, atlasot lapā **Klienti** **Notīrīt filtrus**.</span><span class="sxs-lookup"><span data-stu-id="8e5af-127">Remove your filters by selecting **Clear filters** on the **Customers** page.</span></span>

##  <a name="customer-details-page"></a><span data-ttu-id="8e5af-128">Detalizēta informācija par klientu</span><span class="sxs-lookup"><span data-stu-id="8e5af-128">Customer details page</span></span>

<span data-ttu-id="8e5af-129">Atlasiet jebkuru no klientu elementiem, lai atvērtu **Klientu detalizētās informācijas lapu**.</span><span class="sxs-lookup"><span data-stu-id="8e5af-129">Select any of the customer tiles to open the **Customer details page**.</span></span> <span data-ttu-id="8e5af-130">Šajā skatā ir ietverta vienota informācija par atlasīto klientu.</span><span class="sxs-lookup"><span data-stu-id="8e5af-130">This view contains unified information for the selected customer.</span></span>

<span data-ttu-id="8e5af-131">Detalizēta informācija par klientu:</span><span class="sxs-lookup"><span data-stu-id="8e5af-131">Customer details include:</span></span>

-   <span data-ttu-id="8e5af-132">**Klienta profila elements:** Šis elements rāda dažādas vērtības no vienotā klienta profila entītijas.</span><span class="sxs-lookup"><span data-stu-id="8e5af-132">**Customer profile tile:** This tile shows the different values from the unified customer profile entity.</span></span> <span data-ttu-id="8e5af-133">Šī detalizētā informācija var ietvert e-pasta adresi, nosaukumu, pilsētu un citus datus.</span><span class="sxs-lookup"><span data-stu-id="8e5af-133">These details can include email address, name, city, and so on.</span></span> 

-   <span data-ttu-id="8e5af-134">**Iespējamās intereses, potenciālie zīmoli:** Rāda, ja esat konfigurējis pirmās puses bagātināšanu.</span><span class="sxs-lookup"><span data-stu-id="8e5af-134">**Potential interests, potential brands:** Shows if you configured a first-party enrichment.</span></span> <span data-ttu-id="8e5af-135">Tas ataino iespējamas intereses un zīmolu radniecību, kāda varētu būt klientam ar šim klientam līdzīgu profilu.</span><span class="sxs-lookup"><span data-stu-id="8e5af-135">It represents potential interests and affinities for brands a customer with a profile similar to this customer might have.</span></span> <span data-ttu-id="8e5af-136">Papildinformāciju skatiet tēmā [Klientu profilu bagātināšana ar zīmolu un interešu radniecības datiem](enrichment-microsoft-graph.md).</span><span class="sxs-lookup"><span data-stu-id="8e5af-136">For more information, see [Enrich customer profiles with brand and interest affinities](enrichment-microsoft-graph.md).</span></span>

-   <span data-ttu-id="8e5af-137">**Pasākumi:** Parāda, vai esat konfigurējis vienu vai vairākus noteikta tipa pasākumus: klientu atribūta mērvienības.</span><span class="sxs-lookup"><span data-stu-id="8e5af-137">**Measures:** Shows if you configured one or more measures of a specific type: customer attribute measures.</span></span> <span data-ttu-id="8e5af-138">Tie iekļauj aprēķinātos KPI ap saviem klientiem atsevišķā klientu līmenī.</span><span class="sxs-lookup"><span data-stu-id="8e5af-138">They include calculated KPIs around your customers on the individual customer level.</span></span> <span data-ttu-id="8e5af-139">Papildinformāciju skatiet tēmā [Pasākumu definēšana un pārvaldīšana](measures.md).</span><span class="sxs-lookup"><span data-stu-id="8e5af-139">For more information, see [Define and manage measures](measures.md).</span></span>

-   <span data-ttu-id="8e5af-140">**Darbības laika skala:** Rāda, vai ir konfigurētas darbības.</span><span class="sxs-lookup"><span data-stu-id="8e5af-140">**Activity timeline:** Shows if you have configured activities.</span></span> <span data-ttu-id="8e5af-141">Laika skalas skats ietver šī klienta hronoloģiski kārtotās darbības, sākot ar pēdējo darbību.</span><span class="sxs-lookup"><span data-stu-id="8e5af-141">The timeline view contains chronologically sorted activities of this customer, starting with the most recent activity.</span></span> <span data-ttu-id="8e5af-142">Papildinformācijai skatiet [Klientu darbības](activities.md).</span><span class="sxs-lookup"><span data-stu-id="8e5af-142">For more information, see [Customer activities](activities.md).</span></span>

<span data-ttu-id="8e5af-143">Atlasiet **Atpakaļ pie klientiem**, lai atgrieztos klientu meklēšanas lapā.</span><span class="sxs-lookup"><span data-stu-id="8e5af-143">Select **Back to Customers** to return to the customer search page.</span></span>

## <a name="next-steps"></a><span data-ttu-id="8e5af-144">Nākamās darbības</span><span class="sxs-lookup"><span data-stu-id="8e5af-144">Next steps</span></span>

<span data-ttu-id="8e5af-145">[Pievienojiet papildu datu avotus](data-sources.md) vai [izveidojiet klientu segmentus](segments.md).</span><span class="sxs-lookup"><span data-stu-id="8e5af-145">[Add more data sources](data-sources.md) or [create customer segments](segments.md).</span></span>
