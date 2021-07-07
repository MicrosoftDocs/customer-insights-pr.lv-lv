---
title: Sapludināt entītijas datu apvienošanā
description: Sapludiniet entītijas, lai izveidotu vienotus klientu profilus.
ms.date: 05/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 86ab3cefa70e5fab4bdb27cde363adee26efee4c
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305656"
---
# <a name="merge-entities"></a>Sapludiniet entītijas

Sapludināšanas posms ir pēdējais datu apvienošanas procesa posms. Tā mērķis ir konfliktējošu datu saskaņošana. Konfliktējošo datu piemērs var būt klienta vārds, kas ir atrodams divās datu kopās, taču katrā no tām tas tiek rādīts nedaudz atšķirīgi ("Oto Bērzs" un "Otto Bērzs"), vai tālruņa numurs, kas atšķiras pēc formāta (21-480-309 un 21480309). Šo konfliktējošo datu punktu sapludināšana notiek, pamatojoties uz pieeju “atribūts pēc atribūta”

:::image type="content" source="media/merge-fields-page.png" alt-text="Datu apvienošanas procesa sapludināšanas lapa, kurā redzama tabula ar sapludinātiem laukiem, kas definē vienoto klienta profilu.":::

Pēc [atbilstības posma](match-entities.md) pabeigšanas varat sākt sapludināšanas posmu, lapā **Apvienošana** atlasot **Sapludināt**.

## <a name="review-system-recommendations"></a>Sistēmas ieteikumu pārskatīšana

Izmantojot **Dati** > **Apvienot** > **Sapludināt**, jūs izvēlaties un izslēdzat atribūtus, kas jāsapludina jūsu vienotajā klienta profila entītijā. Vienotais klienta profils ir datu unificēšanas procesa rezultāts. Dažus atribūtus sistēma sapludina automātiski.

Lai skatītu atribūtus, kas iekļauti kādā no automātiski sapludinātajiem atribūtiem, atlasiet šo sapludināto atribūtu entītijas cilnē **Klienta lauki**. Šie divi atribūti, kas veido sapludināto atribūtu, tiks parādīti divās jaunās rindās zem sapludinātā atribūta.

## <a name="separate-rename-exclude-and-edit-merged-fields"></a>Atdalīt, pārdēvēt, izslēgt un rediģēt sapludinātos laukus

Var mainīt, kā sistēma apstrādā sapludinātos atribūtus, lai ģenerētu vienoto klienta profilu. Atlasiet vienumu **Rādīt vairāk** un izvēlieties, ko vēlaties mainīt.

:::image type="content" source="media/manage-merged-attributes.png" alt-text="Nolaižamās izvēlnes Rādīt vairāk opcijas, lai pārvaldītu sapludinātos atribūtus.":::

Papildinformāciju skatiet nākamajās sadaļās.

## <a name="separate-merged-fields"></a>Atdalīt sapludinātos laukus

Lai atdalītu sapludinātos laukus, atrodiet atribūtu tabulā. Atsevišķie lauki vienotā klienta profilā tiek rādīti kā atsevišķi datu punkti. 

1. Atlasiet sapludināto lauku.
  
1. Atlasiet vienumu **Rādīt vairāk** un izvēlieties **Atsevišķi lauki**.
 
1. Apstipriniet atdali.

1. Lai apstrādātu izmaiņas, atlasiet **Saglabāt** un **Palaist**.

## <a name="rename-merged-fields"></a>Sapludināto lauku pārdēvēšana

Mainīt sapludināto atribūtu parādāmo nosaukumu. Izvades entītijas nosaukumu nevar mainīt.

1. Atlasiet sapludināto lauku.
  
1. Atlasiet vienumu **Rādīt vairāk** un izvēlieties **Pārdēvēt**.

1. Apstipriniet mainīto parādāmo nosaukumu. 

1. Lai apstrādātu izmaiņas, atlasiet **Saglabāt** un **Palaist**.

## <a name="exclude-merged-fields"></a>Izslēgt sapludinātos laukus

Neiekļaut atribūtu no vienotā klienta profila. Ja lauks tiek izmantots citos procesos, piemēram, segmentā, pirms lauka izslēgšanas no klienta profila, noņemiet to no šiem procesiem. 

1. Atlasiet sapludināto lauku.
  
1. Atlasiet vienumu **Rādīt vairāk** un izvēlieties **Izslēgt**.

1. Apstipriniet izslēgšanu.

1. Lai apstrādātu izmaiņas, atlasiet **Saglabāt** un **Palaist**. 

**Sapludināšanas** lapā atlasiet **Neiekļautie lauki**, lai redzētu visu neiekļauto lauku sarakstu. Šajā rūtī varat atkal pievienot neiekļautos laukus.

## <a name="manually-combine-fields"></a>Manuāli apvienot laukus

Manuāli norādiet sapludinātu atribūtu. 

1. **Sapludināšanas** lapā atlasiet **Lauku apvienošana**.

1. Norādiet **Nosaukumu** un **Izvades lauka nosaukumu**.

1. Izvēlieties pievienojamo lauku. Atlasiet **Pievienot laukus**, lai apvienotu vairāk lauku.

1. Apstipriniet izslēgšanu.

1. Lai apstrādātu izmaiņas, atlasiet **Saglabāt** un **Palaist**. 

## <a name="change-the-order-of-fields"></a>Lauku secības maiņa

Dažās entītijās ir detalizētāka informācija nekā citās. Ja entītijā ir ietverti jaunākie dati par kādu lauku, sapludinot vērtības, par to var noteikt prioritātes citās entītijās.

1. Atlasiet sapludināto lauku.
  
1. Atlasiet vienumu **Rādīt vairāk** un izvēlieties **Rediģēt**.

1. **Lauku apvienošanas** rūtī atlasiet **Pārvietot uz augšu/uz leju**, lai iestatītu secību, vai velciet un nometiet tos vēlamajā pozīcijā.

1. Apstiprināt izmaiņas.

1. Lai apstrādātu izmaiņas, atlasiet **Saglabāt** un **Palaist**.

## <a name="run-your-merge"></a>Sapludināšanas izpilde

Neatkarīgi no tā, vai manuāli sapludināt atribūtus vai ļaujat tos sapludināt sistēmai, jūs jebkurā gadījumā varat izpildīt sapludināšanu. Lapā **Sapludināšana** atlasiet **Izpildīt**, lai sāktu procesu.

> [!div class="mx-imgBorder"]
> ![Datu sapludināšana: saglabāšana un izpilde](media/configure-data-merge-save-run.png "Datu sapludināšana: saglabāšana un izpilde")

Izvēlieties **Palaist tikai sapludināšanu**, ja vēlaties redzēt tikai vienotā klienta entītijas izvadi. Lejupstraumes procesi tiks atsvaidzināti, kā [definēts atsvaidzināšanas grafikā](system.md#schedule-tab).

Izvēlieties **Palaist sapludināšanu un lejupstraumes procesus**, lai atsvaidzinātu sistēmu ar jūsu izmaiņām. Visi procesi, tostarp bagātināšana, segmenti un pasākumi, tiks automātiski veikti atkārtoti. Kad visi lejupstraumes procesi ir pabeigti, klientu profili atspoguļo jūsu veiktās izmaiņas.

Lai veiktu lielākas izmaiņas un veiktu atkārtotu darbību, varat atcelt notiekošu sapludināšanu. Atlasiet **Atsvaidzina...** un atlasiet **Atcelt uzdevumu** blakus rūtī, kas tiek parādīta.

> [!TIP]
> Uzdevumiem/procesiem ir [seši statusu tipi](system.md#status-types). Turklāt vairums procesu [ir atkarīgi no citiem pakārtotiem procesiem](system.md#refresh-policies). Varat atlasīt procesa statusu, lai skatītu detalizētu informāciju par visa uzdevuma norisi. Pēc tam, kad vienam no darba uzdevumiem esat atlasījis **Skatīt detalizētu informāciju**, jūs redzēsit papildinformāciju: apstrādes laiku, pēdējās apstrādes datumu un visas kļūdas un brīdinājumus, kas saistīti ar uzdevumu.

## <a name="next-step"></a>Nākamā darbība

Konfigurējiet opcijas [darbības](activities.md), [bagātināšana](enrichment-hub.md) vai [relācijas](relationships.md), lai gūtu plašāku ieskatu par saviem klientiem.

Ja jau esat konfigurējis darbības, bagātināšanu vai segmentus, tie tiks apstrādāti automātiski, lai izmantotu jaunākos klientu datus.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
