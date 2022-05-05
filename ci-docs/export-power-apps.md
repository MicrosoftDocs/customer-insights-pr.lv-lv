---
title: Power Apps savienotājs
description: Savienošana ar Power Apps un Power Automate.
ms.date: 10/01/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: e99d7d4f231eb2ade67f27c9e52c61af3a21b99d
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643949"
---
# <a name="microsoft-power-apps-connector-preview"></a>Microsoft Power Apps savienotājs (priekšskatījums)

Ieviesiet vienotos klientu profilus savās personalizētajās programmās, izmantojot risinājumu Power Apps.

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a>Power Apps un Dynamics 365 Customer Insights savienošana

Customer Insights ir viens no daudzajiem [pieejamajiem datu avotiem pakalpojumā Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources).

Skatiet Power Apps dokumentāciju, lai uzzinātu, kā [programmai pievienot datu savienojumu](/powerapps/maker/canvas-apps/add-data-connection). Ieteicams arī pārskatīt, [kā Power Apps izmanto deleģēšanu, lai apstrādātu lielas datu kopas pamatnes programmās](/powerapps/maker/canvas-apps/delegation-overview).

## <a name="available-entities"></a>Pieejamās entītijas

Pēc Customer Insights pievienošanas datu savienojumam varat Power Apps izvēlēties šādas entītijas:

- **Klients**: lai izmantotu datus no [vienotā klienta profila](customer-profiles.md).
- **UnifiedActivity**: lai programmā parādītu [darbību laika grafiku](activities.md).
- **ContactProfile**: lai parādītu klienta kontaktpersonas. Šī entītija ir pieejama tikai Customer Insights vidēs biznesa kontiem.

## <a name="limitations"></a>Ierobežojumi

### <a name="retrievable-entities"></a>Izgūstamas entītijas

Ar savienotāja palīdzību var izgūt tikai entītijas **Klients**, **UnifiedActivity**, **Segmenti** un **ContactProfile** ar Power Apps savienotāju. ContactProfile ir pieejams tikai customer insights piemērā biznesa kontiem. Citas entītijas tiek rādītas, jo pamatā esošais savienotājs tās atbalsta, izmantojot trigerus Power Automate.

Jūs varat veikt ne vairāk kā 100 zvanus 60 sekundēs. API galapunktu var izsaukt vairākas reizes, izmantojot parametru $skip. [Uzziniet vairāk par parametru $skip](/connectors/customerinsights/#get-items-from-an-entity).

### <a name="delegation"></a>Deleģēšana

Deleģēšana darbojas entītijai **Klients** un entītijai **UnifiedActivity**. 

- **Klienta** entītijas deleģēšana: Lai šai entītijai izmantotu deleģēšanu, šie lauki ir jāindeksē, izmantojot [Meklēšanas & filtra indeksu](search-filter-index.md).  
- Deleģēšana **Nedefinēta darbība**: Deleģēšana šai entītijai darbojas tikai laukiem **ActivityId** un **CustomerId**.  
- Deleģēšana **ContactProfile**: šai entītijai deleģēšana darbojas laukiem **ContactId** un **CustomerId**. ContactProfile ir pieejams tikai Customer Insights vidēs biznesa kontiem.

Lai iegūtu papildinformāciju par deleģēšanu, atveriet [Power Apps deleģējamās funkcijas un darbības](/powerapps/maker/canvas-apps/delegation-overview). 

## <a name="example-gallery-control"></a>Galerijas vadīklas piemērs

Klientu profilus var pievienot [galerijas vadīklai](/powerapps/maker/canvas-apps/add-gallery).

1. Pievienojiet **Galerijas** vadīklu programmai, ko veidojat.

    > [!div class="mx-imgBorder"]
    > ![Galerijas elementa pievienošana.](media/connector-powerapps9.png "Pievienojiet galerijas elementu.")

2. Atlasiet **Klientu** kā vienumu datu avotu.

    > [!div class="mx-imgBorder"]
    > ![Datu avota atlasīšana.](media/choose-datasource-powerapps.png "Atlasiet datu avotu.")

3. Varat mainīt labajā pusē esošo datu paneli, lai atlasītu, kuru entītijas Klients lauku rādīt galerijā.

4. Ja vēlaties, lai galerijā tiktu rādīts jebkurš lauks no atlasītā klienta, aizpildiet etiķetes rekvizītu **Teksts**, izmantojot **{Name_of_the_gallery}.Selected.{property_name}**  
    - Piemēram: _Gallery1.Selected.address1_city_

5. Lai tiktu parādīta vienota laika skala klientam, pievienojiet galerijas elementu un rekvizītu **Vienumi**, izmantojot **Filter('UnifiedActivity', CustomerId = {Customer_Id})**  
    - Piemēram:  _Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)_


[!INCLUDE [footer-include](includes/footer-banner.md)]
