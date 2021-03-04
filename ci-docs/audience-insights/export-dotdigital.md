---
title: Customer Insights datu eksportēšana uz DotDigital
description: Uzziniet, kā konfigurēt savienojumu ar DotDigital.
ms.date: 11/14/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 573a22e24f84c65fc4d21faf823cace801cc7ea3
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269109"
---
# <a name="connector-for-dotdigital-preview"></a><span data-ttu-id="ab305-103">Savienotājs ar DotDigital (priekšskatījums)</span><span class="sxs-lookup"><span data-stu-id="ab305-103">Connector for DotDigital (preview)</span></span>

<span data-ttu-id="ab305-104">Eksportējiet vienoto klientu profilu segmentus uz DotDigital adrešu grāmatām un izmantojiet tās kampaņām, e-pasta mārketingā un klientu segmentu izveidei ar DotDigital.</span><span class="sxs-lookup"><span data-stu-id="ab305-104">Export segments of unified customer profiles to DotDigital address books and use them for campaigns, email marketing, and to build customer segments with DotDigital.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="ab305-105">Priekšnosacījumi</span><span class="sxs-lookup"><span data-stu-id="ab305-105">Prerequisites</span></span>

-   <span data-ttu-id="ab305-106">Jums ir [DotDigital konts](https://dotdigital.com/) un atbilstošie administratora akreditācijas dati.</span><span class="sxs-lookup"><span data-stu-id="ab305-106">You have a [DotDigital account](https://dotdigital.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="ab305-107">DotDigital ir esošas adrešu grāmatas un attiecīgie ID.</span><span class="sxs-lookup"><span data-stu-id="ab305-107">There are existing address books in DotDigital and the corresponding IDs.</span></span> <span data-ttu-id="ab305-108">ID var atrast URL, kad atlasāt un atverat adrešu grāmatu.</span><span class="sxs-lookup"><span data-stu-id="ab305-108">The ID can be found in the URL when you select and open an address book.</span></span> <span data-ttu-id="ab305-109">Papildinformāciju skatiet vietnē [DotDigital adrešu grāmatas](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="ab305-109">For more information, see [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>
-   <span data-ttu-id="ab305-110">Jums ir [konfigurēti segmenti](segments.md) auditorijas ieskatos.</span><span class="sxs-lookup"><span data-stu-id="ab305-110">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="ab305-111">Eksportētajos segmentos vienotajiem klientu profiliem ir lauks, kas norāda e-pasta adresi.</span><span class="sxs-lookup"><span data-stu-id="ab305-111">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-dotdigital"></a><span data-ttu-id="ab305-112">Savienojuma izveide ar DotDigital</span><span class="sxs-lookup"><span data-stu-id="ab305-112">Connect to DotDigital</span></span>

1. <span data-ttu-id="ab305-113">Dodieties uz sadaļu **Administrators** > **Eksportēšanas galamērķi**.</span><span class="sxs-lookup"><span data-stu-id="ab305-113">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="ab305-114">Sadaļā **DotDigital** atlasiet vienumu **Iestatīt**.</span><span class="sxs-lookup"><span data-stu-id="ab305-114">Under **DotDigital**, select **Set up**.</span></span>

1. <span data-ttu-id="ab305-115">Piešķiriet eksportēšanas galamērķim atpazīstamu nosaukumu laukā **Parādāmais nosaukums**.</span><span class="sxs-lookup"><span data-stu-id="ab305-115">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/DotDigital_config.PNG" alt-text="Konfigurēšanas rūts DotDigital eksportēšanai.":::

1. <span data-ttu-id="ab305-117">Ievadiet savu **DotDigital lietotājvārdu un paroli**.</span><span class="sxs-lookup"><span data-stu-id="ab305-117">Enter your **DotDigital username and password**.</span></span>

1. <span data-ttu-id="ab305-118">Ievadiet savu **[DotDigital adrešu grāmatas ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span><span class="sxs-lookup"><span data-stu-id="ab305-118">Enter your **[DotDigital address book ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span></span>

1. <span data-ttu-id="ab305-119">Atlasiet **Piekrītu**, lai apstiprinātu **Datu privātumu un atbilstību**.</span><span class="sxs-lookup"><span data-stu-id="ab305-119">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="ab305-120">Atlasiet **Izveidot savienojumu**, lai inicializētu savienojumu ar DotDigital.</span><span class="sxs-lookup"><span data-stu-id="ab305-120">Select **Connect** to initialize the connection to DotDigital.</span></span>

1. <span data-ttu-id="ab305-121">Atlasiet opciju **Pievienot sevi kā eksporta lietotāju** un sniedziet savus Customer Insights akreditācijas datus.</span><span class="sxs-lookup"><span data-stu-id="ab305-121">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="ab305-122">Lai konfigurētu eksportēšanu, atlasiet **Tālāk**.</span><span class="sxs-lookup"><span data-stu-id="ab305-122">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="ab305-123">Savienotāja konfigurēšana</span><span class="sxs-lookup"><span data-stu-id="ab305-123">Configure the connector</span></span>

1. <span data-ttu-id="ab305-124">Sadaļas **Datu atbilstības** laukā **E-pasts** atlasiet lauku, kas iekļauts vienotajā klientu profilā, kas pārstāv klienta e-pasta adresi.</span><span class="sxs-lookup"><span data-stu-id="ab305-124">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="ab305-125">Veiciet tās pašas darbības ar citiem neobligātajiem laukiem, piemēram, **Vārds**, **Uzvārds**, **Pilns vārds**, **Dzimums** un **Pasta indekss**.</span><span class="sxs-lookup"><span data-stu-id="ab305-125">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Full name**, **Gender**, and **Post code**.</span></span>

1. <span data-ttu-id="ab305-126">Atlasiet segmentus, kurus vēlaties eksportēt.</span><span class="sxs-lookup"><span data-stu-id="ab305-126">Select the segments you want to export.</span></span> <span data-ttu-id="ab305-127">Kopsummā var eksportēt līdz 1 000 000 klientu profilu uz DotDigital.</span><span class="sxs-lookup"><span data-stu-id="ab305-127">You can export up to 1 million customer profiles in total to DotDigital.</span></span>

1. <span data-ttu-id="ab305-128">Atlasiet vienumu **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="ab305-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="ab305-129">Datu eksportēšana</span><span class="sxs-lookup"><span data-stu-id="ab305-129">Export the data</span></span>

<span data-ttu-id="ab305-130">Datus var [eksportēt pēc pieprasījuma](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="ab305-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="ab305-131">Eksportēšana arī tiks palaista ar katru [plānoto atsvaidzināšanu](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="ab305-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="ab305-132">DotDigital tagad varat atrast savus segmentus [DotDigital adrešu grāmatās](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="ab305-132">In DotDigital, you can now find your segments in [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="ab305-133">Zināmie ierobežojumi</span><span class="sxs-lookup"><span data-stu-id="ab305-133">Known limitations</span></span>

- <span data-ttu-id="ab305-134">Līdz 1 000 000 profilu, eksportējot uz DotDigital.</span><span class="sxs-lookup"><span data-stu-id="ab305-134">Up to 1 million profiles per export to DotDigital.</span></span>
- <span data-ttu-id="ab305-135">Eksportēšana uz DotDigital ir ierobežota līdz segmentiem.</span><span class="sxs-lookup"><span data-stu-id="ab305-135">Exporting to DotDigital is limited to segments.</span></span>
- <span data-ttu-id="ab305-136">Segmentu eksportēšanai kopā ar 1 000 000 profilu var būt nepieciešamas 3 stundas, jo pastāv ierobežojumi no pakalpojuma sniedzēja puses.</span><span class="sxs-lookup"><span data-stu-id="ab305-136">Exporting segments with a total of 1 million profiles can take up to 3 hours because of limitations on the provider side.</span></span> 
- <span data-ttu-id="ab305-137">To profilu skaits, ko var eksportēt uz DotDigital, ir atkarīgs, un tas ir ierobežots jūsu līgumā ar DotDigital.</span><span class="sxs-lookup"><span data-stu-id="ab305-137">The number of profiles that you can export to DotDigital is dependent and limited on your contract with DotDigital.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="ab305-138">Datu konfidencialitāte un atbilstība</span><span class="sxs-lookup"><span data-stu-id="ab305-138">Data privacy and compliance</span></span>

<span data-ttu-id="ab305-139">Ja iespējojat Dynamics 365 Customer Insights datu pārsūtīšanai uz DotDigital, jūs atļaujat datu pārsūtīšanu ārpus atbilstības robežām Dynamics 365 Customer Insights, ieskaitot iespējami sensitīvus datus, piemēram, personas datus.</span><span class="sxs-lookup"><span data-stu-id="ab305-139">When you enable Dynamics 365 Customer Insights to transmit data to DotDigital, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="ab305-140">Microsoft šos datus pārsūtīs pēc jūsu norādēm, bet jūs esat atbildīgs par to, lai nodrošinātu DotDigital atbilstību konfidencialitātes vai drošības saistībām, kas jums varētu rasties.</span><span class="sxs-lookup"><span data-stu-id="ab305-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that DotDigital meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="ab305-141">Papildinformāciju skatiet rakstā [Microsoft Privātuma paziņojums](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="ab305-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="ab305-142">Jūsu Dynamics 365 Customer Insights administrators var noņemt šo eksportēšanas galamērķi jebkurā laikā, lai pārtrauktu izmantot šo funkcionalitāti.</span><span class="sxs-lookup"><span data-stu-id="ab305-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]