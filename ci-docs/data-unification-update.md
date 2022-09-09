---
title: Klientu, uzņēmumu vai kontaktpersonu apvienošanas iestatījumu atjaunināšana
description: Atjauniniet kārtulu dublikātus, atbilstības kārtulas vai vienotos laukus klienta vai konta apvienošanas iestatījumos.
ms.date: 08/26/2022
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
ms.openlocfilehash: e893e66fd7691b9703d51ed8f87cfad63880cc3b
ms.sourcegitcommit: 560c4ee16376a9c6fdd7860988ce2d2440194fa5
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 09/01/2022
ms.locfileid: "9392480"
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
   - [Avota lauki](#edit-source-fields), lai pievienotu atribūtus vai entītijas vai mainītu atribūtu tipus. Lai noņemtu atribūtu, skatiet rakstu [Vienota lauka](#remove-a-unified-field) noņemšana. Lai noņemtu entītiju, skatiet rakstu [Vienotas entītijas](#remove-a-unified-entity) noņemšana.
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

1. Atlasiet **Rediģēt** elementā **Avota lauki**.

   :::image type="content" source="media/m3_source_edit.png" alt-text="Ekrānuzņēmums, kurā redzama avota lauku lapa, kurā redzams primāro atslēgu, kartēto un atkailināto lauku skaits":::

   Tiek parādīts kartēto un atmaskoto lauku skaits.

1. Lai pievienotu citus atribūtus vai entītijas, atlasiet **Atlasīt entītijas un laukus**.

1. Pēc izvēles varat mainīt entītijas primāro atslēgu, atribūtu tipus un ieslēgt **vai izslēgt viedo kartēšanu**. Papildinformāciju skatiet sadaļā [Avota lauku](map-entities.md) atlasīšana.

1. Atlasiet **Tālāk**, lai veiktu izmaiņas deduplikācijas kārtulās, vai atlasiet **Saglabāt un aizvērt** un atgriezties pie [Atjaunināšanas apvienošanas iestatījumi](#update-unification-settings).

### <a name="remove-a-unified-field"></a>Vienota lauka noņemšana

Lai noņemtu lauku, kas ir vienots, lauks ir jānoņem no visām atkarībām, piemēram, segmentiem, mēriem, bagātinājumiem vai relācijām.

1. Kad visas lauka atkarības ir noņemtas, dodieties uz **Data** > **Unify**.

1. Atlasiet **Rediģēt** vienotajā **klientu lauku elementā**.

1. Atlasiet visus lauka gadījumus un pēc tam atlasiet **Izslēgt**.

   :::image type="content" source="media/m3_remove_attribute1.png" alt-text="Vienoto lauku lapas, kurā redzami atlasītie lauki un poga Izslēgt, ekrānuzņēmums":::

1. Atlasiet **Gatavs**, lai apstiprinātu, un pēc tam atlasiet **Saglabāt un aizvērt**.

   > [!TIP]
   > Ja redzat ziņojumu "Nevarēja saglabāt unificēt. Norādīto resursu nevar modificēt vai izdzēst pakārtoto atkarību dēļ", tad lauks joprojām tiek izmantots pakārtotā atkarībā.

1. Ja lauks kārtulā tiek izmantots ierakstu dublikātiem vai atbilstošiem nosacījumiem, veiciet tālāk norādītās darbības. Pretējā gadījumā pārejiet pie nākamās darbības.
   1. Atlasiet **Rediģēt** elementā **Dublēt ierakstus**.
   1. Noņemiet lauku no visām kārtulām, kurās tas tiek izmantots, ja tāds ir, un pēc tam atlasiet **Tālāk**.
   1. **Lapā Atbilstības nosacījumi** noņemiet lauku no visiem kārtulām, kurās tas tiek izmantots, ja tādi ir, un pēc tam atlasiet **Saglabāt un aizvērt**.
   1. Atlasiet **Unify** > **Unify klientu profilus un atkarības**. Pagaidiet, līdz apvienošanās tiks pabeigta, pirms pāriet uz nākamo soli.

1. Atlasiet **Rediģēt** elementā **Avota lauki**.

1. Atlasiet **Atlasīt entītijas un laukus** un notīriet izvēles rūtiņu blakus katram lauka gadījumam.

   :::image type="content" source="media/m3_remove_attribute2.png" alt-text="Ekrānuzņēmums, kurā redzams dialoglodziņš Entītiju un lauku atlasīšana, kurā redzamas notīrītas izvēles rūtiņas":::

1. Atlasiet vienumu **Piemērot**.

1. Atlasiet **Saglabāt un aizvērt**.

1. Atlasiet **Unify** > **Unify klientu profilus un atkarības**, lai atjauninātu vienoto profilu.

### <a name="remove-a-unified-entity"></a>Vienotas entītijas noņemšana

Lai noņemtu vienotu entītiju, entītija ir jānoņem no visām atkarībām, piemēram, segmentiem, mēriem, bagātinājumiem vai relācijām.

1. Kad visas entītijas atkarības ir noņemtas, dodieties uz **Data** > **Unify**.

1. Atlasiet **Rediģēt** vienotajā **klientu lauku elementā**.

1. Atlasiet visus entītijas laukus un pēc tam atlasiet **Izslēgt**.

   :::image type="content" source="media/m3_remove_entity1.png" alt-text="Vienoti lauki ar atlasītiem visiem entītijas laukiem un izslēgšanas pogu":::

1. Atlasiet **Gatavs**, lai apstiprinātu, un pēc tam atlasiet **Saglabāt un aizvērt**.

   > [!TIP]
   > Ja redzat ziņojumu "Nevarēja saglabāt unificēt. Norādīto resursu nevar modificēt vai dzēst pakārtoto atkarību dēļ", tad entītija joprojām tiek izmantota pakārtotā atkarībā.

1. Atlasiet **Rediģēt** elementā **Dublēt ierakstus**.

1. Noņemiet no entītijas visas kārtulas, ja tādas ir, un pēc tam atlasiet **Tālāk**.

1. **Lapā Atbilstības nosacījumi** atlasiet entītiju un pēc tam atlasiet **Dzēst**.

   :::image type="content" source="media/m3_remove_entity2.png" alt-text="Ekrānuzņēmums, kurā redzami nosacījumu saskaņošana ar atlasītu entītiju un pogu Dzēst":::

1. Atlasiet **Saglabāt un aizvērt**.

1. Atlasiet **Rediģēt** elementā **Avota lauki**.

1. Atlasiet **Atlasīt entītijas un laukus** un notīriet izvēles rūtiņu blakus entītijai.

   :::image type="content" source="media/m3_remove_entity3.png" alt-text="Ekrānuzņēmums, kurā redzams dialoglodziņš Entītiju un lauku atlasīšana ar notīrītu izvēles rūtiņu Entītija":::

1. Atlasiet vienumu **Piemērot**.

1. Atlasiet **Saglabāt un aizvērt**.

1. Atlasiet **Unify** > **Unify klientu profilus un atkarības**, lai atjauninātu vienoto profilu.

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
