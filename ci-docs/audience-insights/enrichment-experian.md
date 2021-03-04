---
title: Bagātināšana ar trešās puses bagātināšanas programmu Experian
description: Vispārēja informācija par Experian trešās puses bagātināšanu.
ms.date: 12/10/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: baf3cc58a233b70c48fb94ac4a543d162f91bdd1
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269569"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="e2532-103">Bagātiniet klientu profilus ar demogrāfijas rādītājiem no Experian (priekšskatījums)</span><span class="sxs-lookup"><span data-stu-id="e2532-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="e2532-104">Experian ir pasaules mēroga līderis patērētāju un uzņēmumu kredītatskaišu un mārketinga pakalpojumu nodrošināšanā.</span><span class="sxs-lookup"><span data-stu-id="e2532-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="e2532-105">Ar Experian datu bagātināšanas pakalpojumiem jūs varat veidot padziļinātāku izpratni par saviem klientiem, bagātinot klientu profilus ar demogrāfijas datiem, piemēram, mājsaimniecības izmēru, ieņēmumiem utt.</span><span class="sxs-lookup"><span data-stu-id="e2532-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e2532-106">Priekšnosacījumi</span><span class="sxs-lookup"><span data-stu-id="e2532-106">Prerequisites</span></span>

<span data-ttu-id="e2532-107">Lai konfigurētu Experian, ir jāatbilst šādiem priekšnosacījumiem:</span><span class="sxs-lookup"><span data-stu-id="e2532-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="e2532-108">Ir jābūt aktīvam Experian abonementam.</span><span class="sxs-lookup"><span data-stu-id="e2532-108">You have an active Experian subscription.</span></span> <span data-ttu-id="e2532-109">Lai iegūtu abonementu, tieši [sazinieties ar Experian](https://www.experian.com/marketing-services/contact).</span><span class="sxs-lookup"><span data-stu-id="e2532-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="e2532-110">[Uzziniet vairāk par Experian datu bagātināšanu](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="e2532-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>
- <span data-ttu-id="e2532-111">Jums ir lietotāja ID, partijas ID un modeļa numurs jūsu SSH iespējotajam drošās transportēšanas (ST) kontam, kuru Experian jums ir izveidojis.</span><span class="sxs-lookup"><span data-stu-id="e2532-111">You have the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>
- <span data-ttu-id="e2532-112">Jums ir [Administratora](permissions.md#administrator) tiesības skatīt auditorijas ieskatus.</span><span class="sxs-lookup"><span data-stu-id="e2532-112">You have [Administrator](permissions.md#administrator) permissions in audience insights.</span></span>

## <a name="configuration"></a><span data-ttu-id="e2532-113">Konfigurācija</span><span class="sxs-lookup"><span data-stu-id="e2532-113">Configuration</span></span>

1. <span data-ttu-id="e2532-114">dodieties uz **Dati** > **Bagātināšana** un atlasiet cilni **Atklāt**.</span><span class="sxs-lookup"><span data-stu-id="e2532-114">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="e2532-115">Experian elementā atlasiet **Bagātināt manus datus**.</span><span class="sxs-lookup"><span data-stu-id="e2532-115">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e2532-116">![Experian elements](media/experian-tile.png "Experian elements")</span><span class="sxs-lookup"><span data-stu-id="e2532-116">![Experian tile](media/experian-tile.png "Experian tile")</span></span>

1. <span data-ttu-id="e2532-117">Atlasiet **Sākt darbu** un ievadiet lietotāja ID, partijas ID un modeļa numuru jūsu Experian drošās transportēšanas kontam.</span><span class="sxs-lookup"><span data-stu-id="e2532-117">Select **Get started** and enter the User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span> <span data-ttu-id="e2532-118">Pārskatiet un sniedziet savu piekrišanu **Datu konfidencialitātei un atbilstībai**, atzīmējot izvēles rūtiņu **Piekrītu**.</span><span class="sxs-lookup"><span data-stu-id="e2532-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> <span data-ttu-id="e2532-119">Apstipriniet visus datus, atlasot **Piemērot**.</span><span class="sxs-lookup"><span data-stu-id="e2532-119">Confirm all inputs by selecting **Apply**.</span></span>

## <a name="map-your-fields"></a><span data-ttu-id="e2532-120">Lauku kartēšana</span><span class="sxs-lookup"><span data-stu-id="e2532-120">Map your fields</span></span>

1.  <span data-ttu-id="e2532-121">Atlasiet **Pievienot datus** un izvēlieties **Klienta datu kopu**, ko vēlaties bagātināt ar demogrāfiskajiem datiem no programmas Experian.</span><span class="sxs-lookup"><span data-stu-id="e2532-121">Select **Add data** and choose the **Customer data set** you want to enrich with demographics data from Experian.</span></span> <span data-ttu-id="e2532-122">Varat atlasīt entītiju **Klients**, lai bagātinātu visus klientu profilus, vai atlasīt segmenta entītiju, lai bagātinātu tikai šajā segmentā iekļautos klientu profilus.</span><span class="sxs-lookup"><span data-stu-id="e2532-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

1. <span data-ttu-id="e2532-123">Atlasiet galvenos identifikatorus no laukiem **Vārds un adrese**, **E-pasts** vai **Tālrunis**, lai tos nosūtītu uz Experian identitātes noteikšanai.</span><span class="sxs-lookup"><span data-stu-id="e2532-123">Select your key identifiers from **Name and Address**, **E-mail**, or **Phone** to send to Experian for identity resolution.</span></span>

   > [!TIP]
   > <span data-ttu-id="e2532-124">Jo vairāk galveno identifikatoru atribūtu tiek nosūtīts Experian, jo augstāka iespēja iegūt augstāku atbilstības rādītāju.</span><span class="sxs-lookup"><span data-stu-id="e2532-124">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="e2532-125">Atlasiet **Nākamais** un kartējiet atbilstošos atribūtus no jūsu vienotās klientu entītijas atlasītajiem galvenajiem identifikatoru laukiem.</span><span class="sxs-lookup"><span data-stu-id="e2532-125">Select **Next** and map the corresponding attributes from your unified customer entity for the selected key identifier fields.</span></span>

1. <span data-ttu-id="e2532-126">Atlasiet **Pievienot atribūtus**, lai kartētu papildu atribūtus, kurus vēlaties nosūtīt uz Experian.</span><span class="sxs-lookup"><span data-stu-id="e2532-126">Select **Add attribute** to map any additional attributes you would like to send to Experian.</span></span>

1.  <span data-ttu-id="e2532-127">Atlasiet **Saglabāt**, lai pabeigtu lauka kartēšanu.</span><span class="sxs-lookup"><span data-stu-id="e2532-127">Select **Save** to complete the field mapping.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="e2532-128">![Experian lauka kartēšana](media/experian-field-mapping.png "Experian lauka kartēšana")</span><span class="sxs-lookup"><span data-stu-id="e2532-128">![Experian field mapping](media/experian-field-mapping.png "Experian field mapping")</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="e2532-129">Bagātināšanas rezultāti</span><span class="sxs-lookup"><span data-stu-id="e2532-129">Enrichment results</span></span>

<span data-ttu-id="e2532-130">Lai sāktu bagātināšanas procesu, komandjoslā atlasiet **Palaist**.</span><span class="sxs-lookup"><span data-stu-id="e2532-130">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="e2532-131">Varat arī ļaut sistēmai palaist bagātināšanu automātiski kā daļu no [plānotās atsvaidzināšanas](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="e2532-131">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="e2532-132">Apstrādes laiks būs atkarīgs no klientu datu izmēra un bagātināšanas procesiem, kurus jūsu kontam ir uzstādījis Experian.</span><span class="sxs-lookup"><span data-stu-id="e2532-132">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="e2532-133">Pēc bagātināšanas procesa noslēgšanas varat pārskatīt tikko bagātinātos klientu profilu datus, dodoties uz sadaļu **Mana bagātināšana**.</span><span class="sxs-lookup"><span data-stu-id="e2532-133">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="e2532-134">Turklāt jūs redzēsit pēdējā atjauninājuma laiku un bagātināto profilu skaitu.</span><span class="sxs-lookup"><span data-stu-id="e2532-134">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="e2532-135">Jūs varat piekļūt detalizētam katra bagātināta profila skatam, atlasot opciju **Skatīt bagātinātos datus**.</span><span class="sxs-lookup"><span data-stu-id="e2532-135">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="e2532-136">Nākamās darbības</span><span class="sxs-lookup"><span data-stu-id="e2532-136">Next steps</span></span>

<span data-ttu-id="e2532-137">Būvējiet virs saviem bagātinātajiem klientu datiem.</span><span class="sxs-lookup"><span data-stu-id="e2532-137">Build on top of your enriched customer data.</span></span> <span data-ttu-id="e2532-138">Veidojiet [segmentus](segments.md), [mērus](measures.md)un pat [eksportējiet datus](export-destinations.md), lai klientiem sniegtu personalizētas iespējas.</span><span class="sxs-lookup"><span data-stu-id="e2532-138">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="e2532-139">Datu konfidencialitāte un atbilstība</span><span class="sxs-lookup"><span data-stu-id="e2532-139">Data privacy and compliance</span></span>

<span data-ttu-id="e2532-140">Ja iespējojat Dynamics 365 Customer Insights datu pārsūtīšanu uz Experian, jūs atļaujat datu pārsūtīšanu ārpus atbilstības robežām Dynamics 365 Customer Insights, ieskaitot iespējami sensitīvus datus, piemēram, personas datus.</span><span class="sxs-lookup"><span data-stu-id="e2532-140">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="e2532-141">Microsoft šos datus pārsūtīs pēc jūsu norādēm, bet jūs esat atbildīgs par to, lai nodrošinātu Experian atbilstību konfidencialitātes vai drošības saistībām, kas jums varētu rasties.</span><span class="sxs-lookup"><span data-stu-id="e2532-141">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="e2532-142">Papildinformāciju skatiet rakstā [Microsoft Privātuma paziņojums](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="e2532-142">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="e2532-143">Jūsu Dynamics 365 Customer Insights administrators var noņemt šo bagātināšanas funkciju jebkurā laikā, lai pārtrauktu izmantot šo funkcionalitāti.</span><span class="sxs-lookup"><span data-stu-id="e2532-143">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]