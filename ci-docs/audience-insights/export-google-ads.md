---
title: Customer Insights datu eksportēšana uz Google Ads
description: Uzziniet, kā konfigurēt savienojumu ar Google Ads.
ms.date: 11/18/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6d9a25af3913e755cccec745c532b35aef3cccf9
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598256"
---
# <a name="connector-for-google-ads-preview"></a><span data-ttu-id="9b170-103">Google Ads savienotājs (priekšskatījums)</span><span class="sxs-lookup"><span data-stu-id="9b170-103">Connector for Google Ads (preview)</span></span>

<span data-ttu-id="9b170-104">Eksportējiet klientu profilu unificētos segmentus uz Google Ads auditorijas sarakstu un izmantojiet tos reklāmām pakalpojumā Google Search, Gmail, YouTube un Google Display Network.</span><span class="sxs-lookup"><span data-stu-id="9b170-104">Export segments of unified customer profiles to Google Ads audience list and use them to advertise on Google Search, Gmail, YouTube, and Google Display Network.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="9b170-105">Priekšnosacījumi</span><span class="sxs-lookup"><span data-stu-id="9b170-105">Prerequisites</span></span>

-   <span data-ttu-id="9b170-106">Jums ir [Google Ads konts](https://ads.google.com/) un atbilstošie administratora akreditācijas dati.</span><span class="sxs-lookup"><span data-stu-id="9b170-106">You have a [Google Ads account](https://ads.google.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="9b170-107">Google Ads ir esošas auditorijas un attiecīgie ID.</span><span class="sxs-lookup"><span data-stu-id="9b170-107">There are existing audiences in Google Ads and the corresponding IDs.</span></span> <span data-ttu-id="9b170-108">Papildinformāciju skatiet rakstā [Google Ads auditorijas](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span><span class="sxs-lookup"><span data-stu-id="9b170-108">For more information, see [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span></span>
-   <span data-ttu-id="9b170-109">Jums ir [konfigurēti segmenti](segments.md)</span><span class="sxs-lookup"><span data-stu-id="9b170-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="9b170-110">Eksportētajos segmentos vienotajiem klientu profiliem ir lauki, kas norāda e-pasta adresi, vārdu un uzvārdu.</span><span class="sxs-lookup"><span data-stu-id="9b170-110">Unified customer profiles in the exported segments contain fields representing an email address, first name, and last name</span></span>

## <a name="connect-to-google-ads"></a><span data-ttu-id="9b170-111">Izveidot savienojumu ar Google Ads</span><span class="sxs-lookup"><span data-stu-id="9b170-111">Connect to Google Ads</span></span>

1. <span data-ttu-id="9b170-112">Dodieties uz sadaļu **Administrators** > **Eksportēšanas galamērķi**.</span><span class="sxs-lookup"><span data-stu-id="9b170-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="9b170-113">Sadaļā **Google Ads** atlasiet **Iestatīt**.</span><span class="sxs-lookup"><span data-stu-id="9b170-113">Under **Google Ads**, select **Set up**.</span></span>

1. <span data-ttu-id="9b170-114">Piešķiriet eksportēšanas galamērķim atpazīstamu nosaukumu laukā **Parādāmais nosaukums**.</span><span class="sxs-lookup"><span data-stu-id="9b170-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="9b170-115">Ievadiet savu **[Google Ads klienta ID](https://support.google.com/google-ads/answer/1704344)**.</span><span class="sxs-lookup"><span data-stu-id="9b170-115">Enter your **[Google Ads customer ID](https://support.google.com/google-ads/answer/1704344)**.</span></span>

1. <span data-ttu-id="9b170-116">Ievadiet savas **[Google Ads apstiprinātu izstrādātāja marķieri](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span><span class="sxs-lookup"><span data-stu-id="9b170-116">Enter your **[Google Ads approved developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span></span>

1. <span data-ttu-id="9b170-117">Atlasiet **Piekrītu**, lai apstiprinātu **Datu privātumu un atbilstību**.</span><span class="sxs-lookup"><span data-stu-id="9b170-117">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="9b170-118">Ievadiet savas **[Google reklāmu auditorijas ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** un atlasiet opciju **Izveidot savienojumu**, lai inicializētu savienojumu ar Google Ads.</span><span class="sxs-lookup"><span data-stu-id="9b170-118">Enter your **[Google Ads audience ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** and select **Connect** to initialize the connection to Google Ads.</span></span>

1. <span data-ttu-id="9b170-119">Atlasiet **Autentificēties ar Google Ads** un sniedziet savus Google Ads akreditācijas datus.</span><span class="sxs-lookup"><span data-stu-id="9b170-119">Select **Authenticate with Google Ads** and provide your Google Ads credentials.</span></span>

1. <span data-ttu-id="9b170-120">Atlasiet opciju **Pievienot sevi kā eksporta lietotāju** un sniedziet savus Customer Insights akreditācijas datus.</span><span class="sxs-lookup"><span data-stu-id="9b170-120">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-segments-googleads.PNG" alt-text="Eksportēt ekrānuzņēmumu Google Ads savienojumā":::

1. <span data-ttu-id="9b170-122">Lai konfigurētu eksportēšanu, atlasiet **Tālāk**.</span><span class="sxs-lookup"><span data-stu-id="9b170-122">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="9b170-123">Savienotāja konfigurēšana</span><span class="sxs-lookup"><span data-stu-id="9b170-123">Configure the connector</span></span>

1. <span data-ttu-id="9b170-124">Sadaļas **Datu atbilstības** laukā **E-pasts** atlasiet lauku, kas iekļauts vienotajā klientu profilā, kas pārstāv klienta e-pasta adresi.</span><span class="sxs-lookup"><span data-stu-id="9b170-124">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="9b170-125">Atkārtojiet šīs pašas darbības ar laukiem **Vārds** un **Uzvārds**.</span><span class="sxs-lookup"><span data-stu-id="9b170-125">Repeat the same steps for \*\*First name" and **Last name** fields.</span></span>

1. <span data-ttu-id="9b170-126">Atlasiet segmentus, kurus vēlaties eksportēt.</span><span class="sxs-lookup"><span data-stu-id="9b170-126">Select the segments you want to export.</span></span> <span data-ttu-id="9b170-127">Kopsummā varat eksportēt līdz 1 000 000 klientu profilu uz Google Ads.</span><span class="sxs-lookup"><span data-stu-id="9b170-127">You can export up to 1 million customer profiles in total to Google Ads.</span></span>

1. <span data-ttu-id="9b170-128">Atlasiet vienumu **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="9b170-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="9b170-129">Datu eksportēšana</span><span class="sxs-lookup"><span data-stu-id="9b170-129">Export the data</span></span>

<span data-ttu-id="9b170-130">Datus var [eksportēt pēc pieprasījuma](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="9b170-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="9b170-131">Eksportēšana arī tiks palaista ar katru [plānoto atsvaidzināšanu](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="9b170-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="9b170-132">Google Ads tagad varat atrast jūsu segmentus sadaļā [Google Ads auditorija](https://support.google.com/google-ads/answer/7558048?hl=en/).</span><span class="sxs-lookup"><span data-stu-id="9b170-132">In Google Ads, you can now find your segments under [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en/).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="9b170-133">Zināmie ierobežojumi</span><span class="sxs-lookup"><span data-stu-id="9b170-133">Known limitations</span></span>

- <span data-ttu-id="9b170-134">Līdz 1 000 000 profilu, eksportējot uz Google Ads.</span><span class="sxs-lookup"><span data-stu-id="9b170-134">Up to 1 million profiles per export to Google Ads.</span></span>
- <span data-ttu-id="9b170-135">Eksportēšana uz Google Ads ir ierobežota līdz segmentiem.</span><span class="sxs-lookup"><span data-stu-id="9b170-135">Exporting to Google Ads is limited to segments.</span></span>
- <span data-ttu-id="9b170-136">Segmentu eksportēšanai kopā ar 1 000 000 profilu var būt nepieciešamas 5 minūtes, jo pastāv ierobežojumi no pakalpojuma sniedzēja puses.</span><span class="sxs-lookup"><span data-stu-id="9b170-136">Exporting segments with a total of 1 million profiles can take up to 5 minutes because of limitations on the provider side.</span></span> 
- <span data-ttu-id="9b170-137">Google Ads savienošana var aizņemt līdz 48 stundām.</span><span class="sxs-lookup"><span data-stu-id="9b170-137">The matching in Google Ads can take up to 48 hours.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="9b170-138">Datu konfidencialitāte un atbilstība</span><span class="sxs-lookup"><span data-stu-id="9b170-138">Data privacy and compliance</span></span>

<span data-ttu-id="9b170-139">Ja iespējojat Dynamics 365 Customer Insights datu pārsūtīšanai uz Google Ads, jūs atļaujat datu pārsūtīšanu ārpus atbilstības robežām Dynamics 365 Customer Insights, ieskaitot iespējami sensitīvus datus, piemēram, personas datus.</span><span class="sxs-lookup"><span data-stu-id="9b170-139">When you enable Dynamics 365 Customer Insights to transmit data to Google Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="9b170-140">Microsoft šos datus pārsūtīs pēc jūsu norādēm, bet jūs esat atbildīgs par to, lai nodrošinātu Google Ads atbilstību konfidencialitātes vai drošības saistībām, kas jums varētu rasties.</span><span class="sxs-lookup"><span data-stu-id="9b170-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Google Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="9b170-141">Papildinformāciju skatiet rakstā [Microsoft Privātuma paziņojums](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="9b170-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="9b170-142">Jūsu Dynamics 365 Customer Insights administrators var noņemt šo eksportēšanas galamērķi jebkurā laikā, lai pārtrauktu izmantot šo funkcionalitāti.</span><span class="sxs-lookup"><span data-stu-id="9b170-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]