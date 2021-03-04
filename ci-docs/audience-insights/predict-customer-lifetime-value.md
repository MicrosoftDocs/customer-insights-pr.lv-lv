---
title: Klienta ilgtermiņa vērtības (CLV) prognoze
description: Prognozējiet potenciālos ieņēmumus aktīvajiem klientiem nākotnē.
ms.date: 02/05/2021
ms.reviewer: wameng
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 363a46c81b5bb737d274998f9a699dc662e38d7c
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268603"
---
# <a name="customer-lifetime-value-clv-prediction-preview"></a>Klienta ilgtermiņa vērtības (CLV) prognoze (priekšskatījums)

Prognozējiet potenciālo vērtību (ieņēmumus), ko jūsu uzņēmumam dos atsevišķi aktīvie klienti definētā nākotnes laika periodā. Šis līdzeklis var palīdzēt sasniegt dažādus mērķus: 
- Noteikt ļoti vērtīgus klientus un apstrādāt šo ieskatu
- Veidojiet stratēģiskus klientu segmentus, balstoties uz to iespējamo vērtību, lai izpildītu personalizētas kampaņas, ar mērķtiecīgiem pārdošanas, mārketinga un atbalsta pasākumiem
- Produktu izstrādes rokasgrāmata, koncentrējoties uz līdzekļiem, kas palielina klienta vērtību
- Optimizējiet pārdošanas vai mārketinga stratēģiju un precīzāk novirziet budžetu klientam
- Atpazīt un apbalvot ļoti vērtīgus klientus, izmantojot apbalvojumu programmas 

## <a name="prerequisites"></a>Priekšnosacījumi

Pirms darba sākšanas atainojiet, ko CLV nozīmē jūsu uzņēmumam. Pašlaik mēs atbalstītu uz transakcijām balstītu CLV prognoze. Klienta prognozētā vērtība ir balstīta uz biznesa transakciju vēsturi. Lai izveidotu prognoze, ir nepieciešamas vismaz [Līdzdalībnieku](permissions.md) atļaujas.

Tā kā CLV modeļa konfigurēšanai un izmantošanai nevajag daudz laika, apsveriet iespēju izveidot vairākus modeļus ar dažādām ievades preferencēm un salīdziniet modeļa rezultātus, lai uzzinātu, kurš modeļa scenārijs vislabāk atbilst jūsu uzņēmuma vajadzībām.

###  <a name="data-requirements"></a>Datu prasības

Ir nepieciešami šādi dati, un, ja tie ir atzīmēti kā neobligāti, ieteicami modeļa veiktspējas palielināšanai. Jo vairāk datu modelis var apstrādāt, jo precīzāka būs prognoze. Tādēļ iesakām ievadīt vairāk klientu darbību datu, ja iespējams.

- Klienta identifikators: unikālais identifikators, kas savieno konkrētu klientu ar transakcijām

- Transakciju vēsture: vēsturisko transakciju žurnāls ar zemāk norādītu semantisko datu shēmu
    - Transakcijas ID: Unikāls katras transakcijas identifikators
    - Transakcijas datums: datums, vēlams, laikspiedols katrai transakcijai
    - Transakcijas summa: katra transakcijas vērtība naudas izteiksmē (piemēram, ieņēmumi vai peļņas norma)
    - Atgriešanai piešķirtā etiķete (neobligāti): Būla vērtība, kas norāda, vai transakcija ir atgriešana 
    - Produkta ID (neobligāti): transakcijā iesaistītā produkta ID

- Papildu dati (neobligāti), piemēram
    - Tīmekļa darbības: vietnes apmeklējuma vēsture, e-pasta vēsture
    - Lojalitātes darbības: lojalitātes programmas punktu uzkrāšanas un izmantošanas vēsture
    - Klientu apkalpošana žurnāls, servisa izsaukumi vai atgriešanas vēsture
- (Neobligāti) Dati par klientu darbībām:
    - Darbības identifikatori, lai nodalītu tāda paša tipa darbības
    - Klientu identifikatori darbību kartēšanai jūsu klientiem
    - Darbības informācija, kas ietver darbības nosaukumu un datumu
    - Darbību semantiskās datu shēmas ietver: 
        - Primārā atslēga: unikāls darbības identifikators
        - Laikspiedols: notikuma datums un laiks, ko identificē primārā atslēga
        - Notikums (darbības nosaukums): norādiet izmantojamā notikuma nosaukumu
        - Detalizēta informācija (summa vai vērtība): detalizēta informācija par klienta darbību

## <a name="create-a-customer-lifetime-value-prediction"></a>Klienta ilgtermiņa vērtības (CLV) prognoze

1. Sadaļā Auditorijas ieskati ejiet uz **Informācija** > **Prognozes**.

1. Atlasiet elementu **Klienta ilgtermiņa** vērtība un atlasiet vienumu **Lietot modeli**. 

1. Rūtī **Klienta ilgtermiņa vērtība** (priekšskatījums) atlasiet **Sākt darbu**.

1. **Nosauciet šo modeli** un **Izvades entītijas nosaukumu**, lai nošķirtu tos no citiem modeļiem vai entītijām.

1. Atlasiet **Tālāk**.

### <a name="define-model-preferences"></a>Definējiet modeļa preferences

1. Iestatiet **Prognozes periodu**, lai definētu, cik tālu nākotnē vēlaties prognozēt CLV.    
   Pēc noklusējuma mērvienība tiek iestatīta kā mēneši. To var mainīt uz gadiem, lai turpmāk meklētu plašāku informāciju.

   > [!TIP]
   > Lai precīzi prognozētu CLV jūsu iestatītajā laika periodā, ir nepieciešams salīdzināms vēsturisko datu periods. Piemēram, ja vēlaties paredzēt nākamos 12 mēnešus, ieteicams izmantot vēsturiskos datus vismaz 18–24 mēnešu laikā.

1. Norādiet, ko **Aktīvie klienti** nozīmē jūsu uzņēmumam. Iestatiet laika periodu, kurā klientam ir jābūt vismaz vienai transakcijai, lai to uzskatītu par aktīvu. Modelis prognozēs CLV tikai aktīvajiem klientiem. 
   - **Ļaujiet modelim aprēķināt iegādes intervālu (ieteicams)**: modelis analizē datus un nosaka laika periodu, pamatojoties uz vēsturiskiem pirkumiem.
   - **Iestatiet intervālu manuāli**: ja jums ir noteikta aktīva klienta biznesa definīcija, izvēlieties šo opciju un atbilstoši iestatiet laika periodu.

1. Definējiet **Augstas vērtības klienta** procentili, lai modelis varētu sniegt jūsu uzņēmuma definīcijai piemērotus rezultātus.
    - **Modeļa aprēķins (ieteicams)**: modelis analizē datus un nosaka, kāda varētu būt jūsu uzņēmuma augsta vērtība, pamatojoties uz klientu transakciju vēsturi. Modelis izmanto heiristisku kārtulu (pamatā ir 80/20 kārtula vai pareto principu), lai atrastu vērtīgāku klientu statistiku. To klientu procentuālais daudzums, kuri vēstures periodā jūsu uzņēmumam prognozēja 80% kumulatīvo ieņēmumu, tiek uzskatīti par augstas vērtības klientiem. Parasti mazāk nekā 30-40% klientu sekmē 80% kumulatīvos ieņēmumus. Tomēr šis skaitlis var atšķirties atkarībā no uzņēmuma un nozares.    
    - **Procenti no populārākajiem aktīvajiem klientiem**: definējiet vērtīgiem klientiem jūsu uzņēmumam kā populārāko aktīvo klientu procentile. Piemēram, šo opciju var izmantot, lai definētu augstas vērtības klientus kā populārākos 20% no nākamajiem klientiem.

    Ja jūsu uzņēmums citādi definē augstas vērtības klientus, [informējiet, jo mēs labprāt vēlētos zināt](https://go.microsoft.com/fwlink/?linkid=2074172).

1. Atlasiet **Tālāk**, lai pārietu uz nākamo darbību.

### <a name="add-required-data"></a>Pievienot nepieciešamos datus

1. Darbībā **Nepieciešamie dati** atlasiet opciju **Pievienot datus** **Klientu transakciju vēsturei** un izvēlieties entītiju, kas nodrošina transakciju vēstures informāciju, kā aprakstīts [priekšnosacījumos](#prerequisites).

1. Kartējiet semantiskos laukus uz atribūtiem jūsu pirkumu vēstures entītijā un atlasiet **Tālāk**.

   :::image type="content" source="media/clv-add-customer-data-mapping.png" alt-text="Konfigurācijas darbības attēls, lai kartētu nepieciešamo datu datu atribūtus.":::
 
1. Ja tālāk norādītie lauki nav aizpildīti, konfigurējiet savas pirkumu vēstures entītijas relācijas ar *Klienta* entītiju un atlasiet **Saglabāt**.
    1. Atlasiet transakciju vēstures entītiju.
    1. Atlasiet lauku, kas identificē klientu pirkumu vēstures entītijā. Tam ir jāattiecas uz jūsu Klienta entītijas primāro klienta ID.
    1. Atlasiet entītiju, kas atbilst primārā klienta entītijai.
    1. Ievadiet nosaukumu, kas apraksta attiecību.

      :::image type="content" source="media/clv-add-customer-data-relationship.png" alt-text="Konfigurācijas soļa attēls, lai definētu attiecības ar klienta entītiju.":::

1. Atlasiet **Tālāk**.

### <a name="add-optional-data"></a>Pievienot papildu datus

Dati, kas atspoguļo galvenās klientu mijiedarbības (piemēram, tīmeklis, klientu apkalpošana un notikumu žurnāli), transakciju ierakstiem pievieno kontekstu. Vairāk struktūru, kas atrastas klientu darbības datos, var uzlabot prognožu precizitāti. 

1. Darbībā **Papildu dati (neobligāti)** atlasiet vienumu **Pievienot datus**. Izvēlieties klienta darbību entītiju, kas sniedz informāciju par klientu darbībām, kā aprakstīts [priekšnosacījumos](#prerequisites).

1. Kartējiet semantiskos laukus uz atribūtiem jūsu klientu darbības entītijā un atlasiet **Tālāk**.

   :::image type="content" source="media/clv-additional-data-mapping.png" alt-text="Konfigurācijas darbības attēls, lai kartētu papildu datu laukus.":::

1. Atlasiet darbības tipu, kas atbilst pievienojamās klienta darbības tipam. Izvēlieties no esošajiem darbību tipiem vai pievienojiet jaunu darbības tipu.

1. Konfigurējiet klienta darbības entītijas attiecības ar *Klienta* entītiju.
    
    1. Atlasiet vienumu Lauks, kas ir identificējis klientu pirkumu vēstures tabulā. To var tieši saistīt ar *Klienta* entītijas primāro klienta ID.
    1. Atlasiet *Klienta* entītiju, kas atbilst primārajai *Klienta* entītijai.
    1. Ievadiet nosaukumu, kas apraksta attiecību.

   :::image type="content" source="media/clv-additional-data.png" alt-text="Konfigurācijas plūsmas soļa attēls, lai pievienotu papildu datus un konfigurētu darbību ar aizpildītiem piemēriem.":::

1. Atlasiet vienumu **Saglabāt**.    
    Pievienojiet papildu datus, ja vēlaties iekļaut citas klientu darbības.

1. Atlasiet **Tālāk**.

### <a name="set-update-schedule"></a>Iestatīt grafika atjaunināšanu

1. **Datu atjaunināšanas grafika** darbībā izvēlieties, cik bieži modelis atkārtoti jāplāno, pamatojoties uz jaunākajiem datiem. Šis iestatījums ir svarīgs, lai atjauninātu tādu prognožu precizitāti kā jauni dati, kas tiek uzņemti auditorijas ieskatos. Lielākā daļa uzņēmumu var pārkvalificēties reizi mēnesī un iegūt labu precizitāti to prognozēšanai.

1. Atlasiet **Tālāk**.


### <a name="review-and-run-the-model-configuration"></a>Modeļa konfigurācijas pārskatīšana un palaišana

1. Darbībā **Modeļa detalizētās informācijas pārskatīšana** validējiet konfigurācijas prognozi. Jūs varat atgriezties jebkurā prognozēšanas konfigurācijas daļā, zemāk parādītajā vērtībā atlasot **Rediģēt**. No norises indikatora var atlasīt arī konfigurācijas soli.

1. Ja visas vērtības ir pareizi konfigurētas, atlasiet **Saglabāt un palaist**, lai palaisu modeli. Cilnē **Manas prognozes** varat redzēt šī procesa prognozes statusu. Atkarībā no prognozēšanas laikā izmantojamā datu daudzuma process var aizņemt vairākas stundas.

## <a name="review-prediction-status-and-results"></a>Prognozes statusa un rezultātu pārskatīšana

### <a name="review-prediction-status"></a>Prognozes statusa pārskatīšana

1.  Atveriet  **Informācija** > **Prognozes** un atlasiet cilni **Manas prognozes**.
2.  Atlasiet prognozes, kuras vēlaties pārskatīt.

- **Prognoze nosaukums**: izveides brīdī paredzētās prognozes nosaukums.
- **Prognoze tips**: prognozei izmantotā modeļa tips
- **Izvades entītija**: entītijas nosaukums, kurā saglabāt prognozes izvadi. Dodieties uz **Dati** > **Entītijas**, lai atrastu entītiju ar šo nosaukumu.
- **Prognozētais lauks**: šis lauks tiek aizpildīts tikai dažu veidu prognozēm, un tos neizmanto klienta ilgtermiņa vērtības prognozē.
- **Statuss**: Prognozes izpildes statuss.
    - **Ierindots**: prognoze gaida citu procesu izpildi.
    - **Atsvaidzināšana**: prognoze pašlaik darbojas, lai iegūtu rezultātus, kas ieplūst izvades entītijā.
    - **Neizdevās**: neizdevās palaist prognozi. Lai iegūtu detalizētu informāciju, [skatiet žurnālfailus](#troubleshoot-a-failed-prediction).
    - **Veiksmīgi**: prognoze ir veiksmīga. Atlasiet **Skats** vertikālās daudzpunktes sadaļā, lai pārskatītu prognozes rezultātus.
- **Rediģēts**: datums, kad tika mainīta prognozes konfigurācija.
- **Pēdējā atsvaidzināšana**: datums, kad prognozes atsvaidzinātais rezultāts ir redzams izvades entītijā.


### <a name="review-prediction-results"></a>Prognozes rezultātu pārskatīšana

1. Atveriet  **Informācija** > **Prognozes** un atlasiet cilni **Manas prognozes**.

1. Atlasiet prognozi, kuras rezultātus vēlaties pārskatīt.

Rezutātu lapā ir trīs primārās datu sadaļas.

- **Apmācības modeļa veiktspēja**: iespējamās kategorijas ir A, B vai C. Šī kategorija norāda prognozes veiktspēju un var palīdzēt pieņemt lēmumu izmantot izvades entītijā saglabātos rezultātus. Atlasiet **Uzzināt par šo rezultātu**, lai labāk izprastu pamatā esošā modeļa veiktspējas metriku un to, kā ir atvasināta galīgā modeļa veiktspējas kategorija.
  
  :::image type="content" source="media/clv-model-score.png" alt-text="Modeļa rezultātu informācijas lodziņa attēls ar atzīmi A.":::

  Konfigurējot prognozi, izmantojot augstas vērtības klientu definīciju, sistēma novērtē, kā AI modelis tiek izpildīts, prognozējot augstas vērtības klientus salīdzinājumā ar bāzlīnijas modeli.    

  Kategorijas tiek noteiktas, pamatojoties uz šādām kārtulām:
  - A kad modelis precīzi prognozēja vismaz par 5% vairāk augstas vērtības klientu salīdzinājumā ar bāzlīnijas modeli.
  - B kad modelis precīzi prognozēja vismaz 0-5% vairāk augstas vērtības klientu salīdzinājumā ar bāzlīnijas modeli.
  - C kad modelis precīzi prognozēja vismaz vairāk augstas vērtības klientu salīdzinājumā ar bāzlīnijas modeli.

  Rūtī **Modeļa novērtējums** ir redzama papildinformācija par mākslīgā intelekta modeļa veiktspēju un bāzlīnijas modeli. Bāzlīnijas modelis izmanto pieeju, kuras pamatā nav mākslīgais intelekts, lai aprēķinātu klientu veiktās sākotnējās vērtības, primāri pamatojoties uz klientu veiktajiem iepriekšējiem pirkumiem.     
  Standarta formula, ko izmanto CLV aprēķinam pēc bāzlīnijas modeļa:    

  *CLV katram klientam = klienta veiktais vidējais mēneša pirkums aktīvā klienta logā * Mēnešu skaits CLV prognoze periodā * Kopējais saglabāšanas līmenis visiem klientiem*

  Mākslīgā intelekta modelis tiek salīdzināts ar bāzlīnijas modeli, pamatojoties uz diviem modeļa veiktspējas rādītājiem.
  
  - **Augstas vērtības klientu sekmīgas prognozēšanas rādītājs**

  Skatiet atšķirību, prognozējot augstas vērtības klientus, kuri izmanto mākslīgā intelekta modeli, salīdzinot ar bāzlīnijas modeli. Piemēram, 84% panākumu līmenis nozīmē, ka no visiem vērtīgiem klientiem mācību datos mākslīgā intelekta modelis spēja precīzi tvert 84%. Pēc tam šos sekmīgos panākumus mēs salīdzinām ar bāzlīnijas modeļa sekmīgo likmi, lai ziņotu par relatīvajām izmaiņām. Šī vērtība tiek izmantota, lai modelim piešķirtu kategoriju.

  - **Kļūdu metrikas**
    
  Cita metrika ļauj pārskatīt modeļa vispārējo veiktspēju attiecībā uz kļūdu nākotnes vērtību prognozēšanas ziņā. Lai novērtētu šo kļūdu, mēs izmantojam kopējo saknes vidējā kvadrāta kļūdas (RMSE) metriku. RMSE ir standarta veids, kā mērīt modeļa kļūdu, prognozējot kvantitatīvus datus. Mākslīgā intelekta modeļa RMSE vērtību salīdzina ar bāzlīnjas modeļa RMSE, un tiek ziņots par relatīvo starpību.

  Mākslīgā intelekta modelis nosaka precīzu klientu rangu pēc vērtības, ko tie sniedz jūsu uzņēmumam. Tātad tikai labākās vērtības klientu prognozēšanas sekmīgais rādītājs tiek izmantots, lai atvasinātu galīgo modeļa kategoriju. RMSE dati ir jutīgi pret novirzēm. Scenārijos, kuros ir mazs procentuālais klientu skaits ar pārāk lielām iegādes vērtībām, kopējā RMSE metrika var nedot pilnīgu priekšstatu par modeļa veiktspēju.   

- **Klientu vērtība pēc percentiles**: izmantojot vērtīgu klientu definīciju, klienti tiek grupēti zemās un augstās vērtībās, pamatojoties uz viņu CLV prognozēm, un atainoti diagrammā. Kursējot pa histogrammas joslām, var redzēt klientu skaitu katrā grupā un šīs grupas vidējo CLV. Šie dati var palīdzēt, ja vēlaties [izveidot klientu segmentus](segments.md), pamatojoties uz viņu CLV prognozi.

- **Vairums ietekmējošo faktoru**: veidojot savu CLV prognozi, tiek izskatīti dažādi faktori, pamatojoties uz mākslīgā intelekta modelim nodrošinātajiem ievades datiem. Katram no šiem faktoriem ir aprēķinātā nozīme modeļa izveidotajām apkopotajām prognozēm. Šos faktorus var izmantot, lai atvieglotu jūsu prognozes rezultātu validēšanu. Šie faktori sniedz arī plašāku ieskatu par visietekmējošākajiem faktoriem, kas veicina CLV prognozēšanu visos klientos.

## <a name="refresh-a-prediction"></a>Atsvaidzināt prognozi

Prognozes automātiski tiek atsvaidzinātas pēc tā paša [grafika, kad dati tiek atsvaidzināti](system.md#schedule-tab), kā tas ir konfigurēts iestatījumos. Tos var atsvaidzināt arī manuāli.

1. Atveriet  **Informācija** > **Prognozes** un atlasiet cilni **Manas prognozes**.
2. Atlasiet vertikālās elipses, kas atrodas blakus prognozei, kuru vēlaties atsvaidzināt.
3. Atlasiet **Atsvaidzināt**.

## <a name="delete-a-prediction"></a>Dzēst prognozi

Dzēšot prognozi, tiek noņemta arī tās izvades entītija.

1. Atveriet  **Informācija** > **Prognozes** un atlasiet cilni **Manas prognozes**.
2. Atlasiet vertikālās elipses, kas atrodas blakus prognozei, kuru vēlaties dzēst.
3. Atlasiet **Dzēst**.

## <a name="troubleshoot-a-failed-prediction"></a>Neizdevušās prognozes problēmas novēršana

1. Atveriet  **Informācija** > **Prognozes** un atlasiet cilni **Manas prognozes**.
2. Atlasiet vertikālās elipses, kas atrodas blakus prognozei, kurai vēlaties skatīt kļūdu žurnālus.
3. Atlasiet **Žurnāli**.
4. Pārskatīt visas kļūdas. Pastāv vairāki kļūdu tipi, kas var rasties, un tie apraksta to, kas izraisīja kļūdu. Piemēram, kļūda, ka nav pietiekami daudz datu, lai precīzi prognozētu, parasti tiek atrisināta, ielādējot papildu datus.


[!INCLUDE[footer-include](../includes/footer-banner.md)]