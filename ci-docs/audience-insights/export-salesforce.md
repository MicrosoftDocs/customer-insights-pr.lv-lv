---
title: Customer Insights datu eksportēšana uz Salesforce Marketing Cloud
description: Uzziniet, kā konfigurēt savienojumu un eksportēt uz Salesforce Marketing Cloud.
ms.date: 06/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 123f8b2dbb6140785dec6c1b4164d2f513f66a53
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314642"
---
# <a name="export-segments-and-other-data-to-salesforce-marketing-cloud-preview"></a><span data-ttu-id="ac39a-103">Segmentu un citu datu eksportēšana uz Salesforce Marketing Cloud (priekšskatījums)</span><span class="sxs-lookup"><span data-stu-id="ac39a-103">Export segments and other data to Salesforce Marketing Cloud (preview)</span></span>

<span data-ttu-id="ac39a-104">Izmantojiet klientu datus programmā Salesforce Marketing Cloud, eksportējot tos, izmantojot drošu failu pārsūtīšanas protokola (SFTP) atrašanās vietu.</span><span class="sxs-lookup"><span data-stu-id="ac39a-104">Use your customer data in Salesforce Marketing Cloud by exporting them through a Secure File Transfer Protocol (SFTP) location.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="ac39a-105">Savienojuma priekšnosacījumi</span><span class="sxs-lookup"><span data-stu-id="ac39a-105">Prerequisites for connection</span></span>

- <span data-ttu-id="ac39a-106">SFTP viesošanas pakalpojuma pieejamība un attiecīgie administratora akreditācijas dati.</span><span class="sxs-lookup"><span data-stu-id="ac39a-106">Availability of an SFTP host and corresponding admin credentials.</span></span> [<span data-ttu-id="ac39a-107">Kā iestatīt SFTP atrašanās vietas programmai Salesforce Marketing Cloud</span><span class="sxs-lookup"><span data-stu-id="ac39a-107">How to setup SFTP locations for Salesforce Marketing Cloud</span></span>](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) 

## <a name="known-limitations"></a><span data-ttu-id="ac39a-108">Zināmie ierobežojumi</span><span class="sxs-lookup"><span data-stu-id="ac39a-108">Known limitations</span></span>

- <span data-ttu-id="ac39a-109">Eksportēšanas izpildlaiks ir atkarīgs no sistēmas veiktspējas.</span><span class="sxs-lookup"><span data-stu-id="ac39a-109">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="ac39a-110">Kā minimālu servera konfigurēšanu ieteicams izmantot divus procesora kodolus un 1 Gb atmiņu.</span><span class="sxs-lookup"><span data-stu-id="ac39a-110">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="ac39a-111">Eksportējot entītijas ar līdz pat 100 miljoniem klientu profilu, var paiet 90 minūtes, izmantojot ieteicamo minimālo konfigurāciju.</span><span class="sxs-lookup"><span data-stu-id="ac39a-111">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration.</span></span> 

## <a name="set-up-the-connection-to-salesforce-marketing-cloud"></a><span data-ttu-id="ac39a-112">Savienojuma iestatīšana ar Salesforce Marketing Cloud</span><span class="sxs-lookup"><span data-stu-id="ac39a-112">Set up the connection to Salesforce Marketing Cloud</span></span>

1. <span data-ttu-id="ac39a-113">Dodieties uz **Administrators** > **Savienojumi**.</span><span class="sxs-lookup"><span data-stu-id="ac39a-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="ac39a-114">Atlasiet vienumu **Pievienot savienojumu** un izvēlieties **Salesforce Marketing Cloud**, lai konfigurētu savienojumu.</span><span class="sxs-lookup"><span data-stu-id="ac39a-114">Select **Add connection** and choose **Salesforce Marketing Cloud** to configure the connection.</span></span>

1. <span data-ttu-id="ac39a-115">Laukā **Parādāmais nosaukums** piešķiriet savienojumam atpazīstamu nosaukumu.</span><span class="sxs-lookup"><span data-stu-id="ac39a-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="ac39a-116">Parādāmais nosaukums un nosaukuma veids raksturo šo savienojumu.</span><span class="sxs-lookup"><span data-stu-id="ac39a-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="ac39a-117">Ir ieteicams izvēlēties nosaukumu, kas paskaidro savienojuma nolūku.</span><span class="sxs-lookup"><span data-stu-id="ac39a-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="ac39a-118">Izvēlieties, kurš var izmantot šo savienojumu.</span><span class="sxs-lookup"><span data-stu-id="ac39a-118">Choose who can use this connection.</span></span> <span data-ttu-id="ac39a-119">Ja nesāksit nekādas darbības, noklusējums būs Administratori.</span><span class="sxs-lookup"><span data-stu-id="ac39a-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="ac39a-120">Papildinformāciju skatiet rakstā [Atļaut līdzstrādniekiem izmantot savienojumu eksportam](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="ac39a-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="ac39a-121">Norādiet **Lietotājvārdu**, **Paroli**, **Resursdatora nosaukumu** un **Eksporta mapi** savam SFTP kontam.</span><span class="sxs-lookup"><span data-stu-id="ac39a-121">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="ac39a-122">Atlasiet **Pārbaudīt**, lai testētu savienojumu.</span><span class="sxs-lookup"><span data-stu-id="ac39a-122">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="ac39a-123">Atlasiet **Piekrītu**, lai apstiprinātu **Datu konfidencialitāti un atbilstību**.</span><span class="sxs-lookup"><span data-stu-id="ac39a-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="ac39a-124">Lai pabeigtu savienošanu, atlasiet **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="ac39a-124">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="ac39a-125">Eksporta konfigurēšana</span><span class="sxs-lookup"><span data-stu-id="ac39a-125">Configure an export</span></span>

<span data-ttu-id="ac39a-126">Šo eksportu varat konfigurēt, ja jums ir piekļuve šā veida pieslēgumam.</span><span class="sxs-lookup"><span data-stu-id="ac39a-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="ac39a-127">Papildinformāciju skatiet rakstā [Atļaujas, kas nepieciešamas eksporta konfigurēšanai](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="ac39a-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="ac39a-128">Pārejiet uz **Dati** > **Eksportēšana**.</span><span class="sxs-lookup"><span data-stu-id="ac39a-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="ac39a-129">Lai izveidotu jaunu eksportu, atlasiet **Pievienot galamērķi**.</span><span class="sxs-lookup"><span data-stu-id="ac39a-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="ac39a-130">Laukā **Savienošana eksportam** atlasiet savienojumu no sadaļas SFTP.</span><span class="sxs-lookup"><span data-stu-id="ac39a-130">In the **Connection for export** field, choose a connection from the SFTP section.</span></span> <span data-ttu-id="ac39a-131">Ja šis sadaļas nosaukums nav redzams, šāda veida savienojumi jums nav pieejami.</span><span class="sxs-lookup"><span data-stu-id="ac39a-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="ac39a-132">Izvēlieties, vai vēlaties eksportēt datus kā **Gzipped** vai **Unzipped**, un eksportēto failu **lauku norobežotāju**.</span><span class="sxs-lookup"><span data-stu-id="ac39a-132">Choose if you want to export your data **Gzipped** or **Unzipped** and the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="ac39a-133">Atlasiet entītijas, piemēram, segmentus, kurus vēlaties eksportēt.</span><span class="sxs-lookup"><span data-stu-id="ac39a-133">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="ac39a-134">Eksportēšanas laikā katra atlasītā entitīja tiks iedalīta maksimums piecos izvades failos.</span><span class="sxs-lookup"><span data-stu-id="ac39a-134">Each selected entity will be split up into up to five output files when exported.</span></span> 

1. <span data-ttu-id="ac39a-135">Atlasiet vienumu **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="ac39a-135">Select **Save**.</span></span>

<span data-ttu-id="ac39a-136">Eksporta saglabāšana automātiski nepalaiž eksportu.</span><span class="sxs-lookup"><span data-stu-id="ac39a-136">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="ac39a-137">Eksports tiek palaists ar katru [plānoto atsvaidzināšanu](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="ac39a-137">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="ac39a-138">Varat arī [eksportēt datus pēc pieprasījuma](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="ac39a-138">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a><span data-ttu-id="ac39a-139">Customer Insights datu importēšana no SFTP atrašanās vietas uz Salesforce Marketing Cloud</span><span class="sxs-lookup"><span data-stu-id="ac39a-139">Import Customer Insights data from SFTP location to Salesforce Marketing Cloud</span></span>

1. <span data-ttu-id="ac39a-140">Izveidojiet [datu paplašinājumus programmai Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5), lai importētu Customer Insights datu failu no SFTP atrašanās vietas.</span><span class="sxs-lookup"><span data-stu-id="ac39a-140">Create [data extensions in Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) to import the Customer Insights data file from the SFTP location.</span></span>

2. <span data-ttu-id="ac39a-141">[Importējiet datus no SFTP atrašanās vietas](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) uz Salesforce Marketing Cloud datu paplašinājumu.</span><span class="sxs-lookup"><span data-stu-id="ac39a-141">[Import the data from the SFTP location](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) into the Salesforce Marketing Cloud data extension.</span></span> 

3. <span data-ttu-id="ac39a-142">Iestatiet automatizāciju, lai datus importētu datu paplašinājumos.</span><span class="sxs-lookup"><span data-stu-id="ac39a-142">Set up the automation to import the data into the data extensions.</span></span> <span data-ttu-id="ac39a-143">Papildinformācija par [failu nomešanas automatizāciju un ieplānotajām automatizācijujām](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).</span><span class="sxs-lookup"><span data-stu-id="ac39a-143">Learn more about [file drop automations and scheduled automations](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).</span></span>

   <span data-ttu-id="ac39a-144">Definējiet [failu nomešanas automatizāciju](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) vai [ieplānotas automatizācijas](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5)</span><span class="sxs-lookup"><span data-stu-id="ac39a-144">Define a [file drop automation](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) or a  [scheduled automation](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5).</span></span> 

<span data-ttu-id="ac39a-145">Tālāk parādīts piemērs [automatizācijai ar SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).</span><span class="sxs-lookup"><span data-stu-id="ac39a-145">Here's an example of [an automation with SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="ac39a-146">Datu konfidencialitāte un atbilstība</span><span class="sxs-lookup"><span data-stu-id="ac39a-146">Data privacy and compliance</span></span>

<span data-ttu-id="ac39a-147">Ja iespējojat Dynamics 365 Customer Insights datu pārsūtīšanu caur SFTP, jūs atļaujat datu pārsūtīšanu ārpus atbilstības robežām Dynamics 365 Customer Insights, ieskaitot iespējami sensitīvus datus, piemēram, personas datus.</span><span class="sxs-lookup"><span data-stu-id="ac39a-147">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="ac39a-148">Microsoft šos datus pārsūtīs pēc jūsu norādēm, bet jūs esat atbildīgs par to, lai nodrošinātu eksporta galamērķa atbilstību konfidencialitātes vai drošības saistībām, kas jums varētu rasties.</span><span class="sxs-lookup"><span data-stu-id="ac39a-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="ac39a-149">Papildinformāciju skatiet rakstā [Microsoft Privātuma paziņojums](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="ac39a-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="ac39a-150">Jūsu Dynamics 365 Customer Insights administrators var noņemt šo eksportēšanas galamērķi jebkurā laikā, lai pārtrauktu izmantot šo funkcionalitāti.</span><span class="sxs-lookup"><span data-stu-id="ac39a-150">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
