---
title: Pārskatīt datu apvienošanu
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
ms.openlocfilehash: 0f7b2e9af65796c4d304dbd9893a21617e847620
ms.sourcegitcommit: 760fbac397c738407c7dea59297d54cae19b6f57
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 06/03/2022
ms.locfileid: "8844095"
---
# <a name="review-data-unification"></a>Pārskatīt datu apvienošanu

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

Šis pēdējais apvienošanas procesa solis parāda procesa darbību kopsavilkumu un dod iespēju veikt izmaiņas pirms vienotā profila izveides.

:::image type="content" source="media/m3_review.png" alt-text="Ekrānuzņēmums, kurā redzama pārskatīšana un klientu profilu izveide.":::

## <a name="review-the-data-unification-steps"></a>Pārskatīt datu apvienošanas darbības

1. Atlasiet **Rediģēt** jebkurā no datu apvienošanas darbībām, lai pārskatītu un veiktu jebkādas izmaiņas.

1. Ja esat apmierināts ar savām atlasēm, atlasiet **Izveidot debitoru profilus**. Lapa **Unify** tiek parādīta vienotā klienta profila izveides laikā. Visiem elementiem, izņemot **avota laukus**, ir redzams **statuss** Rindā vai **Atsvaidzināšana**.

   :::image type="content" source="media/m3_unify_refreshing.png" alt-text="Ekrānuzņēmums, kurā redzama lapa Unify ar elementiem, kuros redzama rinda vai atsvaidzināšana.":::

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

Apvienošanas algoritma pabeigšana prasa zināmu laiku, un konfigurāciju nevar mainīt, kamēr tā nav pabeigta. Kad apvienošanas process ir pabeigts, vienotā klienta profila entītija ar nosaukumu *Klients ir norādīta* sadaļā Profili lapā **Entītijas** **.** Pirmā veiksmīgā apvienošanas izpilde izveido vienotu *klienta entītiju*. Visas turpmākās darbības paplašina šo entītiju.

## <a name="review-the-results-of-data-unification"></a>Pārskatīt datu apvienošanas rezultātus

Pēc apvienošanas **lapā Datu** > **unifikācija** tiek parādīts vienoto klientu profilu skaits. Katra apvienošanas procesa soļa rezultāti tiek parādīti katrā flīzē. Piemēram, **laukos** Avots ir redzams kartēto atribūtu (lauku) skaits, un **ierakstu** dublikāti parāda atrasto ierakstu dublikātu skaitu.

:::image type="content" source="media/m3_unified.png" alt-text="Ekrānuzņēmums, kurā redzama lapa Data Unify pēc datu apvienošanas.":::

> [!TIP]
> Atbilstības **nosacījumu** elements tiek parādīts tikai tad, ja ir atlasītas vairākas entītijas.

Mēs iesakām pārskatīt rezultātus, jo īpaši atbilstības [noteikumu](data-unification-update.md#manage-match-rules) kvalitāti, un vajadzības gadījumā tos uzlabot.

Ja nepieciešams, [veiciet izmaiņas apvienošanas iestatījumos](data-unification-update.md) un vēlreiz palaidiet vienoto profilu.

## <a name="next-step"></a>Nākamā darbība

Konfigurējiet aktivitātes, bagātināšanu [,](activities.md) attiecības [vai](enrichment-hub.md) pasākumus [, lai gūtu plašāku ieskatu par saviem klientiem.](relationships.md)[...](measures.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
