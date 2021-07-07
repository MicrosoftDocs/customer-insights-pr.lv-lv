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
ms.openlocfilehash: 54dd7b629d4b4e7f640b932b0f9246e0602f46bd
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304705"
---
# <a name="data-sources-overview"></a><span data-ttu-id="9765d-103">Datu avotu pārskats</span><span class="sxs-lookup"><span data-stu-id="9765d-103">Data sources overview</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="9765d-104">Auditorijas ieskatus Dynamics 365 Customer Insights var savienot ar datiem no plašas avotu kopas.</span><span class="sxs-lookup"><span data-stu-id="9765d-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="9765d-105">Pieslēgšanos datu avotam bieži vien dēvē par *datu uzņemšanas* procesu.</span><span class="sxs-lookup"><span data-stu-id="9765d-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="9765d-106">Pēc datu uzņemšanas varat tos [apvienot](data-unification.md) un veikt ar tiem darbības.</span><span class="sxs-lookup"><span data-stu-id="9765d-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="9765d-107">Pievienot datu avotu</span><span class="sxs-lookup"><span data-stu-id="9765d-107">Add a data source</span></span>

<span data-ttu-id="9765d-108">Skatiet detalizētus rakstus, kā pievienot datu avotu atkarībā no izvēlētās opcijas.</span><span class="sxs-lookup"><span data-stu-id="9765d-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="9765d-109">Datu avotu varat pievienot trīs galvenajos veidos:</span><span class="sxs-lookup"><span data-stu-id="9765d-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="9765d-110">Izmantojot daudzos Power Query savienotājus</span><span class="sxs-lookup"><span data-stu-id="9765d-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="9765d-111">No Common Data Model mapes</span><span class="sxs-lookup"><span data-stu-id="9765d-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="9765d-112">No sava Microsoft Dataverse ezera</span><span class="sxs-lookup"><span data-stu-id="9765d-112">From your own Microsoft Dataverse lake</span></span>](connect-common-data-service-lake.md)

## <a name="add-data-from-on-premises-data-sources"></a><span data-ttu-id="9765d-113">Datu pievienošana no lokālajiem datu avotiem</span><span class="sxs-lookup"><span data-stu-id="9765d-113">Add data from on-premises data sources</span></span>

<span data-ttu-id="9765d-114">Datu pievienošana no lokālajiem datu avotiem auditorijas ieskatos tiek atbalstīta, balstoties uz Microsoft Power Platform datu plūsmām.</span><span class="sxs-lookup"><span data-stu-id="9765d-114">Ingesting data from on-premises data sources in audience insights is supported based on Microsoft Power Platform dataflows.</span></span> <span data-ttu-id="9765d-115">Datu plūsmas var iespējot risinājumā Customer Insights, [nodrošinot Microsoft Dataverse vides URL](manage-environments.md#create-an-environment-in-an-existing-organization), kad tiek iestatīta vide.</span><span class="sxs-lookup"><span data-stu-id="9765d-115">Dataflows can be enabled in Customer Insights by [providing the Microsoft Dataverse environment URL](manage-environments.md#create-an-environment-in-an-existing-organization) when setting up the environment.</span></span>

<span data-ttu-id="9765d-116">Datu avoti, kuri tiek izveidoti pēc saistīšanas ar Dataverse vidi ar Customer Insights, pēc noklusējuma izmantos [Power Platform datu plūsmas](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365).</span><span class="sxs-lookup"><span data-stu-id="9765d-116">Data sources that are created after associating a Dataverse environment with Customer Insights will use [Power Platform dataflows](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) by default.</span></span> <span data-ttu-id="9765d-117">Datu plūsmas atbalsta lokālo savienojamību, izmantojot datu vārtejas.</span><span class="sxs-lookup"><span data-stu-id="9765d-117">Dataflows support on-premises connectivity using the data gateway.</span></span> <span data-ttu-id="9765d-118">Noņemiet un no jauna izveidojiet datu avotus, kuri pastāvēja, pirms Dataverse vide tika saistīta, lai [lietotu lokālās datu vārtejas](/data-integration/gateway/service-gateway-app.md).</span><span class="sxs-lookup"><span data-stu-id="9765d-118">Remove and recreate data sources that existed before a Dataverse environment was associated to [use the on-premises data gateways](/data-integration/gateway/service-gateway-app.md).</span></span>

<span data-ttu-id="9765d-119">Datu vārtejas no esošās Power BI vai Power Apps vides būs redzama, un to varat atkārtoti izmantot risinājumā Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="9765d-119">Data gateways from an existing Power BI or Power Apps environment will be visible and you can reuse in Customer Insights.</span></span> <span data-ttu-id="9765d-120">Datu avotu lapā ir redzamas saites, kas ļauj pāriet uz Microsoft Power Platform vidi, kurā varat skatīt un konfigurēt lokālās datu vārtejas.</span><span class="sxs-lookup"><span data-stu-id="9765d-120">The data sources page shows links to go to the Microsoft Power Platform environment where you can view and configure on-premises data gateways.</span></span>

## <a name="review-ingested-data"></a><span data-ttu-id="9765d-121">Uzņemto datu pārskatīšana</span><span class="sxs-lookup"><span data-stu-id="9765d-121">Review ingested data</span></span>

<span data-ttu-id="9765d-122">Jūs redzēsit katra uzņemtā datu avota nosaukumu, tā statusu un pēdējo reizi, kad dati tika atsvaidzināti no šī avota.</span><span class="sxs-lookup"><span data-stu-id="9765d-122">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="9765d-123">Datu avotu sarakstu var kārtot pēc katras kolonnas.</span><span class="sxs-lookup"><span data-stu-id="9765d-123">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="9765d-124">![Pievienotie datu avoti](media/configure-data-datasource-added.png "Pievienotie datu avoti")</span><span class="sxs-lookup"><span data-stu-id="9765d-124">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="9765d-125">Statuss</span><span class="sxs-lookup"><span data-stu-id="9765d-125">Status</span></span>  |<span data-ttu-id="9765d-126">Apraksts</span><span class="sxs-lookup"><span data-stu-id="9765d-126">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="9765d-127">Veiksmīgi</span><span class="sxs-lookup"><span data-stu-id="9765d-127">Successful</span></span>   |<span data-ttu-id="9765d-128">Datu avots tika veiksmīgi paņemts, ja ir minēts laiks kolonnā **Atsvaidzināts**.</span><span class="sxs-lookup"><span data-stu-id="9765d-128">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="9765d-129">Nav sākts</span><span class="sxs-lookup"><span data-stu-id="9765d-129">Not started</span></span>   |<span data-ttu-id="9765d-130">Datu avots nesatur datus, kas ir uzņemti vai vēl ir melnraksta režīmā.</span><span class="sxs-lookup"><span data-stu-id="9765d-130">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="9765d-131">Notiek atsvaidzināšana</span><span class="sxs-lookup"><span data-stu-id="9765d-131">Refreshing</span></span>    |<span data-ttu-id="9765d-132">Notiek datu uzņemšana.</span><span class="sxs-lookup"><span data-stu-id="9765d-132">Data ingestion is in progress.</span></span> <span data-ttu-id="9765d-133">Šo darbību varat atcelt, kolonnā **Darbības** atlasot **Apturēt atsvaidzināšanu**.</span><span class="sxs-lookup"><span data-stu-id="9765d-133">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="9765d-134">Apturot datu avota atsvaidzināšanu, tas atkal kļūs tāds pats kā pēdējās atsvaidzināšanas brīdī.</span><span class="sxs-lookup"><span data-stu-id="9765d-134">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="9765d-135">Neizdevās</span><span class="sxs-lookup"><span data-stu-id="9765d-135">Failed</span></span>     |<span data-ttu-id="9765d-136">Veicot datu uzņemšanu, radās kļūdas.</span><span class="sxs-lookup"><span data-stu-id="9765d-136">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="9765d-137">Atlasiet vērtību jebkura datu avoti kolonnā **Statuss**, lai pārskatītu papildinformāciju.</span><span class="sxs-lookup"><span data-stu-id="9765d-137">Select the value in the **Status** column of any data source to review more details.</span></span> <span data-ttu-id="9765d-138">Rūtī **Detalizēta informācija** izvērsiet **Datu avoti**.</span><span class="sxs-lookup"><span data-stu-id="9765d-138">In the **Progress details** pane, expand **Data sources**.</span></span> <span data-ttu-id="9765d-139">Atlasiet **Skatīt detalizētu informāciju** papildu informācijai par atsvaidzināšanas statusu, ieskaitot kļūdas detaļas un pakārtotā procesa atjauninājumus.</span><span class="sxs-lookup"><span data-stu-id="9765d-139">Select **See details** for more information about the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="9765d-140">Datu ielāde var aizņemt laiku.</span><span class="sxs-lookup"><span data-stu-id="9765d-140">Loading data can take time.</span></span> <span data-ttu-id="9765d-141">Pēc veiksmīgas atsvaidzināšanas uzņemtos datus var pārskatīt no lapas **Entītijas**.</span><span class="sxs-lookup"><span data-stu-id="9765d-141">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="9765d-142">Papildinformāciju skatiet rakstā [Entītijas](entities.md).</span><span class="sxs-lookup"><span data-stu-id="9765d-142">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="9765d-143">Atsvaidzināt datu avotu</span><span class="sxs-lookup"><span data-stu-id="9765d-143">Refresh a data source</span></span>

<span data-ttu-id="9765d-144">Datu avotus var atsvaidzināt pēc automātiska grafika vai atsvaidzināt manuāli pēc pieprasījuma.</span><span class="sxs-lookup"><span data-stu-id="9765d-144">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="9765d-145">Apmeklējiet **Administrators** > **Sistēma** > [**Grafiks**](system.md#schedule-tab), lai konfigurētu visu jūsu uzņemto datu avotu plānoto atsvaidzināšanu.</span><span class="sxs-lookup"><span data-stu-id="9765d-145">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="9765d-146">Lai atsvaidzinātu datu avotu pēc pieprasījuma, veiciet šīs darbības:</span><span class="sxs-lookup"><span data-stu-id="9765d-146">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="9765d-147">Sadaļā Auditorijas ieskati skatiet **Dati** > **Datu avoti**.</span><span class="sxs-lookup"><span data-stu-id="9765d-147">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="9765d-148">Nolaižamajā izvēlnes sarakstā atlasiet vertikālās līknes blakus datu avotam, kuru vēlaties atsvaidzināt un atlasiet **Atsvaidzināt**.</span><span class="sxs-lookup"><span data-stu-id="9765d-148">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the dropdown list.</span></span>

3. <span data-ttu-id="9765d-149">Datu avots tagad tiek iespējots manuālai atsvaidzināšanai.</span><span class="sxs-lookup"><span data-stu-id="9765d-149">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="9765d-150">Datu avota atsvaidzināšana atjauninās gan entitījas shēmu, gan datus visām entitījām, kuras ir norādītas datu avotā.</span><span class="sxs-lookup"><span data-stu-id="9765d-150">Refreshing a data source will update both the entity schema and data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="9765d-151">Atlasiet **Pārtraukt atsvaidzināšanu**, ja vēlaties atcelt esošu atsvaidzināšanu, un datu avots atgriezīsies pēdējās atsvaidzināšanas statusā.</span><span class="sxs-lookup"><span data-stu-id="9765d-151">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="9765d-152">Datu avota dzēšana</span><span class="sxs-lookup"><span data-stu-id="9765d-152">Delete a data source</span></span>

1. <span data-ttu-id="9765d-153">Sadaļā Auditorijas ieskati skatiet **Dati** > **Datu avoti**.</span><span class="sxs-lookup"><span data-stu-id="9765d-153">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="9765d-154">Nolaižamajā izvēlnē atlasiet vertikālās līknes blakus datu avotam, kuru vēlaties noņemt un atlasiet **Dzēst**.</span><span class="sxs-lookup"><span data-stu-id="9765d-154">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the dropdown menu.</span></span>

3. <span data-ttu-id="9765d-155">Apstipriniet dzēšanu.</span><span class="sxs-lookup"><span data-stu-id="9765d-155">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
