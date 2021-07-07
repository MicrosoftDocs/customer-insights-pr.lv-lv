---
title: Bagātināšana ar trešās puses bagātināšanas Experian
description: Vispārīga informācija par Experian trešo pušu bagātināšanu.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 7c82fe92b3351a782a4fa6510300d870b742d042
ms.sourcegitcommit: 42b3bce1e20e7cc707d232844dacfeed3d6fc096
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 06/28/2021
ms.locfileid: "6309829"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="6d67e-103">Klientu profilu bagātināšana ar demogrāfiskajiem datiem no Experian (priekšskatījums)</span><span class="sxs-lookup"><span data-stu-id="6d67e-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="6d67e-104">Experian ir globālais līderis patērētāju un uzņēmumu kredītu pārskatu izveides un mārketinga pakalpojumos.</span><span class="sxs-lookup"><span data-stu-id="6d67e-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="6d67e-105">Izmantojot Experian datu bagātināšanas pakalpojumus, jūs varat veidot lielāku izpratni par saviem klientiem, bagātinot savu klientu profilus ar tādiem demogrāfiskiem datiem kā mājsaimniecības lielums, ienākumi un daudz kas cits.</span><span class="sxs-lookup"><span data-stu-id="6d67e-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="6d67e-106">Priekšnosacījumi</span><span class="sxs-lookup"><span data-stu-id="6d67e-106">Prerequisites</span></span>

<span data-ttu-id="6d67e-107">Lai konfigurētu Experian, ir jāizpilda šādi priekšnosacījumi:</span><span class="sxs-lookup"><span data-stu-id="6d67e-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="6d67e-108">Jums ir jābūt aktīvam Experian abonementam.</span><span class="sxs-lookup"><span data-stu-id="6d67e-108">You have an active Experian subscription.</span></span> <span data-ttu-id="6d67e-109">Lai iegūtu abonementu, tieši [sazinieties ar Experian](https://www.experian.com/marketing-services/contact).</span><span class="sxs-lookup"><span data-stu-id="6d67e-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="6d67e-110">[Papildinformācija par Experian datu bagātināšanu](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="6d67e-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>

- <span data-ttu-id="6d67e-111">Administrators jau ir konfigurējis Experian savienojumu *vai* jums ir [administratora](permissions.md#administrator) atļaujas.</span><span class="sxs-lookup"><span data-stu-id="6d67e-111">An Experian connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="6d67e-112">Jums ir nepieciešams arī lietotāja ID, puses ID un modeļa numurs jūsu SSH iespējotajam drošajam transporta (ST) kontam, ko Experian izveidoja jums.</span><span class="sxs-lookup"><span data-stu-id="6d67e-112">You also need the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="6d67e-113">Atbalstītās valstis/reģioni</span><span class="sxs-lookup"><span data-stu-id="6d67e-113">Supported countries/regions</span></span>

<span data-ttu-id="6d67e-114">Pašlaik tiek atbalstīta klientu profilu bagātināšana tikai Amerikas Savienotajās Valstīs.</span><span class="sxs-lookup"><span data-stu-id="6d67e-114">We currently support enriching customer profiles in the United States only.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="6d67e-115">Bagātināto datu konfigurēšana</span><span class="sxs-lookup"><span data-stu-id="6d67e-115">Configure the enrichment</span></span>

1. <span data-ttu-id="6d67e-116">Dodieties uz **Dati** > **Bagātināšana** un atlasiet cilni **Atklāt**.</span><span class="sxs-lookup"><span data-stu-id="6d67e-116">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="6d67e-117">Atlasiet **Bagātināt manus datus** elementā Experian.</span><span class="sxs-lookup"><span data-stu-id="6d67e-117">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="6d67e-118">![Experian elements](media/experian-tile.png "Experian elements")</span><span class="sxs-lookup"><span data-stu-id="6d67e-118">![Experian tile](media/experian-tile.png "Experian tile")</span></span>
   > 

1. <span data-ttu-id="6d67e-119">Atlasiet [savienojumu](connections.md) nolaižamajā sarakstā.</span><span class="sxs-lookup"><span data-stu-id="6d67e-119">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="6d67e-120">Ja nav pieejamu savienojumu, sazinieties ar administratoru.</span><span class="sxs-lookup"><span data-stu-id="6d67e-120">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="6d67e-121">Ja esat administrators, varat izveidot savienojumu, atlasot **Pievienot savienojumu** un izvēloties Experian nolaižamajā sarakstā.</span><span class="sxs-lookup"><span data-stu-id="6d67e-121">If you are an administrator, you can create a connection by selecting **Add connection** and choosing Experian from the dropdown list.</span></span> 

1. <span data-ttu-id="6d67e-122">Atlasiet **Savienot ar Experian**, lai apstiprinātu savienojuma atlasi.</span><span class="sxs-lookup"><span data-stu-id="6d67e-122">Select **Connect to Experian** to confirm the connection selection.</span></span>

1.  <span data-ttu-id="6d67e-123">Atlasiet **Nākamais** un izvēlieties **Klientu datu kopu**, kuru vēlaties bagātināt ar demogrāfiskajiem datiem no Experian.</span><span class="sxs-lookup"><span data-stu-id="6d67e-123">Select **Next** and choose the **Customer data set** you want to enrich with demographics data from Experian.</span></span> <span data-ttu-id="6d67e-124">Varat atlasīt entītiju **Klients**, lai bagātinātu visus klientu profilus, vai atlasīt segmenta entītiju, lai bagātinātu tikai šajā segmentā iekļautos klientu profilus.</span><span class="sxs-lookup"><span data-stu-id="6d67e-124">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Ekrānuzņēmums, izvēloties klientu datu kopu.":::

1. <span data-ttu-id="6d67e-126">Atlasiet **Tālāk** un definējiet, kāda tipa lauki no jūsu vienotajiem profiliem ir jāizmanto, lai meklētu atbilstošos demogrāfisko datus no Experian.</span><span class="sxs-lookup"><span data-stu-id="6d67e-126">Select **Next** and define which type of fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="6d67e-127">Ir obligāti jānorāda vismaz viens no laukiem **Vārds, uzvārds un adrese**, **Tālruņa numurs** vai **E-pasts**.</span><span class="sxs-lookup"><span data-stu-id="6d67e-127">At least one of the fields **Name and address**, **Phone**, or **Email** is required.</span></span> <span data-ttu-id="6d67e-128">Lai nodrošinātu augstāku atbilstības precizitāti, var pievienot līdz diviem citiem laukiem.</span><span class="sxs-lookup"><span data-stu-id="6d67e-128">For a higher match accuracy, up to two other fields can be added.</span></span> <span data-ttu-id="6d67e-129">Šāda atlase ietekmēs kartēšanas laukus, kuriem jums būs piekļuve nākamajā darbībā.</span><span class="sxs-lookup"><span data-stu-id="6d67e-129">This selection will affect the mapping fields you have access to in the next step.</span></span>

    > [!TIP]
    > <span data-ttu-id="6d67e-130">Papildu atslēgas identifikatora atribūti, kas nosūtīti uz Experian, var nodrošināt augstāku atbilstības precizitāti.</span><span class="sxs-lookup"><span data-stu-id="6d67e-130">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="6d67e-131">Lai sāktu lauka kartēšanu, atlasiet **Tālāk**.</span><span class="sxs-lookup"><span data-stu-id="6d67e-131">Select **Next** to start the field mapping.</span></span>

1. <span data-ttu-id="6d67e-132">Definējiet, kāda tipa lauki no jūsu vienotajiem profiliem ir jāizmanto, lai meklētu atbilstošos demogrāfiskos datus no Experian.</span><span class="sxs-lookup"><span data-stu-id="6d67e-132">Define which fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="6d67e-133">Obligātie lauki ir atzīmēti.</span><span class="sxs-lookup"><span data-stu-id="6d67e-133">Required fields are marked.</span></span>

1. <span data-ttu-id="6d67e-134">Norādiet bagātināto datu nosaukumu un izvades entitījas nosaukumu.</span><span class="sxs-lookup"><span data-stu-id="6d67e-134">Provide a name for the enrichment and a name for the output entity.</span></span>

1. <span data-ttu-id="6d67e-135">Pēc izvēļu pārskatīšanas atlasiet **Saglabāt bagātināšanu**.</span><span class="sxs-lookup"><span data-stu-id="6d67e-135">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-experian"></a><span data-ttu-id="6d67e-136">Savienojuma konfigurēšana Experian</span><span class="sxs-lookup"><span data-stu-id="6d67e-136">Configure the connection for Experian</span></span> 

<span data-ttu-id="6d67e-137">Lai konfigurētu savienojumus, jums ir jābūt administratoram.</span><span class="sxs-lookup"><span data-stu-id="6d67e-137">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="6d67e-138">Atlasiet vienumu **Pievienot savienojumu**, konfigurējot bagātināšanu, *vai* pārejiet uz **Administrators** > **Savienojumi** un atlasiet opciju **Iestatīt** Experian elementā.</span><span class="sxs-lookup"><span data-stu-id="6d67e-138">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Experian tile.</span></span>

1. <span data-ttu-id="6d67e-139">Atlasiet **Sākt**.</span><span class="sxs-lookup"><span data-stu-id="6d67e-139">Select **Get Started**.</span></span>

1. <span data-ttu-id="6d67e-140">Lodziņā **Parādāmais nosaukums** ievadiet savienojuma nosaukumu.</span><span class="sxs-lookup"><span data-stu-id="6d67e-140">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="6d67e-141">Ievadiet savam Experian drošajam transporta kontam derīgu lietotāja ID, puses ID un modeļa numuru.</span><span class="sxs-lookup"><span data-stu-id="6d67e-141">Enter valid User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span>

1. <span data-ttu-id="6d67e-142">Pārskatiet un sniedziet savu piekrišanu **Datu konfidencialitātei un atbilstībai**, atlasot **Es piekrītu**.</span><span class="sxs-lookup"><span data-stu-id="6d67e-142">Review and provide your consent for **Data privacy and compliance** by selecting **I agree**.</span></span>

1. <span data-ttu-id="6d67e-143">Lai pārbaudītu konfigurāciju, atlasiet **Pārbaudīt**.</span><span class="sxs-lookup"><span data-stu-id="6d67e-143">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="6d67e-144">Pēc pārbaudes pabeigšanas atlasiet **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="6d67e-144">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Experian savienojuma konfigurācijas rūts.":::

## <a name="enrichment-results"></a><span data-ttu-id="6d67e-146">Bagātināšanas rezultāti</span><span class="sxs-lookup"><span data-stu-id="6d67e-146">Enrichment results</span></span>

<span data-ttu-id="6d67e-147">Lai sāktu bagātināšanas procesu, komandjoslā atlasiet **Palaist**.</span><span class="sxs-lookup"><span data-stu-id="6d67e-147">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="6d67e-148">Varat arī ļaut sistēmai palaist bagātināšanu automātiski kā daļu no [plānotās atsvaidzināšanas](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="6d67e-148">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="6d67e-149">Apstrādes laiks atkarīgs no klientu datu apjoma un bagātināšanas procesiem, ko jūsu kontam iestata Experian.</span><span class="sxs-lookup"><span data-stu-id="6d67e-149">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="6d67e-150">Pēc bagātināšanas procesa noslēgšanas varat pārskatīt tikko bagātinātos klientu profilu datus, dodoties uz sadaļu **Mana bagātināšana**.</span><span class="sxs-lookup"><span data-stu-id="6d67e-150">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="6d67e-151">Turklāt jūs redzēsit pēdējā atjauninājuma laiku un bagātināto profilu skaitu.</span><span class="sxs-lookup"><span data-stu-id="6d67e-151">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="6d67e-152">Jūs varat piekļūt detalizētam katra bagātināta profila skatam, atlasot opciju **Skatīt bagātinātos datus**.</span><span class="sxs-lookup"><span data-stu-id="6d67e-152">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="6d67e-153">Nākamās darbības</span><span class="sxs-lookup"><span data-stu-id="6d67e-153">Next steps</span></span>

<span data-ttu-id="6d67e-154">Pilnveidojiet savus bagātinātos klientu datus.</span><span class="sxs-lookup"><span data-stu-id="6d67e-154">Build on top of your enriched customer data.</span></span> <span data-ttu-id="6d67e-155">Veidojiet [segmentus](segments.md) un [pasākumus](measures.md) un pat [eksportējiet datus](export-destinations.md), lai nodrošinātu klientiem personalizētu pieredzi.</span><span class="sxs-lookup"><span data-stu-id="6d67e-155">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="6d67e-156">Datu konfidencialitāte un atbilstība</span><span class="sxs-lookup"><span data-stu-id="6d67e-156">Data privacy and compliance</span></span>

<span data-ttu-id="6d67e-157">Iespējojot Dynamics 365 Customer Insights datu pārsūtīšanai uz Experian, jūs atļaujat datu pārsūtīšanu ārpus atbilstības robežas, kas paredzēta Dynamics 365 Customer Insights, ieskaitot potenciāli sensitīvus datus, piemēram, personas datus.</span><span class="sxs-lookup"><span data-stu-id="6d67e-157">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="6d67e-158">Microsoft šos datus pārsūtīs pēc jūsu norādījuma, bet jūs esat atbildīgs par to, lai Experian atbilstu visām jūsu konfidencialitātes vai drošības saistībām.</span><span class="sxs-lookup"><span data-stu-id="6d67e-158">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="6d67e-159">Papildinformāciju skatiet rakstā [Microsoft Privātuma paziņojums](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="6d67e-159">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="6d67e-160">Jūsu Dynamics 365 Customer Insights administrators var noņemt šo bagātināšanas funkciju jebkurā laikā, lai pārtrauktu šīs funkcijas izmantošanu.</span><span class="sxs-lookup"><span data-stu-id="6d67e-160">Your Dynamics 365 Customer Insights administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
