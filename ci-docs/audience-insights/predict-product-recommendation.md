---
title: Produktu ieteikumu prognoze
description: Prognozējiet produktus, kurus klients, visticamāk, iegādāsies vai ar kuriem mijiedarbosies.
ms.date: 02/15/2021
ms.reviewer: zacook
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 5a2eb2b4697e51a0abb933b654a9b0b150dfa6a3
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270513"
---
# <a name="product-recommendation-prediction-preview"></a>Produktu ieteikumu prognoze (priekšskatījums)

Produktu ieteikumu modelis izveido paredzamu produktu ieteikumu kopas. Ieteikumi ir balstīti uz iepriekšējo iegādes scenāriju un klientiem ar līdzīgām iegādes shēmām. Lapā **Informācija** > **Prognozes** varat izveidot jaunus ieteikumus par produktiem. Atlasiet **Manas prognozes**, lai skatītu citas jūsu izveidotās prognozes.

Uz produktu ieteikumiem var attiekties vietējie tiesību akti un noteikumi, kā arī klientu prasības, kurām šis modelis nav domāts, lai tos īpaši ņemtu vērā.  Jums kā šīs prognozēšanas iespējas lietotājam **pirms ieteikumu piegādes klientiem jāpārskata ieteikumi**, lai nodrošinātu, ka ievērojat jebkādus atbilstošus likumus vai nosacījumus, kā arī klienta sagaidāmos ieteikumus par to, ko varat ieteikt. 

Šī modeļa izvade sniegs jums ieteikumus, pamatojoties uz produkta ID. Jūsu piegādes mehānismam būs nepieciešams ņemt vērā prognozētos produktu ID un kartēt tos atbilstoši jūsu klientiem piemērotam saturam, lai ņemtu vērā lokalizāciju, attēla saturu un citu uzņēmumam specifisko saturu vai uzvedību.

## <a name="sample-guide"></a>Rokasgrāmatas paraugs

Ja interesē šī līdzekļa izmēģināšana, taču jums nav datu, lai izpildītu tālāk norādītās prasības, varat [izveidot ieviešanas paraugu](sample-guide-predict-product-recommendation.md).

## <a name="prerequisites"></a>Priekšnosacījumi

- Vismaz [Līdzautora atļaujas](permissions.md) Customer Insights.
- Zināšanas par komercdarbību, lai izprastu dažādus jūsu uzņēmuma produktu veidus un veidu, kā klienti ar tiem sazinās. Mēs iesakām produktus, kurus klienti jau iepriekš iegādājušies, vai ieteikumus par jauniem produktiem.
- Dati par jūsu transakcijām, pirkumiem un to vēsturi:
    - Transakciju identifikatori, lai nodalītu pirkumus vai transakcijas.
    - Klientu identifikatori, lai kartētu transakcijas ar klientiem.
    - Darbības notikuma datumi, kuros definēti transakcijas datumi.
    - (Nav obligāti) Transakcijas produkta ID informācija.
    - (Nav obligāti) Ja transakcija ir vai nav atgriezta.
    - Semantiskajai datu shēmuaiir nepieciešama šāda informācija:
        - **Transakcijas ID:** Unikāls pirkšanas vai transakcijas identifikators.
        - **Darbības datums:** pirkšanas vai transakcijas datums.
        - **Darbības vērtība:** darbības vai pirkuma skaitliskās vērtības summa.
        - **Unikāls produkta ID:** produkta vai pakalpojuma ID, kas iegādāts, ja dati ir rindas elementu līmenī.
        - (Neobligāti) **Pirkt vai atgriezt:** lauks patiess/aplams, kas norāda, vai transakcija ir atgriezta vai nav. Ja **Transakcijas vērtība** ir negatīva, mēs arī izmantosim šo informāciju, lai secinātu par peļņu.


## <a name="create-a-product-recommendation-prediction"></a>Produktu ieteikumu prognozes izveide

1. Sadaļā Customer Insights dodieties uz **Informācija** > **Prognozes**.

1. Atlasiet elementu **Produktu ieteikumu modelis (priekšskatījums)** un atlasiet opciju **Lietot šo modeli**.
   > [!div class="mx-imgBorder"]
   > ![Produkta ieteikumu modeļa elements ar pogu Lietot šo modeli](media/product-recommendation-usethismodel.PNG "Produkta ieteikumu modeļa elements ar pogu Lietot šo modeli")

1. Pārskatiet informāciju par modeļa prasībām. Ja jums ir nepieciešamie dati, atlasiet **Sākt darbu**.

### <a name="name-model"></a>Nosaukuma piešķiršana modelim

1. Norādiet modeļa nosaukumu, kas atšķir to no citiem modeļiem.

1. Ievadiet izvades entītijas nosaukumu bez atstarpēm, izmantojot tikai burtus un ciparus. Tas ir nosaukums, ko izmantos modeļa entītija. Pēc tam atlasiet **Tālāk**.

### <a name="define-product-recommendation-configuration"></a>Definēt produkta ieteikumu konfigurāciju

1. Iestatiet to **Produktu skaitu**, ko vēlaties ieteikt klientam. Šī vērtība ir atkarīga no tā, kā piegādes metode aizpilda datus. Ja varat ieteikt trīs produktus, iestatiet šo vērtību atbilstoši.
   
   >[!TIP]
   > Lai saglabātu prognozēšanu kā melnrakstu, varat atlasīt **Saglabāt un aizvērt** jebkurā brīdī. Prognozes melnraksts ir atrodams cilnē **Manas prognozes**.

1. Izvēlieties, vai vēlaties **Ieteikt produktus, ko klienti nesen ir iegādājušies**.

1. Ja esat atlasījis *ne* ieteikt nesen iegādātus produktus, iestatiet logu **Atskats**. Šajā iestatījumā ir norādīts laika posms, kādu modelis apsver pirms produkta atkal ieteikšanas lietotājam. Piemēram, norādiet, ka klients iegādājas klēpjdatoru ik pēc 2 gadiem. Šajā logā tiks apskatīta pēdējo 2 gadu pirkumu vēsture un, ja tiek atrasts elements, tas tiks filtrēts no ieteikumiem.

1. Atlasiet **Tālāk**

### <a name="add-required-data"></a>Pievienot nepieciešamos datus

1. Atlasiet opciju **Pievienot datus** **Pirkumu vēsturei** un izvēlieties entītiju, kas nodrošina transakciju/pirkumu vēstures informāciju, kā aprakstīts [priekšnosacījumos](#prerequisites).

1. Kartējiet semantiskos laukus uz atribūtiem jūsu pirkumu vēstures entītijā un atlasiet **Tālāk**. Attiecībā uz lauku aprakstiem apskatiet [priekšnosacījumus](#prerequisites).
   > [!div class="mx-imgBorder"]
   > ![Entītiju relācijas definēšana](media/product-recommendation-purchasehistorymapping.PNG "Pirkumu vēstures lapa, kurā parādīti semantiskie atribūti, kas ir kartēti ar atlasītās iegādes vēstures entītijas laukiem")

1. Ja lauki nav aizpildīti, konfigurējiet savas pirkumu vēstures entītijas attiecības ar *Klienta* entītiju.
    1. Atlasiet vienumu **Pirkumu vēstures entītija**.
    1. Atlasiet vienumu **Lauks**, kas ir identificējis klientu pirkumu vēstures entītijā. Tam ir jāattiecas uz jūsu *Klienta* entītijas primāro klienta ID.
    1. Atlasiet **Klienta entītiju**, kas atbilst primārajai klienta entītijai.
    1. Ievadiet nosaukumu, kas apraksta attiecību.
       > [!div class="mx-imgBorder"]
       > ![Pirkumu vēstures lapa, kurā parādīta attiecību izveide ar klientu](media/model-purchase-join.png "Pirkumu vēstures lapa, kurā parādīta attiecību izveide ar klientu")

1. Atlasiet vienumu **Saglabāt**.

1. Atlasiet **Tālāk**.

### <a name="set-schedule-and-review-configuration"></a>Iestatiet grafiku un pārskatiet konfigurāciju

1. Lai atkārtoti apmācītu modeli, iestatiet frekvenci. Šis iestatījums ir svarīgs, lai atjauninātu prognožu precizitāti, jo jauni dati tiek importēti uz Customer Insights. Lielākā daļa uzņēmumu var pārkvalificēties reizi mēnesī un iegūt labu precizitāti to prognozēšanai.

1. Atlasiet **Tālāk**.

1. Pārskatīt konfigurāciju. Jūs varat atgriezties jebkurā prognozēšanas konfigurācijas daļā, zemāk parādītajā vērtībā atlasot **Rediģēt**. Vai arī varat atlasīt konfigurācijas soli no progresa rādītāja.

1. Ja visas vērtības ir konfigurētas pareizi, atlasiet **Saglabāt un palaist**, lai sāktu prognozēšanas procesu. Cilnē **Manas prognozes** var redzēt savu prognožu statusu. Atkarībā no prognozēšanas laikā izmantojamā datu daudzuma process var aizņemt vairākas stundas.

## <a name="review-a-prediction-status-and-results"></a>Prognozēšanas statusa un rezultātu pārskatīšana

1. Dodieties uz cilni **Manas prognozes** **Informācija** > **Prognozes**.
   > [!div class="mx-imgBorder"]
   > ![Skats lapā Manas prognozes](media/product-recommendation-mypredictions.PNG "Skats lapā Manas prognozes")

1. Atlasiet prognozes, kuras vēlaties pārskatīt.
   - **Prognozējamais nosaukums:** izveides laikā nodrošinātais prognozes nosaukums.
   - **Prognozes tips:** modeļa tips, ko izmanto prognozēšanai
   - **Izvades entītija:** entītijas nosaukums, kurā saglabāt prognozes izvadi. Entītiju ar šo nosaukumu var atrast **Dati** > **Entītijas**.
   - **Prognozētais lauks:** Šis lauks tiek aizpildīts tikai dažu veidu prognozēm, un tos neizmanto zudumu prognozē.
   - **Statuss:** prognozes izpildes pašreizējais statuss.
        - **Rindā:** prognoze pašlaik gaida citu procesu palaišanu.
        - **Atsvaidzināšana:** prognoze šobrīd darbojas apstrādes "rezultātu" posmā, lai iegūtu rezultātus, kas ieplūdīs izvades entītijā.
        - **Neizdevās:** prognozēšana nav izdevusies. Lai iegūtu detalizētu informāciju, atlasiet **Žurnāli**.
        - **Izdevās:** prognozēšana ir izdevusies. Lai pārskatītu prognozi, zem vertikālajām elipsēm atlasiet **Skatīt**
   - **Rediģēts:** Datums, kad tika mainīta prognozes konfigurācija.
   - **Pēdējā atsvaidzināšana:** Datums, kad atsvaidzinātais rezultāts ir redzams izvades entītijā.

1. Atlasiet vertikālās elipses, kas atrodas blakus prognozei, kurā vēlaties pārskatīt rezultātus, un atlasiet **Skatīt**.
   > [!div class="mx-imgBorder"]
   > ![Opciju skats, kas atrodas izvēlnē vertikālās elipses prognozēšanai, ieskaitot rediģēšanu, atsvaidzināšanu, skatīšanu, žurnālus un dzēšanu](media/product-recommendation-verticalellipses.PNG "Opciju skats, kas atrodas izvēlnē vertikālās elipses prognozēšanai, ieskaitot rediģēšanu, atsvaidzināšanu, skatīšanu, žurnālus un dzēšanu")

1. Rezultātu lapā ir trīs primāro sadaļu dati:
    1. **Apmācības modeļa veiktspēja:** iespējamie rezultāti ir A, B vai C. Šis rezultāts norāda uz prognozes izpildi un var palīdzēt pieņemt lēmumu izmantot izvades entītijā glabātos rezultātus.
        - Rezultātus nosaka, par pamatu izmantojot tālāk norādītās kārtulas:
            - **A** tiek uzskatīts par **A** kvalitātes modeli, ja metrika "Success@K" ir vismaz par 10% lielāka nekā bāzlīnija. 
            - **B** tiek uzskatīts par **B** kvalitātes modeli, ja metrika "Success@K" ir vismaz 0-10% lielāka nekā bāzlīnija.
            - **C** tiek uzskatīts par **C** kvalitātes modeli, ja metrika "Success@K" ir mazāka nekā bāzlīnija.
               
               > [!div class="mx-imgBorder"]
               > ![Modeļa veiktspējas rezultāta skats](media/product-recommendation-modelperformance.PNG "Modeļa veiktspējas rezultāta skats")
            - **Bāzlīnija**: modelī tiek ņemti vērā visbiežāk ieteicamie produkti pēc iegādes skaita visiem klientiem, un šis modelis izmanto modelī identificētās apgūtās kārtulas, lai izveidotu klientiem ieteikumu kopu. Pēc tam šīs prognozes tiek salīdzinātas ar populārākajiem produktiem, ņemot vērā klientu skaitu, kuri iegādājušies šo produktu. Ja klientam ir vismaz viens produkts starp ieteiktajiem produktiem, kas tika redzēti arī populārākajiem iegādātajiem produktiem, šis produkts tiek uzskatīts par daļu no bāzlīnijas. Ja 10 klienti no 100 kopējiem klientiem būtu iegādājušies ieteiktu produktu, bāzlīnijas vērtība būtu 10%.
            - **Sekmīgs@K**: izmantojot transakciju validācijas laika perioda kopu, ieteikumi tiek izveidoti visiem klientiem un salīdzināti ar transakciju validācijas kopu. Piemēram, 12 mēnešu periodā 12. mēnesis var tikt atlikts kā validācijas datu kopa. Ja modelis prognozē vismaz vienu lietu, ko iegādāsies 12. mēnesī, pamatojoties uz to, kas tika gūts no iepriekšējiem 11 mēnešiem, klients palielinās metriku "Success@K".
    
    1. **Lielākā daļa ieteikto produktu (ar sakritību)**: 5 labākie produkti, kas tika prognozēti klientiem.
       > [!div class="mx-imgBorder"]
       > ![Diagramma, kurā parādīti 5 labākie ieteicamie produkti](media/product-recommendation-topproducts.PNG "Diagramma, kurā parādīti 5 labākie ieteicamie produkti")
    
    1. **Ieteikumi par augsta līmeņa produktiem:** klientiem sniegto ieteikumu paraugs, kuru laikā, visticamāk, klients iegādāsies šo modeli.
       > [!div class="mx-imgBorder"]
       > ![Saraksts, kurā parādīti augsta līmeņa ieteikumi par individuālu klientu kopu](media/product-recommendation-highconfidence.PNG "Saraksts, kurā parādīti augsta līmeņa ieteikumi par individuālu klientu kopu")

## <a name="fix-a-failed-prediction"></a>Neveiksmīgas prognozes labošana

1. Dodieties uz cilni **Manas prognozes** **Informācija** > **Prognozes**.

1. Atlasiet prognozi, kurai vēlaties skatīt kļūdu žurnālus, un atlasiet **Žurnāli**.

1. Pārskatīt visas kļūdas. Pastāv vairāki kļūdu tipi, kas var rasties, un tie apraksta to, kas izraisīja kļūdu. Piemēram, kļūda, kurā nav pietiekami daudz datu, lai precīzi prognozētu, parasti tiek novērsta, ielādējot papildu datus Customer Insights.

## <a name="refresh-a-prediction"></a>Atsvaidzināt prognozi

Prognozes automātiski tiek atsvaidzinātas pēc tā paša [grafika, kad dati tiek atsvaidzināti](system.md#schedule-tab), kā tas ir konfigurēts iestatījumos.

1. Dodieties uz cilni **Manas prognozes** **Informācija** > **Prognozes**.

1. Atlasiet vertikālās elipses, kas atrodas blakus prognozei, kuru vēlaties atsvaidzināt.

1. Atlasiet **Atsvaidzināt**.

## <a name="delete-a-prediction"></a>Dzēst prognozi

Dzēšot prognozi, tiek noņemta arī tās izvades entītija.

1. Dodieties uz cilni **Manas prognozes** **Informācija** > **Prognozes**.

1. Atlasiet vertikālās elipses, kas atrodas blakus prognozei, kuru vēlaties dzēst.

1. Atlasiet **Dzēst**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]