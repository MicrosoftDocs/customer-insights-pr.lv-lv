---
title: Sarežģītu segmentu izveide, izmantojot segmentu veidotāju
description: Izmantojiet segmentu veidotāju, lai izveidotu sarežģītus klientu segmentus, grupējot tos, pamatojoties uz dažādiem atribūtiem.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-segments
- ci-segment-builder
- ci-segment-details
- customerInsights
ms.openlocfilehash: cde373cd65e296675e1b3c92f3024e1093853842
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170644"
---
# <a name="create-complex-segments-with-segment-builder"></a>Sarežģītu segmentu izveide, izmantojot segmentu veidotāju

Definēt sarežģītus filtrus vienotā klienta entītijā unsaistītajās entītijās. Katrs segments pēc apstrādes izveido klientu ierakstu kopu, ko var eksportēt un ar kurām veikt darbības.

> [!TIP]
> Segmentos, kas balstīti uz **atsevišķiem klientiem**, automātiski tiek iekļauta segmenta dalībniekiem pieejamā kontaktinformācija. **Uzņēmumu kontu** vidēs segmenti ir balstīti uz uzņēmumiem (uzņēmumiem vai meitasuzņēmumiem). Lai segmentā iekļautu kontaktinformāciju, izmantojiet **Projekta atribūtu** funkcionalitāti segmenta veidotājā. Pārliecinieties, vai kontaktpersonu datu avoti tiek [semantiski kartēti uz ContactProfile](semantic-mappings.md#define-a-contactprofile-semantic-entity-mapping) entītiju.

## <a name="segment-builder"></a>Segmentu veidotājs

Tālāk sniegtajā attēlā ir parādīti dažādie segmentu veidotāja fragmenta aspekti. Tajā ir redzams segments, kura rezultāts ir klientu grupa. Klienti pasūtīja preces noteiktā laika periodā un apkopoja apbalvojumu punktus vai pavadīja noteiktu naudas summu.

:::image type="content" source="media/segment-builder-overview.png" alt-text="Segmentu veidotāja fragmenti." lightbox="media/segment-builder-overview.png":::

1. Organizējiet segmentu, izmantojot kārtulas un apakškārtulas. Katra kārtula vai apakškārtula sastāv no nosacījumiem. Apvienojiet apstākļus ar loģiskiem operatoriem.

1. Izvēlieties [attiecību ceļu](relationships.md) starp entītijām, kas attiecas uz kārtulu. Attiecību ceļš nosaka, kādus atribūtus var izmantot nosacījumā.

1. Pārvaldiet kārtulas un apakškārtulas. Mainīt kārtulas pozīciju vai dzēst to.

1. Pievienojiet nosacījumus un izveidojiet pareizo ligzdošanas līmeni, izmantojot apakškārtulas.

1. Lietojiet iestatītās operācijas pievienotajām kārtulām.

1. Izmantojiet atribūtu rūti, lai pievienotu pieejamos entītijas atribūtus vai izveidotu nosacījumus, pamatojoties uz atribūtiem. Šajā rūtī tiek parādīts entītiju un atribūtu saraksts, pamatojoties uz atlasīto attiecību ceļu, kas pieejams atlasītajai kārtulai.

1. Pievienojiet nosacījumus, kas balstīti uz esošu kārtulu un apakškārtulu atribūtiem, vai pievienojiet to jaunai kārtulai.

1. Atsauciet un atceliet izmaiņas, veidojot segmentu.

Iepriekš sniegtajā piemērā parādīta segmentācijas iespēja. Mēs definējām segmentu klientiem, kuri tiešsaistē $500 vismaz vienu preču segmentu *un* ir ieinteresēti programmatūras izstrādē.

## <a name="create-a-new-segment-with-segment-builder"></a>Jauna segmenta izveide, izmantojot segmentu veidotāju

1. Ejiet uz **Segmenti**.

1. Atlasiet **Jauns** > **Izveidot savu**. Segmenta veidošanas lapā jūs definējat vai rakstāt kārtulas. Kārtula sastāv no viena vai vairākiem nosacījumiem, kas definē klientu kopu.

1. Atlasiet **Rediģēt detalizētu informāciju** blakus segmentam Bez nosaukuma. Norādiet segmenta nosaukumu un atjauniniet segmentam ieteikto **Izvades entītijas nosaukumu**. Pēc izvēles segmentam pievienojiet aprakstu un [atzīmes](work-with-tags-columns.md#manage-tags).

   :::image type="content" source="media/segments_edit_details.png" alt-text="Dialoglodziņš Detalizētas informācijas rediģēšana.":::

1. **Sadaļā Kārtula1** izvēlieties atribūtu entītijai, pēc kuras vēlaties filtrēt klientus. Pastāv divi atibūtu izvēles veid:
   - Rūtī **Pievienot kārtulai** pārskatiet pieejamo entītiju un atribūtu sarakstu un atlasiet ikonu **+** pie pievienojamā atribūta. Izvēlieties, vai atribūtu vēlaties pievienot esošai kārtulai vai izmantot to, lai izveidotu jaunu kārtulu.
   - Lai skatītu atbilstošos ieteikumus, ierakstiet atribūta nosaukumu kārtulu sadaļā.

1. Izvēlieties operatorus, lai norādītu atbilstošās nosacījuma vērtības. Atribūtam kā vērtība var būt viens no četriem datu tipiem: skaitlisks, virkne, datums vai Būla vērtība. Atkarībā no atribūta datu tipa ir pieejami dažādi operatori, lai norādītu nosacījumu. Segmentiem ar biznesa uzņēmumiem ir pieejami divi īpaši operatori, lai iekļautu potenciālās hierarhijas starp noslogotajiem uzņēmumiem. Lai iekļautu saistītus uzņēmumus, izmantojiet *atvasināto* un *primāro* operatoru.

1. Atlasiet **Pievienot nosacījumu**, lai kārtulai pievienotu papildu nosacījumus. Lai zem pašreizējās kārtulas izveidotu kārtulu, atlasiet **Pievienot apakškārtulu**.

1. Ja kārtula izmanto citas entītijas, nevis entītiju *Klients, atlasiet* Iestatīt relācijas ceļu **, lai kartētu atlasīto entītiju uz vienoto** klienta entītiju. Ja ir tikai viens iespējamais relāciju ceļš, sistēma to atlasa automātiski. Dažādi [attiecību ceļi var dot atšķirīgus](relationships.md#relationship-paths) rezultātus. Katrai kārtulai var būt savas attiecību ceļš.

   :::image type="content" source="media/relationship-path.png" alt-text="Potenciālo attiecību ceļš, izveidojot kārtulu, pamatojoties uz entītiju, kas kartēta uz vienoto klienta entītiju.":::

1. Ja kārtulā ir vairāki nosacījumi, izvēlieties, kurš loģiskais operators tos savieno.  
   - Operators **UN**: lai segmentā iekļautu ierakstu, jāizpilda visi nosacījumi. Izmantojiet šo opciju, definējot nosacījumus dažādām entītijām.
   - Operators **VAI**: lai segmentā iekļautu ierakstu, jāizpilda visi nosacījumi. Izmantojiet šo opciju, ja definējat vairākus nosacījumus vienai entītijai.

   :::image type="content" source="media/segmentation-either-condition.png" alt-text="Kārtula ar diviem nosacījumiem UN.":::

   Ja izmantojat operatoru VAI, visiem nosacījumiem ir jābūt balstītiem uz entītijām, kas ir iekļautas attiecību ceļā.

1. Lai izveidotu dažādas klientu ierakstu kopas, izveidojiet vairākas kārtulas. Lai iekļautu jūsu biznesa pamatojumam nepieciešamos klientus, apvienojiet grupas. Konkrētāk, ja nevarat iekļaut entītiju kārtulā norādītā relāciju ceļa dēļ, izveidojiet jaunu kārtulu, lai no tās izvēlētos atribūtus.

      :::image type="content" source="media/segment-rule-grouping.png" alt-text="Segmentam pievienojiet jaunu kārtulu un izvēlieties iestatīšanas operatoru.":::

   1. Atlasiet **Pievienot kārtulu**.
   1. Atlasiet kādu no iestatītajiem operatoriem: **Apvienošana**, **Krustpunkts** vai **Izņemot**.

      - **Apvienot** apvieno divas grupas.
      - **Izveidot krustpunktu** pārklāj divas grupas. Vienotā grupā paliek tikai dati, kas *ir kopīgi* abām grupām.
      - **Izņemot** apvieno divas grupas. Tiek saglabāti tikai A grupas dati, kas *nav kopīgi* B grupas datiem.

1. Pēc noklusējuma izvades entītija automātiski satur visus klientu profilu atribūtus, kas atbilst definētajiem filtriem. Ja segmenta pamatā ir citas entītijas, nevis entītija *Klients, atlasiet* Projekta atribūti **, lai izvades entītijai pievienotu vairāk atribūtu no** šīm entītijām.

   > [!IMPORTANT]
   > Segmentiem, kuru pamatā ir uzņēmuma konti, segmentā ir jāiekļauj detalizēta informācija par vienu vai vairākām kontaktpersonām no *uzņēmuma ContactProfile*, lai šo segmentu varētu aktivizēt vai eksportēt uz galamērķiem, kuriem nepieciešama kontaktinformācija. Papildinformāciju par *ContactProfile* entītiju skatiet [Semantiski kartējumi](semantic-mappings.md).
   > Piemēram, segmenta izvades paraugs, balstoties uz biznesa uzņēmumiem ar plānotajiem kontaktpersonu atribūtiem, var izskatīties šādi:
   >
   > |ID  |Konta nosaukums  |Ieņēmumi  |Kontaktpersonas nosaukums  | Kontaktpersonas loma|
   > |---------|---------|---------|---------|---|
   > |10021     | Contoso | 100K | [Ebija Mosa, Rūta Soto]  | [CEO, Iepirkumu vadītāja]

   :::image type="content" source="media/segments-project-attributes.png" alt-text="Izvades entītijai pievienojamā sānu rūtī atlasīto prognozēto atribūtu piemērs.":::
  
   Piemēram: segments tiek veidots, pamatojoties uz entītiju, kurā ir ietverti ar *Klienta* entītiju saistīti pirkuma dati. Šis segments meklē visus klientus no Spānijā, kas iegādājušies preces pašreizējā gadā. Varat izvēlēties pievienot atribūtus, piemēram, preču cenu vai pirkšanas datumu, visiem atbilstošajiem debitoru ierakstiem izvades entītijā. Šī informācija var būt noderīga, lai analizētu sezonas pretsaderību attiecībā pret kopējiem izdevumiem.

   > [!NOTE]
   > - **Projekta atribūti** darbojas tikai entītijām, kurām ir attiecības viens pret daudziem ar klienta entītiju. Piemēram, vienam klientam var būt vairāki abonementi.
   > - Ja atribūts, ko vēlaties plānot, ir vairāk nekā viens objekts prom no entītijas *Klients*, kā to definē attiecības, šis atribūts ir jāizmanto katrā tā segmenta vaicājuma kārtulā, ko veidojat.
   > - Ja atribūts, ko vēlaties plānot, ir vairāk nekā viens objekts prom no entītijas *Klients*, kā to definē attiecības, šis atribūts ir jāizmanto katrā tā segmenta vaicājuma kārtulā, ko veidojat.
   > - **Plānotie atribūti** tiek faktorizēti, izmantojot kopas operatorus.

1. Atlasiet **Palaist**, lai izveidotu segmentu. Atlasiet **Saglabāt**, ja vēlaties saglabāt pašreizējo konfigurāciju un palaist segmentu vēlāk. Tiek **parādīta lapa Segmenti**.

### <a name="segment-builder-tips"></a>Segmentu veidotāja padomi

Veidojot segmentu, izmantojot segmentu veidotāju, ņemiet vērā šādus padomus:

- Iestatot operatorus nosacījumos, segmentu veidotājs no entītijām neieteiks derīgas vērtības. Varat pāriet uz **Dati** > **Entītijas** un lejupielādēt entītijas datus, lai skatītu pieejamās vērtības.
- Nosacījumi, kuru pamatā ir datumi, ļauj pārslēgties starp fiksētiem datumiem un peldošu datumu diapazonu.
- Ja segmentam ir vairākas kārtulas, rediģējamajai kārtulai blakus ir vertikāla zilā līnija.
- Segmenta definīcijā kārtulas un nosacījumus var pārvietot uz citām vietām. Atlasiet vertikālo elipsi (&vellip;) blakus kārtulai vai nosacījumam un izvēlieties, kā un kur to pārvietot.
- Komandjoslā izmantojot vadīklas **Atsaukt** un **Atcelt**, varat atsaukt atpakaļ veiktās izmaiņas.
- Pēc segmenta izveides daži segmenti ļauj [izsekot segmenta](segments.md#track-usage-of-a-segment) lietojumam.

## <a name="next-steps"></a>Nākamās darbības

[Eksportējiet segmentu](export-destinations.md) un izpētiet [Klienta kartes integrāciju](customer-card-add-in.md), lai izmantotu segmentus citās lietojumprogrammās.

[!INCLUDE [footer-include](includes/footer-banner.md)]
