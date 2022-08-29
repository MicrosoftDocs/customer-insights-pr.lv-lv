---
title: Klientu vienotā skata izveide
description: Veiciet datu apvienošanas procesu ar saviem datiem, lai izveidotu vienu konta vai klientu profilu pamatdatu kopu.
ms.date: 08/12/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: overview
author: Scott-Stabbert
ms.author: sstabbert
manager: shellyha
searchScope:
- ci-map
- customerInsights
ms.openlocfilehash: c2a81776eab147c4b5209a6fbf89c0f4c9853d1d
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304436"
---
# <a name="data-unification-overview"></a>Datu apvienošanas pārskats

Pēc [datu avotu iestatīšanas](data-sources.md) var apvienot datus. Datu apvienošana ļauj apvienot vienreiz atšķirīgus datu avotus vienā datu pamatkopā, kas nodrošina vienotu skatu uz šiem datiem.

Individuāliem patērētājiem (no B-līdz C), kur dati ir centrēti ap indivīdiem, apvienošanās nodrošina vienotu skatījumu uz jūsu klientiem. Uzņēmumu kontiem (B-to-B), kuru dati ir centrēti ap kontiem, apvienošana nodrošina vienotu pārskatu par jūsu kontiem. [Kontaktpersonu apvienošana (priekšskatījums)](data-unification-contacts.md) ļauj šo kontu kontaktpersonām būt atsevišķi vienotām un saistītām ar kontiem.

Datus var apvienot vienā entītijā vai vairākās entītijās.

# <a name="individual-consumers-b-to-c"></a>[Atsevišķi patērētāji (B2C)](#tab/b2c)

Apvienošanas process kartē klientu datus no datu avotiem, noņem dublikātus, saskaņo datus starp entītijām un izveido vienotu profilu. Apvienošana tiek veikta šādā secībā:

1. [Avota lauki](map-entities.md) (iepriekš saukti par karti): darbībā Avota lauki atlasiet entītijas un laukus, kas jāiekļauj apvienošanas procesā. Kartējiet laukus uz kopīgu semantisko tipu, kas apraksta lauka mērķi.

1. [Ierakstu dublikāti](remove-duplicates.md) (iepriekš daļa no atbilstības): darbībā Ierakstu dublikāti pēc izvēles definējiet kārtulas, lai no katras entītijas noņemtu dublētus klientu ierakstus.

1. [Atbilstoši nosacījumi](match-entities.md) (iepriekš saukti par atbilstību): atbilstības nosacījumu solī definējiet kārtulas, kas atbilst klientu ierakstiem starp entītijām. Ja klients ir atrasts divās vai vairākās entītijās, tiek izveidots viens konsolidēts ieraksts ar visām kolonnām un datiem no katras entītijas.

1. [Vienoti klientu lauki](merge-entities.md) (iepriekš saukti par sapludināšanu): vienoto klientu lauku solī nosakiet, kuri avota lauki ir jāiekļauj, jāizslēdz vai jāsapludina vienotā klienta profilā.  

1. [Pārskatiet](review-unification.md) un izveidojiet vienoto profilu.

# <a name="business-accounts-b-to-b"></a>[Uzņēmumu konti (B2B)](#tab/b2b)

Apvienošanas process kartē konta datus no datu avotiem, noņem dublikātus, saskaņo datus starp entītijām un izveido vienotu profilu. Apvienošana tiek veikta šādā secībā:

1. [Avota lauki](map-entities.md) (iepriekš saukti par karti): darbībā Avota lauki atlasiet entītijas un laukus, kas jāiekļauj unify konta procesā. Kartējiet laukus uz kopīgu semantisko tipu, kas apraksta lauka mērķi.

1. [Ierakstu dublikāti](remove-duplicates.md) (iepriekš daļa no atbilstības): darbībā Ierakstu dublikāti pēc izvēles definējiet kārtulas, lai no katras entītijas noņemtu kontu ierakstu dublikātus.

1. [Atbilstības nosacījumi](match-entities.md) (iepriekš saukti par atbilstību): atbilstības nosacījumu solī definējiet kārtulas, kas atbilst entītiju kontu ierakstiem. Ja konts ir atrasts divās vai vairākās entītijās, tiek izveidots viens konsolidēts ieraksts ar visām kolonnām un datiem no katras entītijas.

1. [Vienoti klientu lauki](merge-entities.md) (iepriekš saukti par sapludināšanu): vienoto klientu lauku solī nosakiet, kuri avota lauki ir jāiekļauj, jāizslēdz vai jāsapludina vienotā klienta profilā.  

1. [Pārskatiet](review-unification.md) un izveidojiet vienoto profilu.

Pēc kontu apvienošanas pēc izvēles [varat apvienot kontaktpersonas (priekšskatīt)](data-unification-contacts.md) šiem kontiem un saistīt vienotās kontaktpersonas ar vienotajiem kontiem.

---

Pēc datu apvienošanas pabeigšanas pēc izvēles varat:

- [Iestatiet relācijas starp entītijām](relationships.md), lai izveidotu sarežģītus segmentus.
- [Bagātiniet savus datus](enrichment-hub.md), lai iegūtu plašāku ieskatu klāstu par saviem klientiem.
- [Definējiet darbības](activities.md) no dažiem uzņemtajiem atribūtiem.
- [Veidojiet pasākumus](measures.md), lai labāk izprastu klientu uzvedību un biznesa veiktspēju.

[!INCLUDE [footer-include](includes/footer-banner.md)]
