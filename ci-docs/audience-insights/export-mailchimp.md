---
title: Customer Insights datu eksportēšana uz Mailchimp
description: Uzziniet, kā konfigurēt savienojumu un eksportēt uz Mailchimp.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 7922a6a69f863caae5401549ed6f88a61aa77d39
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124236"
---
# <a name="export-segments-to-mailchimp-preview"></a><span data-ttu-id="04489-103">Segmentu eksportēšana uz Mailchimp (priekšskatījums)</span><span class="sxs-lookup"><span data-stu-id="04489-103">Export segments to Mailchimp (preview)</span></span>

<span data-ttu-id="04489-104">Eksportējiet vienotu klientu profilu segmentus uz Mailchimp, lai izveidotu informatīvas vēstules un e-pasta kampaņas.</span><span class="sxs-lookup"><span data-stu-id="04489-104">Export segments of unified customer profiles to Mailchimp to create newsletters and email campaigns.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="04489-105">Savienojuma priekšnosacījumi</span><span class="sxs-lookup"><span data-stu-id="04489-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="04489-106">Jums ir [Mailchimp konts](https://mailchimp.com/) un atbilstošie administratora akreditācijas dati.</span><span class="sxs-lookup"><span data-stu-id="04489-106">You have a [Mailchimp account](https://mailchimp.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="04489-107">Mailchimp ir esošas auditorijas un attiecīgie ID.</span><span class="sxs-lookup"><span data-stu-id="04489-107">There are existing audiences in Mailchimp and the corresponding IDs.</span></span> <span data-ttu-id="04489-108">Papildinformāciju skatiet rakstā [Mailchimp auditorijas](https://mailchimp.com/help/create-audience/).</span><span class="sxs-lookup"><span data-stu-id="04489-108">For more information, see [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>
-   <span data-ttu-id="04489-109">Jums ir [konfigurēti segmenti](segments.md)</span><span class="sxs-lookup"><span data-stu-id="04489-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="04489-110">Eksportētajos segmentos vienotajiem klientu profiliem ir lauks, kas norāda e-pasta adresi.</span><span class="sxs-lookup"><span data-stu-id="04489-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="04489-111">Zināmie ierobežojumi</span><span class="sxs-lookup"><span data-stu-id="04489-111">Known limitations</span></span>

- <span data-ttu-id="04489-112">Līdz 1 000 000 profilu, eksportējot uz Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="04489-112">Up to 1 million profiles per export to Mailchimp.</span></span>
- <span data-ttu-id="04489-113">Eksportēšana uz Mailchimp ir ierobežota līdz segmentiem.</span><span class="sxs-lookup"><span data-stu-id="04489-113">Exporting to Mailchimp is limited to segments.</span></span>
- <span data-ttu-id="04489-114">Segmentu ar 1 miljonu profilu eksportēšana var aizņemt līdz trim stundām.</span><span class="sxs-lookup"><span data-stu-id="04489-114">Exporting segments with 1 million profiles can take up to three hours.</span></span> 
- <span data-ttu-id="04489-115">To profilu skaits, ko var eksportēt uz Mailchimp, ir atkarīgs, un tas ir ierobežots jūsu līgumā ar Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="04489-115">The number of profiles that you can export to Mailchimp is dependent and limited on your contract with Mailchimp.</span></span>

## <a name="set-up-connection-to-mailchimp"></a><span data-ttu-id="04489-116">Savienojuma ar Mailchimp iestatīšana</span><span class="sxs-lookup"><span data-stu-id="04489-116">Set up connection to Mailchimp</span></span>

1. <span data-ttu-id="04489-117">Dodieties uz **Administrators** > **Savienojumi**.</span><span class="sxs-lookup"><span data-stu-id="04489-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="04489-118">Atlasiet vienumu **Pievienot savienojumu** un atlasiet **Autopilot**, lai konfigurētu savienojumu.</span><span class="sxs-lookup"><span data-stu-id="04489-118">Select **Add connection** and choose **Autopilot** to configure the connection.</span></span>

1. <span data-ttu-id="04489-119">Laukā **Parādāmais nosaukums** piešķiriet savienojumam atpazīstamu nosaukumu.</span><span class="sxs-lookup"><span data-stu-id="04489-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="04489-120">Parādāmais nosaukums un nosaukuma veids raksturo šo savienojumu.</span><span class="sxs-lookup"><span data-stu-id="04489-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="04489-121">Ir ieteicams izvēlēties nosaukumu, kas paskaidro savienojuma nolūku.</span><span class="sxs-lookup"><span data-stu-id="04489-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="04489-122">Izvēlieties, kurš var izmantot šo savienojumu.</span><span class="sxs-lookup"><span data-stu-id="04489-122">Choose who can use this connection.</span></span> <span data-ttu-id="04489-123">Ja nesāksit nekādas darbības, noklusējums būs Administratori.</span><span class="sxs-lookup"><span data-stu-id="04489-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="04489-124">Papildinformāciju skatiet rakstā [Atļaut līdzstrādniekiem izmantot savienojumu eksportam](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="04489-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="04489-125">Atlasiet **Piekrītu**, lai apstiprinātu **Datu konfidencialitāti un atbilstību**.</span><span class="sxs-lookup"><span data-stu-id="04489-125">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="04489-126">Lai uzsāktu savienojumu ar Mailchimp, atlasiet **Savienot**.</span><span class="sxs-lookup"><span data-stu-id="04489-126">Select **Connect** to initialize the connection to Mailchimp.</span></span>

1. <span data-ttu-id="04489-127">Atlasiet **Autentificēties ar Mailchimp** un sniedziet savus Mailchimp akreditācijas datus.</span><span class="sxs-lookup"><span data-stu-id="04489-127">Select **Authenticate with Mailchimp** and provide your Mailchimp credentials.</span></span>

1. <span data-ttu-id="04489-128">Atlasiet opciju **Pievienot sevi kā eksporta lietotāju** un sniedziet savus Customer Insights akreditācijas datus.</span><span class="sxs-lookup"><span data-stu-id="04489-128">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="04489-129">Lai pabeigtu savienošanu, atlasiet **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="04489-129">Select **Save** to complete the connection.</span></span> 

## <a name="configure-the-connector"></a><span data-ttu-id="04489-130">Savienotāja konfigurēšana</span><span class="sxs-lookup"><span data-stu-id="04489-130">Configure the connector</span></span>

<span data-ttu-id="04489-131">Šo eksportu varat konfigurēt, ja jums ir piekļuve šā veida pieslēgumam.</span><span class="sxs-lookup"><span data-stu-id="04489-131">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="04489-132">Papildinformāciju skatiet rakstā [Atļaujas, kas nepieciešamas eksporta konfigurēšanai](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="04489-132">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="04489-133">Pārejiet uz **Dati**> **Eksportēšana**.</span><span class="sxs-lookup"><span data-stu-id="04489-133">Go to **Data**> **Exports**.</span></span>

1. <span data-ttu-id="04489-134">Lai izveidotu jaunu eksportu, atlasiet **Pievienot galamērķi**.</span><span class="sxs-lookup"><span data-stu-id="04489-134">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="04489-135">Laukā **Savienošana eksportam** atlasiet savienojumu no sadaļas Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="04489-135">In the **Connection for export** field, choose a connection from the Mailchimp section.</span></span> <span data-ttu-id="04489-136">Ja šis sadaļas nosaukums nav redzams, šāda veida savienojumi jums nav pieejami.</span><span class="sxs-lookup"><span data-stu-id="04489-136">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="04489-137">Ievadiet **[Mailchimp auditorijas ID](https://mailchimp.com/help/find-audience-id/)**</span><span class="sxs-lookup"><span data-stu-id="04489-137">Enter your **[Mailchimp audience ID](https://mailchimp.com/help/find-audience-id/)**</span></span>

3. <span data-ttu-id="04489-138">Sadaļas **Datu atbilstības** laukā **E-pasts** atlasiet lauku, kas iekļauts vienotajā klientu profilā, kas pārstāv klienta e-pasta adresi.</span><span class="sxs-lookup"><span data-stu-id="04489-138">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="04489-139">Ja vēlaties, varat eksportēt **Vārdu** un **Uzvārdu**, lai izveidotu personalizētākus e-pastus.</span><span class="sxs-lookup"><span data-stu-id="04489-139">Optionally, you can export **First name** and **Last name** to create more personalized emails.</span></span> <span data-ttu-id="04489-140">Atlasiet **Pievienot atribūtu**, lai kartētu šos laukus.</span><span class="sxs-lookup"><span data-stu-id="04489-140">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="04489-141">Atlasiet segmentus, kurus vēlaties eksportēt.</span><span class="sxs-lookup"><span data-stu-id="04489-141">Select the segments you want to export.</span></span> <span data-ttu-id="04489-142">Kopsummā var eksportēt līdz 1 000 000 klientu profilu uz Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="04489-142">You can export up to 1 million customer profiles in total to Mailchimp.</span></span>

1. <span data-ttu-id="04489-143">Atlasiet vienumu **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="04489-143">Select **Save**.</span></span>

<span data-ttu-id="04489-144">Eksporta saglabāšana automātiski nepalaiž eksportu.</span><span class="sxs-lookup"><span data-stu-id="04489-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="04489-145">Eksports tiek palaists ar katru [plānoto atsvaidzināšanu](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="04489-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="04489-146">Varat arī [eksportēt datus pēc pieprasījuma](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="04489-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="04489-147">Datu konfidencialitāte un atbilstība</span><span class="sxs-lookup"><span data-stu-id="04489-147">Data privacy and compliance</span></span>

<span data-ttu-id="04489-148">Ja iespējojat Dynamics 365 Customer Insights datu pārsūtīšanu uz Mailchimp, jūs atļaujat datu pārsūtīšanu ārpus atbilstības robežām Dynamics 365 Customer Insights, ieskaitot iespējami sensitīvus datus, piemēram, personas datus.</span><span class="sxs-lookup"><span data-stu-id="04489-148">When you enable Dynamics 365 Customer Insights to transmit data to Mailchimp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="04489-149">Microsoft šos datus pārsūtīs pēc jūsu norādēm, bet jūs esat atbildīgs par to, lai nodrošinātu Mailchimp atbilstību konfidencialitātes vai drošības saistībām, kas jums varētu rasties.</span><span class="sxs-lookup"><span data-stu-id="04489-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Mailchimp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="04489-150">Papildinformāciju skatiet rakstā [Microsoft Privātuma paziņojums](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="04489-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="04489-151">Jūsu Dynamics 365 Customer Insights administrators var noņemt šo eksportēšanas galamērķi jebkurā laikā, lai pārtrauktu izmantot šo funkcionalitāti.</span><span class="sxs-lookup"><span data-stu-id="04489-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
