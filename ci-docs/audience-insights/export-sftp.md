---
title: Customer Insights datu eksportēšana uz SFTP resursdatoriem
description: Uzziniet, kā konfigurēt savienojumu ar SFTP resursdatoru.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c2529744d7a26a06324b79cad6a8001d75903545
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643512"
---
# <a name="connector-for-sftp-preview"></a><span data-ttu-id="7d485-103">SFTP savienotājs (priekšskatījums)</span><span class="sxs-lookup"><span data-stu-id="7d485-103">Connector for SFTP (preview)</span></span>

<span data-ttu-id="7d485-104">Izmantojiet klienta datus trešo pušu lietojumprogrammās, eksportējot tos caur mūsu Drošo failu pārsūtīšanas protokola (SFTP) resursdatoru.</span><span class="sxs-lookup"><span data-stu-id="7d485-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol(SFTP) host.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="7d485-105">Priekšnosacījumi</span><span class="sxs-lookup"><span data-stu-id="7d485-105">Prerequisites</span></span>

- <span data-ttu-id="7d485-106">SFTP resursdatora pieejamība un atbilstošie akreditācijas dati.</span><span class="sxs-lookup"><span data-stu-id="7d485-106">Availability of a SFTP host and corresponding credentials.</span></span>

## <a name="connect-to-sftp"></a><span data-ttu-id="7d485-107">Izveidot savienojumu ar SFTP</span><span class="sxs-lookup"><span data-stu-id="7d485-107">Connect to SFTP</span></span>

1. <span data-ttu-id="7d485-108">Dodieties uz sadaļu **Administrators** > **Eksportēšanas galamērķi**.</span><span class="sxs-lookup"><span data-stu-id="7d485-108">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="7d485-109">Sadaļā **SFTP** atlasiet **Iestatīt**.</span><span class="sxs-lookup"><span data-stu-id="7d485-109">Under **SFTP**, select **Set up**.</span></span>

1. <span data-ttu-id="7d485-110">Laukā **Parādāmais nosaukums** piešķiriet galamērķim atpazīstamu nosaukumu.</span><span class="sxs-lookup"><span data-stu-id="7d485-110">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="7d485-111">Norādiet **Lietotājvārdu**, **Paroli** un **Resurdatora nosaukumu** savam SFTP kontam.</span><span class="sxs-lookup"><span data-stu-id="7d485-111">Provide a **Username**, **Password** and **Hostname** for your SFTP account.</span></span> <span data-ttu-id="7d485-112">Piemērs: ja jūsu SFTP servera saknes mape ir/root/folder, un jūs vēlaties, lai dati tiktu eksportēti uz/root/Folder/ci_export_destination_folder, tad viesotājam vajadzētu būt SFTP://< server_address >/ci_export_destination_folder ".</span><span class="sxs-lookup"><span data-stu-id="7d485-112">Example: If your SFTP server's root folder is /root/folder, and you would like the data to be exported to /root/folder/ci_export_destination_folder, the the host should be sftp://<server_address>/ci_export_destination_folder".</span></span>

1. <span data-ttu-id="7d485-113">Atlasiet **Pārbaudīt**, lai testētu savienojumu.</span><span class="sxs-lookup"><span data-stu-id="7d485-113">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="7d485-114">Pēc sekmīgas pārbaudes izvēlieties, vai vēlaties eksportēt datus **Saspiestus** vai **Atspiestus**, un atlasiet eksportēto failu **Lauku norobežotāju**.</span><span class="sxs-lookup"><span data-stu-id="7d485-114">After successful verification, choose if you want to export your data **Zipped** or **Unzipped**, and select the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="7d485-115">Atlasiet **Piekrītu**, lai apstiprinātu **Datu konfidencialitāti un atbilstību**.</span><span class="sxs-lookup"><span data-stu-id="7d485-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="7d485-116">Lai sāktu eksporta konfigurēšanu, atlasiet **Tālāk**.</span><span class="sxs-lookup"><span data-stu-id="7d485-116">Select **Next** to start configuring the export.</span></span>

## <a name="configure-the-connection"></a><span data-ttu-id="7d485-117">Savienojuma konfigurēšana</span><span class="sxs-lookup"><span data-stu-id="7d485-117">Configure the connection</span></span>

1. <span data-ttu-id="7d485-118">Atlasiet tos **klienta atribūtus**, kurus vēlaties eksportēt.</span><span class="sxs-lookup"><span data-stu-id="7d485-118">Select the **customer attributes** you want to export.</span></span> <span data-ttu-id="7d485-119">Varat eksportēt vienu vai vairākus atribūtus.</span><span class="sxs-lookup"><span data-stu-id="7d485-119">You can export one or multiple attributes.</span></span>

1. <span data-ttu-id="7d485-120">Atlasiet **Tālāk**.</span><span class="sxs-lookup"><span data-stu-id="7d485-120">Select **Next**.</span></span>

1. <span data-ttu-id="7d485-121">Atlasiet segmentus, kurus vēlaties eksportēt.</span><span class="sxs-lookup"><span data-stu-id="7d485-121">Select the segments you want to export.</span></span>

1. <span data-ttu-id="7d485-122">Atlasiet vienumu **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="7d485-122">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="7d485-123">Datu eksportēšana</span><span class="sxs-lookup"><span data-stu-id="7d485-123">Export the data</span></span>

<span data-ttu-id="7d485-124">Datus var [eksportēt pēc pieprasījuma](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="7d485-124">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="7d485-125">Eksportēšana arī tiks palaista ar katru [plānoto atsvaidzināšanu](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="7d485-125">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="7d485-126">Datu konfidencialitāte un atbilstība</span><span class="sxs-lookup"><span data-stu-id="7d485-126">Data privacy and compliance</span></span>

<span data-ttu-id="7d485-127">Ja iespējojat Dynamics 365 Customer Insights datu pārsūtīšanu caur SFTP, jūs atļaujat datu pārsūtīšanu ārpus atbilstības robežām Dynamics 365 Customer Insights, ieskaitot iespējami sensitīvus datus, piemēram, personas datus.</span><span class="sxs-lookup"><span data-stu-id="7d485-127">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="7d485-128">Microsoft šos datus pārsūtīs pēc jūsu norādēm, bet jūs esat atbildīgs par to, lai nodrošinātu eksporta galamērķa atbilstību konfidencialitātes vai drošības saistībām, kas jums varētu rasties.</span><span class="sxs-lookup"><span data-stu-id="7d485-128">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="7d485-129">Papildinformāciju skatiet rakstā [Microsoft Privātuma paziņojums](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="7d485-129">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="7d485-130">Jūsu Dynamics 365 Customer Insights administrators var noņemt šo eksportēšanas galamērķi jebkurā laikā, lai pārtrauktu izmantot šo funkcionalitāti.</span><span class="sxs-lookup"><span data-stu-id="7d485-130">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
