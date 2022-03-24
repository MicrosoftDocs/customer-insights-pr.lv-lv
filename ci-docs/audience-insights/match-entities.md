---
title: Savienot entītijas datu apvienošanai
description: Savienojiet datus, lai izveidotu vienotus klientu profilus.
ms.date: 02/07/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-map
- customerInsights
ms.openlocfilehash: ab4ab0dba1bd91b1893cd4b16b8d51381d5b6ef8
ms.sourcegitcommit: 50d32a4cab01421a5c3689af789e20857ab009c4
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 03/03/2022
ms.locfileid: "8376931"
---
# <a name="match-entities"></a>Saskaņojiet entītijas

Atbilstības posms norāda, kā kombinēt jūsu datu kopas vienotā klienta profila datu kopā. Pēc [kartējuma darbības](map-entities.md) pabeigšanas datu unificēšanas procesā esat gatavs saskaņot savas entītijas. Atbilstības posmā ir nepieciešamas vismaz divas kartētās entītijas.

Atbilstības lapā ir trīs sadaļas: 
- Galvenās metrikas, kas apkopo atbilstošo ierakstu skaitu
- Atbilstības secība un kārtulas atbilstības starp entītijām saskaņošanai
- Atbilstības entītiju dedublikācijas kārtulas

## <a name="specify-the-match-order"></a>Atbilstības noteikšanas secības norādīšana

Katra atbilstība apvieno divas vai vairākas entītijas vienā, konsolidētā entītijā. Vienlaikus tiek glabāti unikālie klientu ieraksti. Atbilstības secība norāda secību, kādā sistēma mēģina saskaņot ierakstus.

> [!IMPORTANT]
> Entītija, ko izvēlaties kā primāro entītiju, tiks izmantota par pamatu jūsu apvienotajai profilu datu kopai. Citas entītijai, kas tiks atlasītas atbilstības posmā, tiks pievienotas šai entītijai. Tas nozīmē, ka vienotā entītija ietvers *visus* šajā entītijā iekļautos datus.
>
> Izvēloties entītiju hierarhiju, apsveriet divus jautājumus:
>
> - Izvēlieties entītiju ar vispilnīgākajiem un uzticamākajiem profila datiem par klientiem kā primāro entītiju.
> - Kā primāro entītiju izvēlieties entītiju, kurai ir vairāki atribūti, kas ir kopīgi ar citām entītijām (piemēram, vārdu, tālruņa numuru vai e-pasta adresi).

1. Dodieties uz **Dati** > **Apvienot** > **Savienot** un atlasiet **Iestatīt pasūtījumu**, lai sāktu atbilstības posmu.
1. Atlasiet **Entītijas pasūtījums**. Piemēram, atlasiet **e-komercija:eCommerceKontakti** kā primāro entītiju un **LoyaltyScheme:loyCustomers** kā otro entītiju. 
1. Lai katrs entītijas ieraksts būtu unikāls klients un saskaņots ar katru nākamo entītiju, atlasiet **Iekļaut visu**.
1. Atlasiet **Gatavs**. 

Pēc atbilstības secības norādīšanas definētie sērkociņu pāri tiek parādīti **DataUnifyMatch** **·** > **sadaļā Detalizēta informācija** > **par** saskaņotajiem ierakstiem. Galvenie rādītāji ir tukši, līdz atbilstības process ir pabeigts.

:::image type="content" source="media/match-page.png" alt-text="Datu unificēšanas procesa Saskaņošana lapas apgabala Unify ekrānuzņēmums.":::
  
Primārā entītija *eCommerce:eCommerceContacts* tiek saskaņota ar nākamo entītiju *LoyaltyScheme:loyCustomers*. Datu kopa, kas izriet no pirmās atbilstības soļa, tiek saskaņota ar šo entītiju, ja jums ir vairāk nekā divas entītijas.

## <a name="define-rules-for-match-pairs"></a>Kārtulu definēšana atbilstības pāriem

Atbilstības kārtulas nosaka loģiku, kas tiks izmantota konkrētā entītiju pāra atbilstības noteikšanai.

No brīdinājuma **Nepieciešamas kārtulas** blakus entītijas nosaukumam izriet, ka atbilstības pārim nav definēta atbilstības kārtula. 

:::image type="content" source="media/match-rule-add.png" alt-text="Sadaļas Informācija par saskaņotajiem ierakstiem ekrānuzņēmumu ar vadīklu, lai pievienotu iezīmētas kārtulas.":::

1. Sadaļā Detalizēta informācija **par saskaņotiem ierakstiem sadaļā Entītijas atlasiet** Pievienot **kārtulu**, lai definētu atbilstības kārtulas.

1. Rūtī **Izveidot kārtulu** konfigurējiet kārtulas nosacījumus.

   :::image type="content" source="media/match-rule-conditions.png" alt-text="Atvērtas atbilstības kārtulas ekrānuzņēmumu ar pievienotiem nosacījumiem.":::

   - **Entītija/lauks (pirmā rinda)**: izvēlieties saistītu entītiju un atribūtu, lai norādītu klientam unikālu ieraksta rekvizītu. Piemēram, tālruņa numuru vai e-pasta adresi. Izvairieties no saskaņošanas pēc darbības veida atribūtiem. Piemēram, visticamāk, ka pirkuma ID nebūs atbilsmes citos ierakstu veidos.

   - **Entītija/lauks (otrā rinda)**: izvēlieties atribūtu, kas saistīts ar pirmajā rindā norādīto entītijas atribūtu.

   - **Normalizēt**: atlasiet atlasīto atribūtu normalizēšanas opcijas. 
     - Cipari: pārvērš citas ciparu sistēmas, piemēram, latīņu valodas ciparus, par arābu cipariem. *VIII* kļūst par *8*.
     - Simboli: noņem visus simbolus un speciālās rakstzīmes. *Head&Shoulder* kļūst par *HeadShoulder*.
     - Teksts un mazie burti: pārvērš visas rakstzīmes par mazajiem burtiem. *VISI LIELIE BURTI un Virsraksta burti* kļūst par *visi lielie burti un virsraksta burti*.
     - Tips (tālrunis, vārds, adrese, organizācija): standartizē vārdus, virsrakstus, tālruņa numurus, adreses utt. 
     - Unikods uz ASCII: pārvērš unikoda notāciju par ASCII rakstzīmēm. */u00B2* kļūst par *2*.
     - Baltstarpa: noņem visas atstarpes. *Labdien, pasaule* kļūst par *HelloWorld*.

   - **Precizitāte**: iestata šim nosacījumam piemēroto precizitātes līmeni. 
     - **Pamata**: izvēlēties no *Zems*, *Vidējs*, *Augsts* un *Precīzs*. Atlasiet **Precīzs**, lai atbilstu tikai tiem ierakstiem, kas atbilst 100 procentiem. Atlasiet vienu no pārējiem līmeņiem, lai noteiktu atbilstību ierakstiem, kas nav pilnībā identiski.
     - **Pielāgots**: iestatiet procentuālu vērtību, kurai ierakstiem jāatbilst. Sistēma saskaņos tikai ierakstus, kas pārsniedz šo robežvērtību.

1. Norādiet kārtulas **Nosaukumu**.

1. [Pievienojiet papildu nosacījumus](#add-conditions-to-a-rule) vai atlasiet **Pabeigts**, lai pabeigtu kārtulu.

1. Ja vēlaties, [pievienojiet citas kārtulas](#add-rules-to-a-match-pair).

1. Lai veiktās izmaiņas stātos spēkā, atlasiet **Saglabāt**.

### <a name="add-conditions-to-a-rule"></a>Nosacījumu pievienošana kārtulai

Lai saskaņotu entītijas tikai tad, ja atribūti atbilst vairākiem nosacījumiem, pievienojiet papildu nosacījumus atbilstības kārtulai. Nosacījumi ir saistīti ar loģiku UN operatoru, un tādējādi tiek izpildīti tikai tad, ja ir izpildīti visi nosacījumi.

1. Pārejiet uz sadaļu **Dati** > **Unify** > **Saskaņot** un atlasiet **Rediģēt** kārtulai, kurai vēlaties pievienot nosacījumus.

1. Rūtī **Kārtulas rediģēšana** atlasiet **Pievienot nosacījumu**.

1. Atlasiet **Gatavs**, lai saglabātu kārtulu.

### <a name="add-rules-to-a-match-pair"></a>Kārtulu pievienošana atbilstības pārim

Atbilstības kārtulas pārstāv nosacījumu kopas. Lai entītijas saskaņotu ar nosacījumiem, kuru pamatā ir vairāki atribūti, pievienojiet papildu kārtulas.

1.  Pārejiet uz sadaļu **Dati** > **Unify** > **Saskaņot** un atlasiet **Pievienot kārtulu** entītijai, kurai vēlaties pievienot kārtulas.

2. Izpildiet darbības sadaļā [Kārtulu definēšana atbilstības pāriem](#define-rules-for-match-pairs).

> [!NOTE]
> Kārtulu secība ir svarīga. Atbilstības noteikšanas algoritms mēģina saskaņot atbilstoši jūsu pirmajai kārtulai un turpina otro kārtulu tikai tad, ja ar pirmo kārtulu netiek noteiktas atbilstības.

### <a name="change-the-entity-order-in-match-rules"></a>Entītijas secības maiņa kārtulās

Varat pārkārtot atbilstības kārtulu entītijas, lai mainītu to apstrādes secību. Kārtulas, kas konfliktē mainīta pasūtījuma dēļ, tiks noņemtas. Noņemtās kārtulas ir jāveido atkārtoti, izmantojot atjauninātu konfigurāciju.

1. Dodieties uz **Dati** > **Apvienot** > **Saskaņot** un atlasiet **Rediģēt**.

1. **Kārtulu rediģēšanas** rūtī atlasiet vadīklu **Pārvietot uz augšu/uz leju** vai velciet un nometiet entītijas, lai mainītu secību.

   :::image type="content" source="media/reorder-match-rules.png" alt-text="Opcijas, ar kurām var mainīt pasūtījuma entītiju apstrādi atbilstības kodā.":::

1. Atlasiet **Gatavs**, lai saglabātu kārtulu.

## <a name="define-deduplication-on-a-match-entity"></a>Savienotas entītijas dedublēšanas definēšana

Papildus [entītiju atbilstības kārtulām](#define-rules-for-match-pairs) varat norādīt arī dedublikātu kārtulas. *Dedublikācija* ir cits process, kad tiek notiek ierakstu saskaņošana. Tas identificē ierakstu dublikātus un sapludina tos vienā ierakstā. Avota ieraksti tiek saistīti ar sapludināto ierakstu, izmantojot alternatīvus ID.

Dedulicēti ieraksti tiek izmantoti vairāk entītiju salīdzināšanas procesā. Deduplifikācija notiek atsevišķās entītijās, un to var konfigurēt katrai entītijai, kas tiek izmantota spēļu pāros.

Norādīšanas kārtulu norādīšana nav obligāta. Ja šādas kārtulas nav konfigurētas, tiek lietotas sistēmas definētās kārtulas. Tie visus ierakstus apvieno vienā ierakstā pirms entītijas datu nodošanas saskaņošanai starp entītijām, lai uzlabotu veiktspēju.

### <a name="add-deduplication-rules"></a>Dublikātu noteikšanas kārtulas

1. Ejiet uz **Dati** > **Unify** > **Saskaņot**.

1. Sadaļā Detalizēta informācija par **dublējtiem** ierakstiem atlasiet **Iestatīt entītijas**. Ja dedublikācijas kārtulas jau ir izveidotas, atlasiet **Rediģēt**.

1. Rūtī **Sapludināšanas preferences** izvēlieties entītijas, kurām vēlaties palaist dedublikāciju.

   1. Norādiet, kā apvienot ierakstu dublikātus, un izvēlieties vienu no trim opcijām:
      - **Lielākā daļa** : tiek identificēts ieraksts, kuram ir visvairāk aizpildīto atribūtu lauku kā uzvarētāju ieraksts. Tā ir noklusējuma sapludināšanas opcija.
      - **Visjaunākais** : Nosaka uzvarētāju, balstoties uz augšupielādes datumu. Ir nepieciešams datums vai skaitlisks lauks, lai definētu augšupielādes datumu.
      - **Visvecākais** : Nosaka uzvarētāju, balstoties uz visvecāko augšupielādes datumu. Ir nepieciešams datums vai skaitlisks lauks, lai definētu augšupielādes datumu.

   1. Pēc izvēles, lai definētu dedupikācijas kārtulas atsevišķiem entītijas atribūtiem, atlasiet **Papildu**. Piemēram, varat izvēlēties paturēt jaunāko e-pasta ziņojumu UN vispilnīgāko adresi no dažādiem ierakstiem. Izvērsiet entītiju, lai skatītu visus tās atribūtus un definētu, kuru opciju izmantot atsevišķiem atribūtiem. Ja izvēlaties uz atsvešinātību balstītu opciju, ir jānorāda arī datuma/laika lauks, kas definē atsvešinātību. 
 
      > [!div class="mx-imgBorder"]
      > ![Dublikātu noteikšanas kārtulas 1. darbība.](media/match-selfconflation.png "Dedublēšanas kārtulu pirmā darbība")

   1. Atlasiet **Gatavs**, lai lietotu sapludināšanas preferences deduplifikācijai.
 
1. Kad entītijas ir atlasītas un ir iestatītas to sapludināšanas preferences, atlasiet vienumu **Pievienot kārtulu**, lai entītiju līmenī definētu dedublikācijas kārtulas.
   - **Atlasīt laukus** uzskaita visus no šīs entītijas pieejamos laukus. Izvēlieties lauku, kura dublikātus vēlaties pārbaudīt. Izvēlieties laukus, kas, visticamāk, ir unikāli katram atsevišķam klientam. Piemēram, e-pasta adrese vai vārda, pilsētas un tālruņa numura kombinācija.
   - Norādiet normalizēšanas un precizitātes iestatījumus.
   - Definējiet vairāk nosacījumu, atlasot **Pievienot nosacījumu**.
 
   > [!div class="mx-imgBorder"]
   > ![Dublikātu noteikšanas kārtulas 2. darbība.](media/match-selfconflation-rules.png "Dedublēšanas kārtulu otrā darbība")

  Varat izveidot vairākas dedublēšanas kārtulas vienai entītijai. 

1. Izpildot atbilstības procesu, tagad tiek grupēti ieraksti, kas balstīti uz nosacījumiem, kas definēti datu dedublēšanas kārtulās. Pēc ierakstu grupēšanas sapludināšanas politika tiek lietota, lai noteiktu uzvarētāju ierakstu.

1. Pēc tam šis uzvarētāja ieraksts tiek nodots entītiju atbilstības noteikšanai kopā ar ierakstiem, kas nav uzvarētāji (piemēram, alternatīvie ID), lai uzlabotu atbilstošo kvalitāti.

1. Jebkuras pielāgotas atbilstības kārtulas, kas definētas kā pārrakstīšanas dedublikācijas kārtulas. Ja atkārtošanas kārtula identificē atbilstošos ierakstus, un pielāgota atbilstības kārtula ir iestatīta, lai nekad neatbilstu šiem ierakstiem, tad šie divi ieraksti netiek saskaņoti.

1. Pēc [atbilstības procesa](#run-the-match-process) izpildes galvenajās metrikas elementos būs redzama dedupikācijas statistika.

### <a name="deduplication-output-as-an-entity"></a>Dedublikācijas izvade kā entītija

Dedublēšanas process izveido jaunu entītiju katrai entītijai no atbilstības pāriem, lai identificētu dedublētos ierakstus. Šīs entītijas var atrast kopā ar **ConflationMatchPairs:CustomerInsights** sadaļā **Sistēma** lapā **Entītijas** ar nosaukumu **Deduplication_DataSource_Entity**.

Dedublikācijas izvades entītija ietver šādu informāciju:
- ID/ Atslēgas
  - Primārās atslēgas lauks un tā alternatīvais ID lauks. Alternatīvais ID lauks sastāv no visiem alternatīviem ID, kas identificēti ierakstam.
  - Deduplication_GroupId lauks rāda grupu vai klasteru, kas identificēts entītijā, kas grupē visus līdzīgos ierakstus, pamatojoties uz norādītajiem dedublikācijas laukiem. To izmanto sistēmas apstrādes nolūkiem. Ja nav norādītas manuālas dedublikācijas kārtulas un tiek lietotas sistēmas definētās dedublikācijas kārtulas, varat neatrast šo lauku dedublikācijas izvades entītijā.
  - Deduplication_WinnerId: šajā laukā ir norādīts identificēto grupu vai klasteru uzvarētāja ID. Ja Deduplication_WinnerId vērtība ir tāda pati kā ieraksta primārās atslēgas vērtība, tas nozīmē, ka ieraksts ir uzvarētāja ieraksts.
- Lauki, ko lieto dedublikācijas kārtulu definēšanai.
- Kārtulu un punktu skaita lauki, lai apzīmētu, kuras no dedublikācijas kārtulām tika lietotas, un punktu skaitu, kas tika atgriezts, veicot atbilstošu aizstāšanu.
 
## <a name="include-enriched-entities-preview"></a>Bagātinātu entītiju iekļaušana (priekšskatījums)

Ja bagātinātas entītijas datu avots līmenī, atlasiet tās pirms atbilstības procesa izpildes. Bagātinātās entītijas var uzlabot jūsu apvienošanas rezultātus. Plašāku informāciju skatiet [Enrichment for data sources](data-sources-enrichment.md). 

Bagātinātā entītija satur sākotnējos datu avots laukus un bagātinātos laukus. Tātad, ja izvēlaties strādāt ar bagātināto entītiju, esošā konfigurācija netiek ietekmēta. Tomēr, iespējams, būs jāatjaunina atbilstības kārtulas, lai tā vietā izmantotu bagātinātos laukus.

1. Dodieties uz **DataUnifyMatch** > **·** > **un** lapas augšdaļā atlasiet **Izmantot bagātinātas entītijas.**

1. **Rūtī Bagātināto entītiju** izmantošana izvēlieties vienu vai vairākas bagātinātas entītijas.

1. Atlasiet **Gatavs**. Visur, kur tiek izmantota avota entītija (piemēram, atbilstības secība vai kārtulas), tā tiek automātiski mainīta uz bagātināto entītiju.
  
## <a name="run-the-match-process"></a>Saskaņošanas procesa izpilde

Ar konfigurētām atbilstības kārtulām, tostarp saskaņošanu starp entītijām un dedublēšanas kārtulām, varat palaist saskaņošanas procesu. 

Pārejiet uz sadaļu **Dati** > **Unify** > **Saskaņot** un atlasiet **Palaist**, lai sāktu procesu. Saskaņošanas algoritmam nepieciešams zināms laiks, un jūs nevarat mainīt konfigurāciju, kamēr tas nav pabeigts. Lai veiktu izmaiņas, varat atcelt izpildi. Atlasiet darba statusu un atlasiet **Atcelt darbu** rūtī **Informācija par norisi**.

Sekmīgas izpildes rezultāts ir vienotā klienta profila entītija, kas atrodas lapā **Entītijas**. Jūsu apvienotā klientu entītija tiek saukta par **Klientiem** sadaļā **Profili** section. Pirmajā sekmīgās atbilstības izpildes laikā tiek izveidota vienotā entītija *Klients*. Visas nākamās saskaņošanas izpildes izvērš šo entītiju.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="review-and-validate-your-matches"></a>Atbilstību pārskatīšana un pārbaudīšana

Dodieties uz **Dati** > **Unify** > **Saskaņot**, lai novērtētu jūsu atbilstības pāru kvalitāti un vajadzības gadījumā tos attīrītu.

Lapas augšdaļā redzamajās elementos ir parādītas galvenās metrikas, apkopojot saskaņoto ierakstu un dublikātu skaitu.

:::image type="content" source="media/match-KPIs.png" alt-text="Lapā Saskaņošana apgriezts galveno metriku ekrānuzņēmums ar skaitļiem un informāciju.":::

- **Unikālie avota ieraksti** norāda atsevišķu avota ierakstu skaitu, kas tika apstrādāti pēdējās saskaņošanas izpildes laikā.
- **Saskaņotie un nesaskaņotie ieraksti** uzsver, cik daudz unikālu ierakstu saglabājas pēc atbilstības kārtulu apstrādes.
- **Tikai saskaņotie ieraksti** parāda tikai atbilstību skaitu visos jūsu atbilstības pāros.

Varat novērtēt katra atbilstības pāra un tā kārtulu rezultātus tabulā **Informācija par saskaņotajiem ierakstiem**. Salīdziniet to ierakstu skaitu, kuri tika atlasīti no atbilstības pāra, ar sekmīgi saskaņoto ierakstu procentuālo vērtību.

Pārskatiet atbilstības pāra kārtulas, lai kārtulu līmenī redzētu sekmīgi saskaņoto ierakstu procentuālo vērtību. Atlasiet daudzpunkti (...) un pēc tam atlasiet **Atbilstības priekšskatījums**, lai skatītu visus šos ierakstus kārtulas līmenī. Ieteicams apskatīt dažus ierakstus, lai pārbaudītu, vai tie ir pareizi saskaņoti.

Izmēģiniet citas precizitātes robežvērtības nosacījumos, lai atrastu optimālo vērtību.

  1. Atlasiet daudzpunkti (...) kārtulai, ar kuru vēlaties eksperimentēt, un atlasiet **Rediģēt**.

  2. Mainiet precizitātes vērtības nosacījumos, ko vēlaties pārskatīt.

  3. Atlasiet **Priekšskatījums**, lai skatītu atlasītā nosacījuma saskaņoto un nesaskaņoto ierakstu skaitu.

## <a name="manage-match-rules"></a>Atbilstības kārtulu pārvaldība

Varat pārkonfigurēt un pielāgot lielāko daļu atbilstības parametru.

:::image type="content" source="media/match-rules-management.png" alt-text="Nolaižamās izvēlnes ekrānuzņēmums ar atbilstības kārtulas opcijām.":::

- **Mainiet kārtulu secību**, ja definējāt vairākas kārtulas. Varat pārkārtot atbilstības kārtulas, atlasot opcijas **Pārvietot uz augšu** un **Pārvietot uz leju** vai velkot un nometot.

- **Mainiet kārtulas nosacījumus**, atlasot vienumu **Rediģēt**, un izvēlieties citus laukus.

- **Deaktivizēt kārtulu**, lai saglabātu atbilstības kārtulu, to izslēdzot no atbilstības noteikšanas procesa.

- **Dublicējiet kārtulas**, ja esat definējis atbilstības kārtulu un vēlaties izveidot līdzīgu kārtulu ar modifikācijām, atlasot **Dublicēt**.

- **Dzēsiet kārtulu**, atlasot simbolu **Dzēst**.

## <a name="advanced-options"></a>Papildiespējas

### <a name="add-exceptions-to-a-rule"></a>Izņēmumu pievienošana kārtulai

Vairumā gadījumu entītiju salīdzināšana noved pie unikāliem lietotāju profiliem ar konsolidētiem datiem. Lai dinamiski risinātu retos viltus pozitīvo un kļūdaini negatīvos gadījumos, atbilstības kārtulai var definēt izņēmumus. Izņēmumi tiek piemēroti pēc atbilstības kārtulu apstrādes un izvairieties no visu ierakstu atbilstības atbilstības, kas atbilst izņēmuma kritērijiem.

Piemēram, ja atbilstības kārtula apvieno uzvārds, pilsētu un dzimšanas datumu, sistēma identificēs dvīņus ar tādiem pašiem uzvārds, kuri dzīvo vienā pilsētā ar to pašu profilu. Varat norādīt izņēmumu, kas neatbilst profiliem, ja vārds apvienotajās entītijās nav vienādas.

1. Pārejiet uz sadaļu **Dati** > **Unify** > **Saskaņot** un atlasiet **Rediģēt** kārtulai, kurai vēlaties pievienot nosacījumus.

1. Kārtulu **rūtī** Rediģēt atlasiet **Pievienot izņēmumu**.

1. Norādiet izņēmuma kritērijus. 

1. Atlasiet **Gatavs**, lai saglabātu kārtulu.

### <a name="specify-custom-match-conditions"></a>Pielāgotu atbilstības nosacījumu norādīšana

Var norādīt nosacījumus, kas ignorē noklusējuma atbilstības loģiku. Ir pieejamas četras iespējas: 

|Iespēja  |Apraksts |Piemērs  |
|---------|---------|---------|
|Vienmēr atbilst     | Definē vērtības, kas vienmēr tiek saskaņotas.         |  Vienmēr atbilst *Maikam* un *Maikam.*       |
|Nekad neatbilst     | Definē vērtības, kas nekad nesakrīt.        | Nekad nesakrīti ar *Džonu* un *Džonatanu*.        |
|Pielāgota apeja     | Definē vērtības, kuras sistēmai vienmēr jāignorē atbilstības fāzē. |  Spēles laikā ignorēt vērtības *11111* un *Nezināms*.        |
|Aizstājvārda kartējums    | Vērtību definēšana, kas sistēmai būtu jāuzskata par vienu un to pašu vērtību.         | Uzskati *, ka Džo* ir līdzvērtīgs *Džozefam*.        |

1. Pārejiet uz **Dati** > **Unify** > **Saskaņot** un atlasiet **Pielāgota saskaņošana** sadaļā **Informācija par saskaņotajiem ierakstiem**.

   :::image type="content" source="media/custom-match-create.png" alt-text="Sadaļas Atbilstības kārtulas ekrānuzņēmums ar izceltu Pielāgotās saskaņošanas kārtulu.":::

1. **Rūtī Pielāgota** dodieties uz **cilni Ieraksti**.

1. Nolaižamajā izvēlnē Pielāgots tips **izvēlieties pielāgotās atbilstības opciju** un atlasiet **Lejupielādēt veidni**. Katrai atbilstības opcijai ir nepieciešama atsevišķa veidne.

1. Atveriet lejupielādēto veidnes failu un aizpildiet detalizētu informāciju. Veidnē ir ietverti lauki, kuros jānorāda entītija un entītijas primārās atslēgas vērtības, kas tiks izmantotas pielāgotajā atbilstībā. Piemēram, ja vēlaties, lai primārā atslēga *12345* no entītijas *Pārdošana* vienmēr atbilst primārajai atslēgai *34567* no entītijas *Kontaktinformācija*, aizpildiet veidni:
    - Entity1: Pārdošana
    - Entity1Key: 12345
    - Entity2: Kontaktpersona
    - Entity2Key: 34567

   Viens un tas pats veidnes fails var norādīt pielāgotās atbilstības ierakstus no vairākām entītijām.
   
   Ja vēlaties norādīt pielāgotu dedublikācijas atbilstību entītijai, norādiet to pašu entītiju kā Entity1 un Entity2 un iestatiet dažādas primārās atslēgas vērtības.

1. Pēc visu ignorēšanu pievienošanas saglabājiet veidnes failu.

1. Ejiet uz **Dati** > **Datu avoti** un uzņemiet veidnes failus kā jaunas entītijas.

1. Pēc failu un entītiju augšupielādes vēlreiz atlasiet opciju **Pielāgota atbilstība**. Tiks parādītas opcijas, lai norādītu entītijas, ko vēlaties iekļaut. Nolaižamajā izvēlnē atlasiet nepieciešamās entītijas un atlasiet **Gatavs**.

   :::image type="content" source="media/custom-match-overrides.png" alt-text="Dialoga ekrānuzņēmums, lai izvēlētos pielāgotas atbilstības scenārija pārlabošanu.":::

1. Pielāgotās atbilstības lietošana ir atkarīga no atbilstības opcijas, kuru vēlaties izmantot. 

   - Lai **vienmēr atbilstu** vai **Nekad nesakristu**, pārejiet pie nākamās darbības.
   - Pielāgota **apvedceļa** vai **aizstājvārda kartēšanai** atlasiet **Rediģēt** esošā atbilstības kārtulā vai izveidojiet jaunu kārtulu. Nolaižamajā izvēlnē Normalizācijas izvēlieties kartēšanas **opciju** Pielāgots apvedceļš **vai** Aizstājvārds un atlasiet **Gatavs**.

1. Lai piemērotu pielāgoto atbilstības konfigurāciju, lapā **Saskaņot** atlasiet **Saglabāt**.

1. Lai sāktu saskaņošanas procesu, lapā **Saskaņot** atlasiet **Izpildīt**. Pielāgotas atbilstības konfigurācija pārlabo citas norādītās atbilstības kārtulas.

#### <a name="known-issues"></a>Zināmās problēmas

- Paškonfekcija nerāda normalizētos datus dedupikācijas entītijās. Tomēr tas piemēro normalizāciju iekšēji dedupikācijas laikā. Tas ir pēc dizaina visām normalizācijām. 
- Ja semantiskā tipa iestatījums tiek noņemts kartēšanas **fāzē**, kad atbilstības kārtula izmanto aizstājvārda kartējumu vai pielāgoto apiešanu, normalizācija netiks lietota. Tas notiek tikai tad, ja pēc normalizācijas konfigurēšanas atbilstības kārtulā notīrāt semantisko tipu, jo semantisks tips nebūs zināms.


## <a name="next-step"></a>Nākamā darbība

Pēc vismaz viena atbilstības pāra atbilstības procesa pabeigšanas turpiniet sapludināšanas [**·**](merge-entities.md) darbību.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
