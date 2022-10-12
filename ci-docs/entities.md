---
title: Entitījas risinājumā Customer Insights.
description: Datu skatīšana Entītiju lapā.
ms.date: 08/04/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-entities
- customerInsight
ms.openlocfilehash: e365945b27e7c985ca5371c6b72619610b6f3af1
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610107"
---
# <a name="entities-in-customer-insights"></a>Entitījas risinājumā Customer Insights.

Pēc [datu avotu konfigurēšanas](data-sources.md) pārejiet uz lapu **Entītijas**, lai novērtētu uzņemto datu kvalitāti. Entītijas tiek uzskatītas par datu kopām. Dynamics 365 Customer Insights daudzās iespējas ir veidotas ap šīm entītijām. Rūpīga to pārskatīšana var palīdzēt pārbaudīt šo iespēju rezultātus.

Strādājot programmā Customer Insights, bagātinot datus vai veidojot segmentus, mērus un darbības, entītijas, kas izveidotas no šīm darbībām, tiek rādītas **lapā Entītijas**.

## <a name="view-a-list-of-entities"></a>Entītiju saraksta skatīšana

Dodieties uz **Datu** > **entītijas**, lai skatītu entītiju sarakstu. Tālāk sniegtā informācija tiek parādīta par katru entītiju.

- **Nosaukums**: datu elementa nosaukums. Ja blakus entītijas nosaukumam tiek rādīts brīdinājuma simbols, tas nozīmē, ka šīs entītijas dati netika veiksmīgi ielādēti.
- **Avots**: datu avots veids, kas pārņēma entītiju.
- **Atjaunināts**: laiks, kad entītija pēdējo reizi tika atjaunināta.
- **Statuss**: detalizēta informācija par entītijas pēdējo atjauninājumu.

## <a name="explore-a-specific-entitys-data"></a>Noteiktu entītijas datu izpēte

1. Dodieties uz **datu** > **entītijas**.
1. Atlasiet entītiju, lai atvērtu detalizētas informācijas lapu.  
1. Izpētiet dažādos šai entītijai iekļautos laukus un ierakstus.

- Cilne **Atribūti ir atlasīta** pēc noklusējuma, un tajā tiek rādīta detalizēta informācija par atlasīto entītiju, piemēram, lauku nosaukumi, datu tipi un tipi. Kolonnā **Tips** ir redzami kopējā datu modeļa saistītie tipi, ko ir automātiski identificējusi sistēma vai [manuāli kartējuši](map-entities.md) lietotāji. Šie tipi ir semantiskie tipi, kas var atšķirties no atribūtu datu tipiem. Piemēram, tālāk esošajā laukā *E-pasts* ir datu tips *Virkne*, bet tā (semantiskais) Common Data Model tips var būt *E-pasts*, *EmailAddress* vai *Identity.Service.Email*.

   :::image type="content" source="media/data-manager-entities-fields.png" alt-text="Tabula Lauki.":::

   > [!NOTE]
   > Šajā lapā tiek rādīts tikai jūsu entītijas datu paraugs. Lai skatītu pilnu datu kopu, dodieties uz **lapu Datu avoti**, atlasiet entītiju, atlasiet **Rediģēt** un pēc tam skatiet šīs entītijas datus ar Power Query redaktoru, kā paskaidrots sadaļā [Datu avoti](data-sources.md).

   Lai uzzinātu vairāk par entītijā uzņemtajiem datiem, **kolonnā Kopsavilkums** ir norādīti daži svarīgi datu raksturlielumi, piemēram, nulles, trūkstošās vērtības, unikālās vērtības, skaits un sadalījumi neatkarīgi no tā, kas ir piemērojams jūsu datiem. Atlasiet diagrammas ikonu, lai skatītu datu kopsavilkumu.

   :::image type="content" source="media/data-manager-entities-summary.png" alt-text="Datu kopsavilkuma tabula.":::

- Cilnē **Dati** tiek rādīta detalizēta informācija par atsevišķiem entītijas ierakstiem. Norādītā detalizētā informācija ir atkarīga no entītijas datu tipa.

   :::image type="content" source="media/data-manager-entities-data.png" alt-text="Atlasīt entītiju.":::

- Cilnē **Atskaites** (pieejama dažām entītijām) varat vizualizēt datus, izveidojot atskaiti, kurā iekļautas tālāk norādītās kolonnas.

  - **Atskaites nosaukums**: atskaites nosaukums.
  - **Izveidoja**: tās personas vārds, kura izveidoja entītiju.
  - **Izveidots**: entītijas izveides datums un laiks.
  - **Rediģēja**: tās personas vārds, kura modificēja entītiju.
  - **Rediģēts**: entītijas modificēšanas datums un laiks.

[!INCLUDE [footer-include](includes/footer-banner.md)]
