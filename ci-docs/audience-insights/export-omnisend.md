---
title: Customer Insights datu eksportēšana uz Omnisend
description: Uzziniet, kā konfigurēt savienojumu un eksportēt uz Omnisend.
ms.date: 05/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8bd692819fa8451ded5e74191ee717f81f87425d
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124520"
---
# <a name="export-segments-to-omnisend-preview"></a><span data-ttu-id="8823b-103">Segmentu eksportēšana uz Omnisend (priekšskatījums)</span><span class="sxs-lookup"><span data-stu-id="8823b-103">Export segments to Omnisend (preview)</span></span>

<span data-ttu-id="8823b-104">Eksportējiet vienoto klientu profilu segmentus uz Omnisend un izmantojiet tos mārketinga darbībās.</span><span class="sxs-lookup"><span data-stu-id="8823b-104">Export segments of unified customer profiles to Omnisend and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8823b-105">Priekšnosacījumi</span><span class="sxs-lookup"><span data-stu-id="8823b-105">Prerequisites</span></span>

-   <span data-ttu-id="8823b-106">Jums ir [Omnisend konts](https://www.omnisend.com/) un atbilstošie administratora akreditācijas dati.</span><span class="sxs-lookup"><span data-stu-id="8823b-106">You have an [Omnisend account](https://www.omnisend.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="8823b-107">Jums ir [konfigurēti segmenti](segments.md) auditorijas ieskatos.</span><span class="sxs-lookup"><span data-stu-id="8823b-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="8823b-108">Eksportētajos segmentos vienotajiem klientu profiliem ir lauks, kas norāda e-pasta adresi.</span><span class="sxs-lookup"><span data-stu-id="8823b-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="8823b-109">Zināmie ierobežojumi</span><span class="sxs-lookup"><span data-stu-id="8823b-109">Known limitations</span></span>

- <span data-ttu-id="8823b-110">Uz Omnisend var eksportēt līdz pat 1 miljonam profilu, un tas var ilgt līdz 4 stundām.</span><span class="sxs-lookup"><span data-stu-id="8823b-110">You can export up to 1 million profiles per export to Omnisend and it can take up to 4 hours to complete.</span></span>
- <span data-ttu-id="8823b-111">Eksportēšana uz Omnisend attiecas tikai uz segmentiem.</span><span class="sxs-lookup"><span data-stu-id="8823b-111">Exporting to Omnisend is limited to segments.</span></span>
- <span data-ttu-id="8823b-112">Uz Omnisend var eksportēt profilus, kas ir atkarīgi no jūsu līguma ar Omnisend.</span><span class="sxs-lookup"><span data-stu-id="8823b-112">The number of profiles that you can export to Omnisend depends on your contract with Omnisend.</span></span>

## <a name="set-up-connection-to-omnisend"></a><span data-ttu-id="8823b-113">Savienojuma ar Omnisend iestatīšana</span><span class="sxs-lookup"><span data-stu-id="8823b-113">Set up connection to Omnisend</span></span>

1. <span data-ttu-id="8823b-114">Dodieties uz **Administrators** > **Savienojumi**.</span><span class="sxs-lookup"><span data-stu-id="8823b-114">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="8823b-115">Atlasiet vienumu **Pievienot savienojumu** un atlasiet **Omnisend**, lai konfigurētu savienojumu.</span><span class="sxs-lookup"><span data-stu-id="8823b-115">Select **Add connection** and choose **Omnisend** to configure the connection.</span></span>

1. <span data-ttu-id="8823b-116">Laukā **Parādāmais nosaukums** piešķiriet savienojumam atpazīstamu nosaukumu.</span><span class="sxs-lookup"><span data-stu-id="8823b-116">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="8823b-117">Parādāmais nosaukums un nosaukuma veids raksturo šo savienojumu.</span><span class="sxs-lookup"><span data-stu-id="8823b-117">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="8823b-118">Ir ieteicams izvēlēties nosaukumu, kas paskaidro savienojuma nolūku.</span><span class="sxs-lookup"><span data-stu-id="8823b-118">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="8823b-119">Izvēlieties, kurš var izmantot šo savienojumu.</span><span class="sxs-lookup"><span data-stu-id="8823b-119">Choose who can use this connection.</span></span> <span data-ttu-id="8823b-120">Pēc noklusējuma ir tikai administratori.</span><span class="sxs-lookup"><span data-stu-id="8823b-120">By default it's only administrators.</span></span> <span data-ttu-id="8823b-121">Papildinformāciju skatiet rakstā [Atļaut līdzstrādniekiem izmantot savienojumu eksportam](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="8823b-121">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="8823b-122">Ievadiet savu [Omnisend API atslēgu](https://support.omnisend.com/en/articles/1061890-generating-api-key).</span><span class="sxs-lookup"><span data-stu-id="8823b-122">Enter your [Omnisend API key](https://support.omnisend.com/en/articles/1061890-generating-api-key).</span></span>

1. <span data-ttu-id="8823b-123">Atlasiet **Piekrītu**, lai apstiprinātu **Datu konfidencialitāti un atbilstību**.</span><span class="sxs-lookup"><span data-stu-id="8823b-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="8823b-124">Lai uzsāktu savienojumu ar Omnisend, atlasiet **Savienot**.</span><span class="sxs-lookup"><span data-stu-id="8823b-124">Select **Connect** to initialize the connection to Omnisend.</span></span>

1. <span data-ttu-id="8823b-125">Atlasiet opciju **Pievienot sevi kā eksporta lietotāju** un sniedziet savus Customer Insights akreditācijas datus.</span><span class="sxs-lookup"><span data-stu-id="8823b-125">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="8823b-126">Lai pabeigtu savienošanu, atlasiet **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="8823b-126">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="8823b-127">Eksporta konfigurēšana</span><span class="sxs-lookup"><span data-stu-id="8823b-127">Configure an export</span></span>

<span data-ttu-id="8823b-128">Šo eksportu varat konfigurēt, ja jums ir piekļuve šā veida pieslēgumam.</span><span class="sxs-lookup"><span data-stu-id="8823b-128">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="8823b-129">Papildinformāciju skatiet rakstā [Atļaujas, kas nepieciešamas eksporta konfigurēšanai](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="8823b-129">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="8823b-130">Pārejiet uz **Dati** > **Eksportēšana**.</span><span class="sxs-lookup"><span data-stu-id="8823b-130">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="8823b-131">Lai izveidotu jaunu eksportu, atlasiet **Pievienot galamērķi**.</span><span class="sxs-lookup"><span data-stu-id="8823b-131">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="8823b-132">Laukā **Savienošana eksportam** atlasiet savienojumu no sadaļas Omnisend.</span><span class="sxs-lookup"><span data-stu-id="8823b-132">In the **Connection for export** field, choose a connection from the Omnisend section.</span></span> <span data-ttu-id="8823b-133">Ja šis sadaļas nosaukums nav redzams, šāda veida savienojumi jums nav pieejami.</span><span class="sxs-lookup"><span data-stu-id="8823b-133">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="8823b-134">Sadaļas **Datu atbilstības** laukā **E-pasts** atlasiet lauku, kas iekļauts vienotajā klientu profilā, kas pārstāv klienta e-pasta adresi.</span><span class="sxs-lookup"><span data-stu-id="8823b-134">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="8823b-135">Segmenti ir obligāti jāeksportē uz Omnisend.</span><span class="sxs-lookup"><span data-stu-id="8823b-135">It's required to export segments to Omnisend.</span></span> <span data-ttu-id="8823b-136">Ja vēlaties, varat eksportēt Vārdu, Uzvārdu, Pilsētu, Pavalsti un Valsti/reģionu, lai izveidotu personalizētākus e-pastus.</span><span class="sxs-lookup"><span data-stu-id="8823b-136">Optionally, you can export First name, Last name, Address, Country/Region, State, City, and Post Code to create more personalized emails.</span></span> <span data-ttu-id="8823b-137">Atlasiet **Pievienot atribūtu**, lai kartētu šos laukus.</span><span class="sxs-lookup"><span data-stu-id="8823b-137">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="8823b-138">Atlasiet vienumu **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="8823b-138">Select **Save**.</span></span>

<span data-ttu-id="8823b-139">Eksporta saglabāšana automātiski nepalaiž eksportu.</span><span class="sxs-lookup"><span data-stu-id="8823b-139">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="8823b-140">Eksports tiek palaists ar katru [plānoto atsvaidzināšanu](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="8823b-140">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="8823b-141">Varat arī [eksportēt datus pēc pieprasījuma](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="8823b-141">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="8823b-142">Datu konfidencialitāte un atbilstība</span><span class="sxs-lookup"><span data-stu-id="8823b-142">Data privacy and compliance</span></span>

<span data-ttu-id="8823b-143">Iespējojoet Dynamics 365 Customer Insights datu pārnesi uz Omnisend, jūs ļaujat datus pārnest ārpus Dynamics 365 Customer Insights atbilstības robežām, ieskaitot potenciāli sensitīvus datus, tostarp, personas datus.</span><span class="sxs-lookup"><span data-stu-id="8823b-143">When you enable Dynamics 365 Customer Insights to transmit data to Ommisend, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="8823b-144">Microsoft šos datus pārvirzīs atbilstoši jūsu norādījumiem, taču jūs atbildat par to, ka Omnisend atbilst jebkādiem jūsu privātuma vai drošības nosacījumiem.</span><span class="sxs-lookup"><span data-stu-id="8823b-144">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Omnisend meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="8823b-145">Papildinformāciju skatiet rakstā [Microsoft Privātuma paziņojums](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="8823b-145">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="8823b-146">Jūsu Dynamics 365 Customer Insights administrators var noņemt šo eksportēšanas galamērķi jebkurā laikā, lai pārtrauktu izmantot šo funkcionalitāti.</span><span class="sxs-lookup"><span data-stu-id="8823b-146">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
