---
title: Savienot entītijas datu apvienošanai
description: Savienojiet datus, lai izveidotu vienotus klientu profilus.
ms.date: 10/14/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 78549037f9c9e59329f5423c36eeb058128802c0
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406361"
---
# <a name="match-entities"></a>Saskaņojiet entītijas

Pēc kartēšanas posma pabeigšanas varat noteikt atbilstību savām entītijām. Atbilstības posms norāda, kā kombinēt jūsu datu kopas vienotā klienta profila datu kopā. Atbilstības posmā ir nepieciešamas vismaz [divas kartētās entītijas](map-entities.md).

## <a name="specify-the-match-order"></a>Atbilstības noteikšanas secības norādīšana

Pārejiet uz **Apvienošana** > **Atbilstība** un atlasiet **Iestatīt secību**, lai sāktu atbilstības posmu.

Katrā atbilstības noteikšanas gadījumā tiek apvienotas divas vai vairākas entītijas vienā entītijā, saglabājot katru unikālo klienta ierakstu. Nākamajā piemērā ir atlasītas trīs entītijas: **ContactCSV: TestData** kā **primārā** entītija, **WebAccountCSV: TestData** kā **Entītija 2** un **CallRecordSmall: TestData** kā **Entītija 3**. Shēmā virs atlasēm ir parādīts, kā tiks izpildīta atbilstības noteikšanas secība.

> [!div class="mx-imgBorder"]
> ![Datu atbilstības noteikšanas secības rediģēšana](media/configure-data-match-order-edit-page.png "Datu atbilstības noteikšanas secības rediģēšana")
  
**Primārajai** entītijai tiek noteikta atbilstība ar **entītiju 2**. Datu kopai, kas tiek iegūta no pirmās atbilstības noteikšanas, tiek noteikta atbilstība ar **entītiju 3**.
Šajā piemērā tika atlasīti tikai divi atbilstības noteikšanas gadījumi, taču sistēma var atbalstīt vairāk gadījumu.

> [!IMPORTANT]
> Entītija, ko izvēlēsieties kā **primāro** entītiju, tiks izmantota kā pamats jūsu apvienotajai galvenajai datu kopai. Citas entītijai, kas tiks atlasītas atbilstības posmā, tiks pievienotas šai entītijai. Vienlaikus tas nenozīmē, ka apvienotajā entītija būs iekļauti *visi* šajā entītijā esošie dati.
>
> Izvēloties entītiju hierarhiju, apsveriet divus jautājumus:
>
> - Kura entītija, jūsuprāt, ietver vispilnīgākos un uzticamākos datus par jūsu klientiem?
> - Vai entītijai, ko tikko izvēlējāties, ir atribūti, ko koplieto arī citas entītijas (piemēram, vārds, tālruņa numurs vai e-pasta adrese)? Ja nav, izvēlieties otru visuzticamāko entītiju.

Atlasiet **Gatavs**, lai saglabātu atbilstības noteikšanas secību.

## <a name="define-rules-for-your-first-match-pair"></a>Kārtulu definēšana pirmajam atbilstības pārim

Pēc atbilstības noteikšanas secības norādīšanas lapā **Atbilstība** tiks rādīti noteiktie atbilstības noteikšanas gadījumi. Ekrāna augšdaļā esošie elementi būs tukši, līdz izpildīsiet atbilstības noteikšanas secību.

> [!div class="mx-imgBorder"]
> ![Kārtulu definēšana](media/configure-data-match-need-rules.png "Kārtulu definēšana")

Brīdinājums **Ir vajadzīgas kārtulas** norāda, ka atbilstības pārim nav definēta atbilstības kārtula. Atbilstības kārtulas nosaka loģiku, kas tiks izmantota konkrētā entītiju pāra atbilstības noteikšanai.

1. Lai definētu pirmo kārtulu, atveriet rūti **Kārtulas definēšana**, atbilstības tabulā atlasot atbilstošo atbilstības rindu (1) un pēc tam atlasot **Izveidot jaunu kārtulu** (2).

   > [!div class="mx-imgBorder"]
   > ![Jaunas kārtulas izveide](media/configure-data-match-new-rule2.png "Izveidot jaunu kārtulu")

2. Rūtī **Kārtulas rediģēšana** konfigurējiet šīs kārtulas nosacījumus. Katram nosacījumam atbilst divas rindas, kurās ietvertas obligātās atlases.

   > [!div class="mx-imgBorder"]
   > ![Jaunas kārtulas rūts](media/configure-data-match-new-rule-condition.png "Jaunas kārtulas rūts")

   Entītija/Lauks (pirmais) — atribūts, kas tiks izmantots atbilstības noteikšanas no pirmā atbilstības pāra entītijas. Piemēram, tajā var tikt norādīts tālruņa numurs vai e-pasta adrese. Izvēlieties atribūtu, kas varētu būt unikāla klienta informācija.

   > [!TIP]
   > Nav ieteicams noteikt atbilstību pēc darbības tipa atribūtiem. Citiem vārdiem sakot, ja šķiet, ka atribūts ir darbība, iespējams, tas nebūs labs kritērijs, pēc kura noteikt atbilstību.  

   Entītija/Lauks (otrais) — atribūts, kas tiks izmantots atbilstības noteikšanai no otrā atbilstības pāra entītijas.

   Normalizācija — **normalizācijas metode**: atlasītajiem atribūtiem ir pieejamas dažādas normalizācijas opcijas. Piemēram, pieturzīmju noņemšana vai atstarpju noņemšana.

   Organizācijas nosaukuma normalizēšanai (priekšskatījums) varat arī atlasīt **Tips (tālrunis, nosaukums, organizācija)**.

   > [!div class="mx-imgBorder"]
   > ![Normalizācija — B2B](media/match-normalization-b2b.png "Normalizācija — B2B")

   Precizitātes līmenis — precizitātes līmenis, kas tiks izmantots šim nosacījumam. Iestatot precizitātes līmeni atbilstības nosacījumam, var izvēlēties no diviem veidiem: **Pamata** un **Pielāgota**.  
   - Pamata: varat atlasīt kādu no četrām opcijām: zema, vidēja, augsta un precīza. Atlasiet **Precīza**, lai noteiktu atbilstību tikai tādiem ierakstiem, kas atbilst par 100 procentiem. Atlasiet vienu no pārējiem līmeņiem, lai noteiktu atbilstību ierakstiem, kas nav pilnībā identiski.
   - Pielāgota: izmantojiet slīdni, lai noteiktu pielāgotu procentuālo vērtību, kādai ir jāatbilst ierakstiem, vai ievadiet vērtību laukā **Pielāgota**. Sistēma noteiks atbilstība tikai tiem ierakstiem, kas pārsniegs šo sliekšņvērtību kā apvienotie atbilstības pāri. Uz slīdņa ir atrodamas vērtības no 0 līdz 1. Tādējādi 0,64 ir 64 procenti.

3. Atlasiet **Gatavs**, lai saglabātu kārtulu.

### <a name="add-multiple-conditions"></a>Vairāku nosacījumu pievienošana

Lai noteiktu atbilstību entītijām tikai gadījumā, ja tās atbildīs vairākiem nosacījumiem, pievienojiet papildu nosacījumus, kas saistīti, izmantojot operatoru AND.

1. Rūtī **Kārtulas rediģēšana** atlasiet **Pievienot nosacījumu**. Varat arī dzēst nosacījumus, blakus attiecīgajam nosacījumam atlasot pogu Noņemt.

2. Atlasiet **Gatavs**, lai saglabātu kārtulu.

## <a name="add-multiple-rules"></a>Vairāku kārtulu pievienošana

Katrs nosacījums attiecas uz vienu atribūtu pāri, bet kārtulas attiecas uz nosacījumu kopu. Lai atbilstības noteikšanai entītijām tiktu izmantotas dažādas atribūtu kopas, varat pievienot papildu kārtulas.

1. Sadaļā Auditorijas ieskati ejiet uz **Dati** > **Apvienot** > **Savienot**.

2. Atlasiet entītiju, kuru vēlaties atjaunināt, un atlasiet **Pievienot kārtulas**.

3. Veiciet procedūru, kā norādīts sadaļā [Kārtulu definēšana pirmajam atbilstības pārim](#define-rules-for-your-first-match-pair).

> [!NOTE]
> Ir svarīga kārtulu secība. Atbilstošais algoritms mēģina noteikt atbilstību, pamatojoties uz jūsu pirmo kārtulu, un turpina ar otro kārtulu tikai tad, ja pirmā kārtula nenoteica nevienu atbilstību.

## <a name="define-deduplication-on-a-match-entity"></a>Savienotas entītijas dedublēšanas definēšana

Papildus entītiju atbilstības noteikšanas kārtulām, kā norādīts iepriekš minētajās sadaļās, var norādīt arī dedublikātu kārtulas. *Dedublēšana* ir process. Tā identificē ierakstu dublikātus, sapludina tos vienā ierakstā un saista visus avota ierakstus ar šo sapludināto ierakstu ar alternatīviem ID uz sapludināto ierakstu.

Pēc tam, kad ir identificēts nedublēts ieraksts, šis ieraksts tiks izmantots krustenisko entītiju atbilstības procesā. Datu atkārtošana tiek ieviesta entītiju līmenī, un to var lietot katrai entītijai, kas tiek izmantota savienošanas procesā.

### <a name="add-deduplication-rules"></a>Dublikātu noteikšanas kārtulas

1. Sadaļā Auditorijas ieskati ejiet uz **Dati** > **Apvienot** > **Savienot**.

1. Sadaļā **Sapludinātie dublikāti** atlasiet **Iestatīt entītijas**.

1. Sadaļā **Sapludināšanas preferences** atlasiet entītijas, kurām vēlaties piemērot dedublikātus.

1. Norādiet, kā sapludināt ierakstu dublikātus, un izvēlieties vienu no trim sapludināšanas opcijām:
   - *Lielākā daļa* : Tiek identificēts ieraksts, kuram ir visvairāk aizpildīto atribūtu kā uzvarētāju ieraksts. Šī ir noklusējuma sapludināšanas opcija.
   - *Visjaunākais* : Nosaka uzvarētāju, balstoties uz augšupielādes datumu. Ir nepieciešams datums vai skaitlisks lauks, lai definētu augšupielādes datumu.
   - *Visvecākais* : Nosaka uzvarētāju, balstoties uz visvecāko augšupielādes datumu. Ir nepieciešams datums vai skaitlisks lauks, lai definētu augšupielādes datumu.
 
   > [!div class="mx-imgBorder"]
   > ![Dublikātu noteikšanas kārtulas pirmā darbība](media/match-selfconflation.png "Dedublēšanas kārtulu pirmā darbība")
 
1. Kad entītijas ir atlasītas un ir iestatītas to sapludināšanas preferences, atlasiet vienumu **Izveidot jaunu kārtulu**, lai entītiju līmenī definētu dedublēšanas kārtulas.
   - **Atlasiet lauku**, kurā ir uzskaitīti visi pieejamie lauki no tās entītijas, kurā vēlaties atveidot avota datu dublikātus.
   - Norādiet normalizācijas un precizitātes iestatījumus līdzīgā veidā, kā norādīts krusteniskās entītijas atbilstības sistēmā.
   - Varat definēt papildu nosacījumus, atlasot **Pievienot nosacījumu**.
 
   > [!div class="mx-imgBorder"]
   > ![Dublikātu noteikšanas kārtulas otrā darbība](media/match-selfconflation-rules.png "Dedublēšanas kārtulu otrā darbība")

  Varat izveidot vairākas dedublēšanas kārtulas vienai entītijai. 

1. Izpildot atbilstības procesu, tagad tiek grupēti ieraksti, kas balstīti uz nosacījumiem, kas definēti datu dedublēšanas kārtulās. Pēc ierakstu grupēšanas sapludināšanas politika tiek lietota, lai noteiktu uzvarētāju ierakstu.

1. Pēc tam šis uzvarētāja ieraksts tiek nodots pārrobežu entītiju saskaņošanai.

1. Visas pielāgotās atbilstības kārtulas, kas definētas, vienmēr atbilst un nekad neatbilst nenoraidītajām dedublēšanas kārtulām. Ja atkārtošanas kārtula identificē atbilstošos ierakstus, un pielāgota atbilstības kārtula ir iestatīta, lai nekad neatbilstu šiem ierakstiem, tad šie divi ieraksti netiek saskaņoti.

1. Pēc saskaņošanas procesa izpildes tiks parādīts dedublēšanas statistiku.
   
> [!NOTE]
> Norādīšanas kārtulu norādīšana nav obligāta. Ja šādas kārtulas nav konfigurētas, tiek lietotas sistēmas definētās kārtulas. Tie sakļauj visus ierakstus, kuriem ir tāda pati vērtības kombinācija (precīza sakritība) no primārās atslēgas un atbilstības kārtulu laukiem vienā ierakstā, pirms entītijas dati tiek nodoti pārrobežu entītiju saskaņošanai, lai uzlabotu veiktspēju un sistēmas veselo saprātu.

## <a name="run-your-match-order"></a>Atbilstības noteikšanas secības izpilde

Pēc atbilstības kārtulu definēšanas, tostarp attiecībā uz pārrobežu entītiju atbilstību un dedublēšanas kārtulām, varat izpildīt atbilstības pasūtījumu. Lapā **Atbilstība** atlasiet **Izpildīt**, lai sāktu procesu. Var paiet zināms laiks, līdz atbilstības algoritms tiks pabeigts. Lapā **Atbilstība** esošos rekvizītus nevar mainīt, kamēr nav pabeigts atbilstības process. Jūs atradīsiet vienotā klienta profila entītiju, kas tika izveidota lapā **Entītijas**. Vienotās klienta entītijas nosaukums ir **ConflationMatchPairs: CustomerInsights**.

Lai veiktu papildu izmaiņas un atkārtoti palaistu darbību, varat atcelt notiekošu saskaņošanu. Atlasiet tekstu **Atsvaidzina...** un atlasiet **Atcelt uzdevumu** apakšā sānu rūtij, kura parādās.

Kad saskaņošanas process ir pabeigts, teksts **Atsvaidzina...** tiks nomainīts uz **Veiksmīgi** un jūs varēsit izmantot visu lapas funkcionalitāti.

Pēc pirmā atbilstības noteikšanas procesa ir izveidota apvienota galvenā entītija. Visu turpmāko atbilstības noteikšanas gadījumu rezultātā notiks šīs entītijas paplašināšanās.

> [!TIP]
> Uzdevumiem/procesiem ir [seši statusu tipi](system.md#status-types). Turklāt vairums procesu [ir atkarīgi no citiem pakārtotiem procesiem](system.md#refresh-policies). Varat atlasīt procesa statusu, lai skatītu detalizētu informāciju par visa uzdevuma norisi. Pēc tam, kad vienam no darba uzdevumiem esat atlasījis **Skatīt detalizētu informāciju**, jūs redzēsit papildinformāciju: apstrādes laiku, pēdējās apstrādes datumu un visas kļūdas un brīdinājumus, kas saistīti ar uzdevumu.

## <a name="review-and-validate-your-matches"></a>Atbilstību pārskatīšana un pārbaudīšana

Novērtējiet atbilstības pāru kvalitāti un precizējiet to.

- Lapā **Atbilstība** ir ietverti divi elementi, kas parāda sākotnējos ieskatus par jūsu datiem.

  - **Unikālie klienti**: parāda to unikālo profilu skaitu, ko sistēma ir identificējusi.
  - **Ieraksti ar atbilstību**: parāda atbilstību skaitu visos atbilstības pāros.

- Tabulā **Atbilstības noteikšanas secība** varat novērtēt katra atbilstības pāra rezultātus, salīdzinot to ierakstu skaitu, kas iegūti no šī atbilstības pāra entītijas, attiecībā pret to ierakstu procentuālo vērtību, kuriem tika veiksmīgi noteikta atbilstība.

- Entītijas sadaļā **Kārtulas** tabulā **Atbilstības noteikšanas secība** ir norādīta to ierakstu procentuālā vērtība kārtulu līmenī, kuriem tika veiksmīgi noteikta atbilstība. Atlasot tabulas simbolu blakus kārtulai, varat skatīt visus šos ierakstus kārtulu līmenī. Ieteicams pārskatīt ierakstu apakškopu, lai pārliecinātos, ka to atbilstība tika noteikta pareizi.

- Eksperimentējiet ar dažādām precizitātes sliekšņvērtībām attiecībā uz saviem nosacījumiem, lai noteiktu optimālo vērtību.

  1. Atlasiet daudzpunkti (...) tai atbilstības pāra kārtulai, ar kuru vēlaties eksperimentēt, un atlasiet **Rediģēt**.

  2. Atlasiet nosacījumu, ar kuru vēlaties eksperimentēt. Katram kritērijam atbilst viena rinda rūtī **Atbilstības kārtula**.

  3. Tas, kāds saturs tiks rādīts lapā **Kritēriju priekšskatījums**, ir atkarīgs no nosacījumam atlasītā precizitātes līmeņa. Atrodiet atbilstošo un neatbilstošo ierakstu skaitu atlasītajam nosacījumam.

     Iegūstiet plašāku izpratni par dažādu sliekšņa līmeņu ietekmi. Varat salīdzināt, cik daudz ierakstiem tiks noteikta atbilstība katrā no sliekšņa līmeņiem, kā arī skatīt ierakstus katras opcijas gadījumā. Atlasiet katru no elementiem un pārskatiet datus tabulas sadaļā.

## <a name="optimize-your-matches"></a>Atbilstību optimizēšana

Palieliniet kvalitāti, pārkonfigurējot dažus no atbilstības parametriem.

- **Mainiet atbilstības noteikšanas secību**, atlasot **Rediģēt**, un mainiet atbilstības noteikšanas secības laukus.

  > [!div class="mx-imgBorder"]
  > ![Datu atbilstības noteikšanas secības rediģēšana](media/configure-data-match-order-edit.png "Datu atbilstības noteikšanas secības rediģēšana")

- **Mainiet kārtulu secību**, ja definējāt vairākas kārtulas. Varat mainīt atbilstības kārtulu secību, atbilstības kārtulu režģī atlasot opcijas **Pārvietot augšup** un **Pārvietot lejup**.

  > [!div class="mx-imgBorder"]
  > ![Kārtulu secības mainīšana](media/configure-data-change-rule-order.png "Kārtulu secības mainīšana")

- **Dublējiet kārtulas**, ja esat definējis atbilstības kārtulu un vēlaties izveidot līdzīgu kārtulu ar modifikācijām. Lai to izdarītu, atlasiet **Dublikāts**.

  > [!div class="mx-imgBorder"]
  > ![Kārtulas dublicēšana](media/configure-data-duplicate-rule.png "Kārtulas dublicēšana")

- **Rediģējiet kārtulas**, atlasot **rediģēšanas** simbolu. Varat veikt tālāk norādītās izmaiņas.

  - Mainiet nosacījuma atribūtus: atlasiet jaunus atribūtus konkrētā nosacījuma rindā.
  - Mainiet nosacījuma sliekšņvērtību: pielāgojiet precizitātes slīdni.
  - Mainiet nosacījuma normalizācijas metodi: atjauniniet normalizācijas metodi.

## <a name="specify-your-custom-match-records"></a>Pielāgotas atbilstības ierakstu norādīšana

Varat norādīt nosacījumus, kuriem ierakstiem ir vienmēr jāatbilst vai nekad nav jāatbilst. Šīs kārtulas atbilstības noteikšanas procesā varat augšupielādēt lielapjomā.

1. Ekrānā **Atbilstības noteikšanas secība** atlasiet opciju **Pielāgota atbilstība**.

   > [!div class="mx-imgBorder"]
   > ![Pielāgotas atbilstības izveide](media/custom-match-create.png "Pielāgotas atbilstības izveide")

2. Ja jums nav augšupielādētu entītiju, tiks parādīts jauns dialoglodziņš **Pielāgota atbilstība**, kurā būs jāievada dati. Ja jau iepriekš ievadījāt šos datus, pārejiet uz 8. darbību.

   > [!div class="mx-imgBorder"]
   > ![Dialoglodziņš Jauna pielāgotā atbilstība](media/custom-match-new-dialog-box.png "Dialoglodziņš Jauna pielāgotā atbilstība")

3. Atlasiet **Aizpildīt veidni**, lai iegūtu veidnes failu, kurā var norādīt, kuriem ieraksti no kurām entītijām ir vienmēr jāatbilst vai nekad nav jāatbilst. Jums būs atsevišķi divos dažādos failos jānorāda ieraksti, kam “vienmēr jāatbilst” un “nekad nav jāatbilst”.

4. Veidnē ir ietverti lauki, kuros jānorāda entītija un entītijas primārās atslēgas vērtības, kas tiks izmantotas pielāgotajā atbilstībā. Piemēram, ja vēlaties, lai primārā atslēga 12345 no entītijas Pārdošana vienmēr atbilstu primārajai atslēgai 34567 no entītijas Kontaktpersona, ir jānorāda šādi dati:
    - Entity1: Pārdošana
    - Entity1Key: 12345
    - Entity2: Kontaktpersona
    - Entity2Key: 34567

   Viens un tas pats veidnes fails var norādīt pielāgotās atbilstības ierakstus no vairākām entītijām.

5. Kad būsiet pievienojis visus vēlamos labojumus, saglabājiet veidnes failu.

6. Ejiet uz **Dati** > **Datu avoti** un uzņemiet veidnes failus kā jaunas entītijas. Pēc pieņemšanas tos varēsiet izmantot, lai norādītu atbilstības konfigurāciju.

7. Pēc failu un entītiju augšupielādes vēlreiz atlasiet opciju **Pielāgota atbilstība**. Tiks parādītas opcijas, lai norādītu entītijas, ko vēlaties iekļaut. Nolaižamajā izvēlnē atlasiet nepieciešamās entītijas.

   > [!div class="mx-imgBorder"]
   > ![Pielāgotās atbilstības labojumi](media/custom-match-overrides.png "Pielāgotās atbilstības labojumi")

8. Atlasiet entītijas, ko vēlaties izmantot opcijām **Vienmēr atbilst** un **Nekad neatbilst**, atlasiet **Gatavs**.

9. Lapā **Atbilstība** atlasiet **Saglabāt** pielāgotās atbilstības konfigurācijai, ko tikko iestatījāt.

10. Lapā **Atbilstība** atlasiet **Palaist** lapā, lai sāktu atbilstības noteikšanas procesu, un sāks darboties pielāgotās atbilstības konfigurācija. Visas sistēmas piesaistītās kārtulas labos konfigurācijas kopa.

11. Pēc atbilstības noteikšanas varat verificēt entītiju **ConflationMatchPair**, lai apstiprinātu, ka labojumi tiek lietoti apvienojuma atbilstībās.

## <a name="next-step"></a>Nākamā darbība

Kad būsiet pabeidzis atbilstības noteikšanas procesu vismaz vienam atbilstības pārim, varat atrisināt iespējamās pretrunas savos datos, pārskatot tēmu [**Sapludināšana**](merge-entities.md).
