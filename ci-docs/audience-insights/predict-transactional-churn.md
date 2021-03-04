---
title: Transakciju zuduma prognoze
description: Prognozējiet, vai pastāv risks, ka klients vairs neiegādāsies jūsu uzņēmuma produktus vai pakalpojumus.
ms.date: 11/12/2020
ms.reviewer: zacook
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: af461d290c69687fb47bacfcff446a0c62978383
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268327"
---
# <a name="transactional-churn-prediction-preview"></a>Transakciju zuduma prognoze (priekšskatījums)

Transakciju zudumu prognoze palīdz paredzēt, vai klients vairs nepirks jūsu produktus vai pakalpojumus noteiktā laika logā. Jūs varat izveidot jaunas zudumu prognozes **Informācijā** > **Prognozēs**. Atlasiet **Manas prognozes**, lai skatītu citas jūsu izveidotās prognozes.

> [!TIP]
> Izmēģiniet pamācību par abonēšanas zudumu prognozi, izmantojot datu paraugu: [Abonēšanas zudumu prognožu parauga ceļvedis](sample-guide-predict-transactional-churn.md).

## <a name="prerequisites"></a>Priekšnosacījumi

- Vismaz [Līdzautora atļaujas](permissions.md) Customer Insights.
- Biznesa zināšanas, lai saprastu, ko zudums nozīmē jūsu uzņēmumam. Mēs atbalstām uz laiku balstītu zudumu definīcijas, kas nozīmē, ka klients ir uzskatāms par zudušu pēc perioda bez pirkumiem.
- Dati par jūsu transakcijām/pirkumiem un to vēsturi:
    - Transakciju identifikatori, lai atšķirtu pirkumus/transakcijas.
    - Klientu identifikatori, lai saskaņotu transakcijas ar klientiem.
    - Darbības notikuma datumi, kuros definēti transakcijas datumi.
    - Attiecībā uz pirkumu/transakciju semantisko datu shēmu ir nepieciešama šāda informācija:
        - **Transakcijas ID:** Unikāls pirkšanas vai transakcijas identifikators.
        - **Darbības datums:** Pirkšanas vai transakcijas datums.
        - **Darbības vērtība:** Darbības/krājuma valūtas/skaitliskās vērtības summa.
        - (Neobligāti) **Unikāls produkta ID:** Produkta vai servisa ID, kas iegādāts, ja dati ir rindas elementu līmenī.
        - (Neobligāti) **To, vai šī transakcija ir atgriezta:** Patiess/aplams lauks, kas norāda, vai transakcija ir atgriezta vai ne. Ja **Transakcijas vērtība** ir negatīva, mēs arī izmantosim šo informāciju, lai secinātu par peļņu.
- (Neobligāti) Dati par klientu darbībām:
    - Darbības identifikatori, lai nodalītu tāda paša tipa darbības.
    - Klientu identifikatori darbību kartēšanai jūsu klientiem.
    - Darbības informācija, kas ietver darbības nosaukumu un datumu.
    - Klienta darbību semantisko datu shēma ietver:
        - **Primārā atslēga:** unikāls darbības identifikators. Piemēram, vietnes apmeklējums vai lietojuma ieraksts, kas norāda, ka klients ir izmēģinājis jūsu produkta paraugu.
        - **Laikspiedols:** notikuma datums un laiks, ko identificē primārā atslēga.
        - **Notikums:** Norādiet notikuma nosaukumu, kuru vēlaties izmantot. Piemēram, lauks "UserAction" pārtikas preču veikalā varētu būt klientam piemērots kupona lietojums.
        - **Detalizēti:** Detalizēta informācija par notikumu. Piemēram, preču veikala lauks ar nosaukumu "CouponValue" var būt kupona valūtas vērtība.

## <a name="create-a-transactional-churn-prediction"></a>Transakciju zuduma prognozes izveide

1. Sadaļā Customer Insights dodieties uz **Informācija** > **Prognozes**.

1. Atlasiet elementu **Klientu zuduma modeli (priekšskatījums)** un atlasiet opciju **Lietot šo modeli**.
   
1. Rūtī **Klientu zuduma modelis** izvēlieties **Ttransakciju** un atlasiet **Sākt**.

:::image type="content" source="media/select-transaction-churn.PNG" alt-text="Ekrānuzņēmums ar atlasītu transakciju opciju klientu zuduma modeļa rūtī.":::

### <a name="name-model"></a>Nosaukuma piešķiršana modelim

1. Norādiet modeļa nosaukumu, kas atšķir to no citiem modeļiem.

1. Norādiet izvades entītijas nosaukumu, izmantojot tikai burtus un ciparus, bez tukšzīmēm. Tas ir nosaukums, ko izmantos modeļa entītija. 

1. Atlasiet **Tālāk**.

### <a name="define-customer-churn"></a>Definēt klientu zudumu

1. Iestatiet dienu logu, lai paredzētu zudumu, lai **Identificētu tos klientus, kas var zust nākošajā laukā**. Piemēram, prognozētu kannas risku saviem klientiem nākamo 90 dienu laikā, lai pielīdzinātos jūsu mārketinga saglabāšanas pūliņiem. Prognozējot zudumu risku ilgākā vai īsākā laika periodā var apgrūtināt, lai risinātu faktorus jūsu zudumu riska profilu, bet tas ir atkarīgs no jūsu uzņēmuma specifiskajām prasībām. 
   >[!TIP]
   > Lai saglabātu prognozēšanu kā melnrakstu, varat atlasīt **Saglabāt un aizvērt** jebkurā brīdī. Lai turpinātu darbu, cilnē **Manas prognozes** ir atrodama melnraksta prognoze.

1. Ievadiet dienu skaitu, lai definētu zudumu laukā **Klients ir zudis, ja tas nav veicis pirkumus:** laukā. Piemēram, ja klients nav veicis pirkumus pēdējo 30 dienu laikā, tie var tikt uzskatīti par zudušiem jūsu uzņēmumam. 

1. Atlasiet **Tālāk**, lai turpinātu

### <a name="add-required-data"></a>Pievienot nepieciešamos datus

1. Atlasiet opciju **Pievienot datus** **Pirkumu vēsturei** un izvēlieties entītiju, kas nodrošina transakciju/pirkumu vēstures informāciju, kā aprakstīts [priekšnosacījumos](#prerequisites).

1. Kartējiet semantiskos laukus uz atribūtiem jūsu pirkumu vēstures entītijā un atlasiet **Tālāk**. Attiecībā uz lauku aprakstiem apskatiet [priekšnosacījumus](#prerequisites).

   :::image type="content" source="media/model-map-purchase-entity.PNG" alt-text="Kartējiet pirkšanas entītijas semantiskos laukus.":::

1. Ja tālāk norādītie lauki nav aizpildīti, konfigurējiet savas pirkumu vēstures entītijas attiecības ar klienta entītiju.
    1. Atlasiet vienumu **Pirkumu vēstures entītija**.
    1. Atlasiet vienumu **Lauks**, kas ir identificējis klientu pirkumu vēstures entītijā. Tam ir jāattiecas uz jūsu Klienta entītijas primāro klienta ID.
    1. Atlasiet **Klienta entītiju**, kas atbilst primārajai klienta entītijai.
    1. Ievadiet nosaukumu, kas apraksta attiecību.

    :::image type="content" source="media/model-purchase-join.PNG" alt-text="Pirkumu vēstures lapa, kurā parādīta attiecību izveide ar klientu.":::
   
1. Atlasiet **Tālāk**.

1. Ja vēlaties, atlasiet **Pievienot datus** **Klientu darbībām**. Izvēlieties entītiju, kas sniedz informāciju par klientu darbībām, kā aprakstīts priekšnosacījumos.

1. Kartējiet semantiskos laukus uz atribūtiem jūsu klientu darbības entītijā un atlasiet **Tālāk**. Attiecībā uz lauku aprakstiem apskatiet [priekšnosacījumus](#prerequisites).

   :::image type="content" source="media/map-transaction-data-fields.png" alt-text="Kartējiet klientu laukus transakciju datiem.":::

1. Atlasiet darbības tipu, kas atbilst konfigurētā klienta darbības tipam. Atlasiet vienumu **Izveidot jaunu** un izvēlieties pieejamu darbības tipu vai izveidojiet jaunu tipu.

1. Jums ir jākonfigurē attiecības no klienta darbības entītijas uz Klienta entītiju.
    1. Atlasiet vienumu Lauks, kas ir identificējis klientu pirkumu vēstures tabulā. To var tieši saistīt ar klienta entītijas primāro klienta ID.
    1. Atlasiet Klienta entītiju, kas atbilst primārajai Klienta entītijai
    1. Ievadiet nosaukumu, kas apraksta attiecību.

1. Atlasiet vienumu **Saglabāt**.

1. Ja jums ir citas klientu darbības, ko vēlaties iekļaut, atkārtojiet iepriekš aprakstītās darbības.

1. Atlasiet **Tālāk**.

### <a name="set-schedule-and-review-configuration"></a>Iestatiet grafiku un pārskatiet konfigurāciju

1. Lai atkārtoti apmācītu modeli, iestatiet frekvenci. Šis iestatījums ir svarīgs, lai atjauninātu tādu prognožu precizitāti kā jauni dati, kas tiek uzņemti auditorijas ieskatos. Lielākā daļa uzņēmumu var pārkvalificēties reizi mēnesī un iegūt labu precizitāti to prognozēšanai.

1. Atlasiet **Tālāk**.

1. Pārskatiet prognozes konfigurāciju. Varat atgriezties pie iepriekšējiem soļiem, atlasot **Rediģēt** zem parādāmās vērtības. Vai arī varat atlasīt konfigurācijas soli no progresa rādītāja.

1. Ja visas vērtības ir konfigurētas pareizi, atlasiet **Saglabāt un palaist**, lai sāktu prognozēšanas procesu. Cilnē **Manas prognozes** var redzēt savu prognožu statusu. Atkarībā no prognozēšanas laikā izmantojamā datu daudzuma process var aizņemt vairākas stundas.

## <a name="review-a-prediction-status-and-results"></a>Prognozēšanas statusa un rezultātu pārskatīšana

1. Atveriet  **Informācija** > **Prognozes** un atlasiet cilni **Manas prognozes**.

1. Atlasiet prognozes, kuras vēlaties pārskatīt.
   - **Prognoze nosaukums:** Izveides brīdī paredzētās prognozes nosaukums.
   - **Prognoze tips:** Modeļa tips, kas izmantots prognozei
   - **Izvades entītija:** entītijas nosaukums, kurā saglabāt prognozes izvadi. Entītiju ar šo nosaukumu var atrast **Dati** > **Entītijas**.
   - **Prognozētais lauks:** Šis lauks tiek aizpildīts tikai dažu veidu prognozēm, un tos neizmanto zudumu prognozē.
   - **Statuss:** Prognozes izpildes statuss.
        - **Ierindots:** Prognoze gaida citu procesu izpildi.
        - **Atsvaidzināšana:** Prognoze pašlaik darbojas, lai iegūtu rezultātus, kas ieplūst izvades entītijā.
        - **Neizdevās:** Neizdevās palaist prognozi. Lai iegūtu detalizētu informāciju, [skatiet žurnālfailus](#troubleshoot-a-failed-prediction).
        - **Veiksmīgi:** Prognoze ir veiksmīga. Lai pārskatītu prognozi, zem vertikālajām elipsēm atlasiet **Skatīt**
   - **Rediģēts:** Datums, kad tika mainīta prognozes konfigurācija.
   - **Pēdējā atsvaidzināšana:** Datums, kad atsvaidzinātais rezultāts ir redzams izvades entītijā.

1. Atlasiet vertikālās elipses, kas atrodas blakus prognozei, kurā vēlaties pārskatīt rezultātus, un atlasiet **Skatīt**.

   :::image type="content" source="media/model-subs-view.PNG" alt-text="Skatīt vadīklu, lai redzētu prognozes rezultātus.":::   

1. Rezultātu lapā ir trīs primāro sadaļu dati:
    1. **Apmācības modeļa veiktspēja:** iespējamie rezultāti ir A, B vai C. Šis rezultāts norāda uz prognozes izpildi un var palīdzēt pieņemt lēmumu izmantot izvades entītijā glabātos rezultātus. Rezultātus nosaka, par pamatu izmantojot tālāk norādītās kārtulas:
         
         - **A** Ja modelis precīzi prognozēja vismaz 50% no kopējām prognozēm un ja procentuālā daļa no precīzas prognozes klientiem, kuri ir zuduši, pārsniedz bāzes likmi vismaz par 10%.
            
         - **B** Ja modelis precīzi prognozēja vismaz 50% no kopējām prognozēm un ja procentuālā daļa no precīzas prognozes klientiem, kuri ir zuduši, ir līdz 10% lielāki nekā bāzes likme.
            
         - **C** Ja modelis precīzi prognozēja vismaz 50% no kopējām prognozēm un ja procentuālā daļa no precīzas prognozes klientiem, kuri ir zuduši, ir mazāki nekā bāzes likme.
               
         - **Bāzes likme** ņem prognozes laika loga ievadi modelim (piemēram, viens gads), un modelis veido dažādas laika frakcijas, dalot to ar 2, līdz tas sasniedz vienu mēnesi vai mazāk. Šīs frakcijas izmanto, lai izveidotu biznesa kārtulu klientiem, kas nav veikuši pirkumus šajā laika periodā. Šie klienti tiek uzskatīti par zudušiem. Uz laiku balstītā biznesa kārtula ar augstāko iespējamību prognozēt, kurš, visticamāk ir zudis,  ir izvēlēts kā bāzes likmes modelis.
            
    1. **Zuduma varbūtība (klientu skaits):** klientu grupas, pamatojoties uz to prognozējamo zuduma risku. Šie dati var palīdzēt vēlāk, ja vēlaties izveidot klientu segmentu ar augstu zuduma risku. Šādi segmenti palīdz saprast, kur vajadzētu būt dalībai segmentā.
       
    1. **Ietekmīgākie faktori:** ir daudzi faktori, kas tiek ņemti vērā, veidojot jūsu prognozi. Katram faktoram ir nozīme, kas aprēķināta modeļa izveidotajos apkopotajās prognozēs. Šos faktorus var izmantot, lai atvieglotu jūsu prognozes rezultātu validēšanu. Šo informāciju var izmantot arī vēlāk, lai [izveidotu segmentus](segments.md), kas varētu palīdzēt ietekmēt zuduma risku attiecībā uz klientiem.

## <a name="troubleshoot-a-failed-prediction"></a>Neizdevušās prognozes problēmas novēršana

1. Atveriet  **Informācija** > **Prognozes** un atlasiet cilni **Manas prognozes**.

1. Atlasiet vertikālās elipses, kas atrodas blakus prognozei, kurai vēlaties skatīt kļūdu žurnālus.

1. Atlasiet **Žurnāli**

1. Pārskatīt visas kļūdas. Pastāv vairāki kļūdu tipi, kas var rasties, un tie apraksta to, kas izraisīja kļūdu. Piemēram, kļūda, kurā nav pietiekami daudz datu, lai precīzi prognozētu, parasti tiek novērsta, ielādējot papildu datus Customer Insights.

## <a name="refresh-a-prediction"></a>Atsvaidzināt prognozi

Prognozes tiks automātiski atsvaidzinātas ar vienu un to pašu [grafiku, ko jūsu dati atsvaidzina](system.md#schedule-tab) kā konfigurēts iestatījumos. Tos var atsvaidzināt arī manuāli.

1. Atveriet  **Informācija** > **Prognozes** un atlasiet cilni **Manas prognozes**.

1. Atlasiet vertikālās elipses, kas atrodas blakus prognozei, kuru vēlaties atsvaidzināt.

1. Atlasiet **Atsvaidzināt**.

## <a name="delete-a-prediction"></a>Dzēst prognozi

Dzēšot prognozi, tiek noņemta arī tās izvades entītija.

1. Atveriet  **Informācija** > **Prognozes** un atlasiet cilni **Manas prognozes**.

1. Atlasiet vertikālās elipses, kas atrodas blakus prognozei, kuru vēlaties dzēst.

1. Atlasiet **Dzēst**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]