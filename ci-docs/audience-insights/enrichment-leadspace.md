---
title: Uzņēmumu profilu bagātināšana ar trešās puses bagātināšanas programmu Leadspace
description: Vispārēja informācija par Leadspace trešās puses bagātināšanu.
ms.date: 11/24/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 1b5c6e46e8e424df83e855d81fc4dd7ecb394e3c
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668732"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a><span data-ttu-id="871d3-103">Uzņēmuma profilu bagātināšana ar Leadspace (priekšskatījums)</span><span class="sxs-lookup"><span data-stu-id="871d3-103">Enrichment of company profiles with Leadspace (preview)</span></span>

<span data-ttu-id="871d3-104">Leadspace ir datu zinātnes uzņēmums, kas nodrošina B2B klientu datu platformu.</span><span class="sxs-lookup"><span data-stu-id="871d3-104">Leadspace is a data science company that provides a B2B Customer Data Platform.</span></span> <span data-ttu-id="871d3-105">Tā nodrošina klientiem vienotus klientu profilus, lai uzņēmumi bagātinātu datus.</span><span class="sxs-lookup"><span data-stu-id="871d3-105">It enables customers with unified customer profiles for companies to enrich their data.</span></span> <span data-ttu-id="871d3-106">Bagātinājumi ietver papildu atribūtus, kā uzņēmuma lielums, atrašanās vieta, nozare utt.</span><span class="sxs-lookup"><span data-stu-id="871d3-106">Enrichments include additional attributes such as company size, location, industry, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="871d3-107">Priekšnosacījumi</span><span class="sxs-lookup"><span data-stu-id="871d3-107">Prerequisites</span></span>

<span data-ttu-id="871d3-108">Lai konfigurētu Leadspace, ir jāizpilda tālāk aprakstītie priekšnosacījumi:</span><span class="sxs-lookup"><span data-stu-id="871d3-108">To configure Leadspace, the following prerequisites must be met:</span></span>

- <span data-ttu-id="871d3-109">Jums ir aktīva Leadspace licence un "mūžīgā atslēga" (dēvēta par **Leadspace marķieri**).</span><span class="sxs-lookup"><span data-stu-id="871d3-109">You have an active Leadspace license and the “perpetual key” (referred to as **Leadspace token**).</span></span> <span data-ttu-id="871d3-110">Lai iegūtu detalizētu informāciju par viņu produktu, sazinieties tieši ar [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/).</span><span class="sxs-lookup"><span data-stu-id="871d3-110">Contact directly [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) for details about their product.</span></span>
- <span data-ttu-id="871d3-111">ir nepieciešamas [Administratora](permissions.md#administrator) atļaujas.</span><span class="sxs-lookup"><span data-stu-id="871d3-111">You have [Administrator](permissions.md#administrator) permissions.</span></span>
- <span data-ttu-id="871d3-112">Jums ir [vienoti klientu profili](customer-profiles.md) uzņēmumiem.</span><span class="sxs-lookup"><span data-stu-id="871d3-112">You have [unified customer profiles](customer-profiles.md) for companies.</span></span>

## <a name="configuration"></a><span data-ttu-id="871d3-113">Konfigurācija</span><span class="sxs-lookup"><span data-stu-id="871d3-113">Configuration</span></span>

1. <span data-ttu-id="871d3-114">Sadaļā Auditorijas ieskati skatiet **Dati** > **Darbības**.</span><span class="sxs-lookup"><span data-stu-id="871d3-114">In audience insights, go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="871d3-115">Leadspace rūtī atlasiet **Bagātināt manus datus**.</span><span class="sxs-lookup"><span data-stu-id="871d3-115">Select **Enrich my data** on the Leadspace tile.</span></span>

   :::image type="content" source="media/leadspace-tile.png" alt-text="Leadspace mozaīkas ekrānuzņēmums.":::

1. <span data-ttu-id="871d3-117">Atlasiet vienumu **Sākt darbu** un pēc tam ievadiet aktīvu **Leadspace marķieri** (mūžīgo atslēgu).</span><span class="sxs-lookup"><span data-stu-id="871d3-117">Select **Get Started** and then enter an active **Leadspace token** (perpetual key).</span></span> <span data-ttu-id="871d3-118">Pārskatiet un sniedziet savu piekrišanu **Datu konfidencialitātei un atbilstībai**, atzīmējot izvēles rūtiņu **Piekrītu**.</span><span class="sxs-lookup"><span data-stu-id="871d3-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> <span data-ttu-id="871d3-119">Apstipriniet abas ievades, atlasot **Izveidot savienojumu ar Leadspace**.</span><span class="sxs-lookup"><span data-stu-id="871d3-119">Confirm both inputs by selecting **Connect to Leadspace**.</span></span>

1. <span data-ttu-id="871d3-120">Atlasiet **Kartēt datus** un definējiet, kuri no vienoto profilu laukiem ir jāizmanto, lai meklētu atbilstošus uzņēmuma datus no Leadspace.</span><span class="sxs-lookup"><span data-stu-id="871d3-120">Select **Map data** and define which fields from your unified profiles should be used to look for matching company data from Leadspace.</span></span> <span data-ttu-id="871d3-121">Lauks **Uzņēmuma nosaukums** ir obligāts.</span><span class="sxs-lookup"><span data-stu-id="871d3-121">The **Name of company** field is required.</span></span> <span data-ttu-id="871d3-122">Lielākai atbilstībai varat pievienot līdz diviem citiem laukiem - **Uzņēmuma tīmekļa vietne** un **Uzņēmuma atrašanās vieta**.</span><span class="sxs-lookup"><span data-stu-id="871d3-122">For a higher match accuracy, up to two other fields, **Company website** and **Company location**, can be added.</span></span>

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Leadspace lauku kartējuma rūts.":::
   
1. <span data-ttu-id="871d3-124">Atlasiet **Piemērot**, lai pabeigtu lauka kartēšanu.</span><span class="sxs-lookup"><span data-stu-id="871d3-124">Select **Apply** to complete the field mapping.</span></span>

1. <span data-ttu-id="871d3-125">Atlasiet **Palaist**, lai bagātinātu uzņēmuma profilus.</span><span class="sxs-lookup"><span data-stu-id="871d3-125">Select **Run** to enrich the company profiles.</span></span> <span data-ttu-id="871d3-126">Bagātināšanas ilgums ir atkarīgs no vienoto klientu profilu skaita.</span><span class="sxs-lookup"><span data-stu-id="871d3-126">How long an enrichment takes depends on the number of unified customer profiles.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="871d3-127">Bagātināšanas rezultāti</span><span class="sxs-lookup"><span data-stu-id="871d3-127">Enrichment results</span></span>

<span data-ttu-id="871d3-128">Pēc bagātināšanas atsvaidzināšanas varat apskatīt nesen papildinātā uzņēmuma datus [Mani papildinājumi](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="871d3-128">After refreshing the enrichment, you can review the newly enriched company data under [My enrichments](enrichment-hub.md).</span></span> <span data-ttu-id="871d3-129">Varat atrast pēdējās atjaunināšanas laiku un bagātināto profilu skaitu.</span><span class="sxs-lookup"><span data-stu-id="871d3-129">You can find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="871d3-130">Jūs varat piekļūt detalizētam katra bagātināta profila skatam, atlasot opciju **Skatīt bagātinātos datus**.</span><span class="sxs-lookup"><span data-stu-id="871d3-130">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

<span data-ttu-id="871d3-131">Papildinformāciju skatiet tēmā [Leadspace API](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span><span class="sxs-lookup"><span data-stu-id="871d3-131">For more information, see [Leadspace APIs](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span></span>

## <a name="next-steps"></a><span data-ttu-id="871d3-132">Nākamās darbības</span><span class="sxs-lookup"><span data-stu-id="871d3-132">Next steps</span></span>

<span data-ttu-id="871d3-133">Būvējiet virs saviem bagātinātajiem klientu datiem.</span><span class="sxs-lookup"><span data-stu-id="871d3-133">Build on top of your enriched customer data.</span></span> <span data-ttu-id="871d3-134">Veidojiet [segmentus](segments.md), [mērus](measures.md)un pat [eksportējiet datus](export-destinations.md), lai klientiem sniegtu personalizētas iespējas.</span><span class="sxs-lookup"><span data-stu-id="871d3-134">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="871d3-135">Datu konfidencialitāte un atbilstība</span><span class="sxs-lookup"><span data-stu-id="871d3-135">Data privacy and compliance</span></span>

<span data-ttu-id="871d3-136">Ja iespējojat Dynamics 365 Customer Insights datu pārsūtīšanu uz Leadspace, jūs atļaujat datu pārsūtīšanu ārpus atbilstības robežām Dynamics 365 Customer Insights, ieskaitot iespējami sensitīvus datus, piemēram, personas datus.</span><span class="sxs-lookup"><span data-stu-id="871d3-136">When you enable Dynamics 365 Customer Insights to transmit data to Leadspace, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="871d3-137">Microsoft šos datus pārsūtīs pēc jūsu norādēm, bet jūs esat atbildīgs par to, lai nodrošinātu Leadspace atbilstību konfidencialitātes vai drošības saistībām, kas jums varētu rasties.</span><span class="sxs-lookup"><span data-stu-id="871d3-137">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Leadspace meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="871d3-138">Papildinformāciju skatiet rakstā [Microsoft Privātuma paziņojums](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="871d3-138">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="871d3-139">Jūsu Dynamics 365 Customer Insights administrators var noņemt šo bagātināšanas funkciju jebkurā laikā, lai pārtrauktu izmantot šo funkcionalitāti.</span><span class="sxs-lookup"><span data-stu-id="871d3-139">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>