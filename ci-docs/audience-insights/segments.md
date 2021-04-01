---
title: Izveidojiet un pārvaldiet segmentus
description: Izveidojiet klientiem segmentus, lai tos grupētu, pamatojoties uz dažādiem atribūtiem.
ms.date: 03/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 4a6e8a3216a2c0738d60247054afa9fc18412f55
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597061"
---
# <a name="create-and-manage-segments"></a>Izveidojiet un pārvaldiet segmentus

Segmenti jums ļauj sagrupēt klientus, pamatojoties uz demogrāfiskajiem, transakciju vai uzvedības atribūtiem. Lai sasniegtu uzņēmuma mērķus, var izmantot segmentus, lai mērķētu reklāmas kampaņas, pārdošanas darbības un klientu atbalsta darbības.

Varat definēt sarežģītus filtrus ap klienta profila entītiju un to saistītajām entītijām. Katrs segments pēc apstrādes izveido klientu ierakstu kopu, ko var eksportēt un ar kurām veikt darbības. Ir [spēkā noteikti pakalpojuma ierobežojumi](service-limits.md).

Ja vien nav norādīts citādi, visi segmenti ir **dinamiski segmenti**, kas tiek atsvaidzināti periodiskā grafikā.

Šajā piemērā ir aprakstīta segmentācijas iespēja. Mēs esam definējuši segmentu klientiem, kuri pēdējo 90 dienu laikā ir pasūtījuši preces vismaz 500$ vērtībā *un* ir bijuši iesaistīti aktualizēta klientu apkalpošanas zvanā.

> [!div class="mx-imgBorder"]
> ![Vairākas grupas](media/segmentation-group1-2.png "Vairākas grupas")

## <a name="create-a-new-segment"></a>Izveidot jaunu segmentu

Segmenti tiek pārvaldīti lapā **Segmenti**.

1. Sadaļā Auditorijas ieskati ejiet uz lapu **Segmenti**.

1. Atlasiet **Jauns** > **Tukšs segments**.

1. Rūtī **Jauns segments** izvēlieties segmenta tipu un ievadiet **nosaukumu**.

   Ja vēlaties, norādiet parādāmo nosaukumu un aprakstu, kas palīdz identificēt segmentu.

1. Noklikšķiniet uz **Tālāk**, lai piekļūtu lapai **Segmenta veidotājs**, kurā definējat grupu. Grupa ir klientu kopa.

1. Izvēlieties entītiju, kurā iekļauts atribūts, pēc kura vēlaties segmentēt.

1. Atlasiet atribūtu, pēc kura segmentēt. Šim atribūtam var būt viens no četriem vērtību veidiem: skaitlis, virkne, datums vai Būla vērtība.

1. Izvēlieties operatoru un vērtību atlasītajam atribūtam.

   > [!div class="mx-imgBorder"]
   > ![Pielāgots grupas filtrs](media/customer-group-numbers.png "Klientu grupas filtrs")

   |Numurs |Definīcija  |
   |---------|---------|
   |1     |Entītija          |
   |2     |Atribūts          |
   |3    |Operators         |
   |4    |Vērtība         |

8. Ja entītija ir savienota ar vienotā klienta entītiju, izmantojot [relācijas](relationships.md), ir jādefinē relāciju ceļš, lai izveidotu derīgu segmentu. Pievienojiet entītijas no attiecību ceļa, līdz varat nolaižamajā sarakstā atlasīt entitīju **Klients: CustomerInsights**. Pēc tam katram nosacījumam izvēlieties **Visi ieraksti**.

   > [!div class="mx-imgBorder"]
   > ![Relāciju ceļš segmenta izveides laikā](media/segments-multiple-relationships.png "Relāciju ceļš segmenta izveides laikā")

1. Pēc noklusējuma segmenti ģenerē izvades entītiju, kurā ir visi klientu profilu atribūti, kas atbilst definētajiem filtriem. Ja segments ir balstīts uz citām entītijām, nevis entītiju *Klients*, izvades entītijai var pievienot papildu atribūtus no šīm entītijām. Atlasiet **Projekta atribūtus**, lai izvēlētos atribūtus, kas tiks pievienoti izvades entītijai.  

   
   Piemērs. Segments tiek veidots, pamatojoties uz entītiju, kurā ir ietverti ar entītiju *Klients* saistīti klienta darbības dati. Segments meklē visus klientus, kas pēdējo 60 dienu laikā zvanījuši palīdzības dienestam. Varat izvēlēties, vai izvades entītijā pievienot sarunas ilgumu un zvanu skaitu visiem atbilstošajiem klientu ierakstiem. Šī informācija var būt noderīga lai nosūtītu e-pasta ziņojumu ar noderīgām saitēm uz tiešsaistes palīdzības rakstiem un bieži uzdotajiem jautājumiem tiem klientiem, kuri zvanījuši bieži.

1. Lai saglabātu segmentu, atlasiet **Saglabāt**. Jūsu segments tiks saglabāts un apstrādāts, ja visas prasības ir validētas. Pretējā gadījumā tas tiks saglabāts kā melnraksts.

1. Atlasiet **Atgriezties pie segmentiem**, lai atgrieztos pie **Segmentu** lapas.

## <a name="manage-existing-segments"></a>Esošo segmentu pārvaldība

Lapā **Segmenti** var apskatīt visus saglabātos segmentus un pārvaldīt tos.

Katru segmentu apzīmē rinda, kurā ir iekļauta papildu informācija par segmentu.

Segmentus var kārtot kolonnā, atlasot kolonnas virsrakstu.

Lai filtrētu segmentus, labajā augšējā stūrī atlasiet lodziņu **Meklēt**.

> [!div class="mx-imgBorder"]
> ![Esoša segmenta pārvaldīšanas opcijas](media/segments-selected-segment.png "Esoša segmenta pārvaldīšanas opcijas")

Kad atlasāt segmentu, ir pieejamas tālāk norādītās darbības:

- **Skatīt** segmenta informāciju, tostarp segmenta dalībnieku skaita tendences priekšskatījumu.
- **Rediģēt** segmentu, lai mainītu tā rekvizītus.
- **Izveidot dublikātu** segmentam. Varat izvēlēties rediģēt tā rekvizītus uzreiz vai vienkārši saglabāt dublikātu.
- **Atsvaidzināt** segmentu, lai iekļautu jaunākos datus.
- **Aktivizēt** vai **Deaktivizēt** segmentu. Segmentiem ir divi iespējamie statusi — aktīvs vai neaktīvs. Šie statusi ir noderīgi, rediģējot segmentu. Neaktīvajiem segmentiem pastāv segmenta definīcija, taču tajā vēl nav klientu. Aktivizējot segmentu, tā statuss tiek mainīts no “neaktīvs” uz “aktīvs”, un tas sāk meklēt klientus, kas atbilst segmenta definīcijai. Ja ir konfigurēta [plānotā atsvaidzināšana](system.md#schedule-tab), neaktīvajiem segmentiem **Statuss** ir norādīts kā **Izlaists**, kas norāda, ka atsvaidzināšana nav pat mēģināta. Ja ir aktivizēts neaktīvs segments, tas tiek atsvaidzināts un iekļauts atsvaidzināšanas grafikā.
  Vai arī varat izmantot funkcionalitāti **Plānot vēlāk** nolaižamajā izvēlnē **Aktivizēt/Deaktivizēt**, lai norādītu nākotnes datumu un laiku noteikta segmenta aktivizēšanai un deaktivizēšanai.
- **Pārdēvēt** segmentu.
- **Lejupielādēt** dalībnieku sarakstu kā .CSV failu.
- Opcija **Pievienot** nosūta segmenta klientu ID sarakstu apstrādei citā programmā.
- **Dzēst** segmentu.

## <a name="refresh-segments"></a>Atsvaidzināt segmentus

Visus segmentus uzreiz var atsvaidzināt, atlasot **Atsvaidzināt visus** lapā **Segmenti**, vai varat atsvaidzināt vienu vai vairākus segmentus, tos atlasot un izvēloties opciju **Atsvaidzināt** no piedāvātajām opcijām. Vai arī varat konfigurēt periodisku atsvaidzināšanu sadaļā **Administrators** > **Sistēma** > **Grafiks**.

> [!TIP]
> Uzdevumiem/procesiem ir [seši statusu tipi](system.md#status-types). Turklāt vairums procesu [ir atkarīgi no citiem pakārtotiem procesiem](system.md#refresh-policies). Varat atlasīt procesa statusu, lai skatītu detalizētu informāciju par visa uzdevuma norisi. Pēc tam, kad vienam no darba uzdevumiem esat atlasījis **Skatīt detalizētu informāciju**, jūs redzēsit papildinformāciju: apstrādes laiku, pēdējās apstrādes datumu un visas kļūdas un brīdinājumus, kas saistīti ar uzdevumu.

## <a name="download-and-export-segments"></a>Segmentu lejupielāde un eksportēšana

Varat lejupielādēt segmentus CSV failā vai tos eksportēt uz Dynamics 365 Sales.

### <a name="download-segments-to-a-csv-file"></a>Segmentu lejupielāde CSV failā

1. Sadaļā Auditorijas ieskati ejiet uz lapu **Segmenti**.

2. Noteiktā segmenta elementā atlasiet daudzpunkti.

3. Nolaižamajā darbību sarakstā atlasiet **Lejupielādēt kā CSV**.

### <a name="export-segments-to-dynamics-365-sales"></a>Segmentu eksportēšana programmā Dynamics 365 Sales

Pirms segmentu eksportēšanas programmā Dynamics 365 Sales, administratoram ir [jāizveido eksportēšanas galamērķis](export-destinations.md) programmai Dynamics 365 Sales.

1. Sadaļā Auditorijas ieskati ejiet uz lapu **Segmenti**.

2. Noteiktā segmenta elementā atlasiet daudzpunkti.

3. Darbību nolaižamajā sarakstā atlasiet **Pievienot** un atlasiet eksporta galamērķi, uz kuru vēlaties nosūtīt datus.

## <a name="draft-mode-for-segments"></a>Melnraksta režīms segmentiem

Ja netiek izpildītas visas segmenta apstrādes prasības, segmentu var saglabāt kā melnrakstu, lai to varētu izmantot lapā **Segmenti**.

Tas tiks saglabāts kā neaktīvs segments, un to nevar aktivizēt, kamēr tas nav derīgs.

## <a name="add-more-conditions-to-a-group"></a>Papildu nosacījumu pievienošana grupai

Lai grupai pievienotu papildu nosacījumus, varat izmantot divus loģiskos operatorus:

- **UN** operators: Ir jāizpilda abi nosacījumi kā daļa no segmentācijas procesa. Šī opcija ir visnoderīgākā, kad definējat nosacījumus dažādās entītijās.

- **Vai** operators: Viens vai otrs no nosacījumiem ir jāizpilda kā segmentācijas procesa daļa. Šī opcija ir visnoderīgākā, kad definējat vairākus nosacījumus vienai entītijai.

   > [!div class="mx-imgBorder"]
   > ![VAI operators, ja kāds no nosacījumiem ir jāizpilda](media/segmentation-either-condition.png "VAI operators, ja kāds no nosacījumiem ir jāizpilda")

Pašlaik ir iespējams ligzdot **VAI** operatoru, izmantojot operatoru **UN**, bet ne otrādi.

## <a name="combine-multiple-groups"></a>Vairāku grupu apvienošana

Katra grupa veido noteiktu klientu kopu. Varat apvienot šīs grupas, lai tās iekļautu jūsu biznesa pieteikumam nepieciešamos klientus.

1. Sadaļā auditorijas ieskati atveriet lapu **Segmenti** un atlasiet segmentu.

2. Atlasiet **Pievienot grupu**.

   > [!div class="mx-imgBorder"]
   > ![Klientu grupu pievienošanas grupa](media/customer-group-add-group.png "Klientu grupu pievienošanas grupa")

3. Atlasiet vienu no tālāk minētajiem kopu operatoriem: **Savienība**, **Pārklāšanās** vai **Atskaitīšana**.

   > [!div class="mx-imgBorder"]
   > ![Klientu grupu pievienošanas apvienošana](media/customer-group-union.png "Klientu grupu pievienošanas apvienošana")

   Atlasiet iestatīto operatoru, lai definētu jaunu grupu. Saglabājiet dažādas grupas, lai noteiktu, kādus datus uzturēt:

   - **Apvienot** apvieno divas grupas.

   - **Izveidot krustpunktu** pārklāj divas grupas. Vienotajā grupā tiek saglabāti tikai tie dati, kas ir *kopēji* abām grupām.

   - **Izņemot** apvieno divas grupas. Tiek saglabāti tikai A grupas dati, kas *nav kopēji* B grupas datiem.

## <a name="view-processing-history-and-segment-members"></a>Apstrādes vēstures un segmentu elementu skatīšana

Lai skatītu apkopotos datus par segmentu, pārskatot informāciju par segmentu.

Lapā **Segmenti** atlasiet segmentu, kuru vēlaties pārskatīt.

Lapas augšējā daļa ietver tendenču grafiku, kas vizualizē elementu skaita izmaiņas. Norādiet uz datu punktiem, lai skatītu elementu skaitu noteiktā datumā.

Varat atjaunināt vizualizācijas laika periodu.

> [!div class="mx-imgBorder"]
> ![Segmenta laika diapazons](media/segment-time-range.png "Segmenta laika diapazons")

Apakšējā daļa ietver segmenta elementu sarakstu.

> [!NOTE]
> Šajā sarakstā parādītie lauki tiek balstīti uz segmenta entītiju atribūtiem.
>
>Saraksts ir atbilstošo segmenta dalībnieku priekšskatījums un parāda jūsu segmenta pirmos 100 ierakstus, lai to varētu ātri novērtēt un vajadzības gadījumā pārskatīt tā definīcijas. Lai skatītu visus atbilstošos ierakstus, ir [jāeksportē šis segments](export-destinations.md).

## <a name="quick-segments"></a>Ātrie segmenti

Papildus segmenta veidotājam ir vēl viens segmentu izveides ceļš. Ātrie segmenti ļauj veidot vienkāršus segmentus (ar vienu operatoru) ātri un ar tūlītējiem ieskatiem.

1. Lapā **Segmenti** atlasiet vienumu **Jauns** > **Ātri izveidot no**.

   - Atlasiet opciju **Profili**, lai izveidotu segmentu, kura pamatā ir vienotā klienta entītija.
   - Atlasiet opciju **Pasākumi**, lai izveidotu segmentu ap katru klientu atribūtu tipu pasākumiem, kas iepriekš izveidoti lapā **Pasākumi**.
   - Atlasiet opciju **Informācijas apkopošana**, lai izveidotu segmentu ap vienu no izvades entitījām, kuras izveidojāt, izmantojot iespēju **Prognozes** vai **Pielāgotie modeļi**.

2. Dialoglodziņā **Jauns ātrais segments** atlasiet atribūtu no nolaižamā saraksta **Lauks**.

3. Sistēma sniegs papildu ieskatus, kas palīdz izveidot labākus klientu segmentus.
   - Attiecībā uz kategoriju laukiem mēs parādīsim 10 lielāko klientu skaitu. Izvēlieties **Vērtība** un atlasiet **Pārskatīt**.

   - Skaitliskam atribūtam sistēma parādīs, kāda atribūta vērtība atbilst katra klienta procentīlei. Izvēlieties **Operators** un **Vērtība** un pēc tam atlasiet vienumu **Pārskatīt**.

4. Sistēma nodrošinās jūs ar **Aptuveniem segmenta izmēriem**. Varat izvēlēties, vai ģenerēt definēto segmentu, vai arī to vispirms pārskatīt, lai iegūtu citu segmenta lielumu.

    > [!div class="mx-imgBorder"]
    > ![Ātrā segmenta nosaukums un novērtējums](media/quick-segment-name.png "Ātrā segmenta nosaukums un novērtējums")

5. Norādiet segmenta **Nosaukumu**. Vai ari norādiet **Parādāmo vārdu**.

6. Lai izveidotu segmentu, atlasiet opciju **Saglabāt**.

7. Pēc tam, kad segments ir pabeidzis apstrādi, to var apskatīt tāpat kā jebkuru citu izveidoto segmentu.

Tālāk norādītajiem scenārijiem ieteicams izmantot segmentu veidotāju, nevis ieteikto segmentu iespējas:

- Segmentu izveide ar filtriem kategoriskos laukos, kuros operators ir citādāks nekā **Ir**.
- Segmentu izveide, izmantojot filtrus skaitliskos laukos kuros operators ir atšķirīgs no **Starp**, **Lielāks par** un **Mazāks par** operatoriem.
- Segmentu izveide ar filtriem datuma veida laukos

## <a name="next-steps"></a>Nākamās darbības

[Eksportējiet segmentu](export-destinations.md) un izpētiet [Klienta karti](customer-card-add-in.md) un [Savienotājus](export-power-bi.md), lai gūtu ieskatu klientu līmenī.


[!INCLUDE[footer-include](../includes/footer-banner.md)]