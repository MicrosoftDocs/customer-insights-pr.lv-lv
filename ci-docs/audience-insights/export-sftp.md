---
title: Customer Insights datu eksportēšana uz SFTP resursdatoriem
description: Uzziniet, kā konfigurēt savienojumu un eksportēt uz SFTP atrašanās vietu.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 96c6026aded315008439740646827ca910cead90
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760428"
---
# <a name="export-segment-lists-and-other-data-to-sftp-preview"></a><span data-ttu-id="cdec5-103">Eksportējiet segmentu sarakstus un citus datus uz SFTP (priekšskatījums)</span><span class="sxs-lookup"><span data-stu-id="cdec5-103">Export segment lists and other data to SFTP (preview)</span></span>

<span data-ttu-id="cdec5-104">Izmantojiet klientu datus trešo pušu lietojumprogrammās, eksportējot tos uz drošu failu pārsūtīšanas protokola (SFTP) atrašanās vietu.</span><span class="sxs-lookup"><span data-stu-id="cdec5-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol (SFTP) location.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="cdec5-105">Savienojuma priekšnosacījumi</span><span class="sxs-lookup"><span data-stu-id="cdec5-105">Prerequisites for connection</span></span>

- <span data-ttu-id="cdec5-106">SFTP resursdatora pieejamība un atbilstošie akreditācijas dati.</span><span class="sxs-lookup"><span data-stu-id="cdec5-106">Availability of an SFTP host and corresponding credentials.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="cdec5-107">Zināmie ierobežojumi</span><span class="sxs-lookup"><span data-stu-id="cdec5-107">Known limitations</span></span>

- <span data-ttu-id="cdec5-108">Eksportēšanas izpildlaiks ir atkarīgs no sistēmas veiktspējas.</span><span class="sxs-lookup"><span data-stu-id="cdec5-108">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="cdec5-109">Kā minimālu servera konfigurēšanu ieteicams izmantot divus procesora kodolus un 1 Gb atmiņu.</span><span class="sxs-lookup"><span data-stu-id="cdec5-109">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="cdec5-110">Līdz pat 100 miljoniem klientu profilu entītiju eksportēšana var aizņemt 90 minūtes, ja tiek izmantota ieteicama minimālā divu procesoru kodolu konfigurācija un 1 Gb atmiņa.</span><span class="sxs-lookup"><span data-stu-id="cdec5-110">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration of two CPU cores and 1 Gb of memory.</span></span> 

## <a name="set-up-connection-to-sftp"></a><span data-ttu-id="cdec5-111">Savienojuma ar SFTP iestatīšana</span><span class="sxs-lookup"><span data-stu-id="cdec5-111">Set up connection to SFTP</span></span>

1. <span data-ttu-id="cdec5-112">Dodieties uz **Administrators** > **Savienojumi**.</span><span class="sxs-lookup"><span data-stu-id="cdec5-112">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="cdec5-113">Atlasiet vienumu **Pievienot savienojumu** un atlasiet **SFTP**, lai konfigurētu savienojumu.</span><span class="sxs-lookup"><span data-stu-id="cdec5-113">Select **Add connection** and choose **SFTP** to configure the connection.</span></span>

1. <span data-ttu-id="cdec5-114">Laukā **Parādāmais nosaukums** piešķiriet savienojumam atpazīstamu nosaukumu.</span><span class="sxs-lookup"><span data-stu-id="cdec5-114">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="cdec5-115">Parādāmais nosaukums un nosaukuma veids raksturo šo savienojumu.</span><span class="sxs-lookup"><span data-stu-id="cdec5-115">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="cdec5-116">Ir ieteicams izvēlēties nosaukumu, kas paskaidro savienojuma nolūku.</span><span class="sxs-lookup"><span data-stu-id="cdec5-116">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="cdec5-117">Izvēlieties, kurš var izmantot šo savienojumu.</span><span class="sxs-lookup"><span data-stu-id="cdec5-117">Choose who can use this connection.</span></span> <span data-ttu-id="cdec5-118">Ja nesāksit nekādas darbības, noklusējums būs Administratori.</span><span class="sxs-lookup"><span data-stu-id="cdec5-118">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="cdec5-119">Papildinformāciju skatiet rakstā [Atļaut līdzstrādniekiem izmantot savienojumu eksportam](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="cdec5-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="cdec5-120">Norādiet **Lietotājvārdu**, **Paroli**, **Resursdatora nosaukumu** un **Eksporta mapi** savam SFTP kontam.</span><span class="sxs-lookup"><span data-stu-id="cdec5-120">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="cdec5-121">Atlasiet **Pārbaudīt**, lai testētu savienojumu.</span><span class="sxs-lookup"><span data-stu-id="cdec5-121">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="cdec5-122">Izvēlieties, vai vēlaties eksportēt datus kā **Gzipped** vai **Unzipped**, un eksportēto failu **lauku norobežotāju**.</span><span class="sxs-lookup"><span data-stu-id="cdec5-122">Choose if you want to export your data **Gzipped** or **Unzipped** and the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="cdec5-123">Atlasiet **Piekrītu**, lai apstiprinātu **Datu konfidencialitāti un atbilstību**.</span><span class="sxs-lookup"><span data-stu-id="cdec5-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="cdec5-124">Lai pabeigtu savienošanu, atlasiet **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="cdec5-124">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="cdec5-125">Eksporta konfigurēšana</span><span class="sxs-lookup"><span data-stu-id="cdec5-125">Configure an export</span></span>

<span data-ttu-id="cdec5-126">Šo eksportu varat konfigurēt, ja jums ir piekļuve šā veida pieslēgumam.</span><span class="sxs-lookup"><span data-stu-id="cdec5-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="cdec5-127">Papildinformāciju skatiet rakstā [Atļaujas, kas nepieciešamas eksporta konfigurēšanai](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="cdec5-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="cdec5-128">Pārejiet uz **Dati** > **Eksportēšana**.</span><span class="sxs-lookup"><span data-stu-id="cdec5-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="cdec5-129">Lai izveidotu jaunu eksportu, atlasiet **Pievienot galamērķi**.</span><span class="sxs-lookup"><span data-stu-id="cdec5-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="cdec5-130">Laukā **Savienošana eksportam** atlasiet savienojumu no sadaļas SFTP.</span><span class="sxs-lookup"><span data-stu-id="cdec5-130">In the **Connection for export** field, choose a connection from the SFTP section.</span></span> <span data-ttu-id="cdec5-131">Ja šis sadaļas nosaukums nav redzams, šāda veida savienojumi jums nav pieejami.</span><span class="sxs-lookup"><span data-stu-id="cdec5-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="cdec5-132">Atlasiet entītijas, piemēram, segmentus, kurus vēlaties eksportēt.</span><span class="sxs-lookup"><span data-stu-id="cdec5-132">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="cdec5-133">Eksportēšanas laikā katra atlasītā entitīja tiks iedalīta maksimums piecos izvades failos.</span><span class="sxs-lookup"><span data-stu-id="cdec5-133">Each selected entity will be split up into up to five output files when exported.</span></span> 

1. <span data-ttu-id="cdec5-134">Atlasiet vienumu **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="cdec5-134">Select **Save**.</span></span>

<span data-ttu-id="cdec5-135">Eksporta saglabāšana automātiski nepalaiž eksportu.</span><span class="sxs-lookup"><span data-stu-id="cdec5-135">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="cdec5-136">Eksports tiek palaists ar katru [plānoto atsvaidzināšanu](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="cdec5-136">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="cdec5-137">Varat arī [eksportēt datus pēc pieprasījuma](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="cdec5-137">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="cdec5-138">Datu konfidencialitāte un atbilstība</span><span class="sxs-lookup"><span data-stu-id="cdec5-138">Data privacy and compliance</span></span>

<span data-ttu-id="cdec5-139">Ja iespējojat Dynamics 365 Customer Insights datu pārsūtīšanu caur SFTP, jūs atļaujat datu pārsūtīšanu ārpus atbilstības robežām Dynamics 365 Customer Insights, ieskaitot iespējami sensitīvus datus, piemēram, personas datus.</span><span class="sxs-lookup"><span data-stu-id="cdec5-139">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="cdec5-140">Microsoft šos datus pārsūtīs pēc jūsu norādēm, bet jūs esat atbildīgs par to, lai nodrošinātu eksporta galamērķa atbilstību konfidencialitātes vai drošības saistībām, kas jums varētu rasties.</span><span class="sxs-lookup"><span data-stu-id="cdec5-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="cdec5-141">Papildinformāciju skatiet rakstā [Microsoft Privātuma paziņojums](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="cdec5-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="cdec5-142">Jūsu Dynamics 365 Customer Insights administrators var noņemt šo eksportēšanas galamērķi jebkurā laikā, lai pārtrauktu izmantot šo funkcionalitāti.</span><span class="sxs-lookup"><span data-stu-id="cdec5-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
