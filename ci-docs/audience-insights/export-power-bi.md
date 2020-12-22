---
title: Power BI savienotājs
description: Uzziniet, kā izmantot Dynamics 365 Customer Insights savienotāju pakalpojumā Power BI.
ms.date: 09/21/2020
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d497ca779a337c512a7254524f597cff226bcb45
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406325"
---
# <a name="connector-for-power-bi-preview"></a><span data-ttu-id="2b958-103">Power BI savienotājs (priekšskatījums)</span><span class="sxs-lookup"><span data-stu-id="2b958-103">Connector for Power BI (preview)</span></span>

<span data-ttu-id="2b958-104">Izveidojiet vizualizācijas saviem datiem, izmantojot līdzekli Power BI Desktop.</span><span class="sxs-lookup"><span data-stu-id="2b958-104">Create visualizations for your data with the Power BI Desktop.</span></span> <span data-ttu-id="2b958-105">Veidojiet papildu ieskatus un atskaites, izmantojot vienotos klientu datus.</span><span class="sxs-lookup"><span data-stu-id="2b958-105">Generate additional insights and build reports with your unified customer data.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="2b958-106">Priekšnosacījumi</span><span class="sxs-lookup"><span data-stu-id="2b958-106">Prerequisites</span></span>

- <span data-ttu-id="2b958-107">Jums ir vienotie klientu profili.</span><span class="sxs-lookup"><span data-stu-id="2b958-107">You have unified customer profiles.</span></span>
- <span data-ttu-id="2b958-108">Jūsu datorā ir instalēta jaunākā [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) versija.</span><span class="sxs-lookup"><span data-stu-id="2b958-108">The latest version of [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) is installed on your computer.</span></span> <span data-ttu-id="2b958-109">[Papildinformācija par Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).</span><span class="sxs-lookup"><span data-stu-id="2b958-109">[Learn more about Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).</span></span>

## <a name="configure-the-connector-for-power-bi"></a><span data-ttu-id="2b958-110">Power BI savienotāja konfigurēšana</span><span class="sxs-lookup"><span data-stu-id="2b958-110">Configure the connector for Power BI</span></span>

1. <span data-ttu-id="2b958-111">Risinājumā Power BI Desktop atlasiet **Fails** > **Iegūt datus**.</span><span class="sxs-lookup"><span data-stu-id="2b958-111">In Power BI Desktop, select **File** > **Get Data**.</span></span>

1. <span data-ttu-id="2b958-112">Atlasiet **Skatīt vairāk** un meklējiet **Dynamics 365 Customer Insights**.</span><span class="sxs-lookup"><span data-stu-id="2b958-112">Select **See more** and search for **Dynamics 365 Customer Insights**</span></span>

1. <span data-ttu-id="2b958-113">Atlasiet rezultātu un atlasiet **Savienot**.</span><span class="sxs-lookup"><span data-stu-id="2b958-113">Select the result and select **Connect**.</span></span>

1. <span data-ttu-id="2b958-114">**Pierakstieties**, izmantojot to pašu organizācijas kontu, ko izmantojat Customer Insights, un atlasiet **Savienot**.</span><span class="sxs-lookup"><span data-stu-id="2b958-114">**Sign in** with the same organizational account you use for Customer Insights and select **Connect**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="2b958-115">Šajā darbībā norādītais konts tiek izmantots, lai iegūtu datus no Customer Insights, un tiem nav jābūt tādiem pašiem, ar kuriem pierakstījāties Power BI.</span><span class="sxs-lookup"><span data-stu-id="2b958-115">The account you indicate in this step is used to fetch data from Customer Insights and doesn't need to be the same you are signed in to Power BI.</span></span> <span data-ttu-id="2b958-116">Lai atiestatītu datus, kas tiek lietoti datu paņemšanai, atveriet Power BI un atveriet **Fails** > **Opcijas** > **Iestatījumi** > **Datu avotu iestatījumi**.</span><span class="sxs-lookup"><span data-stu-id="2b958-116">To reset the account that is used for data fetching, open Power BI and go to **File** > **Options** > **Settings** > **Data source settings**.</span></span> <span data-ttu-id="2b958-117">Datu avotu sarakstā atlasiet **Dynamics 365 Customer Insights pieteikšanās** un atlasiet **Noņemt atļaujas**.</span><span class="sxs-lookup"><span data-stu-id="2b958-117">In the list of data sources, select **Dynamics 365 Customer Insights Login** and select **Clear permissions**.</span></span>  

1. <span data-ttu-id="2b958-118">Dialoglodziņā **Navigators**.</span><span class="sxs-lookup"><span data-stu-id="2b958-118">In the **Navigator** dialog box.</span></span> <span data-ttu-id="2b958-119">Jūs redzēsiet sarakstu ar visām vidēm, kurām Jums ir piekļuve.</span><span class="sxs-lookup"><span data-stu-id="2b958-119">you see the list of all environments you have access to.</span></span> <span data-ttu-id="2b958-120">Izvērsiet vidi un atveriet jebkuru no mapēm (entītijas, mērvienības, segmenti, bagātinājumi).</span><span class="sxs-lookup"><span data-stu-id="2b958-120">Expand an environment and open any of the folders (entities, measures, segments, enrichments).</span></span> <span data-ttu-id="2b958-121">Piemēram, atveriet mapi **Entītijas**, lai skatītu visas entītijas, ko varat importēt.</span><span class="sxs-lookup"><span data-stu-id="2b958-121">For example, open the **Entities** folder, to see all entities you can import.</span></span>

   <span data-ttu-id="2b958-122">![Power BI savienotāja navigators](media/power-bi-navigator.png "Power BI savienotāja navigators")</span><span class="sxs-lookup"><span data-stu-id="2b958-122">![Power BI Connector Navigator](media/power-bi-navigator.png "Power BI Connector Navigator")</span></span>

1. <span data-ttu-id="2b958-123">Atzīmējiet izvēles rūtiņas, kas atrodas blakus iekļaujamajām entītijām, un atlasiet **Ielādēt**.</span><span class="sxs-lookup"><span data-stu-id="2b958-123">Select the check boxes next to the entities to include and **Load**.</span></span> <span data-ttu-id="2b958-124">Varat atlasīt vairākas entītijas no vairākām vidēm.</span><span class="sxs-lookup"><span data-stu-id="2b958-124">You can select multiple entities from multiple environments.</span></span>

1. <span data-ttu-id="2b958-125">Kamēr notiks entītiju ielāde, tiks rādīts ielādēšanas dialoglodziņš.</span><span class="sxs-lookup"><span data-stu-id="2b958-125">You'll see a loading dialog box while your entities are loaded.</span></span> <span data-ttu-id="2b958-126">Kad ir ielādētas visas atlasītās entītijas, varat izmantot Power BI iespējas, lai vizualizētu datus.</span><span class="sxs-lookup"><span data-stu-id="2b958-126">Once all of your selected entities have loaded, you can use the capabilities of Power BI to visualize the data.</span></span>

## <a name="large-data-sets"></a><span data-ttu-id="2b958-127">Lielas datu kopas</span><span class="sxs-lookup"><span data-stu-id="2b958-127">Large data sets</span></span>

<span data-ttu-id="2b958-128">Customer Insights savienotājs Power BI ir paredzēts darbam ar datu kopām, kurās ir līdz 1 000 000 klientu profilu.</span><span class="sxs-lookup"><span data-stu-id="2b958-128">The Customer Insights connector for Power BI is designed to work for data sets that contain up to 1 million customer profiles.</span></span> <span data-ttu-id="2b958-129">Lielāku datu kopu importēšana var strādāt, bet tai ir nepieciešams ilgs laiks.</span><span class="sxs-lookup"><span data-stu-id="2b958-129">Importing larger data sets may work, but it takes a long time.</span></span> <span data-ttu-id="2b958-130">Turklāt process var tikt pārtraukts, jo Power BI pastāv ierobežojumi.</span><span class="sxs-lookup"><span data-stu-id="2b958-130">Additionally, the process could run into a time-out because of Power BI limitations.</span></span> <span data-ttu-id="2b958-131">Papildinformāciju skatiet [Power BI: ieteikumi lielām datu kopām](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets).</span><span class="sxs-lookup"><span data-stu-id="2b958-131">For more information, see [Power BI: Recommendations for large data sets](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets).</span></span> 

### <a name="work-with-a-subset-of-data"></a><span data-ttu-id="2b958-132">Darbs ar datu apakškopu</span><span class="sxs-lookup"><span data-stu-id="2b958-132">Work with a subset of data</span></span>

<span data-ttu-id="2b958-133">Apsveriet iespēju strādāt ar datu apakškopu.</span><span class="sxs-lookup"><span data-stu-id="2b958-133">Consider working with a subset of your data.</span></span> <span data-ttu-id="2b958-134">Piemēram, varat izveidot [segmentus](segments.md), nevis visu klientu ierakstu eksportēšanu uz Power BI.</span><span class="sxs-lookup"><span data-stu-id="2b958-134">For example, you can create [segments](segments.md) instead of exporting all customer records to Power BI.</span></span>
