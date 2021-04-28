---
title: Customer Insights datu eksportēšana uz DotDigital
description: Uzziniet, kā konfigurēt savienojumu un eksportēt uz DotDigital.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 235bcdfa4a7c4c1a382778bd4f66c1a9f5b7beb1
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759968"
---
# <a name="export-segment-lists-to-dotdigital-preview"></a><span data-ttu-id="11b98-103">Segmentu sarakstu eksportēšana uz DotDigital (priekšskatījums)</span><span class="sxs-lookup"><span data-stu-id="11b98-103">Export segment lists to DotDigital (preview)</span></span>

<span data-ttu-id="11b98-104">Eksportējiet vienoto klientu profilu segmentus uz DotDigital adrešu grāmatām un izmantojiet tās kampaņām, e-pasta mārketingā un klientu segmentu izveidei ar DotDigital.</span><span class="sxs-lookup"><span data-stu-id="11b98-104">Export segments of unified customer profiles to DotDigital address books and use them for campaigns, email marketing, and to build customer segments with DotDigital.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="11b98-105">Savienojuma priekšnosacījumi</span><span class="sxs-lookup"><span data-stu-id="11b98-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="11b98-106">Jums ir [DotDigital konts](https://dotdigital.com/) un atbilstošie administratora akreditācijas dati.</span><span class="sxs-lookup"><span data-stu-id="11b98-106">You have a [DotDigital account](https://dotdigital.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="11b98-107">DotDigital ir esošas adrešu grāmatas un attiecīgie ID.</span><span class="sxs-lookup"><span data-stu-id="11b98-107">There are existing address books in DotDigital and the corresponding IDs.</span></span> <span data-ttu-id="11b98-108">ID var atrast URL, kad atlasāt un atverat adrešu grāmatu.</span><span class="sxs-lookup"><span data-stu-id="11b98-108">The ID can be found in the URL when you select and open an address book.</span></span> <span data-ttu-id="11b98-109">Papildinformāciju skatiet vietnē [DotDigital adrešu grāmatas](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="11b98-109">For more information, see [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>
-   <span data-ttu-id="11b98-110">Jums ir [konfigurēti segmenti](segments.md) auditorijas ieskatos.</span><span class="sxs-lookup"><span data-stu-id="11b98-110">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="11b98-111">Eksportētajos segmentos vienotajiem klientu profiliem ir lauks, kas norāda e-pasta adresi.</span><span class="sxs-lookup"><span data-stu-id="11b98-111">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="11b98-112">Zināmie ierobežojumi</span><span class="sxs-lookup"><span data-stu-id="11b98-112">Known limitations</span></span>

- <span data-ttu-id="11b98-113">Līdz 1 000 000 profilu, eksportējot uz DotDigital.</span><span class="sxs-lookup"><span data-stu-id="11b98-113">Up to 1 million profiles per export to DotDigital.</span></span>
- <span data-ttu-id="11b98-114">Eksportēšana uz DotDigital ir ierobežota līdz segmentiem.</span><span class="sxs-lookup"><span data-stu-id="11b98-114">Exporting to DotDigital is limited to segments.</span></span>
- <span data-ttu-id="11b98-115">Segmentu eksportēšanai kopā ar 1 000 000 profilu var būt nepieciešamas 3 stundas, jo pastāv ierobežojumi no pakalpojuma sniedzēja puses.</span><span class="sxs-lookup"><span data-stu-id="11b98-115">Exporting segments with a total of 1 million profiles can take up to 3 hours because of limitations on the provider side.</span></span> 
- <span data-ttu-id="11b98-116">To profilu skaits, ko var eksportēt uz DotDigital, ir atkarīgs, un tas ir ierobežots jūsu līgumā ar DotDigital.</span><span class="sxs-lookup"><span data-stu-id="11b98-116">The number of profiles that you can export to DotDigital is dependent and limited on your contract with DotDigital.</span></span>

## <a name="set-up-connection-to-dotdigital"></a><span data-ttu-id="11b98-117">Savienojuma ar DotDigital iestatīšana</span><span class="sxs-lookup"><span data-stu-id="11b98-117">Set up connection to DotDigital</span></span>

1. <span data-ttu-id="11b98-118">Dodieties uz **Administrators** > **Savienojumi**.</span><span class="sxs-lookup"><span data-stu-id="11b98-118">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="11b98-119">Atlasiet vienumu **Pievienot savienojumu** un atlasiet **DotDigital**, lai konfigurētu savienojumu.</span><span class="sxs-lookup"><span data-stu-id="11b98-119">Select **Add connection** and choose **DotDigital** to configure the connection.</span></span>

1. <span data-ttu-id="11b98-120">Laukā **Parādāmais nosaukums** piešķiriet savienojumam atpazīstamu nosaukumu.</span><span class="sxs-lookup"><span data-stu-id="11b98-120">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="11b98-121">Parādāmais nosaukums un nosaukuma veids raksturo šo savienojumu.</span><span class="sxs-lookup"><span data-stu-id="11b98-121">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="11b98-122">Ir ieteicams izvēlēties nosaukumu, kas paskaidro savienojuma nolūku.</span><span class="sxs-lookup"><span data-stu-id="11b98-122">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="11b98-123">Izvēlieties, kurš var izmantot šo savienojumu.</span><span class="sxs-lookup"><span data-stu-id="11b98-123">Choose who can use this connection.</span></span> <span data-ttu-id="11b98-124">Ja nesāksit nekādas darbības, noklusējums būs Administratori.</span><span class="sxs-lookup"><span data-stu-id="11b98-124">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="11b98-125">Papildinformāciju skatiet rakstā [Atļaut līdzstrādniekiem izmantot savienojumu eksportam](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="11b98-125">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="11b98-126">Ievadiet savu **DotDigital lietotājvārdu un paroli**.</span><span class="sxs-lookup"><span data-stu-id="11b98-126">Enter your **DotDigital username and password**.</span></span>

1. <span data-ttu-id="11b98-127">Ievadiet savu **[DotDigital adrešu grāmatas ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span><span class="sxs-lookup"><span data-stu-id="11b98-127">Enter your **[DotDigital address book ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span></span>

1. <span data-ttu-id="11b98-128">Atlasiet **Piekrītu**, lai apstiprinātu **Datu privātumu un atbilstību**.</span><span class="sxs-lookup"><span data-stu-id="11b98-128">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="11b98-129">Atlasiet **Izveidot savienojumu**, lai inicializētu savienojumu ar DotDigital.</span><span class="sxs-lookup"><span data-stu-id="11b98-129">Select **Connect** to initialize the connection to DotDigital.</span></span>

1. <span data-ttu-id="11b98-130">Atlasiet opciju **Pievienot sevi kā eksporta lietotāju** un sniedziet savus Customer Insights akreditācijas datus.</span><span class="sxs-lookup"><span data-stu-id="11b98-130">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="11b98-131">Lai pabeigtu savienošanu, atlasiet **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="11b98-131">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="11b98-132">Eksporta konfigurēšana</span><span class="sxs-lookup"><span data-stu-id="11b98-132">Configure an export</span></span>

<span data-ttu-id="11b98-133">Šo eksportu varat konfigurēt, ja jums ir piekļuve šā veida pieslēgumam.</span><span class="sxs-lookup"><span data-stu-id="11b98-133">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="11b98-134">Papildinformāciju skatiet rakstā [Atļaujas, kas nepieciešamas eksporta konfigurēšanai](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="11b98-134">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="11b98-135">Pārejiet uz **Dati** > **Eksportēšana**.</span><span class="sxs-lookup"><span data-stu-id="11b98-135">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="11b98-136">Lai izveidotu jaunu eksportu, atlasiet **Pievienot galamērķi**.</span><span class="sxs-lookup"><span data-stu-id="11b98-136">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="11b98-137">Laukā **Savienošana eksportam** atlasiet savienojumu no sadaļas DotDigital.</span><span class="sxs-lookup"><span data-stu-id="11b98-137">In the **Connection for export** field, choose a connection from the DotDigital section.</span></span> <span data-ttu-id="11b98-138">Ja šis sadaļas nosaukums nav redzams, šāda veida savienojumi jums nav pieejami.</span><span class="sxs-lookup"><span data-stu-id="11b98-138">If you don't see this section name, there are no connections of this type available to you.</span></span>


1. <span data-ttu-id="11b98-139">Sadaļas **Datu atbilstības** laukā **E-pasts** atlasiet lauku, kas iekļauts vienotajā klientu profilā, kas pārstāv klienta e-pasta adresi.</span><span class="sxs-lookup"><span data-stu-id="11b98-139">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="11b98-140">Veiciet tās pašas darbības ar citiem neobligātajiem laukiem, piemēram, **Vārds**, **Uzvārds**, **Pilns vārds**, **Dzimums** un **Pasta indekss**.</span><span class="sxs-lookup"><span data-stu-id="11b98-140">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Full name**, **Gender**, and **Post code**.</span></span>

1. <span data-ttu-id="11b98-141">Atlasiet segmentus, kurus vēlaties eksportēt.</span><span class="sxs-lookup"><span data-stu-id="11b98-141">Select the segments you want to export.</span></span> <span data-ttu-id="11b98-142">Kopsummā var eksportēt līdz 1 000 000 klientu profilu uz DotDigital.</span><span class="sxs-lookup"><span data-stu-id="11b98-142">You can export up to 1 million customer profiles in total to DotDigital.</span></span>

1. <span data-ttu-id="11b98-143">Atlasiet vienumu **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="11b98-143">Select **Save**.</span></span>

<span data-ttu-id="11b98-144">Eksporta saglabāšana automātiski nepalaiž eksportu.</span><span class="sxs-lookup"><span data-stu-id="11b98-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="11b98-145">Eksports tiek palaists ar katru [plānoto atsvaidzināšanu](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="11b98-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="11b98-146">Varat arī [eksportēt datus pēc pieprasījuma](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="11b98-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 
 
<span data-ttu-id="11b98-147">DotDigital tagad varat atrast savus segmentus [DotDigital adrešu grāmatās](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="11b98-147">In DotDigital, you can now find your segments in [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="11b98-148">Datu konfidencialitāte un atbilstība</span><span class="sxs-lookup"><span data-stu-id="11b98-148">Data privacy and compliance</span></span>

<span data-ttu-id="11b98-149">Ja iespējojat Dynamics 365 Customer Insights datu pārsūtīšanai uz DotDigital, jūs atļaujat datu pārsūtīšanu ārpus atbilstības robežām Dynamics 365 Customer Insights, ieskaitot iespējami sensitīvus datus, piemēram, personas datus.</span><span class="sxs-lookup"><span data-stu-id="11b98-149">When you enable Dynamics 365 Customer Insights to transmit data to DotDigital, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="11b98-150">Microsoft šos datus pārsūtīs pēc jūsu norādēm, bet jūs esat atbildīgs par to, lai nodrošinātu DotDigital atbilstību konfidencialitātes vai drošības saistībām, kas jums varētu rasties.</span><span class="sxs-lookup"><span data-stu-id="11b98-150">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that DotDigital meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="11b98-151">Papildinformāciju skatiet rakstā [Microsoft Privātuma paziņojums](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="11b98-151">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="11b98-152">Jūsu Dynamics 365 Customer Insights administrators var noņemt šo eksportēšanas galamērķi jebkurā laikā, lai pārtrauktu izmantot šo funkcionalitāti.</span><span class="sxs-lookup"><span data-stu-id="11b98-152">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
