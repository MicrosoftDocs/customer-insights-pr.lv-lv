---
title: Vienoto klientu profilu bagātināšana
description: Izmantojiet iespējas, lai bagātinātu klientu datus.
ms.date: 11/02/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c25cfbf3808fc1534b54d2d834f1c63ff4c9fe0a
ms.sourcegitcommit: 334633cbd58f5659d20b4f87252c1a10cc7130db
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 12/03/2020
ms.locfileid: "4667103"
---
# <a name="enrichment-for-customer-profiles-preview"></a><span data-ttu-id="000e5-103">Klientu profilu bagātināšana (priekšskatījums)</span><span class="sxs-lookup"><span data-stu-id="000e5-103">Enrichment for customer profiles (preview)</span></span>

<span data-ttu-id="000e5-104">Izmantojiet avotu datus, piemēram, no Microsoft un citiem partneriem, lai bagātinātu klientu datus.</span><span class="sxs-lookup"><span data-stu-id="000e5-104">Use data from sources like Microsoft and other partners to enrich your customer data.</span></span>

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Bagātināšanas centra lapa":::

<span data-ttu-id="000e5-106">Informāciju par auditorijas ieskatiem skatiet sadaļā **Dati** > **Bagātināšana**, lai strādātu ar bagātināšanas iespējām.</span><span class="sxs-lookup"><span data-stu-id="000e5-106">In audience insights, go to **Data** > **Enrichment** to work with enrichment options.</span></span>    
<span data-ttu-id="000e5-107">Lai izveidotu vai rediģētu bagātināšanos, jums ir nepieciešamas Līdzstrādnieka vai Administratora atļaujas.</span><span class="sxs-lookup"><span data-stu-id="000e5-107">You need to have Contributor or Administrator permissions to create or edit enrichments.</span></span> <span data-ttu-id="000e5-108">Lai iegūtu papildinformāciju, skatiet [Atļaujas](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="000e5-108">For more information, see [Permissions](permissions.md).</span></span>

<span data-ttu-id="000e5-109">Cilnē **Atklāt** atradīsiet šādus bagātinātājus:</span><span class="sxs-lookup"><span data-stu-id="000e5-109">On the **Discover** tab, you'll find the following enrichments:</span></span>

- <span data-ttu-id="000e5-110">[Zīmoli](enrichment-microsoft-graph.md) nodrošina Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="000e5-110">[Brands](enrichment-microsoft-graph.md) provided by Microsoft Graph</span></span>
- <span data-ttu-id="000e5-111">[Intereses](enrichment-microsoft-graph.md) nodrošina Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="000e5-111">[Interests](enrichment-microsoft-graph.md) provided by Microsoft Graph</span></span>
- <span data-ttu-id="000e5-112">Leadspace nodrošinātie [uzņēmuma dati](enrichment-leadspace.md)</span><span class="sxs-lookup"><span data-stu-id="000e5-112">[Company data](enrichment-leadspace.md) provided by Leadspace</span></span>
- <span data-ttu-id="000e5-113">Experian nodrošinātie [demogrāfijas dati](enrichment-experian.md)</span><span class="sxs-lookup"><span data-stu-id="000e5-113">[Demographics](enrichment-experian.md) provided by Experian</span></span>
- <span data-ttu-id="000e5-114">[Atrašanās vietas dati](enrichment-here.md) HERE Technologies nodrošinātie atrašanās vietas dati</span><span class="sxs-lookup"><span data-stu-id="000e5-114">[Location data](enrichment-here.md) provided by HERE Technologies</span></span>
- <span data-ttu-id="000e5-115">[Pielāgoti dati](enrichment-SFTP-custom-import.md), izmantojot Drošās failu pārsūtīšanas protokolu (SFTP)</span><span class="sxs-lookup"><span data-stu-id="000e5-115">[Custom data](enrichment-SFTP-custom-import.md) through Secure File Transfer Protocol (SFTP)</span></span>

<span data-ttu-id="000e5-116">Cilnē **Manas bagātināšanas** varat redzēt jūsu konfigurētos bagātinājumus un rediģēt to rekvizītus.</span><span class="sxs-lookup"><span data-stu-id="000e5-116">On the **My enrichments** tab, you can see the enrichments you've configured and edit their properties.</span></span>

## <a name="manage-existing-enrichments"></a><span data-ttu-id="000e5-117">Esošo papildinājumu pārvaldība</span><span class="sxs-lookup"><span data-stu-id="000e5-117">Manage existing enrichments</span></span>

<span data-ttu-id="000e5-118">Lai redzētu visus konfigurētos bagātinājumus, dodieties uz **Mani papildinājumi**.</span><span class="sxs-lookup"><span data-stu-id="000e5-118">Go to the **My enrichments** to see all configured enrichments.</span></span> <span data-ttu-id="000e5-119">Katrs bagātinājums tiek attēlots kā rinda, kurā ir iekļauta papildu informācija par bagātinājumu.</span><span class="sxs-lookup"><span data-stu-id="000e5-119">Each enrichment is represented as a row that includes additional information about the enrichment.</span></span>

<span data-ttu-id="000e5-120">Atlasiet bagātinājumu, lai skatītu pieejamās opcijas.</span><span class="sxs-lookup"><span data-stu-id="000e5-120">Select an enrichment to see the available options.</span></span> <span data-ttu-id="000e5-121">Vai arī, lai skatītu opcijas, varat atlasīt daudzpunkti (...) saraksta elementā.</span><span class="sxs-lookup"><span data-stu-id="000e5-121">Alternatively, you can select the ellipsis (...) on a list item to see the options.</span></span>

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Opcijas bagātinājumu pārvaldībai papildinājumu sarakstā":::

- <span data-ttu-id="000e5-123">**Skatiet** detalizēto informāciju par bagātināšanu ar bagātināto klientu profilu skaitu.</span><span class="sxs-lookup"><span data-stu-id="000e5-123">**View** enrichment details with the number of enriched customer profiles.</span></span>
- <span data-ttu-id="000e5-124">**Rediģējiet** bagātināšanas konfigurāciju.</span><span class="sxs-lookup"><span data-stu-id="000e5-124">**Edit** the enrichment configuration.</span></span>
- <span data-ttu-id="000e5-125">**Palaidiet** bagātinājumu, lai atjauninātu klientu profilus ar jaunākajiem datiem.</span><span class="sxs-lookup"><span data-stu-id="000e5-125">**Run** the enrichment to update customer profiles with the latest data.</span></span>
- <span data-ttu-id="000e5-126">**Deaktivizējiet** esošu bagātinājumu, lai neļautu tam automātiski atsvaidzināties ar katru plānoto atsvaidzināšanu.</span><span class="sxs-lookup"><span data-stu-id="000e5-126">**Deactivate** an existing enrichment to stop it from refreshing automatically with every scheduled refresh.</span></span> <span data-ttu-id="000e5-127">Dati no pēdējās sekmīgās atsvaidzināšanas joprojām būs pieejami.</span><span class="sxs-lookup"><span data-stu-id="000e5-127">Data from the last successful refresh will continue to be available.</span></span> <span data-ttu-id="000e5-128">**Aktivizējiet** neaktīvu bagātināšanu, lai restartētu automātisko atsvaidzināšanu ar katru plānoto atsvaidzināšanu.</span><span class="sxs-lookup"><span data-stu-id="000e5-128">**Activate** an inactive enrichment to restart automatic refreshing with every scheduled refresh.</span></span>
- <span data-ttu-id="000e5-129">**Dzēst** bagātināšanu.</span><span class="sxs-lookup"><span data-stu-id="000e5-129">**Delete** an enrichment.</span></span>

<span data-ttu-id="000e5-130">Vairākus bagātinājumus var vienlaicīgi palaist vai deaktivizēt, tos atlasot sarakstā.</span><span class="sxs-lookup"><span data-stu-id="000e5-130">You can run or deactivate multiple enrichments at once by selecting them in the list.</span></span> <span data-ttu-id="000e5-131">Skatīšanas un rediģēšanas opcijas nav pieejamas kā lielapjoma darbība un vienlaicīgi darbojas tikai vienai veiktajai bagātināšanai.</span><span class="sxs-lookup"><span data-stu-id="000e5-131">View and edit options aren't available as bulk action and only work for one enrichment at a time.</span></span>
