---
title: Power Apps savienotājs (priekšskatījums)
description: Savienošana ar Power Apps un Power Automate.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: 8807e82e65ea20d1a7f7dc07552229f377927eed
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196909"
---
# <a name="power-apps-connector-preview"></a>Power Apps savienotājs (priekšskatījums)

Ieviesiet vienotos klientu profilus savās personalizētajās programmās, izmantojot risinājumu Microsoft Power Apps.

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a>Power Apps un Dynamics 365 Customer Insights savienošana

Customer Insights ir viens no daudzajiem [pieejamajiem datu avotiem pakalpojumā Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources).

Skatiet Power Apps dokumentāciju, lai uzzinātu, kā [programmai pievienot datu savienojumu](/powerapps/maker/canvas-apps/add-data-connection). Ieteicams arī pārskatīt, [kā Power Apps izmanto deleģēšanu, lai apstrādātu lielas datu kopas pamatnes programmās](/powerapps/maker/canvas-apps/delegation-overview).

## <a name="available-entities"></a>Pieejamās entītijas

Pēc Customer Insights pievienošanas kā datu savienojumam izvēlieties šādas entītijas:Power Apps

- **Klients**: lai izmantotu datus no [vienotā klienta profila](customer-profiles.md).
- **UnifiedActivity**: lai programmā parādītu [darbību laika grafiku](activities.md).
- **ContactProfile**: lai parādītu klienta kontaktpersonas. Šī entītija ir pieejama tikai Customer Insights vidēs biznesa kontiem.

## <a name="limitations"></a>Ierobežojumi

### <a name="retrievable-entities"></a>Izgūstamas entītijas

Ar savienotāja palīdzību var izgūt tikai entītijas **Klients**, **UnifiedActivity**, **Segmenti** un **ContactProfile** ar Power Apps savienotāju. ContactProfile ir pieejams tikai Customer Insights vidēs biznesa kontiem. Citas entītijas tiek rādītas, jo pamatā esošais savienotājs tās atbalsta, izmantojot trigerus Power Automate.

Jūs varat veikt ne vairāk kā 100 zvanus 60 sekundēs. API galapunktu var izsaukt vairākas reizes, izmantojot parametru $skip. [Uzziniet vairāk par parametru $skip](/connectors/customerinsights/#get-items-from-an-entity).

### <a name="delegation"></a>Deleģēšana

Deleģēšana darbojas entītijai **Klients** un entītijai **UnifiedActivity**.

- Deleģēšana debitora entītijai **: lai izmantotu deleģēšanu šai entītijai, lauki ir jāindeksē meklēšanas un filtrēšanas indeksā**.[...](search-filter-index.md)  
- Deleģēšana **Nedefinēta darbība**: Deleģēšana šai entītijai darbojas tikai laukiem **ActivityId** un **CustomerId**.  
- Deleģēšana **ContactProfile**: šai entītijai deleģēšana darbojas laukiem **ContactId** un **CustomerId**. ContactProfile ir pieejams tikai Customer Insights vidēs biznesa kontiem.

Lai iegūtu papildinformāciju par deleģēšanu, atveriet [Power Apps deleģējamās funkcijas un darbības](/powerapps/maker/canvas-apps/delegation-overview).

## <a name="example-gallery-control"></a>Galerijas vadīklas piemērs

Ja vēlaties, pievienojiet klientu profilus galerijas [vadīklai](/powerapps/maker/canvas-apps/add-gallery).

1. Pievienojiet **Galerijas** vadīklu programmai, ko veidojat.
  
   :::image type="content" source="media/connector-powerapps9.png" alt-text="Galerijas elementa pievienošana.":::

1. Atlasiet **Klientu** kā vienumu datu avotu.

   :::image type="content" source="media/choose-datasource-powerapps.png" alt-text="Datu avota atlasīšana.":::

1. Mainiet datu paneli labajā pusē, lai atlasītu, kuru lauku klienta entītijai rādīt galerijā.

1. Ja vēlaties, lai galerijā tiktu rādīts jebkurš lauks no atlasītā klienta, aizpildiet etiķetes rekvizītu **Teksts**, izmantojot **{Name_of_the_gallery}.Selected.{property_name}**  
    - Piemēram: _Gallery1.Selected.address1_city_

1. Lai tiktu parādīta vienota laika skala klientam, pievienojiet galerijas elementu un rekvizītu **Vienumi**, izmantojot **Filter('UnifiedActivity', CustomerId = {Customer_Id})**  
    - Piemēram:  _Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)_

[!INCLUDE [footer-include](includes/footer-banner.md)]
