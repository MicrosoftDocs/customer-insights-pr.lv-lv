---
title: Power Apps savienotājs
description: Savienošana ar Power Apps un Power Automate.
ms.date: 10/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: 985e6c85795fba8ca3063cdffc7f9012e798856a
ms.sourcegitcommit: 5d82e5b808517e0e99fdfdd7e4a4422a5b8ebd5c
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 10/11/2021
ms.locfileid: "7623232"
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
- **ContactProfile**: lai parādītu klienta kontaktpersonas. Šī entītija pašlaik nav saderīga ar auditorijas ieskatu vidi uzņēmumiem.

## <a name="limitations"></a>Ierobežojumi

### <a name="retrievable-entities"></a>Izgūstamas entītijas

Ar savienotāja palīdzību var izgūt tikai entītijas **Klients**, **UnifiedActivity**, **Segmenti** un **ContactProfile** ar Power Apps savienotāju. ContactProfile ir pieejama tikai auditorijas ieskatos uzņēmuma kontiem. Citas entītijas tiek rādītas, jo pamatā esošais savienotājs tās atbalsta, izmantojot trigerus Power Automate.

### <a name="delegation"></a>Deleģēšana

Deleģēšana darbojas entītijai **Klients** un entītijai **UnifiedActivity**. 

- **Klienta** entītijas deleģēšana: Lai šai entītijai izmantotu deleģēšanu, šie lauki ir jāindeksē, izmantojot [Meklēšanas & filtra indeksu](search-filter-index.md).  
- Deleģēšana **Nedefinēta darbība**: Deleģēšana šai entītijai darbojas tikai laukiem **ActivityId** un **CustomerId**.  
- Deleģēšana **ContactProfile**: šai entītijai deleģēšana darbojas laukiem **ContactId** un **CustomerId**. ContactProfile ir pieejama tikai auditorijas ieskatu vidēm uzņēmuma kontiem.

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


[!INCLUDE[footer-include](../includes/footer-banner.md)]
