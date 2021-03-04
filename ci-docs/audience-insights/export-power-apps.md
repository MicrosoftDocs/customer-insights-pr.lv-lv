---
title: Power Apps savienotājs
description: Savienošana ar Power Apps un Power Automate.
ms.date: 01/19/2021
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 5a8bbb9a09218d54228589d43c21c8894680b56e
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268925"
---
# <a name="microsoft-power-apps-connector-preview"></a><span data-ttu-id="dda71-103">Microsoft Power Apps savienotājs (priekšskatījums)</span><span class="sxs-lookup"><span data-stu-id="dda71-103">Microsoft Power Apps connector (preview)</span></span>

<span data-ttu-id="dda71-104">Ieviesiet vienotos klientu profilus savās personalizētajās programmās, izmantojot risinājumu Power Apps.</span><span class="sxs-lookup"><span data-stu-id="dda71-104">Bring unified customer profiles into your personalized apps with Power Apps.</span></span>

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a><span data-ttu-id="dda71-105">Power Apps un Dynamics 365 Customer Insights savienošana</span><span class="sxs-lookup"><span data-stu-id="dda71-105">Connect Power Apps and Dynamics 365 Customer Insights</span></span>

<span data-ttu-id="dda71-106">Customer Insights ir viens no daudzajiem [pieejamajiem datu avotiem pakalpojumā Power Apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/working-with-data-sources).</span><span class="sxs-lookup"><span data-stu-id="dda71-106">Customer Insights is one of the many [available sources for data in Power Apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/working-with-data-sources).</span></span>

<span data-ttu-id="dda71-107">Skatiet Power Apps dokumentāciju, lai uzzinātu, kā [programmai pievienot datu savienojumu](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-data-connection).</span><span class="sxs-lookup"><span data-stu-id="dda71-107">Refer to the Power Apps documentation to learn how to [add a data connection to an app](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-data-connection).</span></span> <span data-ttu-id="dda71-108">Ieteicams arī pārskatīt, [kā Power Apps izmanto deleģēšanu, lai apstrādātu lielas datu kopas pamatnes programmās](https://docs.microsoft.com/powerapps/maker/canvas-apps/delegation-overview).</span><span class="sxs-lookup"><span data-stu-id="dda71-108">We recommend you also review [how Power Apps uses delegation to handle large datasets in Canvas apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/delegation-overview).</span></span>

## <a name="available-entities"></a><span data-ttu-id="dda71-109">Pieejamās entītijas</span><span class="sxs-lookup"><span data-stu-id="dda71-109">Available entities</span></span>

<span data-ttu-id="dda71-110">Pēc Customer Insights pievienošanas datu savienojumam varat Power Apps izvēlēties šādas entītijas:</span><span class="sxs-lookup"><span data-stu-id="dda71-110">After adding Customer Insights as a data connection, you can choose the following entities in Power Apps:</span></span>

- <span data-ttu-id="dda71-111">Klients: lai izmantotu datus no [vienotā klienta profila](customer-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="dda71-111">Customer: to use data from the [unified customer profile](customer-profiles.md).</span></span>
- <span data-ttu-id="dda71-112">Vienotā darbība: lai parādītu [darbības laika skalu](activities.md) programmā.</span><span class="sxs-lookup"><span data-stu-id="dda71-112">UnifiedActivity: to display the [activity timeline](activities.md) on the app.</span></span>

## <a name="limitations"></a><span data-ttu-id="dda71-113">Ierobežojumi</span><span class="sxs-lookup"><span data-stu-id="dda71-113">Limitations</span></span>

### <a name="retrievable-entities"></a><span data-ttu-id="dda71-114">Izgūstamas entītijas</span><span class="sxs-lookup"><span data-stu-id="dda71-114">Retrievable entities</span></span>

<span data-ttu-id="dda71-115">Varat izgūt tikai entītijas **Klients**, **Nedefinēta darbība** un **Segmenti**, izmantojot Power Apps savienotāju.</span><span class="sxs-lookup"><span data-stu-id="dda71-115">You can only retrieve the **Customer**, **UnifiedActivity**, and **Segments** entities through the Power Apps connector.</span></span> <span data-ttu-id="dda71-116">Citas entītijas tiek rādītas, jo pamatā esošais savienotājs tās atbalsta, izmantojot trigerus Power Automate.</span><span class="sxs-lookup"><span data-stu-id="dda71-116">Other entities are shown because the underlying connector supports them through triggers in Power Automate.</span></span>  

### <a name="delegation"></a><span data-ttu-id="dda71-117">Deleģēšana</span><span class="sxs-lookup"><span data-stu-id="dda71-117">Delegation</span></span>

<span data-ttu-id="dda71-118">Deleģēšana darbojas entītijai Klients un entītijai Nedefinēta darbība.</span><span class="sxs-lookup"><span data-stu-id="dda71-118">Delegation works for the Customer entity and UnifiedActivity entity.</span></span> 

- <span data-ttu-id="dda71-119">**Klienta** entītijas deleģēšana: Lai šai entītijai izmantotu deleģēšanu, šie lauki ir jāindeksē, izmantojot [Meklēšanas & filtra indeksu](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="dda71-119">Delegation for **Customer** entity: To use delegation for this entity, the fields need to be indexed in [Search & filter index](search-filter-index.md).</span></span>  

- <span data-ttu-id="dda71-120">Deleģēšana **Nedefinēta darbība**: Deleģēšana šai entītijai darbojas tikai laukiem **ActivityId** un **CustomerId**.</span><span class="sxs-lookup"><span data-stu-id="dda71-120">Delegation for **UnifiedActivity**: Delegation for this entity only works for the fields **ActivityId** and **CustomerId**.</span></span>  

- <span data-ttu-id="dda71-121">Papildinformāciju par deleģēšanu skatiet [Power Apps deleģējamās funkcijas un operācijas](https://docs.microsoft.com/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps).</span><span class="sxs-lookup"><span data-stu-id="dda71-121">For more information about delegation, see [Power Apps delegable functions and operations](https://docs.microsoft.com/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps).</span></span> 

## <a name="example-gallery-control"></a><span data-ttu-id="dda71-122">Galerijas vadīklas piemērs</span><span class="sxs-lookup"><span data-stu-id="dda71-122">Example gallery control</span></span>

<span data-ttu-id="dda71-123">Piemēram, varat pievienot klientu profilus [galerijas vadīklai](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-gallery).</span><span class="sxs-lookup"><span data-stu-id="dda71-123">For example, you add customer profiles to a [gallery control](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-gallery).</span></span>

1. <span data-ttu-id="dda71-124">Pievienojiet **Galerijas** vadīklu programmai, ko veidojat.</span><span class="sxs-lookup"><span data-stu-id="dda71-124">Add a **Gallery** control to an app you're building.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="dda71-125">![Galerijas elementa pievienošana](media/connector-powerapps9.png "Galerijas elementa pievienošana")</span><span class="sxs-lookup"><span data-stu-id="dda71-125">![Add a gallery element](media/connector-powerapps9.png "Add a gallery element")</span></span>

1. <span data-ttu-id="dda71-126">Atlasiet **Klientu** kā vienumu datu avotu.</span><span class="sxs-lookup"><span data-stu-id="dda71-126">Select **Customer** as the data source for items.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="dda71-127">![Datu avota atlasīšana](media/choose-datasource-powerapps.png "Datu avota atlasīšana")</span><span class="sxs-lookup"><span data-stu-id="dda71-127">![Select a data source](media/choose-datasource-powerapps.png "Select a data source")</span></span>

1. <span data-ttu-id="dda71-128">Varat mainīt labajā pusē esošo datu paneli, lai atlasītu, kuru entītijas Klients lauku rādīt galerijā.</span><span class="sxs-lookup"><span data-stu-id="dda71-128">You can change the data panel on the right to select which field for the Customer entity to show on the gallery.</span></span>

1. <span data-ttu-id="dda71-129">Ja vēlaties, lai galerijā tiktu rādīts jebkurš lauks no atlasītā klienta, norādiet etiķetes rekvizītu Teksts: **{Name_of_the_gallery}.Selected.{property_name}**</span><span class="sxs-lookup"><span data-stu-id="dda71-129">If you want to show any field from the selected customer on the gallery, fill in the Text property of a label:  **{Name_of_the_gallery}.Selected.{property_name}**</span></span>

    <span data-ttu-id="dda71-130">Piemērs: Gallery1.Selected.address1_city</span><span class="sxs-lookup"><span data-stu-id="dda71-130">Example: Gallery1.Selected.address1_city</span></span>

1. <span data-ttu-id="dda71-131">Lai klientam tiktu parādīta vienota laika skala, pievienojiet elementu Galerija un rekvizītu Vienumi: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**</span><span class="sxs-lookup"><span data-stu-id="dda71-131">To display the unified timeline for a customer, add a Gallery element, and add the Items property: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**</span></span>

    <span data-ttu-id="dda71-132">Piemērs: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)</span><span class="sxs-lookup"><span data-stu-id="dda71-132">Example: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]