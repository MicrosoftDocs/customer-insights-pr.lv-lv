---
title: Customer Insights datu eksportēšana uz Marketo
description: Uzziniet, kā konfigurēt savienojumu ar Marketo.
ms.date: 11/12/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: e0245f2d01aabc86f43532822c056965ff7ae67a
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267090"
---
# <a name="connector-for-marketo-preview"></a><span data-ttu-id="ae0f0-103">Savienotājs ar Marketo (priekšskatījums)</span><span class="sxs-lookup"><span data-stu-id="ae0f0-103">Connector for Marketo (preview)</span></span>

<span data-ttu-id="ae0f0-104">Izmantojiet pakalpojumā Customer Insights izveidotos segmentus kampaņu veidošanai, e-pasta mārketinga sniegšanai un specifisku klientu grupu atlases iespējas pakalpojumā Marketo.</span><span class="sxs-lookup"><span data-stu-id="ae0f0-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Marketo.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ae0f0-105">Priekšnosacījumi</span><span class="sxs-lookup"><span data-stu-id="ae0f0-105">Prerequisites</span></span>

-   <span data-ttu-id="ae0f0-106">Jums ir [Marketo konts](https://login.marketo.com/) un atbilstošie administratora akreditācijas dati.</span><span class="sxs-lookup"><span data-stu-id="ae0f0-106">You have a [Marketo account](https://login.marketo.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="ae0f0-107">Marketo ir esošas auditorijas un attiecīgie ID.</span><span class="sxs-lookup"><span data-stu-id="ae0f0-107">There are existing lists in Marketo and the corresponding IDs.</span></span> <span data-ttu-id="ae0f0-108">Lai iegūtu papildinformāciju, skatiet [Marketo sarakstus](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="ae0f0-108">For more information, see [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>
-   <span data-ttu-id="ae0f0-109">Jums ir [konfigurēti segmenti](segments.md).</span><span class="sxs-lookup"><span data-stu-id="ae0f0-109">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="ae0f0-110">Eksportētajos segmentos vienotajiem klientu profiliem ir lauks, kas norāda e-pasta adresi.</span><span class="sxs-lookup"><span data-stu-id="ae0f0-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-marketo"></a><span data-ttu-id="ae0f0-111">Izveidot savienojumu ar Marketo</span><span class="sxs-lookup"><span data-stu-id="ae0f0-111">Connect to Marketo</span></span>

1. <span data-ttu-id="ae0f0-112">Dodieties uz sadaļu **Administrators** > **Eksportēšanas galamērķi**.</span><span class="sxs-lookup"><span data-stu-id="ae0f0-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="ae0f0-113">Sadaļā **Marketo** atlasiet vienumu **Iestatīt**.</span><span class="sxs-lookup"><span data-stu-id="ae0f0-113">Under **Marketo**, select **Set up**.</span></span>

1. <span data-ttu-id="ae0f0-114">Piešķiriet eksportēšanas galamērķim atpazīstamu nosaukumu laukā **Parādāmais nosaukums**.</span><span class="sxs-lookup"><span data-stu-id="ae0f0-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="ae0f0-115">Ievadiet savu **[Marketo klienta ID, klienta slepeno vārdu un REST galapunktu resursdatorā](https://developers.marketo.com/rest-api/authentication/)**.</span><span class="sxs-lookup"><span data-stu-id="ae0f0-115">Enter your **[Marketo client ID, Client secret and REST Endpoint Hostname](https://developers.marketo.com/rest-api/authentication/)**.</span></span>

1. <span data-ttu-id="ae0f0-116">Ievadiet savu **[Marketo saraksta ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span><span class="sxs-lookup"><span data-stu-id="ae0f0-116">Enter your **[Marketo list ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span></span> 

1. <span data-ttu-id="ae0f0-117">Atlasiet **Es piekrītu**, lai apstiprinātu **Datu konfidencialitāti un atbilstību**, un atlasiet opciju **Izveidot savienojumu**, lai inicializētu savienojumu ar Marketo.</span><span class="sxs-lookup"><span data-stu-id="ae0f0-117">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Marketo.</span></span>

1. <span data-ttu-id="ae0f0-118">Atlasiet opciju **Pievienot sevi kā eksporta lietotāju** un sniedziet savus Customer Insights akreditācijas datus.</span><span class="sxs-lookup"><span data-stu-id="ae0f0-118">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-connect-marketo.png" alt-text="Eksportēt ekrānuzņēmumu Marketo savienojumā":::

1. <span data-ttu-id="ae0f0-120">Lai konfigurētu eksportēšanu, atlasiet **Tālāk**.</span><span class="sxs-lookup"><span data-stu-id="ae0f0-120">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="ae0f0-121">Savienotāja konfigurēšana</span><span class="sxs-lookup"><span data-stu-id="ae0f0-121">Configure the connector</span></span>

1. <span data-ttu-id="ae0f0-122">Sadaļas **Datu atbilstības** laukā **E-pasts** atlasiet lauku, kas iekļauts vienotajā klientu profilā, kas pārstāv klienta e-pasta adresi.</span><span class="sxs-lookup"><span data-stu-id="ae0f0-122">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="ae0f0-123">Ja vēlaties, varat eksportēt **Vārds**, **Uzvārds**, **Pilsēta**, **Štats** un **Valsts/Reģions**  kā papildu laukus, lai izveidotu vairāk personalizētu e-pasta ziņojumu.</span><span class="sxs-lookup"><span data-stu-id="ae0f0-123">Optionally, you can export **First name**, **Last name**, **City**, **State**, and **Country/Region**  as additional fields to create more personalized emails.</span></span> <span data-ttu-id="ae0f0-124">Atlasiet **Pievienot atribūtu**, lai kartētu šos laukus.</span><span class="sxs-lookup"><span data-stu-id="ae0f0-124">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="ae0f0-125">Atlasiet segmentus, kurus vēlaties eksportēt.</span><span class="sxs-lookup"><span data-stu-id="ae0f0-125">Select the segments you want to export.</span></span> <span data-ttu-id="ae0f0-126">Kopsummā var eksportēt līdz 1 000 000 klientu profilu uz Marketo.</span><span class="sxs-lookup"><span data-stu-id="ae0f0-126">You can export up to 1 million customer profiles in total to Marketo.</span></span>

   :::image type="content" source="media/export-segment-marketo.png" alt-text="Atlasīt laukus un segmentus eksportēšanai uz Marketo":::

1. <span data-ttu-id="ae0f0-128">Atlasiet vienumu **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="ae0f0-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="ae0f0-129">Datu eksportēšana</span><span class="sxs-lookup"><span data-stu-id="ae0f0-129">Export the data</span></span>

<span data-ttu-id="ae0f0-130">Datus var [eksportēt pēc pieprasījuma](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="ae0f0-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="ae0f0-131">Eksportēšana arī tiks palaista ar katru [plānoto atsvaidzināšanu](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="ae0f0-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="ae0f0-132">Marketo tagad varat atrast jūsu segmentus sadaļā [Marketo saraksti](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="ae0f0-132">In Marketo, you can now find your segments under [Marketo lists](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="ae0f0-133">Zināmie ierobežojumi</span><span class="sxs-lookup"><span data-stu-id="ae0f0-133">Known limitations</span></span>

- <span data-ttu-id="ae0f0-134">Līdz 1 000 000 profilu, eksportējot uz Marketo.</span><span class="sxs-lookup"><span data-stu-id="ae0f0-134">Up to 1 million profiles per export to Marketo.</span></span>
- <span data-ttu-id="ae0f0-135">Eksportēšana uz Marketo ir ierobežota līdz segmentiem.</span><span class="sxs-lookup"><span data-stu-id="ae0f0-135">Exporting to Marketo is limited to segments.</span></span>
- <span data-ttu-id="ae0f0-136">Eksportējot segmentus kopā ar 1 000 000 profiliem, var būt nepieciešamas 3 stundas.</span><span class="sxs-lookup"><span data-stu-id="ae0f0-136">Exporting segments with a total of 1 million profiles can take up to 3 hours.</span></span> 
- <span data-ttu-id="ae0f0-137">To profilu skaits, ko var eksportēt uz Marketo, ir atkarīgs, un tas ir ierobežots jūsu līgumā ar Marketo.</span><span class="sxs-lookup"><span data-stu-id="ae0f0-137">The number of profiles that you can export to Marketo is dependent and limited on your contract with Marketo.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="ae0f0-138">Datu konfidencialitāte un atbilstība</span><span class="sxs-lookup"><span data-stu-id="ae0f0-138">Data privacy and compliance</span></span>

<span data-ttu-id="ae0f0-139">Ja iespējojat Dynamics 365 Customer Insights datu pārsūtīšanu uz Marketo, jūs atļaujat datu pārsūtīšanu ārpus atbilstības robežām Dynamics 365 Customer Insights, ieskaitot iespējami sensitīvus datus, piemēram, personas datus.</span><span class="sxs-lookup"><span data-stu-id="ae0f0-139">When you enable Dynamics 365 Customer Insights to transmit data to Marketo, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="ae0f0-140">Microsoft šos datus pārsūtīs pēc jūsu norādēm, bet jūs esat atbildīgs par to, lai nodrošinātu Marketo atbilstību konfidencialitātes vai drošības saistībām, kas jums varētu rasties.</span><span class="sxs-lookup"><span data-stu-id="ae0f0-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Marketo meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="ae0f0-141">Papildinformāciju skatiet rakstā [Microsoft Privātuma paziņojums](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="ae0f0-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="ae0f0-142">Jūsu Dynamics 365 Customer Insights administrators var noņemt šo eksportēšanas galamērķi jebkurā laikā, lai pārtrauktu izmantot šo funkcionalitāti.</span><span class="sxs-lookup"><span data-stu-id="ae0f0-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]