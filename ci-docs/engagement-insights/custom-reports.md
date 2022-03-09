---
title: Par pielāgotajām atskaitēm
description: Uzziniet, kā izveidot un pielāgot atskaites.
author: mochimochi016
ms.reviewer: mhart
ms.author: jefhar
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: e8cdfc07b67b78febc1d50b3b1fd44ab94448e64
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 02/16/2022
ms.locfileid: "8232157"
---
# <a name="create-and-edit-custom-reports"></a>Pielāgotu atskaišu izveidošana un rediģēšana

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Papildus standarta (OOB) atskaitēm var izveidot pielāgotu atskaiti ar diagrammām un tabulām, kas palīdzēs izprast lietotāju darbības. Šajā rakstā izskaidrots, kā izveidot atskaiti ar datiem, kas jums nepieciešami, izmantojot tabulu un diagrammu vizualizācijas. Informāciju par OOB atskaitēm skatiet rakstā [Atskaišu skatīšana ](view-reports.md).

## <a name="create-a-custom-report"></a>Pielāgotas atskaites izveidošana

1. Dodieties uz sadaļu **Analizēt** > **Pielāgot**, lai piekļūtu pielāgotam atskaišu sarakstam.

1. Atlasiet **Jauna atskaite**, lai sāktu pielāgotas atskaites izveidi.

   :::image type="content" source="media/new-custom-report.png" alt-text="Jaunas, pielāgotas atskaites.":::

1. Izlemiet, kāda tipa atskaiti jūs vēlaties izveidot:

    - Lai izveidotu noklusējuma tabulas vizualizāciju, komandjoslā atlasiet vienumu **Pievienot vizuālos datus**.
    - Vai **Atskaišu redaktora** rūtī atlasiet kolonnu, joslu, rindu, apgabalu, sektoru, virtuli vai tabulas vizualizāciju.

1. **Vizualizācijas redaktora** rūts **Datu** sadaļā izvēlieties kādu no pieejamajām opcijām (piemēram, lapu skati) nolaižamajā izvēlnē **Metrikas**. Varat arī pievienot **Dimensijas** (piemēram, valsti), lai rādītu vizualizācijā. Papildinformāciju skatiet rakstā [Metriku skatīšana un izveide](metrics.md) un [Dimensiju skatīšana un izveide](dimensions.md).

   :::image type="content" source="media/page-views.png" alt-text="Izvēlieties sava ziņōjuma metriku.":::

1. Atlasiet **Vizualizācijas redaktora** rūts sadaļu **Noformējums**, lai pievienotu **Virsraksta tekstu** un pārslēgtu sadaļu **Nosaukums** no ieslēgtas uz izslēgtu.  Vizualizācijas tipu var mainīt arī, atlasot citu diagrammu, piemēram, **sektoru diagrammu**.

1. Lai mainītu vizualizācijas lielumu un pozīciju:
   - Atlasiet vizualizāciju un pēc tam velciet vienu no stūrīšiem vai apmalēm, lai pielāgotu tās lielumu.
   - Atlasiet vizualizāciju un pārvietojiet to uz jaunu pozīciju. Pozīcijas mainīšanai var izmantot arī bultas taustiņus.
1. Komandjoslā atlasiet **Pievienot vizuālos datus**, lai pievienotu vēl vienu vizualizāciju.
1. Pēc tam, kad ir pievienotas atskaitei vēlamās vizualizācijas, komandjoslā atlasiet **Saglabāt**.

1. Norādiet pielāgotās atskaites nosaukumu un atlasiet **Saglabāt**, lai to izveidotu.
 
## <a name="filter-a-custom-report"></a>Filtrēt pielāgotu ziņojumu

Pielāgotā atskaitē var atlasīt laika periodu vai datumu diapazonu, lai koncentrētos uz vērtību vai laika periodam.

Lai atlasītu laika periodu, atskaites skata augšējā labajā stūrī atlasiet vērtību no atskaites nolaižamā saraksta. Varat arī izvēlēties **Fiksētu datu diapazonu*.

:::image type="content" source="media/filter-time-date-range.png" alt-text="Filtrējiet pēc laika vai datu diapazona.":::

Lielākajai daļai atskaišu atlasiet **+ Pievienot nosacījumu**, lai atskaites filtrēšanai izvēlētos fragmentu vai segmentu. Papildinformāciju skatiet sadaļā [Segmentu skatīšana un izveide](segments.md).

## <a name="edit-a-custom-report"></a>Rediģēt pielāgotu atskaiti

1. Dodieties uz sadaļu **Analizēt** > **Pielāgot**, lai piekļūtu pielāgotam atskaišu sarakstam.

1. Pielāgoto atskaišu sarakstā atlasiet **Vēl [...]** 

1. Izvēlieties **Rediģēt nosaukumu**, lai mainītu atskaites nosaukumu.

1. Atlasiet atskaites nosaukumu un izmantojiet opcijas **+ Pievienot vizuālos datus** un **Rediģēt**, lai pievienotu, noņemtu, pārvietotu vai mainītu vizualizāciju lielumu.

1. Lai mainītu vizualizācijas rekvizītus, atlasiet vizuālos datus, atlasiet **...** un pēc tam **Rediģēt vizuālos datus**.

   :::image type="content" source="media/edit-visual-control.png" alt-text="Pielāgotu atskaišu diagrammu rekvizītu rediģēšana.":::

1. Pēc atskaites rediģēšanas atlasiet opciju **Saglabāt**, lai pielietotu veiktās izmaiņas. 

## <a name="delete-a-custom-report"></a>Pielāgotas atskaites dzēšana

1. Dodieties uz sadaļu **Analizēt** > **Pielāgot**, lai piekļūtu pielāgotam atskaišu sarakstam.

1. Pielāgoto atskaišu sarakstā atlasiet **...**

1. Izvēlieties **Dzēst**, lai noņemtu atskaiti.

1. Apstipriniet dzēšanu, lai neatgriezeniski noņemtu atskaiti.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
