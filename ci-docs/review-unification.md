---
title: Datu apvienošanas pārskatīšana
description: Pārskatiet datu apvienošanas darbības, izveidojiet vienotus klientu profilus un pārskatiet rezultātus
ms.date: 08/12/2022
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
ms.openlocfilehash: b4d77effc347e40fecde625a1a42a24900456471
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 08/16/2022
ms.locfileid: "9303976"
---
# <a name="review-data-unification"></a>Datu apvienošanas pārskatīšana

Pārskatiet izmaiņu kopsavilkumu, izveidojiet vienoto profilu un pārskatiet rezultātus.

## <a name="review-and-create-customer-profiles"></a>Pārskatīt un izveidot klientu profilus

Šis pēdējais apvienošanās procesa solis parāda procesa darbību kopsavilkumu un sniedz iespēju veikt izmaiņas pirms vienotā profila izveides.

[!INCLUDE [m3-first-run-note](includes/m3-first-run-note.md)]

:::image type="content" source="media/m3_review.png" alt-text="Ekrānuzņēmums, kurā redzama klientu profilu pārskatīšana un izveide.":::

1. Atlasiet **Rediģēt** jebkurā no datu apvienošanas darbībām, lai pārskatītu un veiktu izmaiņas.

1. Ja esat apmierināts ar atlasi, atlasiet **Izveidot klientu profilus** (vai **Izveidot kontu profilus** B-to-B). Lapa **Unify** tiek parādīta, kamēr tiek veidots vienotais klienta profils.

   :::image type="content" source="media/m3_unify_refreshing.png" alt-text="Ekrānuzņēmums, kurā redzama lapa Unify ar elementiem, kuros redzama rinda vai atsvaidzināšana.":::

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

Unifikācijas algoritma pabeigšanai ir nepieciešams zināms laiks, un konfigurāciju nevar mainīt, kamēr tā nav pabeigta.

## <a name="view-the-results-of-data-unification"></a>Datu apvienošanas rezultātu skatīšana

Pēc apvienošanas **lapā Data** > **Unify** tiek rādīts vienoto klientu profilu (vai B-to-B kontu profilu) skaits. Katra unifikācijas procesa soļa rezultāti tiek parādīti katrā elementā. Piemēram, **laukos** Avots tiek rādīts kartēto atribūtu (lauku) skaits, un **ierakstu** dublikāti parāda atrasto ierakstu dublikātu skaitu.

:::image type="content" source="media/m3_unified.png" alt-text="Ekrānuzņēmums, kurā redzama lapa Data Unify pēc datu apvienošanas.":::

> [!TIP]
> Elements **Atbilstības nosacījumi** tiek rādīts tikai tad, ja ir atlasītas vairākas entītijas.

Mēs iesakām pārskatīt rezultātus, jo īpaši atbilstības [noteikumu](data-unification-update.md#manage-match-rules) kvalitāti, un, ja nepieciešams, tos precizēt.

Ja nepieciešams, [veiciet izmaiņas apvienošanas iestatījumos](data-unification-update.md) un atkārtoti palaidiet vienoto profilu.

### <a name="verify-output-entities-from-data-unification"></a>Izvades entītiju pārbaude no datu apvienošanas

Dodieties uz **Datu** > **entītijas**, lai pārbaudītu izvades entītijas.

Vienotā klienta profila entītija ar nosaukumu *Klients* tiek rādīta sadaļā **Profili**. Ar pirmo veiksmīgo apvienošanas skrējienu tiek izveidota vienotā *klienta entītija*. Visi turpmākie braucieni paplašina šo entītiju.

Deduplikācijas un konflācijas entītijas tiek izveidotas un parādītas **sadaļā Sistēma**. Katrai avota entītijai tiek izveidota dedublēta entītija ar nosaukumu **Deduplication_DataSource_Entity**. Entītija **ConflationMatchPairs** satur informāciju par atbilstību starp entītijām.

Dedublikācijas izvades entītija ietver šādu informāciju:
- ID/ Atslēgas
  - Primārās atslēgas un alternatīvā ID lauki. Alternatīvais ID lauks sastāv no visiem alternatīvajiem ID, kas identificēti ierakstam.
  - Deduplication_GroupId lauks rāda grupu vai klasteru, kas identificēts entītijā, kas grupē visus līdzīgos ierakstus, pamatojoties uz norādītajiem dedublikācijas laukiem. To izmanto sistēmas apstrādes nolūkiem. Ja nav norādītas manuālas dedublikācijas kārtulas un tiek lietotas sistēmas definētās dedublikācijas kārtulas, varat neatrast šo lauku dedublikācijas izvades entītijā.
  - Deduplication_WinnerId: šajā laukā ir norādīts identificēto grupu vai klasteru uzvarētāja ID. Ja Deduplication_WinnerId vērtība ir tāda pati kā ieraksta primārās atslēgas vērtība, tas nozīmē, ka ieraksts ir uzvarētāja ieraksts.
- Lauki, ko lieto dedublikācijas kārtulu definēšanai.
- Kārtulu un punktu skaita lauki, lai apzīmētu, kuras no dedublikācijas kārtulām tika lietotas, un punktu skaitu, kas tika atgriezts, veicot atbilstošu aizstāšanu.

## <a name="next-step"></a>Nākamā darbība

- B-to-B gadījumā pēc izvēles veiciet [kontaktu apvienošanu](data-unification-contacts.md).

- No B-to-C konfigurējiet [darbības](activities.md), [bagātināšanu,](enrichment-hub.md) attiecības [vai](relationships.md) mērus [...](measures.md), lai gūtu plašāku ieskatu par saviem klientiem.

[!INCLUDE[footer-include](includes/footer-banner.md)]
