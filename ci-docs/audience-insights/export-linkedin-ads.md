---
title: Customer Insights datu eksportēšana uz LinkedIn Ads
description: Uzziniet, kā konfigurēt savienojumu un eksportēt uz LinkedIn Ads.
ms.date: 05/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 1c7b0c728bc4d4cf6b5aea79396cf0779fbf298d
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124521"
---
# <a name="export-segments-to-linkedin-ads-preview"></a><span data-ttu-id="35e8c-103">Segmentu eksportēšana uz LinkedIn Ads (priekšskatījums)</span><span class="sxs-lookup"><span data-stu-id="35e8c-103">Export segments to LinkedIn Ads (preview)</span></span>

<span data-ttu-id="35e8c-104">Eksportēt vienoto klientu profilu segmentus uz LinkedIn Ads, lai izveidotu Matched Audiences.</span><span class="sxs-lookup"><span data-stu-id="35e8c-104">Export segments of unified customer profiles to LinkedIn Ads to create matched audiences.</span></span> <span data-ttu-id="35e8c-105">Izmantojiet Matched Audiences, lai mērķētu uz uzņēmumu un sazinātos ar mērķauditorijas atlasi.</span><span class="sxs-lookup"><span data-stu-id="35e8c-105">Use the matched audiences for company targeting and contact targeting.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="35e8c-106">Priekšnosacījumi</span><span class="sxs-lookup"><span data-stu-id="35e8c-106">Prerequisites</span></span>

-   <span data-ttu-id="35e8c-107">Jums ir [LinkedIn Campaign Manager konts](https://business.linkedin.com/marketing-solutions/ads) un atbilstošie administratora akreditācijas dati.</span><span class="sxs-lookup"><span data-stu-id="35e8c-107">You have an [LinkedIn Campaign Manager account](https://business.linkedin.com/marketing-solutions/ads) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="35e8c-108">Jums ir [konfigurēti segmenti](segments.md) auditorijas ieskatos.</span><span class="sxs-lookup"><span data-stu-id="35e8c-108">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="35e8c-109">Eksportēto segmentu klientu profilos ir lauks ar e-pasta adresi.</span><span class="sxs-lookup"><span data-stu-id="35e8c-109">Customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="35e8c-110">Zināmie ierobežojumi</span><span class="sxs-lookup"><span data-stu-id="35e8c-110">Known limitations</span></span>

- <span data-ttu-id="35e8c-111">Jūs varat eksportēt līdz 100 000 profilu uz katru eksportu uz LinkedIn Ads.</span><span class="sxs-lookup"><span data-stu-id="35e8c-111">You can export up to 100K profiles per export to LinkedIn Ads.</span></span>
- <span data-ttu-id="35e8c-112">Eksportēšana uz LinkedIn Ads attiecas tikai uz segmentiem.</span><span class="sxs-lookup"><span data-stu-id="35e8c-112">Exporting to LinkedIn Ads is limited to segments.</span></span>
- <span data-ttu-id="35e8c-113">Līdz 100 000 profilu eksportēšana uz LinkedIn Ads var aizņemt līdz 10 minūtēm.</span><span class="sxs-lookup"><span data-stu-id="35e8c-113">Exporting up to 100K profiles to LinkedIn Ads can take up to 10 minutes to complete.</span></span> 

## <a name="set-up-the-connection-to-linkedin-ads"></a><span data-ttu-id="35e8c-114">Savienojuma ar LinkedIn Ads krātuvi iestatīšana</span><span class="sxs-lookup"><span data-stu-id="35e8c-114">Set up the connection to LinkedIn Ads</span></span>

1. <span data-ttu-id="35e8c-115">Auditorijas ieskatos dodieties uz **Administrators** > **Savienojumi**.</span><span class="sxs-lookup"><span data-stu-id="35e8c-115">In audience insights, go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="35e8c-116">Atlasiet vienumu **Pievienot savienojumu** un atlasiet **LinkedIn Ads**, lai konfigurētu savienojumu.</span><span class="sxs-lookup"><span data-stu-id="35e8c-116">Select **Add connection** and choose **LinkedIn Ads** to configure the connection.</span></span>

1. <span data-ttu-id="35e8c-117">Laukā **Parādāmais nosaukums** piešķiriet savienojumam atpazīstamu nosaukumu.</span><span class="sxs-lookup"><span data-stu-id="35e8c-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="35e8c-118">Parādāmais nosaukums un nosaukuma veids raksturo šo savienojumu.</span><span class="sxs-lookup"><span data-stu-id="35e8c-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="35e8c-119">Ir ieteicams izvēlēties nosaukumu, kas paskaidro savienojuma nolūku.</span><span class="sxs-lookup"><span data-stu-id="35e8c-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="35e8c-120">Izvēlieties, kurš var izmantot šo savienojumu.</span><span class="sxs-lookup"><span data-stu-id="35e8c-120">Choose who can use this connection.</span></span> <span data-ttu-id="35e8c-121">Ja nesāksit nekādas darbības, noklusējums būs administratori.</span><span class="sxs-lookup"><span data-stu-id="35e8c-121">If you take no action, the default is administrators.</span></span> <span data-ttu-id="35e8c-122">Papildinformāciju skatiet rakstā [Atļaut līdzstrādniekiem izmantot savienojumu eksportam](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="35e8c-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="35e8c-123">Norādiet sava [LinkedIn Campaign Manager konta ID](https://www.linkedin.com/help/lms/answer/a424270).</span><span class="sxs-lookup"><span data-stu-id="35e8c-123">Provide your [LinkedIn Campaign Manager Account ID](https://www.linkedin.com/help/lms/answer/a424270).</span></span>

1. <span data-ttu-id="35e8c-124">Atlasiet **Piekrītu**, lai apstiprinātu **Datu konfidencialitāti un atbilstību**.</span><span class="sxs-lookup"><span data-stu-id="35e8c-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="35e8c-125">Lai uzsāktu savienojumu ar Campaign Monitor, atlasiet **Savienot**.</span><span class="sxs-lookup"><span data-stu-id="35e8c-125">Select **Connect** to initialize the connection to Campaign Monitor.</span></span>

1. <span data-ttu-id="35e8c-126">Atlasiet **Autentificēties ar LinkedIn** un norādiet savus LinkedIn Campaign Manager administratora akreditācijas datus.</span><span class="sxs-lookup"><span data-stu-id="35e8c-126">Select **Authenticate with LinkedIn** and provide your admin credentials for LinkedIn Campaign Manager.</span></span>

1. <span data-ttu-id="35e8c-127">Atlasiet opciju **Pievienot sevi kā eksporta lietotāju** un sniedziet savus Customer Insights akreditācijas datus.</span><span class="sxs-lookup"><span data-stu-id="35e8c-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="35e8c-128">Lai pabeigtu savienošanu, atlasiet **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="35e8c-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="35e8c-129">Eksporta konfigurēšana</span><span class="sxs-lookup"><span data-stu-id="35e8c-129">Configure an export</span></span>

<span data-ttu-id="35e8c-130">Šo eksportu varat konfigurēt, ja jums ir piekļuve šā veida pieslēgumam.</span><span class="sxs-lookup"><span data-stu-id="35e8c-130">You can configure an export if you have access to a connection of this type.</span></span> <span data-ttu-id="35e8c-131">Papildinformāciju skatiet rakstā [Atļaujas, kas nepieciešamas eksporta konfigurēšanai](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="35e8c-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="35e8c-132">Pārejiet uz **Dati** > **Eksportēšana**.</span><span class="sxs-lookup"><span data-stu-id="35e8c-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="35e8c-133">Lai izveidotu jaunu eksportu, atlasiet **Pievienot galamērķi**.</span><span class="sxs-lookup"><span data-stu-id="35e8c-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="35e8c-134">Laukā **Savienošana eksportam** atlasiet savienojumu no sadaļas LinkedIn Ads.</span><span class="sxs-lookup"><span data-stu-id="35e8c-134">In the **Connection for export** field, choose a connection from the LinkedIn Ads section.</span></span> <span data-ttu-id="35e8c-135">Ja šis sadaļas nosaukums nav redzams, šāda veida savienojumi jums nav pieejami.</span><span class="sxs-lookup"><span data-stu-id="35e8c-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="35e8c-136">Izvēlieties, vai vēlaties eksportēt datus, lai sazinātos [ar mērķauditorijas atlasi](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting), [vai uzņēmuma mērķauditorijas atlasi](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) LinkedIn.</span><span class="sxs-lookup"><span data-stu-id="35e8c-136">Choose whether you want to export data to do [contact targeting](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) or [company targeting](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) on LinkedIn.</span></span> 

1. <span data-ttu-id="35e8c-137">Sadaļā **Datu salīdzināšana** atlasiet lauku vienotajā klienta profilā, kas norāda klienta e-pasta adresi.</span><span class="sxs-lookup"><span data-stu-id="35e8c-137">In the **Data matching** section, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="35e8c-138">Segmenti ir obligāti jāeksportē uz LinkedIn Ads.</span><span class="sxs-lookup"><span data-stu-id="35e8c-138">It's required to export segments to LinkedIn Ads.</span></span>

1. <span data-ttu-id="35e8c-139">Atlasiet segmentus, kurus vēlaties eksportēt.</span><span class="sxs-lookup"><span data-stu-id="35e8c-139">Select the segments you want to export.</span></span> <span data-ttu-id="35e8c-140">Matched Audiences programmā LinkedIn Campaign Manager tiks automātiski izveidotas ar eksportējamo segmentu nosaukumu.</span><span class="sxs-lookup"><span data-stu-id="35e8c-140">The matched audiences in LinkedIn Campaign Manager will automatically be created with the name of the segments that you selected to export.</span></span> <span data-ttu-id="35e8c-141">Katrs segments radīs atsevišķu Matched Audience.</span><span class="sxs-lookup"><span data-stu-id="35e8c-141">Each segment will result in a separate matched audience.</span></span> 

1. <span data-ttu-id="35e8c-142">Atlasiet vienumu **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="35e8c-142">Select **Save**.</span></span>

<span data-ttu-id="35e8c-143">Eksporta saglabāšana automātiski nepalaiž eksportu.</span><span class="sxs-lookup"><span data-stu-id="35e8c-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="35e8c-144">Eksports tiek palaists ar katru [plānoto atsvaidzināšanu](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="35e8c-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="35e8c-145">Varat arī [eksportēt datus pēc pieprasījuma](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="35e8c-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="35e8c-146">Datu konfidencialitāte un atbilstība</span><span class="sxs-lookup"><span data-stu-id="35e8c-146">Data privacy and compliance</span></span>

<span data-ttu-id="35e8c-147">Iespējojot Dynamics 365 Customer Insights datu pārnesi uz LinkedIn Ads, jūs ļaujat datus pārnest ārpus Dynamics 365 Customer Insights atbilstības robežām, ieskaitot potenciāli sensitīvus datus, tostarp, personas datus.</span><span class="sxs-lookup"><span data-stu-id="35e8c-147">When you enable Dynamics 365 Customer Insights to transmit data to LinkedIn Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="35e8c-148">Microsoft šos datus pārvirzīs atbilstoši jūsu norādījumiem, taču jūs atbildat par to, ka LinkedIn Ads atbilst jebkādiem jūsu privātuma vai drošības nosacījumiem.</span><span class="sxs-lookup"><span data-stu-id="35e8c-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that LinkedIn Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="35e8c-149">Papildinformāciju skatiet rakstā [Microsoft Privātuma paziņojums](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="35e8c-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="35e8c-150">Lai pārtrauktu izmantot šo funkcionalitāti, jūsu Dynamics 365 Customer Insights administrators var noņemt šo eksportēšanas galamērķi jebkurā laikā.</span><span class="sxs-lookup"><span data-stu-id="35e8c-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to stop the use of this functionality.</span></span>
