---
title: Customer Insights datu eksportēšana uz RollWorks
description: Uzziniet, kā konfigurēt savienojumu un eksportēt uz RollWorks.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 4979f0147dea2270f11342c1bb6b0693f3c24aea
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760583"
---
# <a name="export-segment-lists-to-rollworks-preview"></a><span data-ttu-id="385ec-103">Segmentu sarakstu eksportēšana uz RollWorks (priekšskatījums)</span><span class="sxs-lookup"><span data-stu-id="385ec-103">Export segment lists to RollWorks (preview)</span></span>

<span data-ttu-id="385ec-104">Eksportējiet vienoto klientu profilu segmentus uz RollWorks un izmantojiet tos reklāmā.</span><span class="sxs-lookup"><span data-stu-id="385ec-104">Export segments of unified customer profiles to RollWorks and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="385ec-105">Savienojuma priekšnosacījumi</span><span class="sxs-lookup"><span data-stu-id="385ec-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="385ec-106">Jums ir [RollWorks konts](https://www.rollworks.com/) un atbilstošie administratora akreditācijas dati.</span><span class="sxs-lookup"><span data-stu-id="385ec-106">You have an [RollWorks account](https://www.rollworks.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="385ec-107">Jums ir [konfigurēti segmenti](segments.md) auditorijas ieskatos.</span><span class="sxs-lookup"><span data-stu-id="385ec-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="385ec-108">Eksportētajos segmentos vienotajiem klientu profiliem ir lauks, kas norāda e-pasta adresi.</span><span class="sxs-lookup"><span data-stu-id="385ec-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="385ec-109">Zināmie ierobežojumi</span><span class="sxs-lookup"><span data-stu-id="385ec-109">Known limitations</span></span>

- <span data-ttu-id="385ec-110">Jūs varat eksportēt līdz 250 000 profilu uz katru eksportu uz RollWorks.</span><span class="sxs-lookup"><span data-stu-id="385ec-110">You can export up to 250'000 profiles in per export to RollWorks.</span></span>
- <span data-ttu-id="385ec-111">Uz RollWorks nevar eksportēt segmentus, kuriem ir mazāk par 100 profiliem.</span><span class="sxs-lookup"><span data-stu-id="385ec-111">You can't export segments with fewer than 100 profiles to RollWorks.</span></span> 
- <span data-ttu-id="385ec-112">Eksportēšana uz RollWorks attiecas tikai uz segmentiem.</span><span class="sxs-lookup"><span data-stu-id="385ec-112">Exporting to RollWorks is limited to segments.</span></span>
- <span data-ttu-id="385ec-113">Līdz 250 000 profilu eksportēšana uz RollWorks var aizņemt līdz 10 minūtēm.</span><span class="sxs-lookup"><span data-stu-id="385ec-113">Exporting up to 250'000 profiles to RollWorks can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="385ec-114">Profilu, kurus varat eksportēt uz RollWorks skaits ir atkarīgs no jūsu līguma ar RollWorks un attiecas vienīgi uz tā tvērumu.</span><span class="sxs-lookup"><span data-stu-id="385ec-114">The number of profiles that you can export to RollWorks is dependent and limited on your contract with RollWorks.</span></span>

## <a name="set-up-connection-to-rollworks"></a><span data-ttu-id="385ec-115">Savienojuma ar RollWorks iestatīšana</span><span class="sxs-lookup"><span data-stu-id="385ec-115">Set up connection to RollWorks</span></span>

1. <span data-ttu-id="385ec-116">Dodieties uz **Administrators** > **Savienojumi**.</span><span class="sxs-lookup"><span data-stu-id="385ec-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="385ec-117">Atlasiet vienumu **Pievienot savienojumu** un atlasiet **RollWorks**, lai konfigurētu savienojumu.</span><span class="sxs-lookup"><span data-stu-id="385ec-117">Select **Add connection** and choose **RollWorks** to configure the connection.</span></span>

1. <span data-ttu-id="385ec-118">Laukā **Parādāmais nosaukums** piešķiriet savienojumam atpazīstamu nosaukumu.</span><span class="sxs-lookup"><span data-stu-id="385ec-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="385ec-119">Parādāmais nosaukums un nosaukuma veids raksturo šo savienojumu.</span><span class="sxs-lookup"><span data-stu-id="385ec-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="385ec-120">Ir ieteicams izvēlēties nosaukumu, kas paskaidro savienojuma nolūku.</span><span class="sxs-lookup"><span data-stu-id="385ec-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="385ec-121">Izvēlieties, kurš var izmantot šo savienojumu.</span><span class="sxs-lookup"><span data-stu-id="385ec-121">Choose who can use this connection.</span></span> <span data-ttu-id="385ec-122">Ja nesāksit nekādas darbības, noklusējums būs Administratori.</span><span class="sxs-lookup"><span data-stu-id="385ec-122">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="385ec-123">Papildinformāciju skatiet rakstā [Atļaut līdzstrādniekiem izmantot savienojumu eksportam](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="385ec-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="385ec-124">Atlasiet **Piekrītu**, lai apstiprinātu **Datu konfidencialitāti un atbilstību**.</span><span class="sxs-lookup"><span data-stu-id="385ec-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="385ec-125">Lai uzsāktu savienojumu ar RollWorks, atlasiet **Savienot**.</span><span class="sxs-lookup"><span data-stu-id="385ec-125">Select **Connect** to initialize the connection to RollWorks.</span></span>

1. <span data-ttu-id="385ec-126">Atlasiet **Autentificēt ar RollWorks** un norādiet savus RollWorks administratora akreditācijas datus.</span><span class="sxs-lookup"><span data-stu-id="385ec-126">Select **Authenticate with RollWorks** and provide your admin credentials for RollWorks.</span></span>

1. <span data-ttu-id="385ec-127">Atlasiet opciju **Pievienot sevi kā eksporta lietotāju** un sniedziet savus Customer Insights akreditācijas datus.</span><span class="sxs-lookup"><span data-stu-id="385ec-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="385ec-128">Lai pabeigtu savienošanu, atlasiet **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="385ec-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="385ec-129">Eksporta konfigurēšana</span><span class="sxs-lookup"><span data-stu-id="385ec-129">Configure an export</span></span>

<span data-ttu-id="385ec-130">Šo eksportu varat konfigurēt, ja jums ir piekļuve šā veida pieslēgumam.</span><span class="sxs-lookup"><span data-stu-id="385ec-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="385ec-131">Papildinformāciju skatiet rakstā [Atļaujas, kas nepieciešamas eksporta konfigurēšanai](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="385ec-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="385ec-132">Pārejiet uz **Dati** > **Eksportēšana**.</span><span class="sxs-lookup"><span data-stu-id="385ec-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="385ec-133">Lai izveidotu jaunu eksportu, atlasiet **Pievienot galamērķi**.</span><span class="sxs-lookup"><span data-stu-id="385ec-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="385ec-134">Laukā **Savienošana eksportam** atlasiet savienojumu no sadaļas RollWorks.</span><span class="sxs-lookup"><span data-stu-id="385ec-134">In the **Connection for export** field, choose a connection from the RollWorks section.</span></span> <span data-ttu-id="385ec-135">Ja šis sadaļas nosaukums nav redzams, šāda veida savienojumi jums nav pieejami.</span><span class="sxs-lookup"><span data-stu-id="385ec-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="385ec-136">Ievadiet savu **RollWorks reklāmdevēja ID** [RollWorks Advertisable](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span><span class="sxs-lookup"><span data-stu-id="385ec-136">Enter your **RollWorks Advertiser ID** [RollWorks Advertisable](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span></span>

3. <span data-ttu-id="385ec-137">Sadaļas **Datu atbilstības** laukā **E-pasts** atlasiet lauku, kas iekļauts vienotajā klientu profilā, kas pārstāv klienta e-pasta adresi.</span><span class="sxs-lookup"><span data-stu-id="385ec-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="385ec-138">Segmenti ir obligāti jāeksportē uz RollWorks.</span><span class="sxs-lookup"><span data-stu-id="385ec-138">It's required to export segments to RollWorks.</span></span>

1. <span data-ttu-id="385ec-139">Atlasiet segmentus, kurus vēlaties eksportēt.</span><span class="sxs-lookup"><span data-stu-id="385ec-139">Select the segments you want to export.</span></span> <span data-ttu-id="385ec-140">Atlasiet segmentu, kurā ir vismaz 100 dalībnieku.</span><span class="sxs-lookup"><span data-stu-id="385ec-140">Select a segment with a least 100 members.</span></span> <span data-ttu-id="385ec-141">Nevar eksportēt mazākus segmentus.</span><span class="sxs-lookup"><span data-stu-id="385ec-141">You can't export smaller segments.</span></span> <span data-ttu-id="385ec-142">Turklāt eksportējamā segmenta maksimālais lielums ir 250 000 dalībnieku vienam eksportam.</span><span class="sxs-lookup"><span data-stu-id="385ec-142">Additionally the maximum size of a segment to export is 250'000 members per export.</span></span> 

1. <span data-ttu-id="385ec-143">Atlasiet vienumu **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="385ec-143">Select **Save**.</span></span>

<span data-ttu-id="385ec-144">Eksporta saglabāšana automātiski nepalaiž eksportu.</span><span class="sxs-lookup"><span data-stu-id="385ec-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="385ec-145">Eksports tiek palaists ar katru [plānoto atsvaidzināšanu](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="385ec-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="385ec-146">Varat arī [eksportēt datus pēc pieprasījuma](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="385ec-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="385ec-147">Datu konfidencialitāte un atbilstība</span><span class="sxs-lookup"><span data-stu-id="385ec-147">Data privacy and compliance</span></span>

<span data-ttu-id="385ec-148">Iespējojiet Dynamics 365 Customer Insights datu pārnesi uz RollWorks, jūs ļaujat datus pārnest ārpus Dynamics 365 Customer Insights atbilstības robežām, ieskaitot potenciāli sensitīvus datus, tostarp, personas datus.</span><span class="sxs-lookup"><span data-stu-id="385ec-148">When you enable Dynamics 365 Customer Insights to transmit data to RollWorks, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="385ec-149">Microsoft šos datus pārvirzīs atbilstoši jūsu norādījumiem, taču jūs atbildat par to, ka RollWorks atbilst jebkādiem jūsu privātuma vai drošības nosacījumiem.</span><span class="sxs-lookup"><span data-stu-id="385ec-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that RollWorks meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="385ec-150">Papildinformāciju skatiet rakstā [Microsoft Privātuma paziņojums](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="385ec-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="385ec-151">Jūsu Dynamics 365 Customer Insights administrators var noņemt šo eksportēšanas galamērķi jebkurā laikā, lai pārtrauktu izmantot šo funkcionalitāti.</span><span class="sxs-lookup"><span data-stu-id="385ec-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
