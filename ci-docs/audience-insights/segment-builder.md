---
title: Izveidojiet un pārvaldiet segmentus
description: Izveidojiet klientiem segmentus, lai tos grupētu, pamatojoties uz dažādiem atribūtiem.
ms.date: 07/18/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: e759872643cc7387cf732d73c7a320ae8901e5a9
ms.sourcegitcommit: 42692a815695b9fdc93b9358eae09f2c3e97293c
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 08/13/2021
ms.locfileid: "7377797"
---
# <a name="create-and-manage-segments"></a>Izveidojiet un pārvaldiet segmentus

> [!IMPORTANT]
> Ir vairākas izmaiņas, kas tiek pārnestas uz segmentu izveides pieredzi 2021. gada septembra skatā: 
> - Segmenta būvētājs izskatīsies nedaudz citādi ar pārveidotiem elementiem un uzlabotu lietotāja plūsmu.
> - Jauni datuma un laika operatori, kā arī uzlabotais datuma atlasītājs ir iespējoti segmenta būvētājā.
> - Segmentiem varat pievienot vai noņemt nosacījumus un kārtulas. 
> - Ligzdotas kārtulas, kas sākas ar nosacījumu VAI, kļūst pieejamas. Jums vairs nav nepieciešams nosacījums UN pie slāņa.
> - Sānu rūts atribūtu atlasei būs pastāvīgi pieejama.
> - Entītiju attiecību ceļu atlases opcija.
> Lai izmēģinātu jauno segmenta būvētāju, sūtiet e-pasta ziņojumu ar tēmu "Pieprasīt iespējot jauno segmenta būvētāju" uz cihelp [at] microsoft.com. Iekļaujiet savas organizācijas nosaukumu un jūsu smilškastes vides ID.
> :::image type="content" source="media/segment-builder-overview.png" alt-text="Segmentu veidotāja fragmenti." lightbox="media/segment-builder-overview.png":::
>
> 1 - organizējiet segmentu, izmantojot kārtulas un apakškārtulas. Katra kārtula vai apakškārtula sastāv no nosacījumiem. Nosacījumu apvienošana ar loģiskajiem operatoriem
>
> 2 - izvēlieties [attiecību ceļu](relationships.md) starp entītijām, kas attiecas uz kārtulu. Attiecību ceļš nosaka, kādus atribūtus var izmantot nosacījumā.
>
> 3 - pārvaldiet kārtulas un apakškārtulas. Mainīt kārtulas pozīciju vai dzēst to.
>
> 4 - pievienojiet nosacījumus un izveidojiet pareizo ligzdošanas līmeni, izmantojot apakškārtulas.
>
> 5 - lietot iestatītās operācijas pievienotajām kārtulām.
>
> 6 - izmantojiet atribūtu rūti, lai pievienotu pieejamos entītijas atribūtus vai izveidotu nosacījumus, pamatojoties uz atribūtiem. Šajā rūtī tiek parādīts entītiju un atribūtu saraksts, pamatojoties uz atlasīto attiecību ceļu, kas pieejams atlasītajai kārtulai.
>
> 7 - pievienojiet nosacījumus, kas balstīti uz esošu kārtulu un apakškārtulu atribūtiem, vai pievienojiet to jaunai kārtulai.
>
> 8 - atsauciet un atceliet izmaiņas, veidojot segmentu.

Definēt sarežģītus filtrus vienotā klienta entītijā unsaistītajās entītijās. Katrs segments pēc apstrādes izveido klientu ierakstu kopu, ko var eksportēt un ar kurām veikt darbības. Segmenti tiek pārvaldīti lapā **Segmenti**. 

Šajā piemērā ir aprakstīta segmentācijas iespēja. Mēs esam definējuši segmentu klientiem, kuri pēdējo 90 dienu laikā ir pasūtījuši preces vismaz 500$ vērtībā *un* ir bijuši iesaistīti aktualizēta klientu apkalpošanas zvanā.

:::image type="content" source="media/segmentation-group1-2.png" alt-text="Segmenta būvēšanas UI ekrānuzņēmums, kurā ir divas grupas, kurās norādīts klienta segments.":::

## <a name="create-a-new-segment"></a>Izveidot jaunu segmentu

Ir vairāki jauna segmenta izveides veidi. Šajā sadaļā ir aprakstīts, kā izveidot *tukšu segmentu* no jauna. Var arī izveidot *ātro segmentu*, balstoties uz esošām entītijām, vai izmantot algoritmiskā mācīšanās modeļus, lai iegūtu *ieteiktos segmentus*. Papildinformācija: [Pārskats par segmentiem](segments.md).

Veidojot segmentu, var saglabāt melnrakstu. Tas tiks saglabāts kā neaktīvs segments, un to nevar aktivizēt, un tā ir pabeigta, izmantojot derīgu konfigurāciju.

1. Doties uz lapu **Segmenti**.

1. Atlasiet **Jauns** > **Tukšs segments**.

1. **Jaunā segmenta** rūtī izvēlieties segmenta tipu:

   - **Dinamiski segmenti** [tiek atsvaidzināti](segments.md#refresh-segments) pēc periodiska grafika.
   - **Statiskie segmenti** tiek rādīti vienreiz, tos izveidojot.

1. Norādiet segmenta **Izvades entītijas nosaukumu**. Ja vēlaties, norādiet parādāmo nosaukumu un aprakstu, kas palīdz identificēt segmentu.

1. Noklikšķiniet uz **Tālāk**, lai piekļūtu lapai **Segmenta veidotājs**, kurā definējat grupu. Grupa ir klientu kopa.

1. Izvēlieties entītiju, kurā iekļauts atribūts, pēc kura vēlaties segmentēt.

1. Atlasiet atribūtu, pēc kura segmentēt. Šim atribūtam var būt viens no četriem vērtību veidiem: skaitlis, virkne, datums vai Būla vērtība.

1. Izvēlieties operatoru un vērtību atlasītajam atribūtam.

   > [!div class="mx-imgBorder"]
   > ![Pielāgots grupas filtrs.](media/customer-group-numbers.png "Klientu grupas filtrs")

   |Skaitlis |Definīcija  |
   |---------|---------|
   |1     |Elements          |
   |2     |Atribūts          |
   |3    |Operators         |
   |4    |Vērtība         |

   1. Lai grupai pievienotu papildu nosacījumus, varat izmantot divus loģiskos operatorus:

      - **UN** operators: Ir jāizpilda abi nosacījumi kā daļa no segmentācijas procesa. Šī opcija ir visnoderīgākā, kad definējat nosacījumus dažādās entītijās.

      - **Vai** operators: Viens vai otrs no nosacījumiem ir jāizpilda kā segmentācijas procesa daļa. Šī opcija ir visnoderīgākā, kad definējat vairākus nosacījumus vienai entītijai.

      > [!div class="mx-imgBorder"]
      > ![VAI operators, ja kāds no nosacījumiem ir jāizpilda.](media/segmentation-either-condition.png "VAI operators, ja kāds no nosacījumiem ir jāizpilda")

      Pašlaik ir iespējams ligzdot **VAI** operatoru, izmantojot operatoru **UN**, bet ne otrādi.

   1. Katra grupa atbilst klientu kopai. Grupas var apvienot, lai iekļautu biznesa pieteikumam nepieciešamos klientus.    
   Atlasiet **Pievienot grupu**.

      > [!div class="mx-imgBorder"]
      > ![Klientu grupu pievienošanas grupa.](media/customer-group-add-group.png "Klientu grupu pievienošanas grupa")

   1. Atlasiet kādu no iestatītajiem operatoriem: **Apvienošana**, **Krustpunkts** vai **Izņemot**.

   > [!div class="mx-imgBorder"]
   > ![Klientu grupu pievienošanas apvienošana.](media/customer-group-union.png "Klientu grupu pievienošanas apvienošana")

   - **Apvienot** apvieno divas grupas.

   - **Izveidot krustpunktu** pārklāj divas grupas. Vienotajā grupā tiek saglabāti tikai tie dati, kas ir *kopēji* abām grupām.

   - **Izņemot** apvieno divas grupas. Tiek saglabāti tikai A grupas dati, kas *nav kopēji* B grupas datiem.

1. Ja entītija ir savienota ar vienotā klienta entītiju, izmantojot [relācijas](relationships.md), ir jādefinē relāciju ceļš, lai izveidotu derīgu segmentu. Pievienojiet entītijas no attiecību ceļa, līdz varat nolaižamajā sarakstā atlasīt entitīju **Klients: CustomerInsights**. Pēc tam katrai darbībai izvēlieties **Visi ieraksti**.

   > [!div class="mx-imgBorder"]
   > ![Relāciju ceļš segmenta izveides laikā.](media/segments-multiple-relationships.png "Relāciju ceļš segmenta izveides laikā")

1. Pēc noklusējuma segmenti ģenerē izvades entītiju, kurā ir visi klientu profilu atribūti, kas atbilst definētajiem filtriem. Ja segments ir balstīts uz citām entītijām, nevis entītiju *Klients*, izvades entītijai var pievienot papildu atribūtus no šīm entītijām. Atlasiet **Projekta atribūtus**, lai izvēlētos atribūtus, kas tiks pievienoti izvades entītijai.  
  
   Piemērs. Segments tiek veidots, pamatojoties uz entītiju, kurā ir ietverti ar entītiju *Klients* saistīti klienta darbības dati. Segments meklē visus klientus, kas pēdējo 60 dienu laikā zvanījuši palīdzības dienestam. Varat izvēlēties, vai izvades entītijā pievienot sarunas ilgumu un zvanu skaitu visiem atbilstošajiem klientu ierakstiem. Šī informācija var būt noderīga lai nosūtītu e-pasta ziņojumu ar noderīgām saitēm uz tiešsaistes palīdzības rakstiem un bieži uzdotajiem jautājumiem tiem klientiem, kuri zvanījuši bieži.

   > [!NOTE]
   > - Plānotie atribūti darbojas tikai entītijām, kurām ir attiecības viens pret daudziem ar klienta entītiju. Piemēram, vienam klientam var būt vairāki abonementi.
   > - Projekta atribūtus var izveidot tikai no entītijas, kas tiek izmantota katrā veidotā segmenta vaicājuma grupā.
   > - Plānotie atribūti tiek faktorizēti, izmantojot kopas operatorus.

1. Lai saglabātu segmentu, atlasiet **Saglabāt**. Jūsu segments tiks saglabāts un apstrādāts, ja visas prasības ir validētas. Pretējā gadījumā tas tiks saglabāts kā melnraksts.

1. Atlasiet **Atgriezties pie segmentiem**, lai atgrieztos pie **Segmentu** lapas.



## <a name="quick-segments"></a>Ātrie segmenti

Izmantojot ātros segmentus, varat ātri izveidot vienkāršus segmentus, izmantojot vienu operatoru, lai gūtu ātrākus ieskatus.

1. **Segmentu** lapā atlasiet **Jauns** > **Izveidot no**.

   - Atlasiet opciju **Profili**, lai izveidotu segmentu, kura pamatā ir *vienotā klienta* entītija.
   - Atlasiet opciju **Pasākumi**, lai izveidotu segmentu ap iepriekš izveidotajiem pasākumiem.
   - Atlasiet opciju **Informācijas apkopošana**, lai izveidotu segmentu ap vienu no izvades entitījām, kuras izveidojāt, izmantojot iespēju **Prognozes** vai **Pielāgotie modeļi**.

2. Dialoglodziņā **Jauns ātrais segments** atlasiet atribūtu no nolaižamā saraksta **Lauks**.

3. Sistēma sniegs papildu ieskatus, kas palīdz izveidot labākus klientu segmentus.
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
