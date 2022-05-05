---
title: Klientu profilu skatīšana
description: Iegūstiet kombinētu skatu ar jūsu apvienotajiem klientu datiem.
ms.date: 09/30/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
searchScope:
- ci-customers-page
- ci-customer-card
- ci-activities
- ci-activities-wizard
- customerInsights
ms.openlocfilehash: 45ef6abcd612178a097569825e32ff9ac779de01
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643075"
---
# <a name="customer-profiles"></a>Klientu profili

Lapā **Klienti** tiek rādīts jūsu vienoto klientu profilu apvienotais skats. Klientu profili ir pieejami, tiklīdz [esat izveidojis vienoto klienta entītiju](data-unification.md). Šajā lapā varat meklēt klientus un definēt meklējumu indeksu.

Klienti var būt fiziskas personas vai organizācijas. Katram klienta profilam tiek norādīts elements. Lai iegūtu vairāk ierakstu, izmantojiet lapdales vadīklas. Šajā kartē tiek parādīti entītijas *Klients* lauki, kā definēts **Meklēšanas un filtra indeksā**. Katras kartes lauku secību izvēlas sistēma.

Atlasiet elementu, lai atlasītā klienta datus skatītu īpašā lapā [Klienta informācijas detaļu lapa](customer-profiles.md#customer-details-page).

> [!div class="mx-imgBorder"] 
> ![Klientu lapa, kurā parādīti rezultātu elementi](media/customers-page-result-tiles-B2C.png "Klientu lapa, kurā parādīti rezultātu elementi")

> [!NOTE]
> Ja elementi nav redzami, navigācijas rūtī atlasot **Klientus**, administratoram ir [jādefinē vismaz viens meklējams atribūts](search-filter-index.md)**Meklēšanas un filtra indeksā**.

## <a name="search-for-customers"></a>Meklēt klientus

Meklējiet klientus, meklēšanas lodziņā ievadot vārdu vai citu atribūtu. Meklēšana darbojas tikai _Klienta_ entītijā, kas izveidota datu unificēšanas procesā.

Kā administrators varat konfigurēt meklēšanas atribūtus, izmantojot **Meklēšanas un filtrēšanas rādītāja** lapu. Lai iegūtu papildinformāciju, dodieties uz [Meklēšanas un filtra indeksa pārvaldība](search-filter-index.md).

## <a name="filter-customers"></a>Filtrēt klientus

Klientus var filtrēt pēc _Klienta_ entītijas laukiem. Līdzīgi meklēšanai — jūsu administratoram vispirms ir jādefinē lauki kā filtrējami, izmantojot lapu **Meklēšanas un filtra rādītājs**.

1. Lapā **Klienti** atlasiet **Rādīt filtrus**.

1. Atzīmējiet lodziņus blakus atribūtiem, pēc kuriem vēlaties filtrēt klientus.

1. Noņemiet filtrus, atlasot lapā **Klienti** **Notīrīt filtrus**.

## <a name="customer-details-page"></a>Detalizēta informācija par klientu

Atlasiet jebkuru no klientu elementiem, lai atvērtu **Klientu detalizētās informācijas lapu**. Šajā skatā ir ietverta vienota informācija par atlasīto klientu. Detalizēta informācija par klientu ietver šādu saturu:

**Klienta profila elements**: šajā elementā tiek parādītas atšķirīgas vērtības no vienotās _Klienta_ entītijas. Ja laukam nav vērtības atlasītajam klienta profilam, tas netiks rādīts. Elements ir strukturēts sadaļās:  
  - Pirmajā sadaļā ir redzama iepriekš definēta lauku kopa, kam seko visi lauki, kas veido daļu no meklēšanas un filtra indeksa. Visi ar adresēm saistītie lauki tiek apvienoti vienā rindā, ja profilā ir šādi lauki. 
  - **Šī klienta kontaktpersonas**: biznesa uzņēmumu vidēs visas ar šo klientu saistītās kontaktpersonas būs redzamas otrajā sadaļā. Katra kontaktpersona tiek parādīta ar to laukiem. Tukši lauki ir paslēpti.
  - **Papildu lauki**: rāda atlasītā klienta pārējos laukus, izņemot ID. 
  - **ID**: uzskaita visus ID ar to atbilstošo entītijas nosaukumu. Laukus identificē kā ID pēc to semantikas, kas tos kategorizē tādus.

**Darbību laika grafiks**: rāda datus, ja ir konfigurētas darbības. Laika skalas skatā ir hronoloģiskā secībā sakārtotas atlasītā klienta darbības, sākot ar visjaunāko darbību. Lai iegūtu papildinformāciju, dodieties uz [Klientu darbības](activities.md).

**Ieskati**:  
  - **Pasākumi**: rāda, ja ir konfigurēti viens vai vairāki klienta atribūtu pasākumi. Tie iekļauj aprēķinātos KPI ap saviem klientiem atsevišķā klientu līmenī. Lai iegūtu papildinformāciju, dodieties uz [Pasākumu definēšana un pārvalde](measures.md).

  - **Potenciālās intereses, potenciālie zīmoli**: rāda, vai esat konfigurējis zīmola vai ieinteresētības bagātinātāju. Tas attiecas uz iespējamām interesēm un interesēm attiecībā uz zīmoliem, kas balstīti uz citiem klientiem, kuru profils ir līdzīgs atlasītajam klienta profilam. Lai iegūtu papildinformāciju, atveriet sadaļu [Klientu profilu bagātināšana ar zīmolu un interesēm](enrichment-microsoft.md).

Lai atgrieztos klientu meklēšanas lapā, atlasiet **Atpakaļ pie klientiem**.

## <a name="next-steps"></a>Nākamās darbības

[Pievienojiet vēl datu avotus](data-sources.md), [bagātināt vienotos profilus](enrichment-hub.md) vai [izveidojiet segmentus](segments.md), lai strādātu ar vienoto klientu profiliem citās lietojumprogrammās.


[!INCLUDE [footer-include](includes/footer-banner.md)]
