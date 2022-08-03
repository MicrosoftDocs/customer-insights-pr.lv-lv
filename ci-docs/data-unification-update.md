---
title: Apvienošanas iestatījumu atjaunināšana
description: Atjauniniet kārtulu dublikātus, atbilstības kārtulas vai vienotos laukus apvienošanas iestatījumos.
ms.date: 06/01/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-relationships
- customerInsights
ms.openlocfilehash: 1af7f018abd412c833ff22b3880f0e4508ff4953
ms.sourcegitcommit: 3c5b0b40b2b45e420015bbdd228ce0e610245e6f
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 07/12/2022
ms.locfileid: "9139620"
---
# <a name="update-the-unification-settings"></a>Apvienošanas iestatījumu atjaunināšana

Lai pārskatītu vai mainītu apvienošanas iestatījumus, kad ir izveidots vienots profils, veiciet tālāk norādītās darbības.

1. Dodieties uz **Data** > **Unify**.

   :::image type="content" source="media/m3_unified.png" alt-text="Ekrānuzņēmums, kurā redzama lapa Data Unify pēc datu apvienošanas.":::

   > [!TIP]
   > Elements **Atbilstības nosacījumi** tiek rādīts tikai tad, ja ir atlasītas vairākas entītijas.

1. Izvēlieties, ko vēlaties atjaunināt:
   - [Avota lauki](#edit-source-fields), lai pievienotu entītijas vai atribūtus vai mainītu atribūtu tipus.
   - [Dublēt ierakstus](#manage-deduplication-rules), lai pārvaldītu decentralizācijas kārtulas vai sapludināšanas preferences.
   - [Atbilstoši nosacījumi](#manage-match-rules), lai atjauninātu atbilstības kārtulas divām vai vairākām entītijām.
   - [Vienoti klientu lauki](#manage-unified-fields) lauku apvienošanai vai izslēgšanai. Varat arī grupēt saistītos profilus klasteros.

1. Pēc izmaiņu veikšanas izvēlieties nākamo opciju:

   :::image type="content" source="media/m3_run_match_merge.png" alt-text="Ekrānuzņēmums, kurā redzama lapa Data Unify ar iezīmētām opcijām Unify.":::

   - [Palaidiet atbilstošus nosacījumus](#run-matching-conditions), lai ātri novērtētu atbilstošo nosacījumu kvalitāti (centības un atbilstības kārtulas), neatjauninot vienoto profilu. Opcija **Izpildīt tikai** atbilstošos nosacījumus netiek rādīta vienai entītijai.
   - [Apvienojiet klientu profilus](#run-updates-to-the-unified-customer-profile), lai palaistu atbilstošus nosacījumus un atjauninātu vienoto klienta profila entītiju, neietekmējot atkarības (piemēram, bagātinājumus, segmentus vai mērus). Atkarīgie procesi netiek palaisti, bet tiks atsvaidzināti, kā [definēts atsvaidzināšanas grafikā](system.md#schedule-tab).
   - [Apvienojiet klientu profilus un atkarības](#run-updates-to-the-unified-customer-profile), lai palaistu atbilstošus nosacījumus un atjauninātu vienoto klienta profila entītiju un visas atkarības (piemēram, bagātinājumus, segmentus vai mērus). Visi procesi tiek atkārtoti palaisti automātiski.

## <a name="edit-source-fields"></a>Avota lauku rediģēšana

Atribūtu vai entītiju nevar noņemt, ja tās jau ir apvienotas.

1. Atlasiet **Rediģēt** elementā **Avota lauki**.

   :::image type="content" source="media/m3_source_edit.png" alt-text="Ekrānuzņēmums, kurā redzama avota lauku lapa, kurā redzams primāro atslēgu, kartēto un atkailināto lauku skaits":::

   Tiek parādīts kartēto un atmaskoto lauku skaits.

1. Atlasiet **Atlasīt entītijas un laukus**, lai pievienotu citus atribūtus vai entītijas. Izmantojiet meklēšanu vai ritiniet, lai atrastu un atlasītu interesējošos atribūtus un entītijas. Atlasiet vienumu **Piemērot**.

1. Pēc izvēles varat mainīt entītijas primāro atslēgu, atribūtu tipus un ieslēgt **vai izslēgt viedo kartēšanu**. Papildinformāciju skatiet sadaļā [Primārās atslēgas un semantiskā tipa atlasīšana atribūtiem](map-entities.md#select-primary-key-and-semantic-type-for-attributes).

1. Atlasiet **Tālāk**, lai veiktu izmaiņas deduplikācijas kārtulās, vai atlasiet **Saglabāt un aizvērt** un atgriezties pie [Atjaunināt apvienošanas iestatījumus](#update-the-unification-settings).

## <a name="manage-deduplication-rules"></a>Decentralizācijas kārtulu pārvaldība

1. Atlasiet **Rediģēt** elementā **Dublēt ierakstus**.

   :::image type="content" source="media/m3_duplicates_edit.png" alt-text="Ekrānuzņēmums, kurā redzama lapa Dublēt ierakstus, kurā redzams dublēto ierakstu skaits" lightbox="media/m3_duplicates_edit.png":::

   Atrasto ierakstu dublikātu skaits tiek parādīts sadaļā **Dublikāti**. Kolonnā **Ieraksti ir parādīts**, kurām entītijām ir dublēti ieraksti, un dublēto ierakstu procentuālā daļa.

1. Ja pievienojāt bagātinātu entītiju, atlasiet **Izmantot bagātinātas entītijas**. Papildinformāciju skatiet sadaļā [Bagātināšana datu avotiem](data-sources-enrichment.md).

1. Lai pārvaldītu decentralizācijas kārtulas, izvēlieties kādu no šīm opcijām:
   - **Izveidojiet jaunu kārtulu**: atlasiet **Pievienot kārtulu** zem atbilstošās entītijas. Papildinformāciju skatiet sadaļā [Decentralizācijas kārtulu](remove-duplicates.md#define-deduplication-rules) definēšana.
   - **Kārtulas nosacījumu** maiņa: atlasiet kārtulu un pēc tam **rediģējiet**. Mainiet laukus, pievienojiet vai noņemiet nosacījumus vai pievienojiet vai noņemiet izņēmumus.
   - **Priekšskatījums**: atlasiet kārtulu un pēc tam **priekšskatiet**, lai skatītu šīs kārtulas pēdējās izpildes rezultātus.
   - **Kārtulas** deaktivizēšana: atlasiet kārtulu un pēc tam **deaktivizējiet**, lai saglabātu deduplikācijas kārtulu, vienlaikus izslēdzot to no atbilstības noteikšanas procesa.
   - **Dublēt kārtulu**: atlasiet kārtulu un pēc tam **dublējiet,** lai izveidotu līdzīgu kārtulu ar izmaiņām.
   - **Dzēst kārtulu**: atlasiet kārtulu un pēc tam **izdzēsiet**.

1. Lai mainītu sapludināšanas preferences, atlasiet entītiju. Preferences var mainīt tikai tad, ja ir izveidota kārtula.
   1. Atlasiet **Rediģēt sapludināšanas preferences** un mainiet opciju **Ierakstīt paturēšanai**.
   1. Lai mainītu sapludināšanas preferences atsevišķiem entītijas atribūtiem, atlasiet **Papildu** un veiciet nepieciešamās izmaiņas.

      :::image type="content" source="media/m3_adv_merge.png" alt-text="Ekrānuzņēmums, kurā redzamas papildu sapludināšanas preferences, kurās redzams jaunākais e-pasts un vispilnīgākā adrese":::

   1. Atlasiet **Gatavs**.

1. Atlasiet **Tālāk**, lai veiktu izmaiņas atbilstošos nosacījumos, vai atlasiet **Saglabāt un aizvērt** un atgriezties pie [Atjaunināt apvienošanas iestatījumus](#update-the-unification-settings).

## <a name="manage-match-rules"></a>Atbilstības kārtulu pārvaldība

Varat pārkonfigurēt un pielāgot lielāko daļu atbilstības parametru. Entītijas nevar pievienot vai dzēst. Atbilstības kārtulas neattiecas uz vienu entītiju.

1. Atlasiet **Rediģēt** elementā **Atbilstošie nosacījumi**.

   :::image type="content" source="media/m3_match_edit.png" alt-text="Ekrānuzņēmums, kurā redzama lapa Atbilstības noteikumi un nosacījumi ar statistiku." lightbox="media/m3_match_edit.png":::

   Lapā tiek parādīta atbilstības secība un definētie noteikumi, kā arī šāda statistika:
   - **Unikālie avota ieraksti** norāda atsevišķu avota ierakstu skaitu, kas tika apstrādāti pēdējās saskaņošanas izpildes laikā.
   - **Saskaņotie un nesaskaņotie ieraksti** uzsver, cik daudz unikālu ierakstu saglabājas pēc atbilstības kārtulu apstrādes.
   - **Tikai saskaņotie ieraksti** parāda tikai atbilstību skaitu visos jūsu atbilstības pāros.

1. Lai skatītu visu kārtulu rezultātus un to rezultātus, atlasiet **Skatīt pēdējo reizi**. Tiek parādīti rezultāti, tostarp alternatīvie kontaktpersonu ID. Jūs varat lejupielādēt rezultātus.

1. Lai skatītu noteiktas kārtulas rezultātus un rezultātus, atlasiet kārtulu un pēc tam **priekšskatiet**. Tiek parādīti rezultāti. Jūs varat lejupielādēt rezultātus.

1. Lai skatītu kārtulas noteikta nosacījuma rezultātus, atlasiet kārtulu un pēc tam **rediģējiet**. Rediģēšanas rūtī atlasiet **Priekšskatījums** ar nosacījumu. Jūs varat lejupielādēt rezultātus.

   :::image type="content" source="media/m3_match_condition_preview.png" alt-text="Nepārspējamu un saskaņotu ierakstu grafisks attēlojums, ieskaitot datu sarakstu.":::

1. Ja pievienojāt bagātinātu entītiju, atlasiet **Izmantot bagātinātas entītijas**. Papildinformāciju skatiet sadaļā [Bagātināšana datu avotiem](data-sources-enrichment.md).

1. Lai pārvaldītu kārtulas, izvēlieties kādu no šīm opcijām:
   - **Izveidojiet jaunu kārtulu**: atlasiet **Pievienot kārtulu** zem atbilstošās entītijas. Papildinformāciju skatiet sadaļā [Kārtulu definēšana atbilstības pāriem](match-entities.md#define-rules-for-match-pairs).
   - **Mainiet kārtulu** secību, ja definējāt vairākas kārtulas: Velciet un nometiet kārtulas vajadzīgajā secībā. Papildinformāciju skatiet sadaļā [Atbilstības secības](match-entities.md#specify-the-match-order) norādīšana.
   - **Kārtulas nosacījumu** maiņa: atlasiet kārtulu un pēc tam **rediģējiet**. Mainiet laukus, pievienojiet vai noņemiet nosacījumus vai pievienojiet vai noņemiet izņēmumus.
   - **Deaktivizējiet kārtulu**: atlasiet kārtulu un pēc tam **deaktivizējiet**, lai saglabātu atbilstības kārtulu, vienlaikus izslēdzot to no atbilstības noteikšanas procesa.
   - **Dublēt kārtulu**: atlasiet kārtulu un pēc tam **dublējiet,** lai izveidotu līdzīgu kārtulu ar izmaiņām.
   - **Dzēst kārtulu**: atlasiet kārtulu un pēc tam **izdzēsiet**.

1. Atlasiet **Tālāk**, lai veiktu izmaiņas vienotajos laukos, vai atlasiet **Saglabāt un aizvērt** un atgriezties pie [Atjaunināt apvienošanas iestatījumus](#update-the-unification-settings).

## <a name="manage-unified-fields"></a>Vienotu lauku pārvaldība

1. Atlasiet **Rediģēt** vienotajā **klientu lauku elementā**.

    :::image type="content" source="media/m3_merge_edit.png" alt-text="Unified customer lauku ekrānuzņēmums":::

1. Pārskatiet apvienotos un izslēgtos laukus un pēc vajadzības veiciet izmaiņas. Pievienojiet vai rediģējiet CustomerID atslēgu vai grupu profilus klasteros. Papildinformāciju skatiet sadaļā [Klientu lauku](merge-entities.md) apvienošana.

1. Atlasiet **Tālāk**, lai pārskatītu apvienošanas iestatījumus un [atjauninātu vienoto profilu un atkarības](#run-updates-to-the-unified-customer-profile), vai atlasiet **Saglabāt un aizvērt** un atgriezties pie [Atjaunināt apvienošanas iestatījumus](#update-the-unification-settings), lai veiktu papildu izmaiņas.

## <a name="run-matching-conditions"></a>Skrējiens atbilstošiem nosacījumiem

Izpildīt atbilstošus nosacījumus, tiek palaisti tikai deduplikācijas un atbilstības noteikumi un atjauninātas *entītijas Deduplication_** un *ConflationMatchPair*.

1. **Lapā Data Unify (Datu** > **unify**) atlasiet **Palaist tikai** atbilstošos nosacījumus.

   Elementos **Dublēt ierakstus** un **Atbilstības nosacījumi** tiek rādīts **statuss Rindas** vai **Atsvaidzināšana**.

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

1. Kad atbilstības noteikšanas process ir pabeigts, elementā **Atbilstības nosacījumi** atlasiet **Rediģēt**.

   :::image type="content" source="media/match-KPIs.png" alt-text="Lapā Saskaņošana apgriezts galveno metriku ekrānuzņēmums ar skaitļiem un informāciju.":::

1. Lai veiktu izmaiņas, skatiet rakstu [Decentralizācijas kārtulu](#manage-deduplication-rules) pārvaldība vai [Atbilstības kārtulu](#manage-match-rules) pārvaldība.

1. Vēlreiz palaidiet atbilstības procesu vai [palaidiet klienta profila](#run-updates-to-the-unified-customer-profile) atjauninājumus.

## <a name="run-updates-to-the-unified-customer-profile"></a>Vienotā klienta profila atjauninājumu palaišana

1. **Lapā Data** > **Unify** atlasiet:

   - **Unificējiet klientu profilus**: tiek izpildīti atbilstoši nosacījumi un atjaunināta vienotā klienta profila entītija, neietekmējot atkarības (piemēram, bagātinājumus, segmentus vai mērus). Atkarīgie procesi netiek palaisti, bet tiks atsvaidzināti, kā [definēts atsvaidzināšanas grafikā](system.md#schedule-tab).

   - **Apvienojiet klientu profilus un atkarības**: izpilda atbilstošus nosacījumus un atjaunina vienoto profilu un visas atkarības. Visi procesi tiek atkārtoti palaisti automātiski. Kad visi pakārtotie procesi ir pabeigti, klienta profils atspoguļo atjauninātos datus.

   Elementos **Dublēt ierakstus**, **Atbilstības nosacījumos** un **Vienotajos klientu laukos** tiek rādīts **statuss Rinda** vai **Atsvaidzināšana**.

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

Veiksmīgas palaišanas rezultāti tiek parādīti lapā Unify **,** parādot vienotu klientu profilu skaitu.
