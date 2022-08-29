---
title: Klientu, uzņēmumu vai kontaktpersonu apvienošanas iestatījumu atjaunināšana
description: Atjauniniet kārtulu dublikātus, atbilstības kārtulas vai vienotos laukus klienta vai konta apvienošanas iestatījumos.
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: Scott-Stabbert
ms.author: sstabbert
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-relationships
- customerInsights
ms.openlocfilehash: f2c14c169f5973b5f400989b9eeea593eba09182
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304344"
---
# <a name="update-unification-settings"></a>Unifikācijas iestatījumu atjaunināšana

Lai pārskatītu vai mainītu apvienošanas iestatījumus, kad ir izveidots vienots profils, veiciet tālāk norādītās darbības.

1. Dodieties uz **Data** > **Unify**.

   Atsevišķiem klientiem (no B-līdz C) **lapā Unify** tiek parādīts vienoto klientu profilu un elementu skaits katrai apvienošanas darbībai.

   :::image type="content" source="media/m3_unified.png" alt-text="Ekrānuzņēmums, kurā redzama lapa Data Unify pēc datu apvienošanas." lightbox="media/m3_unified.png":::

   Uzņēmumu kontiem (B-to-B) **lapā Unify** tiek parādīts vienoto kontu profilu un elementu skaits katrai konta apvienošanas darbībai. Ja kontaktpersonas bija vienotas, tiek parādīts vienoto kontaktpersonu profilu un elementu skaits katrai kontaktpersonu apvienošanas darbībai. Izvēlieties atbilstošo elementu sadaļā **Unify Konti** vai **Kontaktpersonu apvienošana (priekšskatījums)** atkarībā no tā, ko vēlaties atjaunināt.

   :::image type="content" source="media/b2b_unified.png" alt-text="Ekrānuzņēmums, kurā redzama lapa Data Unify pēc tam, kad konta un kontaktpersonu dati ir vienoti." lightbox="media/b2b_unified.png":::

   > [!TIP]
   > Elements **Atbilstības nosacījumi** tiek rādīts tikai tad, ja ir atlasītas vairākas entītijas.

1. Izvēlieties, ko vēlaties atjaunināt:
   - [Avota lauki](#edit-source-fields), lai pievienotu entītijas vai atribūtus vai mainītu atribūtu tipus.
   - [Dublēt ierakstus](#manage-deduplication-rules), lai pārvaldītu decentralizācijas kārtulas vai sapludināšanas preferences.
   - [Atbilstoši nosacījumi](#manage-match-rules), lai atjauninātu atbilstības kārtulas divām vai vairākām entītijām.
   - [Vienoti klientu lauki](#manage-unified-fields) lauku apvienošanai vai izslēgšanai. Varat arī grupēt saistītos profilus klasteros.
   - [Semantiskie lauki](#manage-semantic-fields-for-unified-contacts), lai pārvaldītu semantiskos tipus vienotiem kontaktu laukiem.
   - [Relācijas](#manage-contact-and-account-relationships), lai pārvaldītu relāciju starp kontaktpersonu un kontu.

1. Pēc izmaiņu veikšanas izvēlieties nākamo opciju:

   - [Palaidiet atbilstošus nosacījumus](#run-matching-conditions), lai ātri novērtētu atbilstošo nosacījumu kvalitāti (centības un atbilstības kārtulas), neatjauninot vienoto profilu. Opcija **Izpildīt tikai** atbilstošos nosacījumus netiek rādīta vienai entītijai.
   - [Apvienojiet profilus](#run-updates-to-the-unified-profile), lai palaistu atbilstošus nosacījumus un atjauninātu vienotā profila entītiju, neietekmējot atkarības (piemēram, bagātinājumus, segmentus vai mērus). Atkarīgie procesi netiek palaisti, bet tiks atsvaidzināti, kā [definēts atsvaidzināšanas grafikā](schedule-refresh.md).
   - [Apvienojiet profilus un atkarības](#run-updates-to-the-unified-profile), lai palaistu atbilstības nosacījumus, atjauninātu vienoto profila entītiju un atjauninātu visas atkarības (piemēram, bagātinājumus, segmentus vai mērus). Visi procesi tiek atkārtoti palaisti automātiski. B-to-B apvienošana tiek veikta gan konta, gan kontaktpersonu entītijām, kas atjaunina vienotos profilus.

## <a name="edit-source-fields"></a>Avota lauku rediģēšana

Atribūtu vai entītiju nevar noņemt, ja tās jau ir apvienotas.

1. Atlasiet **Rediģēt** elementā **Avota lauki**.

   :::image type="content" source="media/m3_source_edit.png" alt-text="Ekrānuzņēmums, kurā redzama avota lauku lapa, kurā redzams primāro atslēgu, kartēto un atkailināto lauku skaits":::

   Tiek parādīts kartēto un atmaskoto lauku skaits.

1. Lai pievienotu citus atribūtus vai entītijas, atlasiet **Atlasīt entītijas un laukus**.

1. Pēc izvēles varat mainīt entītijas primāro atslēgu, atribūtu tipus un ieslēgt **vai izslēgt viedo kartēšanu**. Papildinformāciju skatiet sadaļā [Avota lauku](map-entities.md) atlasīšana.

1. Atlasiet **Tālāk**, lai veiktu izmaiņas deduplikācijas kārtulās, vai atlasiet **Saglabāt un aizvērt** un atgriezties pie [Atjaunināšanas apvienošanas iestatījumi](#update-unification-settings).

## <a name="manage-deduplication-rules"></a>Decentralizācijas kārtulu pārvaldība

1. Atlasiet **Rediģēt** elementā **Dublēt ierakstus**.

   :::image type="content" source="media/m3_duplicates_edit.png" alt-text="Ekrānuzņēmums, kurā redzama lapa Dublēt ierakstus, kurā redzams dublēto ierakstu skaits" lightbox="media/m3_duplicates_edit.png":::

   Atrasto ierakstu dublikātu skaits tiek parādīts sadaļā **Dublikāti**. Kolonnā **Ieraksti ir parādīts**, kurām entītijām ir dublēti ieraksti, un dublēto ierakstu procentuālā daļa.

1. Lai izmantotu bagātinātu entītiju, atlasiet **Izmantot bagātinātas entītijas**. Papildinformāciju skatiet sadaļā [Bagātināšana datu avotiem](data-sources-enrichment.md).

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

   1. Atlasiet **Gatavs**.

1. Atlasiet **Tālāk**, lai veiktu izmaiņas atbilstošajos nosacījumos, vai atlasiet **Saglabāt un aizvērt** un atgriezties pie [Atjaunināšanas apvienošanas iestatījumi](#update-unification-settings).

## <a name="manage-match-rules"></a>Atbilstības kārtulu pārvaldība

Varat pārkonfigurēt un pielāgot lielāko daļu atbilstības parametru. Entītijas nevar pievienot vai dzēst. Atbilstības kārtulas neattiecas uz vienu entītiju.

1. Atlasiet **Rediģēt** elementā **Atbilstošie nosacījumi**.

   :::image type="content" source="media/m3_match_edit.png" alt-text="Ekrānuzņēmums, kurā redzama lapa Atbilstības noteikumi un nosacījumi ar statistiku." lightbox="media/m3_match_edit.png":::

   Lapā tiek parādīta atbilstības secība un definētie noteikumi, kā arī šāda statistika:
   - **Unikālie avota ieraksti** parāda to atsevišķo avota ierakstu skaitu, kas tika apstrādāti pēdējās atbilstības sērijā.
   - **Atbilstošie un neatbilstošie ieraksti** parāda, cik daudz unikālu ierakstu ir palicis pēc atbilstības kārtulu apstrādes.
   - **Atbilstošie ieraksti parāda tikai** spēļu skaitu visos jūsu atbilstības pāros.

1. Lai skatītu visu kārtulu rezultātus un to rezultātus, atlasiet **Skatīt pēdējo reizi**. Tiek parādīti rezultāti, tostarp alternatīvie kontaktpersonu ID. Jūs varat lejupielādēt rezultātus.

1. Lai skatītu noteiktas kārtulas rezultātus un rezultātus, atlasiet kārtulu un pēc tam **priekšskatiet**. Rezultāti tiek parādīti. Jūs varat lejupielādēt rezultātus.

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

1. Atlasiet **Tālāk**, lai veiktu izmaiņas vienotos laukos, vai atlasiet **Saglabāt un aizvērt** un atgriezties pie [Atjaunināšanas apvienošanas iestatījumi](#update-unification-settings).

## <a name="manage-unified-fields"></a>Vienotu lauku pārvaldība

1. Atlasiet **Rediģēt** vienotajā **klientu lauku elementā**.

    :::image type="content" source="media/m3_merge_edit.png" alt-text="Unified customer lauku ekrānuzņēmums":::

1. Pārskatiet apvienotos un izslēgtos laukus un pēc vajadzības veiciet izmaiņas. Pievienojiet vai rediģējiet CustomerID atslēgu vai grupu profilus klasteros. Papildinformāciju skatiet sadaļā [Klientu lauku](merge-entities.md) apvienošana.

1. Klientiem vai kontiem atlasiet **Tālāk**, lai pārskatītu un [atjauninātu vienoto profilu un atkarības](#run-updates-to-the-unified-profile). Vai arī atlasiet **Saglabāt un aizvērt** un atgriezties sadaļā [Atjaunināšanas apvienošanas iestatījumi](#update-unification-settings), lai veiktu papildu izmaiņas.

   Kontaktpersonām atlasiet **Tālāk**, lai pārvaldītu semantiskos laukus. Vai arī atlasiet **Saglabāt un aizvērt** un atgriezties sadaļā [Atjaunināšanas apvienošanas iestatījumi](#update-unification-settings), lai veiktu papildu izmaiņas.

## <a name="manage-semantic-fields-for-unified-contacts"></a>Vienotu kontaktpersonu semantisko lauku pārvaldība

1. Semantisko lauku **elementā** atlasiet **Rediģēt**.

1. Lai mainītu vienota lauka semantisko tipu, atlasiet jaunu tipu. Papildinformāciju skatiet sadaļā [Semantisko lauku definēšana vienotām kontaktpersonām](data-unification-contacts.md#define-the-semantic-fields-for-unified-contacts).

1. Atlasiet **Tālāk**, lai pārvaldītu konta un kontaktpersonu relāciju, vai atlasiet **Saglabāt un aizvērt** un atgriezties pie [Atjaunināšanas apvienošanas iestatījumi](#update-unification-settings), lai veiktu papildu izmaiņas.

## <a name="manage-contact-and-account-relationships"></a>Kontaktpersonu un kontu relāciju pārvaldība

1. Elementa Relācijas **atlasiet** **Rediģēt**.

1. Lai mainītu kontaktpersonu un konta relāciju, mainiet kādu no šīm ziņām:

   - **Ārējā atslēga no kontaktpersonas entītijas**: izvēlieties atribūtu, kas savieno jūsu kontaktpersonas entītiju ar kontu.
   - **Uz konta entītiju**: izvēlieties ar kontaktpersonu saistīto konta entītiju.

1. Atlasiet **Tālāk**, lai pārskatītu apvienošanas iestatījumus un [atjauninātu vienoto profilu un atkarības](#run-updates-to-the-unified-profile), vai atlasiet **Saglabāt un aizvērt** un atgriezties pie [Atjaunināšanas apvienošanas iestatījumi](#update-unification-settings), lai veiktu papildu izmaiņas.

## <a name="run-matching-conditions"></a>Skrējiens atbilstošiem nosacījumiem

Izpildīt atbilstošus nosacījumus, tiek palaisti tikai deduplikācijas un atbilstības noteikumi un atjauninātas *entītijas Deduplication_** un *ConflationMatchPair*.

1. **Lapā Data Unify (Datu** > **unify**) atlasiet **Palaist tikai** atbilstošos nosacījumus.

   Elementos **Dublēt ierakstus** un **Atbilstības nosacījumi** tiek rādīts **statuss Rindas** vai **Atsvaidzināšana**.

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

1. Kad atbilstības noteikšanas process ir pabeigts, elementā **Atbilstības nosacījumi** atlasiet **Rediģēt**.

   :::image type="content" source="media/match-KPIs.png" alt-text="Lapā Saskaņošana apgriezts galveno metriku ekrānuzņēmums ar skaitļiem un informāciju.":::

1. Lai veiktu izmaiņas, skatiet rakstu [Decentralizācijas kārtulu](#manage-deduplication-rules) pārvaldība vai [Atbilstības kārtulu](#manage-match-rules) pārvaldība.

1. Vēlreiz palaidiet atbilstības procesu vai [palaidiet profila](#run-updates-to-the-unified-profile) atjauninājumus.

## <a name="run-updates-to-the-unified-profile"></a>Vienotā profila atjauninājumu palaišana

- Lai palaistu atbilstības nosacījumus un atjauninātu vienotā profila entītiju, *neietekmējot* atkarības (piemēram, klientu kartes, bagātinājumus, segmentus vai mērus), atlasiet **Unify klientu profilus**. Kontiem atlasiet **Unify kontu** > **unificēt profilus**. Kontaktpersonām atlasiet **Unify contacts (preview)** > **Unify profilus**. Atkarīgie procesi netiek palaisti, bet tiks atsvaidzināti, kā [definēts atsvaidzināšanas grafikā](schedule-refresh.md).
- Lai palaistu atbilstošus nosacījumus, atjauninātu vienoto profilu un palaistu visas atkarības, atlasiet **Unify klientu profilus un atkarības**. Visi procesi tiek atkārtoti palaisti automātiski. Kontiem un kontaktpersonām atlasiet **Unify kontu** > **unificēt profilus un atkarības**. Atbilstības nosacījumi tiek izpildīti gan kontiem, gan kontaktpersonām, kas atjaunina gan vienotos profilus, gan visas pārējās atkarības.

Visi elementi, izņemot **avota laukus**, tiek rādīti **rindā vai** **atsvaidzinoši**.

[!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

Veiksmīgas palaišanas rezultāti tiek parādīti lapā Unify **,** parādot vienoto profilu skaitu.
