---
title: Bagātināšana ar trešās puses bagātināšanas programmu Experian
description: Vispārēja informācija par Experian trešās puses bagātināšanu.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 9cf2a7fa18ecc022ea67f6829f52381ad59f3172
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896382"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="9547c-103">Bagātiniet klientu profilus ar demogrāfijas rādītājiem no Experian (priekšskatījums)</span><span class="sxs-lookup"><span data-stu-id="9547c-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="9547c-104">Experian ir pasaules mēroga līderis patērētāju un uzņēmumu kredītatskaišu un mārketinga pakalpojumu nodrošināšanā.</span><span class="sxs-lookup"><span data-stu-id="9547c-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="9547c-105">Ar Experian datu bagātināšanas pakalpojumiem jūs varat veidot padziļinātāku izpratni par saviem klientiem, bagātinot klientu profilus ar demogrāfijas datiem, piemēram, mājsaimniecības izmēru, ieņēmumiem utt.</span><span class="sxs-lookup"><span data-stu-id="9547c-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9547c-106">Priekšnosacījumi</span><span class="sxs-lookup"><span data-stu-id="9547c-106">Prerequisites</span></span>

<span data-ttu-id="9547c-107">Lai konfigurētu Experian, ir jāatbilst šādiem priekšnosacījumiem:</span><span class="sxs-lookup"><span data-stu-id="9547c-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="9547c-108">Ir jābūt aktīvam Experian abonementam.</span><span class="sxs-lookup"><span data-stu-id="9547c-108">You have an active Experian subscription.</span></span> <span data-ttu-id="9547c-109">Lai iegūtu abonementu, tieši [sazinieties ar Experian](https://www.experian.com/marketing-services/contact).</span><span class="sxs-lookup"><span data-stu-id="9547c-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="9547c-110">[Uzziniet vairāk par Experian datu bagātināšanu](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="9547c-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>

- <span data-ttu-id="9547c-111">Administrators jau ir konfigurējis Experian savienojumu *vai* jums ir [administratora](permissions.md#administrator) atļaujas.</span><span class="sxs-lookup"><span data-stu-id="9547c-111">An Experian connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="9547c-112">Jums arī ir nepieciešams lietotāja ID, partijas ID un modeļa numurs jūsu SSH iespējotajam drošā transporta (ST) kontam, kuru jums izveidoja Experian.</span><span class="sxs-lookup"><span data-stu-id="9547c-112">You also need the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="9547c-113">Bagātināto datu konfigurēšana</span><span class="sxs-lookup"><span data-stu-id="9547c-113">Configure the enrichment</span></span>

1. <span data-ttu-id="9547c-114">dodieties uz **Dati** > **Bagātināšana** un atlasiet cilni **Atklāt**.</span><span class="sxs-lookup"><span data-stu-id="9547c-114">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="9547c-115">Experian elementā atlasiet **Bagātināt manus datus**.</span><span class="sxs-lookup"><span data-stu-id="9547c-115">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9547c-116">![Experian elements](media/experian-tile.png "Experian elements")</span><span class="sxs-lookup"><span data-stu-id="9547c-116">![Experian tile](media/experian-tile.png "Experian tile")</span></span>
   > 

1. <span data-ttu-id="9547c-117">Nolaižamajā izvēlnē atlasiet [savienojums](connections.md).</span><span class="sxs-lookup"><span data-stu-id="9547c-117">Select a [connection](connections.md) from the drop-down.</span></span> <span data-ttu-id="9547c-118">Ja nav pieejamu savienojumu, sazinieties ar administratoru.</span><span class="sxs-lookup"><span data-stu-id="9547c-118">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="9547c-119">Ja esat administrators, jūs varat izveidot savienojumu, atlasot **Pievienot savienojumu** un nolaižamajā izvēlnē izvēloties Experian.</span><span class="sxs-lookup"><span data-stu-id="9547c-119">If you are an administrator, you can create a connection by selecting **Add connection** and choosing Experian from the drop-down.</span></span> 

1. <span data-ttu-id="9547c-120">Atlasiet **Pieslēgties Experian**, lai apstiprinātu savienojuma atlasi.</span><span class="sxs-lookup"><span data-stu-id="9547c-120">Select **Connect to Experian** to confirm the connection selection.</span></span>

1.  <span data-ttu-id="9547c-121">Atlasiet **Tālāk** un izvēlieties **Klientu datu kopu**, kuru vēlaties bagātināt ar demogrāfijas datiem no Experian.</span><span class="sxs-lookup"><span data-stu-id="9547c-121">Select **Next** and choose the **Customer data set** you want to enrich with demographics data from Experian.</span></span> <span data-ttu-id="9547c-122">Varat atlasīt entītiju **Klients**, lai bagātinātu visus klientu profilus, vai atlasīt segmenta entītiju, lai bagātinātu tikai šajā segmentā iekļautos klientu profilus.</span><span class="sxs-lookup"><span data-stu-id="9547c-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Ekrānuzņēmums, izvēloties klientu datu kopu.":::

1. <span data-ttu-id="9547c-124">Atlasiet **Tālāk** un definējiet kura veida laukus no jūsu vienotajiem profiliem vajadzētu izmantot, meklējot atbilstošus demogrāfijas datus no Experian.</span><span class="sxs-lookup"><span data-stu-id="9547c-124">Select **Next** and define which type of fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="9547c-125">Ir obligāti jānorāda vismaz viens no laukiem **Vārds, uzvārds un adrese**, **Tālruņa numurs** vai **E-pasts**.</span><span class="sxs-lookup"><span data-stu-id="9547c-125">At least one of the fields **Name and address**, **Phone**, or **Email** is required.</span></span> <span data-ttu-id="9547c-126">Lai nodrošinātu augstāku atbilstības precizitāti, var pievienot līdz diviem citiem laukiem.</span><span class="sxs-lookup"><span data-stu-id="9547c-126">For a higher match accuracy, up to two other fields can be added.</span></span> <span data-ttu-id="9547c-127">Šāda atlase ietekmēs kartēšanas laukus, kuriem jums būs piekļuve nākamajā darbībā.</span><span class="sxs-lookup"><span data-stu-id="9547c-127">This selection will affect the mapping fields you have access to in the next step.</span></span>

    > [!TIP]
    > <span data-ttu-id="9547c-128">Jo vairāk galveno identifikatoru atribūtu tiek nosūtīts Experian, jo augstāka iespēja iegūt augstāku atbilstības rādītāju.</span><span class="sxs-lookup"><span data-stu-id="9547c-128">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="9547c-129">Lai sāktu lauka kartēšanu, atlasiet **Tālāk**.</span><span class="sxs-lookup"><span data-stu-id="9547c-129">Select **Next** to start the field mapping.</span></span>

1. <span data-ttu-id="9547c-130">Definējiet, kura veida laukus no jūsu vienotajiem profiliem vajadzētu izmantot, meklējot atbilstošus demogrāfijas datus no Experian.</span><span class="sxs-lookup"><span data-stu-id="9547c-130">Define which fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="9547c-131">Obligātie lauki ir atzīmēti.</span><span class="sxs-lookup"><span data-stu-id="9547c-131">Required fields are marked.</span></span>

1. <span data-ttu-id="9547c-132">Norādiet bagātināto datu nosaukumu un izvades entitījas nosaukumu.</span><span class="sxs-lookup"><span data-stu-id="9547c-132">Provide a name for the enrichment and a name for the output entity.</span></span>

1. <span data-ttu-id="9547c-133">Pēc izvēļu pārskatīšanas atlasiet **Saglabāt vidi**.</span><span class="sxs-lookup"><span data-stu-id="9547c-133">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-experian"></a><span data-ttu-id="9547c-134">Experian savienojuma konfigurēšana</span><span class="sxs-lookup"><span data-stu-id="9547c-134">Configure the connection for Experian</span></span> 

<span data-ttu-id="9547c-135">Lai konfigurētu savienojumus, jums ir jābūt administratoram.</span><span class="sxs-lookup"><span data-stu-id="9547c-135">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="9547c-136">Konfigurējot bagātinātos datus, atlasiet **Pievienot savienojumu** *vai* dodieties uz **Administrators** > **Savienojumi** un Experian rūtī atlasiet **Iestatīt**.</span><span class="sxs-lookup"><span data-stu-id="9547c-136">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Experian tile.</span></span>

1. <span data-ttu-id="9547c-137">Atlasiet **Sākt**.</span><span class="sxs-lookup"><span data-stu-id="9547c-137">Select **Get Started**.</span></span>

1. <span data-ttu-id="9547c-138">Lodziņā **Parādāmais nosaukums** ievadiet savienojuma nosaukumu.</span><span class="sxs-lookup"><span data-stu-id="9547c-138">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="9547c-139">Ievadiet derīgu lietotāja ID, partijas ID un modeļa numuru no sava Experian Secure Transport konta.</span><span class="sxs-lookup"><span data-stu-id="9547c-139">Enter valid User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span>

1. <span data-ttu-id="9547c-140">Pārskatiet un sniedziet savu piekrišanu **Datu konfidencialitātei un atbilstībai**, atzīmējot izvēles rūtiņu **Piekrītu**</span><span class="sxs-lookup"><span data-stu-id="9547c-140">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox</span></span>

1. <span data-ttu-id="9547c-141">Lai pārbaudītu konfigurāciju, atlasiet **Pārbaudīt**.</span><span class="sxs-lookup"><span data-stu-id="9547c-141">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="9547c-142">Pēc pārbaudes pabeigšanas atlasiet **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="9547c-142">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Experian savienojuma konfigurācijas rūts.":::

## <a name="enrichment-results"></a><span data-ttu-id="9547c-144">Bagātināšanas rezultāti</span><span class="sxs-lookup"><span data-stu-id="9547c-144">Enrichment results</span></span>

<span data-ttu-id="9547c-145">Lai sāktu bagātināšanas procesu, komandjoslā atlasiet **Palaist**.</span><span class="sxs-lookup"><span data-stu-id="9547c-145">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="9547c-146">Varat arī ļaut sistēmai palaist bagātināšanu automātiski kā daļu no [plānotās atsvaidzināšanas](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="9547c-146">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="9547c-147">Apstrādes laiks būs atkarīgs no klientu datu izmēra un bagātināšanas procesiem, kurus jūsu kontam ir uzstādījis Experian.</span><span class="sxs-lookup"><span data-stu-id="9547c-147">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="9547c-148">Pēc bagātināšanas procesa noslēgšanas varat pārskatīt tikko bagātinātos klientu profilu datus, dodoties uz sadaļu **Mana bagātināšana**.</span><span class="sxs-lookup"><span data-stu-id="9547c-148">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="9547c-149">Turklāt jūs redzēsit pēdējā atjauninājuma laiku un bagātināto profilu skaitu.</span><span class="sxs-lookup"><span data-stu-id="9547c-149">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="9547c-150">Jūs varat piekļūt detalizētam katra bagātināta profila skatam, atlasot opciju **Skatīt bagātinātos datus**.</span><span class="sxs-lookup"><span data-stu-id="9547c-150">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="9547c-151">Nākamās darbības</span><span class="sxs-lookup"><span data-stu-id="9547c-151">Next steps</span></span>

<span data-ttu-id="9547c-152">Būvējiet virs saviem bagātinātajiem klientu datiem.</span><span class="sxs-lookup"><span data-stu-id="9547c-152">Build on top of your enriched customer data.</span></span> <span data-ttu-id="9547c-153">Veidojiet [segmentus](segments.md), [mērus](measures.md)un pat [eksportējiet datus](export-destinations.md), lai klientiem sniegtu personalizētas iespējas.</span><span class="sxs-lookup"><span data-stu-id="9547c-153">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="9547c-154">Datu konfidencialitāte un atbilstība</span><span class="sxs-lookup"><span data-stu-id="9547c-154">Data privacy and compliance</span></span>

<span data-ttu-id="9547c-155">Ja iespējojat Dynamics 365 Customer Insights datu pārsūtīšanu uz Experian, jūs atļaujat datu pārsūtīšanu ārpus atbilstības robežām Dynamics 365 Customer Insights, ieskaitot iespējami sensitīvus datus, piemēram, personas datus.</span><span class="sxs-lookup"><span data-stu-id="9547c-155">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="9547c-156">Microsoft šos datus pārsūtīs pēc jūsu norādēm, bet jūs esat atbildīgs par to, lai nodrošinātu Experian atbilstību konfidencialitātes vai drošības saistībām, kas jums varētu rasties.</span><span class="sxs-lookup"><span data-stu-id="9547c-156">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="9547c-157">Papildinformāciju skatiet rakstā [Microsoft Privātuma paziņojums](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="9547c-157">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="9547c-158">Jūsu Dynamics 365 Customer Insights administrators var noņemt šo bagātināšanas funkciju jebkurā laikā, lai pārtrauktu izmantot šo funkcionalitāti.</span><span class="sxs-lookup"><span data-stu-id="9547c-158">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
