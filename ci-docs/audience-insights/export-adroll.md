---
title: Customer Insights datu eksportēšana uz AdRoll
description: Uzziniet, kā konfigurēt savienojumu ar AdRoll.
ms.date: 02/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6fedd549c2e7de362f36e3fb23d363200bb92a04
ms.sourcegitcommit: d24e52150fe5a4fab45128e12d6a03637771d9b9
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 03/19/2021
ms.locfileid: "5697083"
---
# <a name="connector-for-adroll-preview"></a><span data-ttu-id="dd2ad-103">Savienotājs ar AdRoll (priekšskatījums)</span><span class="sxs-lookup"><span data-stu-id="dd2ad-103">Connector for AdRoll (preview)</span></span>

<span data-ttu-id="dd2ad-104">Eksportējiet vienoto klientu profilu segmentus uz AdRoll un izmantojiet tos reklāmai.</span><span class="sxs-lookup"><span data-stu-id="dd2ad-104">Export segments of unified customer profiles to AdRoll and use them for advertising.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="dd2ad-105">Priekšnosacījumi</span><span class="sxs-lookup"><span data-stu-id="dd2ad-105">Prerequisites</span></span>

-   <span data-ttu-id="dd2ad-106">Jums ir [AdRoll konts](https://www.adroll.com/) un atbilstošie administratora akreditācijas dati.</span><span class="sxs-lookup"><span data-stu-id="dd2ad-106">You have an [AdRoll account](https://www.adroll.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="dd2ad-107">Jums ir [konfigurēti segmenti](segments.md) auditorijas ieskatos.</span><span class="sxs-lookup"><span data-stu-id="dd2ad-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="dd2ad-108">Eksportētajos segmentos vienotajiem klientu profiliem ir lauks, kas norāda e-pasta adresi.</span><span class="sxs-lookup"><span data-stu-id="dd2ad-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-adroll"></a><span data-ttu-id="dd2ad-109">Izveidot savienojumu ar AdRoll</span><span class="sxs-lookup"><span data-stu-id="dd2ad-109">Connect to AdRoll</span></span>

1. <span data-ttu-id="dd2ad-110">Dodieties uz sadaļu **Administrators** > **Eksportēšanas galamērķi**.</span><span class="sxs-lookup"><span data-stu-id="dd2ad-110">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="dd2ad-111">Sadaļā **AdRoll** atlasiet vienumu **Iestatīt**.</span><span class="sxs-lookup"><span data-stu-id="dd2ad-111">Under **AdRoll**, select **Set up**.</span></span>

1. <span data-ttu-id="dd2ad-112">Piešķiriet eksportēšanas galamērķim atpazīstamu nosaukumu laukā **Parādāmais nosaukums**.</span><span class="sxs-lookup"><span data-stu-id="dd2ad-112">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/AdRoll_config.PNG" alt-text="Konfigurēšanas rūts AdRoll savienojumam.":::

1. <span data-ttu-id="dd2ad-114">Atlasiet **Piekrītu**, lai apstiprinātu **Datu konfidencialitāti un atbilstību**.</span><span class="sxs-lookup"><span data-stu-id="dd2ad-114">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="dd2ad-115">Atlasiet **Izveidot savienojumu**, lai inicializētu savienojumu ar AdRoll.</span><span class="sxs-lookup"><span data-stu-id="dd2ad-115">Select **Connect** to initialize the connection to AdRoll.</span></span>

1. <span data-ttu-id="dd2ad-116">Atlasiet **Autentificēties ar AdRoll** un sniedziet savus administratora akreditācijas datus AdRoll.</span><span class="sxs-lookup"><span data-stu-id="dd2ad-116">Select **Authenticate with AdRoll** and provide your admin credentials for AdRoll.</span></span> 

1. <span data-ttu-id="dd2ad-117">Atlasiet opciju **Pievienot sevi kā eksporta lietotāju** un sniedziet savus Customer Insights akreditācijas datus.</span><span class="sxs-lookup"><span data-stu-id="dd2ad-117">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="dd2ad-118">Ievadiet savu **AdRoll reklamētāja ID**[AdRoll reklamējams](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles).</span><span class="sxs-lookup"><span data-stu-id="dd2ad-118">Enter your **AdRoll Advertiser ID** [AdRoll Advertisable](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles).</span></span>

1. <span data-ttu-id="dd2ad-119">Lai konfigurētu eksportēšanu, atlasiet **Tālāk**.</span><span class="sxs-lookup"><span data-stu-id="dd2ad-119">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="dd2ad-120">Savienotāja konfigurēšana</span><span class="sxs-lookup"><span data-stu-id="dd2ad-120">Configure the connector</span></span>

1. <span data-ttu-id="dd2ad-121">Sadaļas **Datu atbilstības** laukā **E-pasts** atlasiet lauku, kas iekļauts vienotajā klientu profilā, kas pārstāv klienta e-pasta adresi.</span><span class="sxs-lookup"><span data-stu-id="dd2ad-121">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="dd2ad-122">Segmenti ir jāeksportē uz AdRoll.</span><span class="sxs-lookup"><span data-stu-id="dd2ad-122">It's required to export segments to AdRoll.</span></span>

1. <span data-ttu-id="dd2ad-123">Atlasiet segmentus, kurus vēlaties eksportēt.</span><span class="sxs-lookup"><span data-stu-id="dd2ad-123">Select the segments you want to export.</span></span> <span data-ttu-id="dd2ad-124">Atlasiet segmentu, kurā ir vismaz 100 dalībnieku.</span><span class="sxs-lookup"><span data-stu-id="dd2ad-124">Select a segment with a least 100 members.</span></span> <span data-ttu-id="dd2ad-125">Nevar eksportēt mazākus segmentus.</span><span class="sxs-lookup"><span data-stu-id="dd2ad-125">You can't export smaller segments.</span></span> <span data-ttu-id="dd2ad-126">Turklāt eksportējamā segmenta maksimālais lielums ir 250 000 dalībnieku vienam eksportam.</span><span class="sxs-lookup"><span data-stu-id="dd2ad-126">Additionally the maximum size of a segment to export is 250'000 members per export.</span></span> 

1. <span data-ttu-id="dd2ad-127">Atlasiet vienumu **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="dd2ad-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="dd2ad-128">Datu eksportēšana</span><span class="sxs-lookup"><span data-stu-id="dd2ad-128">Export the data</span></span>

<span data-ttu-id="dd2ad-129">Datus var [eksportēt pēc pieprasījuma](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="dd2ad-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="dd2ad-130">Eksportēšana arī tiks palaista ar katru [plānoto atsvaidzināšanu](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="dd2ad-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="dd2ad-131">Zināmie ierobežojumi</span><span class="sxs-lookup"><span data-stu-id="dd2ad-131">Known limitations</span></span>

- <span data-ttu-id="dd2ad-132">Vienam eksportam var eksportēt līdz 250 000 profilu uz AdRoll.</span><span class="sxs-lookup"><span data-stu-id="dd2ad-132">You can export up to 250'000 profiles in per export to AdRoll.</span></span>
- <span data-ttu-id="dd2ad-133">Jūs nevarat eksportēt segmentus, kuros ir mazāk par 100 profiliem, uz AdRoll.</span><span class="sxs-lookup"><span data-stu-id="dd2ad-133">You can't export segments with fewer than 100 profiles to AdRoll.</span></span> 
- <span data-ttu-id="dd2ad-134">Eksportēšana uz AdRoll ir ierobežota līdz segmentiem.</span><span class="sxs-lookup"><span data-stu-id="dd2ad-134">Exporting to AdRoll is limited to segments.</span></span>
- <span data-ttu-id="dd2ad-135">Līdz 250 000 profilu eksportēšanai uz AdRoll var paiet 10 minūtes.</span><span class="sxs-lookup"><span data-stu-id="dd2ad-135">Exporting up to 250'000 profiles to AdRoll can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="dd2ad-136">To profilu skaits, ko var eksportēt uz AdRoll, ir atkarīgs, un tas ir ierobežots jūsu līgumā ar AdRoll.</span><span class="sxs-lookup"><span data-stu-id="dd2ad-136">The number of profiles that you can export to AdRoll is dependent and limited on your contract with AdRoll.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="dd2ad-137">Datu konfidencialitāte un atbilstība</span><span class="sxs-lookup"><span data-stu-id="dd2ad-137">Data privacy and compliance</span></span>

<span data-ttu-id="dd2ad-138">Ja iespējojat Dynamics 365 Customer Insights datu pārsūtīšanu uz AdRoll, jūs atļaujat datu pārsūtīšanu ārpus atbilstības robežām Dynamics 365 Customer Insights, ieskaitot iespējami sensitīvus datus, piemēram, personas datus.</span><span class="sxs-lookup"><span data-stu-id="dd2ad-138">When you enable Dynamics 365 Customer Insights to transmit data to AdRoll, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="dd2ad-139">Microsoft šos datus pārsūtīs pēc jūsu norādēm, bet jūs esat atbildīgs par to, lai nodrošinātu AdRoll atbilstību konfidencialitātes vai drošības saistībām, kas jums varētu rasties.</span><span class="sxs-lookup"><span data-stu-id="dd2ad-139">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that AdRoll meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="dd2ad-140">Papildinformāciju skatiet rakstā [Microsoft Privātuma paziņojums](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="dd2ad-140">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="dd2ad-141">Jūsu Dynamics 365 Customer Insights administrators var noņemt šo eksportēšanas galamērķi jebkurā laikā, lai pārtrauktu izmantot šo funkcionalitāti.</span><span class="sxs-lookup"><span data-stu-id="dd2ad-141">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
