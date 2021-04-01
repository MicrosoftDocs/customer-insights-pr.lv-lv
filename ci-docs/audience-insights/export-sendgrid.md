---
title: Customer Insights datu eksportēšana uz SendGrid
description: Uzziniet, kā konfigurēt savienojumu ar SendGrid.
ms.date: 12/08/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 1a1f679fa42d47d524ebfdd6e931ae2822565f77
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597290"
---
# <a name="connector-for-sendgrid-preview"></a><span data-ttu-id="bba9b-103">Savienotājs ar SendGrid (priekšskatījums)</span><span class="sxs-lookup"><span data-stu-id="bba9b-103">Connector for SendGrid (preview)</span></span>

<span data-ttu-id="bba9b-104">Eksportējiet vienoto klientu profilu segmentus uz SendGrid kontaktpersonu sarakstiem un izmantojiet tos kampaņām un e-pasta mārketingam lietojumprogrammā SendGrid.</span><span class="sxs-lookup"><span data-stu-id="bba9b-104">Export segments of unified customer profiles to SendGrid contact lists and use them for campaigns and email marketing in SendGrid.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="bba9b-105">Priekšnosacījumi</span><span class="sxs-lookup"><span data-stu-id="bba9b-105">Prerequisites</span></span>

-   <span data-ttu-id="bba9b-106">Jums ir [SendGrid konts](https://sendgrid.com/) un atbilstošie administratora akreditācijas dati.</span><span class="sxs-lookup"><span data-stu-id="bba9b-106">You have a [SendGrid account](https://sendgrid.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="bba9b-107">SendGrid ir esoši kontaktpersonu saraksti un attiecīgie ID.</span><span class="sxs-lookup"><span data-stu-id="bba9b-107">There are existing contact lists in SendGrid and the corresponding IDs.</span></span> <span data-ttu-id="bba9b-108">Papildinformāciju skatiet rakstā [SendGrid - Pārvaldīt kontaktus](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span><span class="sxs-lookup"><span data-stu-id="bba9b-108">For more information, see [SendGrid - Manage contacts](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span></span>
-   <span data-ttu-id="bba9b-109">Jums ir [konfigurēti segmenti](segments.md) auditorijas ieskatos.</span><span class="sxs-lookup"><span data-stu-id="bba9b-109">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="bba9b-110">Eksportētajos segmentos vienotajiem klientu profiliem ir lauks, kas norāda e-pasta adresi.</span><span class="sxs-lookup"><span data-stu-id="bba9b-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-sendgrid"></a><span data-ttu-id="bba9b-111">Izveidot savienojumu ar SendGrid</span><span class="sxs-lookup"><span data-stu-id="bba9b-111">Connect to SendGrid</span></span>

1. <span data-ttu-id="bba9b-112">Dodieties uz sadaļu **Administrators** > **Eksportēšanas galamērķi**.</span><span class="sxs-lookup"><span data-stu-id="bba9b-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="bba9b-113">Sadaļā **SendGrid** atlasiet vienumu **Iestatīt**.</span><span class="sxs-lookup"><span data-stu-id="bba9b-113">Under **SendGrid**, select **Set up**.</span></span>

1. <span data-ttu-id="bba9b-114">Piešķiriet eksportēšanas galamērķim atpazīstamu nosaukumu laukā **Parādāmais nosaukums**.</span><span class="sxs-lookup"><span data-stu-id="bba9b-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/export-sendgrid.PNG" alt-text="SendGrid eksportēšanas konfigurācijas rūts.":::

1. <span data-ttu-id="bba9b-116">Ievadiet savu **SendGrid API atslēgu** [SendGrid API atslēga](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span><span class="sxs-lookup"><span data-stu-id="bba9b-116">Enter your **SendGrid API key** [SendGrid API key](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span></span>

1. <span data-ttu-id="bba9b-117">Ievadiet savu **[SendGrid saraksta ID](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span><span class="sxs-lookup"><span data-stu-id="bba9b-117">Enter your **[SendGrid list ID](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span></span>

1. <span data-ttu-id="bba9b-118">Atlasiet **Piekrītu**, lai apstiprinātu **Datu konfidencialitāti un atbilstību**.</span><span class="sxs-lookup"><span data-stu-id="bba9b-118">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="bba9b-119">Atlasiet **Izveidot savienojumu**, lai inicializētu savienojumu ar SendGrid.</span><span class="sxs-lookup"><span data-stu-id="bba9b-119">Select **Connect** to initialize the connection to SendGrid.</span></span>

1. <span data-ttu-id="bba9b-120">Atlasiet opciju **Pievienot sevi kā eksporta lietotāju** un sniedziet savus Customer Insights akreditācijas datus.</span><span class="sxs-lookup"><span data-stu-id="bba9b-120">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="bba9b-121">Lai konfigurētu eksportēšanu, atlasiet **Tālāk**.</span><span class="sxs-lookup"><span data-stu-id="bba9b-121">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="bba9b-122">Savienotāja konfigurēšana</span><span class="sxs-lookup"><span data-stu-id="bba9b-122">Configure the connector</span></span>

1. <span data-ttu-id="bba9b-123">Sadaļas **Datu atbilstības** laukā **E-pasts** atlasiet lauku, kas iekļauts vienotajā klientu profilā, kas pārstāv klienta e-pasta adresi.</span><span class="sxs-lookup"><span data-stu-id="bba9b-123">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="bba9b-124">Veiciet tās pašas darbības ar citiem neobligātajiem laukiem, piemēram, **Vārds**, **Uzvārds**, **Valsts/Reģions**, **Štats**, **Pilsēta**, and **Pasta indekss**.</span><span class="sxs-lookup"><span data-stu-id="bba9b-124">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Country/Region**, **State**, **City**, and **Post code**.</span></span>

1. <span data-ttu-id="bba9b-125">Atlasiet segmentus, kurus vēlaties eksportēt.</span><span class="sxs-lookup"><span data-stu-id="bba9b-125">Select the segments you want to export.</span></span> <span data-ttu-id="bba9b-126">Mēs **stingri iesakām eksportēt kopumā ne vairāk kā 100 000 klientu profilu** programmā SendGrid.</span><span class="sxs-lookup"><span data-stu-id="bba9b-126">We strongly **recommend to not export more than 100'000 customer profiles in total** to SendGrid.</span></span> 

1. <span data-ttu-id="bba9b-127">Atlasiet vienumu **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="bba9b-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="bba9b-128">Datu eksportēšana</span><span class="sxs-lookup"><span data-stu-id="bba9b-128">Export the data</span></span>

<span data-ttu-id="bba9b-129">Datus var [eksportēt pēc pieprasījuma](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="bba9b-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="bba9b-130">Eksportēšana arī tiks palaista ar katru [plānoto atsvaidzināšanu](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="bba9b-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="bba9b-131">Zināmie ierobežojumi</span><span class="sxs-lookup"><span data-stu-id="bba9b-131">Known limitations</span></span>

- <span data-ttu-id="bba9b-132">Kopumā līdz 100 000 profiliem uz SendGrid.</span><span class="sxs-lookup"><span data-stu-id="bba9b-132">Up to 100'000 profiles in total to SendGrid.</span></span>
- <span data-ttu-id="bba9b-133">Eksportēšana uz SendGrid ir ierobežota līdz segmentiem.</span><span class="sxs-lookup"><span data-stu-id="bba9b-133">Exporting to SendGrid is limited to segments.</span></span>
- <span data-ttu-id="bba9b-134">100 000 profilu eksportēšana uz SendGrid var aizņemt dažas stundas.</span><span class="sxs-lookup"><span data-stu-id="bba9b-134">Exporting up to 100'000 profiles to SendGrid can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="bba9b-135">To profilu skaits, ko var eksportēt uz SendGrid, ir atkarīgs, un tas ir ierobežots jūsu līgumā ar SendGrid.</span><span class="sxs-lookup"><span data-stu-id="bba9b-135">The number of profiles that you can export to SendGrid is dependent and limited on your contract with SendGrid.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="bba9b-136">Datu konfidencialitāte un atbilstība</span><span class="sxs-lookup"><span data-stu-id="bba9b-136">Data privacy and compliance</span></span>

<span data-ttu-id="bba9b-137">Ja iespējojat Dynamics 365 Customer Insights datu pārsūtīšanu uz SendGrid, jūs atļaujat datu pārsūtīšanu ārpus atbilstības robežām Dynamics 365 Customer Insights, ieskaitot iespējami sensitīvus datus, piemēram, personas datus.</span><span class="sxs-lookup"><span data-stu-id="bba9b-137">When you enable Dynamics 365 Customer Insights to transmit data to SendGrid, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="bba9b-138">Microsoft šos datus pārsūtīs pēc jūsu norādēm, bet jūs esat atbildīgs par to, lai nodrošinātu SendGrid atbilstību konfidencialitātes vai drošības saistībām, kas jums varētu rasties.</span><span class="sxs-lookup"><span data-stu-id="bba9b-138">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that SendGrid meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="bba9b-139">Papildinformāciju skatiet rakstā [Microsoft Privātuma paziņojums](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="bba9b-139">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="bba9b-140">Jūsu Dynamics 365 Customer Insights administrators var noņemt šo eksportēšanas galamērķi jebkurā laikā, lai pārtrauktu izmantot šo funkcionalitāti.</span><span class="sxs-lookup"><span data-stu-id="bba9b-140">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]