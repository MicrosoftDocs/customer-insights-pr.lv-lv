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
# <a name="microsoft-power-apps-connector-preview"></a>Microsoft Power Apps savienotājs (priekšskatījums)

Ieviesiet vienotos klientu profilus savās personalizētajās programmās, izmantojot risinājumu Power Apps.

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a>Power Apps un Dynamics 365 Customer Insights savienošana

Customer Insights ir viens no daudzajiem [pieejamajiem datu avotiem pakalpojumā Power Apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/working-with-data-sources).

Skatiet Power Apps dokumentāciju, lai uzzinātu, kā [programmai pievienot datu savienojumu](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-data-connection). Ieteicams arī pārskatīt, [kā Power Apps izmanto deleģēšanu, lai apstrādātu lielas datu kopas pamatnes programmās](https://docs.microsoft.com/powerapps/maker/canvas-apps/delegation-overview).

## <a name="available-entities"></a>Pieejamās entītijas

Pēc Customer Insights pievienošanas datu savienojumam varat Power Apps izvēlēties šādas entītijas:

- Klients: lai izmantotu datus no [vienotā klienta profila](customer-profiles.md).
- Vienotā darbība: lai parādītu [darbības laika skalu](activities.md) programmā.

## <a name="limitations"></a>Ierobežojumi

### <a name="retrievable-entities"></a>Izgūstamas entītijas

Varat izgūt tikai entītijas **Klients**, **Nedefinēta darbība** un **Segmenti**, izmantojot Power Apps savienotāju. Citas entītijas tiek rādītas, jo pamatā esošais savienotājs tās atbalsta, izmantojot trigerus Power Automate.  

### <a name="delegation"></a>Deleģēšana

Deleģēšana darbojas entītijai Klients un entītijai Nedefinēta darbība. 

- **Klienta** entītijas deleģēšana: Lai šai entītijai izmantotu deleģēšanu, šie lauki ir jāindeksē, izmantojot [Meklēšanas & filtra indeksu](search-filter-index.md).  

- Deleģēšana **Nedefinēta darbība**: Deleģēšana šai entītijai darbojas tikai laukiem **ActivityId** un **CustomerId**.  

- Papildinformāciju par deleģēšanu skatiet [Power Apps deleģējamās funkcijas un operācijas](https://docs.microsoft.com/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps). 

## <a name="example-gallery-control"></a>Galerijas vadīklas piemērs

Piemēram, varat pievienot klientu profilus [galerijas vadīklai](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-gallery).

1. Pievienojiet **Galerijas** vadīklu programmai, ko veidojat.

> [!div class="mx-imgBorder"]
> ![Galerijas elementa pievienošana](media/connector-powerapps9.png "Galerijas elementa pievienošana")

1. Atlasiet **Klientu** kā vienumu datu avotu.

    > [!div class="mx-imgBorder"]
    > ![Datu avota atlasīšana](media/choose-datasource-powerapps.png "Datu avota atlasīšana")

1. Varat mainīt labajā pusē esošo datu paneli, lai atlasītu, kuru entītijas Klients lauku rādīt galerijā.

1. Ja vēlaties, lai galerijā tiktu rādīts jebkurš lauks no atlasītā klienta, norādiet etiķetes rekvizītu Teksts: **{Name_of_the_gallery}.Selected.{property_name}**

    Piemērs: Gallery1.Selected.address1_city

1. Lai klientam tiktu parādīta vienota laika skala, pievienojiet elementu Galerija un rekvizītu Vienumi: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**

    Piemērs: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)


[!INCLUDE[footer-include](../includes/footer-banner.md)]