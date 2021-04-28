---
title: Bagātināšana ar trešās puses bagātināšanas programmu HERE Technologies
description: Vispārēja informācija par HERE Technologies trešās puses bagātināšanu.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 5d1f037377010153045c9255d2d01f98ebf1fdfd
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896060"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a><span data-ttu-id="f55d1-103">Klientu profilu bagātināšana ar HERE Technologies (priekšskatījums)</span><span class="sxs-lookup"><span data-stu-id="f55d1-103">Enrichment of customer profiles with HERE Technologies (preview)</span></span>

<span data-ttu-id="f55d1-104">HERE Technologies ir atrašanās vietas platformas uzņēmums, kas nodrošina atrašanās vietas datus un pakalpojumus.</span><span class="sxs-lookup"><span data-stu-id="f55d1-104">HERE Technologies is a location platform company that provides location-centric data and services.</span></span> <span data-ttu-id="f55d1-105">Izmantojot HERE Technologies datu bagātināšanas pakalpojumus, varat izveidot precīzāku atrašanās vietu, lai izprastu klientus, izmantojot adrešu normalizēšanu, platuma un garuma izgūšanu utt.</span><span class="sxs-lookup"><span data-stu-id="f55d1-105">With HERE Technologies' data enrichment services, you can build a more precise location understanding of your customers with address normalization, latitude and longitude extraction, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f55d1-106">Priekšnosacījumi</span><span class="sxs-lookup"><span data-stu-id="f55d1-106">Prerequisites</span></span>

<span data-ttu-id="f55d1-107">Lai konfigurētu HERE Technologies, ir jāatbilst šādiem priekšnosacījumiem:</span><span class="sxs-lookup"><span data-stu-id="f55d1-107">To configure HERE Technologies enrichments, the following prerequisites must be met:</span></span>

- <span data-ttu-id="f55d1-108">Jums ir jābūt aktīvam HERE Technologies abonementam.</span><span class="sxs-lookup"><span data-stu-id="f55d1-108">You have an active HERE Technologies subscription.</span></span> <span data-ttu-id="f55d1-109">Lai saņemtu abonementu, varat [pierakstīties šeit](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) vai [sazinieties ar HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) tieši.</span><span class="sxs-lookup"><span data-stu-id="f55d1-109">To get a subscription, you can [sign-up here](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) or [contact HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) directly.</span></span> [<span data-ttu-id="f55d1-110">Papildinformācija par HERE Technologies atrašanās vietas bagātināšanu.</span><span class="sxs-lookup"><span data-stu-id="f55d1-110">Learn more about HERE Technologies Location Enrichment.</span></span>](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- <span data-ttu-id="f55d1-111">Ir pieejams HERE [savienojums](connections.md) *vai* jums ir [administratora](permissions.md#administrator) atļaujas un HERE Technologies API atslēga.</span><span class="sxs-lookup"><span data-stu-id="f55d1-111">There is a HERE [connection](connections.md) available *or* you have [administrator](permissions.md#administrator) permissions and the HERE Technologies API key.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="f55d1-112">Bagātināto datu konfigurēšana</span><span class="sxs-lookup"><span data-stu-id="f55d1-112">Configure the enrichment</span></span>

1. <span data-ttu-id="f55d1-113">Dodieties uz **Dati** > **Bagātināšana**.</span><span class="sxs-lookup"><span data-stu-id="f55d1-113">Go to **Data** > **Enrichment**.</span></span> 

1. <span data-ttu-id="f55d1-114">HERE Technologies rūtī atlasiet **Bagātināt datus** un atlasiet **Sākt darbu**.</span><span class="sxs-lookup"><span data-stu-id="f55d1-114">Select **Enrich my data** on the HERE Technologies tile and select **Get started**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f55d1-115">![HERE Technologies elements](media/HERE-tile.png "HERE Technologies elements")</span><span class="sxs-lookup"><span data-stu-id="f55d1-115">![HERE Technologies tile](media/HERE-tile.png "HERE Technologies tile")</span></span>

1. <span data-ttu-id="f55d1-116">Nolaižamajā izvēlnē atlasiet [savienojums](connections.md).</span><span class="sxs-lookup"><span data-stu-id="f55d1-116">Select a [connection](connections.md) from the drop-down.</span></span> <span data-ttu-id="f55d1-117">Ja nav pieejamu savienojumu, sazinieties ar administratoru.</span><span class="sxs-lookup"><span data-stu-id="f55d1-117">Contact  an administrator if no connection is available.</span></span> <span data-ttu-id="f55d1-118">Ja esat administrators, jūs varat izveidot savienojumu, atlasot **Pievienot savienojumu**.</span><span class="sxs-lookup"><span data-stu-id="f55d1-118">If you are an administrator, you can create a connection by selecting **Add connection**.</span></span> <span data-ttu-id="f55d1-119">Nolaižamajā izvēlnē atlasiet **HERE Technologies**.</span><span class="sxs-lookup"><span data-stu-id="f55d1-119">Choose **HERE Technologies** from the drop-down.</span></span> 

1. <span data-ttu-id="f55d1-120">Atlasiet **Pieslēgties HERE Technologies**, lai apstiprinātu savienojuma atlasi.</span><span class="sxs-lookup"><span data-stu-id="f55d1-120">Select **Connect to HERE Technologies** to confirm the selection.</span></span>

1.  <span data-ttu-id="f55d1-121">Atlasiet **Tālāk** un izvēlieties **Klientu datu kopu**, kuru vēlaties bagātināt ar atrašanās vietas datiem no HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="f55d1-121">Select **Next** and choose the **Customer data set** you want to enrich with location data from HERE Technologies.</span></span> <span data-ttu-id="f55d1-122">Varat atlasīt entītiju **Klients**, lai bagātinātu visus klientu profilus, vai atlasīt segmenta entītiju, lai bagātinātu tikai šajā segmentā iekļautos klientu profilus.</span><span class="sxs-lookup"><span data-stu-id="f55d1-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="Ekrānuzņēmums, izvēloties klientu datu kopu.":::

1. <span data-ttu-id="f55d1-124">Izvēlieties, vai jākartē lauki primārajai un/vai sekundārajai adresei.</span><span class="sxs-lookup"><span data-stu-id="f55d1-124">Choose if you want to map fields to the primary and/or secondary address.</span></span> <span data-ttu-id="f55d1-125">Jūs varat norādīt lauka kartējumu abām adresēm un atsevišķi bagātināt abu adrešu profilus.</span><span class="sxs-lookup"><span data-stu-id="f55d1-125">You can specify a field mapping for both addresses and enrich the profiles for both addresses separately.</span></span> <span data-ttu-id="f55d1-126">Piemēram, ja ir mājas un darba adrese.</span><span class="sxs-lookup"><span data-stu-id="f55d1-126">For example, if there's a home and a business address.</span></span> <span data-ttu-id="f55d1-127">Atlasiet **Tālāk**.</span><span class="sxs-lookup"><span data-stu-id="f55d1-127">Select **Next**.</span></span>

1. <span data-ttu-id="f55d1-128">Definējiet, kurus vienoto profilu laukus vajadzētu izmantot, lai meklētu atbilstošos HERE Technologies atrašanās vietas datus.</span><span class="sxs-lookup"><span data-stu-id="f55d1-128">Define which fields from your unified profiles should be used to look for matching location data from HERE Technologies.</span></span> <span data-ttu-id="f55d1-129">Atlasītajai primārajai un/vai sekundārajai adresei ir nepieciešami lauki **1.adrese** un **Pasta indekss**.</span><span class="sxs-lookup"><span data-stu-id="f55d1-129">The **Street 1** and **Zip/Postal Code** fields are required for the selected primary and/or secondary address.</span></span> <span data-ttu-id="f55d1-130">Lai iegūtu augstāku atbilstību precizitāti, var pievienot vairākus laukus.</span><span class="sxs-lookup"><span data-stu-id="f55d1-130">For a higher match accuracy, more fields can be added.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f55d1-131">![HERE Technologies bagātināšanas konfigurācijas lapa](media/enrichment-HERE-configuration.png "HERE Technologies bagātināšanas konfigurācijas lapa")</span><span class="sxs-lookup"><span data-stu-id="f55d1-131">![HERE Technologies enrichment configuration page](media/enrichment-HERE-configuration.png "HERE Technologies enrichment configuration page")</span></span>

1. <span data-ttu-id="f55d1-132">Lai pabeigtu lauka kartēšanu, atlasiet **Tālāk**.</span><span class="sxs-lookup"><span data-stu-id="f55d1-132">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="f55d1-133">Norādiet bagātināto datu nosaukumu.</span><span class="sxs-lookup"><span data-stu-id="f55d1-133">Provide a name for the enrichment.</span></span> 

<span data-ttu-id="f55d1-134">1. Pēc izvēļu pārskatīšanas atlasiet **Saglabāt vidi**.</span><span class="sxs-lookup"><span data-stu-id="f55d1-134">1.Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-here-technologies"></a><span data-ttu-id="f55d1-135">HERE Technologies savienojuma konfigurēšana</span><span class="sxs-lookup"><span data-stu-id="f55d1-135">Configure the connection for HERE technologies</span></span> 

<span data-ttu-id="f55d1-136">Lai konfigurētu savienojumus, jums ir jābūt administratoram.</span><span class="sxs-lookup"><span data-stu-id="f55d1-136">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="f55d1-137">Konfigurējot bagātinātos datus, atlasiet **Pievienot savienojumu** *vai* dodieties uz **Administrators** > **Savienojumi** un HERE Technologies rūtī atlasiet **Iestatīt**.</span><span class="sxs-lookup"><span data-stu-id="f55d1-137">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the HERE Technologies tile.</span></span>

1. <span data-ttu-id="f55d1-138">Lodziņā **Parādāmais nosaukums** ievadiet savienojuma nosaukumu.</span><span class="sxs-lookup"><span data-stu-id="f55d1-138">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="f55d1-139">Norādiet derīgu HERE Technologies API atslēgu.</span><span class="sxs-lookup"><span data-stu-id="f55d1-139">Provide a valid HERE Technologies API key.</span></span>

1. <span data-ttu-id="f55d1-140">Pārskatiet un sniedziet savu piekrišanu **Datu konfidencialitātei un atbilstībai**, atzīmējot izvēles rūtiņu **Piekrītu**</span><span class="sxs-lookup"><span data-stu-id="f55d1-140">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox</span></span>

1. <span data-ttu-id="f55d1-141">Lai pārbaudītu konfigurāciju, atlasiet **Pārbaudīt**.</span><span class="sxs-lookup"><span data-stu-id="f55d1-141">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="f55d1-142">Pēc pārbaudes pabeigšanas atlasiet **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="f55d1-142">After completing the verification, select **Save**.</span></span>

> [!div class="mx-imgBorder"]
   > <span data-ttu-id="f55d1-143">![HERE Technologies savienojuma konfigurēšanas lapa](media/enrichment-HERE-connection.png "HERE Technologies savienojuma konfigurēšanas lapa")</span><span class="sxs-lookup"><span data-stu-id="f55d1-143">![HERE Technologies connection configuration page](media/enrichment-HERE-connection.png "HERE Technologies connection configuration page")</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="f55d1-144">Bagātināšanas rezultāti</span><span class="sxs-lookup"><span data-stu-id="f55d1-144">Enrichment results</span></span>

<span data-ttu-id="f55d1-145">Lai sāktu bagātināšanas procesu, komandjoslā atlasiet **Palaist**.</span><span class="sxs-lookup"><span data-stu-id="f55d1-145">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="f55d1-146">Varat arī ļaut sistēmai palaist bagātināšanu automātiski kā daļu no [plānotās atsvaidzināšanas](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="f55d1-146">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="f55d1-147">Apstrādes laiks ir atkarīgs no jūsu klientu datu izmēra un API atbildes laikiem no HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="f55d1-147">The processing time will depend on the size of your customer data and the API response times from HERE Technologies.</span></span>

<span data-ttu-id="f55d1-148">Pēc bagātināšanas procesa noslēgšanas varat pārskatīt tikko bagātinātos klientu profilu datus, dodoties uz sadaļu **Mana bagātināšana**.</span><span class="sxs-lookup"><span data-stu-id="f55d1-148">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="f55d1-149">Turklāt jūs redzēsit pēdējā atjauninājuma laiku un bagātināto profilu skaitu.</span><span class="sxs-lookup"><span data-stu-id="f55d1-149">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="f55d1-150">Jūs varat piekļūt detalizētam katra bagātināta profila skatam, atlasot opciju **Skatīt bagātinātos datus**.</span><span class="sxs-lookup"><span data-stu-id="f55d1-150">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f55d1-151">Nākamās darbības</span><span class="sxs-lookup"><span data-stu-id="f55d1-151">Next steps</span></span>

<span data-ttu-id="f55d1-152">Būvējiet virs saviem bagātinātajiem klientu datiem.</span><span class="sxs-lookup"><span data-stu-id="f55d1-152">Build on top of your enriched customer data.</span></span> <span data-ttu-id="f55d1-153">Veidojiet [segmentus](segments.md), [mērus](measures.md)un pat [eksportējiet datus](export-destinations.md), lai klientiem sniegtu personalizētas iespējas.</span><span class="sxs-lookup"><span data-stu-id="f55d1-153">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="f55d1-154">Datu konfidencialitāte un atbilstība</span><span class="sxs-lookup"><span data-stu-id="f55d1-154">Data privacy and compliance</span></span>

<span data-ttu-id="f55d1-155">Ja iespējojat Dynamics 365 Customer Insights datu pārsūtīšanu uz HERE Technologies, jūs atļaujat datu pārsūtīšanu ārpus atbilstības robežām Dynamics 365 Customer Insights, ieskaitot iespējami sensitīvus datus, piemēram, personas datus.</span><span class="sxs-lookup"><span data-stu-id="f55d1-155">When you enable Dynamics 365 Customer Insights to transmit data to HERE Technologies, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="f55d1-156">Microsoft šos datus pārsūtīs pēc jūsu norādēm, bet jūs esat atbildīgs par to, lai nodrošinātu HERE Technologies atbilstību konfidencialitātes vai drošības saistībām, kas jums varētu rasties.</span><span class="sxs-lookup"><span data-stu-id="f55d1-156">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that HERE Technologies meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="f55d1-157">Papildinformāciju skatiet rakstā [Microsoft Privātuma paziņojums](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="f55d1-157">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="f55d1-158">Jūsu Dynamics 365 Customer Insights administrators var noņemt šo bagātināšanas funkciju jebkurā laikā, lai pārtrauktu izmantot šo funkcionalitāti.</span><span class="sxs-lookup"><span data-stu-id="f55d1-158">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
