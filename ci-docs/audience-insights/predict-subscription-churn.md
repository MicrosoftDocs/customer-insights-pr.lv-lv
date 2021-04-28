---
title: Abonementu zuduma prognoze
description: Paredziet, vai pastāv risks, ka klients vairs neizmantos jūsu uzņēmuma abonēšanas produktus vai pakalpojumus.
ms.date: 08/19/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: b6bf4f715768b18d69be3bea4085acd96933e8da
ms.sourcegitcommit: 6d5dd572f75ba4c0303ec77c3b74e4318d52705c
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 04/16/2021
ms.locfileid: "5906911"
---
# <a name="subscription-churn-prediction-preview"></a>Abonēšanas zuduma prognoze (priekšskatījums)

Abonēšanas zuduma prognoze palīdz paredzēt, vai pastāv risks, ka klients vairs neizmantos jūsu uzņēmuma abonēšanas produktus vai pakalpojumus. Jūs varat izveidot jaunas abonēšanas zuduma prognozes lapā **Informācija** > **Prognozes**. Atlasiet **Manas prognozes**, lai skatītu citas jūsu izveidotās prognozes.

> [!TIP]
> Izmēģiniet pamācību par abonēšanas zudumu prognozi, izmantojot datu paraugu: [Abonēšanas zudumu prognožu parauga rokasgrāmata](sample-guide-predict-subscription-churn.md).

## <a name="prerequisites"></a>Priekšnosacījumi

- Vismaz [Līdzdalībnieka atļaujas](permissions.md).
- Biznesa zināšanas, lai saprastu, ko zudums nozīmē jūsu uzņēmumam. Mēs atbalstām uz laiku balstītas zuduma definīcijas, kas nozīmē, ka tiek uzskatīts, ka klients ir izvēlējies laika periodu pēc tam, kad beidzas viņu abonements.
- Jūsu abonementu un to vēstures dati:
    - Abonementa identifikatori, lai atšķirtu abonementus.
    - Klientu identifikatori, lai tie atbilstu klientu abonementiem.
    - Abonementa notikuma datumi, kuros ir definēti sākuma datumi, beigu datumi un datumi, kuros ir notikuši abonementa notikumi.
    - Abonementa informācija, lai definētu, vai tas ir periodisks abonements un cik bieži tas atjauno.
    - Abonementa semantiskajai datu shēmai ir nepieciešama šāda informācija:
        - **Abonementa ID:** unikāls abonementa identifikators.
        - **Abonementa beigu datums:** abonementa derīguma termiņš klientam.
        - **Abonementa sākuma datums:** abonementa sākuma datums klientam.
        - **Darbības datums:** datums, kad notikušas izmaiņas abonementā. Piemēram, klientam, kas pērk vai atceļ abonementu.
        - **Vai tas ir periodisks abonements:** būla patiess/aplams lauks, kas nosaka, vai abonements tiks atjaunots ar to pašu abonementa ID bez klienta iejaukšanās
        - **Atkārtošanās biežums (mēnešos):** periodiskiem abonementiem tas ir laiks, uz kādu abonements tiks atjaunots. Tas ir attēlots mēnešos. Piemēram, gada abonements, kas klientam katru gadu automātiski atjaunojas uz vēl vienu gadu, vērtība ir 12.
        - (Neobligāti) **Abonementa summa:** naudas summa, ko klients maksā par abonementa atjaunošanu. Tas var palīdzēt identificēt dažādu abonementu līmeņu shēmas.
- Dati par klientu darbībām:
    - Darbības identifikatori, lai nodalītu tāda paša tipa darbības.
    - Klientu identifikatori darbību kartēšanai jūsu klientiem.
    - Darbības informācija, kas ietver darbības nosaukumu un datumu.
    - Klienta darbību semantisko datu shēma ietver:
        - **Primārā atslēga:** unikāls darbības identifikators. Piemēram, tīmekļa vietnes apmeklējums vai lietojuma ieraksts, kas norāda klienta skatīto TV pārraides epizodi.
        - **Laikspiedols:** notikuma datums un laiks, ko identificē primārā atslēga.
        - **Notikums:** norādiet notikuma nosaukumu, kuru vēlaties izmantot. Piemēram, straumēšanas video pakalpojuma laukā ar nosaukumu "UserAction" var būt vērtība "Apskatīts".
        - **Detalizēti:** detalizēta informācija par notikumu. Piemēram, straumēšanas video pakalpojuma laukā ar nosaukumu "ShowTitle" var būt tāda videoklipa vērtība, kuru klients ir skatījies.
- Ieteicamie datu raksturlielumi:
    - Pietiekami vēsturiskie dati: Abonēšanas dati par laiku, kas vismaz divreiz pārsniedz atlasīto laika logu. Vēlams, lai būtu abonēšanas dati par diviem vai trim gadiem.
    - Abonementa statuss: Dati ietver katra klienta aktīvos un neaktīvos abonementus, tāpēc katram klienta ID ir vairāki ieraksti.
    - Klientu skaits: Vismaz 10 klientu profilu, vēlams vairāk nekā 1000 unikālo klientu. Ja būs mazāk par 10 klientiem un nepietiks datu, modelis būs kļūmīgs.
    - Datu pilnīgums: Vairāk nekā 20% trūkstošo vērtību sniegtās entītijas datu laukā.
   
   > [!NOTE]
   > Jums nepieciešami vismaz divi darbību ieraksti attiecībā uz 50% klientiem, par kuriem vēlaties aprēķināt klientu zudumu.

## <a name="create-a-subscription-churn-prediction"></a>Izveidot abonēšanas zuduma prognozi

1. Sadaļā Auditorijas ieskati ejiet uz **Informācija** > **Prognozes**.
1. Atlasiet elementu **Abonementa zuduma modelis (priekšskatījums)** un atlasiet opciju **Lietot šo modeli**.
   > [!div class="mx-imgBorder"]
   > ![Abonēšanas zuduma modeļa elements ar pogu Lietot šo modeli](media/subscription-churn-usethismodel.PNG "Abonēšanas zuduma modeļa elements ar pogu Lietot šo modeli")

### <a name="name-model"></a>Nosaukuma piešķiršana modelim

1. Norādiet modeļa nosaukumu, kas atšķir to no citiem modeļiem.
1. Norādiet izvades entītijas nosaukumu, izmantojot tikai burtus un ciparus, bez tukšzīmēm. Tas ir nosaukums, ko izmantos modeļa entītija. Pēc tam atlasiet **Tālāk**.

### <a name="define-customer-churn"></a>Definēt klientu zudumu

1. Ievadiet **Dienu skaits, kopš abonements beidzies**, ko jūsu uzņēmums uzskata par klientu zuduma stāvokli. Parasti šim periodam patīk biznesa darbības, piemēram, piedāvājumi vai citi mārketinga pasākumi, kas cenšas nepieļaut klientu zudumu.
1. Lai iestatītu periodu, kurā paredzēt klientu zudumu, ierakstiet skaitu **Dienu skaits nākotnē mainības prognozēšanai**. Piemēram, prognozēt klientu zuduma risku turpmāko 90 dienu laikā, lai pielāgotu mārketinga saglabāšanas aktivitātes. Zuduma riska prognozēšana ilgākiem vai garākiem laikposmiem var apgrūtināt jūsu zuduma risku profila faktoru atrisināšanu atkarībā no jūsu konkrētā biznesa prasībām. Atlasiet **Tālāk**, lai turpinātu
   >[!TIP]
   > Lai saglabātu prognozēšanu kā melnrakstu, varat atlasīt **Saglabāt un aizvērt** jebkurā brīdī. Lai turpinātu darbu, cilnē **Manas prognozes** ir atrodama melnraksta prognoze.

### <a name="add-required-data"></a>Nepieciešamo datu pievienošana

1. Atlasiet **Pievienot datus** **Abonēšanas vēsturei** un izvēlieties entītiju, kas nodrošina abonementu vēstures informāciju, kā aprakstīts [priekšnosacījumos](#prerequisites).
1. Ja tālāk norādītie lauki nav aizpildīti, konfigurējiet savas abonementa vēstures entītijas attiecības ar Klienta entītiju.
    1. Atlasiet **Abonementu vēstures entītija**.
    1. Atlasiet **Lauku**, kas norāda klientu abonementa vēstures entītijā. Tam ir jāattiecas uz jūsu Klienta entītijas primāro klienta ID.
    1. Atlasiet **Klienta entītiju**, kas atbilst primārajai klienta entītijai.
    1. Ievadiet nosaukumu, kas apraksta attiecību.
       > [!div class="mx-imgBorder"]
       > ![Abonementa vēstures lapa, kurā parādīta attiecību izveide ar klientu](media/subscription-churn-subscriptionhistoryrelationship.PNG "Abonementa vēstures lapa, kurā parādīta attiecību izveide ar klientu")
1. Atlasiet **Tālāk**.
1. Kartējiet semantiskos laukus uz atribūtiem jūsu abonementa vēstures entītijā un atlasiet **Saglabāt**. Attiecībā uz lauku aprakstiem apskatiet [priekšnosacījumus](#prerequisites).
   > [!div class="mx-imgBorder"]
   > ![Abonēšanas vēstures lapa, kurā parādīti semantiski atribūti, kas ir kartēti uz atlasītās abonementa vēstures entītijas laukiem](media/subscription-churn-subscriptionhistorymapping.PNG "Abonēšanas vēstures lapa, kurā parādīti semantiski atribūti, kas ir kartēti uz atlasītās abonementa vēstures entītijas laukiem")
1. Atlasiet **Pievienot datus** **Klientu darbībām** un izvēlieties entītiju, kas nodrošina klientu darbības informāciju, kā aprakstīts priekšnosacījumos.
1. Atlasiet darbības tipu, kas atbilst konfigurētā klienta darbības tipam.  Atlasiet **Izveidot jaunu** un norādiet nosaukumu, ja nav redzama opcija, kas atbilst nepieciešamajam darbības tipam.
1. Jums ir jākonfigurē attiecības no klienta darbības entītijas uz Klienta entītiju.
    1. Atlasiet lauku, kas klientu identificē klientu darbības tabulā, kas var būt tieši saistīta ar Klienta entītijas primāro klienta ID.
    1. Atlasiet Klienta entītiju, kas atbilst primārajai Klienta entītijai
    1. Ievadiet nosaukumu, kas apraksta attiecību.
1. Atlasiet **Tālāk**.
1. Kartējiet semantiskos laukus uz atribūtiem jūsu klientu darbības entītijā un atlasiet **Saglabāt**. Attiecībā uz lauku aprakstiem apskatiet [priekšnosacījumus](#prerequisites).
1. (Izvēles) Ja jums ir citas klientu darbības, ko vēlaties iekļaut, atkārtojiet iepriekš aprakstītās darbības.
   > [!div class="mx-imgBorder"]
   > ![Entītiju relācijas definēšana](media/subscription-churn-customeractivitiesmapping.PNG "Klientu darbību lapa, kurā parādīti semantiski atribūti, kas ir kartēti uz atlasītās klientu darbību entītijas laukiem")
1. Atlasiet **Tālāk**.

### <a name="set-schedule-and-review-configuration"></a>Iestatiet grafiku un pārskatiet konfigurāciju

1. Lai atkārtoti apmācītu modeli, iestatiet frekvenci. Šis iestatījums ir svarīgs, lai atjauninātu tādu prognožu precizitāti kā jauni dati, kas tiek uzņemti auditorijas ieskatos. Lielākā daļa uzņēmumu var pārkvalificēties reizi mēnesī un iegūt labu precizitāti to prognozēšanai.
1. Atlasiet **Tālāk**.
1. Pārskatīt konfigurāciju. Jūs varat atgriezties jebkurā prognozēšanas konfigurācijas daļā, zemāk parādītajā vērtībā atlasot **Rediģēt**. Vai arī varat atlasīt konfigurācijas soli no progresa rādītāja.
1. Ja visas vērtības ir konfigurētas pareizi, atlasiet **Saglabāt un palaist**, lai sāktu prognozēšanas procesu. Cilnē **Manas prognozes** var redzēt savu prognožu statusu. Atkarībā no prognozēšanas laikā izmantojamā datu daudzuma process var aizņemt vairākas stundas.

## <a name="review-a-prediction-status-and-results"></a>Prognozēšanas statusa un rezultātu pārskatīšana

1. Dodieties uz cilni **Manas prognozes** **Informācija** > **Prognozes**.
   > [!div class="mx-imgBorder"]
   > ![Skats lapā Manas prognozes](media/subscription-churn-mypredictions.PNG "Skats lapā Manas prognozes")
1. Atlasiet prognozes, kuras vēlaties pārskatīt.
   - **Prognozējamais nosaukums:** izveides laikā nodrošinātais prognozes nosaukums.
   - **Prognozes tips:** modeļa tips, ko izmanto prognozēšanai
   - **Izvades entītija:** entītijas nosaukums, kurā saglabāt prognozes izvadi. Entītiju ar šo nosaukumu var atrast **Dati** > **Entītijas**.    
     Izvades entitījā *ChurnScore* ir prognozētā zuduma iespējamība un *IsChurn* ir binārā etiķete, kas balstās *ChurnScore* ar slieksni 0.5. Noklusējuma slieksnis jūsu scenārijā varētu nedarboties. [Izveidojiet jaunu segmentu](segments.md#create-a-new-segment) ar vēlamo slieksni.
   - **Prognozējamais lauks:** šis lauks tiek aizpildīts tikai dažu veidu prognozēm, un tās netiek izmantotas abonēšanas zuduma prognozēšanā.
   - **Statuss:** prognozes izpildes pašreizējais statuss.
        - **Rindā:** prognoze pašlaik gaida citu procesu palaišanu.
        - **Atsvaidzināšana:** prognoze šobrīd darbojas apstrādes "rezultātu" posmā, lai iegūtu rezultātus, kas ieplūdīs izvades entītijā.
        - **Neizdevās:** prognozēšana nav izdevusies. Lai iegūtu detalizētu informāciju, atlasiet **Žurnāli**.
        - **Izdevās:** prognozēšana ir izdevusies. Lai pārskatītu prognozi, zem vertikālajām elipsēm atlasiet **Skatīt**
   - **Rediģēts:** Datums, kad tika mainīta prognozes konfigurācija.
   - **Pēdējā atsvaidzināšana:** Datums, kad atsvaidzinātais rezultāts ir redzams izvades entītijā.
1. Atlasiet vertikālās elipses, kas atrodas blakus prognozei, kurā vēlaties pārskatīt rezultātus, un atlasiet **Skatīt**.
   > [!div class="mx-imgBorder"]
   > ![Opciju skats, kas atrodas izvēlnē vertikālās elipses prognozēšanai, ieskaitot rediģēšanu, atsvaidzināšanu, skatīšanu, žurnālus un dzēšanu](media/subscription-churn-verticalellipses.PNG "Opciju skats, kas atrodas izvēlnē vertikālās elipses prognozēšanai, ieskaitot rediģēšanu, atsvaidzināšanu, skatīšanu, žurnālus un dzēšanu")
1. Rezultātu lapā ir trīs primāro sadaļu dati:
    1. **Apmācības modeļa veiktspēja:** iespējamie rezultāti ir A, B vai C. Šis rezultāts norāda uz prognozes izpildi un var palīdzēt pieņemt lēmumu izmantot izvades entītijā glabātos rezultātus.
        - Rezultātus nosaka, par pamatu izmantojot tālāk norādītās kārtulas:
            - **A** Ja modelis precīzi prognozēja vismaz 50% no visām prognozēm, un ja precīzo prognožu īpatsvars zudušajiem klientiem ir lielāks par vēsturisko vidējo zušanas rādītāju par vismaz 10% no vēsturiskā zuduma rādītāja.
            - **B** Ja modelis precīzi prognozēja vismaz 50% no visām prognozēm, un ja precīzo prognožu īpatsvars zudušajiem klientiem ir lielāks par vēsturisko vidējo zušanas rādītāju līdz 10% no vēsturiskā zuduma rādītāja.
            - **C** Ja modelis precīzi prognozēja mazāk nekā 50% no kopējām prognozēm vai ja precīzo prognožu īpatsvars zaudētajiem klientiem ir mazāks nekā vēsturiskais vidējais zuduma rādītājs.
               > [!div class="mx-imgBorder"]
               > ![Modeļa veiktspējas rezultāta skats](media/subscription-churn-modelperformance.PNG "Modeļa veiktspējas rezultāta skats")
    1. **Zuduma varbūtība (klientu skaits):** klientu grupas, pamatojoties uz to prognozējamo zuduma risku. Šie dati var palīdzēt vēlāk, ja vēlaties izveidot klientu segmentu ar augstu zuduma risku. Šādi segmenti palīdz saprast, kur vajadzētu būt dalībai segmentā.
       > [!div class="mx-imgBorder"]
       > ![Grafiks, kurā tiek rādīts zuduma rezultātu sadalījums, sadalīts diapazonos no 0-100%](media/subscription-churn-resultdistribution.PNG "Grafiks, kurā tiek rādīts zuduma rezultātu sadalījums, sadalīts diapazonos no 0-100%")
    1. **Ietekmīgākie faktori:** ir daudzi faktori, kas tiek ņemti vērā, veidojot jūsu prognozi. Katram no šiem faktoriem ir aprēķinātā nozīme modeļa izveidotajām apkopotajām prognozēm. Šos faktorus var izmantot, lai atvieglotu jūsu prognozes rezultātu validēšanu. Šo informāciju var izmantot arī vēlāk, lai [izveidotu segmentus](segments.md), kas varētu palīdzēt ietekmēt zuduma risku attiecībā uz klientiem.
       > [!div class="mx-imgBorder"]
       > ![Saraksts rāda svarīgākos faktorus un to nozīmi, prognozējot zuduma rezultātus](media/subscription-churn-influentialfactors.PNG "Saraksts rāda svarīgākos faktorus un to nozīmi, prognozējot zuduma rezultātus")

## <a name="fix-a-failed-prediction"></a>Neveiksmīgas prognozes labošana

1. Dodieties uz cilni **Manas prognozes** **Informācija** > **Prognozes**.
1. Atlasiet prognozi, kurai vēlaties skatīt kļūdu žurnālus, un atlasiet **Žurnāli**.
   > [!div class="mx-imgBorder"]
   > ![Rezultātu izvēļņu joslas skats, kurā ir pogas aizvērt, rediģēt modeli un žurnāli](media/subscription-churn-logsbutton.PNG "Rezultātu izvēļņu joslas skats, kurā ir pogas aizvērt, rediģēt modeli un žurnāli")
1. Pārskatīt visas kļūdas. Pastāv vairāki kļūdu tipi, kas var rasties, un tie apraksta to, kas izraisīja kļūdu. Piemēram, kļūda, ka nav pietiekami daudz datu, lai precīzi prognozētu, parasti tiek atrisināta, ielādējot papildu datus.

## <a name="refresh-a-prediction"></a>Atsvaidzināt prognozi

Prognozes tiks automātiski atsvaidzinātas ar vienu un to pašu [grafiku, ko jūsu dati atsvaidzina](system.md#schedule-tab) kā konfigurēts iestatījumos.

1. Dodieties uz cilni **Manas prognozes** **Informācija** > **Prognozes**.
1. Atlasiet vertikālās elipses, kas atrodas blakus prognozei, kuru vēlaties atsvaidzināt.
1. Atlasiet **Atsvaidzināt**.

## <a name="delete-a-prediction"></a>Dzēst prognozi

1. Dodieties uz cilni **Manas prognozes** **Informācija** > **Prognozes**.
1. Atlasiet vertikālās elipses, kas atrodas blakus prognozei, kuru vēlaties dzēst.
1. Atlasiet **Dzēst**.

> [!NOTE]
> Dzēšot prognozi, tiks noņemta tās izvades entītija.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
