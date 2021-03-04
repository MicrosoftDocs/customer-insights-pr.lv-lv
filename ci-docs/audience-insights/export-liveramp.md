---
title: LiveRamp savienotājs
description: Uzziniet, kā eksportēt datus LiveRamp.
ms.date: 12/02/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 64d781f52e8124fc3e83a7b84f468830c5249cfd
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270167"
---
# <a name="liverampreg-connector-preview"></a><span data-ttu-id="88597-103">LiveRamp&reg; savienotājs (priekšskatījums)</span><span class="sxs-lookup"><span data-stu-id="88597-103">LiveRamp&reg; connector (preview)</span></span>

<span data-ttu-id="88597-104">Aktivizējiet datus risinājumā LiveRamp, lai izveidotu savienojumu ar vairāk nekā 500 platformām digitālajās, sociālajās un TV ekosistēmās.</span><span class="sxs-lookup"><span data-stu-id="88597-104">Activate your data in LiveRamp to connect with over 500 platforms across digital, social, and TV ecosystems.</span></span> <span data-ttu-id="88597-105">Strādājiet ar saviem datiem risinājumā LiveRamp, lai mērķētu, izlaistu un personalizētu reklāmas kampaņas.</span><span class="sxs-lookup"><span data-stu-id="88597-105">Work with your data in LiveRamp to target, suppress, and personalize ad campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="88597-106">Priekšnosacījumi</span><span class="sxs-lookup"><span data-stu-id="88597-106">Prerequisites</span></span>

- <span data-ttu-id="88597-107">Lai izmantotu šo savienotāju, ir nepieciešams LiveRamp abonements.</span><span class="sxs-lookup"><span data-stu-id="88597-107">You need a LiveRamp subscription to use this connector.</span></span>
- <span data-ttu-id="88597-108">Lai iegūtu abonementu, [sazinieties tieši ar LiveRamp](https://liveramp.com/contact/).</span><span class="sxs-lookup"><span data-stu-id="88597-108">To get a subscription, [contact LiveRamp](https://liveramp.com/contact/) directly.</span></span> <span data-ttu-id="88597-109">[Uzzināt vairāk par LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span><span class="sxs-lookup"><span data-stu-id="88597-109">[Learn more about LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span></span>

## <a name="connect-to-liveramp"></a><span data-ttu-id="88597-110">Savienojums ar LiveRamp</span><span class="sxs-lookup"><span data-stu-id="88597-110">Connect to LiveRamp</span></span>

1. <span data-ttu-id="88597-111">Sadaļā Auditorijas ieskati ejiet uz **Administrators** > **Eksportēšanas galamērķi**.</span><span class="sxs-lookup"><span data-stu-id="88597-111">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="88597-112">**LiveRamp** elementā atlasiet **Iestatīt**.</span><span class="sxs-lookup"><span data-stu-id="88597-112">In the **LiveRamp** tile, select **Set up**.</span></span>

1. <span data-ttu-id="88597-113">Laukā **Parādāmais nosaukums** piešķiriet galamērķim atpazīstamu nosaukumu.</span><span class="sxs-lookup"><span data-stu-id="88597-113">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="88597-114">Norādiet **Lietotājvārds** un **Parole** savam LiveRamp Drošajam FTP (SFTP) kontam.</span><span class="sxs-lookup"><span data-stu-id="88597-114">Provide a **Username** and **Password** for your LiveRamp Secure FTP (SFTP) account.</span></span>
<span data-ttu-id="88597-115">Šie akreditācijas dati var atšķirties no jūsu LiveRamp Onboarding akreditācijas datiem.</span><span class="sxs-lookup"><span data-stu-id="88597-115">These credentials may be different from your LiveRamp Onboarding credentials.</span></span>

1. <span data-ttu-id="88597-116">Atlasiet **Pārbaudīt**, lai pārbaudītu savienojumu ar LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="88597-116">Select **Verify** to test the connection to LiveRamp.</span></span>

1. <span data-ttu-id="88597-117">Pēc sekmīgas verifikācijas sniedziet savu piekrišanu **Datu konfidencialitātei un atbilstībai**, atzīmējot izvēles rūtiņu **Piekrītu**.</span><span class="sxs-lookup"><span data-stu-id="88597-117">After successful verification, provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="88597-118">Atlasiet **Tālāk**, lai iestatītu LiveRamp savienotāju.</span><span class="sxs-lookup"><span data-stu-id="88597-118">Select **Next** to set up the LiveRamp connector.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="88597-119">Savienotāja konfigurēšana</span><span class="sxs-lookup"><span data-stu-id="88597-119">Configure the connector</span></span>

1. <span data-ttu-id="88597-120">Laukā **Izvēlēties galveno identifikatoru** atlasiet **E-pasts**, **Vārds un adrese** vai **Tālrunis**, kas tiks nosūtīts uz LiveRamp identitātes atrisināšanai.</span><span class="sxs-lookup"><span data-stu-id="88597-120">In the **Choose your key identifier** field, select **Email**,  **Name and address**, or **Phone** to send to LiveRamp for identity resolution.</span></span>

1. <span data-ttu-id="88597-121">Kartējiet atbilstošos atribūtus no savas vienotās klienta entītijas atlasītajam galvenajam identifikatoram.</span><span class="sxs-lookup"><span data-stu-id="88597-121">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>

1. <span data-ttu-id="88597-122">Atlasiet **Pievienot atribūtu**, lai kartētu papildu atribūtus nosūtīšanai uz LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="88597-122">Select **Add attribute** to map additional attributes to send to LiveRamp.</span></span>

   > [!TIP]
   > <span data-ttu-id="88597-123">Vairāku galveno identifikatora atribūtu nosūtīšana uz LiveRamp, visticamāk, iegūs lielāku atbilstību.</span><span class="sxs-lookup"><span data-stu-id="88597-123">Sending more key identifier attributes to LiveRamp is likely to get you a higher match rate.</span></span>

1. <span data-ttu-id="88597-124">Atlasiet segmentus, kurus vēlaties eksportēt uz LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="88597-124">Select the segments you want to export to LiveRamp.</span></span>

1. <span data-ttu-id="88597-125">Atlasiet vienumu **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="88597-125">Select **Save**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="88597-126">![LiveRamp savienotājs ar atribūtu kartējumu](media/export-liveramp-segments.png "LiveRamp savienotājs ar atribūtu kartējumu")</span><span class="sxs-lookup"><span data-stu-id="88597-126">![LiveRamp connector with attribute mapping](media/export-liveramp-segments.png "LiveRamp connector with attribute mapping")</span></span>

## <a name="export-the-data"></a><span data-ttu-id="88597-127">Datu eksportēšana</span><span class="sxs-lookup"><span data-stu-id="88597-127">Export the data</span></span>

<span data-ttu-id="88597-128">Eksportēšana drīzumā tiks sākta, ja būs pabeigti visi eksportēšanas priekšnosacījumi.</span><span class="sxs-lookup"><span data-stu-id="88597-128">The export will start shortly if all prerequisites for export have been completed.</span></span> <span data-ttu-id="88597-129">Eksportēšana arī tiks palaista ar katru [plānoto atsvaidzināšanu](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="88597-129">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
<span data-ttu-id="88597-130">Kad eksportēšana ir sekmīgi pabeigta, varat pieteikties programmā LiveRamp Onboarding, lai aktivizētu un izplatītu savus datus.</span><span class="sxs-lookup"><span data-stu-id="88597-130">Once the export is successfully completed, you can sign in to LiveRamp Onboarding to activate and distribute your data.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="88597-131">Datu konfidencialitāte un atbilstība</span><span class="sxs-lookup"><span data-stu-id="88597-131">Data privacy and compliance</span></span>

<span data-ttu-id="88597-132">Ja iespējojat Dynamics 365 Customer Insights datu pārsūtīšanu uz Liveramp, jūs atļaujat datu pārsūtīšanu ārpus atbilstības robežām Dynamics 365 Customer Insights, ieskaitot iespējami sensitīvus datus, piemēram, personas datus.</span><span class="sxs-lookup"><span data-stu-id="88597-132">When you enable Dynamics 365 Customer Insights to transmit data to Liveramp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="88597-133">Microsoft šos datus pārsūtīs pēc jūsu norādēm, bet jūs esat atbildīgs par to, lai nodrošinātu Liveramp atbilstību konfidencialitātes vai drošības saistībām, kas jums varētu rasties.</span><span class="sxs-lookup"><span data-stu-id="88597-133">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Liveramp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="88597-134">Papildinformāciju skatiet rakstā [Microsoft Privātuma paziņojums](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="88597-134">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="88597-135">Jūsu Dynamics 365 Customer Insights administrators var noņemt šo eksportēšanas galamērķi jebkurā laikā, lai pārtrauktu izmantot šo funkcionalitāti.</span><span class="sxs-lookup"><span data-stu-id="88597-135">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]