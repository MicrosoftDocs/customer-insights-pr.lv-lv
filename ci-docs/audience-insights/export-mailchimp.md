---
title: Customer Insights datu eksportēšana uz Mailchimp
description: Uzziniet, kā konfigurēt savienojumu un eksportēt uz Mailchimp.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b94a8e8b6bb867ca04a64007d592b22fbd700618
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759887"
---
# <a name="export-segment-lists-to-mailchimp-preview"></a><span data-ttu-id="815f0-103">Segmentu sarakstu eksportēšana uz Mailchimp (priekšskatījums)</span><span class="sxs-lookup"><span data-stu-id="815f0-103">Export segment lists to Mailchimp (preview)</span></span>

<span data-ttu-id="815f0-104">Eksportējiet vienotu klientu profilu segmentus uz Mailchimp, lai izveidotu informatīvas vēstules un e-pasta kampaņas.</span><span class="sxs-lookup"><span data-stu-id="815f0-104">Export segments of unified customer profiles to Mailchimp to create newsletters and email campaigns.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="815f0-105">Savienojuma priekšnosacījumi</span><span class="sxs-lookup"><span data-stu-id="815f0-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="815f0-106">Jums ir [Mailchimp konts](https://mailchimp.com/) un atbilstošie administratora akreditācijas dati.</span><span class="sxs-lookup"><span data-stu-id="815f0-106">You have a [Mailchimp account](https://mailchimp.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="815f0-107">Mailchimp ir esošas auditorijas un attiecīgie ID.</span><span class="sxs-lookup"><span data-stu-id="815f0-107">There are existing audiences in Mailchimp and the corresponding IDs.</span></span> <span data-ttu-id="815f0-108">Papildinformāciju skatiet rakstā [Mailchimp auditorijas](https://mailchimp.com/help/create-audience/).</span><span class="sxs-lookup"><span data-stu-id="815f0-108">For more information, see [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>
-   <span data-ttu-id="815f0-109">Jums ir [konfigurēti segmenti](segments.md)</span><span class="sxs-lookup"><span data-stu-id="815f0-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="815f0-110">Eksportētajos segmentos vienotajiem klientu profiliem ir lauks, kas norāda e-pasta adresi.</span><span class="sxs-lookup"><span data-stu-id="815f0-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="815f0-111">Zināmie ierobežojumi</span><span class="sxs-lookup"><span data-stu-id="815f0-111">Known limitations</span></span>

- <span data-ttu-id="815f0-112">Līdz 1 000 000 profilu, eksportējot uz Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="815f0-112">Up to 1 million profiles per export to Mailchimp.</span></span>
- <span data-ttu-id="815f0-113">Eksportēšana uz Mailchimp ir ierobežota līdz segmentiem.</span><span class="sxs-lookup"><span data-stu-id="815f0-113">Exporting to Mailchimp is limited to segments.</span></span>
- <span data-ttu-id="815f0-114">Segmentu ar 1 miljonu profilu eksportēšana var aizņemt līdz trim stundām.</span><span class="sxs-lookup"><span data-stu-id="815f0-114">Exporting segments with 1 million profiles can take up to three hours.</span></span> 
- <span data-ttu-id="815f0-115">To profilu skaits, ko var eksportēt uz Mailchimp, ir atkarīgs, un tas ir ierobežots jūsu līgumā ar Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="815f0-115">The number of profiles that you can export to Mailchimp is dependent and limited on your contract with Mailchimp.</span></span>

## <a name="set-up-connection-to-mailchimp"></a><span data-ttu-id="815f0-116">Savienojuma ar Mailchimp iestatīšana</span><span class="sxs-lookup"><span data-stu-id="815f0-116">Set up connection to Mailchimp</span></span>

1. <span data-ttu-id="815f0-117">Dodieties uz **Administrators** > **Savienojumi**.</span><span class="sxs-lookup"><span data-stu-id="815f0-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="815f0-118">Atlasiet vienumu **Pievienot savienojumu** un atlasiet **Autopilot**, lai konfigurētu savienojumu.</span><span class="sxs-lookup"><span data-stu-id="815f0-118">Select **Add connection** and choose **Autopilot** to configure the connection.</span></span>

1. <span data-ttu-id="815f0-119">Laukā **Parādāmais nosaukums** piešķiriet savienojumam atpazīstamu nosaukumu.</span><span class="sxs-lookup"><span data-stu-id="815f0-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="815f0-120">Parādāmais nosaukums un nosaukuma veids raksturo šo savienojumu.</span><span class="sxs-lookup"><span data-stu-id="815f0-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="815f0-121">Ir ieteicams izvēlēties nosaukumu, kas paskaidro savienojuma nolūku.</span><span class="sxs-lookup"><span data-stu-id="815f0-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="815f0-122">Izvēlieties, kurš var izmantot šo savienojumu.</span><span class="sxs-lookup"><span data-stu-id="815f0-122">Choose who can use this connection.</span></span> <span data-ttu-id="815f0-123">Ja nesāksit nekādas darbības, noklusējums būs Administratori.</span><span class="sxs-lookup"><span data-stu-id="815f0-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="815f0-124">Papildinformāciju skatiet rakstā [Atļaut līdzstrādniekiem izmantot savienojumu eksportam](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="815f0-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="815f0-125">Atlasiet **Piekrītu**, lai apstiprinātu **Datu konfidencialitāti un atbilstību**.</span><span class="sxs-lookup"><span data-stu-id="815f0-125">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="815f0-126">Lai uzsāktu savienojumu ar Mailchimp, atlasiet **Savienot**.</span><span class="sxs-lookup"><span data-stu-id="815f0-126">Select **Connect** to initialize the connection to Mailchimp.</span></span>

1. <span data-ttu-id="815f0-127">Atlasiet **Autentificēties ar Mailchimp** un sniedziet savus Mailchimp akreditācijas datus.</span><span class="sxs-lookup"><span data-stu-id="815f0-127">Select **Authenticate with Mailchimp** and provide your Mailchimp credentials.</span></span>

1. <span data-ttu-id="815f0-128">Atlasiet opciju **Pievienot sevi kā eksporta lietotāju** un sniedziet savus Customer Insights akreditācijas datus.</span><span class="sxs-lookup"><span data-stu-id="815f0-128">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="815f0-129">Lai pabeigtu savienošanu, atlasiet **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="815f0-129">Select **Save** to complete the connection.</span></span> 

## <a name="configure-the-connector"></a><span data-ttu-id="815f0-130">Savienotāja konfigurēšana</span><span class="sxs-lookup"><span data-stu-id="815f0-130">Configure the connector</span></span>

<span data-ttu-id="815f0-131">Šo eksportu varat konfigurēt, ja jums ir piekļuve šā veida pieslēgumam.</span><span class="sxs-lookup"><span data-stu-id="815f0-131">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="815f0-132">Papildinformāciju skatiet rakstā [Atļaujas, kas nepieciešamas eksporta konfigurēšanai](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="815f0-132">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="815f0-133">Pārejiet uz **Dati**> **Eksportēšana**.</span><span class="sxs-lookup"><span data-stu-id="815f0-133">Go to **Data**> **Exports**.</span></span>

1. <span data-ttu-id="815f0-134">Lai izveidotu jaunu eksportu, atlasiet **Pievienot galamērķi**.</span><span class="sxs-lookup"><span data-stu-id="815f0-134">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="815f0-135">Laukā **Savienošana eksportam** atlasiet savienojumu no sadaļas Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="815f0-135">In the **Connection for export** field, choose a connection from the Mailchimp section.</span></span> <span data-ttu-id="815f0-136">Ja šis sadaļas nosaukums nav redzams, šāda veida savienojumi jums nav pieejami.</span><span class="sxs-lookup"><span data-stu-id="815f0-136">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="815f0-137">Ievadiet **[Mailchimp auditorijas ID](https://mailchimp.com/help/find-audience-id/)**</span><span class="sxs-lookup"><span data-stu-id="815f0-137">Enter your **[Mailchimp audience ID](https://mailchimp.com/help/find-audience-id/)**</span></span>

3. <span data-ttu-id="815f0-138">Sadaļas **Datu atbilstības** laukā **E-pasts** atlasiet lauku, kas iekļauts vienotajā klientu profilā, kas pārstāv klienta e-pasta adresi.</span><span class="sxs-lookup"><span data-stu-id="815f0-138">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="815f0-139">Ja vēlaties, varat eksportēt **Vārdu** un **Uzvārdu**, lai izveidotu personalizētākus e-pastus.</span><span class="sxs-lookup"><span data-stu-id="815f0-139">Optionally, you can export **First name** and **Last name** to create more personalized emails.</span></span> <span data-ttu-id="815f0-140">Atlasiet **Pievienot atribūtu**, lai kartētu šos laukus.</span><span class="sxs-lookup"><span data-stu-id="815f0-140">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="815f0-141">Atlasiet segmentus, kurus vēlaties eksportēt.</span><span class="sxs-lookup"><span data-stu-id="815f0-141">Select the segments you want to export.</span></span> <span data-ttu-id="815f0-142">Kopsummā var eksportēt līdz 1 000 000 klientu profilu uz Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="815f0-142">You can export up to 1 million customer profiles in total to Mailchimp.</span></span>

1. <span data-ttu-id="815f0-143">Atlasiet vienumu **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="815f0-143">Select **Save**.</span></span>

<span data-ttu-id="815f0-144">Eksporta saglabāšana automātiski nepalaiž eksportu.</span><span class="sxs-lookup"><span data-stu-id="815f0-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="815f0-145">Eksports tiek palaists ar katru [plānoto atsvaidzināšanu](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="815f0-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="815f0-146">Varat arī [eksportēt datus pēc pieprasījuma](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="815f0-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="815f0-147">Datu konfidencialitāte un atbilstība</span><span class="sxs-lookup"><span data-stu-id="815f0-147">Data privacy and compliance</span></span>

<span data-ttu-id="815f0-148">Ja iespējojat Dynamics 365 Customer Insights datu pārsūtīšanu uz Mailchimp, jūs atļaujat datu pārsūtīšanu ārpus atbilstības robežām Dynamics 365 Customer Insights, ieskaitot iespējami sensitīvus datus, piemēram, personas datus.</span><span class="sxs-lookup"><span data-stu-id="815f0-148">When you enable Dynamics 365 Customer Insights to transmit data to Mailchimp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="815f0-149">Microsoft šos datus pārsūtīs pēc jūsu norādēm, bet jūs esat atbildīgs par to, lai nodrošinātu Mailchimp atbilstību konfidencialitātes vai drošības saistībām, kas jums varētu rasties.</span><span class="sxs-lookup"><span data-stu-id="815f0-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Mailchimp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="815f0-150">Papildinformāciju skatiet rakstā [Microsoft Privātuma paziņojums](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="815f0-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="815f0-151">Jūsu Dynamics 365 Customer Insights administrators var noņemt šo eksportēšanas galamērķi jebkurā laikā, lai pārtrauktu izmantot šo funkcionalitāti.</span><span class="sxs-lookup"><span data-stu-id="815f0-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
