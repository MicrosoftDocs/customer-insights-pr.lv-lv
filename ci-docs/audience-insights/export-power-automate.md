---
title: Power Automate savienotājs | Microsoft Docs
description: Izveidojiet plūsmas Microsoft Power Automate no Dynamics 365 Customer Insights.
ms.date: 08/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: ffe92414365b0b777691a4a2d585100e4fbea591
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406320"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="5908a-103">Power Automate savienotājs (priekšskatījums)</span><span class="sxs-lookup"><span data-stu-id="5908a-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="5908a-104">Aktivizējiet automatizētu konkrētu notikumu norisi datu izmaiņu gadījumā un pārvaldiet sarežģītākas plūsmas tieši pakalpojumā [Power Automate](https://flow.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="5908a-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="5908a-105">Power Automate trigeri</span><span class="sxs-lookup"><span data-stu-id="5908a-105">Power Automate triggers</span></span>

<span data-ttu-id="5908a-106">Var izmantot dažādus trigerus, kas ļauj izveidot plūsmas, lai automatizētu atkārtojošos uzdevumus, piemēram, paziņojumus vai papildu darbības.</span><span class="sxs-lookup"><span data-stu-id="5908a-106">You can use a variety of triggers that allow you to create flows to automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="5908a-107">Trigeris, kad neizdodas atsvaidzināt datu avotu.</span><span class="sxs-lookup"><span data-stu-id="5908a-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="5908a-108">Trigeris, kad izdodas atsvaidzināt datu avotu.</span><span class="sxs-lookup"><span data-stu-id="5908a-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="5908a-109">Trigeris, kad slieksnis ir šķērsots segmentā.</span><span class="sxs-lookup"><span data-stu-id="5908a-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="5908a-110">Trigeris ir ierobežots, lai šķērsotu virs sliekšņa.</span><span class="sxs-lookup"><span data-stu-id="5908a-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="5908a-111">Trigeris, kad biznesa pasākumā tiek pārsniegts slieksnis.</span><span class="sxs-lookup"><span data-stu-id="5908a-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="5908a-112">Trigeris ir ierobežots, lai šķērsotu virs sliekšņa.</span><span class="sxs-lookup"><span data-stu-id="5908a-112">The trigger is limited crossing above the threshold.</span></span>
- <span data-ttu-id="5908a-113">Trigeris, kad tiek pabeigta pilnīga (datu avotu, segmentu, pasākumu,...) atsvaidzināšana.</span><span class="sxs-lookup"><span data-stu-id="5908a-113">Trigger when a full refresh of (data sources, segments, measures,...) is completed.</span></span>
- <span data-ttu-id="5908a-114">Trigeris, kad ir pabeigta apvienošanas procesa (karte, atbilstība, sapludināšana) atsvaidzināšana.</span><span class="sxs-lookup"><span data-stu-id="5908a-114">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

<span data-ttu-id="5908a-115">[Konfigurējiet trigerus programmā Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span><span class="sxs-lookup"><span data-stu-id="5908a-115">[Configure your triggers in Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span></span>

## <a name="power-automate-actions"></a><span data-ttu-id="5908a-116">Power Automate darbības</span><span class="sxs-lookup"><span data-stu-id="5908a-116">Power Automate actions</span></span>
<span data-ttu-id="5908a-117">Power Automate savienotājs nodrošina citas darbības, izņemot pieejamos trigerus.</span><span class="sxs-lookup"><span data-stu-id="5908a-117">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="5908a-118">Papildinformāciju skatiet [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).</span><span class="sxs-lookup"><span data-stu-id="5908a-118">For more information, see the [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow-in-audience-insights"></a><span data-ttu-id="5908a-119">Power Automate plūsmas izveide no auditorijas ieskatiem</span><span class="sxs-lookup"><span data-stu-id="5908a-119">Create a Power Automate flow in audience insights</span></span>

1. <span data-ttu-id="5908a-120">Sadaļā Auditorijas ieskati skatiet **Administrators** > **Sistēma**.</span><span class="sxs-lookup"><span data-stu-id="5908a-120">In audience insights, go to **Admin** > **System**.</span></span>

1. <span data-ttu-id="5908a-121">Lapā **Sistēma** atlasiet cilni **Statuss**.</span><span class="sxs-lookup"><span data-stu-id="5908a-121">On the **System** page, select the **Status** tab.</span></span>

1. <span data-ttu-id="5908a-122">Sadaļā **Datu avoti** atlasiet **Plūsmas** un nolaižamajā sarakstā atlasiet **Izveidot plūsmu**.</span><span class="sxs-lookup"><span data-stu-id="5908a-122">In the **Data Sources** section, select **Flows** and select **Create a flow** from the dropdown list.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="5908a-123">![Power Automate savienotājs, kas rāda plūsmas darbības izveidošanu](media/power-automate-connector-create-flow.png "Power Automate savienotājs, kas rāda plūsmas izveides darbību")</span><span class="sxs-lookup"><span data-stu-id="5908a-123">![Power Automate connector showing Create a Flow action](media/power-automate-connector-create-flow.png "Power Automate connector showing Create a Flow action")</span></span>

1. <span data-ttu-id="5908a-124">Sadaļā Power Automate atlasiet vienu no pieejamajiem trigeriem, lai izveidotu vēlamo plūsmu.</span><span class="sxs-lookup"><span data-stu-id="5908a-124">In Power Automate, select one of the available triggers to create your preferred flow.</span></span> <span data-ttu-id="5908a-125">Ja veidojat savu pirmo plūsmu, vispirms ir jāautentificējas, izmantojot Power Automate savienotāju.</span><span class="sxs-lookup"><span data-stu-id="5908a-125">If you're creating your first flow, you'll need to authenticate with the Power Automate connector first.</span></span>
