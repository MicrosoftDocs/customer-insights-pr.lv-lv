---
title: Sapludināt entītijas datu apvienošanā
description: Sapludiniet entītijas, lai izveidotu vienotus klientu profilus.
ms.date: 04/16/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 045fd8d8f65161b91caabed2ac52494dc4fb3910
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406360"
---
# <a name="merge-entities"></a>Sapludiniet entītijas

Sapludināšanas posms ir pēdējais datu apvienošanas procesa posms. Tā mērķis ir konfliktējošu datu saskaņošana. Konfliktējošo datu piemērs var būt klienta vārds, kas ir atrodams divās datu kopās, taču katrā no tām tas tiek rādīts nedaudz atšķirīgi ("Oto Bērzs" un "Otto Bērzs"), vai tālruņa numurs, kas atšķiras pēc formāta (21-480-309 un 21480309). Šo konfliktējošo datu punktu sapludināšana notiek, pamatojoties uz pieeju “atribūts pēc atribūta”

Pēc [atbilstības posma](match-entities.md) pabeigšanas varat sākt sapludināšanas posmu, lapā **Apvienošana** atlasot **Sapludināt**.

## <a name="review-system-recommendations"></a>Sistēmas ieteikumu pārskatīšana

Lapā **Sapludināšana** varat izvēlēties un izslēgt atribūtus sapludināšanai ar vienotā klienta profila entītiju (konfigurācijas procesa rezultāts). Dažus atribūtus sistēma sapludina automātiski.

### <a name="view-merged-attributes"></a>Sapludināto atribūtu skatīšana

Lai skatītu atribūtus, kas ir iekļauti kādā no jūsu automātiski sapludinātajiem atribūtiem, atlasiet šo sapludināto atribūtu. Šie divi atribūti, kas veido sapludināto atribūtu, tiks parādīti divās jaunās rindās zem sapludinātā atribūta.

> [!div class="mx-imgBorder"]
> ![Sapludinātā atribūta atlasīšana](media/configure-data-merge-profile-attributes.png "Sapludinātā atribūta atlasīšana")

### <a name="separate-merged-attributes"></a>Sapludināto atribūtu atdalīšana

Lai atdalītu kādu no automātiski sapludinātajiem atribūtiem jeb noņemtu sapludināšanu, atrodiet šo atribūtu tabulā **Profila atribūti**.

1. Atlasiet daudzpunktes (...) pogu.
  
2. Nolaižamajā sarakstā atlasiet **Atsevišķi lauki**.

### <a name="remove-merged-attributes"></a>Sapludināto atribūtu noņemšana

Lai izslēgtu kādu atribūtu no galīgās klienta profila entītijas, atrodiet šo atribūtu tabulā **Profila atribūti**.

1. Atlasiet daudzpunktes (...) pogu.
  
2. Nolaižamajā sarakstā atlasiet **Nesapludināt**.

   Atribūts tiks pārvietots uz sadaļu **Noņemts no klienta ieraksta**.

## <a name="manually-add-a-merged-attribute"></a>Sapludināta atribūta manuāla pievienošana

Lai pievienotu sapludinātu atribūtu, dodieties uz lapu **Sapludināšana**.

1. Atlasiet **Pievienot sapludināto atribūtu**.

2. Norādiet **nosaukumu**, lai vēlāk to identificētu lapā **Sapludināšana**.

3. Varat arī norādīt **Parādāmo nosaukumu**, kas parādās vienotajā klienta profila entītijā.

4. Konfigurējiet opciju **Atribūtu dublikātu atlase**, lai atlasītu atribūtus, ko vēlaties sapludināt no atbilstošajām entītijām. Varat arī meklēt atribūtus.

5. Iestatiet opciju **Ranžēt pēc svarīguma**, lai noteiktu, ka kādam atribūtam būs augstāka prioritāte nekā citiem atribūtiem. Piemēram, ja entītijā *WebAccountCSV* ir ietverti visprecīzākie dati par atribūtu *Full Names*, atlasot *WebAccountCSV*, varat noteikt, ka šai entītijai būs augstāka prioritāte nekā *ContactCSV*. Tā rezultātā, iegūstot vērtības atribūtam *Full Name*, *WebAccountCSV* tiek pārvietots uz pirmo prioritāti, bet *ContactCSV* — uz otro prioritāti.

## <a name="run-your-merge"></a>Sapludināšanas izpilde

Neatkarīgi no tā, vai manuāli sapludināt atribūtus vai ļaujat tos sapludināt sistēmai, jūs jebkurā gadījumā varat izpildīt sapludināšanu. Lapā **Sapludināšana** atlasiet **Izpildīt**, lai sāktu procesu.

> [!div class="mx-imgBorder"]
> ![Datu sapludināšana: saglabāšana un izpilde](media/configure-data-merge-save-run.png "Datu sapludināšana: saglabāšana un izpilde")

Lai veiktu papildu izmaiņas un atkārtoti palaistu darbību, varat atcelt notiekošu sapludināšanu. Atlasiet **Atsvaidzina...** un atlasiet **Atcelt uzdevumu** blakus rūtī, kas tiek parādīta.

Pēc tam, kad teksts **Atsvaidzina...** tiek nomainīts uz **Izdevās**, sapludināšana ir pabeigta un jūsu datu pretrunas ir atrisinātas atbilstoši jūsu definētajām politikām. Sapludinātie un nesapludinātie atribūti ir iekļauti vienotā profila entītijā. Izslēgtie atribūti netiek iekļauti vienotā profila entitījā.

Ja tā nebija pirmā reize, kad veiksmīgi palaidāt sapludināšanu, visi pakārtotie procesi, tostarp bagātināšana, segmentācija un mērīšana, tiks atkārtoti palaista automātiski. Pēc visu pakārtoto procesu atkārtotas palaišanas klientu profili rādīs jebkādas jūsu veiktās izmaiņas.

> [!TIP]
> Uzdevumiem/procesiem ir [seši statusu tipi](system.md#status-types). Turklāt vairums procesu [ir atkarīgi no citiem pakārtotiem procesiem](system.md#refresh-policies). Varat atlasīt procesa statusu, lai skatītu detalizētu informāciju par visa uzdevuma norisi. Pēc tam, kad vienam no darba uzdevumiem esat atlasījis **Skatīt detalizētu informāciju**, jūs redzēsit papildinformāciju: apstrādes laiku, pēdējās apstrādes datumu un visas kļūdas un brīdinājumus, kas saistīti ar uzdevumu.

## <a name="next-step"></a>Nākamā darbība

Konfigurējiet opcijas [darbības](activities.md), [bagātināšana](enrichment-microsoft-graph.md) vai [relācijas](relationships.md), lai gūtu plašāku ieskatu par saviem klientiem.

Ja jau esat konfigurējis darbības, bagātināšanu vai relācijas vai definējāt segmentus, tie tiek apstrādāti automātiski, lai izmantotu jaunākos klientu datus.


