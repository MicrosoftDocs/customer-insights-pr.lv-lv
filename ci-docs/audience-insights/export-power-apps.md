---
title: Power Apps savienotājs
description: Savienošana ar Power Apps un Power Automate.
ms.date: 01/19/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: 3fa91553fd50a22ab62b5a2b1e3f13b9483776a8
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598164"
---
# <a name="microsoft-power-apps-connector-preview"></a><span data-ttu-id="82a78-103">Microsoft Power Apps savienotājs (priekšskatījums)</span><span class="sxs-lookup"><span data-stu-id="82a78-103">Microsoft Power Apps connector (preview)</span></span>

<span data-ttu-id="82a78-104">Ieviesiet vienotos klientu profilus savās personalizētajās programmās, izmantojot risinājumu Power Apps.</span><span class="sxs-lookup"><span data-stu-id="82a78-104">Bring unified customer profiles into your personalized apps with Power Apps.</span></span>

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a><span data-ttu-id="82a78-105">Power Apps un Dynamics 365 Customer Insights savienošana</span><span class="sxs-lookup"><span data-stu-id="82a78-105">Connect Power Apps and Dynamics 365 Customer Insights</span></span>

<span data-ttu-id="82a78-106">Customer Insights ir viens no daudzajiem [pieejamajiem datu avotiem pakalpojumā Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources).</span><span class="sxs-lookup"><span data-stu-id="82a78-106">Customer Insights is one of the many [available sources for data in Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources).</span></span>

<span data-ttu-id="82a78-107">Skatiet Power Apps dokumentāciju, lai uzzinātu, kā [programmai pievienot datu savienojumu](/powerapps/maker/canvas-apps/add-data-connection).</span><span class="sxs-lookup"><span data-stu-id="82a78-107">Refer to the Power Apps documentation to learn how to [add a data connection to an app](/powerapps/maker/canvas-apps/add-data-connection).</span></span> <span data-ttu-id="82a78-108">Ieteicams arī pārskatīt, [kā Power Apps izmanto deleģēšanu, lai apstrādātu lielas datu kopas pamatnes programmās](/powerapps/maker/canvas-apps/delegation-overview).</span><span class="sxs-lookup"><span data-stu-id="82a78-108">We recommend you also review [how Power Apps uses delegation to handle large datasets in Canvas apps](/powerapps/maker/canvas-apps/delegation-overview).</span></span>

## <a name="available-entities"></a><span data-ttu-id="82a78-109">Pieejamās entītijas</span><span class="sxs-lookup"><span data-stu-id="82a78-109">Available entities</span></span>

<span data-ttu-id="82a78-110">Pēc Customer Insights pievienošanas datu savienojumam varat Power Apps izvēlēties šādas entītijas:</span><span class="sxs-lookup"><span data-stu-id="82a78-110">After adding Customer Insights as a data connection, you can choose the following entities in Power Apps:</span></span>

- <span data-ttu-id="82a78-111">Klients: lai izmantotu datus no [vienotā klienta profila](customer-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="82a78-111">Customer: to use data from the [unified customer profile](customer-profiles.md).</span></span>
- <span data-ttu-id="82a78-112">Vienotā darbība: lai parādītu [darbības laika skalu](activities.md) programmā.</span><span class="sxs-lookup"><span data-stu-id="82a78-112">UnifiedActivity: to display the [activity timeline](activities.md) on the app.</span></span>

## <a name="limitations"></a><span data-ttu-id="82a78-113">Ierobežojumi</span><span class="sxs-lookup"><span data-stu-id="82a78-113">Limitations</span></span>

### <a name="retrievable-entities"></a><span data-ttu-id="82a78-114">Izgūstamas entītijas</span><span class="sxs-lookup"><span data-stu-id="82a78-114">Retrievable entities</span></span>

<span data-ttu-id="82a78-115">Varat izgūt tikai entītijas **Klients**, **Nedefinēta darbība** un **Segmenti**, izmantojot Power Apps savienotāju.</span><span class="sxs-lookup"><span data-stu-id="82a78-115">You can only retrieve the **Customer**, **UnifiedActivity**, and **Segments** entities through the Power Apps connector.</span></span> <span data-ttu-id="82a78-116">Citas entītijas tiek rādītas, jo pamatā esošais savienotājs tās atbalsta, izmantojot trigerus Power Automate.</span><span class="sxs-lookup"><span data-stu-id="82a78-116">Other entities are shown because the underlying connector supports them through triggers in Power Automate.</span></span>  

### <a name="delegation"></a><span data-ttu-id="82a78-117">Deleģēšana</span><span class="sxs-lookup"><span data-stu-id="82a78-117">Delegation</span></span>

<span data-ttu-id="82a78-118">Deleģēšana darbojas entītijai Klients un entītijai Nedefinēta darbība.</span><span class="sxs-lookup"><span data-stu-id="82a78-118">Delegation works for the Customer entity and UnifiedActivity entity.</span></span> 

- <span data-ttu-id="82a78-119">**Klienta** entītijas deleģēšana: Lai šai entītijai izmantotu deleģēšanu, šie lauki ir jāindeksē, izmantojot [Meklēšanas & filtra indeksu](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="82a78-119">Delegation for **Customer** entity: To use delegation for this entity, the fields need to be indexed in [Search & filter index](search-filter-index.md).</span></span>  

- <span data-ttu-id="82a78-120">Deleģēšana **Nedefinēta darbība**: Deleģēšana šai entītijai darbojas tikai laukiem **ActivityId** un **CustomerId**.</span><span class="sxs-lookup"><span data-stu-id="82a78-120">Delegation for **UnifiedActivity**: Delegation for this entity only works for the fields **ActivityId** and **CustomerId**.</span></span>  

- <span data-ttu-id="82a78-121">Papildinformāciju par deleģēšanu skatiet [Power Apps deleģējamās funkcijas un operācijas](/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps).</span><span class="sxs-lookup"><span data-stu-id="82a78-121">For more information about delegation, see [Power Apps delegable functions and operations](/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps).</span></span> 

## <a name="example-gallery-control"></a><span data-ttu-id="82a78-122">Galerijas vadīklas piemērs</span><span class="sxs-lookup"><span data-stu-id="82a78-122">Example gallery control</span></span>

<span data-ttu-id="82a78-123">Piemēram, varat pievienot klientu profilus [galerijas vadīklai](/powerapps/maker/canvas-apps/add-gallery).</span><span class="sxs-lookup"><span data-stu-id="82a78-123">For example, you add customer profiles to a [gallery control](/powerapps/maker/canvas-apps/add-gallery).</span></span>

1. <span data-ttu-id="82a78-124">Pievienojiet **Galerijas** vadīklu programmai, ko veidojat.</span><span class="sxs-lookup"><span data-stu-id="82a78-124">Add a **Gallery** control to an app you're building.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="82a78-125">![Galerijas elementa pievienošana](media/connector-powerapps9.png "Galerijas elementa pievienošana")</span><span class="sxs-lookup"><span data-stu-id="82a78-125">![Add a gallery element](media/connector-powerapps9.png "Add a gallery element")</span></span>

1. <span data-ttu-id="82a78-126">Atlasiet **Klientu** kā vienumu datu avotu.</span><span class="sxs-lookup"><span data-stu-id="82a78-126">Select **Customer** as the data source for items.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="82a78-127">![Datu avota atlasīšana](media/choose-datasource-powerapps.png "Datu avota atlasīšana")</span><span class="sxs-lookup"><span data-stu-id="82a78-127">![Select a data source](media/choose-datasource-powerapps.png "Select a data source")</span></span>

1. <span data-ttu-id="82a78-128">Varat mainīt labajā pusē esošo datu paneli, lai atlasītu, kuru entītijas Klients lauku rādīt galerijā.</span><span class="sxs-lookup"><span data-stu-id="82a78-128">You can change the data panel on the right to select which field for the Customer entity to show on the gallery.</span></span>

1. <span data-ttu-id="82a78-129">Ja vēlaties, lai galerijā tiktu rādīts jebkurš lauks no atlasītā klienta, norādiet etiķetes rekvizītu Teksts: **{Name_of_the_gallery}.Selected.{property_name}**</span><span class="sxs-lookup"><span data-stu-id="82a78-129">If you want to show any field from the selected customer on the gallery, fill in the Text property of a label:  **{Name_of_the_gallery}.Selected.{property_name}**</span></span>

    <span data-ttu-id="82a78-130">Piemērs: Gallery1.Selected.address1_city</span><span class="sxs-lookup"><span data-stu-id="82a78-130">Example: Gallery1.Selected.address1_city</span></span>

1. <span data-ttu-id="82a78-131">Lai klientam tiktu parādīta vienota laika skala, pievienojiet elementu Galerija un rekvizītu Vienumi: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**</span><span class="sxs-lookup"><span data-stu-id="82a78-131">To display the unified timeline for a customer, add a Gallery element, and add the Items property: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**</span></span>

    <span data-ttu-id="82a78-132">Piemērs: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)</span><span class="sxs-lookup"><span data-stu-id="82a78-132">Example: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]