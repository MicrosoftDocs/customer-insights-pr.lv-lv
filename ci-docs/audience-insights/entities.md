---
title: Entītijas un datu kopas.
description: Datu skatīšana Entītiju lapā.
ms.date: 04/16/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: f81128183b6e20e1078ad38c42c771d343909270
ms.sourcegitcommit: c1841ab91fbef9ead9db0f63fbc669cc3af80c12
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 05/17/2021
ms.locfileid: "6049403"
---
# <a name="entities-in-audience-insights"></a><span data-ttu-id="59bb7-103">Entītijas auditorijas ieskatiem</span><span class="sxs-lookup"><span data-stu-id="59bb7-103">Entities in audience insights</span></span>

<span data-ttu-id="59bb7-104">Pēc [datu avotu konfigurēšanas](data-sources.md) pārejiet uz lapu **Entītijas**, lai novērtētu uzņemto datu kvalitāti.</span><span class="sxs-lookup"><span data-stu-id="59bb7-104">After [configuring your data sources](data-sources.md), go to the **Entities** page to evaluate the quality of the ingested data.</span></span> <span data-ttu-id="59bb7-105">Entītijas tiek uzskatītas par datu kopām.</span><span class="sxs-lookup"><span data-stu-id="59bb7-105">Entities are considered datasets.</span></span> <span data-ttu-id="59bb7-106">Dynamics 365 Customer Insights daudzās iespējas ir veidotas ap šīm entītijām.</span><span class="sxs-lookup"><span data-stu-id="59bb7-106">Multiple capabilities of Dynamics 365 Customer Insights are built around these entities.</span></span> <span data-ttu-id="59bb7-107">Rūpīga to pārskatīšana var palīdzēt pārbaudīt šo iespēju rezultātus.</span><span class="sxs-lookup"><span data-stu-id="59bb7-107">Reviewing them closely can help you validate the output of those capabilities.</span></span>

<span data-ttu-id="59bb7-108">Lapā **Entītijas** tiek norādītas entītijas, un tajā ir vairākas kolonnas.</span><span class="sxs-lookup"><span data-stu-id="59bb7-108">The **Entities** page lists entities and includes several columns:</span></span>

- <span data-ttu-id="59bb7-109">**Nosaukums**: Datu entītijas nosaukums.</span><span class="sxs-lookup"><span data-stu-id="59bb7-109">**Name**: The name of your data entity.</span></span> <span data-ttu-id="59bb7-110">Ja blakus entītijas nosaukumam tiek rādīts brīdinājuma simbols, tas nozīmē, ka šīs entītijas dati netika veiksmīgi ielādēti.</span><span class="sxs-lookup"><span data-stu-id="59bb7-110">If you see a warning symbol next to an entity name, it means that the data for that entity didn't load successfully.</span></span>
- <span data-ttu-id="59bb7-111">**Avots**: Tas datu avota veids, kas uzņēma entītiju</span><span class="sxs-lookup"><span data-stu-id="59bb7-111">**Source**: The type of data source that ingested the entity</span></span>
- <span data-ttu-id="59bb7-112">**Izveidoja**: Tās personas vārds, kura izveidoja šo entītiju</span><span class="sxs-lookup"><span data-stu-id="59bb7-112">**Created by**: Name of the person who created the entity</span></span>
- <span data-ttu-id="59bb7-113">**Izveidots**: Entītijas izveides datums un laiks</span><span class="sxs-lookup"><span data-stu-id="59bb7-113">**Created**: Date and time of the entity creation</span></span>
- <span data-ttu-id="59bb7-114">**Atjaunināja**: Tās personas vārds, kura atjaunināja šo entītiju</span><span class="sxs-lookup"><span data-stu-id="59bb7-114">**Updated by**: Name of the person who updated the entity</span></span>
- <span data-ttu-id="59bb7-115">**Pēdējā atjaunināšana**: Entītijas pēdējās atjaunināšanas datums un laiks</span><span class="sxs-lookup"><span data-stu-id="59bb7-115">**Last updated**: Date and time of the last update of the entity</span></span>
- <span data-ttu-id="59bb7-116">**Pēdējā atsvaidzināšana**: Pēdējās datu atsvaidzināšanas datums un laiks</span><span class="sxs-lookup"><span data-stu-id="59bb7-116">**Last refresh**: Date and time of the last data refresh</span></span>

## <a name="exploring-a-specific-entitys-data"></a><span data-ttu-id="59bb7-117">Noteiktu entītijas datu izpēte</span><span class="sxs-lookup"><span data-stu-id="59bb7-117">Exploring a specific entity's data</span></span>

<span data-ttu-id="59bb7-118">Atlasiet entītiju, lai izpētītu tajā ietvertos dažādos laukus un ierakstus.</span><span class="sxs-lookup"><span data-stu-id="59bb7-118">Select an entity to explore the different fields and records included within that entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="59bb7-119">![Entītijas atlase](media/data-manager-entities-data.png "Atlasīt entītiju")</span><span class="sxs-lookup"><span data-stu-id="59bb7-119">![Select an entity](media/data-manager-entities-data.png "Select an entity")</span></span>

- <span data-ttu-id="59bb7-120">Cilnē **Dati** ir redzama tabulas detalizēta informācija par atsevišķiem entītijas ierakstiem.</span><span class="sxs-lookup"><span data-stu-id="59bb7-120">The **Data** tab shows a table listing details about individual records of the entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="59bb7-121">![Tabula Lauki](media/data-manager-entities-fields.PNG "Tabula Lauki")</span><span class="sxs-lookup"><span data-stu-id="59bb7-121">![Fields table](media/data-manager-entities-fields.PNG "Fields table")</span></span>

- <span data-ttu-id="59bb7-122">Pēc noklusējuma ir atlasīta cilne **Atribūti**, un tajā ir redzama tabula, lai pārskatītu atlasītās entītijas detalizēto informāciju, piemēram, lauku nosaukumus, datu tipus un tipus.</span><span class="sxs-lookup"><span data-stu-id="59bb7-122">The **Attributes** tab is selected by default and shows a table to review details for the selected entity, such as field names, data types, and types.</span></span> <span data-ttu-id="59bb7-123">Kolonnā **Tips** ir redzami kopējā datu modeļa saistītie tipi, ko ir automātiski identificējusi sistēma vai [manuāli kartējuši](map-entities.md) lietotāji.</span><span class="sxs-lookup"><span data-stu-id="59bb7-123">The **Type** column shows Common Data Model associated types, which are either auto-identified by the system or [manually mapped](map-entities.md) by users.</span></span> <span data-ttu-id="59bb7-124">Šie ir semantiski tipi, kas var atšķirties no atribūtu datu tipiem — piemēram, tālāk redzamajā laukā *Email* ir ietverts datu tips *Text*, bet tā (semantiskais) kopējā datu modeļa tips var būt *Email* vai *EmailAddress*.</span><span class="sxs-lookup"><span data-stu-id="59bb7-124">These are semantic types that can differ from the attributes' data types—for example, the field *Email* below has a data type *Text* but its (semantic) Common Data Model type might be *Email* or *EmailAddress*.</span></span>

> [!NOTE]
> <span data-ttu-id="59bb7-125">Abās tabulās ir redzams tikai entītijas datu paraugs.</span><span class="sxs-lookup"><span data-stu-id="59bb7-125">Both tables show only a sample of your entity's data.</span></span> <span data-ttu-id="59bb7-126">Lai skatītu pilnu datu kopu, atveriet lapu **Datu avoti**, atlasiet entītiju, atlasiet **Rediģēt** un pēc tam skatiet šīs entītijas datus, izmantojot Power Query redaktoru, kā paskaidrots tēmā [Datu avoti](data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="59bb7-126">To view the full data set, go to the **Data sources** page, select an entity, select **Edit**, and then view this entity's data with the Power Query editor as explained in [Data sources](data-sources.md).</span></span>

<span data-ttu-id="59bb7-127">Lai uzzinātu vairāk par entītijā pieņemtajiem datiem, kolonnā **Kopsavilkums** ir norādītas svarīgas datu īpašības, piemēram, vērtības Null, trūkstošās vērtības, unikālās vērtības, skaits un izplatīšanas reižu skaits attiecībā uz jūsu datiem.</span><span class="sxs-lookup"><span data-stu-id="59bb7-127">To learn more about the data ingested in the entity, the **Summary** column provides you with some important characteristics of the data, such as nulls, missing values, unique values, counts, and distributions, as applicable to your data.</span></span>

<span data-ttu-id="59bb7-128">Atlasiet diagrammas ikonu, lai skatītu datu kopsavilkumu.</span><span class="sxs-lookup"><span data-stu-id="59bb7-128">Select the chart icon to see the summary of the data.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="59bb7-129">![Kopsavilkuma simbols](media/data-manager-entities-summary.png "Tabula Datu kopsavilkums")</span><span class="sxs-lookup"><span data-stu-id="59bb7-129">![Summary symbol](media/data-manager-entities-summary.png "Data summary table")</span></span>

### <a name="next-step"></a><span data-ttu-id="59bb7-130">Nākamā darbība</span><span class="sxs-lookup"><span data-stu-id="59bb7-130">Next step</span></span>

<span data-ttu-id="59bb7-131">Skatiet rakstu [Apvienošana](data-unification.md), lai uzzinātu, kā *kartēt*, *noteikt atbilstību* un *sapludināt* pieņemtos datus.</span><span class="sxs-lookup"><span data-stu-id="59bb7-131">See the [Unify](data-unification.md) topic to learn how to *map*, *match*, and *merge* the ingested data.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
