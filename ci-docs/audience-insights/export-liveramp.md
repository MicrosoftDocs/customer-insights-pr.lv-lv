---
title: LiveRamp savienotājs
description: Uzziniet, kā konfigurēt savienojumu un eksportēt uz LiveRamp.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 987457966fe1fc034d9e3cd2a1ce33902c7a84f4
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760336"
---
# <a name="export-segments-to-liverampreg-preview"></a><span data-ttu-id="dc371-103">Segmentu eksportēšana uz LiveRamp&reg; (priekšskatījums)</span><span class="sxs-lookup"><span data-stu-id="dc371-103">Export segments to LiveRamp&reg; (preview)</span></span>

<span data-ttu-id="dc371-104">Aktivizējiet savus datus LiveRamp, lai savienotos ar vairāk nekā 500 digitālajām, sociālajām un TV platformām.</span><span class="sxs-lookup"><span data-stu-id="dc371-104">Activate your data in LiveRamp to connect with over 500 platforms across digital, social, and TVs.</span></span> <span data-ttu-id="dc371-105">Strādājiet ar saviem datiem risinājumā LiveRamp, lai mērķētu, izlaistu un personalizētu reklāmas kampaņas.</span><span class="sxs-lookup"><span data-stu-id="dc371-105">Work with your data in LiveRamp to target, suppress, and personalize ad campaigns.</span></span>

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="dc371-106">Savienojuma priekšnosacījumi</span><span class="sxs-lookup"><span data-stu-id="dc371-106">Prerequisites for a connection</span></span>

- <span data-ttu-id="dc371-107">Lai izmantotu šo savienotāju, ir nepieciešams LiveRamp abonements.</span><span class="sxs-lookup"><span data-stu-id="dc371-107">You need a LiveRamp subscription to use this connector.</span></span>
- <span data-ttu-id="dc371-108">Lai iegūtu abonementu, [sazinieties tieši ar LiveRamp](https://liveramp.com/contact/).</span><span class="sxs-lookup"><span data-stu-id="dc371-108">To get a subscription, [contact LiveRamp](https://liveramp.com/contact/) directly.</span></span> <span data-ttu-id="dc371-109">[Uzzināt vairāk par LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span><span class="sxs-lookup"><span data-stu-id="dc371-109">[Learn more about LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span></span>

## <a name="set-up-connection-to-liveramp"></a><span data-ttu-id="dc371-110">Savienojuma ar LiveRamp iestatīšana</span><span class="sxs-lookup"><span data-stu-id="dc371-110">Set up connection to LiveRamp</span></span>

1. <span data-ttu-id="dc371-111">Dodieties uz **Administrators** > **Savienojumi**.</span><span class="sxs-lookup"><span data-stu-id="dc371-111">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="dc371-112">Atlasiet vienumu **Pievienot savienojumu** un atlasiet **LiveRamp**, lai konfigurētu savienojumu.</span><span class="sxs-lookup"><span data-stu-id="dc371-112">Select **Add connection** and choose **LiveRamp** to configure the connection.</span></span>

1. <span data-ttu-id="dc371-113">Laukā **Parādāmais nosaukums** piešķiriet savienojumam atpazīstamu nosaukumu.</span><span class="sxs-lookup"><span data-stu-id="dc371-113">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="dc371-114">Parādāmais nosaukums un nosaukuma veids raksturo šo savienojumu.</span><span class="sxs-lookup"><span data-stu-id="dc371-114">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="dc371-115">Ir ieteicams izvēlēties nosaukumu, kas paskaidro savienojuma nolūku.</span><span class="sxs-lookup"><span data-stu-id="dc371-115">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="dc371-116">Izvēlieties, kurš var izmantot šo savienojumu.</span><span class="sxs-lookup"><span data-stu-id="dc371-116">Choose who can use this connection.</span></span> <span data-ttu-id="dc371-117">Ja nesāksit nekādas darbības, noklusējums būs Administratori.</span><span class="sxs-lookup"><span data-stu-id="dc371-117">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="dc371-118">Papildinformāciju skatiet rakstā [Atļaut līdzstrādniekiem izmantot savienojumu eksportam](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="dc371-118">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="dc371-119">Norādiet **Lietotājvārds** un **Parole** savam LiveRamp Drošajam FTP (SFTP) kontam.</span><span class="sxs-lookup"><span data-stu-id="dc371-119">Provide a **Username** and **Password** for your LiveRamp Secure FTP (SFTP) account.</span></span>
<span data-ttu-id="dc371-120">Šie akreditācijas dati var atšķirties no jūsu LiveRamp Onboarding akreditācijas datiem.</span><span class="sxs-lookup"><span data-stu-id="dc371-120">These credentials may be different from your LiveRamp Onboarding credentials.</span></span>

1. <span data-ttu-id="dc371-121">Atlasiet **Pārbaudīt**, lai pārbaudītu savienojumu ar LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="dc371-121">Select **Verify** to test the connection to LiveRamp.</span></span>

1. <span data-ttu-id="dc371-122">Pēc sekmīgas verifikācijas sniedziet savu piekrišanu **Datu konfidencialitātei un atbilstībai**, atzīmējot izvēles rūtiņu **Piekrītu**.</span><span class="sxs-lookup"><span data-stu-id="dc371-122">After successful verification, provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="dc371-123">Lai pabeigtu savienošanu, atlasiet **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="dc371-123">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="dc371-124">Eksporta konfigurēšana</span><span class="sxs-lookup"><span data-stu-id="dc371-124">Configure an export</span></span>

<span data-ttu-id="dc371-125">Šo eksportu varat konfigurēt, ja jums ir piekļuve šā veida pieslēgumam.</span><span class="sxs-lookup"><span data-stu-id="dc371-125">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="dc371-126">Papildinformāciju skatiet rakstā [Atļaujas, kas nepieciešamas eksporta konfigurēšanai](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="dc371-126">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="dc371-127">Pārejiet uz **Dati** > **Eksportēšana**.</span><span class="sxs-lookup"><span data-stu-id="dc371-127">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="dc371-128">Lai izveidotu jaunu eksportu, atlasiet **Pievienot galamērķi**.</span><span class="sxs-lookup"><span data-stu-id="dc371-128">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="dc371-129">Laukā **Savienošana eksportam** atlasiet savienojumu no sadaļas LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="dc371-129">In the **Connection for export** field, choose a connection from the LiveRamp section.</span></span> <span data-ttu-id="dc371-130">Ja šis sadaļas nosaukums nav redzams, šāda veida savienojumi jums nav pieejami.</span><span class="sxs-lookup"><span data-stu-id="dc371-130">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="dc371-131">Laukā **Izvēlēties galveno identifikatoru** atlasiet **E-pasts**, **Vārds un adrese** vai **Tālrunis**, kas tiks nosūtīts uz LiveRamp identitātes atrisināšanai.</span><span class="sxs-lookup"><span data-stu-id="dc371-131">In the **Choose your key identifier** field, select **Email**,  **Name and address**, or **Phone** to send to LiveRamp for identity resolution.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="dc371-132">![LiveRamp savienotājs ar atribūtu kartējumu](media/export-liveramp-segments.png "LiveRamp savienotājs ar atribūtu kartējumu")</span><span class="sxs-lookup"><span data-stu-id="dc371-132">![LiveRamp connector with attribute mapping](media/export-liveramp-segments.png "LiveRamp connector with attribute mapping")</span></span>

1. <span data-ttu-id="dc371-133">Kartējiet atbilstošos atribūtus no savas vienotās klienta entītijas atlasītajam galvenajam identifikatoram.</span><span class="sxs-lookup"><span data-stu-id="dc371-133">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>

1. <span data-ttu-id="dc371-134">Atlasiet **Pievienot atribūtu**, lai kartētu vairāk atribūtu, ko nosūtīt uz LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="dc371-134">Select **Add attribute** to map more attributes to send to LiveRamp.</span></span>

   > [!TIP]
   > <span data-ttu-id="dc371-135">Vairāku galveno identifikatora atribūtu nosūtīšana uz LiveRamp, visticamāk, iegūs lielāku atbilstību.</span><span class="sxs-lookup"><span data-stu-id="dc371-135">Sending more key identifier attributes to LiveRamp is likely to get you a higher match rate.</span></span>

1. <span data-ttu-id="dc371-136">Atlasiet segmentus, kurus vēlaties eksportēt uz LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="dc371-136">Select the segments you want to export to LiveRamp.</span></span>

1. <span data-ttu-id="dc371-137">Atlasiet vienumu **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="dc371-137">Select **Save**.</span></span>

<span data-ttu-id="dc371-138">Eksporta saglabāšana automātiski nepalaiž eksportu.</span><span class="sxs-lookup"><span data-stu-id="dc371-138">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="dc371-139">Eksports tiek palaists ar katru [plānoto atsvaidzināšanu](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="dc371-139">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="dc371-140">Varat arī [eksportēt datus pēc pieprasījuma](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="dc371-140">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="dc371-141">Datu konfidencialitāte un atbilstība</span><span class="sxs-lookup"><span data-stu-id="dc371-141">Data privacy and compliance</span></span>

<span data-ttu-id="dc371-142">Ja iespējojat Dynamics 365 Customer Insights datu pārsūtīšanu uz Liveramp, jūs atļaujat datu pārsūtīšanu ārpus atbilstības robežām Dynamics 365 Customer Insights, ieskaitot iespējami sensitīvus datus, piemēram, personas datus.</span><span class="sxs-lookup"><span data-stu-id="dc371-142">When you enable Dynamics 365 Customer Insights to transmit data to Liveramp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="dc371-143">Microsoft šos datus pārsūtīs pēc jūsu norādēm, bet jūs esat atbildīgs par to, lai nodrošinātu Liveramp atbilstību konfidencialitātes vai drošības saistībām, kas jums varētu rasties.</span><span class="sxs-lookup"><span data-stu-id="dc371-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Liveramp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="dc371-144">Papildinformāciju skatiet rakstā [Microsoft Privātuma paziņojums](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="dc371-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="dc371-145">Jūsu Dynamics 365 Customer Insights administrators var noņemt šo eksportēšanas galamērķi jebkurā laikā, lai pārtrauktu izmantot šo funkcionalitāti.</span><span class="sxs-lookup"><span data-stu-id="dc371-145">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
