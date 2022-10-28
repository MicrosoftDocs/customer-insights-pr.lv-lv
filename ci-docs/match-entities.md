---
title: Atbilstoši nosacījumi datu apvienošanai
description: Savienojiet datus, lai izveidotu vienotus klientu profilus.
recommendations: false
ms.date: 10/07/2022
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
ms.openlocfilehash: bbd2c5f441b85460250c11f02358ea67260278d6
ms.sourcegitcommit: 52ea58c872b10f1e6f9d120be93df93cca1a12dd
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 10/26/2022
ms.locfileid: "9721530"
---
# <a name="match-conditions-for-data-unification"></a>Atbilstoši nosacījumi datu apvienošanai

Šī apvienošanas darbība definē atbilstības secību un kārtulas starpentītiju savstarpējai saskaņošanai. Šim solim ir nepieciešamas vismaz divas entītijas.

> [!NOTE]
> Kad esat izveidojis atbilstības nosacījumus un atlasījis **Tālāk**, jūs nevarat noņemt atlasīto entītiju vai atribūtu. Ja nepieciešams, atlasiet **Atpakaļ**, lai pirms turpinātu, pārskatītu atlasītās entītijas un atribūtus.

[!INCLUDE [m3-first-run-note](includes/m3-first-run-note.md)]

## <a name="include-enriched-entities-preview"></a>Bagātināto entītiju iekļaušana (priekšskatījums)

Ja bagātinājāt entītijas datu avots līmenī, lai palīdzētu uzlabot apvienošanas rezultātus, atlasiet tās. Papildinformāciju skatiet sadaļā [Datu avotu bagātināšana](data-sources-enrichment.md). Ja lapā Ierakstu **dublikāti atlasījāt bagātinātas entītijas**, tās nav jāatlasa vēlreiz.

1. Lapā Atbilstoši nosacījumi **lapas augšdaļā atlasiet** Izmantot bagātinātas entītijas **.**

1. Rūtī Izmantot **bagātinātas entītijas izvēlieties vienu vai vairākas bagātinātas entītijas**.

1. Atlasiet **Gatavs**.

## <a name="specify-the-match-order"></a>Atbilstības noteikšanas secības norādīšana

Katra atbilstība apvieno divas vai vairākas entītijas vienā, konsolidētā entītijā. Vienlaikus tiek glabāti unikālie klientu ieraksti. Atbilstības secība norāda secību, kādā sistēma mēģina saskaņot ierakstus.

> [!IMPORTANT]
> Pirmā entītija tiek saukta par primāro entītiju, kas kalpo par pamatu jūsu vienotajiem profiliem. Šai entītijai tiks pievienotas papildu entītijas, kas ir atlasītas.
>
> Svarīgi apsvērumi:
>
> - Kā primāro entītiju izvēlieties entītiju ar vispilnīgākajiem un uzticamākajiem profila datiem par klientiem.
> - Kā primāro entītiju izvēlieties entītiju, kurai ir vairāki atribūti, kas ir kopīgi ar citām entītijām (piemēram, vārds, tālruņa numurs vai e-pasta adrese).

1. Lapā **Atbilstoši nosacījumi** izmantojiet augšupvērsto un lejupvērsto bultiņu, lai entītijas pārvietotu vajadzīgajā secībā, vai velciet un nometiet tās. Piemēram, atlasiet **e-komercijas klientus** kā primāro entītiju un **loyCustomers** kā otro entītiju.

1. Lai katrs entītijas ieraksts būtu unikāls klients neatkarīgi no tā, vai atbilstība ir atrasta, atlasiet **Iekļaut visus ierakstus**. Visi šīs entītijas ieraksti, kas neatbilst ierakstiem nevienā citā entītijā, tiek iekļauti vienotajā profilā. Ierakstus, kuriem nav atbilstības, sauc par singletons.
  
Primārā entītija Kontaktpersonas:e-komercija *tiek saskaņota ar nākamo entītiju* *CustomerLoyalty:Loyalty*. Datu kopa, kas tiek iegūta, veicot pirmo atbilstības darbību, tiek saskaņota ar tālāk norādīto entītiju, ja jums ir vairāk nekā divas entītijas.

:::image type="content" source="media/m3_match.png" alt-text="Atlasītās entītiju atbilstības secības ekrānuzņēmums." lightbox="media/m3_match.png":::

## <a name="define-rules-for-match-pairs"></a>Kārtulu definēšana atbilstības pāriem

Atbilstības kārtulas nosaka loģiku, kas tiks izmantota konkrētā entītiju pāra atbilstības noteikšanai. Noteikums sastāv no viena vai vairākiem nosacījumiem.

Brīdinājums blakus entītijas nosaukumam nozīmē, ka atbilstības pārim nav definēta atbilstības kārtula.

1. Atlasiet **Pievienot kārtulu entītiju pārim, lai definētu atbilstības kārtulas**.

1. Rūtī Pievienot **kārtulu konfigurējiet kārtulas** nosacījumus.

   :::image type="content" source="media/m3_add_rule.png" alt-text="Ekrānuzņēmums, kurā redzama kārtulas pievienošanas rūts.":::

   - **Atlasiet Entītija/lauks (pirmā rinda)**: izvēlieties entītiju un atribūtu, kas, visticamāk, ir unikāls klientam. Piemēram, tālruņa numuru vai e-pasta adresi. Izvairieties no saskaņošanas pēc darbības veida atribūtiem. Piemēram, visticamāk, ka pirkuma ID nebūs atbilsmes citos ierakstu veidos.

   - **Atlasiet Entītija/lauks (otrā rinda):** izvēlieties atribūtu, kas ir saistīts ar pirmajā rindā norādītās entītijas atribūtu.

   - **Normalizēt**: atlasiet atlasīto atribūtu normalizēšanas opcijas.
     - **Cipari**: pārvērš citas ciparu sistēmas, piemēram, romiešu ciparus, par arābu cipariem. *VIII* kļūst par *8*.
     - **Simboli:** noņem visus simbolus un speciālās rakstzīmes. *Head&Shoulder* kļūst par *HeadShoulder*.
     - **Teksts uz mazajiem burtiem: pārvērš visas rakstzīmes par mazajiem burtiem**. *VISI LIELIE BURTI un Virsraksta burti* kļūst par *visi lielie burti un virsraksta burti*.
     - **Tips (tālrunis, vārds, adrese, organizācija)**: standartizē vārdus, amatus, tālruņa numurus, adreses un organizācijas.
     - **Unikods uz ASCII: konvertē unikoda apzīmējumu par ASCII** rakstzīmēm. */u00B2* kļūst par *2*.
     - **Baltā atstarpe: noņem visas atstarpes**. *Labdien, pasaule* kļūst par *HelloWorld*.

   - **Precizitāte**: iestata šim nosacījumam piemēroto precizitātes līmeni.
     - **Pamata**: izvēlieties opciju Zems *(30%), Vidējs (60%),* *Augsts (80%)* un *Precīzs (100%)* *·*. Atlasiet **Precīzs**, lai saskaņotu tikai tos ierakstus, kas atbilst 100 procentiem.
     - **Pielāgots**: iestatiet procentuālu vērtību, kurai ierakstiem jāatbilst. Sistēma saskaņos tikai ierakstus, kas pārsniedz šo robežvērtību.

   - **Nosaukums**: kārtulas nosaukums.

1. Lai saskaņotu entītijas tikai tad, ja atribūti atbilst vairākiem nosacījumiem, atlasiet **Pievienot** > **nosacījumu**, lai atbilstības kārtulai pievienotu papildu nosacījumus. Nosacījumi ir saistīti ar loģiku UN operatoru, un tādējādi tiek izpildīti tikai tad, ja ir izpildīti visi nosacījumi.

1. Pēc izvēles apsveriet papildu opcijas, piemēram, [izņēmumus](#add-exceptions-to-a-rule) vai [pielāgotas atbilstības nosacījumus](#specify-custom-match-conditions).

1. Atlasiet **Gatavs**, lai pabeigtu kārtulu.

1. Ja vēlaties, [pievienojiet citas kārtulas](#add-rules-to-a-match-pair).

1. Noklikšķiniet uz **Tālāk**.

> [!div class="nextstepaction"]
> [Nākamā darbība: lauku apvienošana](merge-entities.md)

### <a name="add-rules-to-a-match-pair"></a>Kārtulu pievienošana atbilstības pārim

Atbilstības kārtulas pārstāv nosacījumu kopas. Lai saskaņotu entītijas pēc nosacījumiem, kuru pamatā ir vairāki atribūti, pievienojiet papildu kārtulas.

1. Entītijai, kurai vēlaties pievienot kārtulas, atlasiet **Pievienot kārtulu**.

1. Izpildiet darbības sadaļā [Kārtulu definēšana atbilstības pāriem](#define-rules-for-match-pairs).

> [!NOTE]
> Kārtulu secība ir svarīga. Atbilstības algoritms mēģina saskaņot konkrētu klienta ierakstu, pamatojoties uz jūsu pirmo kārtulu, un turpina otro kārtulu tikai tad, ja ar pirmo kārtulu nav identificētas atbilstības.

## <a name="advanced-options"></a>Papildiespējas

### <a name="add-exceptions-to-a-rule"></a>Izņēmumu pievienošana kārtulai

Vairumā gadījumu entītiju atbilstības noteikšanas rezultātā tiek izveidoti unikāli klientu profili ar konsolidētiem datiem. Lai novērstu retus aplami pozitīvu un aplami negatīvu gadījumu gadījumus, definējiet atbilstības kārtulas izņēmumus. Izņēmumi tiek piemēroti pēc atbilstības kārtulu apstrādes un izvairās no visu ierakstu atbilstības, kas atbilst izņēmuma kritērijiem.

Piemēram, ja atbilstības kārtula apvieno uzvārds, pilsētu un dzimšanas datumu, sistēma identificēs dvīņus ar tādu pašu uzvārds, kuri dzīvo vienā pilsētā ar to pašu profilu. Varat norādīt izņēmumu, kas neatbilst profiliem, ja vārds apvienotajās entītijās nav vienādas.

1. **Kārtulu** rediģēšanas rūtī atlasiet **Pievienot** > **izņēmumu**.

1. Norādiet izņēmuma kritērijus.

1. Atlasiet **Gatavs**, lai saglabātu kārtulu.

### <a name="specify-custom-match-conditions"></a>Pielāgotu atbilstības nosacījumu norādīšana

Norādiet nosacījumus, kas ignorē noklusējuma atbilstības loģiku. Ir pieejamas četras iespējas:

|Iespēja  |Apraksts |Piemērs  |
|---------|---------|---------|
|Vienmēr atbilst     | Definē primāro atslēgu vērtības, kas vienmēr ir saskaņotas.         |  Vienmēr saskaņojiet rindu ar primāro atslēgu 12345 *ar rindu ar primāro atslēgu* *54321*.       |
|Nekad neatbilst     | Definē vērtības primārajām atslēgām, kas nekad nesakrīt.        | Nekad nesaskaņojiet rindu ar primāro atslēgu 12345 *ar rindu ar primāro atslēgu* *54321*.        |
|Apeja            | Definē vērtības, kuras sistēmai vienmēr jāignorē atbilstības fāzē. |  Spēles laikā ignorējiet vērtības *11111* un *Nezināms*.        |
|Aizstājvārda kartējums    | Vērtību definēšana, kas sistēmai būtu jāuzskata par tādu pašu vērtību.         | Uzskatiet Džo *par līdzvērtīgu Džozefam* *.*        |

1. Atlasiet **Pielāgots**.

   :::image type="content" source="media/m3_match_custom.png" alt-text="Pielāgota poga":::

1. Izvēlieties tipu Pielāgots **un atlasiet** Lejupielādēt veidni **.** Pārdēvējiet veidni, neizmantojot atstarpes. Katrai atbilstības opcijai izmantojiet atsevišķu veidni.

1. Atveriet lejupielādēto veidnes failu un aizpildiet informāciju. Veidnē ir ietverti lauki, kuros jānorāda entītija un entītijas primārās atslēgas vērtības, kas tiks izmantotas pielāgotajā atbilstībā. Entītiju nosaukumi ir reģistrjutīgi. Piemēram, ja vēlaties, lai primārā atslēga *12345* no entītijas *Pārdošana* vienmēr atbilst primārajai atslēgai *34567* no entītijas *Kontaktinformācija*, aizpildiet veidni:
   - Entity1: Pārdošana
   - Entity1Key: 12345
   - Entity2: Kontaktpersona
   - Entity2Key: 34567

   Viens un tas pats veidnes fails var norādīt pielāgotās atbilstības ierakstus no vairākām entītijām.

   > [!NOTE]
   > Ja vēlaties norādīt pielāgotu dedublikācijas atbilstību entītijai, norādiet to pašu entītiju kā Entity1 un Entity2 un iestatiet dažādas primārās atslēgas vērtības. Lai izmantotu pielāgoto atbilstību, entītijai ir jādefinē vismaz viena deduplikācijas kārtula.

1. Pēc visu ignorēšanas failu pievienošanas saglabājiet veidnes failu.

1. Ejiet uz **Dati** > **Datu avoti** un uzņemiet veidnes failus kā jaunas entītijas.

1. Pēc failu augšupielādes vēlreiz atlasiet opciju **Pielāgots**. Nolaižamajā izvēlnē atlasiet nepieciešamās entītijas un atlasiet **Gatavs**.

   :::image type="content" source="media/custom-match-overrides.png" alt-text="Dialoga ekrānuzņēmums, lai izvēlētos pielāgotas atbilstības scenārija pārlabošanu.":::

1. Pielāgotās atbilstības lietošana ir atkarīga no atbilstības opcijas, kuru vēlaties izmantot.

   - Sadaļā **Vienmēr atbilstība** vai **Nekad nesakrītiet**, pārejiet pie nākamās darbības.
   - Sadaļā Apvedceļš **vai aizstājvārdu** kartēšana **atlasiet** Rediģēt **esošu atbilstības kārtulu vai** izveidojiet jaunu kārtulu. Nolaižamajā izvēlnē Normalizācijas izvēlieties opciju Pielāgots **apvedceļš vai** Aizstājvārdu **kartēšana** un atlasiet **Gatavs**.

1. Pielāgotajā **rūtī atlasiet** **Gatavs**, lai lietotu pielāgotās atbilstības konfigurāciju.

   Katrs uzņemtais veidnes fails ir sava datu avots. Ja tiek atklāti ieraksti, kuriem nepieciešama īpaša atbilstības noteikšana, atjauniniet atbilstošo datu avots. Atjauninājums tiks izmantots nākamā apvienošanas procesa laikā. Piemēram, jūs identificējat dvīņus ar gandrīz tādu pašu vārdu, kas dzīvo vienā adresē, kas tika apvienota kā viena persona. Atjauniniet datu avots, lai identificētu dvīņus kā atsevišķus, unikālus ierakstus.

> [!div class="nextstepaction"]
> [Nākamā darbība: lauku apvienošana](merge-entities.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
