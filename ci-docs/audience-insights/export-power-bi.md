---
title: Power BI savienotājs
description: Uzziniet, kā izmantot Dynamics 365 Customer Insights savienotāju pakalpojumā Power BI.
ms.date: 09/21/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: e43e2f9dbc84ebfbf2154990a752740f973296cb
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596048"
---
# <a name="connector-for-power-bi-preview"></a><span data-ttu-id="af61b-103">Power BI savienotājs (priekšskatījums)</span><span class="sxs-lookup"><span data-stu-id="af61b-103">Connector for Power BI (preview)</span></span>

<span data-ttu-id="af61b-104">Izveidojiet vizualizācijas saviem datiem, izmantojot līdzekli Power BI Desktop.</span><span class="sxs-lookup"><span data-stu-id="af61b-104">Create visualizations for your data with the Power BI Desktop.</span></span> <span data-ttu-id="af61b-105">Veidojiet papildu ieskatus un atskaites, izmantojot vienotos klientu datus.</span><span class="sxs-lookup"><span data-stu-id="af61b-105">Generate additional insights and build reports with your unified customer data.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="af61b-106">Priekšnosacījumi</span><span class="sxs-lookup"><span data-stu-id="af61b-106">Prerequisites</span></span>

- <span data-ttu-id="af61b-107">Jums ir vienotie klientu profili.</span><span class="sxs-lookup"><span data-stu-id="af61b-107">You have unified customer profiles.</span></span>
- <span data-ttu-id="af61b-108">Jaunākā [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) versija ir instalēta jūsu datorā.</span><span class="sxs-lookup"><span data-stu-id="af61b-108">The latest version of [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) is installed on your computer.</span></span> <span data-ttu-id="af61b-109">[Papildinformācija par Power BI Desktop](/power-bi/desktop-what-is-desktop).</span><span class="sxs-lookup"><span data-stu-id="af61b-109">[Learn more about Power BI Desktop](/power-bi/desktop-what-is-desktop).</span></span>

## <a name="configure-the-connector-for-power-bi"></a><span data-ttu-id="af61b-110">Power BI savienotāja konfigurēšana</span><span class="sxs-lookup"><span data-stu-id="af61b-110">Configure the connector for Power BI</span></span>

1. <span data-ttu-id="af61b-111">Risinājumā Power BI Desktop atlasiet **Fails** > **Iegūt datus**.</span><span class="sxs-lookup"><span data-stu-id="af61b-111">In Power BI Desktop, select **File** > **Get Data**.</span></span>

1. <span data-ttu-id="af61b-112">Atlasiet **Skatīt vairāk** un meklējiet **Dynamics 365 Customer Insights**.</span><span class="sxs-lookup"><span data-stu-id="af61b-112">Select **See more** and search for **Dynamics 365 Customer Insights**</span></span>

1. <span data-ttu-id="af61b-113">Atlasiet **Izveidot savienojumu**.</span><span class="sxs-lookup"><span data-stu-id="af61b-113">Select **Connect**.</span></span>

1. <span data-ttu-id="af61b-114">**Pierakstieties**, izmantojot to pašu organizācijas kontu, ko izmantojat Customer Insights, un atlasiet **Savienot**.</span><span class="sxs-lookup"><span data-stu-id="af61b-114">**Sign in** with the same organizational account you use for Customer Insights and select **Connect**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="af61b-115">Šajā darbībā norādītais konts tiek izmantots, lai iegūtu datus no Customer Insights, un tiem nav jābūt tādiem pašiem, ar kuriem pierakstījāties Power BI.</span><span class="sxs-lookup"><span data-stu-id="af61b-115">The account you indicate in this step is used to fetch data from Customer Insights and doesn't need to be the same you are signed in to Power BI.</span></span> <span data-ttu-id="af61b-116">Lai atiestatītu datus, kas tiek lietoti datu paņemšanai, atveriet Power BI un atveriet **Fails** > **Opcijas** > **Iestatījumi** > **Datu avotu iestatījumi**.</span><span class="sxs-lookup"><span data-stu-id="af61b-116">To reset the account that is used for data fetching, open Power BI and go to **File** > **Options** > **Settings** > **Data source settings**.</span></span> <span data-ttu-id="af61b-117">Datu avotu sarakstā atlasiet **Dynamics 365 Customer Insights pieteikšanās** un atlasiet **Noņemt atļaujas**.</span><span class="sxs-lookup"><span data-stu-id="af61b-117">In the list of data sources, select **Dynamics 365 Customer Insights Login** and select **Clear permissions**.</span></span>  

1. <span data-ttu-id="af61b-118">Dialoglodziņā **Navigators**.</span><span class="sxs-lookup"><span data-stu-id="af61b-118">In the **Navigator** dialog box.</span></span> <span data-ttu-id="af61b-119">Jūs redzēsiet sarakstu ar visām vidēm, kurām Jums ir piekļuve.</span><span class="sxs-lookup"><span data-stu-id="af61b-119">you see the list of all environments you have access to.</span></span> <span data-ttu-id="af61b-120">Izvērsiet vidi un atveriet jebkuru no mapēm (entītijas, mērvienības, segmenti, bagātinājumi).</span><span class="sxs-lookup"><span data-stu-id="af61b-120">Expand an environment and open any of the folders (entities, measures, segments, enrichments).</span></span> <span data-ttu-id="af61b-121">Piemēram, atveriet mapi **Entītijas**, lai skatītu visas entītijas, ko varat importēt.</span><span class="sxs-lookup"><span data-stu-id="af61b-121">For example, open the **Entities** folder, to see all entities you can import.</span></span>

   <span data-ttu-id="af61b-122">![Power BI savienotāja navigators](media/power-bi-navigator.png "Power BI savienotāja navigators")</span><span class="sxs-lookup"><span data-stu-id="af61b-122">![Power BI Connector Navigator](media/power-bi-navigator.png "Power BI Connector Navigator")</span></span>

1. <span data-ttu-id="af61b-123">Atzīmējiet izvēles rūtiņas, kas atrodas blakus iekļaujamajām entītijām, un atlasiet **Ielādēt**.</span><span class="sxs-lookup"><span data-stu-id="af61b-123">Select the check boxes next to the entities to include and **Load**.</span></span> <span data-ttu-id="af61b-124">Varat atlasīt vairākas entītijas no vairākām vidēm.</span><span class="sxs-lookup"><span data-stu-id="af61b-124">You can select multiple entities from multiple environments.</span></span>

1. <span data-ttu-id="af61b-125">Kamēr notiks entītiju ielāde, tiks rādīts ielādēšanas dialoglodziņš.</span><span class="sxs-lookup"><span data-stu-id="af61b-125">You'll see a loading dialog box while your entities are loaded.</span></span> <span data-ttu-id="af61b-126">Kad ir ielādētas visas atlasītās entītijas, varat izmantot Power BI iespējas, lai vizualizētu datus.</span><span class="sxs-lookup"><span data-stu-id="af61b-126">Once all of your selected entities have loaded, you can use the capabilities of Power BI to visualize the data.</span></span>

## <a name="large-data-sets"></a><span data-ttu-id="af61b-127">Lielas datu kopas</span><span class="sxs-lookup"><span data-stu-id="af61b-127">Large data sets</span></span>

<span data-ttu-id="af61b-128">Customer Insights savienotājs Power BI ir paredzēts darbam ar datu kopām, kurās ir līdz 1 000 000 klientu profilu.</span><span class="sxs-lookup"><span data-stu-id="af61b-128">The Customer Insights connector for Power BI is designed to work for data sets that contain up to 1 million customer profiles.</span></span> <span data-ttu-id="af61b-129">Lielāku datu kopu importēšana var strādāt, bet tai ir nepieciešams ilgs laiks.</span><span class="sxs-lookup"><span data-stu-id="af61b-129">Importing larger data sets may work, but it takes a long time.</span></span> <span data-ttu-id="af61b-130">Turklāt process var tikt pārtraukts, jo Power BI pastāv ierobežojumi.</span><span class="sxs-lookup"><span data-stu-id="af61b-130">Additionally, the process could run into a time-out because of Power BI limitations.</span></span> <span data-ttu-id="af61b-131">Papildinformāciju skatiet [Power BI: ieteikumi lielām datu kopām](/power-bi/admin/service-premium-what-is#large-datasets).</span><span class="sxs-lookup"><span data-stu-id="af61b-131">For more information, see [Power BI: Recommendations for large data sets](/power-bi/admin/service-premium-what-is#large-datasets).</span></span> 

### <a name="work-with-a-subset-of-data"></a><span data-ttu-id="af61b-132">Darbs ar datu apakškopu</span><span class="sxs-lookup"><span data-stu-id="af61b-132">Work with a subset of data</span></span>

<span data-ttu-id="af61b-133">Apsveriet iespēju strādāt ar datu apakškopu.</span><span class="sxs-lookup"><span data-stu-id="af61b-133">Consider working with a subset of your data.</span></span> <span data-ttu-id="af61b-134">Piemēram, varat izveidot [segmentus](segments.md), nevis visu klientu ierakstu eksportēšanu uz Power BI.</span><span class="sxs-lookup"><span data-stu-id="af61b-134">For example, you can create [segments](segments.md) instead of exporting all customer records to Power BI.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="af61b-135">Problēmu novēršana</span><span class="sxs-lookup"><span data-stu-id="af61b-135">Troubleshooting</span></span>

### <a name="customer-insights-environment-doesnt-show-in-power-bi"></a><span data-ttu-id="af61b-136">Customer Insights vide netiek rādīta programmā Power BI</span><span class="sxs-lookup"><span data-stu-id="af61b-136">Customer Insights environment doesn't show in Power BI</span></span>

<span data-ttu-id="af61b-137">Vidēs, kurās ir definētas vairāk nekā vienas [attiecības](relationships.md) starp divām vienādām entītijām auditorijas ieskatos, savienotājā Power BI nebūs pieejamas.</span><span class="sxs-lookup"><span data-stu-id="af61b-137">Environments that have more than one [relationship](relationships.md) defined between two identical entities in audience insights will not be available in the Power BI connector.</span></span>

<span data-ttu-id="af61b-138">Varat identificēt un noņemt dublicētās attiecības.</span><span class="sxs-lookup"><span data-stu-id="af61b-138">You can identify and remove the duplicated relationships.</span></span>

1. <span data-ttu-id="af61b-139">Auditorijas ieskatos dodieties uz **Dati** > **Attiecības** Power BI pazudušajā vidē.</span><span class="sxs-lookup"><span data-stu-id="af61b-139">In audience insights, go to **Data** > **Relationships** on the environment you're missing in Power BI.</span></span>
2. <span data-ttu-id="af61b-140">Nosakiet dublicētās attiecības:</span><span class="sxs-lookup"><span data-stu-id="af61b-140">Identify duplicated relationships:</span></span>
   - <span data-ttu-id="af61b-141">Pārbaudiet, vai starp vienām un tām pašām divām entītijām ir definētas vairākas attiecības.</span><span class="sxs-lookup"><span data-stu-id="af61b-141">Check if there is more than one relationship defined between the same two entities.</span></span>
   - <span data-ttu-id="af61b-142">Pārbaudiet, vai ir izveidotas attiecības starp divām entītijām, kas ir iekļautas apvienošanas procesā.</span><span class="sxs-lookup"><span data-stu-id="af61b-142">Check if there is a relationship created between two entities that are both included in the unification process.</span></span> <span data-ttu-id="af61b-143">Pastāv netiešas attiecības, kas tiek definētas starp visām entītijām, kas ir iekļautas apvienošanas procesā.</span><span class="sxs-lookup"><span data-stu-id="af61b-143">There is an implicit relationship defined between all entities included in the unification process.</span></span>
3. <span data-ttu-id="af61b-144">Noņemiet visus identificēto attiecību dublikātus.</span><span class="sxs-lookup"><span data-stu-id="af61b-144">Remove any duplicate relationships identified.</span></span>

<span data-ttu-id="af61b-145">Pēc dublicēto attiecību noņemšanas mēģiniet vēlreiz konfigurēt Power BI savienotāju.</span><span class="sxs-lookup"><span data-stu-id="af61b-145">After removal of the duplicated relationships, try to configure the Power BI connector again.</span></span> <span data-ttu-id="af61b-146">Videi tagad ir jābūt pieejamai.</span><span class="sxs-lookup"><span data-stu-id="af61b-146">The environment should be available now.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]