---
title: Dublikātu noņemšana pirms datu apvienošanas
description: Otrais apvienošanās procesa solis ir izvēlēties, kuru ierakstu saglabāt, kad tiek atrasti dublikāti.
recommendations: false
ms.date: 08/01/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: sstabbert
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-map
- ci-match
- customerInsights
ms.openlocfilehash: 3f84c1c149f0befcbe489ccdd8a666ce6d5d798a
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304482"
---
# <a name="remove-duplicates-before-unifying-data"></a>Dublikātu noņemšana pirms datu apvienošanas

Šī neobligātā apvienošanas darbība ļauj iestatīt kārtulas ierakstu **dublikātu likvidēšanai entītijā**. Deduplikation identificē vairākus ierakstus klientam un atlasa labāko ierakstu, kas jāsaglabā (pamatojoties uz pamata sapludināšanas preferencēm), vai sapludina ierakstus vienā (pamatojoties uz papildu sapludināšanas preferencēm). Avota ieraksti tiek saistīti ar sapludināto ierakstu, izmantojot alternatīvus ID. Ja kārtulas nav konfigurētas, tiek lietotas sistēmas definētas kārtulas.

## <a name="default-deduplication"></a>Noklusējuma deduplikācija

Sistēmas definētie noteikumi tiek piemēroti, ja nav pievienoti deduplikācijas noteikumi.

- Primārā atslēga ir deduplicēta.
  Visiem ierakstiem ar to pašu primāro atslēgu uzvarētājs **ir visvairāk aizpildītais ieraksts** (tas, kuram ir vismazākās nulles vērtības).
- Entītijai tiek piemēroti visi starppasauļu atbilstības kārtulas.
  Piemēram: ja atbilstības darbībā entītija A tiek saskaņota ar entītiju B FullName un DateofBirth *, tad entītija A tiek dedublēta arī ar* FullName *un* DateofBirth *.* *·* Tā kā *FullName* un *DateofBirth* ir derīgas atslēgas klienta identificēšanai entītijā A, šīs atslēgas ir derīgas arī, lai identificētu dublētus klientus entītijā A.

## <a name="include-enriched-entities-preview"></a>Iekļaut bagātinātas entītijas (priekšskatījums)

Ja esat bagātinājis entītijas datu avots līmenī, lai palīdzētu uzlabot apvienošanas rezultātus, atlasiet tās. Papildinformāciju skatiet sadaļā [Bagātināšana datu avotiem](data-sources-enrichment.md).

1. Lapā Ierakstu **dublikāti lapas augšdaļā atlasiet** Izmantot bagātinātas entītijas **.**

1. **Rūtī Bagātinātu entītiju** izmantošana izvēlieties vienu vai vairākas bagātinātas entītijas.

1. Atlasiet **Gatavs**.

## <a name="define-deduplication-rules"></a>Deduplikācijas kārtulu definēšana

1. **Lapā Ierakstu** dublēšana atlasiet entītiju un atlasiet **Pievienot kārtulu**, lai definētu deduplikācijas kārtulas.

   :::image type="content" source="media/m3_duplicates_showmore.png" alt-text="Ekrānuzņēmums, kurā redzama lapa Dublēt ierakstus ar iezīmētu entītiju un parādītu kārtulu pievienošana"  lightbox="media/m3_duplicates_showmore.png":::

   1. **Rūtī Kārtulu** pievienošana ievadiet šādu informāciju:
      - **Atlasīt lauku**: izvēlieties no pieejamo lauku saraksta entītiju, kurai vēlaties pārbaudīt dublikātus. Izvēlieties laukus, kas, visticamāk, ir unikāli katram atsevišķam klientam. Piemēram, e-pasta adrese vai vārda, pilsētas un tālruņa numura kombinācija.
      - **Normalizēt**: atlasiet atlasīto atribūtu normalizēšanas opcijas.
        - **Cipari**: pārvērš citas ciparu sistēmas, piemēram, romiešu ciparus, par arābu cipariem. *VIII* kļūst par *8*.
        - **Simboli**: Noņem visus simbolus un speciālās rakstzīmes. *Head&Shoulder* kļūst par *HeadShoulder*.
        - **Teksts ar mazajiem burtiem: pārvērš visas rakstzīmes par mazajiem burtiem**. *VISI LIELIE BURTI un Virsraksta burti* kļūst par *visi lielie burti un virsraksta burti*.
        - **Tips (tālrunis, vārds, adrese, organizācija)**: standartizē vārdus, nosaukumus, tālruņa numurus, adreses utt.
        - **Unikods uz ASCII**: pārvērš unikoda apzīmējumu par ASCII rakstzīmēm. */u00B2* kļūst par *2*.
        - **Atstarpe**: noņem visas atstarpes. *Labdien, pasaule* kļūst par *HelloWorld*.
      - **Precizitāte**: iestata šim nosacījumam piemēroto precizitātes līmeni.
        - **Pamata**: izvēlieties no *zema (30%)*, *vidēja (60%)*, *augsta (80%)* un *precīza (100%).*. Atlasiet **Precīzs**, lai atbilstu tikai tiem ierakstiem, kas atbilst 100 procentiem.
        - **Pielāgots**: iestatiet procentuālu vērtību, kurai ierakstiem jāatbilst. Sistēma saskaņos tikai ierakstus, kas pārsniedz šo robežvērtību.
      - **Nosaukums**: kārtulas nosaukums.

      :::image type="content" source="media/m3_duplicates_add.png" alt-text="Ekrānuzņēmums, kurā redzama kārtulu rūts pievienošana dublikātu noņemšanai.":::

   1. Ja vēlaties, atlasiet **Pievienot nosacījumu** > **Pievienot**, lai kārtulai pievienotu papildu nosacījumus. Nosacījumi ir saistīti ar loģiku UN operatoru, un tādējādi tiek izpildīti tikai tad, ja ir izpildīti visi nosacījumi.

   1. Pēc izvēles **pievienojiet** > **izņēmumu**, lai [kārtulai](match-entities.md#add-exceptions-to-a-rule) pievienotu izņēmumus. Izņēmumi tiek izmantoti, lai risinātu retus viltus pozitīvus un viltus negatīvus gadījumus.

   1. Atlasiet **Gatavs**, lai izveidotu kārtulu.

1. Ja vēlaties, [pievienojiet citas kārtulas](#define-deduplication-rules).

1. Atlasiet entītiju un pēc tam **Rediģējiet sapludināšanas preferences**.

1. **Sapludināšanas preferenču** rūtī:
   1. Izvēlieties vienu no trim opcijām, lai noteiktu, kuru ierakstu paturēt, ja tiek atrasts dublikāts:
      - **Lielākā daļa** : tiek identificēts ieraksts, kuram ir visvairāk aizpildīto atribūtu lauku kā uzvarētāju ieraksts. Tā ir noklusējuma sapludināšanas opcija.
      - **Visjaunākais** : Nosaka uzvarētāju, balstoties uz augšupielādes datumu. Ir nepieciešams datums vai skaitlisks lauks, lai definētu augšupielādes datumu.
      - **Visvecākais** : Nosaka uzvarētāju, balstoties uz visvecāko augšupielādes datumu. Ir nepieciešams datums vai skaitlisks lauks, lai definētu augšupielādes datumu.

      Neizšķirta gadījumā uzvarētāja ieraksts ir tas, kuram ir MAX(PK) vai lielāka primārās atslēgas vērtība.

   1. Ja vēlaties, lai definētu sapludināšanas preferences atsevišķiem entītijas atribūtiem, rūts apakšdaļā atlasiet **Papildu**. Piemēram, varat izvēlēties saglabāt jaunāko e-pasta ziņojumu UN vispilnīgāko adresi no dažādiem ierakstiem. Izvērsiet entītiju, lai skatītu visus tās atribūtus un definētu, kuru opciju izmantot atsevišķiem atribūtiem. Ja izvēlaties opciju, kuras pamatā ir rekurence, ir jānorāda arī datuma/laika lauks, kas definē atkārtojamību.

      :::image type="content" source="media/m3_adv_merge.png" alt-text="Papildu sapludināšanas preferenču rūts, kurā redzama pēdējā e-pasta adrese un pilna adrese":::

   1. Atlasiet **Gatavs**, lai lietotu sapludināšanas preferences.

1. Pēc tam, kad esat definējis decentralizācijas kārtulas un sapludināšanas preferences, atlasiet **Tālāk**.
  
> [!div class="nextstepaction"]
> [Nākamā darbība vienai entītijai: Lauku apvienošana](merge-entities.md)

> [!div class="nextstepaction"]
> [Nākamais solis vairākām entītijām: atbilstoši nosacījumi](match-entities.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
