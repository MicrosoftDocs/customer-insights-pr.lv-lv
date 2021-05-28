---
title: Customer Insights datu eksportēšana uz SendGrid
description: Uzziniet, kā konfigurēt savienojumu un eksportēt uz SendGrid.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 5d3d61d2b5b68079c7717e41dee5a2f698f2b62c
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976925"
---
# <a name="export-segments-to-sendgrid-preview"></a><span data-ttu-id="80a40-103">Segmentu eksportēšana uz SendGrid (priekšskatījums)</span><span class="sxs-lookup"><span data-stu-id="80a40-103">Export segments to SendGrid (preview)</span></span>

<span data-ttu-id="80a40-104">Eksportējiet vienoto klientu profilu segmentus uz SendGrid kontaktpersonu sarakstiem un izmantojiet tos kampaņām un e-pasta mārketingam lietojumprogrammā SendGrid.</span><span class="sxs-lookup"><span data-stu-id="80a40-104">Export segments of unified customer profiles to SendGrid contact lists and use them for campaigns and email marketing in SendGrid.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="80a40-105">Savienojuma priekšnosacījumi</span><span class="sxs-lookup"><span data-stu-id="80a40-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="80a40-106">Jums ir [SendGrid konts](https://sendgrid.com/) un atbilstošie administratora akreditācijas dati.</span><span class="sxs-lookup"><span data-stu-id="80a40-106">You have a [SendGrid account](https://sendgrid.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="80a40-107">SendGrid ir esoši kontaktpersonu saraksti un attiecīgie ID.</span><span class="sxs-lookup"><span data-stu-id="80a40-107">There are existing contact lists in SendGrid and the corresponding IDs.</span></span> <span data-ttu-id="80a40-108">Papildinformāciju skatiet rakstā [SendGrid - Pārvaldīt kontaktus](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span><span class="sxs-lookup"><span data-stu-id="80a40-108">For more information, see [SendGrid - Manage contacts](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span></span>
-   <span data-ttu-id="80a40-109">Jums ir [konfigurēti segmenti](segments.md) auditorijas ieskatos.</span><span class="sxs-lookup"><span data-stu-id="80a40-109">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="80a40-110">Eksportētajos segmentos vienotajiem klientu profiliem ir lauks, kas norāda e-pasta adresi.</span><span class="sxs-lookup"><span data-stu-id="80a40-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="80a40-111">Zināmie ierobežojumi</span><span class="sxs-lookup"><span data-stu-id="80a40-111">Known limitations</span></span>

- <span data-ttu-id="80a40-112">Kopumā līdz 100 000 profiliem uz SendGrid.</span><span class="sxs-lookup"><span data-stu-id="80a40-112">Up to 100'000 profiles in total to SendGrid.</span></span>
- <span data-ttu-id="80a40-113">Eksportēšana uz SendGrid ir ierobežota līdz segmentiem.</span><span class="sxs-lookup"><span data-stu-id="80a40-113">Exporting to SendGrid is limited to segments.</span></span>
- <span data-ttu-id="80a40-114">100 000 profilu eksportēšana uz SendGrid var aizņemt dažas stundas.</span><span class="sxs-lookup"><span data-stu-id="80a40-114">Exporting up to 100'000 profiles to SendGrid can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="80a40-115">To profilu skaits, ko var eksportēt uz SendGrid, ir atkarīgs, un tas ir ierobežots jūsu līgumā ar SendGrid.</span><span class="sxs-lookup"><span data-stu-id="80a40-115">The number of profiles that you can export to SendGrid is dependent and limited on your contract with SendGrid.</span></span>

## <a name="set-up-connection-to-sendgrid"></a><span data-ttu-id="80a40-116">Savienojuma ar SendGrid iestatīšana</span><span class="sxs-lookup"><span data-stu-id="80a40-116">Set up connection to SendGrid</span></span>

1. <span data-ttu-id="80a40-117">Dodieties uz **Administrators** > **Savienojumi**.</span><span class="sxs-lookup"><span data-stu-id="80a40-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="80a40-118">Atlasiet vienumu **Pievienot savienojumu** un atlasiet **SendGrid**, lai konfigurētu savienojumu.</span><span class="sxs-lookup"><span data-stu-id="80a40-118">Select **Add connection** and choose **SendGrid** to configure the connection.</span></span>

1. <span data-ttu-id="80a40-119">Laukā **Parādāmais nosaukums** piešķiriet savienojumam atpazīstamu nosaukumu.</span><span class="sxs-lookup"><span data-stu-id="80a40-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="80a40-120">Parādāmais nosaukums un nosaukuma veids raksturo šo savienojumu.</span><span class="sxs-lookup"><span data-stu-id="80a40-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="80a40-121">Ir ieteicams izvēlēties nosaukumu, kas paskaidro savienojuma nolūku.</span><span class="sxs-lookup"><span data-stu-id="80a40-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="80a40-122">Izvēlieties, kurš var izmantot šo savienojumu.</span><span class="sxs-lookup"><span data-stu-id="80a40-122">Choose who can use this connection.</span></span> <span data-ttu-id="80a40-123">Ja nesāksit nekādas darbības, noklusējums būs Administratori.</span><span class="sxs-lookup"><span data-stu-id="80a40-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="80a40-124">Papildinformāciju skatiet rakstā [Atļaut līdzstrādniekiem izmantot savienojumu eksportam](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="80a40-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="80a40-125">Ievadiet savu **SendGrid API atslēgu** [SendGrid API atslēga](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span><span class="sxs-lookup"><span data-stu-id="80a40-125">Enter your **SendGrid API key** [SendGrid API key](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span></span>

1. <span data-ttu-id="80a40-126">Atlasiet **Piekrītu**, lai apstiprinātu **Datu konfidencialitāti un atbilstību**.</span><span class="sxs-lookup"><span data-stu-id="80a40-126">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="80a40-127">Atlasiet **Izveidot savienojumu**, lai inicializētu savienojumu ar SendGrid.</span><span class="sxs-lookup"><span data-stu-id="80a40-127">Select **Connect** to initialize the connection to SendGrid.</span></span>

1. <span data-ttu-id="80a40-128">Atlasiet opciju **Pievienot sevi kā eksporta lietotāju** un sniedziet savus Customer Insights akreditācijas datus.</span><span class="sxs-lookup"><span data-stu-id="80a40-128">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="80a40-129">Lai pabeigtu savienošanu, atlasiet **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="80a40-129">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="80a40-130">Eksporta konfigurēšana</span><span class="sxs-lookup"><span data-stu-id="80a40-130">Configure an export</span></span>

<span data-ttu-id="80a40-131">Šo eksportu varat konfigurēt, ja jums ir piekļuve šā veida pieslēgumam.</span><span class="sxs-lookup"><span data-stu-id="80a40-131">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="80a40-132">Papildinformāciju skatiet rakstā [Atļaujas, kas nepieciešamas eksporta konfigurēšanai](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="80a40-132">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="80a40-133">Pārejiet uz **Dati** > **Eksportēšana**.</span><span class="sxs-lookup"><span data-stu-id="80a40-133">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="80a40-134">Lai izveidotu jaunu eksportu, atlasiet **Pievienot galamērķi**.</span><span class="sxs-lookup"><span data-stu-id="80a40-134">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="80a40-135">Laukā **Savienošana eksportam** atlasiet savienojumu no sadaļas SendGrid.</span><span class="sxs-lookup"><span data-stu-id="80a40-135">In the **Connection for export** field, choose a connection from the SendGrid section.</span></span> <span data-ttu-id="80a40-136">Ja šis sadaļas nosaukums nav redzams, šāda veida savienojumi jums nav pieejami.</span><span class="sxs-lookup"><span data-stu-id="80a40-136">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="80a40-137">Ievadiet savu **[SendGrid saraksta ID](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span><span class="sxs-lookup"><span data-stu-id="80a40-137">Enter your **[SendGrid list ID](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span></span>

1. <span data-ttu-id="80a40-138">Sadaļas **Datu atbilstības** laukā **E-pasts** atlasiet lauku, kas iekļauts vienotajā klientu profilā, kas pārstāv klienta e-pasta adresi.</span><span class="sxs-lookup"><span data-stu-id="80a40-138">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="80a40-139">Veiciet tās pašas darbības ar citiem neobligātajiem laukiem, piemēram, **Vārds**, **Uzvārds**, **Valsts/Reģions**, **Štats**, **Pilsēta**, and **Pasta indekss**.</span><span class="sxs-lookup"><span data-stu-id="80a40-139">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Country/Region**, **State**, **City**, and **Post code**.</span></span>

1. <span data-ttu-id="80a40-140">Atlasiet segmentus, kurus vēlaties eksportēt.</span><span class="sxs-lookup"><span data-stu-id="80a40-140">Select the segments you want to export.</span></span> <span data-ttu-id="80a40-141">Mēs **stingri iesakām eksportēt kopumā ne vairāk kā 100 000 klientu profilu** programmā SendGrid.</span><span class="sxs-lookup"><span data-stu-id="80a40-141">We strongly **recommend to not export more than 100'000 customer profiles in total** to SendGrid.</span></span> 

1. <span data-ttu-id="80a40-142">Atlasiet vienumu **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="80a40-142">Select **Save**.</span></span>

<span data-ttu-id="80a40-143">Eksporta saglabāšana automātiski nepalaiž eksportu.</span><span class="sxs-lookup"><span data-stu-id="80a40-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="80a40-144">Eksports tiek palaists ar katru [plānoto atsvaidzināšanu](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="80a40-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="80a40-145">Varat arī [eksportēt datus pēc pieprasījuma](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="80a40-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="80a40-146">Datu konfidencialitāte un atbilstība</span><span class="sxs-lookup"><span data-stu-id="80a40-146">Data privacy and compliance</span></span>

<span data-ttu-id="80a40-147">Ja iespējojat Dynamics 365 Customer Insights datu pārsūtīšanu uz SendGrid, jūs atļaujat datu pārsūtīšanu ārpus atbilstības robežām Dynamics 365 Customer Insights, ieskaitot iespējami sensitīvus datus, piemēram, personas datus.</span><span class="sxs-lookup"><span data-stu-id="80a40-147">When you enable Dynamics 365 Customer Insights to transmit data to SendGrid, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="80a40-148">Microsoft šos datus pārsūtīs pēc jūsu norādēm, bet jūs esat atbildīgs par to, lai nodrošinātu SendGrid atbilstību konfidencialitātes vai drošības saistībām, kas jums varētu rasties.</span><span class="sxs-lookup"><span data-stu-id="80a40-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that SendGrid meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="80a40-149">Papildinformāciju skatiet rakstā [Microsoft Privātuma paziņojums](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="80a40-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="80a40-150">Jūsu Dynamics 365 Customer Insights administrators var noņemt šo eksportēšanas galamērķi jebkurā laikā, lai pārtrauktu izmantot šo funkcionalitāti.</span><span class="sxs-lookup"><span data-stu-id="80a40-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]