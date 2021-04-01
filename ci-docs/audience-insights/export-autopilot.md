---
title: Customer Insights datu eksportēšana uz Autopilot
description: Uzziniet, kā konfigurēt savienojumu ar Autopilot.
ms.date: 12/08/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6d039c4afd84eaad942d214d4e6fb8ef7b1ec72a
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596140"
---
# <a name="connector-for-autopilot-preview"></a><span data-ttu-id="5eebe-103">Savienotājs ar Autopilot (priekšskatījums)</span><span class="sxs-lookup"><span data-stu-id="5eebe-103">Connector for Autopilot (preview)</span></span>

<span data-ttu-id="5eebe-104">Eksportējiet vienoto klientu profilu segmentus uz Autopilot un izmantojiet tos e-pasta mārketingam lietojumprogrammā Autopilot.</span><span class="sxs-lookup"><span data-stu-id="5eebe-104">Export segments of unified customer profiles to Autopilot and use them for email marketing in Autopilot.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="5eebe-105">Priekšnosacījumi</span><span class="sxs-lookup"><span data-stu-id="5eebe-105">Prerequisites</span></span>

-   <span data-ttu-id="5eebe-106">Jums ir [Autopilot konts](https://www.autopilothq.com/) un atbilstošie administratora akreditācijas dati.</span><span class="sxs-lookup"><span data-stu-id="5eebe-106">You have an [Autopilot account](https://www.autopilothq.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="5eebe-107">Jums ir [konfigurēti segmenti](segments.md) auditorijas ieskatos.</span><span class="sxs-lookup"><span data-stu-id="5eebe-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="5eebe-108">Eksportētajos segmentos vienotajiem klientu profiliem ir lauks, kas norāda e-pasta adresi.</span><span class="sxs-lookup"><span data-stu-id="5eebe-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-autopilot"></a><span data-ttu-id="5eebe-109">Izveidot savienojumu ar Autopilot</span><span class="sxs-lookup"><span data-stu-id="5eebe-109">Connect to Autopilot</span></span>

1. <span data-ttu-id="5eebe-110">Dodieties uz sadaļu **Administrators** > **Eksportēšanas galamērķi**.</span><span class="sxs-lookup"><span data-stu-id="5eebe-110">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="5eebe-111">Sadaļā **Autopilot** atlasiet vienumu **Iestatīt**.</span><span class="sxs-lookup"><span data-stu-id="5eebe-111">Under **Autopilot**, select **Set up**.</span></span>

1. <span data-ttu-id="5eebe-112">Piešķiriet eksportēšanas galamērķim atpazīstamu nosaukumu laukā **Parādāmais nosaukums**.</span><span class="sxs-lookup"><span data-stu-id="5eebe-112">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/export-autopilot.PNG" alt-text="Konfigurēšanas rūts Autopilot savienojumam.":::

1. <span data-ttu-id="5eebe-114">Ievadiet savu **Autopilot API atslēgu** [Autopilot API atslēga](https://autopilot.docs.apiary.io/#).</span><span class="sxs-lookup"><span data-stu-id="5eebe-114">Enter your **Autopilot API key** [Autopilot API key](https://autopilot.docs.apiary.io/#).</span></span>

1. <span data-ttu-id="5eebe-115">Atlasiet **Piekrītu**, lai apstiprinātu **Datu konfidencialitāti un atbilstību**.</span><span class="sxs-lookup"><span data-stu-id="5eebe-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="5eebe-116">Atlasiet **Izveidot savienojumu**, lai inicializētu savienojumu ar Autopilot.</span><span class="sxs-lookup"><span data-stu-id="5eebe-116">Select **Connect** to initialize the connection to Autopilot.</span></span>

1. <span data-ttu-id="5eebe-117">Atlasiet opciju **Pievienot sevi kā eksporta lietotāju** un sniedziet savus Customer Insights akreditācijas datus.</span><span class="sxs-lookup"><span data-stu-id="5eebe-117">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="5eebe-118">Lai konfigurētu eksportēšanu, atlasiet **Tālāk**.</span><span class="sxs-lookup"><span data-stu-id="5eebe-118">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="5eebe-119">Savienotāja konfigurēšana</span><span class="sxs-lookup"><span data-stu-id="5eebe-119">Configure the connector</span></span>

1. <span data-ttu-id="5eebe-120">Sadaļas **Datu atbilstības** laukā **E-pasts** atlasiet lauku, kas iekļauts vienotajā klientu profilā, kas pārstāv klienta e-pasta adresi.</span><span class="sxs-lookup"><span data-stu-id="5eebe-120">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="5eebe-121">Veiciet tās pašas darbības ar citiem neobligātajiem laukiem, piemēram, **Vārds**, **Uzvārds**.</span><span class="sxs-lookup"><span data-stu-id="5eebe-121">Repeat the same steps for other optional fields such as **First name**, **Last name**.</span></span>

1. <span data-ttu-id="5eebe-122">Atlasiet segmentus, kurus vēlaties eksportēt.</span><span class="sxs-lookup"><span data-stu-id="5eebe-122">Select the segments you want to export.</span></span> <span data-ttu-id="5eebe-123">Mēs **stingri iesakām eksportēt kopumā ne vairāk kā 100 000 klientu profilu** programmā Autopilot.</span><span class="sxs-lookup"><span data-stu-id="5eebe-123">We strongly **recommend to not export more than 100'000 customer profiles in total** to Autopilot.</span></span> 

1. <span data-ttu-id="5eebe-124">Atlasiet vienumu **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="5eebe-124">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="5eebe-125">Datu eksportēšana</span><span class="sxs-lookup"><span data-stu-id="5eebe-125">Export the data</span></span>

<span data-ttu-id="5eebe-126">Datus var [eksportēt pēc pieprasījuma](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="5eebe-126">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="5eebe-127">Eksportēšana arī tiks palaista ar katru [plānoto atsvaidzināšanu](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="5eebe-127">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="5eebe-128">Zināmie ierobežojumi</span><span class="sxs-lookup"><span data-stu-id="5eebe-128">Known limitations</span></span>

- <span data-ttu-id="5eebe-129">Kopsummā var eksportēt līdz 100 000 profilu uz Autopilot.</span><span class="sxs-lookup"><span data-stu-id="5eebe-129">You can export up to 100'000 profiles in total to Autopilot.</span></span>
- <span data-ttu-id="5eebe-130">Eksportēšana uz Autopilot ir ierobežota līdz segmentiem.</span><span class="sxs-lookup"><span data-stu-id="5eebe-130">Exporting to Autopilot is limited to segments.</span></span>
- <span data-ttu-id="5eebe-131">100 000 profilu eksportēšana uz Autopilot var aizņemt dažas stundas.</span><span class="sxs-lookup"><span data-stu-id="5eebe-131">Exporting up to 100'000 profiles to Autopilot can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="5eebe-132">To profilu skaits, ko var eksportēt uz Autopilot, ir atkarīgs, un tas ir ierobežots jūsu līgumā ar Autopilot.</span><span class="sxs-lookup"><span data-stu-id="5eebe-132">The number of profiles that you can export to Autopilot is dependent and limited on your contract with Autopilot.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="5eebe-133">Datu konfidencialitāte un atbilstība</span><span class="sxs-lookup"><span data-stu-id="5eebe-133">Data privacy and compliance</span></span>

<span data-ttu-id="5eebe-134">Ja iespējojat Dynamics 365 Customer Insights datu pārsūtīšanu uz Autopilot, jūs atļaujat datu pārsūtīšanu ārpus atbilstības robežām Dynamics 365 Customer Insights, ieskaitot iespējami sensitīvus datus, piemēram, personas datus.</span><span class="sxs-lookup"><span data-stu-id="5eebe-134">When you enable Dynamics 365 Customer Insights to transmit data to Autopilot, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="5eebe-135">Microsoft šos datus pārsūtīs pēc jūsu norādēm, bet jūs esat atbildīgs par to, lai nodrošinātu Autopilot atbilstību konfidencialitātes vai drošības saistībām, kas jums varētu rasties.</span><span class="sxs-lookup"><span data-stu-id="5eebe-135">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Autopilot meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="5eebe-136">Papildinformāciju skatiet rakstā [Microsoft Privātuma paziņojums](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="5eebe-136">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="5eebe-137">Jūsu Dynamics 365 Customer Insights administrators var noņemt šo eksportēšanas galamērķi jebkurā laikā, lai pārtrauktu izmantot šo funkcionalitāti.</span><span class="sxs-lookup"><span data-stu-id="5eebe-137">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]