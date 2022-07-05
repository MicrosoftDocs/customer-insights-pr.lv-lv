---
title: Datu apvienošanas pārskats
description: Veiciet datu apvienošanas procesu ar saviem datiem, lai izveidotu vienotu klientu profilu vienotu datu kopu.
ms.date: 05/10/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: overview
author: v-wendysmith
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-map
- customerInsights
ms.openlocfilehash: 0dbc3b2c75365e94758a1b6330e8cb557e6bd768
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082221"
---
# <a name="data-unification-overview"></a>Datu apvienošanas pārskats

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

Pēc [datu avotu iestatīšanas](data-sources.md) var apvienot datus. Datu apvienošana ļauj apvienot vienreiz atšķirīgus datu avotus vienā datu pamatkopā, kas nodrošina vienotu skatu uz šiem datiem. Individuāliem patērētājiem (no B-līdz C), kur dati ir centrēti ap indivīdiem, apvienošanās nodrošina vienotu skatījumu uz jūsu klientiem. Uzņēmumu kontiem (B-to-B), kuru dati ir centrēti ap kontiem, apvienošana nodrošina vienotu pārskatu par jūsu kontiem.

Datus var apvienot vienā entītijā vai vairākās entītijās. Apvienošana tiek veikta šādā secībā:

1. [Avota lauki](map-entities.md) (iepriekš saukti par karti): darbībā Avota lauki atlasiet entītijas un laukus, kas jāiekļauj apvienošanas procesā. Kartējiet laukus uz kopīgu semantisko tipu, kas apraksta lauka mērķi.

1. [Ierakstu dublikāti](remove-duplicates.md) (iepriekš daļa no atbilstības): darbībā Ierakstu dublikāti pēc izvēles definējiet kārtulas, lai no katras entītijas noņemtu dublētus klientu ierakstus.

1. [Atbilstoši nosacījumi](match-entities.md) (iepriekš saukti par atbilstību): atbilstības nosacījumu solī definējiet kārtulas, kas atbilst klientu ierakstiem starp entītijām. Ja klients ir atrasts divās vai vairākās entītijās, tiek izveidots viens konsolidēts ieraksts ar visām kolonnām un datiem no katras entītijas.

1. [Vienoti klientu lauki](merge-entities.md) (iepriekš saukti par sapludināšanu): vienoto klientu lauku solī nosakiet, kuri avota lauki ir jāiekļauj, jāizslēdz vai jāsapludina vienotā klienta profilā.  

1. [Pārskatiet](review-unification.md) un izveidojiet vienoto profilu.

Pēc datu apvienošanas pabeigšanas pēc izvēles varat:

- [Iestatiet relācijas starp entītijām](relationships.md), lai izveidotu sarežģītus segmentus.
- [Bagātiniet savus datus](enrichment-hub.md), lai iegūtu plašāku ieskatu klāstu par saviem klientiem.
- [Definējiet darbības](activities.md) no dažiem uzņemtajiem atribūtiem.
- [Veidojiet pasākumus](measures.md), lai labāk izprastu klientu uzvedību un biznesa veiktspēju.

[!INCLUDE [footer-include](includes/footer-banner.md)]
