---
title: Klienta ilgtermiņa vērtības prognozēšana (CLV)
description: Prognozējiet potenciālos ieņēmumus aktīvajiem klientiem nākotnē.
ms.date: 09/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-predictions
- ci-create-prediction
- ci-custom-models
- customerInsights
ms.openlocfilehash: f27462ac327027e50e23387ac9f75a671db9a86d
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610383"
---
# <a name="predict-customer-lifetime-value-clv"></a>Klienta ilgtermiņa vērtības prognozēšana (CLV)

Prognozējiet potenciālo vērtību (ieņēmumus), ko jūsu uzņēmumam dos atsevišķi aktīvie klienti definētā nākotnes laika periodā. Šis prognoze jums palīdz:

- Identificējiet augstvērtīgus klientus un apstrādājiet šo ieskatu.
- Izveidojiet stratēģiskus klientu segmentus, pamatojoties uz to potenciālo vērtību, lai palaistu personalizētas kampaņas ar mērķtiecīgiem pārdošanas, mārketinga un atbalsta pasākumiem.
- Virziet produktu izstrādi, koncentrējoties uz funkcijām, kas palielina klientu vērtību.
- Optimizējiet pārdošanas vai mārketinga stratēģiju un precīzāk piešķiriet budžetu klientu informēšanai.
- Atpazīsti un atalgo augstus klientus, izmantojot lojalitātes vai atlīdzības programmas.

Nosakiet, ko CLV nozīmē jūsu uzņēmumam. Mēs atbalstām uz darījumiem balstītuS CLV prognoze. Klienta paredzamā vērtība ir balstīta uz biznesa darījumu vēsturi. Apsveriet iespēju izveidot vairākus modeļus ar dažādām ievades preferencēm un salīdzināt modeļa rezultātus, lai redzētu, kurš modeļa scenārijs vislabāk atbilst jūsu uzņēmuma vajadzībām.

> [!TIP]
> Izmēģiniet CLV prognoze, izmantojot parauga datus: [klienta mūža vērtība (CLV) prognoze parauga ceļvedi](sample-guide-predict-clv.md).

## <a name="prerequisites"></a>Priekšnoteikumi

- Vismaz [līdzstrādnieku](permissions.md) atļaujas
- Vismaz 100 unikāli klienti, vēlams vairāk nekā 10 000 klientu
- Klienta identifikators — unikāls identifikators, lai saskaņotu transakcijas ar atsevišķu klientu
- Vismaz viens gads darījumu vēsturē, vēlams divi līdz trīs gadi. Ideālā gadījumā vismaz divas līdz trīs transakcijas uz vienu klienta ID, vēlams vairākos datumos. Darījumu vēsturē jāiekļauj:
  - **Transakcijas ID**: Unikāls katras transakcijas identifikators
  - **Transakcijas datums**: katras transakcijas datums vai laika zīmogs
  - **Transakcijas summa**: katra transakcijas vērtība naudas izteiksmē (piemēram, ieņēmumi vai peļņas norma)
  - **Atgriešanai** piešķirtā etiķete: Būla patiesā/aplamā vērtība, kas norāda, vai transakcija ir atgriešanās
  - **Produkta ID**: darījumā iesaistītā produkta PRODUKTA ID
- Dati par klientu darbībām:
  - **Primārā atslēga**: unikāls identifikators darbībai
  - **Laikspiedols**: notikuma datums un laiks, ko identificē ar primāro atslēgu
  - **Notikums (aktivitātes nosaukums)**: notikuma nosaukums, kuru vēlaties izmantot
  - **Detalizēta informācija (summa vai vērtība)**: detalizēta informācija par klienta darbību
- Papildu dati, piemēram:
  - Aktivitātes tīmeklī: Tīmekļa vietnes apmeklējumu vēsture vai e-pasta vēsture
  - Lojalitātes aktivitātes: lojalitātes atlīdzības punktu uzkrāšanas un izpirkšanas vēsture
  - Klientu apkalpošana žurnāls: pakalpojuma zvans, sūdzība vai atgriešanas vēsture
  - Informācija par klienta profilu
- Mazāk nekā 20% trūkstošo vērtību obligātajos laukos

> [!NOTE]
> Var konfigurēt tikai vienu transakciju vēstures entītiju. Ja ir vairāki pirkšanas vai darījumu entītijas, apvienojiet tos Power Query pirms datu uzņemšanas.

## <a name="create-a-customer-lifetime-value-prediction"></a>Klienta ilgtermiņa vērtības (CLV) prognoze

Jebkurā laikā atlasiet **Saglabāt melnrakstu**, lai saglabātu prognoze kā melnrakstu. Melnraksts prognoze tiek parādīts **cilnē Manas prognozes**.

1. Dodieties uz **izlūkošanas** > **prognozēm**.

1. Cilnē Izveide elementā **Klienta mūža vērtība** atlasiet **Lietot modeli** **.**

1. Atlasiet **Sākt darbu**.

1. **Nosauciet šo modeli** un **Izvades entītijas nosaukumu**, lai nošķirtu tos no citiem modeļiem vai entītijām.

1. Atlasiet **Tālāk**.

### <a name="define-model-preferences"></a>Definējiet modeļa preferences

1. Iestatiet **Prognozes periodu**, lai definētu, cik tālu nākotnē vēlaties prognozēt CLV. Pēc noklusējuma mērvienība tiek iestatīta kā mēneši.

   > [!TIP]
   > Lai precīzi prognozētu CLV iestatītajam laika periodam, ir nepieciešams salīdzināms vēsturisko datu periods. Piemēram, ja vēlaties prognozēt CLV nākamajiem 12 mēnešiem, izmantojiet vismaz 18–24 mēnešu vēsturiskos datus.

1. Iestatiet laika periodu, kurā klientam ir jābūt vismaz vienai transakcijai, lai to uzskatītu par aktīvu. Modelis paredz tikai CLV **Active klientiem**.
   - **Ļaujiet modelim aprēķināt pirkšanas intervālu (ieteicams)**: modelis analizē jūsu datus un nosaka laika periodu, pamatojoties uz vēsturiskajiem pirkumiem.
   - **Iestatiet intervālu manuāli**: laika periods aktīva klienta definīcijai.

1. Definējiet augstvērtīga **klienta** procentili.
    - **Modeļa aprēķins (ieteicams)**: Modelis izmanto 80/20 kārtulu. To klientu procentuālais daudzums, kuri vēstures periodā jūsu uzņēmumam prognozēja 80% kumulatīvo ieņēmumu, tiek uzskatīti par augstas vērtības klientiem. Parasti mazāk nekā 30-40% klientu sekmē 80% kumulatīvos ieņēmumus. Tomēr šis skaitlis var atšķirties atkarībā no uzņēmuma un nozares.
    - **Procenti no labākajiem aktīvajiem klientiem**: Īpaša procentile augstvērtīgam klientam. Piemēram, ievadiet **25**, lai definētu augstvērtīgus klientus kā 25% no nākamajiem maksājošajiem klientiem.

    Ja jūsu uzņēmums citādi definē augstas vērtības klientus, [informējiet, jo mēs labprāt vēlētos zināt](https://go.microsoft.com/fwlink/?linkid=2074172).

1. Atlasiet **Tālāk**.

### <a name="add-required-data"></a>Pievienot nepieciešamos datus

1. Atlasiet **Pievienot datus** klientu darījumu **vēsturei**.

1. Atlasiet semantiskās darbības veidu **SalesOrder** vai **SalesOrderLine**, kas satur transakciju vēsturi. Ja darbība nav iestatīta, atlasiet **šeit** un izveidojiet to.

1. Sadaļā **Darbības**, ja aktivitātes izveides laikā aktivitātes atribūti tika semantiski kartēti izvēlieties konkrētus atribūtus vai entītiju, uz kuru vēlaties koncentrēties aprēķinam. Ja semantiskā kartēšana nenotika, atlasiet **Rediģēt** un kartējiet savus datus.
  
   :::image type="content" source="media/CLV-add-required.PNG" alt-text="Nepieciešamo datu pievienošana CLV modelim":::

1. Atlasiet **Tālāk** un pārskatiet šim modelim nepieciešamos atribūtus.

1. Atlasiet **Saglabāt**.

1. Pievienojiet papildu aktivitātes vai atlasiet **Tālāk**.

### <a name="add-optional-activity-data"></a>Neobligāto darbību datu pievienošana

Dati, kas atspoguļo galvenās klientu mijiedarbības (piemēram, tīmeklis, klientu apkalpošana un notikumu žurnāli), transakciju ierakstiem pievieno kontekstu. Vairāk struktūru, kas atrastas klientu darbības datos, var uzlabot prognožu precizitāti.

1. Atlasiet **Pievienot datus sadaļā** Boost model insights with additional activity data (Pielāgot modeļa **ieskatus ar papildu darbību datiem**).

1. Atlasiet darbības tipu, kas atbilst pievienojamās klienta darbības tipam. Ja darbība nav iestatīta, atlasiet **šeit** un izveidojiet to.

1. Sadaļā **Darbības**, ja aktivitātes atribūti tika kartēti, kad darbība tika izveidota, izvēlieties konkrētos atribūtus vai entītiju, uz kuru vēlaties koncentrēties aprēķinam. Ja kartēšana nenotika, atlasiet **Rediģēt** un kartēt savus datus.

1. Atlasiet **Tālāk** un pārskatiet šim modelim nepieciešamos atribūtus.

1. Atlasiet **Saglabāt**.

1. Atlasiet **Tālāk**.

1. [Pievienojiet neobligātos klientu datus](#add-optional-customer-data) vai atlasiet **Tālāk** un dodieties uz [Iestatīt atjaunināšanas grafiku](#set-update-schedule).

### <a name="add-optional-customer-data"></a>Neobligāto klientu datu pievienošana

Atlasiet kādu no 18 bieži izmantotajiem klienta profila atribūtiem, ko iekļaut kā ievadi modelī. Šie atribūti var nodrošināt personalizētākus, atbilstošākus un praktiskākus modeļa rezultātus jūsu uzņēmuma lietošanas gadījumos.

Piemēram: Contoso Coffee vēlas prognozēt klientu dzīves cikla vērtību, lai mērķētu uz augstvērtīgiem klientiem ar personalizētu piedāvājumu, kas saistīts ar viņu jaunā espresso automāta palaišanu. Contoso izmanto CLV modeli un pievieno visus 18 klientu profila atribūtus, lai redzētu, kuri faktori ietekmē viņu visaugstākās vērtības klientus. Viņi uzskata, ka klientu atrašanās vieta ir visietekmīgākais faktors šiem klientiem.
Izmantojot šo informāciju, viņi organizē vietējo pasākumu espresso automāta palaišanai un sadarbojas ar vietējiem pārdevējiem, lai iegūtu personalizētus piedāvājumus un īpašu pieredzi pasākumā. Bez šīs informācijas Contoso, iespējams, būtu nosūtījuši tikai vispārīgus mārketinga e-pastus un palaiduši garām iespēju personalizēt šo savu augstvērtīgo klientu vietējo segmentu.

1. Atlasiet **Pievienot datus** sadaļā **Boost modeļa ieskati vēl vairāk, izmantojot papildu klientu datus**.

1. Uzņēmumam **izvēlieties** Klients: CustomerInsights **, lai atlasītu vienoto klienta profilu, kas kartē klienta** atribūtu datus. Klienta **ID** izvēlieties **System.Customer.CustomerId**.

1. Kartējiet citus laukus, ja dati ir pieejami jūsu vienotajos klientu profilos.

   :::image type="content" source="media/clv-optional-customer-profile-mapping.png" alt-text="Klienta profila datu kartēto lauku piemērs.":::

1. Atlasiet **Saglabāt**.

1. Atlasiet **Tālāk**.

### <a name="set-update-schedule"></a>Iestatīt grafika atjaunināšanu

1. Izvēlieties frekvenci, lai pārkvalificētu savu modeli, pamatojoties uz jaunākajiem datiem. Šis iestatījums ir svarīgs, lai atjauninātu prognožu precizitāti, jo programmā Customer Insights tiek iekļauti jauni dati. Lielākā daļa uzņēmumu var pārkvalificēties reizi mēnesī un iegūt labu precizitāti to prognozēšanai.

1. Atlasiet **Tālāk**.

### <a name="review-and-run-the-model-configuration"></a>Modeļa konfigurācijas pārskatīšana un palaišana

Darbībā Pārskatīšana **un izpilde** tiek rādīts konfigurācijas kopsavilkums, un tā nodrošina iespēju veikt izmaiņas pirms prognoze izveides.

1. Atlasiet **Rediģēt**, veicot kādu no darbībām, lai pārskatītu un veiktu izmaiņas.

1. Ja esat apmierināts ar atlasi, atlasiet **Saglabāt un palaist**, lai sāktu modeļa darbību. Atlasiet **Gatavs**. Cilne **Manas prognozes** tiek rādīta, kamēr tiek veidota prognoze. Atkarībā no prognozēšanas laikā izmantojamā datu daudzuma process var aizņemt vairākas stundas.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-prediction-results"></a>Prognoze rezultātu skatīšana

1. Dodieties uz **izlūkošanas** > **prognozēm**.

1. **Cilnē Manas prognozes** atlasiet prognoze, kuru vēlaties skatīt.

Rezutātu lapā ir trīs primārās datu sadaļas.

- **Apmācības modeļa veiktspēja**: A, B vai C pakāpe norāda prognoze veiktspēju un var palīdzēt pieņemt lēmumu izmantot izvades entītijā saglabātos rezultātus.
  
  :::image type="content" source="media/clv-model-score.png" alt-text="Modeļa rezultātu informācijas lodziņa attēls ar atzīmi A.":::

  Customer Insights novērtē, kā AI modelis darbojās, prognozējot augstvērtīgus klientus salīdzinājumā ar bāzlīnijas modeli.

  Kategorijas tiek noteiktas, pamatojoties uz šādām kārtulām:
  - **A**, kad modelis precīzi prognozēja vismaz par 5% vairāk augstas vērtības klientu salīdzinājumā ar bāzlīnijas modeli.
  - **B** kad modelis precīzi prognozēja vismaz 0-5% vairāk augstas vērtības klientu salīdzinājumā ar bāzlīnijas modeli.
  - **C** kad modelis precīzi prognozēja vismaz vairāk augstas vērtības klientu salīdzinājumā ar bāzlīnijas modeli.
  
  Atlasiet [**Uzzināt par šo rezultātu**](#learn-about-the-score), lai atvērtu **modeļa vērtēšanas** rūti, kurā tiek rādīta papildinformācija par AI modeļa veiktspēju un bāzlīnijas modeli. Tas palīdzēs jums labāk izprast pamatā esošos modeļa veiktspējas rādītājus un to, kā tika iegūta galīgā modeļa veiktspējas pakāpe. Bāzlīnijas modelis izmanto pieeju, kuras pamatā nav mākslīgais intelekts, lai aprēķinātu klientu veiktās sākotnējās vērtības, primāri pamatojoties uz klientu veiktajiem iepriekšējiem pirkumiem.

- **Klientu vērtība pēc procentiles**: diagrammā tiek parādīti mazvērtīgi un augstvērtīgi klienti. Virziet kursoru virs histogrammas joslām, lai redzētu katras grupas klientu skaitu un šīs grupas vidējo CLV. Pēc izvēles izveidojiet klientu [segmentus,](prediction-based-segment.md) pamatojoties uz viņu CLV prognozēm.
  
   :::image type="content" source="media/CLV-value-percent.png" alt-text="Klientu vērtība pēc procentiles CLV modelim":::

- **Vairums ietekmējošo faktoru**: veidojot savu CLV prognozi, tiek izskatīti dažādi faktori, pamatojoties uz mākslīgā intelekta modelim nodrošinātajiem ievades datiem. Katram no šiem faktoriem ir aprēķinātā nozīme modeļa izveidotajām apkopotajām prognozēm. Izmantojiet šos faktorus, lai palīdzētu apstiprināt prognoze rezultātus. Šie faktori sniedz arī plašāku ieskatu par visietekmējošākajiem faktoriem, kas veicina CLV prognozēšanu visos klientos.
  
   :::image type="content" source="media/CLV-influence-factors.png" alt-text="Visietekmīgākie faktori CLV modelim":::

### <a name="learn-about-the-score"></a>Uzziniet par rezultātu

Standarta formula, ko izmanto CLV aprēķinam pēc bāzlīnijas modeļa:

 _**CLV katram klientam** = Klienta vidējais mēneša pirkums aktīvajā klientu logā * Mēnešu skaits CLV prognoze periodā * Visu klientu kopējais saglabāšanas līmenis_

Mākslīgā intelekta modelis tiek salīdzināts ar bāzlīnijas modeli, pamatojoties uz diviem modeļa veiktspējas rādītājiem.
  
- **Augstas vērtības klientu sekmīgas prognozēšanas rādītājs**

  Skatiet atšķirību, prognozējot augstas vērtības klientus, kuri izmanto mākslīgā intelekta modeli, salīdzinot ar bāzlīnijas modeli. Piemēram, 84% panākumu līmenis nozīmē, ka no visiem vērtīgiem klientiem mācību datos mākslīgā intelekta modelis spēja precīzi tvert 84%. Pēc tam šos sekmīgos panākumus mēs salīdzinām ar bāzlīnijas modeļa sekmīgo likmi, lai ziņotu par relatīvajām izmaiņām. Šī vērtība tiek izmantota, lai modelim piešķirtu kategoriju.

- **Kļūdu metrikas**

  Skatiet modeļa vispārējo veiktspēju kļūdu ziņā, prognozējot nākotnes vērtības. Lai novērtētu šo kļūdu, mēs izmantojam kopējo saknes vidējā kvadrāta kļūdas (RMSE) metriku. RMSE ir standarta veids, kā mērīt modeļa kļūdu, prognozējot kvantitatīvus datus. Mākslīgā intelekta modeļa RMSE vērtību salīdzina ar bāzlīnjas modeļa RMSE, un tiek ziņots par relatīvo starpību.

Mākslīgā intelekta modelis nosaka precīzu klientu rangu pēc vērtības, ko tie sniedz jūsu uzņēmumam. Tātad tikai labākās vērtības klientu prognozēšanas sekmīgais rādītājs tiek izmantots, lai atvasinātu galīgo modeļa kategoriju. RMSE dati ir jutīgi pret novirzēm. Scenārijos, kuros ir mazs procentuālais klientu skaits ar pārāk lielām iegādes vērtībām, kopējā RMSE metrika var nedot pilnīgu priekšstatu par modeļa veiktspēju.

[!INCLUDE [footer-include](includes/footer-banner.md)]
