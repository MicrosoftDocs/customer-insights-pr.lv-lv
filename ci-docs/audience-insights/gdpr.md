---
title: Datu subjektu tiesību (DSR) pieprasījumi saskaņā ar VDAR | Microsoft Docs
description: Atbilde uz datu subjektu prasībām saistībā ar Dynamics 365 Customer Insights auditorijas ieskatiem.
ms.date: 05/14/2020
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: f276a73feca52023391ad92fbc84359921b85328
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406351"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a><span data-ttu-id="001ef-103">Datu subjektu tiesību (DSR) pieprasījumi saskaņā ar VDAR</span><span class="sxs-lookup"><span data-stu-id="001ef-103">Data Subject Rights (DSR) requests under GDPR</span></span>

## <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a><span data-ttu-id="001ef-104">Atbilde uz VDAR datu subjektu dzēšanas prasībām saistībā ar Dynamics 365 Customer Insights auditorijas ieskatiem.</span><span class="sxs-lookup"><span data-stu-id="001ef-104">Responding to GDPR data subject delete requests for Dynamics 365 Customer Insights audience insights capability</span></span>

<span data-ttu-id="001ef-105">“Tiesības dzēst”, veicot personas datu noņemšanu no organizācijas klientu datiem, ir galvenā aizsardzība saskaņā ar Vispārīgo datu aizsardzības regulu (VDAR).</span><span class="sxs-lookup"><span data-stu-id="001ef-105">The “right to erasure” by the removal of personal data from an organization’s customer data is a key protection in the General Data Protection Regulation (GDPR).</span></span> <span data-ttu-id="001ef-106">Personas datu dzēšana ietver visu personas datu un sistēmas radītu ierakstu, izņemot audita ierakstu informācijas, dzēšanu.</span><span class="sxs-lookup"><span data-stu-id="001ef-106">Removing personal data includes removing all personal data and system-generated logs, except audit log information.</span></span>

### <a name="manage-data-subject-delete-requests"></a><span data-ttu-id="001ef-107">Datu subjekta dzēšanas pieprasījumu pārvaldība</span><span class="sxs-lookup"><span data-stu-id="001ef-107">Manage data subject delete requests</span></span>

<span data-ttu-id="001ef-108">Auditorijas ieskati piedāvā tālāk norādītās produkta lietošanas iespējas, lai izdzēstu konkrēta klienta vai lietotāja personas datus:</span><span class="sxs-lookup"><span data-stu-id="001ef-108">Audience insights offers the following in-product experiences to delete personal data for a specific customer or user:</span></span>

- <span data-ttu-id="001ef-109">**Klienta datu dzēšanas pieprasījumu pārvaldīšana**: klientu dati programmā Customer Insights tiek pieņemti no sākotnējiem datu avotiem ārpus programmas Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="001ef-109">**Manage delete requests for customer data**: Customer data in Customer Insights is ingested from original data sources external to Customer Insights.</span></span> <span data-ttu-id="001ef-110">Visi VDAR dzēšanas pieprasījumi ir jāizpilda sākotnējā datu avotā.</span><span class="sxs-lookup"><span data-stu-id="001ef-110">All GDPR delete requests must be performed in the original data source.</span></span>
- <span data-ttu-id="001ef-111">**Pārvaldiet dzēšanas pieprasījumus Customer Insights lietotāju datiem** : Dati lietotājiem tiek izveidoti, izmantojot Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="001ef-111">**Manage delete requests for Customer Insights user data**: Data for users is created by Customer Insights.</span></span> <span data-ttu-id="001ef-112">Visi VDAR dzēšanas pieprasījumi ir jāizpilda programmā Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="001ef-112">All GDPR delete requests must be performed in Customer Insights.</span></span>

#### <a name="manage-delete-requests-for-customer-data"></a><span data-ttu-id="001ef-113">Klienta datu dzēšanas pieprasījumu pārvaldīšana</span><span class="sxs-lookup"><span data-stu-id="001ef-113">Manage delete requests for customer data</span></span>

<span data-ttu-id="001ef-114">Customer Insights administrators var veikt šīs darbības, lai noņemtu datus, kas bija dzēsti klientu datos:</span><span class="sxs-lookup"><span data-stu-id="001ef-114">A Customer Insights admin can follow these steps to remove customer data that was deleted in the data source:</span></span>

1. <span data-ttu-id="001ef-115">Pierakstieties programmā Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="001ef-115">Sign in to Dynamics 365 Customer Insights.</span></span>
2. <span data-ttu-id="001ef-116">Sadaļā Auditorijas ieskati ejiet uz **Dati** > **Datu avoti**.</span><span class="sxs-lookup"><span data-stu-id="001ef-116">In audience insights, go to **Data** > **Data sources**</span></span>
3. <span data-ttu-id="001ef-117">Katram sarakstā iekļautajam datu avotam, kurā ir izdzēsti klienta dati:</span><span class="sxs-lookup"><span data-stu-id="001ef-117">For each data source in the list that contains deleted customer data:</span></span>
   1. <span data-ttu-id="001ef-118">Atlasiet (...) un pēc tam atlasiet **Atsvaidzināt**.</span><span class="sxs-lookup"><span data-stu-id="001ef-118">Select (...) and then select **Refresh**.</span></span>
   2. <span data-ttu-id="001ef-119">Skatiet datu avota statusu sadaļā **Statuss**.</span><span class="sxs-lookup"><span data-stu-id="001ef-119">Check the status of the data source under **Status**.</span></span> <span data-ttu-id="001ef-120">Atzīme nozīmē, ka atsvaidzināšana bija veiksmīga.</span><span class="sxs-lookup"><span data-stu-id="001ef-120">A check mark means the refresh was successful.</span></span> <span data-ttu-id="001ef-121">Brīdinājuma trijstūris nozīmē, ka radās problēma.</span><span class="sxs-lookup"><span data-stu-id="001ef-121">A warning triangle means something went wrong.</span></span> <span data-ttu-id="001ef-122">Ja tiek parādīts brīdinājuma trijstūris, sazinieties ar D365CI@microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="001ef-122">If a warning triangle is displayed, contact D365CI@microsoft.com.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="001ef-123">![Klienta datu VDAR dzēšanas pieprasījumu apstrāde](media/gdpr-data-sources.png "Klienta datu VDAR dzēšanas pieprasījumu apstrāde")</span><span class="sxs-lookup"><span data-stu-id="001ef-123">![Handling GDPR delete requests for customer data](media/gdpr-data-sources.png "Handling GDPR delete requests for customer data")</span></span>

#### <a name="manage-delete-requests-for-user-data"></a><span data-ttu-id="001ef-124">Lietotāju datu dzēšanas pieprasījumu pārvaldīšana</span><span class="sxs-lookup"><span data-stu-id="001ef-124">Manage delete requests for user data</span></span>

<span data-ttu-id="001ef-125">Customer Insights administrators var veikt tālāk norādītās darbības, lai dzēstu Customer Insights lietotāja datus:</span><span class="sxs-lookup"><span data-stu-id="001ef-125">A Customer Insights admin can follow these steps to delete Customer Insights user data:</span></span>

1. <span data-ttu-id="001ef-126">Pierakstieties programmā Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="001ef-126">Sign in to Dynamics 365 Customer Insights.</span></span>
2. <span data-ttu-id="001ef-127">Sadaļā Auditorijas ieskati ejiet uz **Administrators** > **Atļaujas**.</span><span class="sxs-lookup"><span data-stu-id="001ef-127">In audience insights, go to **Admin** > **Permissions**.</span></span>
3. <span data-ttu-id="001ef-128">Atzīmējiet tā lietotāja izvēles rūtiņu, kuru vēlaties dzēst.</span><span class="sxs-lookup"><span data-stu-id="001ef-128">Select the check box for the user you want to delete.</span></span>
4. <span data-ttu-id="001ef-129">Atlasiet **Noņemt**.</span><span class="sxs-lookup"><span data-stu-id="001ef-129">Select **Remove**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="001ef-130">![Lietotāju VDAR datu dzēšanas pieprasījumu pārvaldīšana](media/gdpr-permissions.png "Lietotāju VDAR datu dzēšanas pieprasījumu pārvaldīšana")</span><span class="sxs-lookup"><span data-stu-id="001ef-130">![Handling GDPR delete requests foruser data](media/gdpr-permissions.png "Handling GDPR delete requests for user data")</span></span>

## <a name="responding-to-gdpr-data-subject-export-requests"></a><span data-ttu-id="001ef-131">Reaģēšana uz VDAR datu subjekta eksportēšanas pieprasījumiem</span><span class="sxs-lookup"><span data-stu-id="001ef-131">Responding to GDPR data subject export requests</span></span>

<span data-ttu-id="001ef-132">Tā kā vēlamies atvieglot jūsu pieredzi ar Vispārīgo datu aizsardzības regulu (VDAR), esam izstrādājuši dokumentāciju, kas palīdzēs sagatavoties.</span><span class="sxs-lookup"><span data-stu-id="001ef-132">As part of our commitment to partner with you on your journey to the General Data Protection Regulation (GDPR), we’ve developed documentation to help you prepare.</span></span> <span data-ttu-id="001ef-133">Šajā dokumentācijā ir aprakstītas darbības, kuras varat veikt mūsdienās, lai atbalstītu VDAR atbilstību, izmantojot auditorijas ieskatus.</span><span class="sxs-lookup"><span data-stu-id="001ef-133">This documentation describes steps you can take today to support GDPR compliance when using audience insights.</span></span>

### <a name="manage-export-and-view-requests"></a><span data-ttu-id="001ef-134">Eksportēšanas pārvaldīšana un pieprasījumu skatīšana</span><span class="sxs-lookup"><span data-stu-id="001ef-134">Manage export and view requests</span></span>

<span data-ttu-id="001ef-135">Datu pārvietojamības tiesības ļauj datu subjektiem pieprasīt savu personas datu kopiju elektroniskā formātā ("strukturēts, plaši lietots, mašīnlasāms un savstarpēji izmantojams formāts), kurus var pārsūtīt citam datu pārzinim.</span><span class="sxs-lookup"><span data-stu-id="001ef-135">The right of data portability allows data subjects to request a copy of their personal data in an electronic format (a “structured, commonly used, machine readable, and interoperable format”) that can be transmitted to another data controller.</span></span>

#### <a name="export-customer-data-tenant-admin"></a><span data-ttu-id="001ef-136">Klienta datu eksportētājs (nomnieka administrators)</span><span class="sxs-lookup"><span data-stu-id="001ef-136">Export customer data (tenant admin)</span></span>

<span data-ttu-id="001ef-137">Lai eksportētu datus, nomnieka administrators var veikt tālāk norādītas darbības:.</span><span class="sxs-lookup"><span data-stu-id="001ef-137">A tenant administrator can follow these steps to export data:</span></span>

1. <span data-ttu-id="001ef-138">Nosūtiet e-pasta ziņojumu uz e-pasta adresi D365CI@microsoft.com, norādot klienta e-pasta adresi pieprasījumā.</span><span class="sxs-lookup"><span data-stu-id="001ef-138">Send an email to D365CI@microsoft.com specifying the customer’s email address in the request.</span></span> <span data-ttu-id="001ef-139">Customer Insights komanda nosūtīs e-pasta ziņojumu uz reģistrēto nomnieka administratora e-pasta adresi, lūdzot apstiprinājumu datu eksportēšanai.</span><span class="sxs-lookup"><span data-stu-id="001ef-139">The Customer Insights team will send an email to the registered tenant admin email address, asking for confirmation to export data.</span></span>
2. <span data-ttu-id="001ef-140">Atzīstiet apstiprinājumu eksportēt pieprasītā klienta datus.</span><span class="sxs-lookup"><span data-stu-id="001ef-140">Acknowledge the confirmation to export the data for the requested customer.</span></span>
3. <span data-ttu-id="001ef-141">Saņemiet eksportētos datus, izmantojot nomnieka administratora e-pasta adresi.</span><span class="sxs-lookup"><span data-stu-id="001ef-141">Receive the exported data through the tenant admin email address.</span></span>

#### <a name="export-user-data-tenant-admin"></a><span data-ttu-id="001ef-142">Klienta datu eksportēšana (nomnieka administrators)</span><span class="sxs-lookup"><span data-stu-id="001ef-142">Export user data (tenant admin)</span></span>

1. <span data-ttu-id="001ef-143">Nosūtiet e-pasta ziņojumu uz e-pasta adresi D365CI@microsoft.com, norādot lietotāja e-pasta adresi pieprasījumā.</span><span class="sxs-lookup"><span data-stu-id="001ef-143">Send an email to D365CI@microsoft.com specifying the user’s email address in the request.</span></span> <span data-ttu-id="001ef-144">Customer Insights komanda nosūtīs e-pasta ziņojumu uz reģistrēto nomnieka administratora e-pasta adresi, lūdzot apstiprinājumu datu eksportēšanai.</span><span class="sxs-lookup"><span data-stu-id="001ef-144">The Customer Insights team will send an email to the registered tenant admin email address, asking for confirmation to export data.</span></span>
2. <span data-ttu-id="001ef-145">Atzīstiet apstiprinājumu eksportēt pieprasītā lietotāja datus.</span><span class="sxs-lookup"><span data-stu-id="001ef-145">Acknowledge the confirmation to export the data for the requested user.</span></span>
3. <span data-ttu-id="001ef-146">Saņemiet eksportētos datus, izmantojot nomnieka administratora e-pasta adresi.</span><span class="sxs-lookup"><span data-stu-id="001ef-146">Receive the exported data through the tenant admin email address.</span></span>
