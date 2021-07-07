---
title: Uzņēmumu profilu bagātināšana ar trešās puses bagātināšanas programmu Leadspace
description: Vispārēja informācija par Leadspace trešās puses bagātināšanu.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 0496d10c994cd077a778a6e745e3774e316765ae
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305211"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a><span data-ttu-id="19c8f-103">Uzņēmuma profilu bagātināšana ar Leadspace (priekšskatījums)</span><span class="sxs-lookup"><span data-stu-id="19c8f-103">Enrichment of company profiles with Leadspace (preview)</span></span>

<span data-ttu-id="19c8f-104">Leadspace ir datu zinātnes uzņēmums, kas nodrošina B2B klientu datu platformu.</span><span class="sxs-lookup"><span data-stu-id="19c8f-104">Leadspace is a data science company that provides a B2B Customer Data Platform.</span></span> <span data-ttu-id="19c8f-105">Tā nodrošina klientiem vienotus klientu profilus, lai uzņēmumi bagātinātu datus.</span><span class="sxs-lookup"><span data-stu-id="19c8f-105">It enables customers with unified customer profiles for companies to enrich their data.</span></span> <span data-ttu-id="19c8f-106">Bagātinātie dati ietver vairākus atribūtus, piemēram, uzņēmuma izmēru, atrašanās vietu, nozari u.c.</span><span class="sxs-lookup"><span data-stu-id="19c8f-106">Enrichments include more attributes such as company size, location, industry, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="19c8f-107">Priekšnosacījumi</span><span class="sxs-lookup"><span data-stu-id="19c8f-107">Prerequisites</span></span>

<span data-ttu-id="19c8f-108">Lai konfigurētu Leadspace, ir jāizpilda tālāk aprakstītie priekšnosacījumi:</span><span class="sxs-lookup"><span data-stu-id="19c8f-108">To configure Leadspace, the following prerequisites must be met:</span></span>

- <span data-ttu-id="19c8f-109">Jums ir aktīva Leadspace licence.</span><span class="sxs-lookup"><span data-stu-id="19c8f-109">You have an active Leadspace license.</span></span>
- <span data-ttu-id="19c8f-110">Jums ir [vienoti klientu profili](customer-profiles.md) uzņēmumiem.</span><span class="sxs-lookup"><span data-stu-id="19c8f-110">You have [unified customer profiles](customer-profiles.md) for companies.</span></span>
- <span data-ttu-id="19c8f-111">Administrators jau ir konfigurējis Leadspace savienojumu vai jums ir [administratora](permissions.md#administrator) atļaujas un “pastāvīgā atslēga” (jeb **Leadspace marķieris**).</span><span class="sxs-lookup"><span data-stu-id="19c8f-111">A Leadspace connection has already been configured by an administrator or you have [administrator](permissions.md#administrator) permissions and the “perpetual key” (referred to as **Leadspace token**).</span></span> <span data-ttu-id="19c8f-112">Tieši sazinieties ar [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/), lai iegūtu informāciju par produktu.</span><span class="sxs-lookup"><span data-stu-id="19c8f-112">Contact [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) directly for details about their product.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="19c8f-113">Bagātināto datu konfigurēšana</span><span class="sxs-lookup"><span data-stu-id="19c8f-113">Configure the enrichment</span></span>

1. <span data-ttu-id="19c8f-114">Sadaļā Auditorijas ieskati skatiet **Dati** > **Darbības**.</span><span class="sxs-lookup"><span data-stu-id="19c8f-114">In audience insights, go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="19c8f-115">Leadspace rūtī atlasiet **Bagātināt datus** un atlasiet **Sākt darbu**.</span><span class="sxs-lookup"><span data-stu-id="19c8f-115">Select **Enrich my data** on the Leadspace tile and select **Get started**.</span></span>

   :::image type="content" source="media/leadspace-tile.png" alt-text="Leadspace mozaīkas ekrānuzņēmums.":::

1. <span data-ttu-id="19c8f-117">Atlasiet [savienojumu](connections.md) nolaižamajā sarakstā.</span><span class="sxs-lookup"><span data-stu-id="19c8f-117">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="19c8f-118">Ja nav pieejamu savienojumu, sazinieties ar administratoru.</span><span class="sxs-lookup"><span data-stu-id="19c8f-118">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="19c8f-119">Ja esat administrators, jūs varat izveidot savienojumu, atlasot **Pievienot savienojumu** un izvēloties **Leadspace**.</span><span class="sxs-lookup"><span data-stu-id="19c8f-119">If you are an administrator, you can create a connection by selecting **Add connection** and choosing **Leadspace**.</span></span> 

1. <span data-ttu-id="19c8f-120">Lai apstiprinātu savienojumu, atlasiet **Pieslēgties Leadspace**.</span><span class="sxs-lookup"><span data-stu-id="19c8f-120">Select **Connect to Leadspace** to confirm the connection.</span></span>

1. <span data-ttu-id="19c8f-121">Atlasiet **Tālāk** un izvēlieties **Klientu datu kopu**, kuru vēlaties bagātināt ar uzņēmuma datiem no Leadspace.</span><span class="sxs-lookup"><span data-stu-id="19c8f-121">Select **Next** and choose the **Customer data set** you want to enrich with company data from Leadspace.</span></span> <span data-ttu-id="19c8f-122">Varat atlasīt entītiju **Klients**, lai bagātinātu visus klientu profilus, vai atlasīt segmenta entītiju, lai bagātinātu tikai šajā segmentā iekļautos klientu profilus.</span><span class="sxs-lookup"><span data-stu-id="19c8f-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="Ekrānuzņēmums, izvēloties klientu datu kopu.":::

1. <span data-ttu-id="19c8f-124">Atlasiet **Tālāk** un definējiet kuri lauki no jūsu vienotajiem profiliem tiek izmantoti, lai meklētu atbilstošus uzņēmuma datus no Leadspace.</span><span class="sxs-lookup"><span data-stu-id="19c8f-124">Select **Next** and define which fields from your unified profiles are used to look for matching company data from Leadspace.</span></span> <span data-ttu-id="19c8f-125">Lauks **Uzņēmuma nosaukums** ir obligāts.</span><span class="sxs-lookup"><span data-stu-id="19c8f-125">The **Name of company** field is required.</span></span> <span data-ttu-id="19c8f-126">Lielākai atbilstībai varat pievienot līdz diviem citiem laukiem - **Uzņēmuma tīmekļa vietne** un **Uzņēmuma atrašanās vieta**.</span><span class="sxs-lookup"><span data-stu-id="19c8f-126">For a higher match accuracy, up to two other fields, **Company website** and **Company location**, can be added.</span></span>

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Leadspace lauku kartējuma rūts.":::

1. <span data-ttu-id="19c8f-128">Lai pabeigtu lauka kartēšanu, atlasiet **Tālāk**.</span><span class="sxs-lookup"><span data-stu-id="19c8f-128">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="19c8f-129">Norādiet bagātināto datu nosaukumu un pēc izvēles pārskatīšanas atlasiet **Saglabāt bagātinātos datus**.</span><span class="sxs-lookup"><span data-stu-id="19c8f-129">Provide a name for the enrichment and select **Save enrichment** after reviewing your choices.</span></span>


## <a name="configure-the-connection-for-leadspace"></a><span data-ttu-id="19c8f-130">Leadspace savienojuma konfigurēšana</span><span class="sxs-lookup"><span data-stu-id="19c8f-130">Configure the connection for Leadspace</span></span> 

<span data-ttu-id="19c8f-131">Lai konfigurētu savienojumus, jums ir jābūt administratoram.</span><span class="sxs-lookup"><span data-stu-id="19c8f-131">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="19c8f-132">Konfigurējot bagātinātos datus, atlasiet **Pievienot savienojumu** *vai* dodieties uz **Administrators** > **Savienojumi** un Leadspace rūtī atlasiet **Iestatīt**.</span><span class="sxs-lookup"><span data-stu-id="19c8f-132">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Leadspace tile.</span></span>

1. <span data-ttu-id="19c8f-133">Atlasiet **Sākt**.</span><span class="sxs-lookup"><span data-stu-id="19c8f-133">Select **Get Started**.</span></span> 

1. <span data-ttu-id="19c8f-134">Lodziņā **Parādāmais nosaukums** ievadiet savienojuma nosaukumu.</span><span class="sxs-lookup"><span data-stu-id="19c8f-134">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="19c8f-135">Iesniedziet derīgu Leadspace marķieri.</span><span class="sxs-lookup"><span data-stu-id="19c8f-135">Provide a valid Leadspace token.</span></span>

1. <span data-ttu-id="19c8f-136">Pārskatiet un sniedziet savu piekrišanu **Datu konfidencialitātei un atbilstībai**, atlasot **Es piekrītu**.</span><span class="sxs-lookup"><span data-stu-id="19c8f-136">Review and provide your consent for **Data privacy and compliance** by selecting **I agree**.</span></span>

1. <span data-ttu-id="19c8f-137">Lai pārbaudītu konfigurāciju, atlasiet **Pārbaudīt**.</span><span class="sxs-lookup"><span data-stu-id="19c8f-137">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="19c8f-138">Pēc pārbaudes pabeigšanas atlasiet **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="19c8f-138">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Leadspace savienojuma konfigurēšanas lapa.":::

## <a name="enrichment-results"></a><span data-ttu-id="19c8f-140">Bagātināšanas rezultāti</span><span class="sxs-lookup"><span data-stu-id="19c8f-140">Enrichment results</span></span>

<span data-ttu-id="19c8f-141">Pēc bagātināšanas atsvaidzināšanas varat apskatīt nesen papildinātā uzņēmuma datus [Mani papildinājumi](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="19c8f-141">After refreshing the enrichment, you can review the newly enriched company data under [My enrichments](enrichment-hub.md).</span></span> <span data-ttu-id="19c8f-142">Varat atrast pēdējās atjaunināšanas laiku un bagātināto profilu skaitu.</span><span class="sxs-lookup"><span data-stu-id="19c8f-142">You can find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="19c8f-143">Jūs varat piekļūt detalizētam katra bagātināta profila skatam, atlasot opciju **Skatīt bagātinātos datus**.</span><span class="sxs-lookup"><span data-stu-id="19c8f-143">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

<span data-ttu-id="19c8f-144">Papildinformāciju skatiet tēmā [Leadspace API](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span><span class="sxs-lookup"><span data-stu-id="19c8f-144">For more information, see [Leadspace APIs](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span></span>

## <a name="next-steps"></a><span data-ttu-id="19c8f-145">Nākamās darbības</span><span class="sxs-lookup"><span data-stu-id="19c8f-145">Next steps</span></span>

<span data-ttu-id="19c8f-146">Pilnveidojiet savus bagātinātos klientu datus.</span><span class="sxs-lookup"><span data-stu-id="19c8f-146">Build on top of your enriched customer data.</span></span> <span data-ttu-id="19c8f-147">Veidojiet [segmentus](segments.md) un [pasākumus](measures.md) un pat [eksportējiet datus](export-destinations.md), lai nodrošinātu klientiem personalizētu pieredzi.</span><span class="sxs-lookup"><span data-stu-id="19c8f-147">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="19c8f-148">Datu konfidencialitāte un atbilstība</span><span class="sxs-lookup"><span data-stu-id="19c8f-148">Data privacy and compliance</span></span>

<span data-ttu-id="19c8f-149">Ja iespējojat Dynamics 365 Customer Insights datu pārsūtīšanu uz Leadspace, jūs atļaujat datu pārsūtīšanu ārpus atbilstības robežām Dynamics 365 Customer Insights, ieskaitot iespējami sensitīvus datus, piemēram, personas datus.</span><span class="sxs-lookup"><span data-stu-id="19c8f-149">When you enable Dynamics 365 Customer Insights to transmit data to Leadspace, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="19c8f-150">Microsoft šos datus pārsūtīs pēc jūsu norādēm, bet jūs esat atbildīgs par to, lai nodrošinātu Leadspace atbilstību konfidencialitātes vai drošības saistībām, kas jums varētu rasties.</span><span class="sxs-lookup"><span data-stu-id="19c8f-150">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Leadspace meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="19c8f-151">Papildinformāciju skatiet rakstā [Microsoft Privātuma paziņojums](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="19c8f-151">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="19c8f-152">Jūsu Dynamics 365 Customer Insights administrators var noņemt šo bagātināšanas funkciju jebkurā laikā, lai pārtrauktu šīs funkcijas izmantošanu.</span><span class="sxs-lookup"><span data-stu-id="19c8f-152">Your Dynamics 365 Customer Insights administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
