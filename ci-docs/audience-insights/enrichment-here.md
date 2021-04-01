---
title: Bagātināšana ar trešās puses bagātināšanas programmu HERE Technologies
description: Vispārēja informācija par HERE Technologies trešās puses bagātināšanu.
ms.date: 12/10/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 8e8d6bfea4e0df54682501f60759c24c893444af
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597750"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a><span data-ttu-id="b103c-103">Klientu profilu bagātināšana ar HERE Technologies (priekšskatījums)</span><span class="sxs-lookup"><span data-stu-id="b103c-103">Enrichment of customer profiles with HERE Technologies (preview)</span></span>

<span data-ttu-id="b103c-104">HERE Technologies ir atrašanās vietas platformas uzņēmums, kas nodrošina atrašanās vietas datus un pakalpojumus.</span><span class="sxs-lookup"><span data-stu-id="b103c-104">HERE Technologies is a location platform company that provides location-centric data and services.</span></span> <span data-ttu-id="b103c-105">Izmantojot HERE Technologies datu bagātināšanas pakalpojumus, varat izveidot precīzāku atrašanās vietu, lai izprastu klientus, izmantojot adrešu normalizēšanu, platuma un garuma izgūšanu utt.</span><span class="sxs-lookup"><span data-stu-id="b103c-105">With HERE Technologies' data enrichment services, you can build a more precise location understanding of your customers with address normalization, latitude and longitude extraction, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b103c-106">Priekšnosacījumi</span><span class="sxs-lookup"><span data-stu-id="b103c-106">Prerequisites</span></span>

<span data-ttu-id="b103c-107">Lai konfigurētu HERE Technologies, ir jāatbilst šādiem priekšnosacījumiem:</span><span class="sxs-lookup"><span data-stu-id="b103c-107">To configure HERE Technologies enrichments, the following prerequisites must be met:</span></span>

- <span data-ttu-id="b103c-108">Jums ir jābūt aktīvam HERE Technologies abonementam.</span><span class="sxs-lookup"><span data-stu-id="b103c-108">You have an active HERE Technologies subscription.</span></span> <span data-ttu-id="b103c-109">Lai saņemtu abonementu, varat [pierakstīties šeit](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) vai [sazinieties ar HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) tieši.</span><span class="sxs-lookup"><span data-stu-id="b103c-109">To get a subscription, you can [sign-up here](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) or [contact HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) directly.</span></span> [<span data-ttu-id="b103c-110">Papildinformācija par HERE Technologies atrašanās vietas bagātināšanu.</span><span class="sxs-lookup"><span data-stu-id="b103c-110">Learn more about HERE Technologies Location Enrichment.</span></span>](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- <span data-ttu-id="b103c-111">Jums ir HERE Technologies API atslēga.</span><span class="sxs-lookup"><span data-stu-id="b103c-111">You have the HERE Technologies API key.</span></span>

- <span data-ttu-id="b103c-112">ir nepieciešamas [Administratora](permissions.md#administrator) atļaujas.</span><span class="sxs-lookup"><span data-stu-id="b103c-112">You have [Administrator](permissions.md#administrator) permissions.</span></span>

## <a name="configuration"></a><span data-ttu-id="b103c-113">Konfigurācija</span><span class="sxs-lookup"><span data-stu-id="b103c-113">Configuration</span></span>

1. <span data-ttu-id="b103c-114">Dodieties uz **Dati** > **Bagātināšana**.</span><span class="sxs-lookup"><span data-stu-id="b103c-114">Go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="b103c-115">Atlasiet HERE Technologies elementu **Bagātināt manus datus**.</span><span class="sxs-lookup"><span data-stu-id="b103c-115">Select **Enrich my data** on the HERE Technologies tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b103c-116">![HERE Technologies elements](media/HERE-tile.png "HERE Technologies elements")</span><span class="sxs-lookup"><span data-stu-id="b103c-116">![HERE Technologies tile](media/HERE-tile.png "HERE Technologies tile")</span></span>

1. <span data-ttu-id="b103c-117">Ievadiet aktīvu **HERE Technologies API atslēgu**.</span><span class="sxs-lookup"><span data-stu-id="b103c-117">Enter an active **HERE Technologies API key**.</span></span> <span data-ttu-id="b103c-118">Pārskatiet un sniedziet savu piekrišanu **Datu konfidencialitātei un atbilstībai**, atzīmējot izvēles rūtiņu **Piekrītu**.</span><span class="sxs-lookup"><span data-stu-id="b103c-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> 

1. <span data-ttu-id="b103c-119">Apstipriniet abas ievades, atlasot **Izveidot savienojumu ar HERE**.</span><span class="sxs-lookup"><span data-stu-id="b103c-119">Confirm both inputs by selecting **Connect to HERE**.</span></span>

1.  <span data-ttu-id="b103c-120">Atlasiet **Pievienot datus** un izvēlieties **Klienta datu kopu**, ko vēlaties bagātināt ar atrašanās vietas datiem no programmas HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="b103c-120">Select **Add data** and choose the **Customer data set** you want to enrich with location data from HERE Technologies.</span></span> <span data-ttu-id="b103c-121">Varat atlasīt entītiju **Klients**, lai bagātinātu visus klientu profilus, vai atlasīt segmenta entītiju, lai bagātinātu tikai šajā segmentā iekļautos klientu profilus.</span><span class="sxs-lookup"><span data-stu-id="b103c-121">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="Ekrānuzņēmums, izvēloties klientu datu kopu.":::

1. <span data-ttu-id="b103c-123">Izvēlieties, vai jākartē lauki primārajai un/vai sekundārajai adresei.</span><span class="sxs-lookup"><span data-stu-id="b103c-123">Choose if you want to map fields to the primary and/or secondary address.</span></span> <span data-ttu-id="b103c-124">Varat norādīt lauka kartējumu abām adresēm (piemēram, mājas un darba adrese), kā arī bagātināt abu adrešu profilus atsevišķi.</span><span class="sxs-lookup"><span data-stu-id="b103c-124">You can specify a field mapping for both addresses (for example, a home and a business address) and enrich the profiles for both addresses separately.</span></span> <span data-ttu-id="b103c-125">Atlasiet **Tālāk**.</span><span class="sxs-lookup"><span data-stu-id="b103c-125">Select **Next**.</span></span>

1. <span data-ttu-id="b103c-126">Definējiet, kurus vienoto profilu laukus vajadzētu izmantot, lai meklētu atbilstošos HERE Technologies atrašanās vietas datus.</span><span class="sxs-lookup"><span data-stu-id="b103c-126">Define which fields from your unified profiles should be used to look for matching location data from HERE Technologies.</span></span> <span data-ttu-id="b103c-127">Atlasītajai primārajai un/vai sekundārajai adresei ir nepieciešami lauki **1.adrese** un **Pasta indekss**.</span><span class="sxs-lookup"><span data-stu-id="b103c-127">The **Street 1** and **Zip/Postal Code** fields are required for the selected primary and/or secondary address.</span></span> <span data-ttu-id="b103c-128">Lai iegūtu augstāku atbilstību precizitāti, var pievienot vairākus laukus.</span><span class="sxs-lookup"><span data-stu-id="b103c-128">For a higher match accuracy, more fields can be added.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b103c-129">![HERE Technologies bagātināšanas konfigurācijas lapa](media/enrichment-HERE-configuration.png "HERE Technologies bagātināšanas konfigurācijas lapa")</span><span class="sxs-lookup"><span data-stu-id="b103c-129">![HERE Technologies enrichment configuration page](media/enrichment-HERE-configuration.png "HERE Technologies enrichment configuration page")</span></span>

1. <span data-ttu-id="b103c-130">Atlasiet **Piemērot**, lai pabeigtu lauka kartēšanu.</span><span class="sxs-lookup"><span data-stu-id="b103c-130">Select **Apply** to complete the field mapping.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="b103c-131">Bagātināšanas rezultāti</span><span class="sxs-lookup"><span data-stu-id="b103c-131">Enrichment results</span></span>

<span data-ttu-id="b103c-132">Lai sāktu bagātināšanas procesu, komandjoslā atlasiet **Palaist**.</span><span class="sxs-lookup"><span data-stu-id="b103c-132">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="b103c-133">Varat arī ļaut sistēmai palaist bagātināšanu automātiski kā daļu no [plānotās atsvaidzināšanas](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="b103c-133">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="b103c-134">Apstrādes laiks ir atkarīgs no jūsu klientu datu izmēra un API atbildes laikiem no HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="b103c-134">The processing time will depend on the size of your customer data and the API response times from HERE Technologies.</span></span>

<span data-ttu-id="b103c-135">Pēc bagātināšanas procesa noslēgšanas varat pārskatīt tikko bagātinātos klientu profilu datus, dodoties uz sadaļu **Mana bagātināšana**.</span><span class="sxs-lookup"><span data-stu-id="b103c-135">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="b103c-136">Turklāt jūs redzēsit pēdējā atjauninājuma laiku un bagātināto profilu skaitu.</span><span class="sxs-lookup"><span data-stu-id="b103c-136">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="b103c-137">Jūs varat piekļūt detalizētam katra bagātināta profila skatam, atlasot opciju **Skatīt bagātinātos datus**.</span><span class="sxs-lookup"><span data-stu-id="b103c-137">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="b103c-138">Nākamās darbības</span><span class="sxs-lookup"><span data-stu-id="b103c-138">Next steps</span></span>

<span data-ttu-id="b103c-139">Būvējiet virs saviem bagātinātajiem klientu datiem.</span><span class="sxs-lookup"><span data-stu-id="b103c-139">Build on top of your enriched customer data.</span></span> <span data-ttu-id="b103c-140">Veidojiet [segmentus](segments.md), [mērus](measures.md)un pat [eksportējiet datus](export-destinations.md), lai klientiem sniegtu personalizētas iespējas.</span><span class="sxs-lookup"><span data-stu-id="b103c-140">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="b103c-141">Datu konfidencialitāte un atbilstība</span><span class="sxs-lookup"><span data-stu-id="b103c-141">Data privacy and compliance</span></span>

<span data-ttu-id="b103c-142">Ja iespējojat Dynamics 365 Customer Insights datu pārsūtīšanu uz HERE Technologies, jūs atļaujat datu pārsūtīšanu ārpus atbilstības robežām Dynamics 365 Customer Insights, ieskaitot iespējami sensitīvus datus, piemēram, personas datus.</span><span class="sxs-lookup"><span data-stu-id="b103c-142">When you enable Dynamics 365 Customer Insights to transmit data to HERE Technologies, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="b103c-143">Microsoft šos datus pārsūtīs pēc jūsu norādēm, bet jūs esat atbildīgs par to, lai nodrošinātu HERE Technologies atbilstību konfidencialitātes vai drošības saistībām, kas jums varētu rasties.</span><span class="sxs-lookup"><span data-stu-id="b103c-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that HERE Technologies meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="b103c-144">Papildinformāciju skatiet rakstā [Microsoft Privātuma paziņojums](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="b103c-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="b103c-145">Jūsu Dynamics 365 Customer Insights administrators var noņemt šo bagātināšanas funkciju jebkurā laikā, lai pārtrauktu izmantot šo funkcionalitāti.</span><span class="sxs-lookup"><span data-stu-id="b103c-145">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]