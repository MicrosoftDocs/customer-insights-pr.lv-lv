---
title: Customer Insights datu eksportēšana uz AdRoll
description: Uzziniet, kā konfigurēt savienojumu un eksportēt uz AdRoll.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e8f4d4ee6b2c6cdec513b700641db568fa16076d
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 04/14/2021
ms.locfileid: "5895968"
---
# <a name="export-segment-lists-to-adroll-preview"></a><span data-ttu-id="731e6-103">Segmentu sarakstu eksportēšana uz AdRoll (priekšskatījums)</span><span class="sxs-lookup"><span data-stu-id="731e6-103">Export segment lists to AdRoll (preview)</span></span>

<span data-ttu-id="731e6-104">Eksportējiet vienoto klientu profilu segmentus uz AdRoll un izmantojiet tos reklāmai.</span><span class="sxs-lookup"><span data-stu-id="731e6-104">Export segments of unified customer profiles to AdRoll and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="731e6-105">Savienojuma priekšnosacījumi</span><span class="sxs-lookup"><span data-stu-id="731e6-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="731e6-106">Jums ir [AdRoll konts](https://www.adroll.com/) un atbilstošie administratora akreditācijas dati.</span><span class="sxs-lookup"><span data-stu-id="731e6-106">You have an [AdRoll account](https://www.adroll.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="731e6-107">Jums ir [konfigurēti segmenti](segments.md) auditorijas ieskatos.</span><span class="sxs-lookup"><span data-stu-id="731e6-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="731e6-108">Eksportētajos segmentos vienotajiem klientu profiliem ir lauks, kas norāda e-pasta adresi.</span><span class="sxs-lookup"><span data-stu-id="731e6-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="731e6-109">Zināmie ierobežojumi</span><span class="sxs-lookup"><span data-stu-id="731e6-109">Known limitations</span></span>

- <span data-ttu-id="731e6-110">Vienam eksportam var eksportēt līdz 250 000 profilu uz AdRoll.</span><span class="sxs-lookup"><span data-stu-id="731e6-110">You can export up to 250'000 profiles in per export to AdRoll.</span></span>
- <span data-ttu-id="731e6-111">Jūs nevarat eksportēt segmentus, kuros ir mazāk par 100 profiliem, uz AdRoll.</span><span class="sxs-lookup"><span data-stu-id="731e6-111">You can't export segments with fewer than 100 profiles to AdRoll.</span></span> 
- <span data-ttu-id="731e6-112">Eksportēšana uz AdRoll ir ierobežota līdz segmentiem.</span><span class="sxs-lookup"><span data-stu-id="731e6-112">Exporting to AdRoll is limited to segments.</span></span>
- <span data-ttu-id="731e6-113">Līdz 250 000 profilu eksportēšanai uz AdRoll var paiet 10 minūtes.</span><span class="sxs-lookup"><span data-stu-id="731e6-113">Exporting up to 250'000 profiles to AdRoll can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="731e6-114">To profilu skaits, ko var eksportēt uz AdRoll, ir atkarīgs, un tas ir ierobežots jūsu līgumā ar AdRoll.</span><span class="sxs-lookup"><span data-stu-id="731e6-114">The number of profiles that you can export to AdRoll is dependent and limited on your contract with AdRoll.</span></span>

## <a name="set-up-connection-to-adroll"></a><span data-ttu-id="731e6-115">Savienojuma ar AdRoll iestatīšana</span><span class="sxs-lookup"><span data-stu-id="731e6-115">Set up connection to AdRoll</span></span>

1. <span data-ttu-id="731e6-116">Dodieties uz **Administrators** > **Savienojumi**.</span><span class="sxs-lookup"><span data-stu-id="731e6-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="731e6-117">Atlasiet vienumu **Pievienot savienojumu** un atlasiet **AdRoll**, lai konfigurētu savienojumu.</span><span class="sxs-lookup"><span data-stu-id="731e6-117">Select **Add connection** and choose **AdRoll** to configure the connection.</span></span>

1. <span data-ttu-id="731e6-118">Laukā **Parādāmais nosaukums** piešķiriet savienojumam atpazīstamu nosaukumu.</span><span class="sxs-lookup"><span data-stu-id="731e6-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="731e6-119">Parādāmais nosaukums un nosaukuma veids raksturo šo savienojumu.</span><span class="sxs-lookup"><span data-stu-id="731e6-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="731e6-120">Ir ieteicams izvēlēties nosaukumu, kas paskaidro savienojuma nolūku.</span><span class="sxs-lookup"><span data-stu-id="731e6-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="731e6-121">Izvēlieties, kurš var izmantot šo savienojumu.</span><span class="sxs-lookup"><span data-stu-id="731e6-121">Choose who can use this connection.</span></span> <span data-ttu-id="731e6-122">Ja nesāksit nekādas darbības, noklusējums būs Administratori.</span><span class="sxs-lookup"><span data-stu-id="731e6-122">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="731e6-123">Papildinformāciju skatiet rakstā [Atļaut līdzstrādniekiem izmantot savienojumu eksportam](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="731e6-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="731e6-124">Atlasiet **Piekrītu**, lai apstiprinātu **Datu konfidencialitāti un atbilstību**.</span><span class="sxs-lookup"><span data-stu-id="731e6-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="731e6-125">Atlasiet **Izveidot savienojumu**, lai inicializētu savienojumu ar AdRoll.</span><span class="sxs-lookup"><span data-stu-id="731e6-125">Select **Connect** to initialize the connection to AdRoll.</span></span>

1. <span data-ttu-id="731e6-126">Atlasiet **Autentificēties ar AdRoll** un sniedziet savus administratora akreditācijas datus AdRoll.</span><span class="sxs-lookup"><span data-stu-id="731e6-126">Select **Authenticate with AdRoll** and provide your admin credentials for AdRoll.</span></span> 

1. <span data-ttu-id="731e6-127">Atlasiet opciju **Pievienot sevi kā eksporta lietotāju** un sniedziet savus Customer Insights akreditācijas datus.</span><span class="sxs-lookup"><span data-stu-id="731e6-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="731e6-128">Lai pabeigtu savienošanu, atlasiet **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="731e6-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="731e6-129">Eksporta konfigurēšana</span><span class="sxs-lookup"><span data-stu-id="731e6-129">Configure an export</span></span>

<span data-ttu-id="731e6-130">Šo eksportu varat konfigurēt, ja jums ir piekļuve šā veida pieslēgumam.</span><span class="sxs-lookup"><span data-stu-id="731e6-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="731e6-131">Papildinformāciju skatiet rakstā [Atļaujas, kas nepieciešamas eksporta konfigurēšanai](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="731e6-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="731e6-132">Pārejiet uz **Dati** > **Eksportēšana**.</span><span class="sxs-lookup"><span data-stu-id="731e6-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="731e6-133">Lai izveidotu jaunu eksportu, atlasiet **Pievienot galamērķi**.</span><span class="sxs-lookup"><span data-stu-id="731e6-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="731e6-134">Laukā **Savienošana eksportam** atlasiet savienojumu no sadaļas AdRoll.</span><span class="sxs-lookup"><span data-stu-id="731e6-134">In the **Connection for export** field, choose a connection from the AdRoll section.</span></span> <span data-ttu-id="731e6-135">Ja šis sadaļas nosaukums nav redzams, šāda veida savienojumi jums nav pieejami.</span><span class="sxs-lookup"><span data-stu-id="731e6-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="731e6-136">Ievadiet savu **AdRoll Advertiser ID** Papildu informāciju skatiet rakstā [AdRoll Advertiser profili](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span><span class="sxs-lookup"><span data-stu-id="731e6-136">Enter your **AdRoll Advertiser ID** For more information, see [AdRoll Advertiser Profiles](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span></span>

3. <span data-ttu-id="731e6-137">Sadaļas **Datu atbilstības** laukā **E-pasts** atlasiet lauku, kas iekļauts vienotajā klientu profilā, kas pārstāv klienta e-pasta adresi.</span><span class="sxs-lookup"><span data-stu-id="731e6-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="731e6-138">Segmenti ir jāeksportē uz AdRoll.</span><span class="sxs-lookup"><span data-stu-id="731e6-138">It's required to export segments to AdRoll.</span></span>

1. <span data-ttu-id="731e6-139">Atlasiet segmentus, kurus vēlaties eksportēt.</span><span class="sxs-lookup"><span data-stu-id="731e6-139">Select the segments you want to export.</span></span> <span data-ttu-id="731e6-140">Atlasiet segmentu, kurā ir vismaz 100 dalībnieku.</span><span class="sxs-lookup"><span data-stu-id="731e6-140">Select a segment with a least 100 members.</span></span> <span data-ttu-id="731e6-141">Nevar eksportēt mazākus segmentus.</span><span class="sxs-lookup"><span data-stu-id="731e6-141">You can't export smaller segments.</span></span> <span data-ttu-id="731e6-142">Turklāt eksportējamā segmenta maksimālais lielums ir 250 000 dalībnieku vienam eksportam.</span><span class="sxs-lookup"><span data-stu-id="731e6-142">Additionally the maximum size of a segment to export is 250'000 members per export.</span></span> 

1. <span data-ttu-id="731e6-143">Atlasiet vienumu **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="731e6-143">Select **Save**.</span></span>

<span data-ttu-id="731e6-144">Eksporta saglabāšana automātiski nepalaiž eksportu.</span><span class="sxs-lookup"><span data-stu-id="731e6-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="731e6-145">Eksports tiek palaists ar katru [plānoto atsvaidzināšanu](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="731e6-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="731e6-146">Varat arī [eksportēt datus pēc pieprasījuma](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="731e6-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="731e6-147">Datu konfidencialitāte un atbilstība</span><span class="sxs-lookup"><span data-stu-id="731e6-147">Data privacy and compliance</span></span>

<span data-ttu-id="731e6-148">Ja iespējojat Dynamics 365 Customer Insights datu pārsūtīšanu uz AdRoll, jūs atļaujat datu pārsūtīšanu ārpus atbilstības robežām Dynamics 365 Customer Insights, ieskaitot iespējami sensitīvus datus, piemēram, personas datus.</span><span class="sxs-lookup"><span data-stu-id="731e6-148">When you enable Dynamics 365 Customer Insights to transmit data to AdRoll, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="731e6-149">Microsoft šos datus pārsūtīs pēc jūsu norādēm, bet jūs esat atbildīgs par to, lai nodrošinātu AdRoll atbilstību konfidencialitātes vai drošības saistībām, kas jums varētu rasties.</span><span class="sxs-lookup"><span data-stu-id="731e6-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that AdRoll meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="731e6-150">Papildinformāciju skatiet rakstā [Microsoft Privātuma paziņojums](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="731e6-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="731e6-151">Jūsu Dynamics 365 Customer Insights administrators var noņemt šo eksportēšanas galamērķi jebkurā laikā, lai pārtrauktu izmantot šo funkcionalitāti.</span><span class="sxs-lookup"><span data-stu-id="731e6-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
