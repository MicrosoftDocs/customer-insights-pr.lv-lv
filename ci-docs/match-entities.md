---
title: Atbilstības nosacījumi datu apvienošanai
description: Savienojiet datus, lai izveidotu vienotus klientu profilus.
recommendations: false
ms.date: 07/27/2022
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
ms.openlocfilehash: eaa3409aaa7541dc88953336942e43afaf6511c6
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304666"
---
# <a name="match-conditions-for-data-unification"></a>Atbilstības nosacījumi datu apvienošanai

Šis apvienošanas solis definē atbilstības secību un kārtulas vairāku entītiju atbilstībai. Šai darbībai ir nepieciešamas vismaz divas entītijas.

> [!NOTE]
> Kad esat izveidojis atbilstības nosacījumus un atlasījis **Tālāk**, nevarat noņemt atlasīto entītiju vai atribūtu. Ja nepieciešams, atlasiet **Atpakaļ**, lai pirms turpināšanas pārskatītu atlasītās entītijas un atribūtus.

[!INCLUDE [m3-first-run-note](includes/m3-first-run-note.md)]

## <a name="include-enriched-entities-preview"></a>Iekļaut bagātinātas entītijas (priekšskatījums)

Ja esat bagātinājis entītijas datu avots līmenī, lai palīdzētu uzlabot apvienošanas rezultātus, atlasiet tās. Papildinformāciju skatiet sadaļā [Bagātināšana datu avotiem](data-sources-enrichment.md). Ja lapā Dublēt ierakstus **atlasījāt bagātinātas entītijas**, tās nav jāatlasa vēlreiz.

1. **Lapā Atbilstības nosacījumi** lapas augšdaļā atlasiet **Izmantot bagātinātas entītijas**.

1. **Rūtī Bagātinātu entītiju** izmantošana izvēlieties vienu vai vairākas bagātinātas entītijas.

1. Atlasiet **Gatavs**.

## <a name="specify-the-match-order"></a>Atbilstības noteikšanas secības norādīšana

Katra atbilstība apvieno divas vai vairākas entītijas vienā, konsolidētā entītijā. Vienlaikus tiek glabāti unikālie klientu ieraksti. Atbilstības secība norāda secību, kādā sistēma mēģina saskaņot ierakstus.

> [!IMPORTANT]
> Pirmo entītiju sauc par primāro entītiju, kas kalpo par pamatu jūsu vienotajiem profiliem. Šai entītijai tiks pievienotas atlasītās papildu entītijas.
>
> Svarīgi apsvērumi:
>
> - Kā primāro entītiju izvēlieties entītiju ar vispilnīgākajiem un uzticamākajiem profila datiem par jūsu klientiem.
> - Kā primāro entītiju izvēlieties entītiju, kurai ir vairāki atribūti, kas ir kopīgi ar citām entītijām (piemēram, vārds, tālruņa numurs vai e-pasta adrese).

1. **Lapā Atbilstības nosacījumi** izmantojiet augšupvērsto un lejupvērsto bultiņu, lai pārvietotu entītijas vajadzīgajā secībā, vai velciet un nometiet tās. Piemēram, atlasiet **e-komercijaskomisijas kā primāro entītiju** un **loyCustomers** kā otro entītiju.

1. Lai katrs entītijas ieraksts būtu unikāls klients neatkarīgi no atbilstības atrašanas, atlasiet **Iekļaut visus ierakstus**. Visi ieraksti šajā entītijā, kas neatbilst ierakstiem nevienā citā entītijā, tiek iekļauti vienotajā profilā. Ierakstus, kuriem nav atbilstības, sauc par singletoniem.
  
Primārā entītija *Kontaktpersonas:e-komercija* tiek saskaņota ar nākamo entītiju *CustomerLoyalty:Loyalty*. Datu kopa, kas izriet no pirmās atbilstības darbības, tiek saskaņota ar tālāk norādīto entītiju, ja jums ir vairāk nekā divas entītijas.

:::image type="content" source="media/m3_match.png" alt-text="Entītiju atlasītās atbilstības secības ekrānuzņēmums." lightbox="media/m3_match.png":::

## <a name="define-rules-for-match-pairs"></a>Kārtulu definēšana atbilstības pāriem

Atbilstības kārtulas nosaka loģiku, kas tiks izmantota konkrētā entītiju pāra atbilstības noteikšanai. Noteikums sastāv no viena vai vairākiem nosacījumiem.

Brīdinājums blakus entītijas nosaukumam nozīmē, ka atbilstības pārim nav definēts neviens atbilstības noteikums.

1. Atlasiet **Pievienot kārtulu** entītiju pārim, lai definētu atbilstības kārtulas.

1. **Rūtī Pievienot kārtulu** konfigurējiet kārtulas nosacījumus.

   :::image type="content" source="media/m3_add_rule.png" alt-text="Kārtulu pievienošanas rūts ekrānuzņēmums.":::

   - **Atlasiet Entītija/Lauks (pirmā rinda)**: izvēlieties entītiju un atribūtu, kas, iespējams, ir unikāls debitoram. Piemēram, tālruņa numuru vai e-pasta adresi. Izvairieties no saskaņošanas pēc darbības veida atribūtiem. Piemēram, visticamāk, ka pirkuma ID nebūs atbilsmes citos ierakstu veidos.

   - **Atlasiet Entītija/Lauks (otrā rinda)**: izvēlieties atribūtu, kas attiecas uz pirmajā rindā norādītā entītijas atribūtu.

   - **Normalizēt**: atlasiet atlasīto atribūtu normalizēšanas opcijas.
     - **Cipari**: pārvērš citas ciparu sistēmas, piemēram, romiešu ciparus, par arābu cipariem. *VIII* kļūst par *8*.
     - **Simboli**: Noņem visus simbolus un speciālās rakstzīmes. *Head&Shoulder* kļūst par *HeadShoulder*.
     - **Teksts ar mazajiem burtiem**: pārvērš visas rakstzīmes par mazajiem burtiem. *VISI LIELIE BURTI un Virsraksta burti* kļūst par *visi lielie burti un virsraksta burti*.
     - **Tips (tālrunis, vārds, adrese, organizācija)**: standartizē vārdus, nosaukumus, tālruņa numurus, adreses un organizācijas.
     - **Unikods uz ASCII**: pārvērš unikoda apzīmējumu par ASCII rakstzīmēm. */u00B2* kļūst par *2*.
     - **Atstarpe**: noņem visas atstarpes. *Labdien, pasaule* kļūst par *HelloWorld*.

   - **Precizitāte**: iestata šim nosacījumam piemēroto precizitātes līmeni.
     - **Pamata**: izvēlieties no *zema (30%)*, *vidēja (60%)*, *augsta (80%)* un *precīza (100%).*. Atlasiet **Precīzs**, lai atbilstu tikai tiem ierakstiem, kas atbilst 100 procentiem.
     - **Pielāgots**: iestatiet procentuālu vērtību, kurai ierakstiem jāatbilst. Sistēma saskaņos tikai ierakstus, kas pārsniedz šo robežvērtību.

   - **Nosaukums**: kārtulas nosaukums.

1. Lai saskaņotu entītijas tikai tad, ja atribūti atbilst vairākiem nosacījumiem, atlasiet **Pievienot** > **nosacījumu** pievienot, lai atbilstības kārtulai pievienotu papildu nosacījumus. Nosacījumi ir saistīti ar loģiku UN operatoru, un tādējādi tiek izpildīti tikai tad, ja ir izpildīti visi nosacījumi.

1. Ja vēlaties, apsveriet papildu opcijas, piemēram [, izņēmumus vai](#add-exceptions-to-a-rule) pielāgotas [atbilstības nosacījumus](#specify-custom-match-conditions).

1. Atlasiet **Gatavs**, lai pabeigtu kārtulu.

1. Ja vēlaties, [pievienojiet citas kārtulas](#add-rules-to-a-match-pair).

1. Noklikšķiniet uz **Tālāk**.

> [!div class="nextstepaction"]
> [Nākamā darbība: Lauku apvienošana](merge-entities.md)

### <a name="add-rules-to-a-match-pair"></a>Kārtulu pievienošana atbilstības pārim

Atbilstības kārtulas pārstāv nosacījumu kopas. Lai saskaņotu entītijas pēc nosacījumiem, kuru pamatā ir vairāki atribūti, pievienojiet papildu kārtulas.

1. Atlasiet **Pievienot kārtulu** entītijai, kurai vēlaties pievienot kārtulas.

1. Izpildiet darbības sadaļā [Kārtulu definēšana atbilstības pāriem](#define-rules-for-match-pairs).

> [!NOTE]
> Kārtulu secība ir svarīga. Atbilstības algoritms mēģina saskaņot konkrētu klienta ierakstu, pamatojoties uz jūsu pirmo kārtulu, un turpina lietot otro kārtulu tikai tad, ja ar pirmo kārtulu nav identificētas atbilstības.

## <a name="advanced-options"></a>Papildiespējas

### <a name="add-exceptions-to-a-rule"></a>Izņēmumu pievienošana kārtulai

Vairumā gadījumu atbilstība entītijai rada unikālus klientu profilus ar konsolidētiem datiem. Lai novērstu retus aplami pozitīvus un aplami negatīvus gadījumus, definējiet atbilstības kārtulas izņēmumus. Izņēmumi tiek piemēroti pēc atbilstības kārtulu apstrādes un izvairās no visu ierakstu atbilstības, kas atbilst izņēmuma kritērijiem.

Piemēram, ja jūsu atbilstības kārtula apvieno uzvārds, pilsētu un dzimšanas datumu, sistēma identificēs dvīņus ar tādu pašu uzvārds, kuri dzīvo tajā pašā pilsētā, kur tas pats profils. Varat norādīt izņēmumu, kas neatbilst profiliem, ja vārds entītijās, kuras apvienojat, nav vienādas.

1. **Rūtī Rediģēt kārtulu** atlasiet **Pievienot** > **izņēmumu**.

1. Norādiet izņēmuma kritērijus.

1. Atlasiet **Gatavs**, lai saglabātu kārtulu.

### <a name="specify-custom-match-conditions"></a>Pielāgotu atbilstības nosacījumu norādīšana

Varat norādīt nosacījumus, kas ignorē noklusējuma atbilstības loģiku. Ir pieejamas četras iespējas:

|Iespēja  |Apraksts |Piemērs  |
|---------|---------|---------|
|Vienmēr atbilst     | Definē vērtības, kas vienmēr tiek saskaņotas.         |  Vienmēr atbilst *Maikam* un *Maikam*.       |
|Nekad neatbilst     | Definē vērtības, kas nekad nesakrīt.        | Nekad nesakrīt ar *Džonu* un *Džonatanu*.        |
|Apeja            | Definē vērtības, kuras sistēmai vienmēr ir jāignorē atbilstības fāzē. |  Spēles laikā ignorējiet vērtības *11111* un *Nezināms*.        |
|Aizstājvārda kartējums    | Vērtību definēšana, kas sistēmai būtu jāuzskata par vienu un to pašu vērtību.         | Uzskatiet, ka *Džo ir līdzvērtīgs Džozefam* *.*        |

1. Atlasiet **Pielāgots**.

   :::image type="content" source="media/m3_match_custom.png" alt-text="Poga Pielāgots":::

1. Izvēlieties veidu Pielāgots **un atlasiet** Lejupielādēt veidni **.** Katrai atbilstības opcijai ir nepieciešama atsevišķa veidne.

1. Atveriet lejupielādēto veidnes failu un aizpildiet detalizētu informāciju. Veidnē ir ietverti lauki, kuros jānorāda entītija un entītijas primārās atslēgas vērtības, kas tiks izmantotas pielāgotajā atbilstībā. Piemēram, ja vēlaties, lai primārā atslēga *12345* no entītijas *Pārdošana* vienmēr atbilst primārajai atslēgai *34567* no entītijas *Kontaktinformācija*, aizpildiet veidni:
    - Entity1: Pārdošana
    - Entity1Key: 12345
    - Entity2: Kontaktpersona
    - Entity2Key: 34567

   Viens un tas pats veidnes fails var norādīt pielāgotās atbilstības ierakstus no vairākām entītijām.

   Ja vēlaties norādīt pielāgotu dedublikācijas atbilstību entītijai, norādiet to pašu entītiju kā Entity1 un Entity2 un iestatiet dažādas primārās atslēgas vērtības.

1. Pēc visu ignorējumu pievienošanas saglabājiet veidnes failu.

1. Ejiet uz **Dati** > **Datu avoti** un uzņemiet veidnes failus kā jaunas entītijas.

1. Pēc failu augšupielādes vēlreiz atlasiet opciju **Pielāgots**. Nolaižamajā izvēlnē atlasiet nepieciešamās entītijas un atlasiet **Gatavs**.

   :::image type="content" source="media/custom-match-overrides.png" alt-text="Dialoga ekrānuzņēmums, lai izvēlētos pielāgotas atbilstības scenārija pārlabošanu.":::

1. Pielāgotās atbilstības lietošana ir atkarīga no atbilstības opcijas, kuru vēlaties izmantot.

   - Lai **vienmēr atbilstu** vai **nekad nesakristu**, pārejiet pie nākamās darbības.
   - Sadaļā **Apiešana** vai **aizstājvārda kartēšana** atlasiet **Rediģēt** esošā atbilstības kārtulā vai izveidojiet jaunu kārtulu. Nolaižamajā izvēlnē Normalizācijas izvēlieties opciju **Pielāgots apvedceļš** vai **Aizstājvārda kartēšana** un atlasiet **Gatavs**.

1. Pielāgotajā **rūtī** atlasiet **Gatavs**, lai lietotu pielāgotās atbilstības konfigurāciju.

> [!div class="nextstepaction"]
> [Nākamā darbība: Lauku apvienošana](merge-entities.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
