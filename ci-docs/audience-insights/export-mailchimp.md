---
title: Customer Insights datu eksportēšana uz Mailchimp
description: Uzziniet, kā konfigurēt savienojumu ar Mailchimp.
ms.date: 10/26/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: edff494f6edf26a8b641cb1d788a715389ddb346
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406326"
---
# <a name="connector-for-mailchimp-preview"></a><span data-ttu-id="38b68-103">Savienotājs ar Mailchimp (priekšskatījums)</span><span class="sxs-lookup"><span data-stu-id="38b68-103">Connector for Mailchimp (preview)</span></span>

<span data-ttu-id="38b68-104">Eksportējiet vienotu klientu profilu segmentus uz Mailchimp, lai izveidotu informatīvas vēstules un e-pasta kampaņas.</span><span class="sxs-lookup"><span data-stu-id="38b68-104">Export segments of unified customer profiles to Mailchimp to create newsletters and email campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="38b68-105">Priekšnosacījumi</span><span class="sxs-lookup"><span data-stu-id="38b68-105">Prerequisites</span></span>

-   <span data-ttu-id="38b68-106">Jums ir [Mailchimp konts](https://mailchimp.com/) un atbilstošie administratora akreditācijas dati.</span><span class="sxs-lookup"><span data-stu-id="38b68-106">You have a [Mailchimp account](https://mailchimp.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="38b68-107">Mailchimp ir esošas auditorijas un attiecīgie ID.</span><span class="sxs-lookup"><span data-stu-id="38b68-107">There are existing audiences in Mailchimp and the corresponding IDs.</span></span> <span data-ttu-id="38b68-108">Papildinformāciju skatiet rakstā [Mailchimp auditorijas](https://mailchimp.com/help/create-audience/).</span><span class="sxs-lookup"><span data-stu-id="38b68-108">For more information, see [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>
-   <span data-ttu-id="38b68-109">Jums ir [konfigurēti segmenti](segments.md)</span><span class="sxs-lookup"><span data-stu-id="38b68-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="38b68-110">Eksportētajos segmentos vienotajiem klientu profiliem ir lauks, kas norāda e-pasta adresi.</span><span class="sxs-lookup"><span data-stu-id="38b68-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-mailchimp"></a><span data-ttu-id="38b68-111">Izveidot savienojumu ar Mailchimp</span><span class="sxs-lookup"><span data-stu-id="38b68-111">Connect to Mailchimp</span></span>

1. <span data-ttu-id="38b68-112">Dodieties uz sadaļu **Administrators** > **Eksportēšanas galamērķi**.</span><span class="sxs-lookup"><span data-stu-id="38b68-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="38b68-113">Sadaļā **Mailchimp** atlasiet vienumu **Iestatīt**.</span><span class="sxs-lookup"><span data-stu-id="38b68-113">Under **Mailchimp**, select **Set up**.</span></span>

1. <span data-ttu-id="38b68-114">Piešķiriet eksportēšanas galamērķim atpazīstamu nosaukumu laukā **Parādāmais nosaukums**.</span><span class="sxs-lookup"><span data-stu-id="38b68-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="38b68-115">Atlasiet **Piekrītu**, lai apstiprinātu **Datu privātumu un atbilstību**.</span><span class="sxs-lookup"><span data-stu-id="38b68-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="38b68-116">Ievadiet savas **[Mailchimp auditorijas ID](https://mailchimp.com/help/find-audience-id/)** un atlasiet opciju **Izveidot savienojumu**, lai inicializētu savienojumu ar Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="38b68-116">Enter your **[Mailchimp audience ID](https://mailchimp.com/help/find-audience-id/)** and select **Connect** to initialize the connection to Mailchimp.</span></span>

1. <span data-ttu-id="38b68-117">Atlasiet **Autentificēties ar Mailchimp** un sniedziet savus Mailchimp akreditācijas datus.</span><span class="sxs-lookup"><span data-stu-id="38b68-117">Select **Authenticate with Mailchimp** and provide your Mailchimp credentials.</span></span>

1. <span data-ttu-id="38b68-118">Atlasiet opciju **Pievienot sevi kā eksporta lietotāju** un sniedziet savus Customer Insights akreditācijas datus.</span><span class="sxs-lookup"><span data-stu-id="38b68-118">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-connect-mailchimp.png" alt-text="Eksportēt ekrānuzņēmumu Mailchimp savienojumā":::

1. <span data-ttu-id="38b68-120">Lai konfigurētu eksportēšanu, atlasiet **Tālāk**.</span><span class="sxs-lookup"><span data-stu-id="38b68-120">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="38b68-121">Savienotāja konfigurēšana</span><span class="sxs-lookup"><span data-stu-id="38b68-121">Configure the connector</span></span>

1. <span data-ttu-id="38b68-122">Sadaļas **Datu atbilstības** laukā **E-pasts** atlasiet lauku, kas iekļauts vienotajā klientu profilā, kas pārstāv klienta e-pasta adresi.</span><span class="sxs-lookup"><span data-stu-id="38b68-122">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="38b68-123">Ja vēlaties, varat eksportēt **Vārds** un **Uzvārds** kā papildu laukus, lai izveidotu vairāk personalizētu e-pasta ziņojumu.</span><span class="sxs-lookup"><span data-stu-id="38b68-123">Optionally, you can export **First name** and **Last name** as additional fields to create more personalized emails.</span></span> <span data-ttu-id="38b68-124">Atlasiet **Pievienot atribūtu**, lai kartētu šos laukus.</span><span class="sxs-lookup"><span data-stu-id="38b68-124">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="38b68-125">Atlasiet segmentus, kurus vēlaties eksportēt.</span><span class="sxs-lookup"><span data-stu-id="38b68-125">Select the segments you want to export.</span></span> <span data-ttu-id="38b68-126">Kopsummā var eksportēt līdz 1 000 000 klientu profilu uz Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="38b68-126">You can export up to 1 million customer profiles in total to Mailchimp.</span></span>

   :::image type="content" source="media/export-segments-mailchimp.png" alt-text="Atlasīt laukus un segmentus eksportēšanai uz Mailchimp":::

1. <span data-ttu-id="38b68-128">Atlasiet vienumu **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="38b68-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="38b68-129">Datu eksportēšana</span><span class="sxs-lookup"><span data-stu-id="38b68-129">Export the data</span></span>

<span data-ttu-id="38b68-130">Datus var [eksportēt pēc pieprasījuma](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="38b68-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="38b68-131">Eksportēšana arī tiks palaista ar katru [plānoto atsvaidzināšanu](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="38b68-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="38b68-132">Mailchimp tagad varat atrast jūsu segmentus sadaļā [Mailchimp auditorija](https://mailchimp.com/help/create-audience/).</span><span class="sxs-lookup"><span data-stu-id="38b68-132">In Mailchimp, you can now find your segments under [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="38b68-133">Zināmie ierobežojumi</span><span class="sxs-lookup"><span data-stu-id="38b68-133">Known limitations</span></span>

- <span data-ttu-id="38b68-134">Līdz 1 000 000 profilu, eksportējot uz Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="38b68-134">Up to 1 million profiles per export to Mailchimp.</span></span>
- <span data-ttu-id="38b68-135">Eksportēšana uz Mailchimp ir ierobežota līdz segmentiem.</span><span class="sxs-lookup"><span data-stu-id="38b68-135">Exporting to Mailchimp is limited to segments.</span></span>
- <span data-ttu-id="38b68-136">Segmentu eksportēšanai kopā ar 1 000 000 profilu var būt nepieciešamas 3 stundas, jo pastāv ierobežojumi no pakalpojuma sniedzēja puses.</span><span class="sxs-lookup"><span data-stu-id="38b68-136">Exporting segments with a total of 1 million profiles can take up to three hours due to limitations on the provider side.</span></span> 
- <span data-ttu-id="38b68-137">To profilu skaits, ko var eksportēt uz Mailchimp, ir atkarīgs, un tas ir ierobežots jūsu līgumā ar Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="38b68-137">The number of profiles that you can export to Mailchimp is dependent and limited on your contract with Mailchimp.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="38b68-138">Datu konfidencialitāte un atbilstība</span><span class="sxs-lookup"><span data-stu-id="38b68-138">Data privacy and compliance</span></span>

<span data-ttu-id="38b68-139">Ja iespējojat Dynamics 365 Customer Insights datu pārsūtīšanu uz Mailchimp, jūs atļaujat datu pārsūtīšanu ārpus atbilstības robežām Dynamics 365 Customer Insights, ieskaitot iespējami sensitīvus datus, piemēram, personas datus.</span><span class="sxs-lookup"><span data-stu-id="38b68-139">When you enable Dynamics 365 Customer Insights to transmit data to Mailchimp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="38b68-140">Microsoft šos datus pārsūtīs pēc jūsu norādēm, bet jūs esat atbildīgs par to, lai nodrošinātu Mailchimp atbilstību konfidencialitātes vai drošības saistībām, kas jums varētu rasties.</span><span class="sxs-lookup"><span data-stu-id="38b68-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Mailchimp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="38b68-141">Papildinformāciju skatiet rakstā [Microsoft Privātuma paziņojums](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="38b68-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="38b68-142">Jūsu Dynamics 365 Customer Insights administrators var noņemt šo eksportēšanas galamērķi jebkurā laikā, lai pārtrauktu izmantot šo funkcionalitāti.</span><span class="sxs-lookup"><span data-stu-id="38b68-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
