---
title: Klientu vienotā skata izveide
description: Veiciet datu apvienošanas procesu ar saviem datiem, lai izveidotu vienotu vienotu klientu profilu datu kopu.
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
ms.openlocfilehash: bb8da6f4b9f92f2b265ff9807e04638edae4f814
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755743"
---
# <a name="data-unification-overview"></a>Datu apvienošanas pārskats

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

Pēc [datu avotu iestatīšanas](data-sources.md) var apvienot datus. Datu apvienošana ļauj apvienot vienreiz atšķirīgus datu avotus vienā pamatdatu kopā, kas nodrošina vienotu skatījumu uz šiem datiem. Individuāliem patērētājiem (no B-C līdz C), kur datu centrā ir indivīdi, apvienošanās nodrošina vienotu priekšstatu par jūsu klientiem. Biznesa kontiem (B-to-B), kur dati ir centrēti uz kontiem, apvienošana nodrošina vienotu skatījumu uz jūsu kontiem.

Datus var apvienot vienā entītijā vai vairākās entītijās. Apvienošana tiek veikta šādā secībā:

1. [Avota lauki](map-entities.md) (iepriekš saukti par Karti): Avota lauku solī atlasiet entītijas un laukus, kas jāiekļauj apvienošanas procesā. Kartējiet laukus uz parastu semantisko tipu, kas apraksta lauka mērķi.

1. [Ierakstu](remove-duplicates.md) dublikāti (iepriekš atbilstības daļa): ierakstu dublikātu solī pēc izvēles definējiet kārtulas, lai noņemtu klientu ierakstu dublikātus no katras entītijas.

1. [Atbilstības nosacījumi](match-entities.md) (iepriekš saukti par Atbilstību): saskaņošanas nosacījumu solī definējiet kārtulas, kas atbilst klientu ierakstiem starp entītijām. Ja klients ir atrasts divās vai vairākās entītijās, tiek izveidots viens konsolidēts ieraksts ar visām kolonnām un datiem no katras entītijas.

1. [Vienotie klienta lauki](merge-entities.md) (iepriekš saukti par sapludināšanu): vienotā klienta lauku solī nosakiet, kuri avota lauki jāiekļauj, jāizslēdz vai jāapvieno vienotā klienta profilā.  

1. [Pārskatiet](review-unification.md) un izveidojiet vienoto profilu.

Pēc datu apvienošanas pabeigšanas pēc izvēles varat:

- [Iestatiet attiecības starp entītijām](relationships.md), lai izveidotu sarežģītus segmentus.
- [Bagātiniet savus datus](enrichment-hub.md), lai gūtu plašāku ieskatu par saviem klientiem.
- [Definējiet aktivitātes](activities.md) no dažiem uzņemtajiem atribūtiem.
- [Veidojiet pasākumus](measures.md), lai labāk izprastu klientu uzvedību un biznesa sniegumu.

[!INCLUDE [footer-include](includes/footer-banner.md)]
