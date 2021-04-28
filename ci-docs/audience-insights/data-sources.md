---
title: Izmantojiet datu avotus datu uzņemšanai
description: Uzziniet, kā importēt datus no dažādiem avotiem.
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 0fc13d3ac0a5176637b6fe481dabe0b2aec11649
ms.sourcegitcommit: d89b19b2a3497722b78362aeee688ae7e94915d9
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 04/13/2021
ms.locfileid: "5887903"
---
# <a name="data-sources-overview"></a><span data-ttu-id="731db-103">Datu avotu pārskats</span><span class="sxs-lookup"><span data-stu-id="731db-103">Data sources overview</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="731db-104">Auditorijas ieskatus Dynamics 365 Customer Insights var savienot ar datiem no plašas avotu kopas.</span><span class="sxs-lookup"><span data-stu-id="731db-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="731db-105">Pieslēgšanos datu avotam bieži vien dēvē par *datu uzņemšanas* procesu.</span><span class="sxs-lookup"><span data-stu-id="731db-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="731db-106">Pēc datu uzņemšanas varat tos [apvienot](data-unification.md) un veikt ar tiem darbības.</span><span class="sxs-lookup"><span data-stu-id="731db-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="731db-107">Pievienot datu avotu</span><span class="sxs-lookup"><span data-stu-id="731db-107">Add a data source</span></span>

<span data-ttu-id="731db-108">Skatiet detalizētus rakstus, kā pievienot datu avotu atkarībā no izvēlētās opcijas.</span><span class="sxs-lookup"><span data-stu-id="731db-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="731db-109">Datu avotu varat pievienot trīs galvenajos veidos:</span><span class="sxs-lookup"><span data-stu-id="731db-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="731db-110">Izmantojot daudzos Power Query savienotājus</span><span class="sxs-lookup"><span data-stu-id="731db-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="731db-111">No Common Data Model mapes</span><span class="sxs-lookup"><span data-stu-id="731db-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="731db-112">No sava Common Data Service ezera</span><span class="sxs-lookup"><span data-stu-id="731db-112">From your own Common Data Service lake</span></span>](connect-common-data-service-lake.md)

## <a name="add-data-from-on-premises-data-sources"></a><span data-ttu-id="731db-113">Datu pievienošana no lokālajiem datu avotiem</span><span class="sxs-lookup"><span data-stu-id="731db-113">Add data from on-premises data sources</span></span>

<span data-ttu-id="731db-114">Datu uzņemšana no lokālajiem datu avotiem Audience Insights tiek atbalstīta, balstoties Power Platform datu plūsmām.</span><span class="sxs-lookup"><span data-stu-id="731db-114">Ingesting data from on-premises data sources in Audience Insights is supported based on Power Platform dataflows.</span></span> <span data-ttu-id="731db-115">Datu plūsmas var iespējot risinājumā Customer Insights, [nodrošinot Microsoft Dataverse vides URL](manage-environments.md#create-an-environment-in-an-existing-organization), kad tiek iestatīta vide.</span><span class="sxs-lookup"><span data-stu-id="731db-115">Dataflows can be enabled in Customer Insights by [providing the Microsoft Dataverse environment URL](manage-environments.md#create-an-environment-in-an-existing-organization) when setting up the environment.</span></span>

<span data-ttu-id="731db-116">Datu avoti, kuri tiek izveidoti pēc saistīšanas ar Dataverse vidi ar Customer Insights, pēc noklusējuma izmantos [Power Platform datu plūsmas](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365).</span><span class="sxs-lookup"><span data-stu-id="731db-116">Data sources that are created after associating a Dataverse environment with Customer Insights will use [Power Platform dataflows](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) by default.</span></span> <span data-ttu-id="731db-117">Datu plūsmas atbalsta lokālo savienojamību, izmantojot datu vārtejas.</span><span class="sxs-lookup"><span data-stu-id="731db-117">Dataflows support on-prem connectivity using the data gateways.</span></span> <span data-ttu-id="731db-118">Noņemiet un no jauna izveidojiet datu avotus, kuri pastāvēja, pirms Dataverse vide tika saistīta, lai lietotu lokālās datu vārtejas.</span><span class="sxs-lookup"><span data-stu-id="731db-118">Remove and recreate data sources that existed before a Dataverse environment was associated to use the on-premises data gateways.</span></span>

<span data-ttu-id="731db-119">Datu vārtejas no esošās Power BI vai Power Apps vides būs redzama, un to varat atkārtoti izmantot risinājumā Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="731db-119">Data gateways from an existing Power BI or Power Apps environment will be visible and you can reuse in Customer Insights.</span></span> <span data-ttu-id="731db-120">Datu avotu lapā redzamas saites uz Power Platform vidi, kurā varat skatīt un konfigurēt lokālo datu vārtejas.</span><span class="sxs-lookup"><span data-stu-id="731db-120">The data sources page shows links to go the Power Platform environment where you can view and configure on-premises data gateways.</span></span>

:::image type="content" source="media/data-sources-onpremises-gateways.png" alt-text=" Ekrānuzņēmums ar datu avotu lapu, kurā redzamas saites, kuras norāda uz Power Platform vidi.":::

## <a name="review-ingested-data"></a><span data-ttu-id="731db-122">Uzņemto datu pārskatīšana</span><span class="sxs-lookup"><span data-stu-id="731db-122">Review ingested data</span></span>

<span data-ttu-id="731db-123">Jūs redzēsit katra uzņemtā datu avota nosaukumu, tā statusu un pēdējo reizi, kad dati tika atsvaidzināti no šī avota.</span><span class="sxs-lookup"><span data-stu-id="731db-123">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="731db-124">Datu avotu sarakstu var kārtot pēc katras kolonnas.</span><span class="sxs-lookup"><span data-stu-id="731db-124">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="731db-125">![Pievienotie datu avoti](media/configure-data-datasource-added.png "Pievienotie datu avoti")</span><span class="sxs-lookup"><span data-stu-id="731db-125">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="731db-126">Statuss</span><span class="sxs-lookup"><span data-stu-id="731db-126">Status</span></span>  |<span data-ttu-id="731db-127">Apraksts</span><span class="sxs-lookup"><span data-stu-id="731db-127">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="731db-128">Veiksmīgi</span><span class="sxs-lookup"><span data-stu-id="731db-128">Successful</span></span>   |<span data-ttu-id="731db-129">Datu avots tika veiksmīgi paņemts, ja ir minēts laiks kolonnā **Atsvaidzināts**.</span><span class="sxs-lookup"><span data-stu-id="731db-129">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="731db-130">Nav sākts</span><span class="sxs-lookup"><span data-stu-id="731db-130">Not started</span></span>   |<span data-ttu-id="731db-131">Datu avots nesatur datus, kas ir uzņemti vai vēl ir melnraksta režīmā.</span><span class="sxs-lookup"><span data-stu-id="731db-131">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="731db-132">Notiek atsvaidzināšana</span><span class="sxs-lookup"><span data-stu-id="731db-132">Refreshing</span></span>    |<span data-ttu-id="731db-133">Notiek datu uzņemšana.</span><span class="sxs-lookup"><span data-stu-id="731db-133">Data ingestion is in progress.</span></span> <span data-ttu-id="731db-134">Šo darbību varat atcelt, kolonnā **Darbības** atlasot **Apturēt atsvaidzināšanu**.</span><span class="sxs-lookup"><span data-stu-id="731db-134">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="731db-135">Apturot datu avota atsvaidzināšanu, tas atkal kļūs tāds pats kā pēdējās atsvaidzināšanas brīdī.</span><span class="sxs-lookup"><span data-stu-id="731db-135">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="731db-136">Neizdevās</span><span class="sxs-lookup"><span data-stu-id="731db-136">Failed</span></span>     |<span data-ttu-id="731db-137">Veicot datu uzņemšanu, radās kļūdas.</span><span class="sxs-lookup"><span data-stu-id="731db-137">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="731db-138">Atlasiet vērtību jebkura datu avoti kolonnā **Statuss**, lai pārskatītu papildinformāciju.</span><span class="sxs-lookup"><span data-stu-id="731db-138">Select the value in the **Status** column of any data source to review more details.</span></span> <span data-ttu-id="731db-139">Rūtī **Detalizēta informācija** izvērsiet **Datu avoti**.</span><span class="sxs-lookup"><span data-stu-id="731db-139">In the **Progress details** pane, expand **Data sources**.</span></span> <span data-ttu-id="731db-140">Atlasiet **Skatīt detalizētu informāciju** papildu informācijai par atsvaidzināšanas statusu, ieskaitot kļūdas detaļas un pakārtotā procesa atjauninājumus.</span><span class="sxs-lookup"><span data-stu-id="731db-140">Select **See details** for more information about the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="731db-141">Datu ielāde var ilgt kādu laiku.</span><span class="sxs-lookup"><span data-stu-id="731db-141">Loading data can take some time.</span></span> <span data-ttu-id="731db-142">Pēc veiksmīgas atsvaidzināšanas uzņemtos datus var pārskatīt no lapas **Entītijas**.</span><span class="sxs-lookup"><span data-stu-id="731db-142">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="731db-143">Papildinformāciju skatiet rakstā [Entītijas](entities.md).</span><span class="sxs-lookup"><span data-stu-id="731db-143">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="731db-144">Atsvaidzināt datu avotu</span><span class="sxs-lookup"><span data-stu-id="731db-144">Refresh a data source</span></span>

<span data-ttu-id="731db-145">Datu avotus var atsvaidzināt pēc automātiska grafika vai atsvaidzināt manuāli pēc pieprasījuma.</span><span class="sxs-lookup"><span data-stu-id="731db-145">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="731db-146">Apmeklējiet **Administrators** > **Sistēma** > [**Grafiks**](system.md#schedule-tab), lai konfigurētu visu jūsu uzņemto datu avotu plānoto atsvaidzināšanu.</span><span class="sxs-lookup"><span data-stu-id="731db-146">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="731db-147">Lai atsvaidzinātu datu avotu pēc pieprasījuma, veiciet šīs darbības:</span><span class="sxs-lookup"><span data-stu-id="731db-147">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="731db-148">Sadaļā Auditorijas ieskati ejiet uz **Dati** > **Datu avoti**.</span><span class="sxs-lookup"><span data-stu-id="731db-148">In audience insights, go to **Data** > **Data sources**</span></span>

2. <span data-ttu-id="731db-149">Atlasiet vertikālo daudzpunkti blakus atsvaidzināmajam datu avotam un nolaižamajā izvēlnē atlasiet **Atsvaidzināt**.</span><span class="sxs-lookup"><span data-stu-id="731db-149">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the drop-down list.</span></span>

3. <span data-ttu-id="731db-150">Datu avots tagad tiek iespējots manuālai atsvaidzināšanai.</span><span class="sxs-lookup"><span data-stu-id="731db-150">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="731db-151">Datu avota atsvaidzināšana atjauninās gan entitījas shēmu, gan datus visām entitījām, kuras ir norādītas datu avotā.</span><span class="sxs-lookup"><span data-stu-id="731db-151">Refreshing a data source will update both the entity schema and data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="731db-152">Atlasiet **Pārtraukt atsvaidzināšanu**, ja vēlaties atcelt esošu atsvaidzināšanu, un datu avots atgriezīsies pēdējās atsvaidzināšanas statusā.</span><span class="sxs-lookup"><span data-stu-id="731db-152">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="731db-153">Datu avota dzēšana</span><span class="sxs-lookup"><span data-stu-id="731db-153">Delete a data source</span></span>

1. <span data-ttu-id="731db-154">Sadaļā Auditorijas ieskati skatiet **Dati** > **Datu avoti**.</span><span class="sxs-lookup"><span data-stu-id="731db-154">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="731db-155">Atlasiet vertikālo daudzpunkti blakus noņemamajam datu avotam un nolaižamajā izvēlnē atlasiet **Dzēst**.</span><span class="sxs-lookup"><span data-stu-id="731db-155">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the drop-down menu.</span></span>

3. <span data-ttu-id="731db-156">Apstipriniet dzēšanu.</span><span class="sxs-lookup"><span data-stu-id="731db-156">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
