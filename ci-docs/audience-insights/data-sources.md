---
title: Izmantojiet datu avotus datu uzņemšanai
description: Uzziniet, kā importēt datus no dažādiem avotiem.
ms.date: 11/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 780dc61a82d6ed9856a37dc8f164fa946d982bbe
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595956"
---
# <a name="data-sources-overview"></a><span data-ttu-id="b0d59-103">Datu avotu pārskats</span><span class="sxs-lookup"><span data-stu-id="b0d59-103">Data sources overview</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="b0d59-104">Auditorijas ieskatus Dynamics 365 Customer Insights var savienot ar datiem no plašas avotu kopas.</span><span class="sxs-lookup"><span data-stu-id="b0d59-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="b0d59-105">Pieslēgšanos datu avotam bieži vien dēvē par *datu uzņemšanas* procesu.</span><span class="sxs-lookup"><span data-stu-id="b0d59-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="b0d59-106">Pēc datu uzņemšanas varat tos [apvienot](data-unification.md) un veikt ar tiem darbības.</span><span class="sxs-lookup"><span data-stu-id="b0d59-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="b0d59-107">Pievienot datu avotu</span><span class="sxs-lookup"><span data-stu-id="b0d59-107">Add a data source</span></span>

<span data-ttu-id="b0d59-108">Skatiet detalizētus rakstus, kā pievienot datu avotu atkarībā no izvēlētās opcijas.</span><span class="sxs-lookup"><span data-stu-id="b0d59-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="b0d59-109">Datu avotu varat pievienot trīs galvenajos veidos:</span><span class="sxs-lookup"><span data-stu-id="b0d59-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="b0d59-110">Izmantojot daudzos Power Query savienotājus</span><span class="sxs-lookup"><span data-stu-id="b0d59-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="b0d59-111">No Common Data Model mapes</span><span class="sxs-lookup"><span data-stu-id="b0d59-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="b0d59-112">No sava Common Data Service ezera</span><span class="sxs-lookup"><span data-stu-id="b0d59-112">From your own Common Data Service lake</span></span>](connect-common-data-service-lake.md)

> [!NOTE]
> <span data-ttu-id="b0d59-113">Pagaidām nav iespējams pievienot datus no lokālajiem datu avotiem.</span><span class="sxs-lookup"><span data-stu-id="b0d59-113">You can't add data from on-premises data sources yet.</span></span>

## <a name="review-ingested-data"></a><span data-ttu-id="b0d59-114">Uzņemto datu pārskatīšana</span><span class="sxs-lookup"><span data-stu-id="b0d59-114">Review ingested data</span></span>

<span data-ttu-id="b0d59-115">Jūs redzēsit katra uzņemtā datu avota nosaukumu, tā statusu un pēdējo reizi, kad dati tika atsvaidzināti no šī avota.</span><span class="sxs-lookup"><span data-stu-id="b0d59-115">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="b0d59-116">Datu avotu sarakstu var kārtot pēc katras kolonnas.</span><span class="sxs-lookup"><span data-stu-id="b0d59-116">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="b0d59-117">![Pievienotie datu avoti](media/configure-data-datasource-added.png "Pievienotie datu avoti")</span><span class="sxs-lookup"><span data-stu-id="b0d59-117">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="b0d59-118">Statuss</span><span class="sxs-lookup"><span data-stu-id="b0d59-118">Status</span></span>  |<span data-ttu-id="b0d59-119">Apraksts</span><span class="sxs-lookup"><span data-stu-id="b0d59-119">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="b0d59-120">Veiksmīgi</span><span class="sxs-lookup"><span data-stu-id="b0d59-120">Successful</span></span>   |<span data-ttu-id="b0d59-121">Datu avots tika veiksmīgi paņemts, ja ir minēts laiks kolonnā **Atsvaidzināts**.</span><span class="sxs-lookup"><span data-stu-id="b0d59-121">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="b0d59-122">Nav sākts</span><span class="sxs-lookup"><span data-stu-id="b0d59-122">Not started</span></span>   |<span data-ttu-id="b0d59-123">Datu avots nesatur datus, kas ir uzņemti vai vēl ir melnraksta režīmā.</span><span class="sxs-lookup"><span data-stu-id="b0d59-123">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="b0d59-124">Notiek atsvaidzināšana</span><span class="sxs-lookup"><span data-stu-id="b0d59-124">Refreshing</span></span>    |<span data-ttu-id="b0d59-125">Notiek datu uzņemšana.</span><span class="sxs-lookup"><span data-stu-id="b0d59-125">Data ingestion is in progress.</span></span> <span data-ttu-id="b0d59-126">Šo darbību varat atcelt, kolonnā **Darbības** atlasot **Apturēt atsvaidzināšanu**.</span><span class="sxs-lookup"><span data-stu-id="b0d59-126">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="b0d59-127">Apturot datu avota atsvaidzināšanu, tas atkal kļūs tāds pats kā pēdējās atsvaidzināšanas brīdī.</span><span class="sxs-lookup"><span data-stu-id="b0d59-127">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="b0d59-128">Neizdevās</span><span class="sxs-lookup"><span data-stu-id="b0d59-128">Failed</span></span>     |<span data-ttu-id="b0d59-129">Veicot datu uzņemšanu, radās kļūdas.</span><span class="sxs-lookup"><span data-stu-id="b0d59-129">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="b0d59-130">Atlasiet vērtību jebkura datu avoti kolonnā **Statuss**, lai pārskatītu papildinformāciju.</span><span class="sxs-lookup"><span data-stu-id="b0d59-130">Select the value in the **Status** column of any data source to review more details.</span></span> <span data-ttu-id="b0d59-131">Rūtī **Detalizēta informācija** izvērsiet **Datu avoti**.</span><span class="sxs-lookup"><span data-stu-id="b0d59-131">In the **Progress details** pane, expand **Data sources**.</span></span> <span data-ttu-id="b0d59-132">Atlasiet **Skatīt detalizētu informāciju** papildu informācijai par atsvaidzināšanas statusu, ieskaitot kļūdas detaļas un pakārtotā procesa atjauninājumus.</span><span class="sxs-lookup"><span data-stu-id="b0d59-132">Select **See details** for more information about the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="b0d59-133">Datu ielāde var ilgt kādu laiku.</span><span class="sxs-lookup"><span data-stu-id="b0d59-133">Loading data can take some time.</span></span> <span data-ttu-id="b0d59-134">Pēc veiksmīgas atsvaidzināšanas uzņemtos datus var pārskatīt no lapas **Entītijas**.</span><span class="sxs-lookup"><span data-stu-id="b0d59-134">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="b0d59-135">Papildinformāciju skatiet rakstā [Entītijas](entities.md).</span><span class="sxs-lookup"><span data-stu-id="b0d59-135">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="b0d59-136">Atsvaidzināt datu avotu</span><span class="sxs-lookup"><span data-stu-id="b0d59-136">Refresh a data source</span></span>

<span data-ttu-id="b0d59-137">Datu avotus var atsvaidzināt pēc automātiska grafika vai atsvaidzināt manuāli pēc pieprasījuma.</span><span class="sxs-lookup"><span data-stu-id="b0d59-137">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="b0d59-138">Apmeklējiet **Administrators** > **Sistēma** > [**Grafiks**](system.md#schedule-tab), lai konfigurētu visu jūsu uzņemto datu avotu plānoto atsvaidzināšanu.</span><span class="sxs-lookup"><span data-stu-id="b0d59-138">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="b0d59-139">Lai atsvaidzinātu datu avotu pēc pieprasījuma, veiciet šīs darbības:</span><span class="sxs-lookup"><span data-stu-id="b0d59-139">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="b0d59-140">Sadaļā Auditorijas ieskati ejiet uz **Dati** > **Datu avoti**.</span><span class="sxs-lookup"><span data-stu-id="b0d59-140">In audience insights, go to **Data** > **Data sources**</span></span>

2. <span data-ttu-id="b0d59-141">Atlasiet vertikālo daudzpunkti blakus atsvaidzināmajam datu avotam un nolaižamajā izvēlnē atlasiet **Atsvaidzināt**.</span><span class="sxs-lookup"><span data-stu-id="b0d59-141">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the drop-down list.</span></span>

3. <span data-ttu-id="b0d59-142">Datu avots tagad tiek iespējots manuālai atsvaidzināšanai.</span><span class="sxs-lookup"><span data-stu-id="b0d59-142">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="b0d59-143">Atsvaidzinot datu avotu, tiek atjaunināta gan entītijas shēma, gan visu entītiju dati, kas ir norādīti datu avotā.</span><span class="sxs-lookup"><span data-stu-id="b0d59-143">Refreshing a data source will update both the entity schema as well as data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="b0d59-144">Atlasiet **Pārtraukt atsvaidzināšanu**, ja vēlaties atcelt esošu atsvaidzināšanu, un datu avots atgriezīsies pēdējās atsvaidzināšanas statusā.</span><span class="sxs-lookup"><span data-stu-id="b0d59-144">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="b0d59-145">Datu avota dzēšana</span><span class="sxs-lookup"><span data-stu-id="b0d59-145">Delete a data source</span></span>

1. <span data-ttu-id="b0d59-146">Sadaļā Auditorijas ieskati skatiet **Dati** > **Datu avoti**.</span><span class="sxs-lookup"><span data-stu-id="b0d59-146">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="b0d59-147">Atlasiet vertikālo daudzpunkti blakus noņemamajam datu avotam un nolaižamajā izvēlnē atlasiet **Dzēst**.</span><span class="sxs-lookup"><span data-stu-id="b0d59-147">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the drop-down menu.</span></span>

3. <span data-ttu-id="b0d59-148">Apstipriniet dzēšanu.</span><span class="sxs-lookup"><span data-stu-id="b0d59-148">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]