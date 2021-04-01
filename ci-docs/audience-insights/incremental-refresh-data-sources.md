---
title: Power Query esošu datu avotu inkrementālā atsvaidzināšana.
description: Atsvaidziniet jaunus un atjauninātus datus lieliem datu avotiem, kas balstīti Power Query.
ms.date: 09/28/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.openlocfilehash: 03f76bcfc7336d8430146e8a26ffa649c6a17db0
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596830"
---
# <a name="incremental-refresh-for-data-sources-based-on-power-query"></a><span data-ttu-id="ff419-103">Inkrementālā atsvaidzināšana Power Query bāzes datu avotiem</span><span class="sxs-lookup"><span data-stu-id="ff419-103">Incremental refresh for data sources based on Power Query</span></span>

<span data-ttu-id="ff419-104">Inkrementālajai datu avotu atsvaidzināšanai ir šādas priekšrocības:</span><span class="sxs-lookup"><span data-stu-id="ff419-104">Incremental refresh for data sources provides the following advantages:</span></span>

- <span data-ttu-id="ff419-105">**Ātrāka atsvaidzināšana** — Tiek atsvaidzināti tikai tie dati, kas tika mainīti.</span><span class="sxs-lookup"><span data-stu-id="ff419-105">**Faster refreshes** - Only data that has changed gets refreshed.</span></span> <span data-ttu-id="ff419-106">Piemēram, jūs varat atsvaidzināt tikai pēdējās piecas vēstures datu kopas dienas.</span><span class="sxs-lookup"><span data-stu-id="ff419-106">For example, you might refresh only the past five days of a historical dataset.</span></span>
- <span data-ttu-id="ff419-107">**Lielāka uzticamība** — Ar mazākiem atsvaidzināšanas savienojumiem nav nepieciešams uzturēt savienojumus ar netveramām avota sistēmām tik ilgi, samazinot savienojuma problēmu risku.</span><span class="sxs-lookup"><span data-stu-id="ff419-107">**Increased reliability** - With smaller refreshes, you don't need to maintain connections to volatile source systems for as long, reducing the risk of connection issues.</span></span>
- <span data-ttu-id="ff419-108">**Samazināts resursu patēriņš** — Atsvaidzinot tikai datu apakškopu no jūsu datu kopapjoma, tiek efektīvāk izmantoti skaitļošanas resursi un samazināta ietekme uz vidi.</span><span class="sxs-lookup"><span data-stu-id="ff419-108">**Reduced resource consumption** - Refreshing only a subset of your total data leads to more efficient use of computing resources and decreases the environmental footprint.</span></span>

## <a name="configure-incremental-refresh"></a><span data-ttu-id="ff419-109">Konfigurēt inkrementālo atsvaidzināšanu</span><span class="sxs-lookup"><span data-stu-id="ff419-109">Configure incremental refresh</span></span>

<span data-ttu-id="ff419-110">Auditorijas ieskati ļauj inkrementāli atsvaidzināt datus, kuri ir importēti, izmantojot Power Query, kas atbalsta inkrementālu uzņemšanu.</span><span class="sxs-lookup"><span data-stu-id="ff419-110">Audience insights allows incremental refresh for data sources imported through Power Query that support incremental ingestion.</span></span> <span data-ttu-id="ff419-111">Piemēram, Azure SQL datu bāzes ar datuma un laika laukiem, kas norāda, kad pēdējo reizi tika atjaunināti datu ieraksti.</span><span class="sxs-lookup"><span data-stu-id="ff419-111">For example, Azure SQL databases with date and time fields, which indicate when data records were last updated.</span></span>

1. <span data-ttu-id="ff419-112">[Jauna Power Query bāzes datu avota izveide](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="ff419-112">[Create a new data source based on Power Query](connect-power-query.md).</span></span>

1. <span data-ttu-id="ff419-113">Ierakstiet datu avota nosaukumu.</span><span class="sxs-lookup"><span data-stu-id="ff419-113">Provide a name for the data source.</span></span>

1. <span data-ttu-id="ff419-114">Atlasiet datu avotu, kas atbalsta inkrementālo atsvaidzināšanu, piemēram, Azure SQL datu bāzi.</span><span class="sxs-lookup"><span data-stu-id="ff419-114">Select a data source that supports incremental refresh, such as Azure SQL database.</span></span>

1. <span data-ttu-id="ff419-115">Atlasiet uzņemamās entitījas vai tabulas.</span><span class="sxs-lookup"><span data-stu-id="ff419-115">Select the entities or tables to ingest.</span></span>

1. <span data-ttu-id="ff419-116">Pabeidziet transformācijas darbības un atlasiet **Tālāk**.</span><span class="sxs-lookup"><span data-stu-id="ff419-116">Complete the transformation steps and select **Next**.</span></span>

1. <span data-ttu-id="ff419-117">Dialoglodziņā **Iestatīt inkrementālo atsvaidzināšanu** atlasiet **Iestatīt**, lai atvērtu sadaļu **Inkrementālā atsvaidzināšanas iestatījumi**.</span><span class="sxs-lookup"><span data-stu-id="ff419-117">In the **Set up incremental refresh** dialog box, select **Set up** to open the **Incremental refresh settings**.</span></span> <span data-ttu-id="ff419-118">Ja atlasīsiet **Izlaist**, datu avots atsvaidzinās viss datu kopu.</span><span class="sxs-lookup"><span data-stu-id="ff419-118">If you select **Skip**, the data source will refresh the entire data set.</span></span>
   > [!TIP]
   > <span data-ttu-id="ff419-119">Inkrementālo atsvaidzināšanu var lietot arī vēlāk, rediģējot esošu datu avotu.</span><span class="sxs-lookup"><span data-stu-id="ff419-119">You can also apply incremental refresh later by editing an existing data source.</span></span>

1. <span data-ttu-id="ff419-120">Sadaļā **Inkrementālās atsvaidzināšanas iestatījumi** jūs konfigurēsiet inkrementālo atsvaidzināšanu visām entītijām, ko atlasījāt, veidojot datu avotu.</span><span class="sxs-lookup"><span data-stu-id="ff419-120">On **Incremental refresh settings**, you'll configure the incremental refresh for all entities that you selected when creating the data source.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ff419-121">![Entītiju konfigurēšana datu avotā inkrementālajai atsvaidzināšanai](media/incremental-refresh-settings.png "Entītiju konfigurēšana datu avotā inkrementālajai atsvaidzināšanai")</span><span class="sxs-lookup"><span data-stu-id="ff419-121">![Configure entities in a data source for incremental refresh](media/incremental-refresh-settings.png "Configure entities in a data source for incremental refresh")</span></span>

1. <span data-ttu-id="ff419-122">Atlasiet entītiju un norādiet šādu informāciju:</span><span class="sxs-lookup"><span data-stu-id="ff419-122">Select an entity, and provide the following details:</span></span>

   - <span data-ttu-id="ff419-123">**Definēt primāro atslēgu**: Atlasiet entītijas vai tabulas primāro atslēgu.</span><span class="sxs-lookup"><span data-stu-id="ff419-123">**Define the primary key**: Select a primary key for the entity or table.</span></span>
   - <span data-ttu-id="ff419-124">**Definēt lauku “pēdējoreiz atjaunināts”**: Šajā laukā tiek parādīti tikai datuma un laika tipa atribūti.</span><span class="sxs-lookup"><span data-stu-id="ff419-124">**Define the "last updated" field**: This field will only display attributes of type date or time.</span></span> <span data-ttu-id="ff419-125">Atlasiet atribūtu, kas norāda, kad ieraksti tika atjaunināti pēdējoreiz.</span><span class="sxs-lookup"><span data-stu-id="ff419-125">Select an attribute that indicates when the records were last updated.</span></span> <span data-ttu-id="ff419-126">To izmantos, lai identificētu ierakstus, kuri ietilpst inkrementālās atsvaidzināšanas laika periodā.</span><span class="sxs-lookup"><span data-stu-id="ff419-126">It will be used to identify the records that fall within the incremental refresh time frame.</span></span>
   - <span data-ttu-id="ff419-127">**Pārbaudīt, vai ir pieejami atjauninājumi**: Norādiet, cik ilgam ir jābūt inkrementālās atsvaidzināšanas laika periodam.</span><span class="sxs-lookup"><span data-stu-id="ff419-127">**Check for updates every**: Specify how long you want the incremental refresh time frame to be.</span></span>

1. <span data-ttu-id="ff419-128">Atlasiet **Saglabāt**, lai pabeigtu datu avota izveidi.</span><span class="sxs-lookup"><span data-stu-id="ff419-128">Select **Save** to complete the creation of the data source.</span></span> <span data-ttu-id="ff419-129">Sākotnējā datu atsvaidzināšana būs pilna atsvaidzināšana.</span><span class="sxs-lookup"><span data-stu-id="ff419-129">The initial data refresh will be a full refresh.</span></span> <span data-ttu-id="ff419-130">Pēc tam inkrementālā datu atsvaidzināšana notiek, kā tas ir konfigurēts iepriekšējā darbībā.</span><span class="sxs-lookup"><span data-stu-id="ff419-130">Afterwards, the incremental data refresh happens as configured in the previous step.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]