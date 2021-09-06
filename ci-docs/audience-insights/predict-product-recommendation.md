---
title: Produktu ieteikumu prognoze
description: Prognozējiet produktus, kurus klients, visticamāk, iegādāsies vai ar kuriem mijiedarbosies.
ms.date: 03/17/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 60d511181aa85e3e939eff3e5931f0de7807c01c8f38134ebca5c5604cd53871
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034965"
---
# <a name="product-recommendation-prediction-preview"></a>Produktu ieteikumu prognoze (priekšskatījums)

Produktu ieteikumu modelis izveido paredzamu produktu ieteikumu kopas. Ieteikumi ir balstīti uz iepriekšējo iegādes scenāriju un klientiem ar līdzīgām iegādes shēmām. Lapā **Informācija** > **Prognozes** varat izveidot jaunus ieteikumus par produktiem. Atlasiet **Manas prognozes**, lai skatītu citas jūsu izveidotās prognozes.

Uz produktu ieteikumiem var attiekties vietējie tiesību akti un noteikumi, kā arī klientu prasības, kuras modelis nevar konkrēti ņemt vērā.  Kā šīs prognozēšanas iespējas lietotājam, **jums ir jāpārskata ieteikumi, pirms tos pārvirzāt saviem klientiem**, lai nodrošinātu, ka tiek ievēroti visi spēkā esošie tiesību akti un regulējumi un klientu vēlmes attiecībā uz produktu, kuru iesakāt. 

Šī modeļa izvade sniegs jums ieteikumus, pamatojoties uz produkta ID. Jūsu piegādes mehānismam būs jākartē prognozētie produktu ID uz atbilstošo saturu, lai atbilstošais saturs jūsu klientiem tiktu rādīts ievērojot lokalizāciju, attēla saturu un citu uzņēmējdarbībai raksturīgu saturu vai uzvedību.

## <a name="sample-guide"></a>Rokasgrāmatas paraugs

Ja interesē šī līdzekļa izmēģināšana, taču jums nav datu, lai izpildītu tālāk norādītās prasības, varat [izveidot ieviešanas paraugu](sample-guide-predict-product-recommendation.md).

## <a name="prerequisites"></a>Priekšnosacījumi

- Vismaz [Līdzautora atļaujas](permissions.md) Customer Insights.

- Zināšanas par komercdarbību, lai izprastu dažādus jūsu uzņēmuma produktu veidus un veidu, kā klienti ar tiem sazinās. Mēs iesakām produktus, kurus klienti jau iepriekš iegādājušies, vai ieteikumus par jauniem produktiem.

- Dati par jūsu transakcijām, pirkumiem un to vēsturi:
    - Transakciju identifikatori, lai nodalītu pirkumus vai transakcijas.
    - Klientu identifikatori, lai kartētu transakcijas ar klientiem.
    - Darbības notikuma datumi, kuros definēti transakcijas datumi.
    - Produkta ID informācija transakcijai.
    - (Neobligāti) Produktu kataloga datu vienība, lai lietotu produktu filtru.
    - (Nav obligāti) Ja transakcija ir vai nav atgriezta.
    - Semantiskajai datu shēmuaiir nepieciešama šāda informācija:
        - **Transakcijas ID:** Unikāls pirkšanas vai transakcijas identifikators.
        - **Transakcijas datums:** Pirkšanas vai transakcijas datums.
        - **Darbības vērtība:** darbības vai pirkuma skaitliskās vērtības summa.
        - **Unikāls produkta ID:** produkta vai pakalpojuma ID, kas iegādāts, ja dati ir rindas elementu līmenī.
        - (Neobligāti)**Iegāde vai atgriešana:** Būla vērtības lauka, kurā vērtība *true* norāda, ka transakcija bija atgriešana. Ja modelī netiek nodrošināti Pirkšanas vai Atgriešanas dati un **Transakcijas vērtība** ir negatīva, mēs izmantosim arī šo informāciju, lai veiktu secinājumus par atgriešanu.
- Ieteicamie datu raksturlielumi:
    - Pietiekami vēsturiskie dati: Vismaz viens gads transakcijas datu, vēlams divi vai trīs gadi, lai tiktu ietverta zināma sezonalitāte.
    - Vairāki pirkumi katram klientam: Trīs vai vairākas transakcijas vienam klienta ID
    - Klientu skaits: Vismaz 100 klientu, vēlams vairāk nekā 10 000 klientu. Ja klientu būs mazāk par 100, modelis neizdosies.

> [!NOTE]
> - Modelim ir nepieciešama jūsu klientu darījumu vēsture. Transakcijas definīcija ir diezgan elastīga. Jebkuri dati, kuri raksturo lietotāja-produkta mijiedarbību, var darboties kā ievade. Piemēram, produkta iegāde, nodarbību apmeklējums, pasākuma apmeklējums.
> - Pašlaik ir iespējams konfigurēt tikai vienu transakcijas vēstures entitīju. Ja ir vairākas pirkumu entitījas, apvienojiet tās risinājumā Power Query, pirms veicat datu uzņemšanu.
> - Ja pasūtījums un pasūtījuma informācija ir atšķirīgas entitījas, pirms lietošanas modelī tās apvienojiet. Modelis nedarbojas tikai ar entitījas pasūtījuma ID vai kvīts ID.


## <a name="create-a-product-recommendation-prediction"></a>Produktu ieteikumu prognozes izveide

1. Sadaļā Customer Insights dodieties uz **Informācija** > **Prognozes**.

1. Atlasiet elementu **Produktu ieteikumu modelis (priekšskatījums)** un atlasiet opciju **Lietot šo modeli**.
   > [!div class="mx-imgBorder"]
   > ![Produkta ieteikumu modeļa elements ar pogu Lietot šo modeli.](media/product-recommendation-usethismodel.PNG "Produkta ieteikumu modeļa elements ar pogu Lietot šo modeli")

1. Pārskatiet informāciju par modeļa prasībām. Ja jums ir nepieciešamie dati, atlasiet **Sākt darbu**.

### <a name="name-model"></a>Nosaukuma piešķiršana modelim

1. Norādiet modeļa nosaukumu, kas atšķir to no citiem modeļiem.

1. Ievadiet izvades entītijas nosaukumu bez atstarpēm, izmantojot tikai burtus un ciparus. Tas ir nosaukums, ko izmantos modeļa entītija. Pēc tam atlasiet **Tālāk**.

### <a name="define-product-recommendation-configuration"></a>Definēt produkta ieteikumu konfigurāciju

1. Iestatiet to **Produktu skaitu**, ko vēlaties ieteikt klientam. Šī vērtība ir atkarīga no tā, kā piegādes metode aizpilda datus. Ja varat ieteikt trīs produktus, iestatiet šo vērtību atbilstoši.
   
   >[!TIP]
   > Lai saglabātu prognozēšanu kā melnrakstu, varat atlasīt **Saglabāt un aizvērt** jebkurā brīdī. Prognozes melnraksts ir atrodams cilnē **Manas prognozes**.

1. Izvēlieties, vai vēlaties **Ieteikt produktus, ko klienti nesen ir iegādājušies**.

1. Ja esat atlasījis *ne* ieteikt nesen iegādātus produktus, iestatiet logu **Atskats**. Šajā iestatījumā ir norādīts laika posms, kādu modelis apsver pirms produkta atkal ieteikšanas lietotājam. Piemēram, norādiet, ka klients reizi divos gados iegādājas klēpjdatoru. Šis logs aplūkos pirkumu vēsturi pēdējos divos gados, un, ja tiks atrasts produkts, tas tiks filtrēts no ieteikumiem.

1. Atlasiet **Tālāk**

### <a name="add-required-data"></a>Pievienot nepieciešamos datus

1. Atlasiet opciju **Pievienot datus** **Pirkumu vēsturei** un izvēlieties entītiju, kas nodrošina transakciju/pirkumu vēstures informāciju, kā aprakstīts [priekšnosacījumos](#prerequisites).

1. Kartējiet semantiskos laukus uz atribūtiem jūsu pirkumu vēstures entītijā un atlasiet **Tālāk**. Attiecībā uz lauku aprakstiem apskatiet [priekšnosacījumus](#prerequisites).
   > [!div class="mx-imgBorder"]
   > ![Entītiju relācijas definēšana.](media/product-recommendation-purchasehistorymapping.PNG "Pirkumu vēstures lapa, kurā parādīti semantiskie atribūti, kas ir kartēti ar atlasītās iegādes vēstures entītijas laukiem")

1. Ja lauki nav aizpildīti, konfigurējiet savas pirkumu vēstures entītijas attiecības ar *Klienta* entītiju.
    1. Atlasiet vienumu **Pirkumu vēstures entītija**.
    1. Atlasiet vienumu **Lauks**, kas ir identificējis klientu pirkumu vēstures entītijā. Tam ir jāattiecas uz jūsu *Klienta* entītijas primāro klienta ID.
    1. Atlasiet **Klienta entītiju**, kas atbilst primārajai klienta entītijai.
    1. Ievadiet nosaukumu, kas apraksta attiecību.
       > [!div class="mx-imgBorder"]
       > ![Pirkumu vēstures lapa, kurā parādīta attiecību izveide ar klientu.](media/model-purchase-join.png "Pirkumu vēstures lapa, kurā parādīta attiecību izveide ar klientu")

1. Atlasiet vienumu **Saglabāt**.

1. Atlasiet **Tālāk**.

### <a name="configure-product-filters"></a>Produktu filtru konfigurēšana

Reizēm noderīgi vai jūsu veidotajam prognozes veidam piemēroti ir tikai noteikti produkti. Produktu filtri ļauj identificēt produktu kopu ar īpašiem raksturlielumiem, kurus varat ieteikt saviem klientiem. Modelis ir izmantos visus pieejamos produktus, lai apgūtu modeļus, taču savā izvadē izmantos vienīgi produktu filtram atbilstošos produktus.

1. Darbībā **Pievienot produkta informāciju** pievienojiet savu preču katalogu ar informāciju par katru produktu. Kartējiet nepieciešamo informāciju un atlasiet **Tālāk**.

3. Darbībā **Produktu filtri** izvēlieties no šīm opcijām.

   * **Nav filtru**: Prognozē lietojiet visus produkta ieteikuma produktus.

   * **Definēt konkrētus produktu filtrus**: Produkta ieteikuma prognozē izmantojiet konkrētus produktus.

1. Atlasiet **Tālāk**.

1. Ja izvēlaties definēt produkta filtru, tas ir jādefinē nekavējoties. Rūtī **Produktu kataloga atribūti** atlasiet atribūtus no savas *Produktu kataloga entitījas*, kurus vēlaties iekļaut filtrā.

   :::image type="content" source="media/product-filters-sidepane.png" alt-text=" Sānu rūts, kurā redzami produktu kataloga entitījas atribūti, kurus atlasīt produktu filtriem.":::

1. Izvēlieties, vai vēlaties, lai produkta filtrs izmanto savienotājus **un** vai **vai**, lai loģiski saistītu jūsu atribūtu atlasi no produktu kataloga.
   
   :::image type="content" source="media/product-filters-sample.png" alt-text="Preču filtru konfigurācijas paraugs apvienojumā ar loģiskajiem AND savienotājiem.":::

1. Atlasiet **Tālāk**.

### <a name="set-update-schedule-and-review-configuration"></a>Atjaunināšanas grafika iestatīšana un konfigurācijas pārskatīšana

1. Lai atkārtoti apmācītu modeli, iestatiet frekvenci. Šis iestatījums ir svarīgs, lai atjauninātu prognožu precizitāti, jo jauni dati tiek importēti uz Customer Insights. Lielākā daļa uzņēmumu var pārkvalificēties reizi mēnesī un iegūt labu precizitāti to prognozēšanai.

1. Atlasiet **Tālāk**.

1. Pārskatīt konfigurāciju. Jūs varat atgriezties jebkurā prognozēšanas konfigurācijas daļā, zemāk parādītajā vērtībā atlasot **Rediģēt**. Vai arī varat atlasīt konfigurācijas soli no progresa rādītāja.

1. Ja visas vērtības ir konfigurētas pareizi, atlasiet **Saglabāt un palaist**, lai sāktu prognozēšanas procesu. Cilnē **Manas prognozes** var redzēt savu prognožu statusu. Atkarībā no prognozēšanas laikā izmantojamā datu daudzuma process var aizņemt vairākas stundas.

## <a name="review-a-prediction-status-and-results"></a>Prognozēšanas statusa un rezultātu pārskatīšana

1. Dodieties uz cilni **Manas prognozes** **Informācija** > **Prognozes**.
   > [!div class="mx-imgBorder"]
   > ![Skats lapā Manas prognozes.](media/product-recommendation-mypredictions.PNG "Skats lapā Manas prognozes")

1. Atlasiet prognozes, kuras vēlaties pārskatīt.
   - **Prognozējamais nosaukums:** izveides laikā nodrošinātais prognozes nosaukums.
   - **Prognozes tips:** modeļa tips, ko izmanto prognozēšanai
   - **Izvades entītija:** entītijas nosaukums, kurā saglabāt prognozes izvadi. Entītiju ar šo nosaukumu var atrast **Dati** > **Entītijas**.    
      *Rezultāts* izlaides entitīja ir ieteikuma kvantitatīvais rādītājs. Modelis iesaka produktus ar augstāku rezultātu iepretim produktiem, kuru rezultāts ir zemāks.
   - **Prognozētais lauks:** Šis lauks tiek aizpildīts vienīgi dažiem prognožu veidiem, un to nelieto produkta ieteikuma prognozē.
   - **Statuss:** prognozes izpildes pašreizējais statuss.
        - **Rindā:** prognoze pašlaik gaida citu procesu palaišanu.
        - **Atsvaidzināšana:** prognoze šobrīd darbojas apstrādes "rezultātu" posmā, lai iegūtu rezultātus, kas ieplūdīs izvades entītijā.
        - **Neizdevās:** prognozēšana nav izdevusies. Lai iegūtu detalizētu informāciju, atlasiet **Žurnāli**.
        - **Izdevās:** prognozēšana ir izdevusies. Lai pārskatītu prognozi, zem vertikālajām elipsēm atlasiet **Skatīt**
   - **Rediģēts:** Datums, kad tika mainīta prognozes konfigurācija.
   - **Pēdējā atsvaidzināšana:** Datums, kad atsvaidzinātais rezultāts ir redzams izvades entītijā.

1. Atlasiet vertikālās elipses, kas atrodas blakus prognozei, kurā vēlaties pārskatīt rezultātus, un atlasiet **Skatīt**.
   > [!div class="mx-imgBorder"]
   > ![Opciju skats, kas atrodas izvēlnē vertikālās elipses prognozēšanai, ieskaitot rediģēšanu, atsvaidzināšanu, skatīšanu, žurnālus un dzēšanu.](media/product-recommendation-verticalellipses.PNG "Opciju skats, kas atrodas izvēlnē vertikālās elipses prognozēšanai, ieskaitot rediģēšanu, atsvaidzināšanu, skatīšanu, žurnālus un dzēšanu")

1. Rezultātu lapai ir piecas galvenās datu sadaļas:
    1. **Apmācības modeļa veiktspēja:** iespējamie rezultāti ir A, B vai C. Šis rezultāts norāda uz prognozes izpildi un var palīdzēt pieņemt lēmumu izmantot izvades entītijā glabātos rezultātus.
        - Rezultātus nosaka, par pamatu izmantojot tālāk norādītās kārtulas:
            - **A** tiek uzskatīts par **A** kvalitātes modeli, ja metrika "Success@K" ir vismaz par 10% lielāka nekā bāzlīnija. 
            - **B** tiek uzskatīts par **B** kvalitātes modeli, ja metrika "Success@K" ir vismaz 0-10% lielāka nekā bāzlīnija.
            - **C** tiek uzskatīts par **C** kvalitātes modeli, ja metrika "Success@K" ir mazāka nekā bāzlīnija.
               
               > [!div class="mx-imgBorder"]
               > ![Modeļa veiktspējas rezultāta skats.](media/product-recommendation-modelperformance.PNG "Modeļa veiktspējas rezultāta skats")
            - **Bāzlīnija**: modelī tiek ņemti vērā visbiežāk ieteicamie produkti pēc iegādes skaita visiem klientiem, un šis modelis izmanto modelī identificētās apgūtās kārtulas, lai izveidotu klientiem ieteikumu kopu. Pēc tam šīs prognozes tiek salīdzinātas ar populārākajiem produktiem, ņemot vērā klientu skaitu, kuri iegādājušies šo produktu. Ja klientam ir vismaz viens produkts starp ieteiktajiem produktiem, kas tika redzēti arī populārākajiem iegādātajiem produktiem, šis produkts tiek uzskatīts par daļu no bāzlīnijas. Ja 10 klienti no 100 kopējiem klientiem būtu iegādājušies ieteiktu produktu, bāzlīnijas vērtība būtu 10%.
            - **Sekmīgs@K**: izmantojot transakciju validācijas laika perioda kopu, ieteikumi tiek izveidoti visiem klientiem un salīdzināti ar transakciju validācijas kopu. Piemēram, 12 mēnešu periodā 12. mēnesis var tikt atlikts kā validācijas datu kopa. Ja modelis prognozē vismaz vienu lietu, ko iegādāsies 12. mēnesī, pamatojoties uz to, kas tika gūts no iepriekšējiem 11 mēnešiem, klients palielinās metriku "Success@K".
    
    1. **Visvairāk ieteiktie produkti (ar rēķinu):** Pieci galvenie klientiem prognozētie produkti.
       > [!div class="mx-imgBorder"]
       > ![Diagramma, kurā parādīti 5 labākie ieteicamie produkti.](media/product-recommendation-topproducts.PNG "Diagramma, kurā parādīti 5 labākie ieteicamie produkti")
    
    1. **Ieteikšanas galvenie faktori:** Lai sniegtu produktu ieteikumus, modelis pielieto klienta transakciju vēsturi. Tas apgūst modeļus, balstoties iepriekšējos pirkumos, un atrod līdzības starp klientiem un produktiem. Pēc tam šīs līdzības tiek izmantotas, lai ģenerētu produktu ieteikumus.
    Zemāk ir uzskaitīti faktori, kuri var ietekmēt modeļa ģenerēto produkta ieteikumu. 
        - **Iepriekšējās transakcijas**: Modelis izmantoja iepriekšējo pirkumu modeļus, lai ģenerētu produkta ieteikumus. Piemēram, modelis var ieteikt _Surface peli_, ka kāds nesen iegādājies _Surface grāmatu 3_ un _Surface pildspalvu_. Modelis ieguva informāciju, ka daudzi klienti iepriekš ir pēc _Surface grāmatas 3_ un _Surface pildspalvas_ iegādes ir iegādājušies _Surface peli_.
        - **Klientu līdzība**: Ieteikto produktu iepriekš iegādājušies citi klienti ar līdzīgiem pirkšanas modeļiem. Piemēram, Džonam tika ieteiktas _Surface austiņas 2_, jo Dženifera un Breds nesen iegādājās _Surface austiņas 2_. Modelis uzskata, ka Džons ir līdzīgs Dženiferai un Bredam, jo viņiem iepriekš bijuši līdzīgi pirkšanas paradumi.
        - **Produktu līdzība**: Ieteicamais produkts ir līdzīgs citiem produktiem, kurus klients iepriekš bija iegādājies. Modelis uzskata, ka divi ražojumi ir līdzīgi, ja tie tika iegādāti kopā vai ja tos iegādājās līdzīgi klienti. Piemēram, kādam tiek ieteikts _USB atmiņas disks_, jo šī persona iepriekš iegādājās _Adapteru no USB-C uz USB_ un modelis uzskata, ka produkts _USB atmiņas disks_ ir līdzīgs produktam _Adapters no USB-C uz USB_.

        Katru produkta ieteikumu ietekmē viens vai vairāki no šiem faktoriem. Ieteikumu procentuālā daļa, kurā nozīme bija katram no faktoriem, ir attēlota diagrammā. Šajā piemērā 100% ieteikumu ietekmēja iepriekšējās transakcijas, 60% — klientu līdzība un 22% — produktu līdzība. Pārvelciet kursoru pāri diagrammas joslām, lai aplūkotu precīzu procentuālo daļu, kurā bijusi nozīme katram no faktoriem.

        > [!div class="mx-imgBorder"]
        > ![Galvenie ieteikumu faktori.](media/product-recommendation-keyrecommendationfactors.png "Galvenie modeļa apgūtie ieteikumu faktori produktu rekomendāciju ģenerēšanai")
       
     
   1. **Datu statistika** : Sniedz pārskatu par modeļa izmantoto transakciju, klientu un preču skaitu. Tā balstās ievades datos, kuri tika izmantoti, lai apgūtu modeļus un ģenerētu produktu ieteikumus.

      > [!div class="mx-imgBorder"]
      > ![Datu statistika.](media/product-recommendation-datastatistics.png "Datu statistika par modeļa izmantotajiem ievades datiem modeļu apgūšanai")

      Šajā sadaļā ir redzama statistika par datu punktiem, kurus modelis izmantoja, lai apgūtu modeļus un ģenerētu produktu ieteikumus. Filtrēšana, saskaņā ar modeļa konfigurāciju, tiks piemērota modeļa ģenerētajai izvadei. Taču modeļu apgūšanā modelis izmanto visus pieejamos datus. Tāpēc, ja modeļa konfigurācijā lietojat produkta filtrēšanu, šī sadaļa parādīs kopējo modeļa analizēto produktu skaitu, lai tiktu apgūti modeļi, un šis skaits var atšķirties no to produktu skaita, kuri atbilst definētajiem filtrēšanas kritērijiem.

   1. **Ieteikumi par augsta līmeņa produktiem:** klientiem sniegto ieteikumu paraugs, kuru laikā, visticamāk, klients iegādāsies šo modeli.    
      Ja tiek pievienots produktu katalogs, produkta ID nomaina pret produkta nosaukumiem. Produktu nosaukumi sniedz izmantojamāku un intuitīvāku informāciju par prognozēm.
       > [!div class="mx-imgBorder"]
       > ![Saraksts, kurā parādīti augsta līmeņa ieteikumi par individuālu klientu kopu.](media/product-recommendation-highconfidence.PNG "Saraksts, kurā parādīti augsta līmeņa ieteikumi par individuālu klientu kopu")

## <a name="manage-predictions"></a>Pārvaldīt prognozes

Ir iespējams optimizēt, novērst problēmas, atsvaidzināt vai dzēst prognozes. Pārskatiet ievades datu lietojamības ziņojumu, lai uzzinātu, kā padarīt prognozi ātrāku un uzticamāku. Papildinformāciju skatiet šeit: [Prognožu pārvaldība](manage-predictions.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
