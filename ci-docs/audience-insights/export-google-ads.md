---
title: Customer Insights datu eksportēšana uz Google Ads
description: Uzziniet, kā konfigurēt savienojumu un eksportēt uz Google Ads.
ms.date: 03/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 73f3257a3ae6e8423f45410546535df5e3b400ce
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976327"
---
# <a name="export-segments-to-google-ads-preview"></a><span data-ttu-id="64c04-103">Segmentu eksportēšana uz Google Ads (priekšskatījums)</span><span class="sxs-lookup"><span data-stu-id="64c04-103">Export segments to Google Ads (preview)</span></span>

<span data-ttu-id="64c04-104">Eksportējiet klientu profilu unificētos segmentus uz Google Ads auditorijas sarakstu un izmantojiet tos reklāmām pakalpojumā Google Search, Gmail, YouTube un Google Display Network.</span><span class="sxs-lookup"><span data-stu-id="64c04-104">Export segments of unified customer profiles to Google Ads audience list and use them to advertise on Google Search, Gmail, YouTube, and Google Display Network.</span></span> 

## <a name="prerequisites-for-connection"></a><span data-ttu-id="64c04-105">Savienojuma priekšnosacījumi</span><span class="sxs-lookup"><span data-stu-id="64c04-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="64c04-106">Jums ir [Google Ads konts](https://ads.google.com/) un atbilstošie administratora akreditācijas dati.</span><span class="sxs-lookup"><span data-stu-id="64c04-106">You have a [Google Ads account](https://ads.google.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="64c04-107">Jums ir [apstiprināts Google Ads izstrādātāja marķieris](https://developers.google.com/google-ads/api/docs/first-call/dev-token)</span><span class="sxs-lookup"><span data-stu-id="64c04-107">You have an [approved Google Ads Developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)</span></span> 
-   <span data-ttu-id="64c04-108">Jūs atbilstat [Klientu atbilstības politikas](https://support.google.com/adspolicy/answer/6299717) prasībām</span><span class="sxs-lookup"><span data-stu-id="64c04-108">You fulfill the requirements of the [Customer Match Policy](https://support.google.com/adspolicy/answer/6299717)</span></span>
-   <span data-ttu-id="64c04-109">Jūs atbilstat [atkārtota mārketinga saraksta izmēru](https://support.google.com/google-ads/answer/7558048) prasībām</span><span class="sxs-lookup"><span data-stu-id="64c04-109">You fulfill the requirements of the [remarketing list sizes](https://support.google.com/google-ads/answer/7558048)</span></span> 

-   <span data-ttu-id="64c04-110">Google Ads ir esošas auditorijas un attiecīgie ID.</span><span class="sxs-lookup"><span data-stu-id="64c04-110">There are existing audiences in Google Ads and the corresponding IDs.</span></span> <span data-ttu-id="64c04-111">Papildinformāciju skatiet rakstā [Google Ads auditorijas](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span><span class="sxs-lookup"><span data-stu-id="64c04-111">For more information, see [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span></span>
-   <span data-ttu-id="64c04-112">Jums ir [konfigurēti segmenti](segments.md)</span><span class="sxs-lookup"><span data-stu-id="64c04-112">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="64c04-113">Eksportētajos segmentos vienotajiem klientu profiliem ir lauki, kas norāda e-pasta adresi, vārdu un uzvārdu.</span><span class="sxs-lookup"><span data-stu-id="64c04-113">Unified customer profiles in the exported segments contain fields representing an email address, first name, and last name</span></span>

## <a name="known-limitations"></a><span data-ttu-id="64c04-114">Zināmie ierobežojumi</span><span class="sxs-lookup"><span data-stu-id="64c04-114">Known limitations</span></span>

- <span data-ttu-id="64c04-115">Līdz 1 000 000 profilu, eksportējot uz Google Ads.</span><span class="sxs-lookup"><span data-stu-id="64c04-115">Up to 1 million profiles per export to Google Ads.</span></span>
- <span data-ttu-id="64c04-116">Eksportēšana uz Google Ads ir ierobežota līdz segmentiem.</span><span class="sxs-lookup"><span data-stu-id="64c04-116">Exporting to Google Ads is limited to segments.</span></span>
- <span data-ttu-id="64c04-117">Segmentu eksportēšanai kopā ar 1 000 000 profilu var būt nepieciešamas 5 minūtes, jo pastāv ierobežojumi no pakalpojuma sniedzēja puses.</span><span class="sxs-lookup"><span data-stu-id="64c04-117">Exporting segments with a total of 1 million profiles can take up to 5 minutes because of limitations on the provider side.</span></span> 
- <span data-ttu-id="64c04-118">Google Ads savienošana var aizņemt līdz 48 stundām.</span><span class="sxs-lookup"><span data-stu-id="64c04-118">The matching in Google Ads can take up to 48 hours.</span></span>

## <a name="set-up-connection-to-google-ads"></a><span data-ttu-id="64c04-119">Savienojuma ar Google Ads iestatīšana</span><span class="sxs-lookup"><span data-stu-id="64c04-119">Set up connection to Google Ads</span></span>

1. <span data-ttu-id="64c04-120">Dodieties uz **Administrators** > **Savienojumi**.</span><span class="sxs-lookup"><span data-stu-id="64c04-120">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="64c04-121">Atlasiet vienumu **Pievienot savienojumu** un atlasiet **Google Ads**, lai konfigurētu savienojumu.</span><span class="sxs-lookup"><span data-stu-id="64c04-121">Select **Add connection** and choose **Google Ads** to configure the connection.</span></span>

1. <span data-ttu-id="64c04-122">Laukā **Parādāmais nosaukums** piešķiriet savienojumam atpazīstamu nosaukumu.</span><span class="sxs-lookup"><span data-stu-id="64c04-122">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="64c04-123">Parādāmais nosaukums un nosaukuma veids raksturo šo savienojumu.</span><span class="sxs-lookup"><span data-stu-id="64c04-123">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="64c04-124">Ir ieteicams izvēlēties nosaukumu, kas paskaidro savienojuma nolūku.</span><span class="sxs-lookup"><span data-stu-id="64c04-124">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="64c04-125">Izvēlieties, kurš var izmantot šo savienojumu.</span><span class="sxs-lookup"><span data-stu-id="64c04-125">Choose who can use this connection.</span></span> <span data-ttu-id="64c04-126">Ja nesāksit nekādas darbības, noklusējums būs Administratori.</span><span class="sxs-lookup"><span data-stu-id="64c04-126">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="64c04-127">Papildinformāciju skatiet rakstā [Atļaut līdzstrādniekiem izmantot savienojumu eksportam](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="64c04-127">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="64c04-128">Ievadiet savu **[Google Ads klienta ID](https://support.google.com/google-ads/answer/1704344)**.</span><span class="sxs-lookup"><span data-stu-id="64c04-128">Enter your **[Google Ads customer ID](https://support.google.com/google-ads/answer/1704344)**.</span></span>

1. <span data-ttu-id="64c04-129">Ievadiet savas **[Google Ads apstiprinātu izstrādātāja marķieri](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span><span class="sxs-lookup"><span data-stu-id="64c04-129">Enter your **[Google Ads approved developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span></span>

1. <span data-ttu-id="64c04-130">Atlasiet **Piekrītu**, lai apstiprinātu **Datu konfidencialitāti un atbilstību**.</span><span class="sxs-lookup"><span data-stu-id="64c04-130">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="64c04-131">Atlasiet **Autentificēties ar Google Ads** un sniedziet savus Google Ads akreditācijas datus.</span><span class="sxs-lookup"><span data-stu-id="64c04-131">Select **Authenticate with Google Ads** and provide your Google Ads credentials.</span></span>

1. <span data-ttu-id="64c04-132">Atlasiet opciju **Pievienot sevi kā eksporta lietotāju** un sniedziet savus Customer Insights akreditācijas datus.</span><span class="sxs-lookup"><span data-stu-id="64c04-132">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="64c04-133">Lai pabeigtu savienošanu, atlasiet **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="64c04-133">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="64c04-134">Eksporta konfigurēšana</span><span class="sxs-lookup"><span data-stu-id="64c04-134">Configure an export</span></span>

<span data-ttu-id="64c04-135">Šo eksportu varat konfigurēt, ja jums ir piekļuve šā veida pieslēgumam.</span><span class="sxs-lookup"><span data-stu-id="64c04-135">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="64c04-136">Papildinformāciju skatiet rakstā [Atļaujas, kas nepieciešamas eksporta konfigurēšanai](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="64c04-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="64c04-137">Pārejiet uz **Dati** > **Eksportēšana**.</span><span class="sxs-lookup"><span data-stu-id="64c04-137">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="64c04-138">Lai izveidotu jaunu eksportu, atlasiet **Pievienot galamērķi**.</span><span class="sxs-lookup"><span data-stu-id="64c04-138">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="64c04-139">Laukā **Savienošana eksportam** atlasiet savienojumu no sadaļas Google Ads.</span><span class="sxs-lookup"><span data-stu-id="64c04-139">In the **Connection for export** field, choose a connection from the Google Ads section.</span></span> <span data-ttu-id="64c04-140">Ja šis sadaļas nosaukums nav redzams, šāda veida savienojumi jums nav pieejami.</span><span class="sxs-lookup"><span data-stu-id="64c04-140">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="64c04-141">Ievadiet savas **[Google reklāmu auditorijas ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** un atlasiet opciju **Izveidot savienojumu**, lai inicializētu savienojumu ar Google Ads.</span><span class="sxs-lookup"><span data-stu-id="64c04-141">Enter your **[Google Ads audience ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** and select **Connect** to initialize the connection to Google Ads.</span></span>

1. <span data-ttu-id="64c04-142">Sadaļas **Datu atbilstības** laukā **E-pasts** atlasiet lauku, kas iekļauts vienotajā klientu profilā, kas pārstāv klienta e-pasta adresi.</span><span class="sxs-lookup"><span data-stu-id="64c04-142">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="64c04-143">Atkārtojiet šīs pašas darbības ar laukiem **Vārds** un **Uzvārds**.</span><span class="sxs-lookup"><span data-stu-id="64c04-143">Repeat the same steps for \*\*First name" and **Last name** fields.</span></span>

1. <span data-ttu-id="64c04-144">Atlasiet segmentus, kurus vēlaties eksportēt.</span><span class="sxs-lookup"><span data-stu-id="64c04-144">Select the segments you want to export.</span></span> <span data-ttu-id="64c04-145">Kopsummā varat eksportēt līdz 1 000 000 klientu profilu uz Google Ads.</span><span class="sxs-lookup"><span data-stu-id="64c04-145">You can export up to 1 million customer profiles in total to Google Ads.</span></span>

<span data-ttu-id="64c04-146">Eksporta saglabāšana automātiski nepalaiž eksportu.</span><span class="sxs-lookup"><span data-stu-id="64c04-146">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="64c04-147">Eksports tiek palaists ar katru [plānoto atsvaidzināšanu](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="64c04-147">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="64c04-148">Varat arī [eksportēt datus pēc pieprasījuma](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="64c04-148">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="64c04-149">Datu konfidencialitāte un atbilstība</span><span class="sxs-lookup"><span data-stu-id="64c04-149">Data privacy and compliance</span></span>

<span data-ttu-id="64c04-150">Ja iespējojat Dynamics 365 Customer Insights datu pārsūtīšanai uz Google Ads, jūs atļaujat datu pārsūtīšanu ārpus atbilstības robežām Dynamics 365 Customer Insights, ieskaitot iespējami sensitīvus datus, piemēram, personas datus.</span><span class="sxs-lookup"><span data-stu-id="64c04-150">When you enable Dynamics 365 Customer Insights to transmit data to Google Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="64c04-151">Microsoft šos datus pārsūtīs pēc jūsu norādēm, bet jūs esat atbildīgs par to, lai nodrošinātu Google Ads atbilstību konfidencialitātes vai drošības saistībām, kas jums varētu rasties.</span><span class="sxs-lookup"><span data-stu-id="64c04-151">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Google Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="64c04-152">Papildinformāciju skatiet rakstā [Microsoft Privātuma paziņojums](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="64c04-152">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="64c04-153">Jūsu Dynamics 365 Customer Insights administrators var noņemt šo eksportēšanas galamērķi jebkurā laikā, lai pārtrauktu izmantot šo funkcionalitāti.</span><span class="sxs-lookup"><span data-stu-id="64c04-153">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
