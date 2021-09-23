---
title: Izveidojiet segmentus, izmantojot segmenta veidotāju
description: Izveidojiet klientiem segmentus, lai tos grupētu, pamatojoties uz dažādiem atribūtiem.
ms.date: 09/07/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 7f7bd0e7e581305836287bd503ef273a2d556bff
ms.sourcegitcommit: fecdee73e26816c42d39d160d4d5cfb6c8a91596
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 09/15/2021
ms.locfileid: "7494511"
---
# <a name="create-segments"></a>Izveidot segmentus

Definēt sarežģītus filtrus vienotā klienta entītijā unsaistītajās entītijās. Katrs segments pēc apstrādes izveido klientu ierakstu kopu, ko var eksportēt un ar kurām veikt darbības. Segmenti tiek pārvaldīti lapā **Segmenti**. Jūs varat [izveidot jaunus segmentus](#create-a-new-segment), izmantojot [segmentu veidotāju](#segment-builder), vai [izveidot ātros segmentus](#quick-segments) no citiem programmas apgabaliem.

## <a name="segment-builder"></a>Segmentu veidotājs

Tālāk sniegtajā attēlā ir parādīti dažādie segmentu veidotāja fragmenta aspekti. Tajā ir redzams segments, kura rezultāts ir klientu grupa. Klienti pasūtīja preces noteiktā laika periodā un apkopoja vairākus apbalvojumu punktus vai iztērēja noteiktu naudas summu. 

:::image type="content" source="media/segment-builder-overview.png" alt-text="Segmentu veidotāja fragmenti." lightbox="media/segment-builder-overview.png":::

1 - organizējiet segmentu, izmantojot kārtulas un apakškārtulas. Katra kārtula vai apakškārtula sastāv no nosacījumiem. Nosacījumu apvienošana ar loģiskajiem operatoriem

2 - izvēlieties [attiecību ceļu](relationships.md) starp entītijām, kas attiecas uz kārtulu. Attiecību ceļš nosaka, kādus atribūtus var izmantot nosacījumā.

3 - pārvaldiet kārtulas un apakškārtulas. Mainīt kārtulas pozīciju vai dzēst to.

4 - pievienojiet nosacījumus un izveidojiet pareizo ligzdošanas līmeni, izmantojot apakškārtulas.

5 - lietot iestatītās operācijas pievienotajām kārtulām.

6 - izmantojiet atribūtu rūti, lai pievienotu pieejamos entītijas atribūtus vai izveidotu nosacījumus, pamatojoties uz atribūtiem. Šajā rūtī tiek parādīts entītiju un atribūtu saraksts, pamatojoties uz atlasīto attiecību ceļu, kas pieejams atlasītajai kārtulai.

7 - pievienojiet nosacījumus, kas balstīti uz esošu kārtulu un apakškārtulu atribūtiem, vai pievienojiet to jaunai kārtulai.

8 - atsauciet un atceliet izmaiņas, veidojot segmentu.

Iepriekš sniegtajā piemērā parādīta segmentācijas iespēja. Mēs definējām segmentu klientiem, kuri tiešsaistē $500 vismaz vienu preču segmentu *un* ir ieinteresēti programmatūras izstrādē.

## <a name="create-a-new-segment"></a>Izveidot jaunu segmentu

Ir vairāki jauna segmenta izveides veidi. Šajā sadaļā ir aprakstīts, kā no jauna izveidot savu segmentu. Var arī izveidot *ātro segmentu*, balstoties uz esošām entītijām, vai izmantot algoritmiskā mācīšanās modeļus, lai iegūtu *ieteiktos segmentus*. Papildinformācija: [Pārskats par segmentiem](segments.md).

Veidojot segmentu, var saglabāt melnrakstu. Tas tiks saglabāts kā neaktīvs segments, un to nevar aktivizēt, un tā ir pabeigta, izmantojot derīgu konfigurāciju.

1. Doties uz lapu **Segmenti**.

1. Atlasiet **Jauns** > **Izveidot savu**.

1. Uz segmentu veidotāja lapas jūs definējat pirmo kārtulu. Kārtula sastāv no viena vai vairākiem nosacījumiem un definē klientu kopu.

1. Sadaļā **1. kārtula** izvēlieties entītijas atribūtu, pēc kura vēlaties filtrēt klientus. Pastāv divi atibūtu izvēles veid: 
   - Rūtī **Pievienot kārtulai** pārskatiet pieejamo entītiju un atribūtu sarakstu un atlasiet ikonu **+** pie pievienojamā atribūta. Izvēlieties, vai atribūtu vēlaties pievienot esošai kārtulai vai izmantot to, lai izveidotu jaunu kārtulu.
   - Lai skatītu atbilstošos ieteikumus, ierakstiet atribūta nosaukumu kārtulu sadaļā.

1. Izvēlieties operatorus, lai norādītu atbilstošās nosacījuma vērtības. Atribūtam kā vērtība var būt viens no četriem datu tipiem: skaitlisks, virkne, datums vai Būla vērtība. Atkarībā no atribūta datu tipa ir pieejami dažādi operatori, lai norādītu nosacījumu. 

1. Atlasiet **Pievienot nosacījumu**, lai kārtulai pievienotu papildu nosacījumus. Lai zem pašreizējās kārtulas izveidotu kārtulu, atlasiet **Pievienot apakškārtulu**.

1. Ja kārtula izmanto citas entītijas, nevis *Klienta* entītiju, ir jāiestata attiecību ceļš. Attiecību ceļš informē sistēmu, kurai ir attiecības piekļūt vienotā profila entītijai. Atlasiet **Iestatīt attiecību ceļu**, lai kartētu atlasīto entītiju uz vienoto klienta entītiju. Ja ir tikai viens iespējamais attiecību ceļš, sistēma to automātiski atlasīs. Dažādi attiecību ceļi var iegūt atšķirīgus rezultātus. Katrai kārtulai var būt savas attiecību ceļš.

   :::image type="content" source="media/relationship-path.png" alt-text="Potenciālo attiecību ceļš, izveidojot kārtulu, pamatojoties uz entītiju, kas kartēta uz vienoto klienta entītiju.":::

   Piemēram, entītijai *eCommerce_eCommercePurchases* ir šādas attiecības ar vienoto profila entītiju *Klients*: 
   - eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > Klients
   - eCommerce_eCommercePurchases > Klients
   - eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > Klients
   - Commerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > loyaltyScheme_loyCustomers > Klients Izvēloties pēdējo opciju, kārtulas nosacījumos mēs varam iekļaut atribūtus no visām uzskaitītajām entītijām. Visticamāk, tiks iegūts mazāk rezultātu, jo atbilstošajiem klientu ierakstiem ir jābūt daļai no visām entītijām. Šajā piemērā klientam ir jāiegādājas preces, izmantojot e-tirdzniecības (*eCommerce_eCommercePurchases*), pārdošanas punktu (POS_ *posPurchases*), un jāpiedalās mūsu lojalitātes programmā (*loyaltyScheme_loyCustomers*). Izvēloties otru opciju, atribūtus var izvēlēties tikai no *eCommerce_eCommercePurchases* entītijas *Klients*. Tā rezultātā var iegūt vairāk klientu profilu.

1. Ja kārtulā ir vairāki nosacījumi, varat izvēlēties, kurš loģiskais operators tos savieno.

   - Operators **UN**: lai segmentā iekļautu ierakstu, jāizpilda visi nosacījumi. Šī opcija ir visnoderīgākā, kad definējat nosacījumus dažādās entītijās.

   - Operators **VAI**: lai segmentā iekļautu ierakstu, jāizpilda visi nosacījumi. Šī opcija ir visnoderīgākā, kad definējat vairākus nosacījumus vienai entītijai.

   :::image type="content" source="media/segmentation-either-condition.png" alt-text="Kārtula ar diviem nosacījumiem UN.":::

   Ja izmantojat operatoru VAI, visiem nosacījumiem ir jābūt balstītiem uz entītijām, kas ir iekļautas attiecību ceļā.

   1. Var izveidot vairākas kārtulas, lai izveidotu dažādas klientu ierakstu kopas. Grupas var apvienot, lai iekļautu biznesa pieteikumam nepieciešamos klientus. Lai izveidotu jaunu kārtulu, atlasiet **Pievienot kārtulu**. Īpaši, ja nevarat iekļaut kārtulā un entītiju norādīto attiecību ceļa dēļ, jums ir jāizveido jauna kārtula, lai izvēlētos tās atribūtus.

      :::image type="content" source="media/segment-rule-grouping.png" alt-text="Segmentam pievienojiet jaunu kārtulu un izvēlieties iestatīšanas operatoru.":::

   1. Atlasiet kādu no iestatītajiem operatoriem: **Apvienošana**, **Krustpunkts** vai **Izņemot**.

   - **Apvienot** apvieno divas grupas.

   - **Izveidot krustpunktu** pārklāj divas grupas. Vienotajā grupā tiek saglabāti tikai tie dati, kas ir *kopēji* abām grupām.

   - **Izņemot** apvieno divas grupas. Tiek saglabāti tikai A grupas dati, kas *nav kopēji* B grupas datiem.

1. Pēc noklusējuma segmenti ģenerē izvades entītiju, kurā ir visi klientu profilu atribūti, kas atbilst definētajiem filtriem. Ja segments ir balstīts uz citām entītijām, nevis entītiju *Klients*, izvades entītijai var pievienot papildu atribūtus no šīm entītijām. Atlasiet **Projekta atribūtus**, lai izvēlētos atribūtus, kas tiks pievienoti izvades entītijai.  

   :::image type="content" source="media/segments-project-attributes.png" alt-text="Izvades entītijai pievienojamā sānu rūtī atlasīto prognozēto atribūtu piemērs.":::
  
   Piemērs. Segments tiek veidots, pamatojoties uz entītiju, kurā ir ietverti ar *Klienta* entītiju saistītie iegādes dati. Šis segments meklē visus klientus no Spānijā, kas iegādājušies preces pašreizējā gadā. Varat izvēlēties pievienot atribūtus, piemēram, preču cenu, vai iegādes datumu visiem atbilstošajiem klientu ierakstiem izvades entītijā. Šī informācija var būt noderīga, lai analizētu sezonas pretsaderību attiecībā pret kopējiem izdevumiem.

   > [!NOTE]
   > - Plānotie atribūti darbojas tikai entītijām, kurām ir attiecības viens pret daudziem ar klienta entītiju. Piemēram, vienam klientam var būt vairāki abonementi.
   > - Projekta atribūtus var izveidot tikai no entītijas, kas tiek izmantota katrā segmenta vaicājuma kārtulā, kuru veidojāt.
   > - Plānotie atribūti tiek faktorizēti, izmantojot kopas operatorus.

1. Pirms segmenta saglabāšanas un palaišanas atlasiet vienumu **Rediģēt detalizēto informāciju** pie segmenta nosaukuma. Norādiet segmenta nosaukumu un atjauniniet segmentam ieteikto **Izvades entītijas nosaukumu**. Segmentam var pievienot arī aprakstu.

1. Atlasiet **Palaist**, lai saglabātu un apstrādātu segmentu, ja tiek validētas visas prasības. Pretējā gadījumā tā tiks saglabāta kā neaktīva segmenta melnraksts.

1. Atlasiet **Atgriezties pie segmentiem**, lai atgrieztos pie **Segmentu** lapas.

> [!TIP]
> - Iestatot operatorus nosacījumos, segmentu veidotājs no entītijām neieteiks derīgas vērtības. Varat pāriet uz **Dati** > **Entītijas** un lejupielādēt entītijas datus, lai skatītu pieejamās vērtības.
> - Nosacījumi atkarībā no datumiem ļauj pārslēgt fiksētus datumus un peldošu datumu diapazonu.
> - Ja segmentam ir vairākas kārtulas, rediģējamajā kārtulā ir zilā josla.
> - Segmenta definīcijā kārtulas un nosacījumus var pārvietot uz citām vietām. Atlasiet [...] blakus kārtulai vai nosacījumam un izvēlieties, kā un kur to pārvietot.
> - Komandjoslā **Atsaukt** un **Atcelt atsaukšanu** varat atgriezt veiktās izmaiņas.

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

    > [!div class="mx-imgBorder"]
    > ![Ātrā segmenta nosaukums un novērtējums.](media/quick-segment-name.png "Ātrā segmenta nosaukums un novērtējums")

5. Norādiet segmenta **Nosaukumu**. Vai ari norādiet **Parādāmo vārdu**.

6. Lai izveidotu segmentu, atlasiet opciju **Saglabāt**.

7. Pēc tam, kad segments ir pabeidzis apstrādi, to var apskatīt tāpat kā jebkuru citu izveidoto segmentu.

## <a name="next-steps"></a>Nākamās darbības

[Eksportējiet segmentu](export-destinations.md) un izpētiet [Klienta kartes integrāciju](customer-card-add-in.md), lai izmantotu segmentus citās lietojumprogrammās.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
