---
title: Savienot entītijas datu apvienošanai
description: Savienojiet datus, lai izveidotu vienotus klientu profilus.
recommendations: false
ms.date: 05/05/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-map
- customerInsights
ms.openlocfilehash: bc470dd932c2c981adc5840bb52d60f8dfe0de61
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 05/11/2022
ms.locfileid: "8740958"
---
# <a name="match-conditions"></a>Atbilstības nosacījumi

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

Šis apvienošanas solis definē atbilstības secību un kārtulas vairāku entītiju saskaņošanai. Šim solim ir nepieciešamas vismaz divas entītijas.

> [!NOTE]
> Kad esat izveidojis atbilstības nosacījumus un atlasījis **Tālāk**, atlasīto entītiju vai atribūtu nevar noņemt. Ja nepieciešams, pirms turpināt, atlasiet **Atpakaļ**, lai pārskatītu atlasītās entītijas un atribūtus.

## <a name="include-enriched-entities-preview"></a>Bagātināto entītiju iekļaušana (priekšskatījums)

Ja bagātinājāt entītijas datu avots līmenī, lai palīdzētu uzlabot apvienošanās rezultātus, atlasiet tos. Papildinformāciju skatiet rakstā [Datu avotu bagātināšana](data-sources-enrichment.md). Ja lapā Ierakstu **dublikāti** atlasījāt bagātinātās entītijas, tās vairs nav jāatlasa.

1. **Lapā Atbilstības nosacījumi** lapas augšdaļā atlasiet **Izmantot bagātinātas entītijas**.

1. **Rūtī Bagātinātu entītiju** izmantošana izvēlieties vienu vai vairākas bagātinātas entītijas.

1. Atlasiet **Gatavs**.

## <a name="specify-the-match-order"></a>Atbilstības noteikšanas secības norādīšana

Katra atbilstība apvieno divas vai vairākas entītijas vienā, konsolidētā entītijā. Vienlaikus tiek glabāti unikālie klientu ieraksti. Atbilstības secība norāda secību, kādā sistēma mēģina saskaņot ierakstus.

> [!IMPORTANT]
> Saraksta pirmo entītiju sauc par primāro entītiju. Primārā entītija kalpo par pamatu jūsu vienoto profilu datu kopai. Šai entītijai tiks pievienotas atlasītas papildu entītijas.
>
> Svarīgi apsvērumi:
>
> - Izvēlieties entītiju ar vispilnīgākajiem un uzticamākajiem profila datiem par klientiem kā primāro entītiju.
> - Kā primāro entītiju izvēlieties entītiju, kurai ir vairāki atribūti, kas ir kopīgi ar citām entītijām (piemēram, vārds, tālruņa numurs vai e-pasta adrese).

1. **Lapā Atbilstības nosacījumi** izmantojiet pārvietošanas augšupvērsto un lejupvērsto bultiņu, lai pārvietotu entītijas vajadzīgajā secībā, vai velciet un nometiet tās. Piemēram, atlasiet **Kontaktpersonas:e-komercija** kā primāro entītiju un **Klientu lojalitāte:Lojalitāte** kā otro entītiju.

1. Lai katrs entītijas ieraksts būtu unikāls klients neatkarīgi no tā, vai ir atrasta atbilstība, atlasiet **Iekļaut visus ierakstus**. Visi šīs entītijas ieraksti, kas neatbilst ierakstiem nevienā citā entītijā, tiek iekļauti vienotajā profilā. Ierakstus, kuriem nav atbilstības, sauc par singliem.
  
Primārā entītija *Kontaktpersonas:e-komercija* tiek saskaņota ar nākamo entītiju *CustomerLoyalty:Loyalty*. Datu kopa, kas izriet no pirmās atbilstības soļa, tiek saskaņota ar šo entītiju, ja jums ir vairāk nekā divas entītijas.

:::image type="content" source="media/m3_match.png" alt-text="Entītijām atlasītās atbilstības secības ekrānuzņēmums." lightbox="media/m3_match.png":::

## <a name="define-rules-for-match-pairs"></a>Kārtulu definēšana atbilstības pāriem

Atbilstības kārtulas nosaka loģiku, kas tiks izmantota konkrētā entītiju pāra atbilstības noteikšanai. Noteikums sastāv no viena vai vairākiem nosacījumiem.

Brīdinājums blakus entītijas nosaukumam nozīmē, ka atbilstības pārim nav definēta atbilstības kārtula.

1. Atlasiet **Pievienot kārtulu** entītiju pārim, lai definētu atbilstības kārtulas.

1. Kārtulu **pievienošanas** rūtī konfigurējiet kārtulas nosacījumus.

   :::image type="content" source="media/m3_add_rule.png" alt-text="Kārtulu pievienošanas rūts ekrānuzņēmums.":::

   - **Atlasiet Entītija/lauks (pirmajā rindā)**: izvēlieties saistītu entītiju un atribūtu, lai norādītu ieraksta rekvizītu, kas, iespējams, ir unikāls klientam. Piemēram, tālruņa numuru vai e-pasta adresi. Izvairieties no saskaņošanas pēc darbības veida atribūtiem. Piemēram, visticamāk, ka pirkuma ID nebūs atbilsmes citos ierakstu veidos.

   - **Atlasiet Entītija/lauks (otrā rinda)**: izvēlieties atribūtu, kas attiecas uz pirmajā rindā norādītās entītijas atribūtu.

   - **Normalizēt**: atlasiet atlasīto atribūtu normalizēšanas opcijas.
     - **Cipari**: Pārvērš citas ciparu sistēmas, piemēram, romiešu ciparus, par arābu cipariem. *VIII* kļūst par *8*.
     - **Simboli**: noņem visus simbolus un speciālās rakstzīmes. *Head&Shoulder* kļūst par *HeadShoulder*.
     - **Teksts uz mazajiem burtiem**: pārvērš visu rakstzīmi par mazajiem burtiem. *VISI LIELIE BURTI un Virsraksta burti* kļūst par *visi lielie burti un virsraksta burti*.
     - **Tips (Tālrunis, Vārds, Adrese, Organizācija)**: Standartizē vārdus, nosaukumus, tālruņa numurus, adreses un organizācijas.
     - **Unikods uz ASCII**: pārvērš unikoda apzīmējumu par ASCII rakstzīmēm. */u00B2* kļūst par *2*.
     - **Baltstarpa**: noņem visas atstarpes. *Labdien, pasaule* kļūst par *HelloWorld*.

   - **Precizitāte**: iestata šim nosacījumam piemēroto precizitātes līmeni.
     - **Pamata**: izvēlieties no *zema (30%)*, *vidēja (60%)*, *augsta (80%)* un *precīza (100%)*. Atlasiet **Precīzi**, lai atbilstu tikai tiem ierakstiem, kas atbilst 100 procentiem.
     - **Pielāgots**: iestatiet procentuālu vērtību, kurai ierakstiem jāatbilst. Sistēma saskaņos tikai ierakstus, kas pārsniedz šo robežvērtību.

   - **Nosaukums**: kārtulas nosaukums.

1. Lai saskaņotu entītijas tikai tad, ja atribūti atbilst vairākiem nosacījumiem, atlasiet **Pievienot** > **nosacījumu Pievienot,** lai atbilstības kārtulai pievienotu papildu nosacījumus. Nosacījumi ir saistīti ar loģiku UN operatoru, un tādējādi tiek izpildīti tikai tad, ja ir izpildīti visi nosacījumi.

1. Pēc izvēles apsveriet papildu opcijas, piemēram [, izņēmumus vai](#add-exceptions-to-a-rule) pielāgotus [atbilstības nosacījumus](#specify-custom-match-conditions).

1. Atlasiet **Gatavs**, lai pabeigtu kārtulu.

1. Ja vēlaties, [pievienojiet citas kārtulas](#add-rules-to-a-match-pair).

1. Noklikšķiniet uz **Tālāk**.

> [!div class="nextstepaction"]
> [Nākamais solis: lauku apvienošana](merge-entities.md)

### <a name="add-rules-to-a-match-pair"></a>Kārtulu pievienošana atbilstības pārim

Atbilstības kārtulas pārstāv nosacījumu kopas. Lai saskaņotu entītijas pēc nosacījumiem, kuru pamatā ir vairāki atribūti, pievienojiet papildu kārtulas.

1. Atlasiet **Pievienot kārtulu** entītijai, kurai vēlaties pievienot kārtulas.

1. Izpildiet darbības sadaļā [Kārtulu definēšana atbilstības pāriem](#define-rules-for-match-pairs).

> [!NOTE]
> Kārtulu secība ir svarīga. Atbilstības algoritms mēģina saskaņot noteiktu klienta ierakstu, pamatojoties uz jūsu pirmo noteikumu, un turpina lietot otro kārtulu tikai tad, ja nav identificēta atbilstība pirmajam noteikumam.

## <a name="advanced-options"></a>Papildiespējas

### <a name="add-exceptions-to-a-rule"></a>Izņēmumu pievienošana kārtulai

Vairumā gadījumu entītiju saskaņošana noved pie unikāliem klientu profiliem ar konsolidētiem datiem. Lai dinamiski risinātu retus viltus pozitīvu un viltus negatīvu gadījumus, varat definēt atbilstības kārtulas izņēmumus. Izņēmumi tiek piemēroti pēc atbilstības noteikumu apstrādes un izvairās no visu ierakstu saskaņošanas, kas atbilst izņēmuma kritērijiem.

Piemēram, ja atbilstības noteikums apvieno uzvārds, pilsētu un dzimšanas datumu, sistēma identificē dvīņus ar tādu pašu uzvārds, kuri dzīvo vienā pilsētā ar tādu pašu profilu. Varat norādīt izņēmumu, kas neatbilst profiliem, ja apvienojamo entītiju vārds nav vienādi.

1. Rediģēšanas kārtulu **rūtī** atlasiet **Pievienot** > **izņēmumu**.

1. Norādiet izņēmuma kritērijus.

1. Atlasiet **Gatavs**, lai saglabātu kārtulu.

### <a name="specify-custom-match-conditions"></a>Pielāgotu atbilstības nosacījumu norādīšana

Var norādīt nosacījumus, kas ignorē noklusējuma atbilstības loģiku. Ir pieejamas četras iespējas:

|Iespēja  |Apraksts |Piemērs  |
|---------|---------|---------|
|Vienmēr atbilst     | Definē vērtības, kas vienmēr ir saskaņotas.         |  Vienmēr atbilst *Maikam* un *Maikam.*       |
|Nekad neatbilst     | Definē vērtības, kas nekad neatbilst.        | Nekad nesakrīt ar *Džonu* un *Džonatanu*.        |
|Pielāgota apeja     | Definē vērtības, kuras sistēmai vienmēr jāignorē atbilstības fāzē. |  Spēles laikā ignorēt vērtības *11111* un *Nezināms*.        |
|Aizstājvārda kartējums    | Vērtību definēšana, kas sistēmai būtu jāuzskata par vienu un to pašu vērtību.         | Uzskatiet *, ka Džo* ir līdzvērtīgs *Jāzepam*.        |

1. Atlasiet **Pielāgots**.

   :::image type="content" source="media/m3_match_custom.png" alt-text="Poga Pielāgots":::

1. Izvēlieties pielāgoto **tipu** un atlasiet **Lejupielādēt veidni**. Katrai atbilstības opcijai ir nepieciešama atsevišķa veidne.

1. Atveriet lejupielādēto veidnes failu un aizpildiet detalizētu informāciju. Veidnē ir ietverti lauki, kuros jānorāda entītija un entītijas primārās atslēgas vērtības, kas tiks izmantotas pielāgotajā atbilstībā. Piemēram, ja vēlaties, lai primārā atslēga *12345* no entītijas *Pārdošana* vienmēr atbilst primārajai atslēgai *34567* no entītijas *Kontaktinformācija*, aizpildiet veidni:
    - Entity1: Pārdošana
    - Entity1Key: 12345
    - Entity2: Kontaktpersona
    - Entity2Key: 34567

   Viens un tas pats veidnes fails var norādīt pielāgotās atbilstības ierakstus no vairākām entītijām.

   Ja vēlaties norādīt pielāgotu dedublikācijas atbilstību entītijai, norādiet to pašu entītiju kā Entity1 un Entity2 un iestatiet dažādas primārās atslēgas vērtības.

1. Pēc visu ignorējumu pievienošanas saglabājiet veidnes failu.

1. Ejiet uz **Dati** > **Datu avoti** un uzņemiet veidnes failus kā jaunas entītijas.

1. Pēc failu augšupielādes vēlreiz atlasiet opciju **Pielāgot**. Nolaižamajā izvēlnē atlasiet nepieciešamās entītijas un atlasiet **Gatavs**.

   :::image type="content" source="media/custom-match-overrides.png" alt-text="Dialoga ekrānuzņēmums, lai izvēlētos pielāgotas atbilstības scenārija pārlabošanu.":::

1. Pielāgotās atbilstības lietošana ir atkarīga no atbilstības opcijas, kuru vēlaties izmantot.

   - Sadaļā **Vienmēr saskaņot** vai **Nekad nesakrist** pārejiet pie nākamās darbības.
   - Apvedceļa **vai** **aizstājvārda kartēšanai** atlasiet **Rediģēt** esošā atbilstības kārtulā vai izveidojiet jaunu kārtulu. Nolaižamajā izvēlnē Normalizācija izvēlieties pielāgotās **apvedceļa** vai **aizstājvārda kartēšanas** opciju un atlasiet **Gatavs**.

1. Pielāgotajā **rūtī atlasiet** Gatavs **·**, lai lietotu pielāgoto atbilstības konfigurāciju.

> [!div class="nextstepaction"]
> [Nākamais solis: lauku apvienošana](merge-entities.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
