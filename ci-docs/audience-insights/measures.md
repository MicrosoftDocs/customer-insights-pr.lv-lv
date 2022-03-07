---
title: Izprotiet un pārvaldiet pasākumus
description: Uzziniet, kā mēri palīdz analizēt un atspoguļot jūsu uzņēmuma veiktspēju.
ms.date: 02/28/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-measures
- ci-measure-builder
- ci-measure-template
- ci-enrichment-details
- customerInsights
ms.openlocfilehash: c46fcc3baba1d6c92c2c0fe459a62277343cc0e4
ms.sourcegitcommit: cf6a0ed44915908a44c70889a2dd199a9d0d4798
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 02/28/2022
ms.locfileid: "8359796"
---
# <a name="measures-overview"></a>Pasākumu pārskats

Mēri palīdz labāk izprast klientu paradumus un uzņēmuma veiktspēju. Tie aplūko atbilstošās vērtības no [vienotajiem profiliem](data-unification.md). Piemēram, uzņēmums vēlas redzēt *kopējos tēriņus uz klientu*, lai izprastu katra klienta pirkumu vēsturi vai izmērīt *uzņēmuma kopējos pārdošanas apjomus*, lai izprastu kopējā līmeņa ieņēmumus visā uzņēmumā.  

Pasākumi tiek izveidoti [, izmantojot mērvienību veidotāju](measure-builder.md), datu vaicājumu platformu ar dažādiem operatoriem un vienkāršām kartēšanas iespējām. Tas ļauj filtrēt datus, grupēt rezultātus, noteikt [entītiju attiecību ceļus](relationships.md) un priekšskatīt izvadi. Iepriekš definētas veidnes [var](measure-templates.md) izmantot, lai efektīvi konfigurētu bieži lietotos pasākumus.

Izmantojiet mērījumu veidotāju, lai plānotu uzņēmuma aktivitātes, vaicājot klientu datus un izgūstot ieskatus. Piemēram, *katra klienta kopējo tēriņu* un *katra klienta kopējo ienākumu* mēra izveide palīdz identificēt klientu grupu, kuriem ir augsti tēriņi, bet arī augsti ieņēmumi. Pamatojoties uz šiem pasākumiem, varat [izveidot segmentu](segments.md), lai virzītu nākamās labākās darbības. 

## <a name="manage-your-measures"></a>Pārvaldiet savus mērus

Mērījumu saraksts atrodams lapā **Mērījumi**.

Atradīsiet informāciju par mēra tipu, izveidotāju, izveides datumu, statusu un stāvokli. Kad sarakstā atlasāt kādu mēru, varat priekšskatīt izvadi un lejupielādēt CSV failu.

Lai vienlaikus atsvaidzinātu visus mērus, atlasiet **Atsvaidzināt visu**, neatlasot noteiktu mēru.

:::image type="content" source="media/measure-actions.png" alt-text="Darbības, lai pārvaldītu atsevišķus mērus.":::

Sarakstā atlasiet mēru, lai izvēlētos kādu no šīm opcijām:

- Atlasiet mēra nosaukumu, lai skatītu tā detalizētu informāciju.
- **Rediģējiet** mēra konfigurāciju.
- **Atsvaidzināt** mēru, pamatojoties uz jaunākajiem datiem.
- **Pārdēvējiet** mēru.
- **Dzēsiet** mēru.
- **Aktivizēt** vai **Deaktivizēt**. Neaktīvie mēri netiks atsvaidzināti [plānotās atsvaidzināšanas laikā](system.md#schedule-tab).

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="next-step"></a>Nākamā darbība

Esošus mērus var izmantot, lai izveidotu [klientu segmentu](segments.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
