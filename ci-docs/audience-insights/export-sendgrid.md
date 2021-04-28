---
title: Customer Insights datu eksportēšana uz SendGrid
description: Uzziniet, kā konfigurēt savienojumu un eksportēt uz SendGrid.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: a4c64cf77c682e07f3d0759c43355336b5806fc8
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759774"
---
# <a name="export-segments-to-sendgrid-preview"></a><span data-ttu-id="235d6-103">Segmentu eksportēšana uz SendGrid (priekšskatījums)</span><span class="sxs-lookup"><span data-stu-id="235d6-103">Export segments to SendGrid (preview)</span></span>

<span data-ttu-id="235d6-104">Eksportējiet vienoto klientu profilu segmentus uz SendGrid kontaktpersonu sarakstiem un izmantojiet tos kampaņām un e-pasta mārketingam lietojumprogrammā SendGrid.</span><span class="sxs-lookup"><span data-stu-id="235d6-104">Export segments of unified customer profiles to SendGrid contact lists and use them for campaigns and email marketing in SendGrid.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="235d6-105">Savienojuma priekšnosacījumi</span><span class="sxs-lookup"><span data-stu-id="235d6-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="235d6-106">Jums ir [SendGrid konts](https://sendgrid.com/) un atbilstošie administratora akreditācijas dati.</span><span class="sxs-lookup"><span data-stu-id="235d6-106">You have a [SendGrid account](https://sendgrid.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="235d6-107">SendGrid ir esoši kontaktpersonu saraksti un attiecīgie ID.</span><span class="sxs-lookup"><span data-stu-id="235d6-107">There are existing contact lists in SendGrid and the corresponding IDs.</span></span> <span data-ttu-id="235d6-108">Papildinformāciju skatiet rakstā [SendGrid - Pārvaldīt kontaktus](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span><span class="sxs-lookup"><span data-stu-id="235d6-108">For more information, see [SendGrid - Manage contacts](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span></span>
-   <span data-ttu-id="235d6-109">Jums ir [konfigurēti segmenti](segments.md) auditorijas ieskatos.</span><span class="sxs-lookup"><span data-stu-id="235d6-109">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="235d6-110">Eksportētajos segmentos vienotajiem klientu profiliem ir lauks, kas norāda e-pasta adresi.</span><span class="sxs-lookup"><span data-stu-id="235d6-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="235d6-111">Zināmie ierobežojumi</span><span class="sxs-lookup"><span data-stu-id="235d6-111">Known limitations</span></span>

- <span data-ttu-id="235d6-112">Kopumā līdz 100 000 profiliem uz SendGrid.</span><span class="sxs-lookup"><span data-stu-id="235d6-112">Up to 100'000 profiles in total to SendGrid.</span></span>
- <span data-ttu-id="235d6-113">Eksportēšana uz SendGrid ir ierobežota līdz segmentiem.</span><span class="sxs-lookup"><span data-stu-id="235d6-113">Exporting to SendGrid is limited to segments.</span></span>
- <span data-ttu-id="235d6-114">100 000 profilu eksportēšana uz SendGrid var aizņemt dažas stundas.</span><span class="sxs-lookup"><span data-stu-id="235d6-114">Exporting up to 100'000 profiles to SendGrid can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="235d6-115">To profilu skaits, ko var eksportēt uz SendGrid, ir atkarīgs, un tas ir ierobežots jūsu līgumā ar SendGrid.</span><span class="sxs-lookup"><span data-stu-id="235d6-115">The number of profiles that you can export to SendGrid is dependent and limited on your contract with SendGrid.</span></span>

## <a name="set-up-connection-to-sendgrid"></a><span data-ttu-id="235d6-116">Savienojuma ar SendGrid iestatīšana</span><span class="sxs-lookup"><span data-stu-id="235d6-116">Set up connection to SendGrid</span></span>

1. <span data-ttu-id="235d6-117">Dodieties uz **Administrators** > **Savienojumi**.</span><span class="sxs-lookup"><span data-stu-id="235d6-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="235d6-118">Atlasiet vienumu **Pievienot savienojumu** un atlasiet **SendGrid**, lai konfigurētu savienojumu.</span><span class="sxs-lookup"><span data-stu-id="235d6-118">Select **Add connection** and choose **SendGrid** to configure the connection.</span></span>

1. <span data-ttu-id="235d6-119">Laukā **Parādāmais nosaukums** piešķiriet savienojumam atpazīstamu nosaukumu.</span><span class="sxs-lookup"><span data-stu-id="235d6-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="235d6-120">Parādāmais nosaukums un nosaukuma veids raksturo šo savienojumu.</span><span class="sxs-lookup"><span data-stu-id="235d6-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="235d6-121">Ir ieteicams izvēlēties nosaukumu, kas paskaidro savienojuma nolūku.</span><span class="sxs-lookup"><span data-stu-id="235d6-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="235d6-122">Izvēlieties, kurš var izmantot šo savienojumu.</span><span class="sxs-lookup"><span data-stu-id="235d6-122">Choose who can use this connection.</span></span> <span data-ttu-id="235d6-123">Ja nesāksit nekādas darbības, noklusējums būs Administratori.</span><span class="sxs-lookup"><span data-stu-id="235d6-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="235d6-124">Papildinformāciju skatiet rakstā [Atļaut līdzstrādniekiem izmantot savienojumu eksportam](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="235d6-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="235d6-125">Ievadiet savu **SendGrid API atslēgu** [SendGrid API atslēga](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span><span class="sxs-lookup"><span data-stu-id="235d6-125">Enter your **SendGrid API key** [SendGrid API key](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span></span>

1. <span data-ttu-id="235d6-126">Atlasiet **Piekrītu**, lai apstiprinātu **Datu konfidencialitāti un atbilstību**.</span><span class="sxs-lookup"><span data-stu-id="235d6-126">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="235d6-127">Atlasiet **Izveidot savienojumu**, lai inicializētu savienojumu ar SendGrid.</span><span class="sxs-lookup"><span data-stu-id="235d6-127">Select **Connect** to initialize the connection to SendGrid.</span></span>

1. <span data-ttu-id="235d6-128">Atlasiet opciju **Pievienot sevi kā eksporta lietotāju** un sniedziet savus Customer Insights akreditācijas datus.</span><span class="sxs-lookup"><span data-stu-id="235d6-128">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="235d6-129">Lai pabeigtu savienošanu, atlasiet **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="235d6-129">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="235d6-130">Eksporta konfigurēšana</span><span class="sxs-lookup"><span data-stu-id="235d6-130">Configure an export</span></span>

<span data-ttu-id="235d6-131">Šo eksportu varat konfigurēt, ja jums ir piekļuve šā veida pieslēgumam.</span><span class="sxs-lookup"><span data-stu-id="235d6-131">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="235d6-132">Papildinformāciju skatiet rakstā [Atļaujas, kas nepieciešamas eksporta konfigurēšanai](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="235d6-132">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="235d6-133">Pārejiet uz **Dati** > **Eksportēšana**.</span><span class="sxs-lookup"><span data-stu-id="235d6-133">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="235d6-134">Lai izveidotu jaunu eksportu, atlasiet **Pievienot galamērķi**.</span><span class="sxs-lookup"><span data-stu-id="235d6-134">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="235d6-135">Laukā **Savienošana eksportam** atlasiet savienojumu no sadaļas SendGrid.</span><span class="sxs-lookup"><span data-stu-id="235d6-135">In the **Connection for export** field, choose a connection from the SendGrid section.</span></span> <span data-ttu-id="235d6-136">Ja šis sadaļas nosaukums nav redzams, šāda veida savienojumi jums nav pieejami.</span><span class="sxs-lookup"><span data-stu-id="235d6-136">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="235d6-137">Ievadiet savu **[SendGrid saraksta ID](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span><span class="sxs-lookup"><span data-stu-id="235d6-137">Enter your **[SendGrid list ID](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span></span>

1. <span data-ttu-id="235d6-138">Sadaļas **Datu atbilstības** laukā **E-pasts** atlasiet lauku, kas iekļauts vienotajā klientu profilā, kas pārstāv klienta e-pasta adresi.</span><span class="sxs-lookup"><span data-stu-id="235d6-138">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="235d6-139">Veiciet tās pašas darbības ar citiem neobligātajiem laukiem, piemēram, **Vārds**, **Uzvārds**, **Valsts/Reģions**, **Štats**, **Pilsēta**, and **Pasta indekss**.</span><span class="sxs-lookup"><span data-stu-id="235d6-139">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Country/Region**, **State**, **City**, and **Post code**.</span></span>

1. <span data-ttu-id="235d6-140">Atlasiet segmentus, kurus vēlaties eksportēt.</span><span class="sxs-lookup"><span data-stu-id="235d6-140">Select the segments you want to export.</span></span> <span data-ttu-id="235d6-141">Mēs **stingri iesakām eksportēt kopumā ne vairāk kā 100 000 klientu profilu** programmā SendGrid.</span><span class="sxs-lookup"><span data-stu-id="235d6-141">We strongly **recommend to not export more than 100'000 customer profiles in total** to SendGrid.</span></span> 

1. <span data-ttu-id="235d6-142">Atlasiet vienumu **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="235d6-142">Select **Save**.</span></span>

<span data-ttu-id="235d6-143">Eksporta saglabāšana automātiski nepalaiž eksportu.</span><span class="sxs-lookup"><span data-stu-id="235d6-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="235d6-144">Eksports tiek palaists ar katru [plānoto atsvaidzināšanu](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="235d6-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="235d6-145">Varat arī [eksportēt datus pēc pieprasījuma](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="235d6-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="235d6-146">Datu konfidencialitāte un atbilstība</span><span class="sxs-lookup"><span data-stu-id="235d6-146">Data privacy and compliance</span></span>

<span data-ttu-id="235d6-147">Ja iespējojat Dynamics 365 Customer Insights datu pārsūtīšanu uz SendGrid, jūs atļaujat datu pārsūtīšanu ārpus atbilstības robežām Dynamics 365 Customer Insights, ieskaitot iespējami sensitīvus datus, piemēram, personas datus.</span><span class="sxs-lookup"><span data-stu-id="235d6-147">When you enable Dynamics 365 Customer Insights to transmit data to SendGrid, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="235d6-148">Microsoft šos datus pārsūtīs pēc jūsu norādēm, bet jūs esat atbildīgs par to, lai nodrošinātu SendGrid atbilstību konfidencialitātes vai drošības saistībām, kas jums varētu rasties.</span><span class="sxs-lookup"><span data-stu-id="235d6-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that SendGrid meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="235d6-149">Papildinformāciju skatiet rakstā [Microsoft Privātuma paziņojums](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="235d6-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="235d6-150">Jūsu Dynamics 365 Customer Insights administrators var noņemt šo eksportēšanas galamērķi jebkurā laikā, lai pārtrauktu izmantot šo funkcionalitāti.</span><span class="sxs-lookup"><span data-stu-id="235d6-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]