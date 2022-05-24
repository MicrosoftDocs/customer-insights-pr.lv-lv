---
title: Dublikātu noņemšana pirms datu apvienošanas
description: Otrais apvienošanas procesa solis ir izvēlēties, kuru ierakstu paturēt, atrodot dublikātus.
recommendations: false
ms.date: 04/22/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-map
- ci-match
- customerInsights
ms.openlocfilehash: 27dff3551ab411a12c273536d7431d651c48573e
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 05/11/2022
ms.locfileid: "8742974"
---
# <a name="remove-duplicates-before-unifying-data"></a>Dublikātu noņemšana pirms datu apvienošanas

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

Šī apvienošanas darbība pēc izvēles ļauj iestatīt kārtulas ierakstu dublikātu apstrādei entītijā. *Deduplication* identificē ierakstu dublikātus un apvieno tos vienā ierakstā. Avota ieraksti tiek saistīti ar sapludināto ierakstu, izmantojot alternatīvus ID. Ja kārtulas nav konfigurētas, tiek lietotas sistēmas definētās kārtulas.

## <a name="include-enriched-entities-preview"></a>Bagātināto entītiju iekļaušana (priekšskatījums)

Ja bagātinājāt entītijas datu avots līmenī, lai palīdzētu uzlabot apvienošanās rezultātus, atlasiet tos. Papildinformāciju skatiet rakstā [Datu avotu bagātināšana](data-sources-enrichment.md).

1. **Lapā Ierakstu dublikāti** lapas augšdaļā atlasiet **Izmantot bagātinātas entītijas**.

1. **Rūtī Bagātinātu entītiju** izmantošana izvēlieties vienu vai vairākas bagātinātas entītijas.

1. Atlasiet **Gatavs**.

## <a name="define-deduplication-rules"></a>Definēt deduplikācijas kārtulas

1. **Lapā Ierakstu dublikāti** atlasiet entītiju un atlasiet **Pievienot kārtulu**, lai definētu deduplikācijas kārtulas.

   :::image type="content" source="media/m3_duplicates_showmore.png" alt-text="Ierakstu dublikātu lapu ekrānuzņēmums ar iezīmētu opciju Rādīt vairāk":::

   1. Kārtulu **pievienošanas** rūtī ievadiet šādu informāciju:
      - **Atlasiet lauku**: izvēlieties no tās entītijas pieejamo lauku saraksta, kuru vēlaties pārbaudīt, vai nav dublikātu. Izvēlieties laukus, kas, visticamāk, ir unikāli katram atsevišķam klientam. Piemēram, e-pasta adrese vai vārda, pilsētas un tālruņa numura kombinācija.
      - **Normalizēt**: atlasiet atlasīto atribūtu normalizēšanas opcijas.
        - **Cipari**: Pārvērš citas ciparu sistēmas, piemēram, romiešu ciparus, par arābu cipariem. *VIII* kļūst par *8*.
        - **Simboli**: noņem visus simbolus un speciālās rakstzīmes. *Head&Shoulder* kļūst par *HeadShoulder*.
        - **Teksts uz mazajiem burtiem: pārvērš visu rakstzīmi par mazajiem burtiem**. *VISI LIELIE BURTI un Virsraksta burti* kļūst par *visi lielie burti un virsraksta burti*.
        - **Tips (tālrunis, vārds, adrese, organizācija)**: standartizē vārdus, nosaukumus, tālruņa numurus, adreses utt.
        - **Unikods uz ASCII**: pārvērš unikoda apzīmējumu par ASCII rakstzīmēm. */u00B2* kļūst par *2*.
        - **Baltstarpa**: noņem visas atstarpes. *Labdien, pasaule* kļūst par *HelloWorld*.
      - **Precizitāte**: iestata šim nosacījumam piemēroto precizitātes līmeni.
        - **Pamata**: izvēlieties no *zema (30%)*, *vidēja (60%)*, *augsta (80%)* un *precīza (100%)*. Atlasiet **Precīzi**, lai atbilstu tikai tiem ierakstiem, kas atbilst 100 procentiem.
        - **Pielāgots**: iestatiet procentuālu vērtību, kurai ierakstiem jāatbilst. Sistēma saskaņos tikai ierakstus, kas pārsniedz šo robežvērtību.
      - **Nosaukums**: kārtulas nosaukums.

      :::image type="content" source="media/m3_duplicates_add.png" alt-text="Dublikātu noņemšanas rūts pievienošanas rūts ekrānuzņēmums.":::

   1. Pēc izvēles atlasiet **Pievienot nosacījumu** > **Pievienot**, lai kārtulai pievienotu papildu nosacījumus. Nosacījumi ir saistīti ar loģiku UN operatoru, un tādējādi tiek izpildīti tikai tad, ja ir izpildīti visi nosacījumi.

   1. Pēc izvēles pievienojiet **izņēmumu** > **,** lai [kārtulai](match-entities.md#add-exceptions-to-a-rule) pievienotu izņēmumus. Izņēmumi tiek izmantoti, lai risinātu retus viltus pozitīvu un viltus negatīvu gadījumus.

   1. Atlasiet **Gatavs**, lai izveidotu kārtulu.

1. Ja vēlaties, [pievienojiet citas kārtulas](#define-deduplication-rules).

1. Atlasiet entītiju un pēc tam **rediģējiet sapludināšanas preferences**.

1. Sapludināšanas **preferenču** rūtī:
   1. Izvēlieties vienu no trim opcijām, lai noteiktu, kurš ieraksts jāsaglabā, ja tiek atrasts dublikāts:
      - **Lielākā daļa** : tiek identificēts ieraksts, kuram ir visvairāk aizpildīto atribūtu lauku kā uzvarētāju ieraksts. Tā ir noklusējuma sapludināšanas opcija.
      - **Visjaunākais** : Nosaka uzvarētāju, balstoties uz augšupielādes datumu. Ir nepieciešams datums vai skaitlisks lauks, lai definētu augšupielādes datumu.
      - **Visvecākais** : Nosaka uzvarētāju, balstoties uz visvecāko augšupielādes datumu. Ir nepieciešams datums vai skaitlisks lauks, lai definētu augšupielādes datumu.
      
      Neizšķirta gadījumā uzvarētāja ieraksts ir tas, kuram ir MAX(PK) vai lielāka primārā atslēgas vērtība.
      
   1. Pēc izvēles, lai definētu sapludināšanas preferences atsevišķiem entītijas atribūtiem, rūts apakšdaļā atlasiet **Papildu**. Piemēram, varat izvēlēties saglabāt jaunāko e-pastu UN vispilnīgāko adresi no dažādiem ierakstiem. Izvērsiet entītiju, lai skatītu visus tās atribūtus un definētu, kuru opciju izmantot atsevišķiem atribūtiem. Ja izvēlaties opciju, kuras pamatā ir recency, ir jānorāda arī datuma/laika lauks, kas definē korekcijas koeficientu.

      :::image type="content" source="media/m3_adv_merge.png" alt-text="Papildu sapludināšanas preferenču rūts, kurā redzams nesenais e-pasts un pilnā adrese":::

   1. Atlasiet **Gatavs**, lai lietotu sapludināšanas preferences.

1. Pēc deduplicācijas kārtulu un sapludināšanas preferenču definēšanas atlasiet **Tālāk**.
  
> [!div class="nextstepaction"]
> [Nākamais solis vienai entītijai: lauku apvienošana: lauku apvienošana](merge-entities.md)

> [!div class="nextstepaction"]
> [Nākamais solis vairākām entītijām: nosacījumu saskaņošana](match-entities.md)

## <a name="deduplication-output-as-an-entity"></a>Dedublikācijas izvade kā entītija

Paplašināšanas process katrai avota entītijai izveido jaunu paplašinātu entītiju. Šīs entītijas var atrast kopā ar **ConflationMatchPairs:CustomerInsights** sadaļā **Sistēma** lapā **Entītijas** ar nosaukumu **Deduplication_DataSource_Entity**.

Dedublikācijas izvades entītija ietver šādu informāciju:

- ID/ Atslēgas
  - Primārās atslēgas un alternatīvā ID lauki. Alternatīvais ID lauks sastāv no visiem alternatīvajiem ID, kas identificēti ierakstam.
  - Deduplication_GroupId lauks rāda grupu vai klasteru, kas identificēts entītijā, kas grupē visus līdzīgos ierakstus, pamatojoties uz norādītajiem dedublikācijas laukiem. To izmanto sistēmas apstrādes nolūkiem. Ja nav norādītas manuālas dedublikācijas kārtulas un tiek lietotas sistēmas definētās dedublikācijas kārtulas, varat neatrast šo lauku dedublikācijas izvades entītijā.
  - Deduplication_WinnerId: šajā laukā ir norādīts identificēto grupu vai klasteru uzvarētāja ID. Ja Deduplication_WinnerId vērtība ir tāda pati kā ieraksta primārās atslēgas vērtība, tas nozīmē, ka ieraksts ir uzvarētāja ieraksts.
- Lauki, ko lieto dedublikācijas kārtulu definēšanai.
- Kārtulu un punktu skaita lauki, lai apzīmētu, kuras no dedublikācijas kārtulām tika lietotas, un punktu skaitu, kas tika atgriezts, veicot atbilstošu aizstāšanu.

[!INCLUDE[footer-include](includes/footer-banner.md)]
