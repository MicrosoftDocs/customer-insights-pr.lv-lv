---
title: Izpratne par pasākumiem un to pārvaldība
description: Uzziniet, kā pasākumi palīdz analizēt un atspoguļot jūsu uzņēmuma darbību.
ms.date: 03/24/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.author: wameng
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-measures
- ci-measure-builder
- ci-measure-template
- ci-enrichment-details
- customerInsights
ms.openlocfilehash: 84a3a10a2517258c1f895800882b9c67391ec3de
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643310"
---
# <a name="measures-overview"></a>Pasākumu pārskats

Mēri palīdz labāk izprast klientu paradumus un uzņēmuma veiktspēju. Tie aplūko atbilstošās vērtības no [vienotajiem profiliem](data-unification.md). Piemēram, uzņēmums vēlas redzēt *kopējos tēriņus uz klientu*, lai izprastu katra klienta pirkumu vēsturi vai izmērīt *uzņēmuma kopējos pārdošanas apjomus*, lai izprastu kopējā līmeņa ieņēmumus visā uzņēmumā.  

Pasākumi tiek izveidoti [, izmantojot mērījumu veidotāju](measure-builder.md), datu vaicājumu platformu ar dažādiem operatoriem un vienkāršām kartēšanas opcijām. Tas ļauj filtrēt datus, grupēt rezultātus, noteikt [entītiju attiecību ceļus](relationships.md) un priekšskatīt izvadi. [Varat izmantot iepriekš definētas](measure-templates.md) veidnes, lai efektīvi konfigurētu bieži lietotos pasākumus.

Izmantojiet mērījumu veidotāju, lai plānotu uzņēmuma aktivitātes, vaicājot klientu datus un izgūstot ieskatus. Piemēram, *katra klienta kopējo tēriņu* un *katra klienta kopējo ienākumu* mēra izveide palīdz identificēt klientu grupu, kuriem ir augsti tēriņi, bet arī augsti ieņēmumi. Pamatojoties uz šiem pasākumiem, varat [izveidot segmentu](segments.md), lai virzītu nākamās labākās darbības.

## <a name="manage-your-measures"></a>Pārvaldiet savus mērus

Mērījumu saraksts atrodams lapā **Mērījumi**.

Atradīsiet informāciju par mēra tipu, izveidotāju, izveides datumu, statusu un stāvokli. Kad sarakstā atlasāt kādu mēru, varat priekšskatīt izvadi un lejupielādēt CSV failu.

:::image type="content" source="media/measures-actions.png" alt-text="Darbības, lai pārvaldītu atsevišķus mērus."lightbox="media/measures-actions.png":::

Atlasot pasākumu, ir pieejamas šādas darbības:

- **Rediģējiet** mēra konfigurāciju.
- **Dublējiet** mēru. Varat izvēlēties rediģēt tā rekvizītus uzreiz vai vienkārši saglabāt dublikātu.
- **Atsvaidzināt** mēru, pamatojoties uz jaunākajiem datiem. Lai vienlaikus atsvaidzinātu visus pasākumus, atlasiet visus pasākumus un pēc tam **atsvaidziniet**.
- **Pārdēvējiet** mēru.
- **Aktivizēt** vai **Deaktivizēt**. Neaktīvie mēri netiks atsvaidzināti [plānotās atsvaidzināšanas laikā](system.md#schedule-tab).
- **Atzīmējiet**, lai [pārvaldītu segmenta atzīmes](work-with-tags-columns.md#manage-tags).
- **Dzēsiet** mēru.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="next-step"></a>Nākamā darbība

Esošus mērus var izmantot, lai izveidotu [klientu segmentu](segments.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
