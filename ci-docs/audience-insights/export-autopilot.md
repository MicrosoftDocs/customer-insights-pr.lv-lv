---
title: Customer Insights datu eksportēšana uz Autopilot
description: Uzziniet, kā konfigurēt savienojumu un eksportēt uz Autopilot.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e320a48d5b7c35b530e3a38567b226b804879e4e
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760152"
---
# <a name="export-segments-to-autopilot-preview"></a><span data-ttu-id="f86b7-103">Segmentu eksportēšana uz Autopilot (priekšskatījums)</span><span class="sxs-lookup"><span data-stu-id="f86b7-103">Export segments to Autopilot (preview)</span></span>

<span data-ttu-id="f86b7-104">Eksportējiet vienoto klientu profilu segmentus uz Autopilot un izmantojiet tos e-pasta mārketingam lietojumprogrammā Autopilot.</span><span class="sxs-lookup"><span data-stu-id="f86b7-104">Export segments of unified customer profiles to Autopilot and use them for email marketing in Autopilot.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="f86b7-105">Savienojuma priekšnosacījumi</span><span class="sxs-lookup"><span data-stu-id="f86b7-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="f86b7-106">Jums ir [Autopilot konts](https://www.autopilothq.com/) un atbilstošie administratora akreditācijas dati.</span><span class="sxs-lookup"><span data-stu-id="f86b7-106">You have an [Autopilot account](https://www.autopilothq.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="f86b7-107">Jums ir [konfigurēti segmenti](segments.md) auditorijas ieskatos.</span><span class="sxs-lookup"><span data-stu-id="f86b7-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="f86b7-108">Eksportētajos segmentos vienotajiem klientu profiliem ir lauks, kas norāda e-pasta adresi.</span><span class="sxs-lookup"><span data-stu-id="f86b7-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="f86b7-109">Zināmie ierobežojumi</span><span class="sxs-lookup"><span data-stu-id="f86b7-109">Known limitations</span></span>

- <span data-ttu-id="f86b7-110">Kopsummā var eksportēt līdz 100 000 profilu uz Autopilot.</span><span class="sxs-lookup"><span data-stu-id="f86b7-110">You can export up to 100'000 profiles in total to Autopilot.</span></span>
- <span data-ttu-id="f86b7-111">Eksportēšana uz Autopilot ir ierobežota līdz segmentiem.</span><span class="sxs-lookup"><span data-stu-id="f86b7-111">Exporting to Autopilot is limited to segments.</span></span>
- <span data-ttu-id="f86b7-112">100 000 profilu eksportēšana uz Autopilot var aizņemt dažas stundas.</span><span class="sxs-lookup"><span data-stu-id="f86b7-112">Exporting up to 100'000 profiles to Autopilot can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="f86b7-113">To profilu skaits, ko var eksportēt uz Autopilot, ir atkarīgs, un tas ir ierobežots jūsu līgumā ar Autopilot.</span><span class="sxs-lookup"><span data-stu-id="f86b7-113">The number of profiles that you can export to Autopilot is dependent and limited on your contract with Autopilot.</span></span>

## <a name="set-up-connection-to-autopilot"></a><span data-ttu-id="f86b7-114">Savienojuma ar Autopilot iestatīšana</span><span class="sxs-lookup"><span data-stu-id="f86b7-114">Set up connection to Autopilot</span></span>

1. <span data-ttu-id="f86b7-115">Dodieties uz **Administrators** > **Savienojumi**.</span><span class="sxs-lookup"><span data-stu-id="f86b7-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="f86b7-116">Atlasiet vienumu **Pievienot savienojumu** un atlasiet **Autopilot**, lai konfigurētu savienojumu.</span><span class="sxs-lookup"><span data-stu-id="f86b7-116">Select **Add connection** and choose **Autopilot** to configure the connection.</span></span>

1. <span data-ttu-id="f86b7-117">Laukā **Parādāmais nosaukums** piešķiriet savienojumam atpazīstamu nosaukumu.</span><span class="sxs-lookup"><span data-stu-id="f86b7-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="f86b7-118">Parādāmais nosaukums un nosaukuma veids raksturo šo savienojumu.</span><span class="sxs-lookup"><span data-stu-id="f86b7-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="f86b7-119">Ir ieteicams izvēlēties nosaukumu, kas paskaidro savienojuma nolūku.</span><span class="sxs-lookup"><span data-stu-id="f86b7-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="f86b7-120">Izvēlieties, kurš var izmantot šo savienojumu.</span><span class="sxs-lookup"><span data-stu-id="f86b7-120">Choose who can use this connection.</span></span> <span data-ttu-id="f86b7-121">Ja nesāksit nekādas darbības, noklusējums būs Administratori.</span><span class="sxs-lookup"><span data-stu-id="f86b7-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="f86b7-122">Papildinformāciju skatiet rakstā [Atļaut līdzstrādniekiem izmantot savienojumu eksportam](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="f86b7-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

3. <span data-ttu-id="f86b7-123">Ievadiet savu [Autopilot API atslēgu](https://autopilot.docs.apiary.io/#).</span><span class="sxs-lookup"><span data-stu-id="f86b7-123">Enter your [Autopilot API key](https://autopilot.docs.apiary.io/#).</span></span>

1. <span data-ttu-id="f86b7-124">Atlasiet **Piekrītu**, lai apstiprinātu **Datu konfidencialitāti un atbilstību**.</span><span class="sxs-lookup"><span data-stu-id="f86b7-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="f86b7-125">Atlasiet **Izveidot savienojumu**, lai inicializētu savienojumu ar Autopilot.</span><span class="sxs-lookup"><span data-stu-id="f86b7-125">Select **Connect** to initialize the connection to Autopilot.</span></span>

1. <span data-ttu-id="f86b7-126">Atlasiet opciju **Pievienot sevi kā eksporta lietotāju** un sniedziet savus Customer Insights akreditācijas datus.</span><span class="sxs-lookup"><span data-stu-id="f86b7-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="f86b7-127">Lai pabeigtu savienošanu, atlasiet **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="f86b7-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="f86b7-128">Eksporta konfigurēšana</span><span class="sxs-lookup"><span data-stu-id="f86b7-128">Configure an export</span></span>

<span data-ttu-id="f86b7-129">Šo eksportu varat konfigurēt, ja jums ir piekļuve šā veida pieslēgumam.</span><span class="sxs-lookup"><span data-stu-id="f86b7-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="f86b7-130">Papildinformāciju skatiet rakstā [Atļaujas, kas nepieciešamas eksporta konfigurēšanai](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="f86b7-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="f86b7-131">Pārejiet uz **Dati** > **Eksportēšana**.</span><span class="sxs-lookup"><span data-stu-id="f86b7-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="f86b7-132">Lai izveidotu jaunu eksportu, atlasiet **Pievienot galamērķi**.</span><span class="sxs-lookup"><span data-stu-id="f86b7-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="f86b7-133">Laukā **Savienošana eksportam** atlasiet savienojumu no sadaļas Autopilot.</span><span class="sxs-lookup"><span data-stu-id="f86b7-133">In the **Connection for export** field, choose a connection from the Autopilot section.</span></span> <span data-ttu-id="f86b7-134">Ja šis sadaļas nosaukums nav redzams, šāda veida savienojumi jums nav pieejami.</span><span class="sxs-lookup"><span data-stu-id="f86b7-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

3. <span data-ttu-id="f86b7-135">Sadaļas **Datu atbilstības** laukā **E-pasts** atlasiet lauku, kas iekļauts vienotajā klientu profilā, kas pārstāv klienta e-pasta adresi.</span><span class="sxs-lookup"><span data-stu-id="f86b7-135">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="f86b7-136">Veiciet tās pašas darbības ar citiem neobligātajiem laukiem, piemēram, **Vārds**, **Uzvārds**.</span><span class="sxs-lookup"><span data-stu-id="f86b7-136">Repeat the same steps for other optional fields such as **First name**, **Last name**.</span></span>

1. <span data-ttu-id="f86b7-137">Atlasiet segmentus, kurus vēlaties eksportēt.</span><span class="sxs-lookup"><span data-stu-id="f86b7-137">Select the segments you want to export.</span></span> <span data-ttu-id="f86b7-138">Mēs **stingri iesakām eksportēt kopumā ne vairāk kā 100 000 klientu profilu** programmā Autopilot.</span><span class="sxs-lookup"><span data-stu-id="f86b7-138">We strongly **recommend to not export more than 100'000 customer profiles in total** to Autopilot.</span></span> 

1. <span data-ttu-id="f86b7-139">Atlasiet vienumu **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="f86b7-139">Select **Save**.</span></span>

<span data-ttu-id="f86b7-140">Eksporta saglabāšana automātiski nepalaiž eksportu.</span><span class="sxs-lookup"><span data-stu-id="f86b7-140">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="f86b7-141">Eksports tiek palaists ar katru [plānoto atsvaidzināšanu](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="f86b7-141">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="f86b7-142">Varat arī [eksportēt datus pēc pieprasījuma](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="f86b7-142">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="f86b7-143">Datu konfidencialitāte un atbilstība</span><span class="sxs-lookup"><span data-stu-id="f86b7-143">Data privacy and compliance</span></span>

<span data-ttu-id="f86b7-144">Ja iespējojat Dynamics 365 Customer Insights datu pārsūtīšanu uz Autopilot, jūs atļaujat datu pārsūtīšanu ārpus atbilstības robežām Dynamics 365 Customer Insights, ieskaitot iespējami sensitīvus datus, piemēram, personas datus.</span><span class="sxs-lookup"><span data-stu-id="f86b7-144">When you enable Dynamics 365 Customer Insights to transmit data to Autopilot, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="f86b7-145">Microsoft šos datus pārsūtīs pēc jūsu norādēm, bet jūs esat atbildīgs par to, lai nodrošinātu Autopilot atbilstību konfidencialitātes vai drošības saistībām, kas jums varētu rasties.</span><span class="sxs-lookup"><span data-stu-id="f86b7-145">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Autopilot meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="f86b7-146">Papildinformāciju skatiet rakstā [Microsoft Privātuma paziņojums](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="f86b7-146">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="f86b7-147">Jūsu Dynamics 365 Customer Insights administrators var noņemt šo eksportēšanas galamērķi jebkurā laikā, lai pārtrauktu izmantot šo funkcionalitāti.</span><span class="sxs-lookup"><span data-stu-id="f86b7-147">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
