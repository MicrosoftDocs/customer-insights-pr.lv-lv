---
title: Power Automate savienotājs | Microsoft Docs
description: Plūsmu veidošana programmā Microsoft Power Automate no Dynamics 365 Customer Insights.
ms.date: 01/20/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ce2477d957a1792e0436a0dfc15a33621b1c89a9
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976097"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="9f56a-103">Power Automate savienotājs (priekšskatījums)</span><span class="sxs-lookup"><span data-stu-id="9f56a-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="9f56a-104">Aktivizējiet automatizētu konkrētu notikumu norisi datu izmaiņu gadījumā un pārvaldiet sarežģītākas plūsmas tieši pakalpojumā [Power Automate](https://flow.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="9f56a-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="9f56a-105">Power Automate trigeri</span><span class="sxs-lookup"><span data-stu-id="9f56a-105">Power Automate triggers</span></span>

<span data-ttu-id="9f56a-106">Izmantojiet trigerus, kas ļauj izveidot mākoņa plūsma un automatizēt atkārtojošos uzdevumu, piemēram, paziņojumu vai papildu darbību automatizēšana.</span><span class="sxs-lookup"><span data-stu-id="9f56a-106">Use triggers to create cloud flows and automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="9f56a-107">Trigeris, kad neizdodas atsvaidzināt datu avotu.</span><span class="sxs-lookup"><span data-stu-id="9f56a-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="9f56a-108">Trigeris, kad izdodas atsvaidzināt datu avotu.</span><span class="sxs-lookup"><span data-stu-id="9f56a-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="9f56a-109">Trigeris, kad slieksnis ir šķērsots segmentā.</span><span class="sxs-lookup"><span data-stu-id="9f56a-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="9f56a-110">Trigeris ir ierobežots, lai šķērsotu virs sliekšņa.</span><span class="sxs-lookup"><span data-stu-id="9f56a-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="9f56a-111">Trigeris, kad biznesa pasākumā tiek pārsniegts slieksnis.</span><span class="sxs-lookup"><span data-stu-id="9f56a-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="9f56a-112">Tiek atbalstīti tikai uzņēmuma mērījumi bez dimensijas.</span><span class="sxs-lookup"><span data-stu-id="9f56a-112">Only business measures without a dimension are supported.</span></span> <span data-ttu-id="9f56a-113">Trigeris ir ierobežots, lai šķērsotu virs sliekšņa.</span><span class="sxs-lookup"><span data-stu-id="9f56a-113">The trigger is limited crossing above the threshold.</span></span>
- <span data-ttu-id="9f56a-114">Trigeris, kad tiek pabeigta pilnīga (datu avotu, segmentu, pasākumu,...) atsvaidzināšana.</span><span class="sxs-lookup"><span data-stu-id="9f56a-114">Trigger when a full refresh of (data sources, segments, measures,...) is completed.</span></span>
- <span data-ttu-id="9f56a-115">Trigeris, kad ir pabeigta apvienošanas procesa (karte, atbilstība, sapludināšana) atsvaidzināšana.</span><span class="sxs-lookup"><span data-stu-id="9f56a-115">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

<span data-ttu-id="9f56a-116">[Konfigurējiet trigerus programmā Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span><span class="sxs-lookup"><span data-stu-id="9f56a-116">[Configure your triggers in Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span></span>

## <a name="power-automate-actions"></a><span data-ttu-id="9f56a-117">Power Automate darbības</span><span class="sxs-lookup"><span data-stu-id="9f56a-117">Power Automate actions</span></span>
<span data-ttu-id="9f56a-118">Power Automate savienotājs nodrošina citas darbības, izņemot pieejamos trigerus.</span><span class="sxs-lookup"><span data-stu-id="9f56a-118">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="9f56a-119">Papildinformāciju skatiet [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).</span><span class="sxs-lookup"><span data-stu-id="9f56a-119">For more information, see the [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow"></a><span data-ttu-id="9f56a-120">Izveidot Power Automate plūsmu</span><span class="sxs-lookup"><span data-stu-id="9f56a-120">Create a Power Automate flow</span></span>

1. <span data-ttu-id="9f56a-121">Sadaļā Auditorijas ieskati ejiet uz **Administrators** > **Eksportēšanas galamērķi**.</span><span class="sxs-lookup"><span data-stu-id="9f56a-121">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="9f56a-122">Elementā **Power Automate** atlasiet **Iestatīt**.</span><span class="sxs-lookup"><span data-stu-id="9f56a-122">On the **Power Automate** tile, select **Set up**.</span></span>

1. <span data-ttu-id="9f56a-123">Customer Insights savienotājs (priekšskatījums) atveras programmā Power Automate.</span><span class="sxs-lookup"><span data-stu-id="9f56a-123">The Customer Insights Connector (preview) in Power Automate opens.</span></span> <span data-ttu-id="9f56a-124">**Pierakstieties risinājumā** Power Automate.</span><span class="sxs-lookup"><span data-stu-id="9f56a-124">**Sign in** to Power Automate.</span></span>

1. <span data-ttu-id="9f56a-125">Izvēlieties kādu no pieejamajiem trigeriem un pievienojiet jaunajai plūsmai papildu soļus.</span><span class="sxs-lookup"><span data-stu-id="9f56a-125">Choose one of the available triggers and add more steps to your new flow.</span></span> <span data-ttu-id="9f56a-126">Papildinformāciju skatiet [Mākoņa plūsmas izveide programmā Power Automate](/power-automate/get-started-logic-flow).</span><span class="sxs-lookup"><span data-stu-id="9f56a-126">For more information, see [Create a cloud flow in Power Automate](/power-automate/get-started-logic-flow).</span></span>

<span data-ttu-id="9f56a-127">Tālāk ir parādīts, kā izmantot plūsmas:</span><span class="sxs-lookup"><span data-stu-id="9f56a-127">Examples how to use flows:</span></span> 
- <span data-ttu-id="9f56a-128">Publicē ziņojumu Microsoft Teams kanālā, ja neizdodas datu avota atsvaidzināšana.</span><span class="sxs-lookup"><span data-stu-id="9f56a-128">Post a message to a Microsoft Teams channel if a data source refresh fails.</span></span> 
- <span data-ttu-id="9f56a-129">Nosūtiet e-pasta ziņojumu datu īpašniekiem, kad tiek pārsvītrota segmenta sliekšņa vērtība.</span><span class="sxs-lookup"><span data-stu-id="9f56a-129">Send an email to the data owners when a threshold on a segment is crossed.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]
