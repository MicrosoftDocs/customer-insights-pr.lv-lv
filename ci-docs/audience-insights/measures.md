---
title: Mēru izveide un rediģēšana
description: Definējiet ar klientiem saistītus mērus, lai analizētu un atspoguļotu noteiktu uzņēmējdarbības jomu veiktspēju.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: wameng
manager: shellyha
ms.openlocfilehash: 0e214a6eb66abd27f7292db3ce2c2a6e16a8ff33
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406363"
---
# <a name="define-and-manage-measures"></a>Definējiet un pārvaldiet mērus

**Mēri** attiecas uz izpildes pamatrādītājiem (KPI), kas atspoguļo noteiktu uzņēmējdarbības jomu veiktspēju un darbības efektivitāti. Auditorijas ieskati nodrošina intuitīvu pieredzi dažādu tipu pasākumu veidošanā, izmantojot vaicājumu veidotāju, kuram nav nepieciešams manuāli piešķirt kodeksu vai validēt pasākumus. Varat izsekot savus uzņēmējdarbības mērus **sākumlapā**, skatīt konkrētu klientu mērus **klienta kartē** un izmantot mērus klientu segmentu definēšanai lapā **Segmenti**.

## <a name="create-a-measure"></a>Mēra izveide

Šajā sadaļā ir izklāstīts, kā izveidot mērus no jauna. Varat izveidot mērus, izmantojot datus no vairākiem datu avotiem, kas ir saistīti, izmantojot entītiju Klients. Ir [spēkā noteikti pakalpojuma ierobežojumi](service-limits.md).

1. Sadaļā Auditorijas ieskati ejiet uz **Mēri**.

2. Atlasiet **Jauns mērs**.

3. Izvēlieties mēra **tipu**.

   - **Klienta atribūts**: katram klientam ir viens lauks, kurā norādīts klienta rezultāts, vērtība vai statuss. Klienta atribūti tiek izveidoti kā atribūti jaunā sistēmas ģenerētajā entītijā, ko sauc **Customer_Measure**.

   - **Klienta mērs**: ieskati par klienta rīcību ar sadalījumu pēc atlasītajām dimensijām. Katram mēram tiek ģenerēta jauna entītija, iespējams, ar vairākiem ierakstiem katram klientam.

   - **Uzņēmuma mērs**: izsekojiet sava uzņēmuma veiktspējai un darbības efektivitātei. Uzņēmuma mēriem var būt divas dažādas izvades: skaitliska izvade, kas tiek parādīta **sākumlapā**, vai jauna entītija, kas atrodama lapā **Entītijas**.

4. Norādiet **nosaukumu** (varat norādīt arī **parādāmo nosaukumu**), pēc tam atlasiet **Tālāk**.

5. Sadaļā **Entītijas** atlasiet pirmo ierakstu nolaižamajā sarakstā. Šajā brīdī jums ir jāizlemj, vai mēra definēšanai ir nepieciešamas papildu entītijas.

   > [!div class="mx-imgBorder"]
   > ![Mēra definēšana](media/measure-definition.png "Mēra definīcija")

   Lai pievienotu papildu entītijas, atlasiet **Pievienot entītiju** un atlasiet entītijas, ko vēlaties izmantot šim mēram.

   > [!NOTE]
   > Varat atlasīt tikai tās entītijas, kurām ir relācijas ar jūsu sākuma entītiju. Papildinformāciju par relāciju definēšanu skatiet rakstā [Relācijas](relationships.md).

6. Varat arī konfigurēt mainīgos. Sadaļā **Mainīgie** atlasiet **Jauns mainīgais**.

   Mainīgie ir aprēķini, kas tiek veikti katram no atlasītajiem ierakstiem. Piemēram, summējot pārdošanas punktu (POS) un pārdošanu tiešsaistē katram jūsu klienta ierakstam.

7. Norādiet mainīgā **Nosaukumu**.

8. Apgabalā **Izteiksme** izvēlieties lauku, ar kuru sākt aprēķinu.

9. Izteiksmes nosaukumu ierakstiet apgabalā **Izteiksme** un izvēlieties papildu laukus iekļaušanai aprēķinā.

   > [!NOTE]
   > Pašlaik tiek atbalstītas tikai aritmētiskas izteiksmes. Turklāt mainīgo aprēķins netiek atbalstīts entītijām no atšķirīgiem [entītiju ceļiem](relationships.md).

10. Atlasiet **Gatavs**.

11. Sadaļā **Mēra definēšana** ir jānosaka, kā jūsu izvēlētās entītijas un aprēķinātie mainīgie tiks apkopoti jaunā mēra entītijā vai atribūtā.

12. Atlasiet **Jauna dimensija**. Dimensiju var uzskatīt par *grupu pēc* funkcijas. Mēra entītijas vai atribūta datu izvade tiks grupēta pēc visām jūsu definētajām dimensijām.

    > [!div class="mx-imgBorder"]
    > ![Apkopojuma cikla izvēle](media/measures-businessreport-measure-definition2.png "Apkopojuma cikla izvēle")

    Definējot dimensijas, atlasiet vai ievadiet tālāk norādītos informāciju.

    - **Entītija**: Ja definējat mēra entītiju, tajā ir jābūt vismaz vienam atribūtam. Ja definējat mēra atribūtu, pēc noklusējuma tajā būs tikai viens atribūts. Šī atlase ir paredzēta, lai izvēlētos entītiju, kurā ir ietverts šis atribūts.
    - **Lauks**: Izvēlieties konkrētu atribūtu, kas tiks iekļauts mēra entītijā, vai atribūtā.
    - **Intervāls**: Izvēlieties, vai dati tiks apkopoti reizi dienā, mēnesī vai gadā. Tā ir obligāta atlase tikai tad, ja atlasījāt datuma veida atribūtu.
    - **Kā**: definē jaunā lauka nosaukumu.
    - **Parādāmais nosaukums**: Definē lauka parādāmo nosaukumu.

    > [!NOTE]
    > Jūsu uzņēmuma mērs tiks saglabāts kā viena skaitļa entītija, un tas tiks parādīts **sākumlapā**, ja vien savam mēram nepievienosiet papildu dimensijas. Pēc papildu dimensiju pievienošanas šis mērs *netiks* parādīts **sākumlapā**.

13. Varat arī pievienot apkopošanas funkcijas. Jebkuras veiktās apkopošanas rezultātā tiek iegūta jauna vērtība mēra entītijā vai atribūtā. Atbalstītās apkopošanas funkcijas: **Min**, **Max**, **Average**, **Median**, **Sum**, **Count Unique**, **First** (tiek izmantots pirmais dimensijas vērtības ieraksts) un **Last** (tiek izmantots pēdējais dimensijas vērtībai pievienotais ieraksts).

14. Atlasiet **Saglabāt**, lai lietotu izmaiņas mēram.

## <a name="manage-your-measures"></a>Pārvaldiet savus mērus

Kad esat izveidojis vismaz vienu pasākumu, lapā **Mēri** tiks atainots pasākumu saraksts.

Jūs atradīsiet informāciju par mēra tipu, izveidotāju, izveidošanas datumu un laiku, pēdējās rediģēšanas datumu un laiku, statusu (vai mērs ir aktīvs, neaktīvs vai neveiksmīgs) un pēdējās atsvaidzināšanas datumu un laiku. Atlasot mēru no saraksta, varat redzēt tā izvades priekšskatījumu.

Lai vienlaikus atsvaidzinātu visus mērus, atlasiet **Atsvaidzināt visu**, neatlasot noteiktu mēru.

> [!div class="mx-imgBorder"]
> ![Darbības, lai pārvaldītu atsevišķus mērus](media/measure-actions.png "Darbības, lai pārvaldītu atsevišķus mērus")

Varat arī atlasīt mēru no saraksta un izpildīt vienu no šīm darbībām:

- Atlasiet mēra nosaukumu, lai skatītu tā detalizētu informāciju.
- **Rediģējiet** mēra konfigurāciju.
- **Pārdēvējiet** mēru. 
- **Dzēsiet** mēru.
- Atlasiet daudzpunkti (...) un pēc tam **Atsvaidziniet**, lai sāktu mēra atsvaidzināšanas procesu.
- Atlasiet daudzpunkti (...) un pēc tam **Lejupielādēt**, lai iegūtu mēra .CSV failu.

> [!TIP]
> Uzdevumiem/procesiem ir [seši statusu tipi](system.md#status-types). Turklāt vairums procesu [ir atkarīgi no citiem pakārtotiem procesiem](system.md#refresh-policies). Varat atlasīt procesa statusu, lai skatītu detalizētu informāciju par visa uzdevuma norisi. Pēc tam, kad vienam no darba uzdevumiem esat atlasījis **Skatīt detalizētu informāciju**, jūs redzēsit papildinformāciju: apstrādes laiku, pēdējās apstrādes datumu un visas kļūdas un brīdinājumus, kas saistīti ar uzdevumu.

## <a name="next-step"></a>Nākamā darbība

Esošos mērus varat izmantot, lai izveidotu savu pirmo klientu segmentu lapā **Segmenti**. Papildinformāciju skatiet rakstā [Segmenti](segments.md).
