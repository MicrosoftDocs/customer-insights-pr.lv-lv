---
title: Vienoto klientu profilu bagātināšana
description: Izmantojiet iespējas, lai bagātinātu klientu datus.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: c35e73b366fcd5db2ba5a757295ddda6db30efa0
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305257"
---
# <a name="enrichment-for-customer-profiles-preview"></a><span data-ttu-id="44842-103">Klientu profilu bagātināšana (priekšskatījums)</span><span class="sxs-lookup"><span data-stu-id="44842-103">Enrichment for customer profiles (preview)</span></span>

<span data-ttu-id="44842-104">Izmantojiet avotu datus, piemēram, no Microsoft un citiem partneriem, lai bagātinātu klientu datus.</span><span class="sxs-lookup"><span data-stu-id="44842-104">Use data from sources like Microsoft and other partners to enrich your customer data.</span></span>

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Bagātināšanas centra lapa":::

<span data-ttu-id="44842-106">Informāciju par auditorijas ieskatiem skatiet sadaļā **Dati** > **Bagātināšana**, lai strādātu ar bagātināšanas iespējām.</span><span class="sxs-lookup"><span data-stu-id="44842-106">In audience insights, go to **Data** > **Enrichment** to work with enrichment options.</span></span>  

<span data-ttu-id="44842-107">Lai izveidotu vai rediģētu bagātināšanos, jums ir nepieciešamas Līdzstrādnieka vai Administratora atļaujas.</span><span class="sxs-lookup"><span data-stu-id="44842-107">You need to have Contributor or Administrator permissions to create or edit enrichments.</span></span> <span data-ttu-id="44842-108">Lai iegūtu papildinformāciju, skatiet [Atļaujas](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="44842-108">For more information, see [Permissions](permissions.md).</span></span>

<span data-ttu-id="44842-109">Cilnē **Atklāt** atradīsiet šādus bagātinātājus:</span><span class="sxs-lookup"><span data-stu-id="44842-109">On the **Discover** tab, you'll find the following enrichments:</span></span>

- <span data-ttu-id="44842-110">Microsoft nodrošinātie [Zīmoli](enrichment-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="44842-110">[Brands](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="44842-111">Microsoft nodrošinātās [Intereses](enrichment-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="44842-111">[Interests](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="44842-112">[Paplašinātās adreses](enrichment-enhanced-addresses.md), ko nodrošina Microsoft</span><span class="sxs-lookup"><span data-stu-id="44842-112">[Enhanced addresses](enrichment-enhanced-addresses.md) provided by Microsoft</span></span>
- <span data-ttu-id="44842-113">Leadspace nodrošinātie [uzņēmuma dati](enrichment-leadspace.md)</span><span class="sxs-lookup"><span data-stu-id="44842-113">[Company data](enrichment-leadspace.md) provided by Leadspace</span></span>
- <span data-ttu-id="44842-114">[Demogrāfiskie dati](enrichment-experian.md), ko nodrošina Experian</span><span class="sxs-lookup"><span data-stu-id="44842-114">[Demographics](enrichment-experian.md) provided by Experian</span></span>
- <span data-ttu-id="44842-115">[Atrašanās vietas dati](enrichment-here.md) HERE Technologies nodrošinātie atrašanās vietas dati</span><span class="sxs-lookup"><span data-stu-id="44842-115">[Location data](enrichment-here.md) provided by HERE Technologies</span></span>
- <span data-ttu-id="44842-116">[Pielāgoti dati](enrichment-SFTP-custom-import.md), izmantojot Drošās failu pārsūtīšanas protokolu (SFTP)</span><span class="sxs-lookup"><span data-stu-id="44842-116">[Custom data](enrichment-SFTP-custom-import.md) through Secure File Transfer Protocol (SFTP)</span></span>

<span data-ttu-id="44842-117">Cilnē **Manas bagātināšanas** varat redzēt jūsu konfigurētos bagātinājumus un rediģēt to rekvizītus.</span><span class="sxs-lookup"><span data-stu-id="44842-117">On the **My enrichments** tab, you can see the enrichments you've configured and edit their properties.</span></span>

## <a name="manage-existing-enrichments"></a><span data-ttu-id="44842-118">Esošo papildinājumu pārvaldība</span><span class="sxs-lookup"><span data-stu-id="44842-118">Manage existing enrichments</span></span>

<span data-ttu-id="44842-119">Lai skatītu visus konfigurētos bagātinātos datus, dodieties uz **Manas bagātināšanas** cilni.</span><span class="sxs-lookup"><span data-stu-id="44842-119">Go to the **My enrichments** tab to see all configured enrichments.</span></span> <span data-ttu-id="44842-120">Katrs bagātinājums tiek attēlots kā rinda, kurā ir iekļauta papildu informācija par bagātinājumu.</span><span class="sxs-lookup"><span data-stu-id="44842-120">Each enrichment is represented as a row that includes additional information about the enrichment.</span></span>

<span data-ttu-id="44842-121">Atlasiet bagātinājumu, lai skatītu pieejamās opcijas.</span><span class="sxs-lookup"><span data-stu-id="44842-121">Select an enrichment to see the available options.</span></span> <span data-ttu-id="44842-122">Lai skatītu opcijas, varat arī saraksta elementā atlasīt daudzpunkti (...).</span><span class="sxs-lookup"><span data-stu-id="44842-122">You can also select the ellipsis (...) on a list item to see the options.</span></span>

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Opcijas bagātinājumu pārvaldībai papildinājumu sarakstā":::

- <span data-ttu-id="44842-124">**Skatiet** detalizēto informāciju par bagātināšanu ar bagātināto klientu profilu skaitu.</span><span class="sxs-lookup"><span data-stu-id="44842-124">**View** enrichment details with the number of enriched customer profiles.</span></span>
- <span data-ttu-id="44842-125">**Rediģējiet** bagātināšanas konfigurāciju.</span><span class="sxs-lookup"><span data-stu-id="44842-125">**Edit** the enrichment configuration.</span></span>
- <span data-ttu-id="44842-126">**Palaidiet** bagātinājumu, lai atjauninātu klientu profilus ar jaunākajiem datiem.</span><span class="sxs-lookup"><span data-stu-id="44842-126">**Run** the enrichment to update customer profiles with the latest data.</span></span>
- <span data-ttu-id="44842-127">**Deaktivizējiet** esošu bagātinājumu, lai neļautu tam automātiski atsvaidzināties ar katru plānoto atsvaidzināšanu.</span><span class="sxs-lookup"><span data-stu-id="44842-127">**Deactivate** an existing enrichment to stop it from refreshing automatically with every scheduled refresh.</span></span> <span data-ttu-id="44842-128">Dati no pēdējās sekmīgās atsvaidzināšanas joprojām būs pieejami.</span><span class="sxs-lookup"><span data-stu-id="44842-128">Data from the last successful refresh will continue to be available.</span></span> <span data-ttu-id="44842-129">**Aktivizējiet** neaktīvu bagātināšanu, lai restartētu automātisko atsvaidzināšanu ar katru plānoto atsvaidzināšanu.</span><span class="sxs-lookup"><span data-stu-id="44842-129">**Activate** an inactive enrichment to restart automatic refreshing with every scheduled refresh.</span></span>
- <span data-ttu-id="44842-130">**Dzēst** bagātināšanu.</span><span class="sxs-lookup"><span data-stu-id="44842-130">**Delete** an enrichment.</span></span>

<span data-ttu-id="44842-131">Vairākus bagātinājumus var vienlaicīgi palaist vai deaktivizēt, tos atlasot sarakstā.</span><span class="sxs-lookup"><span data-stu-id="44842-131">You can run or deactivate multiple enrichments at once by selecting them in the list.</span></span> <span data-ttu-id="44842-132">Skatīšanas un rediģēšanas opcijas nav pieejamas kā lielapjoma darbība un vienlaicīgi darbojas tikai vienai veiktajai bagātināšanai.</span><span class="sxs-lookup"><span data-stu-id="44842-132">View and edit options aren't available as bulk action and only work for one enrichment at a time.</span></span>

## <a name="enrichments-and-connections"></a><span data-ttu-id="44842-133">Bagātināšana un savienojumi</span><span class="sxs-lookup"><span data-stu-id="44842-133">Enrichments and connections</span></span>

<span data-ttu-id="44842-134">Trešo pušu bagātinātos datus konfigurē, izmantojot [savienojumus](connections.md), kurus administrators iestata ar akreditāciju un kuru pārnesei tiek sniegta piekrišana.</span><span class="sxs-lookup"><span data-stu-id="44842-134">Third-party enrichments are configured using [connections](connections.md), which an administrator sets up with credentials and provides consent for data transfers.</span></span> <span data-ttu-id="44842-135">Administratori un līdzstrādnieki var izmantot savienojumus, lai konfigurētu bagātinātos datus.</span><span class="sxs-lookup"><span data-stu-id="44842-135">The connection can be used by administrators and contributors to configure enrichments.</span></span>  

## <a name="multiple-enrichments-of-the-same-type"></a><span data-ttu-id="44842-136">Vairāki viena veida bagātinātie dati</span><span class="sxs-lookup"><span data-stu-id="44842-136">Multiple enrichments of the same type</span></span>

<span data-ttu-id="44842-137">Bagātināmo entitīju norāda bagātināšanas konfigurēšanas laikā, kas ļauj bagātināt vienīgi jūsu profilu apakškopu.</span><span class="sxs-lookup"><span data-stu-id="44842-137">The entity to be enriched is specified during the enrichment configuration, which allows you to enrich only a subset of your profiles.</span></span> <span data-ttu-id="44842-138">Piemēram, bagātināt datus tikai noteiktam segmentam.</span><span class="sxs-lookup"><span data-stu-id="44842-138">For example, enrich data only for a specific segment.</span></span> <span data-ttu-id="44842-139">Jūs varat konfigurēt vairākus viena veida bagātinātos datus un atkārtoti izmantot to pašu savienojumu.</span><span class="sxs-lookup"><span data-stu-id="44842-139">You can configure several enrichments of the same type and reuse the same connection.</span></span> <span data-ttu-id="44842-140">Daži bagātinātie dati tiks ierobežoti līdz atļautajam bagātināmo datu izveides skaitam.</span><span class="sxs-lookup"><span data-stu-id="44842-140">Some enrichments will have limits to the number of enrichments of the same type that can be created.</span></span> <span data-ttu-id="44842-141">Ierobežojumus un pašreizējo lietojumu var aplūkot lapā **Bagātināšana**.</span><span class="sxs-lookup"><span data-stu-id="44842-141">The limits and current use can be seen on the **Enrichment** page.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
