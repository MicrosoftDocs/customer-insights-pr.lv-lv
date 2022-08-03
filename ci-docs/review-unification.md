---
title: Datu apvienošanas pārskatīšana
description: Pārskatiet datu apvienošanas darbības, izveidojiet vienotus klientu profilus un pārskatiet rezultātus
ms.date: 06/02/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: adkuppa
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-relationships
- customerInsights
ms.openlocfilehash: 20728ffaef9bb705410b3ac22d19868ffd5d1243
ms.sourcegitcommit: 3c5b0b40b2b45e420015bbdd228ce0e610245e6f
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 07/12/2022
ms.locfileid: "9139593"
---
# <a name="review-data-unification"></a>Datu apvienošanas pārskatīšana

Šis pēdējais apvienošanās procesa solis parāda procesa darbību kopsavilkumu un sniedz iespēju veikt izmaiņas pirms vienotā profila izveides.

:::image type="content" source="media/m3_review.png" alt-text="Ekrānuzņēmums, kurā redzama klientu profilu pārskatīšana un izveide.":::

## <a name="review-the-data-unification-steps"></a>Datu apvienošanas darbību pārskatīšana

1. Atlasiet **Rediģēt** jebkurā no datu apvienošanas darbībām, lai pārskatītu un veiktu izmaiņas.

1. Ja esat apmierināts ar atlasi, atlasiet **Izveidot klientu profilus**. Lapa **Unify** tiek parādīta, kamēr tiek veidots vienotais klienta profils. Visos elementos, izņemot avota laukus **, tiek rādīts** statuss Rinda vai **Atsvaidzināšana** **.**

   :::image type="content" source="media/m3_unify_refreshing.png" alt-text="Ekrānuzņēmums, kurā redzama lapa Unify ar elementiem, kuros redzama rinda vai atsvaidzināšana.":::

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

Unifikācijas algoritma pabeigšanai ir nepieciešams zināms laiks, un konfigurāciju nevar mainīt, kamēr tā nav pabeigta. Kad apvienošanas process ir pabeigts, vienotā klienta profila entītija ar nosaukumu *Klients* tiek norādīta **lapas** Entītijas **sadaļā Profili**. Ar pirmo veiksmīgo apvienošanas skrējienu tiek izveidota vienotā *klienta entītija*. Visi turpmākie braucieni paplašina šo entītiju.

## <a name="review-the-results-of-data-unification"></a>Datu unifikācijas rezultātu pārskatīšana

Pēc apvienošanas **lapā Data** > **Unify** tiek rādīts vienoto klientu profilu skaits. Katra unifikācijas procesa soļa rezultāti tiek parādīti katrā elementā. Piemēram, **laukos** Avots tiek rādīts kartēto atribūtu (lauku) skaits, un **ierakstu** dublikāti parāda atrasto ierakstu dublikātu skaitu.

:::image type="content" source="media/m3_unified.png" alt-text="Ekrānuzņēmums, kurā redzama lapa Data Unify pēc datu apvienošanas.":::

> [!TIP]
> Elements **Atbilstības nosacījumi** tiek rādīts tikai tad, ja ir atlasītas vairākas entītijas.

Mēs iesakām pārskatīt rezultātus, jo īpaši atbilstības [noteikumu](data-unification-update.md#manage-match-rules) kvalitāti, un, ja nepieciešams, tos precizēt.

Ja nepieciešams, [veiciet izmaiņas apvienošanas iestatījumos](data-unification-update.md) un atkārtoti palaidiet vienoto profilu.

## <a name="next-step"></a>Nākamā darbība

Konfigurējiet [darbības](activities.md), [bagātināšanu](enrichment-hub.md), [attiecības](relationships.md) vai [mērus](measures.md), lai gūtu plašāku ieskatu par saviem klientiem.

[!INCLUDE[footer-include](includes/footer-banner.md)]
