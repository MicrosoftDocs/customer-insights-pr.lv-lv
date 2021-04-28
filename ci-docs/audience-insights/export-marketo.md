---
title: Customer Insights datu eksportēšana uz Marketo
description: Uzziniet, kā konfigurēt savienojumu un eksportēt uz Marketo.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 01290d5fae7af1737b73373d75e334ae1ed67d37
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759830"
---
# <a name="export-segments-to-marketo-preview"></a><span data-ttu-id="78ad4-103">Segmentu eksportēšana uz Marketo (priekšskatījums)</span><span class="sxs-lookup"><span data-stu-id="78ad4-103">Export segments to Marketo (preview)</span></span>

<span data-ttu-id="78ad4-104">Izmantojiet pakalpojumā Customer Insights izveidotos segmentus kampaņu veidošanai, e-pasta mārketinga sniegšanai un specifisku klientu grupu atlases iespējas pakalpojumā Marketo.</span><span class="sxs-lookup"><span data-stu-id="78ad4-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Marketo.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="78ad4-105">Savienojuma priekšnosacījumi</span><span class="sxs-lookup"><span data-stu-id="78ad4-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="78ad4-106">Jums ir [Marketo konts](https://login.marketo.com/) un atbilstošie administratora akreditācijas dati.</span><span class="sxs-lookup"><span data-stu-id="78ad4-106">You have a [Marketo account](https://login.marketo.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="78ad4-107">Marketo ir esošas auditorijas un attiecīgie ID.</span><span class="sxs-lookup"><span data-stu-id="78ad4-107">There are existing lists in Marketo and the corresponding IDs.</span></span> <span data-ttu-id="78ad4-108">Lai iegūtu papildinformāciju, skatiet [Marketo sarakstus](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="78ad4-108">For more information, see [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>
-   <span data-ttu-id="78ad4-109">Jums ir [konfigurēti segmenti](segments.md).</span><span class="sxs-lookup"><span data-stu-id="78ad4-109">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="78ad4-110">Eksportētajos segmentos vienotajiem klientu profiliem ir lauks, kas norāda e-pasta adresi.</span><span class="sxs-lookup"><span data-stu-id="78ad4-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="78ad4-111">Zināmie ierobežojumi</span><span class="sxs-lookup"><span data-stu-id="78ad4-111">Known limitations</span></span>

- <span data-ttu-id="78ad4-112">Līdz 1 000 000 profilu, eksportējot uz Marketo.</span><span class="sxs-lookup"><span data-stu-id="78ad4-112">Up to 1 million profiles per export to Marketo.</span></span>
- <span data-ttu-id="78ad4-113">Eksportēšana uz Marketo ir ierobežota līdz segmentiem.</span><span class="sxs-lookup"><span data-stu-id="78ad4-113">Exporting to Marketo is limited to segments.</span></span>
- <span data-ttu-id="78ad4-114">Eksportējot segmentus kopā ar 1 000 000 profiliem, var būt nepieciešamas 3 stundas.</span><span class="sxs-lookup"><span data-stu-id="78ad4-114">Exporting segments with a total of 1 million profiles can take up to 3 hours.</span></span> 
- <span data-ttu-id="78ad4-115">To profilu skaits, ko var eksportēt uz Marketo, ir atkarīgs, un tas ir ierobežots jūsu līgumā ar Marketo.</span><span class="sxs-lookup"><span data-stu-id="78ad4-115">The number of profiles that you can export to Marketo is dependent and limited on your contract with Marketo.</span></span>

## <a name="set-up-connection-to-marketo"></a><span data-ttu-id="78ad4-116">Savienojuma ar Marketo iestatīšana</span><span class="sxs-lookup"><span data-stu-id="78ad4-116">Set up connection to Marketo</span></span>

1. <span data-ttu-id="78ad4-117">Dodieties uz **Administrators** > **Savienojumi**.</span><span class="sxs-lookup"><span data-stu-id="78ad4-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="78ad4-118">Atlasiet vienumu **Pievienot savienojumu** un atlasiet **Marketo**, lai konfigurētu savienojumu.</span><span class="sxs-lookup"><span data-stu-id="78ad4-118">Select **Add connection** and choose **Marketo** to configure the connection.</span></span>

1. <span data-ttu-id="78ad4-119">Laukā **Parādāmais nosaukums** piešķiriet savienojumam atpazīstamu nosaukumu.</span><span class="sxs-lookup"><span data-stu-id="78ad4-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="78ad4-120">Parādāmais nosaukums un nosaukuma veids raksturo šo savienojumu.</span><span class="sxs-lookup"><span data-stu-id="78ad4-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="78ad4-121">Ir ieteicams izvēlēties nosaukumu, kas paskaidro savienojuma nolūku.</span><span class="sxs-lookup"><span data-stu-id="78ad4-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="78ad4-122">Izvēlieties, kurš var izmantot šo savienojumu.</span><span class="sxs-lookup"><span data-stu-id="78ad4-122">Choose who can use this connection.</span></span> <span data-ttu-id="78ad4-123">Ja nesāksit nekādas darbības, noklusējums būs Administratori.</span><span class="sxs-lookup"><span data-stu-id="78ad4-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="78ad4-124">Papildinformāciju skatiet rakstā [Atļaut līdzstrādniekiem izmantot savienojumu eksportam](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="78ad4-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="78ad4-125">Ievadiet savu **[Marketo klienta ID, klienta slepeno vārdu un REST galapunktu resursdatorā](https://developers.marketo.com/rest-api/authentication/)**.</span><span class="sxs-lookup"><span data-stu-id="78ad4-125">Enter your **[Marketo client ID, Client secret, and REST Endpoint Hostname](https://developers.marketo.com/rest-api/authentication/)**.</span></span>

1. <span data-ttu-id="78ad4-126">Atlasiet **Es piekrītu**, lai apstiprinātu **Datu konfidencialitāti un atbilstību**, un atlasiet opciju **Izveidot savienojumu**, lai inicializētu savienojumu ar Marketo.</span><span class="sxs-lookup"><span data-stu-id="78ad4-126">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Marketo.</span></span>

1. <span data-ttu-id="78ad4-127">Atlasiet opciju **Pievienot sevi kā eksporta lietotāju** un sniedziet savus Customer Insights akreditācijas datus.</span><span class="sxs-lookup"><span data-stu-id="78ad4-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="78ad4-128">Lai pabeigtu savienošanu, atlasiet **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="78ad4-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="78ad4-129">Eksporta konfigurēšana</span><span class="sxs-lookup"><span data-stu-id="78ad4-129">Configure an export</span></span>

<span data-ttu-id="78ad4-130">Šo eksportu varat konfigurēt, ja jums ir piekļuve šā veida pieslēgumam.</span><span class="sxs-lookup"><span data-stu-id="78ad4-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="78ad4-131">Papildinformāciju skatiet rakstā [Atļaujas, kas nepieciešamas eksporta konfigurēšanai](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="78ad4-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="78ad4-132">Pārejiet uz **Dati** > **Eksportēšana**.</span><span class="sxs-lookup"><span data-stu-id="78ad4-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="78ad4-133">Lai izveidotu jaunu eksportu, atlasiet **Pievienot galamērķi**.</span><span class="sxs-lookup"><span data-stu-id="78ad4-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="78ad4-134">Laukā **Savienošana eksportam** atlasiet savienojumu no sadaļas Marketo.</span><span class="sxs-lookup"><span data-stu-id="78ad4-134">In the **Connection for export** field, choose a connection from the Marketo section.</span></span> <span data-ttu-id="78ad4-135">Ja šis sadaļas nosaukums nav redzams, šāda veida savienojumi jums nav pieejami.</span><span class="sxs-lookup"><span data-stu-id="78ad4-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="78ad4-136">Ievadiet savu **[Marketo saraksta ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span><span class="sxs-lookup"><span data-stu-id="78ad4-136">Enter your **[Marketo list ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span></span> 

1. <span data-ttu-id="78ad4-137">Sadaļas **Datu atbilstības** laukā **E-pasts** atlasiet lauku, kas iekļauts vienotajā klientu profilā, kas pārstāv klienta e-pasta adresi.</span><span class="sxs-lookup"><span data-stu-id="78ad4-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="78ad4-138">Ja vēlaties, varat eksportēt **Vārdu**, **Uzvārdu**, **Pilsētu**, **Pavalsti** un **Valsti/reģionu**, lai izveidotu personalizētākus e-pastus.</span><span class="sxs-lookup"><span data-stu-id="78ad4-138">Optionally, you can export **First name**, **Last name**, **City**, **State**, and **Country/Region**  to create more personalized emails.</span></span> <span data-ttu-id="78ad4-139">Atlasiet **Pievienot atribūtu**, lai kartētu šos laukus.</span><span class="sxs-lookup"><span data-stu-id="78ad4-139">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="78ad4-140">Atlasiet segmentus, kurus vēlaties eksportēt.</span><span class="sxs-lookup"><span data-stu-id="78ad4-140">Select the segments you want to export.</span></span> <span data-ttu-id="78ad4-141">Kopsummā var eksportēt līdz 1 000 000 klientu profilu uz Marketo.</span><span class="sxs-lookup"><span data-stu-id="78ad4-141">You can export up to 1 million customer profiles in total to Marketo.</span></span>

1. <span data-ttu-id="78ad4-142">Atlasiet vienumu **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="78ad4-142">Select **Save**.</span></span>

<span data-ttu-id="78ad4-143">Eksporta saglabāšana automātiski nepalaiž eksportu.</span><span class="sxs-lookup"><span data-stu-id="78ad4-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="78ad4-144">Eksports tiek palaists ar katru [plānoto atsvaidzināšanu](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="78ad4-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="78ad4-145">Varat arī [eksportēt datus pēc pieprasījuma](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="78ad4-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="78ad4-146">Marketo tagad varat atrast jūsu segmentus sadaļā [Marketo saraksti](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="78ad4-146">In Marketo, you can now find your segments under [Marketo lists](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="78ad4-147">Datu konfidencialitāte un atbilstība</span><span class="sxs-lookup"><span data-stu-id="78ad4-147">Data privacy and compliance</span></span>

<span data-ttu-id="78ad4-148">Ja iespējojat Dynamics 365 Customer Insights datu pārsūtīšanu uz Marketo, jūs atļaujat datu pārsūtīšanu ārpus atbilstības robežām Dynamics 365 Customer Insights, ieskaitot iespējami sensitīvus datus, piemēram, personas datus.</span><span class="sxs-lookup"><span data-stu-id="78ad4-148">When you enable Dynamics 365 Customer Insights to transmit data to Marketo, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="78ad4-149">Microsoft šos datus pārsūtīs pēc jūsu norādēm, bet jūs esat atbildīgs par to, lai nodrošinātu Marketo atbilstību konfidencialitātes vai drošības saistībām, kas jums varētu rasties.</span><span class="sxs-lookup"><span data-stu-id="78ad4-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Marketo meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="78ad4-150">Papildinformāciju skatiet rakstā [Microsoft Privātuma paziņojums](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="78ad4-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="78ad4-151">Jūsu Dynamics 365 Customer Insights administrators var noņemt šo eksportēšanas galamērķi jebkurā laikā, lai pārtrauktu izmantot šo funkcionalitāti.</span><span class="sxs-lookup"><span data-stu-id="78ad4-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]