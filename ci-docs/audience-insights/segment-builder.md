---
title: Izveidojiet segmentus, izmantojot segmenta veidotāju
description: Izveidojiet klientiem segmentus, lai tos grupētu, pamatojoties uz dažādiem atribūtiem.
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
ms.openlocfilehash: 1a28289ecb740ab6cdfa603b2cd66376e7e8b576
ms.sourcegitcommit: 9ef2cf99b847e7bd8f890f83d84b3a4045aaf8cc
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 04/01/2022
ms.locfileid: "8529594"
---
# <a name="create-segments"></a>Izveidot segmentus

Definēt sarežģītus filtrus vienotā klienta entītijā unsaistītajās entītijās. Katrs segments pēc apstrādes izveido klientu ierakstu kopu, ko var eksportēt un ar kurām veikt darbības. Segmenti tiek pārvaldīti lapā **Segmenti**. Jūs varat [izveidot jaunus segmentus](#create-a-new-segment), izmantojot segmentu veidotāju, vai [izveidot ātros segmentus](#quick-segments) no citiem programmas apgabaliem.

> [!TIP]
> - Ātrie segmenti tiek atbalstīti tikai vidēs, kas ir pieejamas **atsevišķiem klientiem**.
> - Segmentos, kas balstīti uz **atsevišķiem klientiem**, automātiski tiek iekļauta segmenta dalībniekiem pieejamā kontaktinformācija. **Uzņēmumu kontu** vidēs segmenti ir balstīti uz uzņēmumiem (uzņēmumiem vai meitasuzņēmumiem). Lai segmentā iekļautu kontaktinformāciju, izmantojiet **Projekta atribūtu** funkcionalitāti segmenta veidotājā. Pārliecinieties, vai kontaktpersonu datu avoti tiek [semantiski kartēti uz ContactProfile](semantic-mappings.md#define-a-contactprofile-semantic-entity-mapping) entītiju.

## <a name="segment-builder"></a>Segmentu veidotājs

Tālāk sniegtajā attēlā ir parādīti dažādie segmentu veidotāja fragmenta aspekti. Tajā ir redzams segments, kura rezultāts ir klientu grupa. Klienti pasūtīja preces noteiktā laika periodā un apkopoja apbalvojumu punktus vai pavadīja noteiktu naudas summu.

:::image type="content" source="media/segment-builder-overview.png" alt-text="Segmentu veidotāja fragmenti." lightbox="media/segment-builder-overview.png":::

1. Organizējiet segmentu, izmantojot kārtulas un apakškārtulas. Katra kārtula vai apakškārtula sastāv no nosacījumiem. Nosacījumu apvienošana ar loģiskajiem operatoriem

1. Izvēlieties [attiecību ceļu](relationships.md) starp entītijām, kas attiecas uz kārtulu. Attiecību ceļš nosaka, kādus atribūtus var izmantot nosacījumā.

1. Pārvaldiet kārtulas un apakškārtulas. Mainīt kārtulas pozīciju vai dzēst to.

1. Pievienojiet nosacījumus un izveidojiet pareizo ligzdošanas līmeni, izmantojot apakškārtulas.

1. Lietojiet iestatītās operācijas pievienotajām kārtulām.

1. Izmantojiet atribūtu rūti, lai pievienotu pieejamos entītijas atribūtus vai izveidotu nosacījumus, pamatojoties uz atribūtiem. Šajā rūtī tiek parādīts entītiju un atribūtu saraksts, pamatojoties uz atlasīto attiecību ceļu, kas pieejams atlasītajai kārtulai.

1. Pievienojiet nosacījumus, kas balstīti uz esošu kārtulu un apakškārtulu atribūtiem, vai pievienojiet to jaunai kārtulai.

1. Atsauciet un atceliet izmaiņas, veidojot segmentu.

Iepriekš sniegtajā piemērā parādīta segmentācijas iespēja. Mēs definējām segmentu klientiem, kuri tiešsaistē $500 vismaz vienu preču segmentu *un* ir ieinteresēti programmatūras izstrādē.

## <a name="create-a-new-segment"></a>Izveidot jaunu segmentu

Ir vairāki jauna segmenta izveides veidi. Šajā sadaļā ir aprakstīts, kā no jauna izveidot savu segmentu. Var arī izveidot *ātro segmentu*, balstoties uz esošām entītijām, vai izmantot algoritmiskā mācīšanās modeļus, lai iegūtu *ieteiktos segmentus*. Lai iegūtu papildinformāciju, dodieties uz [Segmentu pārskatu](segments.md).

Veidojot segmentu, var saglabāt melnrakstu. Melnraksta posmā segments tiek saglabāts kā neaktīvs segments. Kad segmenta konfigurācija ir pabeigta, palaidiet to, lai aktivizētu segmentu. Varat arī **Aktivizēt** segmentu no lapas **Visi segmenti**.

1. Doties uz lapu **Segmenti**.

1. Atlasiet **Jauns** > **Izveidot savu**.

1. Segmenta veidošanas lapā jūs definējat vai rakstāt kārtulas. Kārtula sastāv no viena vai vairākiem nosacījumiem, kas definē klientu kopu.

1. Sadaļā Kārtula1 **izvēlieties** tās entītijas atribūtu, pēc kuras vēlaties filtrēt klientus. Pastāv divi atibūtu izvēles veid:
   - Rūtī **Pievienot kārtulai** pārskatiet pieejamo entītiju un atribūtu sarakstu un atlasiet ikonu **+** pie pievienojamā atribūta. Izvēlieties, vai atribūtu vēlaties pievienot esošai kārtulai vai izmantot to, lai izveidotu jaunu kārtulu.
   - Lai skatītu atbilstošos ieteikumus, ierakstiet atribūta nosaukumu kārtulu sadaļā.

1. Izvēlieties operatorus, lai norādītu atbilstošās nosacījuma vērtības. Atribūtam kā vērtība var būt viens no četriem datu tipiem: skaitlisks, virkne, datums vai Būla vērtība. Atkarībā no atribūta datu tipa ir pieejami dažādi operatori, lai norādītu nosacījumu. Segmentiem ar biznesa uzņēmumiem ir pieejami divi īpaši operatori, lai iekļautu potenciālās hierarhijas starp noslogotajiem uzņēmumiem. Lai iekļautu saistītus uzņēmumus, izmantojiet *atvasināto* un *primāro* operatoru.

1. Atlasiet **Pievienot nosacījumu**, lai kārtulai pievienotu papildu nosacījumus. Lai zem pašreizējās kārtulas izveidotu kārtulu, atlasiet **Pievienot apakškārtulu**.

1. Ja kārtula izmanto citas entītijas, nevis *Klienta* entītiju, ir jāiestata attiecību ceļš. Attiecību ceļš informē sistēmu, kurai ir attiecības piekļūt vienotā profila entītijai. Atlasiet **Iestatīt attiecību ceļu**, lai kartētu atlasīto entītiju uz vienoto klienta entītiju. Ja ir tikai viens iespējamais attiecību ceļš, sistēma to automātiski atlasīs. Dažādi attiecību ceļi var iegūt atšķirīgus rezultātus. Katrai kārtulai var būt savas attiecību ceļš.

   :::image type="content" source="media/relationship-path.png" alt-text="Potenciālo attiecību ceļš, izveidojot kārtulu, pamatojoties uz entītiju, kas kartēta uz vienoto klienta entītiju.":::

   Piemēram, entītijai *eCommerce_eCommercePurchases* ir šādas attiecības ar vienoto profila entītiju *Klients*:
   - eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > Klients
   - eCommerce_eCommercePurchases > Klients
   - eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > Klients
   - Commerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > loyaltyScheme_loyCustomers > Klients Izvēloties pēdējo opciju, kārtulas nosacījumos mēs varam iekļaut atribūtus no visām uzskaitītajām entītijām. Visticamāk, tiks iegūts mazāk rezultātu, jo atbilstošajiem klientu ierakstiem ir jābūt daļai no visām entītijām. Šajā piemērā klientam ir jāiegādājas preces, izmantojot e-tirdzniecības (*eCommerce_eCommercePurchases*), pārdošanas punktu (*POS_posPurchases*), un jāpiedalās mūsu lojalitātes programmā (*loyaltyScheme_loyCustomers*). Izvēloties otru opciju, atribūtus var izvēlēties tikai no *eCommerce_eCommercePurchases* entītijas *Klients*. Tā rezultātā var iegūt vairāk klientu profilu.

1. Ja kārtulā ir vairāki nosacījumi, varat izvēlēties, kurš loģiskais operators tos savieno.  
   - Operators **UN**: lai segmentā iekļautu ierakstu, jāizpilda visi nosacījumi. Šī opcija ir visnoderīgākā, kad definējat nosacījumus dažādās entītijās.
   - Operators **VAI**: lai segmentā iekļautu ierakstu, jāizpilda visi nosacījumi. Šī opcija ir visnoderīgākā, kad definējat vairākus nosacījumus vienai entītijai.

   :::image type="content" source="media/segmentation-either-condition.png" alt-text="Kārtula ar diviem nosacījumiem UN.":::

   Ja izmantojat operatoru VAI, visiem nosacījumiem ir jābūt balstītiem uz entītijām, kas ir iekļautas attiecību ceļā.

   - Var izveidot vairākas kārtulas, lai izveidotu dažādas klientu ierakstu kopas. Grupas var apvienot, lai iekļautu biznesa pieteikumam nepieciešamos klientus. Lai izveidotu jaunu kārtulu, atlasiet **Pievienot kārtulu**. Proti, ja nevarat iekļaut kārtulā un entītiju norādīto attiecību ceļa dēļ, ir jāizveido jauna kārtula, lai izvēlētos tās atribūtus.

      :::image type="content" source="media/segment-rule-grouping.png" alt-text="Segmentam pievienojiet jaunu kārtulu un izvēlieties iestatīšanas operatoru.":::

   - Atlasiet kādu no iestatītajiem operatoriem: **Apvienošana**, **Krustpunkts** vai **Izņemot**.

      - **Apvienot** apvieno divas grupas.
      - **Izveidot krustpunktu** pārklāj divas grupas. Vienotā grupā paliek tikai dati, kas *ir kopīgi* abām grupām.
      - **Izņemot** apvieno divas grupas. Tiek saglabāti tikai A grupas dati, kas *nav kopīgi* B grupas datiem.

1. Pēc noklusējuma segmenti ģenerē izvades entītiju, kurā ir visi klientu profilu atribūti, kas atbilst definētajiem filtriem. Ja segments ir balstīts uz citām entītijām, nevis entītiju *Klients*, izvades entītijai var pievienot papildu atribūtus no šīm entītijām. Atlasiet **Projekta atribūtus**, lai izvēlētos atribūtus, kas tiks pievienoti izvades entītijai.

   > [!IMPORTANT]
   > Segmentos, kuru pamatā ir biznesa uzņēmumi, segmentā ir jāiekļauj detalizēta informācija par vienu vai vairākām katra uzņēmuma kontaktpersonām no entītijas *ContactProfile*, lai šo segmentu varētu aktivizēt vai eksportēt uz adresātiem, kuriem ir vajadzīga kontaktinformācija. Papildinformāciju par *ContactProfile* entītiju skatiet [Semantiski kartējumi](semantic-mappings.md).
   > Piemēram, segmenta izvades paraugs, balstoties uz biznesa uzņēmumiem ar plānotajiem kontaktpersonu atribūtiem, var izskatīties šādi:
   >
   > |ID  |Konta nosaukums  |Ieņēmumi  |Kontaktpersonas nosaukums  | Kontaktpersonas loma|
   > |---------|---------|---------|---------|---|
   > |10021     | Contoso | 100K | [Ebija Mosa, Rūta Soto]  | [CEO, Iepirkumu vadītāja]

   :::image type="content" source="media/segments-project-attributes.png" alt-text="Izvades entītijai pievienojamā sānu rūtī atlasīto prognozēto atribūtu piemērs.":::
  
   Piemēram: segments tiek veidots, pamatojoties uz entītiju, kurā ir ietverti ar *Klienta* entītiju saistīti pirkuma dati. Šis segments meklē visus klientus no Spānijā, kas iegādājušies preces pašreizējā gadā. Varat izvēlēties pievienot atribūtus, piemēram, preču cenu, vai iegādes datumu visiem atbilstošajiem klientu ierakstiem izvades entītijā. Šī informācija var būt noderīga, lai analizētu sezonas pretsaderību attiecībā pret kopējiem izdevumiem.

   > [!NOTE]
   > - **Projekta atribūti** darbojas tikai entītijām, kurām ir attiecības viens pret daudziem ar klienta entītiju. Piemēram, vienam klientam var būt vairāki abonementi.
   > - Ja atribūts, ko vēlaties plānot, ir vairāk nekā viens objekts prom no entītijas *Klients*, kā to definē attiecības, šis atribūts ir jāizmanto katrā tā segmenta vaicājuma kārtulā, ko veidojat.
   > - Ja atribūts, ko vēlaties plānot, ir vairāk nekā viens objekts prom no entītijas *Klients*, kā to definē attiecības, šis atribūts ir jāizmanto katrā tā segmenta vaicājuma kārtulā, ko veidojat.
   > - **Plānotie atribūti** tiek faktorizēti, izmantojot kopas operatorus.

1. Blakus segmentam Bez nosaukuma atlasiet **Rediģēt detaļas**. Norādiet segmenta nosaukumu un atjauniniet segmentam ieteikto **Izvades entītijas nosaukumu**. Pēc izvēles pievienojiet segmentam aprakstu un [atzīmes](work-with-tags-columns.md#manage-tags).

   :::image type="content" source="media/segments_edit_details.png" alt-text="Dialoglodziņš Detalizētas informācijas rediģēšana.":::

1. Atlasiet **Palaist**, lai saglabātu segmentu, aktivizējiet to un sāciet segmenta apstrādi, pamatojoties uz visām kārtulām un nosacījumiem. Pretējā gadījumā tas tiks saglabāts kā neaktīvs segments.

1. Atlasiet **Atgriezties pie segmentiem**, lai atgrieztos pie **Segmentu** lapas.

1. Pēc noklusējuma segments tiek izveidots kā dinamiskais segments. Tas nozīmē, ka segments tiek atsvaidzināts sistēmas atsvaidzināšanas laikā. Lai [apturētu automātisko atsvaidzināšanu](segments.md#manage-existing-segments), atlasiet segmentu, izvēlieties opciju **Padarīt statisku**. Statiskos segmentus var [atsvaidzināt manuāli](segments.md#refresh-segments) jebkurā laikā.

> [!TIP]
> - Iestatot operatorus nosacījumos, segmentu veidotājs no entītijām neieteiks derīgas vērtības. Varat pāriet uz **Dati** > **Entītijas** un lejupielādēt entītijas datus, lai skatītu pieejamās vērtības.
> - Nosacījumi atkarībā no datumiem ļauj pārslēgt fiksētus datumus un peldošu datumu diapazonu.
> - Ja segmentam ir vairākas kārtulas, rediģējamajai kārtulai blakus ir vertikāla zilā līnija.
> - Segmenta definīcijā kārtulas un nosacījumus var pārvietot uz citām vietām. Atlasiet [...] blakus kārtulai vai nosacījumam un izvēlieties, kā un kur to pārvietot.
> - Komandjoslā izmantojot vadīklas **Atsaukt** un **Atcelt**, varat atsaukt atpakaļ veiktās izmaiņas.

## <a name="quick-segments"></a>Ātrie segmenti

Izmantojot ātros segmentus, varat ātri izveidot vienkāršus segmentus, izmantojot vienu operatoru, lai gūtu ātrākus ieskatus.

1. **Segmentu** lapā atlasiet **Jauns** > **Izveidot no**.
   - Atlasiet opciju **Profili**, lai izveidotu segmentu, kura pamatā ir *vienotā klienta* entītija.
   - Atlasiet opciju **Pasākumi**, lai izveidotu segmentu ap iepriekš izveidotajiem pasākumiem.
   - Atlasiet opciju **Informācijas apkopošana**, lai izveidotu segmentu ap vienu no izvades entitījām, kuras izveidojāt, izmantojot iespēju **Prognozes** vai **Pielāgotie modeļi**.

2. Dialoglodziņā **Jauns ātrais segments** atlasiet atribūtu no nolaižamā saraksta **Lauks**.

3. Sistēma sniegs ieskatus, kas palīdzēs izveidot labākus klientu segmentus.
   - Attiecībā uz kategoriju laukiem mēs parādīsim 10 lielāko klientu skaitu. Izvēlieties **Vērtība** un atlasiet **Pārskatīt**.
   - Skaitliskam atribūtam sistēma parādīs, kāda atribūta vērtība atbilst katra klienta procentīlei. Izvēlieties **Operators** un **Vērtība** un pēc tam atlasiet vienumu **Pārskatīt**.

4. Sistēma nodrošinās jūs ar **Aptuveniem segmenta izmēriem**. Varat izvēlēties, vai ģenerēt definēto segmentu, vai arī to vispirms pārskatīt, lai iegūtu citu segmenta lielumu.

   :::image type="content" source="media/quick-segment-name.png" alt-text="Ātrā segmenta nosaukums un novērtējums.":::

5. Norādiet segmenta **nosaukumu** un **izvades entītijas nosaukumu**. Pēc izvēles pievienojiet [atzīmes](work-with-tags-columns.md#manage-tags).

6. Lai izveidotu segmentu, atlasiet opciju **Saglabāt**.

7. Pēc tam, kad segments ir pabeidzis apstrādi, to var apskatīt tāpat kā jebkuru citu izveidoto segmentu.

## <a name="next-steps"></a>Nākamās darbības

[Eksportējiet segmentu](export-destinations.md) un izpētiet [Klienta kartes integrāciju](customer-card-add-in.md), lai izmantotu segmentus citās lietojumprogrammās.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
