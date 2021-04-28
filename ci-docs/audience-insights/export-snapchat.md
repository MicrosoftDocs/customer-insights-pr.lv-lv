---
title: Customer Insights datu eksportēšana uz Snapchat
description: Uzziniet, kā konfigurēt savienojumu un eksportēt uz Snapchat.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d3dae7f0fef1fc3792c90c8ac0d3b037f5c0923d
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760580"
---
# <a name="export-segment-lists-to-snapchat-preview"></a><span data-ttu-id="75e64-103">Segmentu sarakstu eksportēšana uz Snapchat (priekšskatījums)</span><span class="sxs-lookup"><span data-stu-id="75e64-103">Export segment lists to Snapchat (preview)</span></span>

<span data-ttu-id="75e64-104">Eksportējiet vienoto klientu profilu segmentus uz Snapchat un izmantojiet tos reklāmā.</span><span class="sxs-lookup"><span data-stu-id="75e64-104">Export segments of unified customer profiles to Snapchat and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="75e64-105">Savienojuma priekšnosacījumi</span><span class="sxs-lookup"><span data-stu-id="75e64-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="75e64-106">Jums ir [Snapchat Business konts](https://business.snapchat.com/), [Snapchat Ads konts](https://ads.snapchat.com/) un atbilstošie administratora akreditācijas dati.</span><span class="sxs-lookup"><span data-stu-id="75e64-106">You have a [Snapchat Business account](https://business.snapchat.com/), a [Snapchat Ads account](https://ads.snapchat.com/), and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="75e64-107">Jums ir [konfigurēti segmenti](segments.md) auditorijas ieskatos.</span><span class="sxs-lookup"><span data-stu-id="75e64-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="75e64-108">Eksportētajos segmentos vienotajiem klientu profiliem ir lauks, kas norāda e-pasta adresi.</span><span class="sxs-lookup"><span data-stu-id="75e64-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="75e64-109">Zināmie ierobežojumi</span><span class="sxs-lookup"><span data-stu-id="75e64-109">Known limitations</span></span>

- <span data-ttu-id="75e64-110">Eksportēšana uz Snapchat attiecas tikai uz segmentiem.</span><span class="sxs-lookup"><span data-stu-id="75e64-110">Exporting to Snapchat is limited to segments.</span></span>
- <span data-ttu-id="75e64-111">Līdz 1 miljona profilu eksportēšana uz Snapchat var aizņemt līdz 15 minūtēm.</span><span class="sxs-lookup"><span data-stu-id="75e64-111">Exporting up to 1 million profiles to Snapchat can take up to 15 minutes to complete.</span></span> 

## <a name="set-up-connection-to-snapchat"></a><span data-ttu-id="75e64-112">Savienojuma ar Snapchat iestatīšana</span><span class="sxs-lookup"><span data-stu-id="75e64-112">Set up connection to Snapchat</span></span>

1. <span data-ttu-id="75e64-113">Dodieties uz **Administrators** > **Savienojumi**.</span><span class="sxs-lookup"><span data-stu-id="75e64-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="75e64-114">Atlasiet vienumu **Pievienot savienojumu** un atlasiet **Snapchat**, lai konfigurētu savienojumu.</span><span class="sxs-lookup"><span data-stu-id="75e64-114">Select **Add connection** and choose **Snapchat** to configure the connection.</span></span>

1. <span data-ttu-id="75e64-115">Laukā **Parādāmais nosaukums** piešķiriet savienojumam atpazīstamu nosaukumu.</span><span class="sxs-lookup"><span data-stu-id="75e64-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="75e64-116">Parādāmais nosaukums un nosaukuma veids raksturo šo savienojumu.</span><span class="sxs-lookup"><span data-stu-id="75e64-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="75e64-117">Ir ieteicams izvēlēties nosaukumu, kas paskaidro savienojuma nolūku.</span><span class="sxs-lookup"><span data-stu-id="75e64-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="75e64-118">Izvēlieties, kurš var izmantot šo savienojumu.</span><span class="sxs-lookup"><span data-stu-id="75e64-118">Choose who can use this connection.</span></span> <span data-ttu-id="75e64-119">Ja nesāksit nekādas darbības, noklusējums būs Administratori.</span><span class="sxs-lookup"><span data-stu-id="75e64-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="75e64-120">Papildinformāciju skatiet rakstā [Atļaut līdzstrādniekiem izmantot savienojumu eksportam](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="75e64-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="75e64-121">Atlasiet **Piekrītu**, lai apstiprinātu **Datu konfidencialitāti un atbilstību**.</span><span class="sxs-lookup"><span data-stu-id="75e64-121">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="75e64-122">Lai uzsāktu savienojumu ar Snapchat, atlasiet **Savienot**.</span><span class="sxs-lookup"><span data-stu-id="75e64-122">Select **Connect** to initialize the connection to Snapchat.</span></span>

1. <span data-ttu-id="75e64-123">Atlasiet **Autentificēt ar Snapchat** un norādiet savus Snapchat administratora akreditācijas datus.</span><span class="sxs-lookup"><span data-stu-id="75e64-123">Select **Authenticate with Snapchat** and provide your admin credentials for Snapchat.</span></span> 

1. <span data-ttu-id="75e64-124">Atlasiet opciju **Pievienot sevi kā eksporta lietotāju** un sniedziet savus Customer Insights akreditācijas datus.</span><span class="sxs-lookup"><span data-stu-id="75e64-124">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="75e64-125">Lai pabeigtu savienošanu, atlasiet **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="75e64-125">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="75e64-126">Eksporta konfigurēšana</span><span class="sxs-lookup"><span data-stu-id="75e64-126">Configure an export</span></span>

<span data-ttu-id="75e64-127">Šo eksportu varat konfigurēt, ja jums ir piekļuve šā veida pieslēgumam.</span><span class="sxs-lookup"><span data-stu-id="75e64-127">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="75e64-128">Papildinformāciju skatiet rakstā [Atļaujas, kas nepieciešamas eksporta konfigurēšanai](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="75e64-128">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="75e64-129">Pārejiet uz **Dati** > **Eksportēšana**.</span><span class="sxs-lookup"><span data-stu-id="75e64-129">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="75e64-130">Lai izveidotu jaunu eksportu, atlasiet **Pievienot galamērķi**.</span><span class="sxs-lookup"><span data-stu-id="75e64-130">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="75e64-131">Laukā **Savienošana eksportam** atlasiet savienojumu no sadaļas Snapchat.</span><span class="sxs-lookup"><span data-stu-id="75e64-131">In the **Connection for export** field, choose a connection from the Snapchat section.</span></span> <span data-ttu-id="75e64-132">Ja šis sadaļas nosaukums nav redzams, šāda veida savienojumi jums nav pieejami.</span><span class="sxs-lookup"><span data-stu-id="75e64-132">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="75e64-133">Ievadiet [**Snapchat auditorijas ID**](https://businesshelp.snapchat.com/s/article/custom-audiences).</span><span class="sxs-lookup"><span data-stu-id="75e64-133">Enter the [**Snapchat Audience ID**](https://businesshelp.snapchat.com/s/article/custom-audiences).</span></span>

1. <span data-ttu-id="75e64-134">Sadaļas **Datu atbilstības** laukā **E-pasts** atlasiet lauku, kas iekļauts vienotajā klientu profilā, kas pārstāv klienta e-pasta adresi.</span><span class="sxs-lookup"><span data-stu-id="75e64-134">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="75e64-135">Segmenti ir obligāti jāeksportē uz Snapchat.</span><span class="sxs-lookup"><span data-stu-id="75e64-135">It's required to export segments to Snapchat.</span></span>

1. <span data-ttu-id="75e64-136">Atlasiet segmentus, kurus vēlaties eksportēt.</span><span class="sxs-lookup"><span data-stu-id="75e64-136">Select the segments you want to export.</span></span> 

1. <span data-ttu-id="75e64-137">Atlasiet vienumu **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="75e64-137">Select **Save**.</span></span>

<span data-ttu-id="75e64-138">Eksporta saglabāšana automātiski nepalaiž eksportu.</span><span class="sxs-lookup"><span data-stu-id="75e64-138">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="75e64-139">Eksports tiek palaists ar katru [plānoto atsvaidzināšanu](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="75e64-139">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="75e64-140">Varat arī [eksportēt datus pēc pieprasījuma](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="75e64-140">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="75e64-141">Datu konfidencialitāte un atbilstība</span><span class="sxs-lookup"><span data-stu-id="75e64-141">Data privacy and compliance</span></span>

<span data-ttu-id="75e64-142">Iespējojiet Dynamics 365 Customer Insights datu pārnesi uz Snapchat, jūs ļaujat datus pārnest ārpus Dynamics 365 Customer Insights atbilstības robežām, ieskaitot potenciāli sensitīvus datus, tostarp, personas datus.</span><span class="sxs-lookup"><span data-stu-id="75e64-142">When you enable Dynamics 365 Customer Insights to transmit data to Snapchat, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="75e64-143">Microsoft šos datus pārvirzīs atbilstoši jūsu norādījumiem, taču jūs atbildat par to, ka Snapchat atbilst jebkādiem jūsu privātuma vai drošības nosacījumiem.</span><span class="sxs-lookup"><span data-stu-id="75e64-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Snapchat meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="75e64-144">Papildinformāciju skatiet rakstā [Microsoft Privātuma paziņojums](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="75e64-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="75e64-145">Jūsu Dynamics 365 Customer Insights administrators var noņemt šo eksportēšanas galamērķi jebkurā laikā, lai pārtrauktu izmantot šo funkcionalitāti.</span><span class="sxs-lookup"><span data-stu-id="75e64-145">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
