---
title: Customer Insights datu eksportēšana uz SFTP resursdatoriem
description: Uzziniet, kā konfigurēt savienojumu ar SFTP resursdatoru.
ms.date: 01/27/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 9ec14fafa8f99e34b95349371298082e166535d0
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598394"
---
# <a name="connector-for-sftp-preview"></a><span data-ttu-id="2b395-103">SFTP savienotājs (priekšskatījums)</span><span class="sxs-lookup"><span data-stu-id="2b395-103">Connector for SFTP (preview)</span></span>

<span data-ttu-id="2b395-104">Izmantojiet klienta datus trešo pušu lietojumprogrammās, eksportējot tos caur mūsu Drošo failu pārsūtīšanas protokola (SFTP) resursdatoru.</span><span class="sxs-lookup"><span data-stu-id="2b395-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol (SFTP) host.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="2b395-105">Priekšnosacījumi</span><span class="sxs-lookup"><span data-stu-id="2b395-105">Prerequisites</span></span>

- <span data-ttu-id="2b395-106">SFTP resursdatora pieejamība un atbilstošie akreditācijas dati.</span><span class="sxs-lookup"><span data-stu-id="2b395-106">Availability of an SFTP host and corresponding credentials.</span></span>

## <a name="connect-to-sftp"></a><span data-ttu-id="2b395-107">Savienojuma izveide ar SFTP</span><span class="sxs-lookup"><span data-stu-id="2b395-107">Connect to SFTP</span></span>

1. <span data-ttu-id="2b395-108">Dodieties uz sadaļu **Administrators** > **Eksportēšanas galamērķi**.</span><span class="sxs-lookup"><span data-stu-id="2b395-108">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="2b395-109">Sadaļā **SFTP** atlasiet **Iestatīt**.</span><span class="sxs-lookup"><span data-stu-id="2b395-109">Under **SFTP**, select **Set up**.</span></span>

1. <span data-ttu-id="2b395-110">Laukā **Parādāmais nosaukums** piešķiriet galamērķim atpazīstamu nosaukumu.</span><span class="sxs-lookup"><span data-stu-id="2b395-110">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="2b395-111">Norādiet **Lietotājvārdu**, **Paroli**, **Resursdatora nosaukumu** un **Eksporta mapi** savam SFTP kontam.</span><span class="sxs-lookup"><span data-stu-id="2b395-111">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="2b395-112">Atlasiet **Pārbaudīt**, lai testētu savienojumu.</span><span class="sxs-lookup"><span data-stu-id="2b395-112">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="2b395-113">Pēc sekmīgas pārbaudes izvēlieties, vai vēlaties eksportēt datus **Saspiestus** vai **Atspiestus**, un atlasiet eksportēto failu **Lauku norobežotāju**.</span><span class="sxs-lookup"><span data-stu-id="2b395-113">After successful verification, choose if you want to export your data **Gzipped** or **Unzipped**, and select the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="2b395-114">Atlasiet **Piekrītu**, lai apstiprinātu **Datu konfidencialitāti un atbilstību**.</span><span class="sxs-lookup"><span data-stu-id="2b395-114">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="2b395-115">Lai sāktu eksporta konfigurēšanu, atlasiet **Tālāk**.</span><span class="sxs-lookup"><span data-stu-id="2b395-115">Select **Next** to start configuring the export.</span></span>

## <a name="configure-the-export"></a><span data-ttu-id="2b395-116">Eksporta konfigurēšana</span><span class="sxs-lookup"><span data-stu-id="2b395-116">Configure the export</span></span>

1. <span data-ttu-id="2b395-117">Atlasiet entītijas, piemēram, segmentus, kurus vēlaties eksportēt.</span><span class="sxs-lookup"><span data-stu-id="2b395-117">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="2b395-118">Katra atlasītajā entītija pēc eksportēšanas būs līdz pieciem izvades failiem.</span><span class="sxs-lookup"><span data-stu-id="2b395-118">Each selected entity will be up to five output files when exported.</span></span> 

1. <span data-ttu-id="2b395-119">Atlasiet vienumu **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="2b395-119">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="2b395-120">Datu eksportēšana</span><span class="sxs-lookup"><span data-stu-id="2b395-120">Export the data</span></span>

<span data-ttu-id="2b395-121">Datus var [eksportēt pēc pieprasījuma](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="2b395-121">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="2b395-122">Eksportēšana arī tiks palaista ar katru [plānoto atsvaidzināšanu](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="2b395-122">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="2b395-123">Zināmie ierobežojumi</span><span class="sxs-lookup"><span data-stu-id="2b395-123">Known limitations</span></span>

- <span data-ttu-id="2b395-124">Eksportēšanas izpildlaiks ir atkarīgs no sistēmas veiktspējas.</span><span class="sxs-lookup"><span data-stu-id="2b395-124">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="2b395-125">Kā minimālu servera konfigurēšanu ieteicams izmantot divus procesora kodolus un 1 Gb atmiņu.</span><span class="sxs-lookup"><span data-stu-id="2b395-125">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="2b395-126">Līdz pat 100 miljoniem klientu profilu entītiju eksportēšana var aizņemt 90 minūtes, ja tiek izmantota ieteicama minimālā divu procesoru kodolu konfigurācija un 1 Gb atmiņa.</span><span class="sxs-lookup"><span data-stu-id="2b395-126">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration of two CPU cores and 1 Gb of memory.</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="2b395-127">Datu konfidencialitāte un atbilstība</span><span class="sxs-lookup"><span data-stu-id="2b395-127">Data privacy and compliance</span></span>

<span data-ttu-id="2b395-128">Ja iespējojat Dynamics 365 Customer Insights datu pārsūtīšanu caur SFTP, jūs atļaujat datu pārsūtīšanu ārpus atbilstības robežām Dynamics 365 Customer Insights, ieskaitot iespējami sensitīvus datus, piemēram, personas datus.</span><span class="sxs-lookup"><span data-stu-id="2b395-128">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="2b395-129">Microsoft šos datus pārsūtīs pēc jūsu norādēm, bet jūs esat atbildīgs par to, lai nodrošinātu eksporta galamērķa atbilstību konfidencialitātes vai drošības saistībām, kas jums varētu rasties.</span><span class="sxs-lookup"><span data-stu-id="2b395-129">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="2b395-130">Papildinformāciju skatiet rakstā [Microsoft Privātuma paziņojums](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="2b395-130">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="2b395-131">Jūsu Dynamics 365 Customer Insights administrators var noņemt šo eksportēšanas galamērķi jebkurā laikā, lai pārtrauktu izmantot šo funkcionalitāti.</span><span class="sxs-lookup"><span data-stu-id="2b395-131">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]