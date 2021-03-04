---
title: Power Query esošu datu avotu inkrementālā atsvaidzināšana.
description: Atsvaidziniet jaunus un atjauninātus datus lieliem datu avotiem, kas balstīti Power Query.
ms.date: 09/28/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d4b01be75d25fa0e120904924a193171eefec579
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268557"
---
# <a name="incremental-refresh-for-data-sources-based-on-power-query"></a><span data-ttu-id="319f7-103">Inkrementālā atsvaidzināšana Power Query bāzes datu avotiem</span><span class="sxs-lookup"><span data-stu-id="319f7-103">Incremental refresh for data sources based on Power Query</span></span>

<span data-ttu-id="319f7-104">Inkrementālajai datu avotu atsvaidzināšanai ir šādas priekšrocības:</span><span class="sxs-lookup"><span data-stu-id="319f7-104">Incremental refresh for data sources provides the following advantages:</span></span>

- <span data-ttu-id="319f7-105">**Ātrāka atsvaidzināšana** — Tiek atsvaidzināti tikai tie dati, kas tika mainīti.</span><span class="sxs-lookup"><span data-stu-id="319f7-105">**Faster refreshes** - Only data that has changed gets refreshed.</span></span> <span data-ttu-id="319f7-106">Piemēram, jūs varat atsvaidzināt tikai pēdējās piecas vēstures datu kopas dienas.</span><span class="sxs-lookup"><span data-stu-id="319f7-106">For example, you might refresh only the past five days of a historical dataset.</span></span>
- <span data-ttu-id="319f7-107">**Lielāka uzticamība** — Ar mazākiem atsvaidzināšanas savienojumiem nav nepieciešams uzturēt savienojumus ar netveramām avota sistēmām tik ilgi, samazinot savienojuma problēmu risku.</span><span class="sxs-lookup"><span data-stu-id="319f7-107">**Increased reliability** - With smaller refreshes, you don't need to maintain connections to volatile source systems for as long, reducing the risk of connection issues.</span></span>
- <span data-ttu-id="319f7-108">**Samazināts resursu patēriņš** — Atsvaidzinot tikai datu apakškopu no jūsu datu kopapjoma, tiek efektīvāk izmantoti skaitļošanas resursi un samazināta ietekme uz vidi.</span><span class="sxs-lookup"><span data-stu-id="319f7-108">**Reduced resource consumption** - Refreshing only a subset of your total data leads to more efficient use of computing resources and decreases the environmental footprint.</span></span>

## <a name="configure-incremental-refresh"></a><span data-ttu-id="319f7-109">Konfigurēt inkrementālo atsvaidzināšanu</span><span class="sxs-lookup"><span data-stu-id="319f7-109">Configure incremental refresh</span></span>

<span data-ttu-id="319f7-110">Auditorijas ieskati ļauj inkrementāli atsvaidzināt datus, kuri ir importēti, izmantojot Power Query, kas atbalsta inkrementālu uzņemšanu.</span><span class="sxs-lookup"><span data-stu-id="319f7-110">Audience insights allows incremental refresh for data sources imported through Power Query that support incremental ingestion.</span></span> <span data-ttu-id="319f7-111">Piemēram, Azure SQL datu bāzes ar datuma un laika laukiem, kas norāda, kad pēdējo reizi tika atjaunināti datu ieraksti.</span><span class="sxs-lookup"><span data-stu-id="319f7-111">For example, Azure SQL databases with date and time fields, which indicate when data records were last updated.</span></span>

1. <span data-ttu-id="319f7-112">[Jauna Power Query bāzes datu avota izveide](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="319f7-112">[Create a new data source based on Power Query](connect-power-query.md).</span></span>

1. <span data-ttu-id="319f7-113">Ierakstiet datu avota nosaukumu.</span><span class="sxs-lookup"><span data-stu-id="319f7-113">Provide a name for the data source.</span></span>

1. <span data-ttu-id="319f7-114">Atlasiet datu avotu, kas atbalsta inkrementālo atsvaidzināšanu, piemēram, Azure SQL datu bāzi.</span><span class="sxs-lookup"><span data-stu-id="319f7-114">Select a data source that supports incremental refresh, such as Azure SQL database.</span></span>

1. <span data-ttu-id="319f7-115">Atlasiet uzņemamās entitījas vai tabulas.</span><span class="sxs-lookup"><span data-stu-id="319f7-115">Select the entities or tables to ingest.</span></span>

1. <span data-ttu-id="319f7-116">Pabeidziet transformācijas darbības un atlasiet **Tālāk**.</span><span class="sxs-lookup"><span data-stu-id="319f7-116">Complete the transformation steps and select **Next**.</span></span>

1. <span data-ttu-id="319f7-117">Dialoglodziņā **Iestatīt inkrementālo atsvaidzināšanu** atlasiet **Iestatīt**, lai atvērtu sadaļu **Inkrementālā atsvaidzināšanas iestatījumi**.</span><span class="sxs-lookup"><span data-stu-id="319f7-117">In the **Set up incremental refresh** dialog box, select **Set up** to open the **Incremental refresh settings**.</span></span> <span data-ttu-id="319f7-118">Ja atlasīsiet **Izlaist**, datu avots atsvaidzinās viss datu kopu.</span><span class="sxs-lookup"><span data-stu-id="319f7-118">If you select **Skip**, the data source will refresh the entire data set.</span></span>
   > [!TIP]
   > <span data-ttu-id="319f7-119">Inkrementālo atsvaidzināšanu var lietot arī vēlāk, rediģējot esošu datu avotu.</span><span class="sxs-lookup"><span data-stu-id="319f7-119">You can also apply incremental refresh later by editing an existing data source.</span></span>

1. <span data-ttu-id="319f7-120">Sadaļā **Inkrementālās atsvaidzināšanas iestatījumi** jūs konfigurēsiet inkrementālo atsvaidzināšanu visām entītijām, ko atlasījāt, veidojot datu avotu.</span><span class="sxs-lookup"><span data-stu-id="319f7-120">On **Incremental refresh settings**, you'll configure the incremental refresh for all entities that you selected when creating the data source.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="319f7-121">![Entītiju konfigurēšana datu avotā inkrementālajai atsvaidzināšanai](media/incremental-refresh-settings.png "Entītiju konfigurēšana datu avotā inkrementālajai atsvaidzināšanai")</span><span class="sxs-lookup"><span data-stu-id="319f7-121">![Configure entities in a data source for incremental refresh](media/incremental-refresh-settings.png "Configure entities in a data source for incremental refresh")</span></span>

1. <span data-ttu-id="319f7-122">Atlasiet entītiju un norādiet šādu informāciju:</span><span class="sxs-lookup"><span data-stu-id="319f7-122">Select an entity, and provide the following details:</span></span>

   - <span data-ttu-id="319f7-123">**Definēt primāro atslēgu**: Atlasiet entītijas vai tabulas primāro atslēgu.</span><span class="sxs-lookup"><span data-stu-id="319f7-123">**Define the primary key**: Select a primary key for the entity or table.</span></span>
   - <span data-ttu-id="319f7-124">**Definēt lauku “pēdējoreiz atjaunināts”**: Šajā laukā tiek parādīti tikai datuma un laika tipa atribūti.</span><span class="sxs-lookup"><span data-stu-id="319f7-124">**Define the "last updated" field**: This field will only display attributes of type date or time.</span></span> <span data-ttu-id="319f7-125">Atlasiet atribūtu, kas norāda, kad ieraksti tika atjaunināti pēdējoreiz.</span><span class="sxs-lookup"><span data-stu-id="319f7-125">Select an attribute that indicates when the records were last updated.</span></span> <span data-ttu-id="319f7-126">To izmantos, lai identificētu ierakstus, kuri ietilpst inkrementālās atsvaidzināšanas laika periodā.</span><span class="sxs-lookup"><span data-stu-id="319f7-126">It will be used to identify the records that fall within the incremental refresh time frame.</span></span>
   - <span data-ttu-id="319f7-127">**Pārbaudīt, vai ir pieejami atjauninājumi**: Norādiet, cik ilgam ir jābūt inkrementālās atsvaidzināšanas laika periodam.</span><span class="sxs-lookup"><span data-stu-id="319f7-127">**Check for updates every**: Specify how long you want the incremental refresh time frame to be.</span></span>

1. <span data-ttu-id="319f7-128">Atlasiet **Saglabāt**, lai pabeigtu datu avota izveidi.</span><span class="sxs-lookup"><span data-stu-id="319f7-128">Select **Save** to complete the creation of the data source.</span></span> <span data-ttu-id="319f7-129">Sākotnējā datu atsvaidzināšana būs pilna atsvaidzināšana.</span><span class="sxs-lookup"><span data-stu-id="319f7-129">The initial data refresh will be a full refresh.</span></span> <span data-ttu-id="319f7-130">Pēc tam inkrementālā datu atsvaidzināšana notiek, kā tas ir konfigurēts iepriekšējā darbībā.</span><span class="sxs-lookup"><span data-stu-id="319f7-130">Afterwards, the incremental data refresh happens as configured in the previous step.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]