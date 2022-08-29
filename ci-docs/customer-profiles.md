---
title: Klientu profilu skatīšana
description: Savu vienoto klientu datu skatīšana, tostarp izmantojot meklēšanu un filtrēšanu
ms.date: 06/08/2022
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
ms.openlocfilehash: 0c8edfd8f45ce7770d568811df2b38be1b04e73a
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 08/16/2022
ms.locfileid: "9303792"
---
# <a name="view-customer-profiles"></a>Klientu profilu skatīšana

Klientu profili ir pieejami, kad esat [izveidojis vienotu *klienta* entītiju](data-unification.md). Jūsu vienoto klientu profilu apvienotais skats tiek rādīts **lapā Klienti**. Klienti var būt fiziskas personas vai organizācijas.

Dodieties uz **lapu Klienti**, lai skatītu savus klientus un viņu profilus. Katram klienta profilam tiek norādīts elements. Lai iegūtu vairāk ierakstu, izmantojiet lapdales vadīklas. Šajā kartē tiek parādīti entītijas *Klients* lauki, kā definēts **Meklēšanas un filtra indeksā**. Katras kartes lauku secību izvēlas sistēma.

> [!NOTE]
> Ja, atlasot Vienumus, **neredzat elementus, administratoram ir jādefinē** vismaz viens meklējams atribūts [meklēšanas un filtrēšanas indeksā](search-filter-index.md)**.**

:::image type="content" source="media/customers-page-result-tiles-B2C.png" alt-text="Klientu lapa, kurā redzami rezultātu elementi.":::

Atlasiet kādu no šīm darbībām:
- [Klienta informācijas skatīšana](#view-customer-details)
- [Meklēšanas un filtra indeksa](search-filter-index.md) pārvaldība (tikai administratoriem)
- [Filtrēt klientus](#filter-customers)
- **Karšu** vai **sakļaušanas karšu** izvēršana, lai izvērstu vai sakļautu informāciju, kas tiek rādīta klienta elementā
- **Kārtošana pēc** noteikta atribūta
- [Meklēt klientus](#search-for-customers)

  > [!NOTE]
  > Lai izmantotu meklēšanu un filtrēšanu, administratoram ir jākonfigurē meklējamie atribūti un jādefinē filtrējamie lauki, izmantojot meklēšanas un filtrēšanas indeksu.

## <a name="search-for-customers"></a>Meklēt klientus

Meklējiet klientus, ievadot vārdu vai kādu citu atribūtu sadaļā **Meklēt klientus**. Meklējamos atribūtus definē administrators, un tie nāk no vienotās *Klienta* entītijas.

> [!NOTE]
> **Virkne** ir vienīgais datu tips, kas ir iekļauts meklēšanā. Izmantojiet to **lapas Klienti laukā Meklēt klientus**, lai meklētu klientus.

## <a name="filter-customers"></a>Filtrēt klientus

Filtrējiet klientus pēc klienta *entītijas* laukiem. Filtrējamos laukus definē administrators.

1. **Lapā Klienti** atlasiet **Rādīt filtrus**. Tiek parādīta rūts Filtrs.

1. Atzīmējiet lodziņus blakus atribūtiem, pēc kuriem vēlaties filtrēt klientus.

1. Noņemiet visus filtrus, atlasot **Notīrīt filtrus** vai notīriet izvēles rūtiņu blakus atlasītajam atribūtam.

1. Atlasiet **Paslēpt filtrus**, lai aizvērtu filtra rūti.

1. Lai filtra rezultātus saglabātu kā segmentu, atlasiet [Saglabāt filtrus kā segmentu.](segments.md)**·**
   1. Ievadiet segmenta nosaukumu.
   1. Atlasiet **Saglabāt**, lai saglabātu segmentu.
   1. Izvēlieties, vai palaist segmentu tūlīt, atlasot **Aktivizēt** vai palaist to **vēlāk**.

## <a name="view-customer-details"></a>Klienta informācijas skatīšana

**Lapā Klienti** atlasiet klienta elementu, lai skatītu detalizētu informāciju par atlasīto klientu.

:::image type="content" source="media/customers-details-B2C.png" alt-text="Klienta informācijas lapa.":::

Detalizēta informācija par klientu:

**Klienta profila elementā** tiek rādītas no vienotās *klienta* entītijas atšķirīgas vērtības. Ja laukam nav atlasītā klienta profila vērtības, tas netiks rādīts, izņemot adreses lauku. Elements ir strukturēts sadaļās:

- Pirmajā sadaļā ir redzama iepriekš definēta lauku kopa, kam seko visi lauki, kas veido daļu no meklēšanas un filtra indeksa. Visi ar adresēm saistītie lauki tiek apvienoti vienā rindā, kas tiek rādīta pat tad, ja profilā nav adreses informācijas.
- **Kontaktpersonas šim klientam** tiek rādītas biznesa kontu vidēs (no B līdz B). Katra kontaktpersona tiek parādīta ar to laukiem. Tukši lauki ir paslēpti.
- **Papildu laukos** tiek rādīti atlasītā klienta atlikušie lauki, izņemot ID.
- **ID ir** uzskaitīti visi ID ar atbilstošo entītijas nosaukumu. Lauki tiek identificēti kā ID pēc to semantikas.

**Darbību laika grafiks** parāda datus, ja esat konfigurējis [darbības](activities.md). Laika skalas skatā ir hronoloģiskā secībā sakārtotas atlasītā klienta darbības, sākot ar visjaunāko darbību.

**Ieskati**:

- **Mēri** rāda, vai esat konfigurējis klienta atribūtu [mērus](measures.md). Tie iekļauj aprēķinātos KPI ap saviem klientiem atsevišķā klientu līmenī.

- **Potenciālās intereses, potenciālie zīmoli** parāda, ja esat konfigurējis [zīmolu vai interešu interešu bagātināšanu](enrichment-microsoft.md). Tas attiecas uz iespējamām interesēm un interesēm attiecībā uz zīmoliem, kas balstīti uz citiem klientiem, kuru profils ir līdzīgs atlasītajam klienta profilam.

Lai atgrieztos **lapā Klienti**, atlasiet **Atpakaļ pie klientiem**.

## <a name="next-steps"></a>Nākamās darbības

[Pievienojiet vēl datu avotus](data-sources.md), [bagātināt vienotos profilus](enrichment-hub.md) vai [izveidojiet segmentus](segments.md), lai strādātu ar vienoto klientu profiliem citās lietojumprogrammās.

[!INCLUDE [footer-include](includes/footer-banner.md)]
