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
ms.openlocfilehash: ccf4f661ecffb281556a4545b1f26ee809c697cd
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 04/14/2021
ms.locfileid: "5895922"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a><span data-ttu-id="bb012-103">Uzņēmuma profilu bagātināšana ar Leadspace (priekšskatījums)</span><span class="sxs-lookup"><span data-stu-id="bb012-103">Enrichment of company profiles with Leadspace (preview)</span></span>

<span data-ttu-id="bb012-104">Leadspace ir datu zinātnes uzņēmums, kas nodrošina B2B klientu datu platformu.</span><span class="sxs-lookup"><span data-stu-id="bb012-104">Leadspace is a data science company that provides a B2B Customer Data Platform.</span></span> <span data-ttu-id="bb012-105">Tā nodrošina klientiem vienotus klientu profilus, lai uzņēmumi bagātinātu datus.</span><span class="sxs-lookup"><span data-stu-id="bb012-105">It enables customers with unified customer profiles for companies to enrich their data.</span></span> <span data-ttu-id="bb012-106">Bagātinātie dati ietver vairākus atribūtus, piemēram, uzņēmuma izmēru, atrašanās vietu, nozari u.c.</span><span class="sxs-lookup"><span data-stu-id="bb012-106">Enrichments include more attributes such as company size, location, industry, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="bb012-107">Priekšnosacījumi</span><span class="sxs-lookup"><span data-stu-id="bb012-107">Prerequisites</span></span>

<span data-ttu-id="bb012-108">Lai konfigurētu Leadspace, ir jāizpilda tālāk aprakstītie priekšnosacījumi:</span><span class="sxs-lookup"><span data-stu-id="bb012-108">To configure Leadspace, the following prerequisites must be met:</span></span>

- <span data-ttu-id="bb012-109">Jums ir aktīva Leadspace licence.</span><span class="sxs-lookup"><span data-stu-id="bb012-109">You have an active Leadspace license.</span></span>
- <span data-ttu-id="bb012-110">Jums ir [vienoti klientu profili](customer-profiles.md) uzņēmumiem.</span><span class="sxs-lookup"><span data-stu-id="bb012-110">You have [unified customer profiles](customer-profiles.md) for companies.</span></span>
- <span data-ttu-id="bb012-111">Administrators jau ir konfigurējis Leadspace savienojumu vai jums ir [administratora](permissions.md#administrator) atļaujas un “pastāvīgā atslēga” (jeb **Leadspace marķieris**).</span><span class="sxs-lookup"><span data-stu-id="bb012-111">A Leadspace connection has already been configured by an administrator or you have [administrator](permissions.md#administrator) permissions and the “perpetual key” (referred to as **Leadspace token**).</span></span> <span data-ttu-id="bb012-112">Tieši sazinieties ar [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/), lai iegūtu informāciju par produktu.</span><span class="sxs-lookup"><span data-stu-id="bb012-112">Contact [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) directly for details about their product.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="bb012-113">Bagātināto datu konfigurēšana</span><span class="sxs-lookup"><span data-stu-id="bb012-113">Configure the enrichment</span></span>

1. <span data-ttu-id="bb012-114">Sadaļā Auditorijas ieskati skatiet **Dati** > **Darbības**.</span><span class="sxs-lookup"><span data-stu-id="bb012-114">In audience insights, go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="bb012-115">Leadspace rūtī atlasiet **Bagātināt datus** un atlasiet **Sākt darbu**.</span><span class="sxs-lookup"><span data-stu-id="bb012-115">Select **Enrich my data** on the Leadspace tile and select **Get started**.</span></span>

   :::image type="content" source="media/leadspace-tile.png" alt-text="Leadspace mozaīkas ekrānuzņēmums.":::

1. <span data-ttu-id="bb012-117">Nolaižamajā izvēlnē atlasiet [savienojums](connections.md).</span><span class="sxs-lookup"><span data-stu-id="bb012-117">Select a [connection](connections.md) from the drop-down.</span></span> <span data-ttu-id="bb012-118">Ja nav pieejamu savienojumu, sazinieties ar administratoru.</span><span class="sxs-lookup"><span data-stu-id="bb012-118">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="bb012-119">Ja esat administrators, jūs varat izveidot savienojumu, atlasot **Pievienot savienojumu** un izvēloties **Leadspace**.</span><span class="sxs-lookup"><span data-stu-id="bb012-119">If you are an administrator, you can create a connection by selecting **Add connection** and choosing **Leadspace**.</span></span> 

1. <span data-ttu-id="bb012-120">Lai apstiprinātu savienojumu, atlasiet **Pieslēgties Leadspace**.</span><span class="sxs-lookup"><span data-stu-id="bb012-120">Select **Connect to Leadspace** to confirm the connection.</span></span>

1. <span data-ttu-id="bb012-121">Atlasiet **Tālāk** un izvēlieties **Klientu datu kopu**, kuru vēlaties bagātināt ar uzņēmuma datiem no Leadspace.</span><span class="sxs-lookup"><span data-stu-id="bb012-121">Select **Next** and choose the **Customer data set** you want to enrich with company data from Leadspace.</span></span> <span data-ttu-id="bb012-122">Varat atlasīt entītiju **Klients**, lai bagātinātu visus klientu profilus, vai atlasīt segmenta entītiju, lai bagātinātu tikai šajā segmentā iekļautos klientu profilus.</span><span class="sxs-lookup"><span data-stu-id="bb012-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="Ekrānuzņēmums, izvēloties klientu datu kopu.":::

1. <span data-ttu-id="bb012-124">Atlasiet **Tālāk** un definējiet kuri lauki no jūsu vienotajiem profiliem tiek izmantoti, lai meklētu atbilstošus uzņēmuma datus no Leadspace.</span><span class="sxs-lookup"><span data-stu-id="bb012-124">Select **Next** and define which fields from your unified profiles are used to look for matching company data from Leadspace.</span></span> <span data-ttu-id="bb012-125">Lauks **Uzņēmuma nosaukums** ir obligāts.</span><span class="sxs-lookup"><span data-stu-id="bb012-125">The **Name of company** field is required.</span></span> <span data-ttu-id="bb012-126">Lielākai atbilstībai varat pievienot līdz diviem citiem laukiem - **Uzņēmuma tīmekļa vietne** un **Uzņēmuma atrašanās vieta**.</span><span class="sxs-lookup"><span data-stu-id="bb012-126">For a higher match accuracy, up to two other fields, **Company website** and **Company location**, can be added.</span></span>

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Leadspace lauku kartējuma rūts.":::

1. <span data-ttu-id="bb012-128">Lai pabeigtu lauka kartēšanu, atlasiet **Tālāk**.</span><span class="sxs-lookup"><span data-stu-id="bb012-128">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="bb012-129">Norādiet bagātināto datu nosaukumu un pēc izvēles pārskatīšanas atlasiet **Saglabāt bagātinātos datus**.</span><span class="sxs-lookup"><span data-stu-id="bb012-129">Provide a name for the enrichment and select **Save enrichment** after reviewing your choices.</span></span>


## <a name="configure-the-connection-for-leadspace"></a><span data-ttu-id="bb012-130">Leadspace savienojuma konfigurēšana</span><span class="sxs-lookup"><span data-stu-id="bb012-130">Configure the connection for Leadspace</span></span> 

<span data-ttu-id="bb012-131">Lai konfigurētu savienojumus, jums ir jābūt administratoram.</span><span class="sxs-lookup"><span data-stu-id="bb012-131">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="bb012-132">Konfigurējot bagātinātos datus, atlasiet **Pievienot savienojumu** *vai* dodieties uz **Administrators** > **Savienojumi** un Leadspace rūtī atlasiet **Iestatīt**.</span><span class="sxs-lookup"><span data-stu-id="bb012-132">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Leadspace tile.</span></span>

1. <span data-ttu-id="bb012-133">Atlasiet **Sākt darbu**</span><span class="sxs-lookup"><span data-stu-id="bb012-133">Select **Get Started**</span></span> 

1. <span data-ttu-id="bb012-134">Lodziņā **Parādāmais nosaukums** ievadiet savienojuma nosaukumu.</span><span class="sxs-lookup"><span data-stu-id="bb012-134">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="bb012-135">Iesniedziet derīgu Leadspace marķieri.</span><span class="sxs-lookup"><span data-stu-id="bb012-135">Provide a valid Leadspace token.</span></span>

1. <span data-ttu-id="bb012-136">Pārskatiet un sniedziet savu piekrišanu **Datu konfidencialitātei un atbilstībai**, atzīmējot izvēles rūtiņu **Piekrītu**</span><span class="sxs-lookup"><span data-stu-id="bb012-136">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox</span></span>

1. <span data-ttu-id="bb012-137">Lai pārbaudītu konfigurāciju, atlasiet **Pārbaudīt**.</span><span class="sxs-lookup"><span data-stu-id="bb012-137">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="bb012-138">Pēc pārbaudes pabeigšanas atlasiet **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="bb012-138">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Leadspace savienojuma konfigurēšanas lapa.":::

## <a name="enrichment-results"></a><span data-ttu-id="bb012-140">Bagātināšanas rezultāti</span><span class="sxs-lookup"><span data-stu-id="bb012-140">Enrichment results</span></span>

<span data-ttu-id="bb012-141">Pēc bagātināšanas atsvaidzināšanas varat apskatīt nesen papildinātā uzņēmuma datus [Mani papildinājumi](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="bb012-141">After refreshing the enrichment, you can review the newly enriched company data under [My enrichments](enrichment-hub.md).</span></span> <span data-ttu-id="bb012-142">Varat atrast pēdējās atjaunināšanas laiku un bagātināto profilu skaitu.</span><span class="sxs-lookup"><span data-stu-id="bb012-142">You can find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="bb012-143">Jūs varat piekļūt detalizētam katra bagātināta profila skatam, atlasot opciju **Skatīt bagātinātos datus**.</span><span class="sxs-lookup"><span data-stu-id="bb012-143">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

<span data-ttu-id="bb012-144">Papildinformāciju skatiet tēmā [Leadspace API](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span><span class="sxs-lookup"><span data-stu-id="bb012-144">For more information, see [Leadspace APIs](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span></span>

## <a name="next-steps"></a><span data-ttu-id="bb012-145">Nākamās darbības</span><span class="sxs-lookup"><span data-stu-id="bb012-145">Next steps</span></span>

<span data-ttu-id="bb012-146">Būvējiet virs saviem bagātinātajiem klientu datiem.</span><span class="sxs-lookup"><span data-stu-id="bb012-146">Build on top of your enriched customer data.</span></span> <span data-ttu-id="bb012-147">Veidojiet [segmentus](segments.md), [mērus](measures.md)un pat [eksportējiet datus](export-destinations.md), lai klientiem sniegtu personalizētas iespējas.</span><span class="sxs-lookup"><span data-stu-id="bb012-147">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="bb012-148">Datu konfidencialitāte un atbilstība</span><span class="sxs-lookup"><span data-stu-id="bb012-148">Data privacy and compliance</span></span>

<span data-ttu-id="bb012-149">Ja iespējojat Dynamics 365 Customer Insights datu pārsūtīšanu uz Leadspace, jūs atļaujat datu pārsūtīšanu ārpus atbilstības robežām Dynamics 365 Customer Insights, ieskaitot iespējami sensitīvus datus, piemēram, personas datus.</span><span class="sxs-lookup"><span data-stu-id="bb012-149">When you enable Dynamics 365 Customer Insights to transmit data to Leadspace, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="bb012-150">Microsoft šos datus pārsūtīs pēc jūsu norādēm, bet jūs esat atbildīgs par to, lai nodrošinātu Leadspace atbilstību konfidencialitātes vai drošības saistībām, kas jums varētu rasties.</span><span class="sxs-lookup"><span data-stu-id="bb012-150">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Leadspace meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="bb012-151">Papildinformāciju skatiet rakstā [Microsoft Privātuma paziņojums](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="bb012-151">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="bb012-152">Jūsu Dynamics 365 Customer Insights administrators var noņemt šo bagātināšanas funkciju jebkurā laikā, lai pārtrauktu izmantot šo funkcionalitāti.</span><span class="sxs-lookup"><span data-stu-id="bb012-152">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
