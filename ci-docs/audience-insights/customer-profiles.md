---
title: Klientu profilu skatīšana
description: Iegūstiet kombinētu skatu ar jūsu apvienotajiem klientu datiem.
ms.date: 12/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: c9adb4d7db74573d0512ae7a68a0e7ab51c994a0
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304613"
---
# <a name="customer-profiles"></a>Klientu profili

Lapā **Klienti** tiek parādīts apvienots klientu skatījums, pamatojoties uz profila datiem, kas apkopoti no [visiem datu avotiem](data-sources.md). Klientu profili ir pieejami, kad [izveidojat vienotu klienta entītiju](data-unification.md). Pārliecinieties, vai esat pabeidzis datu apvienošanas procesu, lai iegūtu plašākus klientu skatus. Šī lapa arī sniedz iespēju meklēt klientus.

Klienti var būt personas vai organizācijas (priekšskatījums). Katram klientam vai organizācijas profilam tiek piešķirts elements. Atlasiet elementu, lai skatītu papildinformāciju par noteiktu klientu vai organizāciju. Lapas apakšdaļā izmantojiet lappušu numerācijas vadīklas, lai skatītu papildu ierakstus.

> [!div class="mx-imgBorder"] 
> ![B2C klienta profils](media/profiles-customers.png "B2C klienta profili")

Organizācijas (priekšskatījums)
> [!div class="mx-imgBorder"] 
> ![B2B klienta profils](media/profile-customers-b2b.png "B2B klienta profili")

> [!NOTE]
> Ja, navigācijas rūtī atlasot **Klienti**, neredzat rūtis, jūsu administratoram ir [jādefinē vismaz viens meklējams atribūts](search-filter-index.md) **Meklēšanas un filtrēšanas indeksā**.

## <a name="search-for-customers"></a>Meklēt klientus

Meklējiet klientus, meklēšanas lodziņā ievadot vārdu vai citu atribūtu. Meklēšana darbojas tikai klienta profila entītijā, kas ir izveidota datu apvienošanas procesā.

Kā administrators varat konfigurēt meklēšanas atribūtus, izmantojot **Meklēšanas un filtrēšanas rādītāja** lapu. Papildinformāciju skatiet sadaļā [Pārvaldīt meklēšanas un filtra rādītāju](search-filter-index.md).

## <a name="filter-customers"></a>Filtrēt klientus

Klientus var filtrēt pēc Klienta profila entītijas laukiem. Līdzīgi meklēšanai — jūsu administratoram vispirms ir jādefinē lauki kā filtrējami, izmantojot lapu **Meklēšanas un filtra rādītājs**.

1. Lapā **Klienti** atlasiet **Filtrs**.

2. Atzīmējiet lodziņus blakus atribūtiem, pēc kuriem vēlaties filtrēt klientus.

   > [!div class="mx-imgBorder"] 
   > ![Klientu profili](media/profiles-customers3.png "Klientu profili")

3. Noņemiet filtrus, atlasot lapā **Klienti** **Notīrīt filtrus**.

##  <a name="customer-details-page"></a>Detalizēta informācija par klientu

Atlasiet jebkuru no klientu elementiem, lai atvērtu **Klientu detalizētās informācijas lapu**. Šajā skatā ir ietverta vienota informācija par atlasīto klientu.

Detalizēta informācija par klientu:

-   **Klienta profila elements**: Šis elements rāda dažādas vērtības no vienotā klienta profila entītijas. Šī detalizētā informācija var ietvert e-pasta adresi, nosaukumu, pilsētu un citus datus. 

-   **Iespējamās intereses, potenciālie zīmoli**: Rāda, ja esat konfigurējis pirmās puses bagātināšanu. Tas ataino iespējamas intereses un zīmolu radniecību, kāda varētu būt klientam ar šim klientam līdzīgu profilu. Papildinformāciju skatiet tēmā [Klientu profilu bagātināšana ar zīmolu un interešu radniecības datiem](enrichment-microsoft.md).

-   **Pasākumi**: Parāda, vai esat konfigurējis vienu vai vairākus noteikta tipa pasākumus: klientu atribūta mērvienības. Tie iekļauj aprēķinātos KPI ap saviem klientiem atsevišķā klientu līmenī. Papildinformāciju skatiet tēmā [Pasākumu definēšana un pārvaldīšana](measures.md).

-   **Darbību laika skala**: Rāda, vai ir konfigurētas darbības. Laika skalas skats ietver šī klienta hronoloģiski kārtotās darbības, sākot ar pēdējo darbību. Papildinformācijai skatiet [Klientu darbības](activities.md).

Atlasiet **Atpakaļ pie klientiem**, lai atgrieztos klientu meklēšanas lapā.

## <a name="next-steps"></a>Nākamās darbības

[Pievienojiet papildu datu avotus](data-sources.md) vai [izveidojiet klientu segmentus](segments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
