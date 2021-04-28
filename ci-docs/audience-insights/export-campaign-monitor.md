---
title: Customer Insights datu eksportēšana uz Campaign Monitor
description: Uzziniet, kā konfigurēt savienojumu un eksportēt uz Campaign Monitor.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 7fd6af37b40e21d030a1ace0cd5f8fcc7861c3fa
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760582"
---
# <a name="export-segment-lists-to-campaign-monitor-preview"></a><span data-ttu-id="fd86b-103">Segmentu sarakstu eksportēšana uz Campaign Monitor (priekšskatījums)</span><span class="sxs-lookup"><span data-stu-id="fd86b-103">Export segment lists to Campaign Monitor (preview)</span></span>

<span data-ttu-id="fd86b-104">Eksportējiet vienoto klientu profilu segmentus uz Campaign Monitor un izmantojiet tos mārketinga darbībās.</span><span class="sxs-lookup"><span data-stu-id="fd86b-104">Export segments of unified customer profiles to Campaign Monitor and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="fd86b-105">Priekšnosacījumi</span><span class="sxs-lookup"><span data-stu-id="fd86b-105">Prerequisites</span></span>

-   <span data-ttu-id="fd86b-106">Jums ir [Campaign Monitor konts](https://www.campaignmonitor.com/) un atbilstošie administratora akreditācijas dati.</span><span class="sxs-lookup"><span data-stu-id="fd86b-106">You have an [Campaign Monitor account](https://www.campaignmonitor.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="fd86b-107">Jums ir [konfigurēti segmenti](segments.md) auditorijas ieskatos.</span><span class="sxs-lookup"><span data-stu-id="fd86b-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="fd86b-108">Eksportētajos segmentos vienotajiem klientu profiliem ir lauks, kas norāda e-pasta adresi.</span><span class="sxs-lookup"><span data-stu-id="fd86b-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="fd86b-109">Zināmie ierobežojumi</span><span class="sxs-lookup"><span data-stu-id="fd86b-109">Known limitations</span></span>

- <span data-ttu-id="fd86b-110">Jūs varat eksportēt līdz 1 miljonam profilu uz katru eksportu uz Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="fd86b-110">You can export up to 1 million profiles per export to Campaign Monitor.</span></span>
- <span data-ttu-id="fd86b-111">Eksportēšana uz Campaign Monitor attiecas tikai uz segmentiem.</span><span class="sxs-lookup"><span data-stu-id="fd86b-111">Exporting to Campaign Monitor is limited to segments.</span></span>
- <span data-ttu-id="fd86b-112">Līdz 1 miljona profilu eksportēšana uz Campaign Monitor var aizņemt līdz 20 minūtēm.</span><span class="sxs-lookup"><span data-stu-id="fd86b-112">Exporting up to 1 million profiles to Campaign Monitor can take up to 20 minutes to complete.</span></span> 
- <span data-ttu-id="fd86b-113">Profilu, kurus varat eksportēt uz Campaign Monitor skaits ir atkarīgs no jūsu līguma ar Campaign Monitor un attiecas vienīgi uz tā tvērumu.</span><span class="sxs-lookup"><span data-stu-id="fd86b-113">The number of profiles that you can export to Campaign Monitor is dependent and limited on your contract with Campaign Monitor.</span></span>

## <a name="set-up-connection-to-campaign-monitor"></a><span data-ttu-id="fd86b-114">Savienojuma ar Campaign Monitor iestatīšana</span><span class="sxs-lookup"><span data-stu-id="fd86b-114">Set up connection to Campaign Monitor</span></span>

1. <span data-ttu-id="fd86b-115">Dodieties uz **Administrators** > **Savienojumi**.</span><span class="sxs-lookup"><span data-stu-id="fd86b-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="fd86b-116">Atlasiet vienumu **Pievienot savienojumu** un atlasiet **Campaign Monitor**, lai konfigurētu savienojumu.</span><span class="sxs-lookup"><span data-stu-id="fd86b-116">Select **Add connection** and choose **Campaign Monitor** to configure the connection.</span></span>

1. <span data-ttu-id="fd86b-117">Laukā **Parādāmais nosaukums** piešķiriet savienojumam atpazīstamu nosaukumu.</span><span class="sxs-lookup"><span data-stu-id="fd86b-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="fd86b-118">Parādāmais nosaukums un nosaukuma veids raksturo šo savienojumu.</span><span class="sxs-lookup"><span data-stu-id="fd86b-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="fd86b-119">Ir ieteicams izvēlēties nosaukumu, kas paskaidro savienojuma nolūku.</span><span class="sxs-lookup"><span data-stu-id="fd86b-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="fd86b-120">Izvēlieties, kurš var izmantot šo savienojumu.</span><span class="sxs-lookup"><span data-stu-id="fd86b-120">Choose who can use this connection.</span></span> <span data-ttu-id="fd86b-121">Ja nesāksit nekādas darbības, noklusējums būs Administratori.</span><span class="sxs-lookup"><span data-stu-id="fd86b-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="fd86b-122">Papildinformāciju skatiet rakstā [Atļaut līdzstrādniekiem izmantot savienojumu eksportam](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="fd86b-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="fd86b-123">Atlasiet **Piekrītu**, lai apstiprinātu **Datu konfidencialitāti un atbilstību**.</span><span class="sxs-lookup"><span data-stu-id="fd86b-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="fd86b-124">Lai uzsāktu savienojumu ar Campaign Monitor, atlasiet **Savienot**.</span><span class="sxs-lookup"><span data-stu-id="fd86b-124">Select **Connect** to initialize the connection to Campaign Monitor.</span></span>

1. <span data-ttu-id="fd86b-125">Atlasiet **Autentificēt ar Campaign Monitor** un norādiet savus Campaign Monitor administratora akreditācijas datus.</span><span class="sxs-lookup"><span data-stu-id="fd86b-125">Select **Authenticate with Campaign Monitor** and provide your admin credentials for Campaign Monitor.</span></span>

1. <span data-ttu-id="fd86b-126">Atlasiet opciju **Pievienot sevi kā eksporta lietotāju** un sniedziet savus Customer Insights akreditācijas datus.</span><span class="sxs-lookup"><span data-stu-id="fd86b-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="fd86b-127">Lai pabeigtu savienošanu, atlasiet **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="fd86b-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="fd86b-128">Eksporta konfigurēšana</span><span class="sxs-lookup"><span data-stu-id="fd86b-128">Configure an export</span></span>

<span data-ttu-id="fd86b-129">Šo eksportu varat konfigurēt, ja jums ir piekļuve šā veida pieslēgumam.</span><span class="sxs-lookup"><span data-stu-id="fd86b-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="fd86b-130">Papildinformāciju skatiet rakstā [Atļaujas, kas nepieciešamas eksporta konfigurēšanai](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="fd86b-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="fd86b-131">Pārejiet uz **Dati** > **Eksportēšana**.</span><span class="sxs-lookup"><span data-stu-id="fd86b-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="fd86b-132">Lai izveidotu jaunu eksportu, atlasiet **Pievienot galamērķi**.</span><span class="sxs-lookup"><span data-stu-id="fd86b-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="fd86b-133">Laukā **Savienošana eksportam** atlasiet savienojumu no sadaļas Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="fd86b-133">In the **Connection for export** field, choose a connection from the Campaign Monitor section.</span></span> <span data-ttu-id="fd86b-134">Ja šis sadaļas nosaukums nav redzams, šāda veida savienojumi jums nav pieejami.</span><span class="sxs-lookup"><span data-stu-id="fd86b-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="fd86b-135">Ievadiet savu [**Campaign Monitor saraksta ID**](https://www.campaignmonitor.com/api/getting-started/#your-list-id).</span><span class="sxs-lookup"><span data-stu-id="fd86b-135">Enter your [**Campaign Monitor List ID**](https://www.campaignmonitor.com/api/getting-started/#your-list-id).</span></span>    
   <span data-ttu-id="fd86b-136">Vispirms [Ģenerējiet API atslēgu](https://www.campaignmonitor.com/api/getting-started/) no Campaign Monitor **Konta iestatījumiem**, lai skatītu API saraksta ID.</span><span class="sxs-lookup"><span data-stu-id="fd86b-136">[Generate the API key](https://www.campaignmonitor.com/api/getting-started/) from **Account Settings** in Campaign Monitor first to view the API list ID.</span></span>  

3. <span data-ttu-id="fd86b-137">Sadaļas **Datu atbilstības** laukā **E-pasts** atlasiet lauku, kas iekļauts vienotajā klientu profilā, kas pārstāv klienta e-pasta adresi.</span><span class="sxs-lookup"><span data-stu-id="fd86b-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="fd86b-138">Segmenti ir obligāti jāeksportē uz Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="fd86b-138">It's required to export segments to Campaign Monitor.</span></span>

1. <span data-ttu-id="fd86b-139">Atlasiet vienumu **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="fd86b-139">Select **Save**.</span></span>

<span data-ttu-id="fd86b-140">Eksporta saglabāšana automātiski nepalaiž eksportu.</span><span class="sxs-lookup"><span data-stu-id="fd86b-140">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="fd86b-141">Eksports tiek palaists ar katru [plānoto atsvaidzināšanu](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="fd86b-141">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="fd86b-142">Varat arī [eksportēt datus pēc pieprasījuma](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="fd86b-142">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="fd86b-143">Datu konfidencialitāte un atbilstība</span><span class="sxs-lookup"><span data-stu-id="fd86b-143">Data privacy and compliance</span></span>

<span data-ttu-id="fd86b-144">Iespējojot Dynamics 365 Customer Insights datu pārnesi uz Campaign Monitor, jūs ļaujat datus pārnest ārpus Dynamics 365 Customer Insights atbilstības robežām, ieskaitot potenciāli sensitīvus datus, tostarp, personas datus.</span><span class="sxs-lookup"><span data-stu-id="fd86b-144">When you enable Dynamics 365 Customer Insights to transmit data to Campaign Monitor, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="fd86b-145">Microsoft šos datus pārvirzīs atbilstoši jūsu norādījumiem, taču jūs atbildat par to, ka Campaign Monitor atbilst jebkādiem jūsu privātuma vai drošības nosacījumiem.</span><span class="sxs-lookup"><span data-stu-id="fd86b-145">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Campaign Monitor meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="fd86b-146">Papildinformāciju skatiet rakstā [Microsoft Privātuma paziņojums](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="fd86b-146">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="fd86b-147">Jūsu Dynamics 365 Customer Insights administrators var noņemt šo eksportēšanas galamērķi jebkurā laikā, lai pārtrauktu izmantot šo funkcionalitāti.</span><span class="sxs-lookup"><span data-stu-id="fd86b-147">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
