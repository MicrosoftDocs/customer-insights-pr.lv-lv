---
title: Vienota kontaktpersonas profila izveide (priekšskatījums)
description: Veiciet datu apvienošanas procesu, lai izveidotu vienu kontaktpersonu pamatdatu kopu.
ms.date: 08/12/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: overview
author: Scott-Stabbert
ms.author: sstabbert
manager: shellyha
searchScope:
- ci-map
- ci-match
- ci-merge
- customerInsights
ms.openlocfilehash: 721f47563582a94b5b8244ca5d5d7d1350695512
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 08/16/2022
ms.locfileid: "9305078"
---
# <a name="create-a-unified-contact-profile-preview"></a>Vienota kontaktpersonas profila izveide (priekšskatījums)

Pēc [biznesa kontu](map-entities.md) apvienošanas pēc izvēles varat apvienot kontaktpersonas šiem kontiem un saistīt vienotās kontaktpersonas ar vienotajiem kontiem. Kontaktpersonu apvienošanas process kartē kontaktinformāciju no vairākiem datu avotiem, noņem dublikātus, saskaņo datus starp entītijām, iestata semantisko kartēšanu, izveido relācijas starp kontaktpersonām un kontiem un pēc tam izveido vienotu kontaktpersonu profilu.

[!INCLUDE [m3-first-run-note](includes/m3-first-run-note.md)]

Daži pirmie soļi ir identiski vienojošajiem kontu soļiem.

## <a name="prerequisites"></a>Priekšnoteikumi

Kontu un kontaktpersonu ierakstiem ir jābūt unikālai atslēgai (sauktai par ārvalstu atslēgu), kas tos savieno. Piemēram, konta ID, kas atrodas konta ierakstā un kontaktpersonas ierakstā, kas saista kontu un kontaktpersonu.

## <a name="preview-limitations"></a>Priekšskatījuma ierobežojumi

- Kontaktpersonas bez saites uz kontu tiek atmestas.
- Ja konts tiek dedublēts, uzvarētāja ieraksts tiek identificēts, pamatojoties uz sapludināšanas preferencēm. Zaudētāju rekordi netiek atlasīti un tāpēc tiek atmesti. Kontakti, kas saistīti ar zaudētajiem ierakstiem, tiek atmesti.
- Kontam var būt vairākas kontaktpersonas, bet kontaktpersona ir saistīta ar vienu kontu.
- Semantiskās kartēšanas solī kartētie kontaktpersonu atribūti ir vienīgie atribūti, kas var tikt parādīti klienta kartītē. Tomēr ir pieejami 17 atribūti.

## <a name="select-source-fields"></a>Avota lauku atlasīšana

1. Sadaļā **Kontaktpersonu apvienošana (priekšskatījums)** atlasiet **Sākt darbu**.

1. [Atlasiet kontaktpersonu datu avotu entītijas un laukus](map-entities.md), tostarp primārās atslēgas un atribūtu tipus.

1. Atlasiet **Tālāk**.

## <a name="remove-duplicate-records"></a>Ierakstu dublikātu noņemšana

1. Pēc izvēles [definējiet deduplikācijas kārtulas](remove-duplicates.md) savām atlasītajām entītijām.

1. Atlasiet **Tālāk**.

## <a name="match-conditions"></a>Spēles nosacījumi

1. [Definējiet atbilstības secību un kārtulas](match-entities.md) vairāku entītiju atbilstībai.

1. Atlasiet **Tālāk**.

## <a name="unify-contact-fields"></a>Kontaktpersonu lauku apvienošana

1. [Apvienojiet un izslēdziet kontaktpersonu laukus](merge-entities.md).

1. Atlasiet **Tālāk**.

## <a name="define-the-semantic-fields-for-unified-contacts"></a>Definēt apvienoto kontaktpersonu semantiskos laukus

Šis apvienošanās procesa solis kartē jūsu vienotos kontaktpersonu laukus uz semantiskajiem tipiem. B-to-B klientu kartēs tiek rādīti konti. Kad karte ir atlasīta, tiek parādītas visas ar kontu saistītās kontaktpersonas. Šajā darbībā kartētie lauki ir lauki, kas tiks parādīti kartēs.

1. Atlasiet semantisko tipu, kas kartē uz katru vienoto lauku. Atlasiet **Nav**, ja semantiskā tipa nav pieejams.

   :::image type="content" source="media/semantic_mapping.png" alt-text="Ekrānuzņēmums ar semantisko lauku lapu, lai definētu semantiskos tipus." lightbox="media/semantic_mapping.png":::

1. Pēc visu vienoto lauku kartēšanas atlasiet **Tālāk**.

## <a name="set-the-relationship-between-contacts-and-accounts"></a>Kontaktpersonu un kontu relācijas iestatīšana

Šī apvienošanās procesa darbība savieno jūsu kontaktinformāciju ar atbilstošajiem konta datiem.

1. Katrai entītijai ievadiet šādu informāciju:

   - **Ārējā atslēga no kontaktpersonas entītijas**: izvēlieties atribūtu, kas savieno jūsu kontaktpersonas entītiju ar kontu.
   - **Uz konta entītiju**: izvēlieties ar kontaktpersonu saistīto konta entītiju.

   :::image type="content" source="media/contact_relationship.png" alt-text="Relāciju lapas ekrānuzņēmums, lai savienotu kontaktpersonu un konta entītijas.":::

1. Atlasiet **Tālāk**.

## <a name="review-contact-unification"></a>Kontaktpersonu apvienošanas pārskatīšana

Pārskatiet izmaiņu kopsavilkumu, izveidojiet vienoto profilu un pārskatiet rezultātus.

### <a name="review-and-create-contact-profiles"></a>Kontaktpersonu profilu pārskatīšana un izveide

Šis pēdējais apvienošanās procesa solis parāda procesa darbību kopsavilkumu un sniedz iespēju veikt izmaiņas pirms vienotā kontaktpersonas profila izveides.

:::image type="content" source="media/b2b_review_contacts.png" alt-text="Ekrānuzņēmums, kurā redzama kontaktpersonu profilu pārskatīšana un izveide.":::

1. Atlasiet **Rediģēt** jebkurā no kontaktpersonu apvienošanas darbībām, lai pārskatītu un veiktu izmaiņas.

1. Ja esat apmierināts ar atlasi, atlasiet **Izveidot kontaktpersonu profilus**. Lapa **Unify** tiek parādīta, kamēr tiek veidots vienotais kontaktpersonas profils.
  
   :::image type="content" source="media/b2b_unify_refreshing.png" alt-text="Ekrānuzņēmums, kurā redzama lapa Unify Kontaktpersonas ar elementiem, kuros redzama rinda vai atsvaidzināšana.":::

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

Unifikācijas algoritma pabeigšanai ir nepieciešams zināms laiks, un konfigurāciju nevar mainīt, kamēr tā nav pabeigta.

### <a name="view-the-results-of-contact-unification"></a>Kontaktpersonu apvienošanas rezultātu skatīšana

Kad apvienošana ir pabeigta, **lapā Datu** > **apvienošana** tiek rādīts vienoto kontaktpersonu profilu skaits. Katra apvienošanās procesa soļa rezultāti tiek parādīti katrā elementā. Piemēram, **laukos** Avots tiek rādīts kartēto atribūtu (lauku) skaits, un **ierakstu** dublikāti parāda atrasto ierakstu dublikātu skaitu.

:::image type="content" source="media/unified_contacts.png" alt-text="Ekrānuzņēmums, kurā redzama lapa Data Unify pēc kontaktpersonu apvienošanas.":::

> [!TIP]
> Elements **Atbilstības nosacījumi** tiek rādīts tikai tad, ja ir atlasītas vairākas entītijas.

Mēs iesakām pārskatīt rezultātus, jo īpaši atbilstības [noteikumu](data-unification-update.md#manage-match-rules) kvalitāti, un, ja nepieciešams, tos precizēt.

Ja nepieciešams, [veiciet izmaiņas kontaktpersonu apvienošanas iestatījumos](data-unification-update.md) un atkārtoti palaidiet vienoto profilu.

### <a name="verify-output-entities-from-data-unification"></a>Izvades entītiju pārbaude no datu apvienošanas

Dodieties uz **Datu** > **entītijas**, lai pārbaudītu izvades entītijas.

Vienotā kontaktpersonas profila entītija, ko sauc par *ContactProfile*, tiek rādīta sadaļā Semantiskās **entītijas**. Ar pirmo veiksmīgo apvienošanas skrējienu tiek izveidota vienotā *ContactProfile entītija*. Visi turpmākie braucieni paplašina šo entītiju.

Entītija *ContactsCustomer* (priekšskatījums **) tiek izveidota un parādīta sadaļā Profili**. Šī entītija satur kontaktinformāciju bez saitēm uz kontiem. Šī entītija tiek izmantota kā ievade kontaktu apvienošanas semantiskajā kartēšanā un relāciju darbībās.

Deduplikācijas un konflācijas entītijas tiek izveidotas un parādītas **sadaļā Sistēma**. Katrai avota entītijai tiek izveidota dedublēta entītija ar nosaukumu **Deduplication_DataSource_Entity**. Entītija **ContactsConflationMatchPairs** satur informāciju par vairāku entītiju atbilstību.

Dedublikācijas izvades entītija ietver šādu informāciju:
- ID/ Atslēgas
  - Primārās atslēgas un alternatīvā ID lauki. Alternatīvais ID lauks sastāv no visiem alternatīvajiem ID, kas identificēti ierakstam.
  - Deduplication_GroupId lauks rāda grupu vai klasteru, kas identificēts entītijā, kas grupē visus līdzīgos ierakstus, pamatojoties uz norādītajiem dedublikācijas laukiem. To izmanto sistēmas apstrādes nolūkiem. Ja nav norādītas manuālas dedublikācijas kārtulas un tiek lietotas sistēmas definētās dedublikācijas kārtulas, varat neatrast šo lauku dedublikācijas izvades entītijā.
  - Deduplication_WinnerId: šajā laukā ir norādīts identificēto grupu vai klasteru uzvarētāja ID. Ja Deduplication_WinnerId vērtība ir tāda pati kā ieraksta primārās atslēgas vērtība, tas nozīmē, ka ieraksts ir uzvarētāja ieraksts.
- Lauki, ko lieto dedublikācijas kārtulu definēšanai.
- Kārtulu un punktu skaita lauki, lai apzīmētu, kuras no dedublikācijas kārtulām tika lietotas, un punktu skaitu, kas tika atgriezts, veicot atbilstošu aizstāšanu.

## <a name="next-step"></a>Nākamā darbība

Konfigurējiet [darbības](activities.md), [bagātināšanu](enrichment-hub.md) vai [relācijas](relationships.md), lai gūtu vairāk ieskatu par savām kontaktpersonām.
