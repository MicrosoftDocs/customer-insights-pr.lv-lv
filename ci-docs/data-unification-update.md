---
title: Atjaunināt apvienošanas iestatījumus
description: Atjauniniet dublikātus kārtulas, atbilstības kārtulas vai vienotus laukus apvienošanas iestatījumos.
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
ms.openlocfilehash: 590a2996cf8b2b1c6def59b78583169ec1910b59
ms.sourcegitcommit: 760fbac397c738407c7dea59297d54cae19b6f57
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 06/03/2022
ms.locfileid: "8844049"
---
# <a name="update-the-unification-settings"></a>Atjaunināt apvienošanas iestatījumus

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

Lai pārskatītu vai mainītu visus apvienošanas iestatījumus pēc vienotā profila izveides, veiciet tālāk norādītās darbības.

1. Dodieties uz **Data** > **Unify**.

   :::image type="content" source="media/m3_unified.png" alt-text="Ekrānuzņēmums, kurā redzama lapa Data Unify pēc datu apvienošanas.":::

   > [!TIP]
   > Atbilstības **nosacījumu** elements tiek parādīts tikai tad, ja ir atlasītas vairākas entītijas.

1. Izvēlieties, ko vēlaties atjaunināt:
   - [Avota lauki](#edit-source-fields), lai pievienotu entītijas vai atribūtus vai mainītu atribūtu tipus.
   - [Dublējiet ierakstus](#manage-deduplication-rules), lai pārvaldītu deduplikācijas kārtulas vai sapludināšanas preferences.
   - [Atbilstoši nosacījumi](#manage-match-rules) atbilstības kārtulu atjaunināšanai divās vai vairākās entītijās.
   - [Vienoti klienta lauki](#manage-unified-fields), lai apvienotu vai izslēgtu laukus. Saistītos profilus var arī grupēt kopās.

1. Pēc izmaiņu veikšanas izvēlieties nākamo opciju:

   :::image type="content" source="media/m3_run_match_merge.png" alt-text="Ekrānuzņēmums, kurā redzama lapa Datu unifikācija ar iezīmētām unify opcijām.":::

   - [Palaidiet atbilstības nosacījumus](#run-matching-conditions), lai ātri novērtētu atbilstošo nosacījumu (deduplication and match rules) kvalitāti, neatjauninot vienoto profilu. Opcija **Palaist tikai** atbilstošos nosacījumus netiek rādīta vienai entītijai.
   - [Apvienojiet klientu profilus](#run-updates-to-the-unified-customer-profile), lai palaistu atbilstošus nosacījumus un atjauninātu vienoto klienta profila entītiju, neietekmējot atkarības (piemēram, bagātināšanu, segmentus vai pasākumus). Atkarīgie procesi netiek palaisti, bet tiks atsvaidzināti, kā [definēts atsvaidzināšanas grafikā](system.md#schedule-tab).
   - [Apvienojiet klientu profilus un atkarības, lai palaistu atbilstošos](#run-updates-to-the-unified-customer-profile) nosacījumus un atjauninātu vienoto klienta profila entītiju un visas atkarības (piemēram, bagātinājumus, segmentus vai pasākumus). Visi procesi tiek atkārtoti izpildīti automātiski.

## <a name="edit-source-fields"></a>Rediģēt avota laukus

Atribūtu vai entītiju nevar noņemt, ja tas jau ir vienots.

1. Elementā **Avota lauki** atlasiet **Rediģēt**.

   :::image type="content" source="media/m3_source_edit.png" alt-text="Avota lauku lapas ekrānuzņēmums, kurā redzams primāro atslēgu, kartēto un nekartēto lauku skaits":::

   Tiek parādīts kartēto un nekartēto lauku skaits.

1. Atlasiet **Atlasīt entītijas un laukus**, lai pievienotu citus atribūtus vai entītijas. Izmantojiet meklēšanu vai ritiniet, lai atrastu un atlasītu interesējošos atribūtus un entītijas. Atlasiet vienumu **Piemērot**.

1. Pēc izvēles varat mainīt entītijas primāro atslēgu, atribūtu tipus un ieslēgt vai izslēgt **inteliģento kartēšanu**. Papildinformāciju skatiet sadaļā [Primārās atslēgas un semantiskā tipa atlasīšana atribūtiem](map-entities.md#select-primary-key-and-semantic-type-for-attributes).

1. Atlasiet **Tālāk**, lai veiktu izmaiņas deduplikācijas kārtulās, vai atlasiet **Saglabāt un aizvērt** un atgriezties pie [Apvienošanas iestatījumu atjaunināšanas](#update-the-unification-settings).

## <a name="manage-deduplication-rules"></a>Deduplikācijas kārtulu pārvaldība

1. Elementā Ierakstu dublikāti **atlasiet** **Rediģēt**.

   :::image type="content" source="media/m3_duplicates_edit.png" alt-text="Ierakstu dublikātu lapas ekrānuzņēmums, kurā redzams dublēto ierakstu skaits" lightbox="media/m3_duplicates_edit.png":::

   Atrasto ierakstu dublikātu skaits tiek parādīts sadaļā **Dublikāti**. Kolonnā **Ierakstu paplašināšana** ir redzams, kurām entītijām bija ierakstu dublikāti un dublēto ierakstu procentuālā vērtība.

1. Ja pievienojāt bagātinātu entītiju, atlasiet **Izmantot bagātinātas entītijas**. Papildinformāciju skatiet rakstā [Datu avotu](data-sources-enrichment.md) bagātināšana.

1. Lai pārvaldītu deduplikācijas kārtulas, izvēlieties kādu no šīm opcijām:
   - **Izveidot jaunu kārtulu**: atbilstošajā entītijā atlasiet **Pievienot kārtulu**. Plašāku informāciju skatiet [Define deduplication rules](remove-duplicates.md#define-deduplication-rules).
   - **Mainīt kārtulas nosacījumus**: atlasiet kārtulu un pēc tam **rediģējiet**. Mainiet laukus, pievienojiet vai noņemiet nosacījumus vai pievienojiet vai noņemiet izņēmumus.
   - **Priekšskatījums**: atlasiet kārtulu un pēc tam **preview**, lai skatītu šīs kārtulas pēdējās izpildes rezultātus.
   - **Deaktivizēt kārtulu**: atlasiet kārtulu un pēc tam **deaktivizējiet**, lai saglabātu deduplikācijas kārtulu, vienlaikus izslēdzot to no atbilstības procesa.
   - **Dublēt kārtulu**: atlasiet kārtulu un pēc tam **dublējiet**, lai izveidotu līdzīgu kārtulu ar modifikācijām.
   - **Kārtulas** dzēšana: atlasiet kārtulu un pēc tam **Dzēsiet**.

1. Lai mainītu sapludināšanas preferences, atlasiet entītiju. Preferences var mainīt tikai tad, ja ir izveidota kārtula.
   1. Atlasiet **Rediģēt sapludināšanas preferences** un mainiet opciju Ieraksts, **lai paturētu**.
   1. Lai mainītu sapludināšanas preferences atsevišķiem entītijas atribūtiem, atlasiet **Papildu** un veiciet nepieciešamās izmaiņas.

      :::image type="content" source="media/m3_adv_merge.png" alt-text="Papildu sapludināšanas preferenču ekrānuzņēmums, kurā redzams jaunākais e-pasts un vispilnīgākā adrese":::

   1. Atlasiet **Gatavs**.

1. Atlasiet **Tālāk**, lai veiktu izmaiņas atbilstošajos nosacījumos, vai atlasiet **Saglabāt un aizvērt** un atgriezties pie [Apvienošanas iestatījumu atjaunināšanas](#update-the-unification-settings).

## <a name="manage-match-rules"></a>Atbilstības kārtulu pārvaldība

Varat pārkonfigurēt un pielāgot lielāko daļu atbilstības parametru. Entītijas nevar pievienot vai dzēst. Atbilstības kārtulas neattiecas uz vienu entītiju.

1. Elementā **Atbilstības nosacījumi** atlasiet **Rediģēt**.

   :::image type="content" source="media/m3_match_edit.png" alt-text="Ekrānuzņēmums, kurā redzama lapa Saskaņot kārtulas un nosacījumus ar statistiku." lightbox="media/m3_match_edit.png":::

   Lapā tiek parādīta atbilstības secība un definētās kārtulas, kā arī šāda statistika:
   - **Unikālie avota ieraksti** norāda atsevišķu avota ierakstu skaitu, kas tika apstrādāti pēdējās saskaņošanas izpildes laikā.
   - **Saskaņotie un nesaskaņotie ieraksti** uzsver, cik daudz unikālu ierakstu saglabājas pēc atbilstības kārtulu apstrādes.
   - **Tikai saskaņotie ieraksti** parāda tikai atbilstību skaitu visos jūsu atbilstības pāros.

1. Lai skatītu visu kārtulu rezultātus un to rezultātus, atlasiet **Skatīt pēdējo izpildi**. Tiek parādīti rezultāti, tostarp alternatīvās kontaktpersonu ID. Jūs varat lejupielādēt rezultātus.

1. Lai skatītu noteiktas kārtulas rezultātus un rezultātus, atlasiet kārtulu un pēc tam **Preview**. Rezultāti tiek parādīti. Jūs varat lejupielādēt rezultātus.

1. Lai skatītu noteikta kārtulas nosacījuma rezultātus, atlasiet kārtulu un pēc tam **rediģējiet**. Rediģēšanas rūtī atlasiet **Priekšskatījums** ar nosacījumu. Jūs varat lejupielādēt rezultātus.

   :::image type="content" source="media/m3_match_condition_preview.png" alt-text="Nesaskaņotu un saskaņotu ierakstu grafisks attēlojums, ieskaitot datu sarakstu.":::

1. Ja pievienojāt bagātinātu entītiju, atlasiet **Izmantot bagātinātas entītijas**. Papildinformāciju skatiet rakstā [Datu avotu](data-sources-enrichment.md) bagātināšana.

1. Lai pārvaldītu kārtulas, izvēlieties kādu no šīm opcijām:
   - **Izveidot jaunu kārtulu**: atbilstošajā entītijā atlasiet **Pievienot kārtulu**. Papildinformāciju skatiet rakstā [Atbilstības pāru kārtulu definēšana](match-entities.md#define-rules-for-match-pairs).
   - **Mainiet kārtulu** secību, ja definējāt vairākas kārtulas: velciet un nometiet kārtulas vajadzīgajā secībā. Plašāku informāciju skatiet [Norādiet atbilstības secību](match-entities.md#specify-the-match-order).
   - **Mainīt kārtulas nosacījumus**: atlasiet kārtulu un pēc tam **rediģējiet**. Mainiet laukus, pievienojiet vai noņemiet nosacījumus vai pievienojiet vai noņemiet izņēmumus.
   - **Deaktivizējiet kārtulu**: atlasiet kārtulu un pēc tam **deaktivizējiet**, lai saglabātu atbilstības kārtulu, vienlaikus izslēdzot to no atbilstības procesa.
   - **Dublēt kārtulu**: atlasiet kārtulu un pēc tam **dublējiet**, lai izveidotu līdzīgu kārtulu ar modifikācijām.
   - **Kārtulas** dzēšana: atlasiet kārtulu un pēc tam **Dzēsiet**.

1. Atlasiet **Tālāk**, lai veiktu izmaiņas vienotajos laukos, vai atlasiet **Saglabāt un aizvērt** un atgriezties pie [Apvienošanas iestatījumu atjaunināšanas](#update-the-unification-settings).

## <a name="manage-unified-fields"></a>Pārvaldīt vienotos laukus

1. Elementā Vienotie **debitoru lauki** atlasiet **Rediģēt**.

    :::image type="content" source="media/m3_merge_edit.png" alt-text="Vienotā klienta lauku ekrānuzņēmums":::

1. Pārskatiet kombinētos un izslēgtos laukus un veiciet nepieciešamās izmaiņas. Pievienojiet vai rediģējiet CustomerID atslēgu vai grupas profilus kopās. Plašāku informāciju skatiet Unify [customer fields](merge-entities.md).

1. Atlasiet **Tālāk**, lai pārskatītu apvienošanas iestatījumus un [atjauninātu vienoto profilu un atkarības](#run-updates-to-the-unified-customer-profile), vai atlasiet **Saglabāt un aizvērt** un atgriezties pie [Atjaunināšanas apvienošanas iestatījumiem](#update-the-unification-settings), lai veiktu papildu izmaiņas.

## <a name="run-matching-conditions"></a>Izpildīt atbilstības nosacījumus

Izpildīt atbilstošos nosacījumus izpilda tikai deduplikācijas un atbilstības kārtulas un atjaunina *entītijas Deduplication_** un *ConflationMatchPair*.

1. **Lapā Datu** > **unifikācija** atlasiet **Palaist tikai** atbilstošos nosacījumus.

   Elementu **Ierakstu** dublikāti un **atbilstošie nosacījumi** parāda **statusu Rindā** vai **Atsvaidzināšana**.

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

1. Kad atbilstības process ir pabeigts, elementā **Atbilstības nosacījumi** atlasiet **Rediģēt**.

   :::image type="content" source="media/match-KPIs.png" alt-text="Lapā Saskaņošana apgriezts galveno metriku ekrānuzņēmums ar skaitļiem un informāciju.":::

1. Lai veiktu izmaiņas, skatiet rakstu [Deduplikācijas kārtulu](#manage-deduplication-rules) pārvaldība vai [Atbilstības kārtulu](#manage-match-rules) pārvaldība.

1. Vēlreiz palaidiet atbilstības procesu vai [palaidiet klienta profila](#run-updates-to-the-unified-customer-profile) atjauninājumus.

## <a name="run-updates-to-the-unified-customer-profile"></a>Palaist vienotā klienta profila atjauninājumus

1. **Lapā Datu** > **unifikācija** atlasiet:

   - **Klientu profilu** apvienošana: izpilda atbilstības nosacījumus un atjaunina vienoto klienta profila entītiju, neietekmējot atkarības (piemēram, bagātināšanu, segmentus vai pasākumus). Atkarīgie procesi netiek palaisti, bet tiks atsvaidzināti, kā [definēts atsvaidzināšanas grafikā](system.md#schedule-tab).

   - **Unificēt klientu profilus un atkarības**: izpilda atbilstošos nosacījumus un atjaunina vienoto profilu un visas atkarības. Visi procesi tiek atkārtoti izpildīti automātiski. Kad visi pakārtotie procesi ir pabeigti, klienta profils atspoguļo atjauninātos datus.

   Elementos **Ierakstu** dublikāti, **Atbilstības nosacījumi** un **Vienotie klientu lauki** rāda **statusu Rindas** vai **Atsvaidzināšana**.

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

Veiksmīgas izpildes displeja **rezultāti lapā Unify**, parādot vienoto klientu profilu skaitu.
