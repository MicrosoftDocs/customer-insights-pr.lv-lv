---
title: Customer Insights datu eksportēšana uz ActiveCampaign
description: Uzziniet, kā konfigurēt savienojumu un eksportēt uz ActiveCampaign.
ms.date: 06/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6d85fa9836618e27f7f3da6ce17c07b4bc89e187
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314644"
---
# <a name="export-segments-to-activecampaign-preview"></a><span data-ttu-id="92586-103">Segmentu eksportēšana uz ActiveCampaign (priekšskatījums)</span><span class="sxs-lookup"><span data-stu-id="92586-103">Export segments to ActiveCampaign (preview)</span></span>

<span data-ttu-id="92586-104">Eksportējiet vienoto klientu profilu segmentus uz ActiveCampaign un izmantojiet tos mārketinga darbībām.</span><span class="sxs-lookup"><span data-stu-id="92586-104">Export segments of unified customer profiles to ActiveCampaign and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="92586-105">Priekšnosacījumi</span><span class="sxs-lookup"><span data-stu-id="92586-105">Prerequisites</span></span>

-   <span data-ttu-id="92586-106">Jums ir [ActiveCampaign konts](https://www.activecampaign.com/) un atbilstošie administratora akreditācijas dati.</span><span class="sxs-lookup"><span data-stu-id="92586-106">You have an [ActiveCampaign account](https://www.activecampaign.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="92586-107">Jums ir [konfigurēti segmenti](segments.md) auditorijas ieskatos.</span><span class="sxs-lookup"><span data-stu-id="92586-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="92586-108">Eksportētajos segmentos vienoto klientu profilos ir lauks ar e-pasta adresi.</span><span class="sxs-lookup"><span data-stu-id="92586-108">Unified customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="92586-109">Zināmie ierobežojumi</span><span class="sxs-lookup"><span data-stu-id="92586-109">Known limitations</span></span>

- <span data-ttu-id="92586-110">Uz ActiveCampaign vienā reizē var eksportēt līdz 1 miljonam profilu, un tas var ilgt līdz 90 minūtēm.</span><span class="sxs-lookup"><span data-stu-id="92586-110">You can export up to 1 million profiles per export to ActiveCampaign and it can take up to 90 minutes to complete.</span></span>
- <span data-ttu-id="92586-111">Eksportēšana uz ActiveCampaign attiecas tikai uz segmentiem.</span><span class="sxs-lookup"><span data-stu-id="92586-111">Exporting to ActiveCampaign is limited to segments.</span></span>
- <span data-ttu-id="92586-112">Profilu skaits, ko var eksportēt uz ActiveCampaign, ir atkarīgs no jūsu līguma ar ActiveCampaign.</span><span class="sxs-lookup"><span data-stu-id="92586-112">The number of profiles that you can export to ActiveCampaign depends on your contract with ActiveCampaign.</span></span>

## <a name="set-up-connection-to-activecampaign"></a><span data-ttu-id="92586-113">Savienojuma izveide ar ActiveCampaign</span><span class="sxs-lookup"><span data-stu-id="92586-113">Set up connection to ActiveCampaign</span></span>

1. <span data-ttu-id="92586-114">Dodieties uz **Administrators** > **Savienojumi**.</span><span class="sxs-lookup"><span data-stu-id="92586-114">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="92586-115">Atlasiet vienumu **Pievienot savienojumu** un izvēlieties **ActiveCampaign**, lai konfigurētu savienojumu.</span><span class="sxs-lookup"><span data-stu-id="92586-115">Select **Add connection** and choose **ActiveCampaign** to configure the connection.</span></span>

1. <span data-ttu-id="92586-116">Laukā **Parādāmais nosaukums** piešķiriet savienojumam atpazīstamu nosaukumu.</span><span class="sxs-lookup"><span data-stu-id="92586-116">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="92586-117">Parādāmais nosaukums un nosaukuma veids raksturo šo savienojumu.</span><span class="sxs-lookup"><span data-stu-id="92586-117">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="92586-118">Ir ieteicams izvēlēties nosaukumu, kas paskaidro savienojuma nolūku.</span><span class="sxs-lookup"><span data-stu-id="92586-118">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="92586-119">Izvēlieties, kurš var izmantot šo savienojumu.</span><span class="sxs-lookup"><span data-stu-id="92586-119">Choose who can use this connection.</span></span> <span data-ttu-id="92586-120">Pēc noklusējuma tie ir tikai administratori.</span><span class="sxs-lookup"><span data-stu-id="92586-120">By default, it's only administrators.</span></span> <span data-ttu-id="92586-121">Papildinformāciju skatiet rakstā [Atļaut līdzstrādniekiem izmantot savienojumu eksportam](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="92586-121">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="92586-122">Ievadiet savu [ActiveCampaign API atslēgu un REST galapunkta resursdatora nosaukumu](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key).</span><span class="sxs-lookup"><span data-stu-id="92586-122">Enter your [ActiveCampaign API Key and REST Endpoint Hostname](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key).</span></span> <span data-ttu-id="92586-123">REST galapunkta resursdatora nosaukums ir tikai viesošanas nosaukums bez https://.</span><span class="sxs-lookup"><span data-stu-id="92586-123">The REST Endpoint Hostname is the hostname only, without https://.</span></span> 

1. <span data-ttu-id="92586-124">Atlasiet **Piekrītu**, lai apstiprinātu **Datu konfidencialitāti un atbilstību**.</span><span class="sxs-lookup"><span data-stu-id="92586-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="92586-125">Atlasiet **Savienot**, lai uzsāktu savienojuma izveidi ar ActiveCampaign.</span><span class="sxs-lookup"><span data-stu-id="92586-125">Select **Connect** to initialize the connection to ActiveCampaign.</span></span>

1. <span data-ttu-id="92586-126">Atlasiet opciju **Pievienot sevi kā eksporta lietotāju** un sniedziet savus Customer Insights akreditācijas datus.</span><span class="sxs-lookup"><span data-stu-id="92586-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="92586-127">Lai pabeigtu savienošanu, atlasiet **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="92586-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="92586-128">Eksporta konfigurēšana</span><span class="sxs-lookup"><span data-stu-id="92586-128">Configure an export</span></span>

<span data-ttu-id="92586-129">Šo eksportu varat konfigurēt, ja jums ir piekļuve šā veida pieslēgumam.</span><span class="sxs-lookup"><span data-stu-id="92586-129">You can configure an export if you have access to a connection of this type.</span></span> <span data-ttu-id="92586-130">Papildinformāciju skatiet rakstā [Atļaujas, kas nepieciešamas eksporta konfigurēšanai](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="92586-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="92586-131">Pārejiet uz **Dati** > **Eksportēšana**.</span><span class="sxs-lookup"><span data-stu-id="92586-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="92586-132">Lai izveidotu jaunu eksportu, atlasiet **Pievienot galamērķi**.</span><span class="sxs-lookup"><span data-stu-id="92586-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="92586-133">Laukam **Savienojums eksportēšanai** izvēlieties savienojumu no ActiveCampaign sadaļas.</span><span class="sxs-lookup"><span data-stu-id="92586-133">In the **Connection for export** field, choose a connection from the ActiveCampaign section.</span></span> <span data-ttu-id="92586-134">Ja šis sadaļas nosaukums nav redzams, šāda veida savienojumi jums nav pieejami.</span><span class="sxs-lookup"><span data-stu-id="92586-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="92586-135">Ievadiet savu [**ActiveCampaign saraksta ID**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).</span><span class="sxs-lookup"><span data-stu-id="92586-135">Enter your [**ActiveCampaign List ID**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).</span></span>    

3. <span data-ttu-id="92586-136">Sadaļas **Datu atbilstības** laukā **E-pasts** atlasiet lauku, kas iekļauts vienotajā klientu profilā, kas pārstāv klienta e-pasta adresi.</span><span class="sxs-lookup"><span data-stu-id="92586-136">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="92586-137">Tas ir nepieciešams, lai eksportētu segmentus uz ActiveCampaign.</span><span class="sxs-lookup"><span data-stu-id="92586-137">It's required to export segments to ActiveCampaign.</span></span> <span data-ttu-id="92586-138">Pēc izvēles, varat eksportēt vārdu, uzvārdu un tālruņa numuru, lai izveidotu personalizētākus e-pasta ziņojumus.</span><span class="sxs-lookup"><span data-stu-id="92586-138">Optionally, you can export First name, Last name, and Phone to create more personalized emails.</span></span> <span data-ttu-id="92586-139">Atlasiet Pievienot atribūtu, lai kartētu šos laukus.</span><span class="sxs-lookup"><span data-stu-id="92586-139">Select Add attribute to map these fields.</span></span>

1. <span data-ttu-id="92586-140">Atlasiet vienumu **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="92586-140">Select **Save**.</span></span>

<span data-ttu-id="92586-141">Eksporta saglabāšana automātiski nepalaiž eksportu.</span><span class="sxs-lookup"><span data-stu-id="92586-141">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="92586-142">Eksports tiek palaists ar katru [plānoto atsvaidzināšanu](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="92586-142">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="92586-143">Varat arī [eksportēt datus pēc pieprasījuma](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="92586-143">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="92586-144">Datu konfidencialitāte un atbilstība</span><span class="sxs-lookup"><span data-stu-id="92586-144">Data privacy and compliance</span></span>

<span data-ttu-id="92586-145">Iespējojot Dynamics 365 Customer Insights datu pārsūtīšanai uz ActiveCampaign, jūs atļaujat datu pārsūtīšanu ārpus atbilstības robežas, kas paredzēta Dynamics 365 Customer Insights, ieskaitot potenciāli sensitīvus datus, piemēram, personas datus.</span><span class="sxs-lookup"><span data-stu-id="92586-145">When you enable Dynamics 365 Customer Insights to transmit data to ActiveCampaign, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="92586-146">Microsoft šos datus pārsūtīs pēc jūsu norādījuma, bet jūs esat atbildīgs par to, lai ActiveCampaign atbilstu visām jūsu konfidencialitātes vai drošības saistībām.</span><span class="sxs-lookup"><span data-stu-id="92586-146">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that ActiveCampaign meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="92586-147">Papildinformāciju skatiet rakstā [Microsoft Privātuma paziņojums](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="92586-147">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="92586-148">Jūsu Dynamics 365 Customer Insights administrators var noņemt šo eksportēšanas galamērķi jebkurā laikā, lai pārtrauktu izmantot šo funkcionalitāti.</span><span class="sxs-lookup"><span data-stu-id="92586-148">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
