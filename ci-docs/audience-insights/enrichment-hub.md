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
ms.openlocfilehash: 10c338b89a6f9971912d05986c105cba1221b01b
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896014"
---
# <a name="enrichment-for-customer-profiles-preview"></a><span data-ttu-id="25a7a-103">Klientu profilu bagātināšana (priekšskatījums)</span><span class="sxs-lookup"><span data-stu-id="25a7a-103">Enrichment for customer profiles (preview)</span></span>

<span data-ttu-id="25a7a-104">Izmantojiet avotu datus, piemēram, no Microsoft un citiem partneriem, lai bagātinātu klientu datus.</span><span class="sxs-lookup"><span data-stu-id="25a7a-104">Use data from sources like Microsoft and other partners to enrich your customer data.</span></span>

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Bagātināšanas centra lapa":::

<span data-ttu-id="25a7a-106">Informāciju par auditorijas ieskatiem skatiet sadaļā **Dati** > **Bagātināšana**, lai strādātu ar bagātināšanas iespējām.</span><span class="sxs-lookup"><span data-stu-id="25a7a-106">In audience insights, go to **Data** > **Enrichment** to work with enrichment options.</span></span>    
<span data-ttu-id="25a7a-107">Lai izveidotu vai rediģētu bagātināšanos, jums ir nepieciešamas Līdzstrādnieka vai Administratora atļaujas.</span><span class="sxs-lookup"><span data-stu-id="25a7a-107">You need to have Contributor or Administrator permissions to create or edit enrichments.</span></span> <span data-ttu-id="25a7a-108">Lai iegūtu papildinformāciju, skatiet [Atļaujas](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="25a7a-108">For more information, see [Permissions](permissions.md).</span></span>

<span data-ttu-id="25a7a-109">Cilnē **Atklāt** atradīsiet šādus bagātinātājus:</span><span class="sxs-lookup"><span data-stu-id="25a7a-109">On the **Discover** tab, you'll find the following enrichments:</span></span>

- <span data-ttu-id="25a7a-110">Microsoft nodrošinātie [Zīmoli](enrichment-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="25a7a-110">[Brands](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="25a7a-111">Microsoft nodrošinātās [Intereses](enrichment-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="25a7a-111">[Interests](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="25a7a-112">Leadspace nodrošinātie [uzņēmuma dati](enrichment-leadspace.md)</span><span class="sxs-lookup"><span data-stu-id="25a7a-112">[Company data](enrichment-leadspace.md) provided by Leadspace</span></span>
- <span data-ttu-id="25a7a-113">Experian nodrošinātie [demogrāfijas dati](enrichment-experian.md)</span><span class="sxs-lookup"><span data-stu-id="25a7a-113">[Demographics](enrichment-experian.md) provided by Experian</span></span>
- <span data-ttu-id="25a7a-114">[Atrašanās vietas dati](enrichment-here.md) HERE Technologies nodrošinātie atrašanās vietas dati</span><span class="sxs-lookup"><span data-stu-id="25a7a-114">[Location data](enrichment-here.md) provided by HERE Technologies</span></span>
- <span data-ttu-id="25a7a-115">[Pielāgoti dati](enrichment-SFTP-custom-import.md), izmantojot Drošās failu pārsūtīšanas protokolu (SFTP)</span><span class="sxs-lookup"><span data-stu-id="25a7a-115">[Custom data](enrichment-SFTP-custom-import.md) through Secure File Transfer Protocol (SFTP)</span></span>

<span data-ttu-id="25a7a-116">Cilnē **Manas bagātināšanas** varat redzēt jūsu konfigurētos bagātinājumus un rediģēt to rekvizītus.</span><span class="sxs-lookup"><span data-stu-id="25a7a-116">On the **My enrichments** tab, you can see the enrichments you've configured and edit their properties.</span></span>

## <a name="manage-existing-enrichments"></a><span data-ttu-id="25a7a-117">Esošo papildinājumu pārvaldība</span><span class="sxs-lookup"><span data-stu-id="25a7a-117">Manage existing enrichments</span></span>

<span data-ttu-id="25a7a-118">Lai redzētu visus konfigurētos bagātinājumus, dodieties uz **Mani papildinājumi**.</span><span class="sxs-lookup"><span data-stu-id="25a7a-118">Go to the **My enrichments** to see all configured enrichments.</span></span> <span data-ttu-id="25a7a-119">Katrs bagātinājums tiek attēlots kā rinda, kurā ir iekļauta papildu informācija par bagātinājumu.</span><span class="sxs-lookup"><span data-stu-id="25a7a-119">Each enrichment is represented as a row that includes additional information about the enrichment.</span></span>

<span data-ttu-id="25a7a-120">Atlasiet bagātinājumu, lai skatītu pieejamās opcijas.</span><span class="sxs-lookup"><span data-stu-id="25a7a-120">Select an enrichment to see the available options.</span></span> <span data-ttu-id="25a7a-121">Lai skatītu opcijas, varat arī saraksta elementā atlasīt daudzpunkti (...).</span><span class="sxs-lookup"><span data-stu-id="25a7a-121">You can also select the ellipsis (...) on a list item to see the options.</span></span>

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Opcijas bagātinājumu pārvaldībai papildinājumu sarakstā":::

- <span data-ttu-id="25a7a-123">**Skatiet** detalizēto informāciju par bagātināšanu ar bagātināto klientu profilu skaitu.</span><span class="sxs-lookup"><span data-stu-id="25a7a-123">**View** enrichment details with the number of enriched customer profiles.</span></span>
- <span data-ttu-id="25a7a-124">**Rediģējiet** bagātināšanas konfigurāciju.</span><span class="sxs-lookup"><span data-stu-id="25a7a-124">**Edit** the enrichment configuration.</span></span>
- <span data-ttu-id="25a7a-125">**Palaidiet** bagātinājumu, lai atjauninātu klientu profilus ar jaunākajiem datiem.</span><span class="sxs-lookup"><span data-stu-id="25a7a-125">**Run** the enrichment to update customer profiles with the latest data.</span></span>
- <span data-ttu-id="25a7a-126">**Deaktivizējiet** esošu bagātinājumu, lai neļautu tam automātiski atsvaidzināties ar katru plānoto atsvaidzināšanu.</span><span class="sxs-lookup"><span data-stu-id="25a7a-126">**Deactivate** an existing enrichment to stop it from refreshing automatically with every scheduled refresh.</span></span> <span data-ttu-id="25a7a-127">Dati no pēdējās sekmīgās atsvaidzināšanas joprojām būs pieejami.</span><span class="sxs-lookup"><span data-stu-id="25a7a-127">Data from the last successful refresh will continue to be available.</span></span> <span data-ttu-id="25a7a-128">**Aktivizējiet** neaktīvu bagātināšanu, lai restartētu automātisko atsvaidzināšanu ar katru plānoto atsvaidzināšanu.</span><span class="sxs-lookup"><span data-stu-id="25a7a-128">**Activate** an inactive enrichment to restart automatic refreshing with every scheduled refresh.</span></span>
- <span data-ttu-id="25a7a-129">**Dzēst** bagātināšanu.</span><span class="sxs-lookup"><span data-stu-id="25a7a-129">**Delete** an enrichment.</span></span>

<span data-ttu-id="25a7a-130">Vairākus bagātinājumus var vienlaicīgi palaist vai deaktivizēt, tos atlasot sarakstā.</span><span class="sxs-lookup"><span data-stu-id="25a7a-130">You can run or deactivate multiple enrichments at once by selecting them in the list.</span></span> <span data-ttu-id="25a7a-131">Skatīšanas un rediģēšanas opcijas nav pieejamas kā lielapjoma darbība un vienlaicīgi darbojas tikai vienai veiktajai bagātināšanai.</span><span class="sxs-lookup"><span data-stu-id="25a7a-131">View and edit options aren't available as bulk action and only work for one enrichment at a time.</span></span>

## <a name="enrichments-and-connections"></a><span data-ttu-id="25a7a-132">Bagātināšana un savienojumi</span><span class="sxs-lookup"><span data-stu-id="25a7a-132">Enrichments and connections</span></span>

<span data-ttu-id="25a7a-133">Trešo pušu bagātinātos datus konfigurē, izmantojot [savienojumus](connections.md), kurus administrators iestata ar akreditāciju un kuru pārnesei tiek sniegta piekrišana.</span><span class="sxs-lookup"><span data-stu-id="25a7a-133">Third-party enrichments are configured using [connections](connections.md), which an administrator sets up with credentials and provides consent for data transfers.</span></span> <span data-ttu-id="25a7a-134">Administratori un līdzstrādnieki var izmantot savienojumus, lai konfigurētu bagātinātos datus.</span><span class="sxs-lookup"><span data-stu-id="25a7a-134">The connection can be used by administrators and contributors to configure enrichments.</span></span>  

## <a name="multiple-enrichments-of-the-same-type"></a><span data-ttu-id="25a7a-135">Vairāki viena veida bagātinātie dati</span><span class="sxs-lookup"><span data-stu-id="25a7a-135">Multiple enrichments of the same type</span></span>

<span data-ttu-id="25a7a-136">Bagātināmo entitīju norāda bagātināšanas konfigurēšanas laikā, kas ļauj bagātināt vienīgi jūsu profilu apakškopu.</span><span class="sxs-lookup"><span data-stu-id="25a7a-136">The entity to be enriched is specified during the enrichment configuration, which allows you to enrich only a subset of your profiles.</span></span> <span data-ttu-id="25a7a-137">Piemēram, bagātināt datus tikai konkrētam segmentam.</span><span class="sxs-lookup"><span data-stu-id="25a7a-137">For exmaple, enrich data only for a specific segment.</span></span> <span data-ttu-id="25a7a-138">Jūs varat konfigurēt vairākus viena veida bagātinātos datus un atkārtoti izmantot to pašu savienojumu.</span><span class="sxs-lookup"><span data-stu-id="25a7a-138">You can configure several enrichments of the same type and reuse the same connection.</span></span> <span data-ttu-id="25a7a-139">Daži bagātinātie dati tiks ierobežoti līdz atļautajam bagātināmo datu izveides skaitam.</span><span class="sxs-lookup"><span data-stu-id="25a7a-139">Some enrichments will have limits to the number of enrichments of the same type that can be created.</span></span> <span data-ttu-id="25a7a-140">Ierobežojumus un pašreizējo lietojumu var aplūkot lapā **Bagātināšana**.</span><span class="sxs-lookup"><span data-stu-id="25a7a-140">The limits and current use can be seen on the **Enrichment** page.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
