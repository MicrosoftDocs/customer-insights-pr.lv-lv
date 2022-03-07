---
title: Transakcijas čup prognoze (satur video)
description: Prognozējiet, vai pastāv risks, ka klients vairs neiegādāsies jūsu uzņēmuma produktus vai pakalpojumus.
ms.date: 01/13/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 9aa208ad94dcb6b1e0f110a3f974c56de00bbd07
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 02/25/2022
ms.locfileid: "8355668"
---
# <a name="transaction-churn-prediction"></a>Transakciju zuduma prognoze

Transakciju zudumu prognoze palīdz paredzēt, vai klients vairs nepirks jūsu produktus vai pakalpojumus noteiktā laika logā. Jūs varat izveidot jaunas zudumu prognozes **Informācijā** > **Prognozēs**. Atlasiet **Manas prognozes**, lai skatītu citas jūsu izveidotās prognozes. 

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6Eg]

Attiecībā uz vidēm, kuru pamatā ir uzņēmuma konti, mēs varam paredzēt uzņēmuma transakciju procesu, kā arī uzņēmuma un cita līmeņa informācijas kombināciju, piemēram, produktu kategoriju. Pievienojot dimensiju, varat uzzināt, kāda ir iespēja, ka uzņēmums "Contoso" pārtrauks produktu kategorijas "biroja iekārtas" iegādi. Turklāt attiecībā uz uzņēmuma kontiem mēs varam izmantot arī AI, lai ģenerētu iespējamo iemeslu sarakstu, kāpēc uzņēmums, visticamāk, būs sekundāra līmeņa informācijas kategorijai.

> [!TIP]
> Izmēģiniet apmācību par darījumu churn prognoze, izmantojot parauga datus: [Transaction churn prognoze parauga rokasgrāmatu](sample-guide-predict-transactional-churn.md).

## <a name="prerequisites"></a>Priekšnoteikumi

# <a name="individual-consumers-b-to-c"></a>[Atsevišķi patērētāji (B2C)](#tab/b2c)

- Vismaz [Līdzautora atļaujas](permissions.md) Customer Insights.
- Biznesa zināšanas, lai saprastu, ko zudums nozīmē jūsu uzņēmumam. Mēs atbalstām uz laiku balstītu zudumu definīcijas, kas nozīmē, ka klients ir uzskatāms par zudušu pēc perioda bez pirkumiem.
- Dati par jūsu transakcijām/pirkumiem un to vēsturi:
    - Transakciju identifikatori, lai atšķirtu pirkumus/transakcijas.
    - Klientu identifikatori, lai saskaņotu transakcijas ar klientiem.
    - Darbības notikuma datumi, kuros definēti transakcijas datumi.
    - Attiecībā uz pirkumu/transakciju semantisko datu shēmu ir nepieciešama šāda informācija:
        - **Transakcijas ID**: Unikāls pirkšanas vai transakcijas identifikators.
        - **Transakcijas datums**: Pirkšanas vai transakcijas datums.
        - **Transakcijas vērtība**: Transakcijas/krājuma valūtas/skaitliskās vērtības summa.
        - (Neobligāti) **Unikāls produkta ID**: Produkta vai servisa ID, kas iegādāts, ja dati ir rindas elementu līmenī.
        - (Neobligāti) **Vai šī transakcija ir atgriezta**: Patiess/aplams lauks, kas norāda, vai transakcija ir atgriezta vai ne. Ja **Transakcijas vērtība** ir negatīva, mēs arī izmantosim šo informāciju, lai secinātu par peļņu.
- (Neobligāti) Dati par klientu darbībām:
    - Darbības identifikatori, lai nodalītu tāda paša tipa darbības.
    - Klientu identifikatori darbību kartēšanai jūsu klientiem.
    - Darbības informācija, kas ietver darbības nosaukumu un datumu.
    - Klienta darbību semantisko datu shēma ietver:
        - **Primārā atslēga:** unikāls darbības identifikators. Piemēram, vietnes apmeklējums vai lietojuma ieraksts, kas norāda, ka klients ir izmēģinājis jūsu produkta paraugu.
        - **Laikspiedols:** notikuma datums un laiks, ko identificē primārā atslēga.
        - **Notikums:** Norādiet notikuma nosaukumu, kuru vēlaties izmantot. Piemēram, lauks "UserAction" pārtikas preču veikalā varētu būt klientam piemērots kupona lietojums.
        - **Detalizēti:** Detalizēta informācija par notikumu. Piemēram, preču veikala lauks ar nosaukumu "CouponValue" var būt kupona valūtas vērtība.

# <a name="business-accounts-b-to-b"></a>[Uzņēmumu konti (B2B)](#tab/b2b)

- Vismaz [Līdzautora atļaujas](permissions.md) Customer Insights.
- Biznesa zināšanas, lai saprastu, ko zudums nozīmē jūsu uzņēmumam. Mēs atbalstām uz laiku balstītu zudumu definīcijas, kas nozīmē, ka klients ir uzskatāms par zudušu pēc perioda bez pirkumiem.
- Dati par jūsu transakcijām/pirkumiem un to vēsturi:
    - Transakciju identifikatori, lai atšķirtu pirkumus/transakcijas.
    - Klientu identifikatori, lai saskaņotu transakcijas ar klientiem.
    - Darbības notikuma datumi, kuros definēti transakcijas datumi.
    - Attiecībā uz pirkumu/transakciju semantisko datu shēmu ir nepieciešama šāda informācija:
        - **Transakcijas ID**: Unikāls pirkšanas vai transakcijas identifikators.
        - **Transakcijas datums**: Pirkšanas vai transakcijas datums.
        - **Transakcijas vērtība**: Transakcijas/krājuma valūtas/skaitliskās vērtības summa.
        - (Neobligāti) **Unikāls produkta ID**: Produkta vai servisa ID, kas iegādāts, ja dati ir rindas elementu līmenī.
        - (Neobligāti) **Vai šī transakcija ir atgriezta**: Patiess/aplams lauks, kas norāda, vai transakcija ir atgriezta vai ne. Ja **Transakcijas vērtība** ir negatīva, mēs arī izmantosim šo informāciju, lai secinātu par peļņu.
- (Neobligāti) Dati par klientu darbībām:
    - Darbības identifikatori, lai nodalītu tāda paša tipa darbības.
    - Klientu identifikatori darbību kartēšanai jūsu klientiem.
    - Darbības informācija, kas ietver darbības nosaukumu un datumu.
    - Klienta darbību semantisko datu shēma ietver:
        - **Primārā atslēga:** unikāls darbības identifikators. Piemēram, vietnes apmeklējums vai lietojuma ieraksts, kas norāda, ka klients ir izmēģinājis jūsu produkta paraugu.
        - **Laikspiedols:** notikuma datums un laiks, ko identificē primārā atslēga.
        - **Notikums:** Norādiet notikuma nosaukumu, kuru vēlaties izmantot. Piemēram, lauks "UserAction" pārtikas preču veikalā varētu būt klientam piemērots kupona lietojums.
        - **Detalizēti:** Detalizēta informācija par notikumu. Piemēram, preču veikala lauks ar nosaukumu "CouponValue" var būt kupona valūtas vērtība.
- (Nav obligāti) Dati par klientiem:
    - Šie dati ir jākārto ar daudz statiskākiem atribūtiem, lai nodrošinātu modeļa labāko veiktspēju.
    - Klientu datu semantikas datu shēma ietver:
        - **CustomerID:** Unikāls klienta indentifikators.
        - **Izveides datums**: klienta sākotnējās pievienošanas datums.
        - **Rajons vai apgabals:** rajona vai apgabala atrašanās vieta.
        - **Valsts:** klienta valsts.
        - **Nozare:** klienta nozares tips. Piemēram, lauks ar nosaukumu "Nozare" kafijas grauzdēšanā var norādīt, vai klients ir mazumtirdzniecībā.
        - **Klasifikācija:** klienta kategorizēšana jūsu uzņēmumam. Piemēram, lauks ar nosaukumu "ValueSegment" kafijas grauzdēšanā var būt klientu līmenis, uz kura balstās klientu lielums.

---

- Ieteicamie datu raksturlielumi:
    - Pietiekami vēsturiskie dati: Transakcijas dati par laiku, kas vismaz divreiz pārsniedz atlasīto laika logu. 2-3 gadus ilga transakciju vēsture. 
    - Vairāki pirkumi katram klientam: Vēlams, vismaz divas transakcijas uz katru klientu.
    - Klientu skaits: Vismaz 10 klientu profilu, vēlams vairāk nekā 1000 unikālo klientu. Ja būs mazāk par 10 klientiem un nepietiks datu, modelis būs kļūmīgs.
    - Datu pilnīgums: Vairāk nekā 20% trūkstošo vērtību sniegtās entītijas datu laukā.

> [!NOTE]
> Uzņēmumiem ar augstu klientu pirkšanas biežumu (reizi dažās nedēļās) ir ieteicams izvēlēties īsāku prognozēšanas logu un zuduma definīciju. Ja pirkšanas biežums ir zems (reizi dažos mēnešos vai reizi gadā), izvēlieties garāku prognozēšanas logu un zuduma definīciju.

## <a name="create-a-transaction-churn-prediction"></a>Transakciju zuduma prognozes izveide

1. Sadaļā Customer Insights dodieties uz **Informācija** > **Prognozes**.

1. Atlasiet **elementu Klients, kas izmanto modeli**, un atlasiet **Izmantot šo modeli**.

1. Rūtī **Klientu zuduma modelis** izvēlieties **Transakcija** un atlasiet **Sākt darbu**.

:::image type="content" source="media/select-transaction-churn.PNG" alt-text="Ekrānuzņēmums ar atlasītu transakcijas opciju Klientu zuduma modeļa rūtī.":::
 
### <a name="name-model"></a>Nosaukuma piešķiršana modelim

1. Norādiet modeļa nosaukumu, kas atšķir to no citiem modeļiem.

1. Norādiet izvades entītijas nosaukumu, izmantojot tikai burtus un ciparus, bez tukšzīmēm. Tas ir nosaukums, ko izmantos modeļa entītija. 

1. Atlasiet **Tālāk**.

### <a name="define-customer-churn"></a>Definēt klientu zudumu

1. Iestatiet **logu prognoze**. Piemēram, prognozētu kannas risku saviem klientiem nākamo 90 dienu laikā, lai pielīdzinātos jūsu mārketinga saglabāšanas pūliņiem. Prognozējot zudumu risku ilgākā vai īsākā laika periodā var apgrūtināt, lai risinātu faktorus jūsu zudumu riska profilu, bet tas ir atkarīgs no jūsu uzņēmuma specifiskajām prasībām.
   >[!TIP]
   > Jebkurā laikā varat atlasīt **Saglabāt melnrakstu**, lai saglabātu prognoze kā melnrakstu. Lai turpinātu darbu, cilnē **Manas prognozes** ir atrodama melnraksta prognoze.

1. Ievadiet dienu skaitu, lai definētu čupli laukā **Churn definition**. Piemēram, ja klients nav veicis pirkumus pēdējo 30 dienu laikā, tie var tikt uzskatīti par zudušiem jūsu uzņēmumam. 

1. Atlasiet **Tālāk**, lai turpinātu.

### <a name="add-required-data"></a>Pievienot nepieciešamos datus

1. Atlasiet vienumu **Pievienot datus** un izvēlieties darbības tipu sānu rūtij, kurā ir nepieciešamā informācija par transakciju vai pirkumu vēsturi.

1. Sadaļā **Darbību atlase** izvēlieties konkrētas aktivitātes no atlasītā aktivitātes tipa, uz kuru vēlaties, lai aprēķins koncentrētos.

   :::image type="content" source="media/transaction-churn-select-activity.PNG" alt-text="Sānu rūts, kurā redzama noteiktu darbību izvēle zem semantiskā tipa.":::

   Ja vēl neesat kartējis darbību uz semantiskās darbības tipu, atlasiet **Rediģēt**, lai to izdarītu. Tiek atvērta vadītā pieredze semantiskās darbības kartēšanas laikā. Tagad kartējiet datus uz darbības tipa saistītajiem laukiem.

1. Kartējiet semantiskos atribūtus uz laukiem, kas nepieciešami modeļa palaišanai. Ja tālāk norādītie lauki nav aizpildīti, konfigurējiet savas pirkumu vēstures entītijas attiecības ar *Klienta* entītiju. Atlasiet **Saglabāt**.

1. **Solī Pievienot nepieciešamos datus** atlasiet **Tālāk**, lai turpinātu, ja nevēlaties pievienot papildu darbības.


# <a name="individual-consumers-b-to-c"></a>[Atsevišķi patērētāji (B2C)](#tab/b2c)

### <a name="add-additional-data-optional"></a>Pievienot papildu datus (neobligāti)

Konfigurējiet klienta darbības entītijas attiecības ar *Klienta* entītiju.

1. Atlasiet vienumu Lauks, kas ir identificējis klientu pirkumu vēstures tabulā. To var tieši saistīt ar *Klienta* entītijas primāro klienta ID.

1. Atlasiet entītiju, kas ir jūsu primārā *Klienta* entītija.

1. Ievadiet nosaukumu, kas apraksta attiecību.

#### <a name="customer-activities"></a>Klienta darbības

1. Ja vēlaties, atlasiet **Pievienot datus** **Klientu darbībām**.

1. Atlasiet semantiskās darbības tipu, kurā ir dati, ko vēlaties izmantot, un sadaļā **Darbības** atlasiet vienu vai vairākas darbības.

1. Atlasiet darbības tipu, kas atbilst konfigurētā klienta darbības tipam. Atlasiet vienumu **Izveidot jaunu** un izvēlieties pieejamu darbības tipu vai izveidojiet jaunu tipu.

1. Atlasiet **Tālāk**, tad **Saglabāt**.

1. Ja jums ir citas klientu darbības, ko vēlaties iekļaut, atkārtojiet iepriekš aprakstītās darbības.

# <a name="business-accounts-b-to-b"></a>[Uzņēmumu konti (B2B)](#tab/b2b)

### <a name="select-prediction-level"></a>Atlasīt prognozes līmenis

Vairums prognožu ir izveidotas klientu līmenī. Dažās situācijās, iespējams, tās nav pietiekoši detalizētas, lai atbilstu jūsu uzņēmuma vajadzībām. Šo līdzekli var izmantot, lai prognozētu zudumu klienta zaram, piemēram, nevis klientam kā tādam.

1. Lai izveidotu prognozi daudz detalizētākā līmenī, kas lielāks par klientu, atlasiet **Atlasīt entītiju sekundārajam līmenim**. Ja šī opcija nav pieejama, pārliecinieties, vai iepriekšējā sadaļa ir pabeigta.

1. Izvērsiet entītijas, no kurām vēlaties izvēlēties sekundāro līmeni, vai izmantojiet meklēšanas filtra lodziņu, lai filtrētu atlasītās opcijas.

1. Izvēlieties atribūtu, ko vēlaties izmantot kā sekundāro līmeni, un pēc tam atlasiet vienumu **Pievienot**.

1. Atlasiet **Tālāk**.

> [!NOTE]
> Šajā sadaļā pieejamās entītijas tiek parādītas, jo tām ir attiecības ar entītiju, ko izvēlējāties iepriekšējā sadaļā. Ja neredzat entītiju, kuru vēlaties pievienot, pārliecinieties, vai tai ir spēkā esošas attiecības sadaļā **Attiecības**. Šai konfigurācijai ir derīgas tikai attiecības viens pret vienu un daudzi pret vienu.

### <a name="add-additional-data-optional"></a>Pievienot papildu datus (neobligāti)

Konfigurējiet klienta darbības entītijas attiecības ar *Klienta* entītiju.

1. Atlasiet vienumu Lauks, kas ir identificējis klientu pirkumu vēstures tabulā. To var tieši saistīt ar *Klienta* entītijas primāro klienta ID.

1. Atlasiet entītiju, kas ir jūsu primārā *Klienta* entītija.

1. Ievadiet nosaukumu, kas apraksta attiecību.

#### <a name="customer-activities"></a>Klienta darbības

1. Ja vēlaties, atlasiet **Pievienot datus** **Klientu darbībām**.

1. Atlasiet semantiskās darbības tipu, kurā ir dati, ko vēlaties izmantot, un sadaļā **Darbības** atlasiet vienu vai vairākas darbības.

1. Atlasiet darbības tipu, kas atbilst konfigurētā klienta darbības tipam. Atlasiet vienumu **Izveidot jaunu** un izvēlieties pieejamu darbības tipu vai izveidojiet jaunu tipu.

1. Atlasiet **Tālāk**, tad **Saglabāt**.

1. Ja jums ir citas klientu darbības, ko vēlaties iekļaut, atkārtojiet iepriekš aprakstītās darbības.

#### <a name="customers-data"></a>Klientu dati

1. Ja vēlaties, atlasiet **Pievienot datus** **Klientu datiem**.

1. Kartējiet semantiskos atribūtus uz laukiem, kas ir jūsu identificētie klientu dati. Izmantotajiem laukiem vajadzētu bieži mainīties, lai nodrošinātu modeļa vislabāko veiktspēju. Piemēram, atlasot lauku "Klasifikācija", kas mainīs katru mēnesi, tiks izmantota tikai pēdējā vērtība laukā prognoze, lai gan vēsturiski tā pati vērtība var nebūt piemērojama klientam, veidojot prognoze shēmas.

1. Atlasiet **Tālāk**.

### <a name="provide-an-optional-list-of-benchmark-accounts"></a>Norādiet neobligātu sarakstu ar procesu mērījumu uzņēmumiem

Pievienojiet biznesa klientu un uzņēmumu sarakstu, kurus vēlaties izmantot kā procesu mērījumus. Jūs saņemsit [detalizētu informāciju par šiem procesu mērījumu kontiem](#review-a-prediction-status-and-results), tostarp to gūsiet punktu skaitu un iespaidīgākajiem līdzekļiem, kas ietekmēja viņu zuduma prognozi.

1. Atlasīt **+ Pievienot klientus**.

1. Izvēlieties klientus, kas darbojas kā procesu mērījumi.

1. Atlasiet **Tālāk**, lai turpinātu.

---

### <a name="set-schedule-and-review-configuration"></a>Iestatiet grafiku un pārskatiet konfigurāciju

1. Lai atkārtoti apmācītu modeli, iestatiet frekvenci. Šis iestatījums ir svarīgs, lai atjauninātu tādu prognožu precizitāti kā jauni dati, kas tiek uzņemti auditorijas ieskatos. Lielākā daļa uzņēmumu var pārkvalificēties reizi mēnesī un iegūt labu precizitāti to prognozēšanai.

1. Atlasiet **Tālāk**.

1. Pārskatiet prognozes konfigurāciju. Varat atgriezties pie iepriekšējiem soļiem, atlasot **Rediģēt** zem parādāmās vērtības. Vai arī varat atlasīt konfigurācijas soli no progresa rādītāja.

1. Ja visas vērtības ir konfigurētas pareizi, atlasiet **Saglabāt un palaist**, lai sāktu prognozēšanas procesu. Cilnē **Manas prognozes** var redzēt savu prognožu statusu. Atkarībā no prognozēšanas laikā izmantojamā datu daudzuma process var aizņemt vairākas stundas.

## <a name="review-a-prediction-status-and-results"></a>Prognozēšanas statusa un rezultātu pārskatīšana

1. Atveriet  **Informācija** > **Prognozes** un atlasiet cilni **Manas prognozes**.

1. Atlasiet prognozes, kuras vēlaties pārskatīt.
   - **Prognoze nosaukums**: izveides brīdī paredzētās prognozes nosaukums.
   - **Prognoze tips**: prognozei izmantotā modeļa tips
   - **Izvades entītija**: entītijas nosaukums, kurā saglabāt prognozes izvadi. Entītiju ar šo nosaukumu var atrast **Dati** > **Entītijas**.
     Izvades entitījā *ChurnScore* ir prognozētā zuduma iespējamība un *IsChurn* ir binārā etiķete, kas balstās *ChurnScore* ar slieksni 0.5. Noklusējuma slieksnis jūsu scenārijā varētu nedarboties. [Izveidojiet jaunu segmentu](segments.md#create-a-new-segment) ar vēlamo slieksni.
     Ne visi klienti ir aktīvi. Iespējams, daži no viņiem nav bijuši aktīvi ilgāku laiku un jau tiek uzskatīti par zudušiem, pamatojoties uz jūsu zuduma definīciju. Zuduma riska prognoze klientiem, kas jau ir zuduši, nav lietderīga, jo tie nav ieinteresētā auditorija.
   - **Prognozētais lauks**: Šis lauks tiek aizpildīts tikai dažu veidu prognozēm, un tos neizmanto zudumu prognozē.
   - **Statuss**: Prognozes izpildes statuss.
        - **Ierindots**: Prognoze gaida citu procesu izpildi.
        - **Atsvaidzināšana**: Prognoze pašlaik darbojas, lai iegūtu rezultātus, kas ieplūst izvades entītijā.
        - **Neizdevās**: neizdevās palaist prognozi. Lai iegūtu detalizētu informāciju, [skatiet žurnālfailus](manage-predictions.md#troubleshoot-a-failed-prediction).
        - **Veiksmīgi**: prognoze ir veiksmīga. Lai pārskatītu prognozi, zem vertikālajām elipsēm atlasiet **Skatīt**
   - **Rediģēts**: datums, kad tika mainīta prognozes konfigurācija.
   - **Pēdējā atsvaidzināšana**: datums, kad prognozes atsvaidzinātais rezultāts ir redzams izvades entītijā.

1. Atlasiet vertikālās elipses, kas atrodas blakus prognozei, kurā vēlaties pārskatīt rezultātus, un atlasiet **Skatīt**.

   :::image type="content" source="media/model-subs-view.PNG" alt-text="Skatīt vadīklu, lai redzētu prognozes rezultātus.":::

# <a name="individual-consumers-b-to-c"></a>[Atsevišķi patērētāji (B2C)](#tab/b2c)

1. Rezultātu lapā ir trīs primāro sadaļu dati:
   - **Apmācības modeļa veiktspēja**: iespējamie rezultāti ir A, B vai C. Šis rezultāts norāda uz prognozes izpildi un var palīdzēt pieņemt lēmumu izmantot izvades entītijā glabātos rezultātus. Rezultātus nosaka, par pamatu izmantojot tālāk norādītās kārtulas: 
        - **A** Ja modelis precīzi prognozēja vismaz 50% no kopējām prognozēm un ja procentuālā daļa no precīzas prognozes klientiem, kuri ir zuduši, pārsniedz bāzes likmi vismaz par 10%.
            
        - **B** Ja modelis precīzi prognozēja vismaz 50% no kopējām prognozēm un ja procentuālā daļa no precīzas prognozes klientiem, kuri ir zuduši, ir līdz 10% lielāki nekā bāzes likme.
            
        - **C** Ja modelis precīzi prognozēja vismaz 50% no kopējām prognozēm un ja procentuālā daļa no precīzas prognozes klientiem, kuri ir zuduši, ir mazāki nekā bāzes likme.
               
        - **Bāze** ņem prognozes laika loga ievadi modelim (piemēram, viens gads), un modelis veido dažādas laika frakcijas, dalot to ar 2, līdz tas sasniedz vienu mēnesi vai mazāk. Šīs frakcijas izmanto, lai izveidotu biznesa kārtulu klientiem, kas nav veikuši pirkumus šajā laika periodā. Šie klienti tiek uzskatīti par zudušiem. Uz laiku balstītā biznesa kārtula ar augstāko iespējamību prognozēt, kurš, visticamāk ir zudis, ir izvēlēts kā bāzes likmes modelis.
            
    - **Zuduma varbūtība (klientu skaits)**: klientu grupas, pamatojoties uz to prognozējamo zuduma risku. Šie dati var palīdzēt vēlāk, ja vēlaties izveidot klientu segmentu ar augstu zuduma risku. Šādi segmenti palīdz saprast, kur vajadzētu būt dalībai segmentā.
       
    - **Ietekmīgākie faktori**: ir daudzi faktori, kas tiek ņemti vērā, veidojot jūsu prognozi. Katram faktoram ir nozīme, kas aprēķināta modeļa izveidotajos apkopotajās prognozēs. Šos faktorus var izmantot, lai apstiprinātu prognozes rezultātus, vai arī šo informāciju var izmantot vēlāk, lai [izveidotu segmentus](segments.md), kas var palīdzēt ietekmēt klientu zuduma risku.


# <a name="business-accounts-b-to-b"></a>[Uzņēmumu konti (B2B)](#tab/b2b)

1. Rezultātu lapā ir trīs primāro sadaļu dati:
   - **Apmācības modeļa veiktspēja**: iespējamie rezultāti ir A, B vai C. Šis rezultāts norāda uz prognozes izpildi un var palīdzēt pieņemt lēmumu izmantot izvades entītijā glabātos rezultātus. Rezultātus nosaka, par pamatu izmantojot tālāk norādītās kārtulas: 
        - **A** Ja modelis precīzi prognozēja vismaz 50% no kopējām prognozēm un ja procentuālā daļa no precīzas prognozes klientiem, kuri ir zuduši, pārsniedz bāzes likmi vismaz par 10%.
            
        - **B** Ja modelis precīzi prognozēja vismaz 50% no kopējām prognozēm un ja procentuālā daļa no precīzas prognozes klientiem, kuri ir zuduši, ir līdz 10% lielāki nekā bāzes likme.
            
        - **C** Ja modelis precīzi prognozēja vismaz 50% no kopējām prognozēm un ja procentuālā daļa no precīzas prognozes klientiem, kuri ir zuduši, ir mazāki nekā bāzes likme.
               
        - **Bāze** ņem prognozes laika loga ievadi modelim (piemēram, viens gads), un modelis veido dažādas laika frakcijas, dalot to ar 2, līdz tas sasniedz vienu mēnesi vai mazāk. Šīs frakcijas izmanto, lai izveidotu biznesa kārtulu klientiem, kas nav veikuši pirkumus šajā laika periodā. Šie klienti tiek uzskatīti par zudušiem. Uz laiku balstītā biznesa kārtula ar augstāko iespējamību prognozēt, kurš, visticamāk ir zudis, ir izvēlēts kā bāzes likmes modelis.
            
    - **Zuduma varbūtība (klientu skaits)**: klientu grupas, pamatojoties uz to prognozējamo zuduma risku. Šie dati var palīdzēt vēlāk, ja vēlaties izveidot klientu segmentu ar augstu zuduma risku. Šādi segmenti palīdz saprast, kur vajadzētu būt dalībai segmentā.
       
    - **Ietekmīgākie faktori**: ir daudzi faktori, kas tiek ņemti vērā, veidojot jūsu prognozi. Katram faktoram ir nozīme, kas aprēķināta modeļa izveidotajos apkopotajās prognozēs. Šos faktorus var izmantot, lai apstiprinātu prognozes rezultātus, vai arī šo informāciju var izmantot vēlāk, lai [izveidotu segmentus](segments.md), kas var palīdzēt ietekmēt klientu zuduma risku.


1. Darba uzņēmumiem ir pieejama **Ietekmes līdzekļu analīzes** informācijas lapa. Tajā ir četras datu sadaļas:

    - Labajā rūtī atlasītais vienums nosaka saturu šajā lapā. Atlasiet elementu no **Populārākajiem klientiem** vai no **Procesu mērījumu klientiem**. Abi saraksti tiek pasūtīti, to vērtība samazinoties un vai nu rezultāts ir tikai klientam, vai arī apvienots rezultāts klientiem, un sekundārais līmenis, piemēram, produktu kategorija.
        
        - **Populārākie klienti**: saraksts ar 10 klientiem, kuriem ir vislielākais un vismazākais zuduma risks, pamatojoties uz viņu zuduma rezultātiem. 
        - **Procesu mērījumu klienti**: saraksts ar līdz pat 10 klientiem, kuri tika atlasīti modeļa konfigurēšanas laikā.
 
    - **Zuduma rezultāts**: rāda zuduma rezultātu atlasītajam elementam labajā rūtī.
    
    - **Zuduma riska sadale:** rāda klientu zuduma riska sadali un procentuālo attiecību, kādā atrodas atlasītais klients. 
    
    - **Populārākās funkcijas, kas palielina un samazina risku:** Attiecībā uz atlasīto elementu labajā rūtī tiek uzskaitīti pieci labākie līdzekļi, kas palielina vai samazina zuduma risku. Attiecībā uz katru ietekmes līdzekli jūs atradīsit šī elementa vērtību un tā ietekmi uz zuduma rezultātu. Tiek rādīta arī katra līdzekļa vidējā vērtība zema, vidēja un augsta klientu zuduma segmentos. Tas palīdz labāk kontekstualizēt atlasītā elementa augšējo ietekmes līdzekļu vērtību un salīdzināt to ar zema, vidēja un augsta zuduma klientu segmentiem.

       - Zems: uzņēmuma un sekundārā līmeņa uzņēmumi vai kombinācijas ar 0–0,33 zuduma punktu skaitu
       - Vidējs: uzņēmuma un sekundārā līmeņa uzņēmumi vai kombinācijas ar 0.33–0,66 zuduma punktu skaitu
       - Augsts: uzņēmuma un sekundārā līmeņa uzņēmumi vai kombinācijas, kuru zuduma rezultāts ir lielāks nekā 0,66
    
       Kad jūs prognozējat zudumu uzņēmuma līmenī, visi uzņēmumi tiek ņemti vērā, atvasinot vidējās līdzekļu vērtības zuduma segmentiem. Katra uzņēmuma sekundārā līmeņa zuduma prognozēm zuduma segmentu atvasināšana ir atkarīga no atlasītā sānu rūts elementa sekoundārā līmeņa. Piemēram, ja elementam ir sekundārais produktu kategorijas līmenis = biroja preces, tad tikai tādi elementi, kam kā produktu kategorija ir biroja palīgs, tiek izskatīti, kad tiek dena šādi izlīdzinātas vidējām līdzekļa vērtībām segmentos. Šī loģika tiek pielietota, lai nodrošinātu elementa līdzekļu vērtību taisnīgu salīdzinājumu ar vidējām vērtībām maziem, vidējiem un augstiem segmentiem.

       Dažos gadījumos zema, vidēja vai augsta segmenta vidējā vērtība ir tukša vai nav pieejama, jo nav elementu, kas pieder atbilstošajiem zuduma segmentiem, pamatojoties uz iepriekš minēto definīciju.
       
       > [!NOTE]
       > Vērtībām, kuru vērtība ir vidējam zemam, vidējam un augstam, ir atšķirīgas attiecībā uz iedarboju funkcijām, piemēram, valsti vai nozari. Tā kā līdzekļa "vidējā" vērtība neattiecas uz kategoriju līdzekļiem, šajās kolonnās vērtībām ir tādu klientu proporcija, kuru segmenti ir mazi, vidēji vai augsti, un tiem ir tāda pati līdzekļa vērtība kā sānu panelī atlasītajam elementam.

---

## <a name="manage-predictions"></a>Pārvaldīt prognozes

Ir iespējams optimizēt, novērst problēmas, atsvaidzināt vai dzēst prognozes. Pārskatiet ievades datu lietojamības ziņojumu, lai uzzinātu, kā padarīt prognozi ātrāku un uzticamāku. Lai iegūtu papildinformāciju, dodieties uz [Pārvaldīt prognozes](manage-predictions.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
