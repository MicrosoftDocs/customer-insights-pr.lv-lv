---
title: Customer Insights datu eksportēšana Microsoft Advertising
description: Uzziniet, kā konfigurēt savienojumu un eksportēt uz Microsoft Advertising.
ms.date: 05/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c2ac92de2718cf7f0622b407bf198a7a7e50a37b
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124519"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a><span data-ttu-id="1ae70-103">Segmentu eksportēšana uz Microsoft Advertising (priekšskatījums)</span><span class="sxs-lookup"><span data-stu-id="1ae70-103">Export segments to Microsoft Advertising (preview)</span></span>

<span data-ttu-id="1ae70-104">Eksportēt Customer Insights segmentus uz Microsoft Advertising, lai izveidotu Customer Match auditorijas.</span><span class="sxs-lookup"><span data-stu-id="1ae70-104">Export Customer Insights segments to Microsoft Advertising to create Customer Match audiences.</span></span> <span data-ttu-id="1ae70-105">Izmantojiet šīs mērķauditorijas savām reklāmu kampaņām.</span><span class="sxs-lookup"><span data-stu-id="1ae70-105">Use these audiences for your ad campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1ae70-106">Priekšnosacījumi</span><span class="sxs-lookup"><span data-stu-id="1ae70-106">Prerequisites</span></span>

-   <span data-ttu-id="1ae70-107">[Microsoft Advertising konts](https://ads.microsoft.com/) un atbilstošie administratora akreditācijas dati.</span><span class="sxs-lookup"><span data-stu-id="1ae70-107">An [Microsoft Advertising account](https://ads.microsoft.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="1ae70-108">Jūs esat piekritis Customer Match lietošanas noteikumiem.</span><span class="sxs-lookup"><span data-stu-id="1ae70-108">You've accepted the Customer Match terms of use.</span></span> 
-   <span data-ttu-id="1ae70-109">[Konfigurēti segmenti](segments.md) Audience Insights.</span><span class="sxs-lookup"><span data-stu-id="1ae70-109">[Configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="1ae70-110">Eksportētajos segmentos vienoto klientu profilos ir lauks ar e-pasta adresi.</span><span class="sxs-lookup"><span data-stu-id="1ae70-110">Unified customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="1ae70-111">Zināmie ierobežojumi</span><span class="sxs-lookup"><span data-stu-id="1ae70-111">Known limitations</span></span>

- <span data-ttu-id="1ae70-112">Jūs varat eksportēt līdz 500 000 profilu katrā Microsoft Advertising eksportēšanas darbībā.</span><span class="sxs-lookup"><span data-stu-id="1ae70-112">You can export up to 500 K profiles per export to Microsoft Advertising.</span></span>
- <span data-ttu-id="1ae70-113">Eksportēšana uz Microsoft Advertising attiecas tikai uz segmentiem.</span><span class="sxs-lookup"><span data-stu-id="1ae70-113">Exporting to Microsoft Advertising is limited to segments.</span></span>
- <span data-ttu-id="1ae70-114">Līdz 500 000 profilu eksportēšana uz Microsoft Advertising var aizņemt līdz 10 minūtēm.</span><span class="sxs-lookup"><span data-stu-id="1ae70-114">Exporting up to 500 K profiles to Microsoft Advertising can take up to 10 minutes to complete.</span></span> 


## <a name="set-up-the-connection-to-microsoft-advertising"></a><span data-ttu-id="1ae70-115">Iestatiet savienojumu ar Microsoft Advertising</span><span class="sxs-lookup"><span data-stu-id="1ae70-115">Set up the connection to Microsoft Advertising</span></span>

1. <span data-ttu-id="1ae70-116">Dodieties uz **Administrators** > **Savienojumi**.</span><span class="sxs-lookup"><span data-stu-id="1ae70-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="1ae70-117">Atlasiet vienumu **Pievienot savienojumu** un atlasiet **Microsoft Advertising**, lai konfigurētu savienojumu.</span><span class="sxs-lookup"><span data-stu-id="1ae70-117">Select **Add connection** and choose **Microsoft Advertising** to configure the connection.</span></span>

1. <span data-ttu-id="1ae70-118">Laukā **Parādāmais nosaukums** piešķiriet savienojumam atpazīstamu nosaukumu.</span><span class="sxs-lookup"><span data-stu-id="1ae70-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="1ae70-119">Parādāmais nosaukums un nosaukuma veids raksturo šo savienojumu.</span><span class="sxs-lookup"><span data-stu-id="1ae70-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="1ae70-120">Ir ieteicams izvēlēties nosaukumu, kas paskaidro savienojuma nolūku.</span><span class="sxs-lookup"><span data-stu-id="1ae70-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="1ae70-121">Izvēlieties, kurš var izmantot šo savienojumu.</span><span class="sxs-lookup"><span data-stu-id="1ae70-121">Choose who can use this connection.</span></span> <span data-ttu-id="1ae70-122">Noklusējums ir administratori.</span><span class="sxs-lookup"><span data-stu-id="1ae70-122">The default is administrators.</span></span> <span data-ttu-id="1ae70-123">Papildinformāciju skatiet rakstā [Atļaut līdzstrādniekiem izmantot savienojumu eksportam](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="1ae70-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="1ae70-124">Atlasiet **Piekrītu**, lai apstiprinātu **Datu konfidencialitāti un atbilstību**.</span><span class="sxs-lookup"><span data-stu-id="1ae70-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="1ae70-125">Lai uzsāktu savienojumu ar Microsoft Advertising, atlasiet **Savienot**.</span><span class="sxs-lookup"><span data-stu-id="1ae70-125">Select **Connect** to initialize the connection to Microsoft Advertising.</span></span>

1. <span data-ttu-id="1ae70-126">Atlasiet **Autentificēties ar Microsoft Advertising** un norādiet savus Microsoft Advertising administratora akreditācijas datus.</span><span class="sxs-lookup"><span data-stu-id="1ae70-126">Select **Authenticate with Microsoft Advertising** and provide your admin credentials for Microsoft Advertising.</span></span>

1. <span data-ttu-id="1ae70-127">Atlasiet opciju **Pievienot sevi kā eksporta lietotāju** un sniedziet savus Customer Insights akreditācijas datus.</span><span class="sxs-lookup"><span data-stu-id="1ae70-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="1ae70-128">Lai pabeigtu savienošanu, atlasiet **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="1ae70-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="1ae70-129">Eksporta konfigurēšana</span><span class="sxs-lookup"><span data-stu-id="1ae70-129">Configure an export</span></span>

<span data-ttu-id="1ae70-130">Šo eksportu varat konfigurēt, ja jums ir piekļuve šā veida pieslēgumam.</span><span class="sxs-lookup"><span data-stu-id="1ae70-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="1ae70-131">Papildinformāciju skatiet rakstā [Atļaujas, kas nepieciešamas eksporta konfigurēšanai](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="1ae70-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="1ae70-132">Pārejiet uz **Dati** > **Eksportēšana**.</span><span class="sxs-lookup"><span data-stu-id="1ae70-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="1ae70-133">Lai izveidotu jaunu eksportu, atlasiet **Pievienot galamērķi**.</span><span class="sxs-lookup"><span data-stu-id="1ae70-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="1ae70-134">Laukā **Savienošana eksportam** atlasiet savienojumu no sadaļas Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="1ae70-134">In the **Connection for export** field, choose a connection from the Microsoft Advertising section.</span></span> <span data-ttu-id="1ae70-135">Ja šis sadaļas nosaukums nav redzams, šāda veida savienojumi jums nav pieejami.</span><span class="sxs-lookup"><span data-stu-id="1ae70-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="1ae70-136">Atlasiet eksportējamos segmentus.</span><span class="sxs-lookup"><span data-stu-id="1ae70-136">Select the segments to export.</span></span> <span data-ttu-id="1ae70-137">Klientu atbilstības auditorijas programmā Microsoft Advertising tiek automātiski izveidotas ar eksportēšanai atlasīto segmentu nosaukumu.</span><span class="sxs-lookup"><span data-stu-id="1ae70-137">The Customer Match audiences in Microsoft Advertising are automatically created with the name of the segments selected for export.</span></span> <span data-ttu-id="1ae70-138">Katrs segments radīs atsevišķu Customer Match auditoriju.</span><span class="sxs-lookup"><span data-stu-id="1ae70-138">Each segment will result in a separate Customer Match audience.</span></span> 

1. <span data-ttu-id="1ae70-139">Ievadiet savu **Microsoft Advertising klienta ID un konta ID**.</span><span class="sxs-lookup"><span data-stu-id="1ae70-139">Enter your **Microsoft Advertising Customer ID and Account ID**.</span></span> <span data-ttu-id="1ae70-140">Vietrāža URL parametros varat atrast klienta ID (`cid`) un konta ID (`aid`), kad esat pieteicies Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="1ae70-140">You can find the Customer ID (`cid`) and Account ID (`aid`) in the parameters of the URL when you're signed in Microsoft Advertising.</span></span>

1. <span data-ttu-id="1ae70-141">Sadaļas **Datu atbilstība** laukā **E-pasts** atlasiet lauku vienotajā klienta profilā ar klienta e-pasta adresi.</span><span class="sxs-lookup"><span data-stu-id="1ae70-141">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile with a customer's email address.</span></span> <span data-ttu-id="1ae70-142">Segmenti ir obligāti jāeksportē uz Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="1ae70-142">It's required to export segments to Microsoft Advertising.</span></span>

1. <span data-ttu-id="1ae70-143">Atlasiet vienumu **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="1ae70-143">Select **Save**.</span></span>

<span data-ttu-id="1ae70-144">Eksporta saglabāšana automātiski nepalaiž eksportu.</span><span class="sxs-lookup"><span data-stu-id="1ae70-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="1ae70-145">Eksports tiek palaists ar katru [plānoto atsvaidzināšanu](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="1ae70-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="1ae70-146">Varat arī [eksportēt datus pēc pieprasījuma](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="1ae70-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="1ae70-147">Datu konfidencialitāte un atbilstība</span><span class="sxs-lookup"><span data-stu-id="1ae70-147">Data privacy and compliance</span></span>

<span data-ttu-id="1ae70-148">Iespējojot Dynamics 365 Customer Insights datu pārnesi uz Microsoft Advertising, jūs ļaujat datus pārnest ārpus Dynamics 365 Customer Insights atbilstības robežām, ieskaitot potenciāli sensitīvus datus, tostarp, personas datus.</span><span class="sxs-lookup"><span data-stu-id="1ae70-148">When you enable Dynamics 365 Customer Insights to transmit data to Microsoft Advertising, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="1ae70-149">Microsoft šos datus pārvirzīs atbilstoši jūsu norādījumiem, taču jūs atbildat par to, ka Microsoft Advertising atbilst jebkādiem jūsu privātuma vai drošības nosacījumiem.</span><span class="sxs-lookup"><span data-stu-id="1ae70-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Microsoft Advertising meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="1ae70-150">Papildinformāciju skatiet rakstā [Microsoft Privātuma paziņojums](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="1ae70-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="1ae70-151">Lai pārtrauktu izmantot šo funkcionalitāti, jūsu Dynamics 365 Customer Insights administrators var noņemt šo eksportēšanas galamērķi jebkurā laikā.</span><span class="sxs-lookup"><span data-stu-id="1ae70-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to stop use of this functionality.</span></span>
