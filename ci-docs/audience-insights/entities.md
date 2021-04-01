---
title: Entītijas un datu kopas.
description: Datu skatīšana Entītiju lapā.
ms.date: 04/16/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 383523bad5105e08e57758838e90a49e805b5f9b
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596416"
---
# <a name="entities-in-audience-insights"></a>Entītijas auditorijas ieskatiem

Pēc [datu avotu konfigurēšanas](data-sources.md) pārejiet uz lapu **Entītijas**, lai novērtētu uzņemto datu kvalitāti. Entītijas tiek uzskatītas par datu kopām. Dynamics 365 Customer Insights daudzās iespējas ir veidotas ap šīm entītijām. Rūpīga to pārskatīšana var palīdzēt pārbaudīt šo iespēju rezultātus.

Lapā **Entītijas** tiek norādītas entītijas, un tajā ir vairākas kolonnas.

- **Nosaukums**: Datu entītijas nosaukums. Ja blakus entītijas nosaukumam tiek rādīts brīdinājuma simbols, tas nozīmē, ka šīs entītijas dati netika veiksmīgi ielādēti.
- **Avots**: Tas datu avota veids, kas uzņēma entītiju
- **Izveidoja**: Tās personas vārds, kura izveidoja šo entītiju
- **Izveidots**: Entītijas izveides datums un laiks
- **Atjaunināja**: Tās personas vārds, kura atjaunināja šo entītiju
- **Pēdējā atjaunināšana**: Entītijas pēdējās atjaunināšanas datums un laiks
- **Pēdējā atsvaidzināšana**: Pēdējās datu atsvaidzināšanas datums un laiks

## <a name="exploring-a-specific-entitys-data"></a>Noteiktu entītijas datu izpēte

Atlasiet entītiju, lai izpētītu tajā ietvertos dažādos laukus un ierakstus.

> [!div class="mx-imgBorder"]
> ![Atlasīt entītiju](media/data-manager-entities-data.png "Atlasīt entītiju")

- Cilne **Dati** ir atlasīta pēc noklusējuma, un tajā ir redzama tabula ar detalizētu informāciju par atsevišķiem entītijas ierakstiem.

> [!div class="mx-imgBorder"]
> ![Tabula Lauki](media/data-manager-entities-fields.PNG "Tabula Lauki")

- Cilnē **Lauki** ir redzama tabula, kurā varat pārskatīt detalizētu informāciju par atlasīto entītiju, piemēram, lauku nosaukumus, datu tipus un tipus. Kolonnā **Tips** ir redzami kopējā datu modeļa saistītie tipi, ko ir automātiski identificējusi sistēma vai [manuāli kartējuši](map-entities.md) lietotāji. Šie ir semantiski tipi, kas var atšķirties no atribūtu datu tipiem — piemēram, tālāk redzamajā laukā *Email* ir ietverts datu tips *Text*, bet tā (semantiskais) kopējā datu modeļa tips var būt *Email* vai *EmailAddress*.

> [!NOTE]
> Abās tabulās ir redzams tikai entītijas datu paraugs. Lai skatītu pilnu datu kopu, atveriet lapu **Datu avoti**, atlasiet entītiju, atlasiet **Rediģēt** un pēc tam skatiet šīs entītijas datus, izmantojot Power Query redaktoru, kā paskaidrots tēmā [Datu avoti](data-sources.md).

Lai uzzinātu vairāk par entītijā pieņemtajiem datiem, kolonnā **Kopsavilkums** ir norādītas svarīgas datu īpašības, piemēram, vērtības Null, trūkstošās vērtības, unikālās vērtības, skaits un izplatīšanas reižu skaits attiecībā uz jūsu datiem.

Atlasiet diagrammas ikonu, lai skatītu datu kopsavilkumu.

> [!div class="mx-imgBorder"]
> ![Kopsavilkuma simbols](media/data-manager-entities-summary.png "Tabula Datu kopsavilkums")

### <a name="next-step"></a>Nākamā darbība

Skatiet rakstu [Apvienošana](data-unification.md), lai uzzinātu, kā *kartēt*, *noteikt atbilstību* un *sapludināt* pieņemtos datus.


[!INCLUDE[footer-include](../includes/footer-banner.md)]