---
title: Sapludināt entītijas datu apvienošanā
description: Sapludiniet entītijas, lai izveidotu vienotus klientu profilus.
ms.date: 09/14/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: b038cd3f5b433fedf918d34bbfaf2261e11c5c17
ms.sourcegitcommit: fecdee73e26816c42d39d160d4d5cfb6c8a91596
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 09/15/2021
ms.locfileid: "7494328"
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

1. Atlasiet sapludinātu lauku.
  
1. Atlasiet vienumu **Rādīt vairāk** un izvēlieties **Izslēgt**.

1. Apstipriniet izslēgšanu.

1. Lai apstrādātu izmaiņas, atlasiet **Saglabāt** un **Palaist**. 

**Sapludināšanas** lapā atlasiet **Neiekļautie lauki**, lai redzētu visu neiekļauto lauku sarakstu. Šajā rūtī varat atkal pievienot neiekļautos laukus.

## <a name="edit-a-merged-field"></a>Rediģējiet sapludinātu lauku

1.  Atlasiet sapludinātu lauku.

1.  Atlasiet vienumu **Rādīt vairāk** un izvēlieties **Rediģēt**.

1.  Norādiet, kā laukus apvienot vai sapludināt no vienas no trim opcijām:
    - **Nozīme**: Norāda kā uzvarētāja vērtību, pamatojoties uz iesaistītajā laukā norādīto rangu. Tā ir noklusējuma sapludināšanas opcija. Atlasiet **Pārvietot uz augšu/uz leju**, lai iestatītu svarīguma reitingu.
    :::image type="content" source="media/importance-merge-option.png" alt-text="Svarīguma opcija sapludināšanas lauku dialoglodziņā."::: 
    - **Jaunākais** : identificē uzvarētāja vērtību, pamatojoties uz visizplatītāko resnību. Lai definētu rekvizītus, nepieciešama katras sapludināšanas lauku tvērumā iesaistītās entītijas datums vai skaitlisks lauks.
    :::image type="content" source="media/recency-merge-option.png" alt-text="Svarīguma opcija sapludināšanas lauku dialoglodziņā.":::
    - **Jaunākais** : identificē uzvarētāja vērtību, pamatojoties uz visizplatītāko resnību. Lai definētu rekvizītus, nepieciešama katras sapludināšanas lauku tvērumā iesaistītās entītijas datums vai skaitlisks lauks.

1.  Sapludināšanas procesā var pievienot papildu laukus.

1.  Sapludināto lauku var pārdēvēt.

1. Atlasiet **Labi**, lai piemērotu izmaiņas.

1. Lai apstrādātu izmaiņas, atlasiet **Saglabāt** un **Palaist**. 

## <a name="manually-combine-fields"></a>Manuāli apvienot laukus

Manuāli norādiet sapludinātu atribūtu. 

1. **Sapludināšanas** lapā atlasiet **Lauku apvienošana**.

1. Nolaižamajā izvēlnē **Lauku apvienošana** norādiet sapludināšanas uzvarētāja politiku.

1. Izvēlieties pievienojamo lauku. Atlasiet **Pievienot laukus**, lai apvienotu vairāk lauku.

1. Norādiet **Nosaukumu** un **Izvades lauka nosaukumu**.

1. Atlasiet **Labi**, lai piemērotu izmaiņas.

1. Lai apstrādātu izmaiņas, atlasiet **Saglabāt** un **Palaist**. 

## <a name="change-the-order-of-fields"></a>Lauku secības maiņa

Dažās entītijās ir detalizētāka informācija nekā citās. Ja entītijā ir ietverti jaunākie dati par kādu lauku, sapludinot vērtības, par to var noteikt prioritātes citās entītijās.

1. Atlasiet sapludināto lauku.
  
1. Atlasiet vienumu **Rādīt vairāk** un izvēlieties **Rediģēt**.

1. **Lauku apvienošanas** rūtī atlasiet **Pārvietot uz augšu/uz leju**, lai iestatītu secību, vai velciet un nometiet tos vēlamajā pozīcijā.

1. Apstiprināt izmaiņas.

1. Lai apstrādātu izmaiņas, atlasiet **Saglabāt** un **Palaist**.

## <a name="configure-customer-id-generation"></a>Klienta ID ģenerēšanas konfigurēšana 

Pēc lauku sapludināšanas konfigurēšanas varat definēt, kā ģenerēt CustomerId vērtības, unikālos klienta profila identifikatorus. Sapludināšanas darbība datu unificēšanas procesā ģenerē unikālu klienta profila identifikatoru. Identifikators ir *Klienta* entītijas CustomerId, kas rodas datu apvienošanas procesa rezultātā. 

Klienta entītijas CustomerId pamatā ir primārās atslēgas, kas nav Null, pirmās vērtības jaukšana. Šos taustiņus nodrošina atbilstības spēlē un sapludināšanā izmantotās entītijas, un tos nosaka atbilstības pasūtījums.Tāpēc ģenerētais CustomerID var tikt mainīts, kad primārās atslēgas vērtība mainās atbilstības pasūtījuma primārajā entītijā. Primārais kritērijs ir primārās atslēgas vērtība, iespējams, ne vienmēr apzīmē vienu un to pašu klientu.

Konfigurējot stabilu klienta ID, varat izvairīties no šādas uzvedības.

**Unikālā klienta ID konfigurēšana**

1. Dodieties uz **Apvienot** > **Sapludināt**.

1. **Sapludināšanas** lapā atlasiet cilni **Taustiņi**. 

1. Norādiet uz **CustomerId** rindu un atlasiet opciju **Konfigurēt**.
   :::image type="content" source="media/customize-stable-id.png" alt-text="Vadīklu, lai pielāgotu ID ģenerēšanu.":::

1. Atlasiet līdz pieciem laukiem, kuros būs unikāls klienta ID un kuri ir ar daudz lielāku stabilitāti. Ieraksti, kas neatbilst jūsu konfigurācijai, tā vietā izmanto sistēmas konfigurētu ID.  

1. Atlasiet **Pabeigts** un palaidiet sapludināšanas procesu, lai lietotu veiktās izmaiņas.

## <a name="run-your-merge"></a>Sapludināšanas izpilde

Neatkarīgi no tā, vai manuāli sapludināt atribūtus vai ļaujat tos sapludināt sistēmai, jūs jebkurā gadījumā varat izpildīt sapludināšanu. Lapā **Sapludināšana** atlasiet **Izpildīt**, lai sāktu procesu.

> [!div class="mx-imgBorder"]
> ![Datu sapludināšana: saglabāšana un izpilde.](media/configure-data-merge-save-run.png "Datu sapludināšana: saglabāšana un izpilde")

Izvēlieties **Palaist tikai sapludināšanu**, ja vēlaties redzēt tikai vienotā klienta entītijas izvadi. Lejupstraumes procesi tiks atsvaidzināti, kā [definēts atsvaidzināšanas grafikā](system.md#schedule-tab).

Izvēlieties **Palaist sapludināšanu un lejupstraumes procesus**, lai atsvaidzinātu sistēmu ar jūsu izmaiņām. Visi procesi, tostarp bagātināšana, segmenti un pasākumi, tiks automātiski veikti atkārtoti. Kad visi lejupstraumes procesi ir pabeigti, klientu profili atspoguļo jūsu veiktās izmaiņas.

Lai veiktu lielākas izmaiņas un veiktu atkārtotu darbību, varat atcelt notiekošu sapludināšanu. Atlasiet **Atsvaidzina...** un atlasiet **Atcelt uzdevumu** blakus rūtī, kas tiek parādīta.

> [!TIP]
> Pēc sapludināšanas procesa izpildīšanas atlasiet procesa statusu, lai atvērtu **Uzdevuma detalizētās informācijas** rūti. Tajā sniegts pārskats par apstrādes laiku, pēdējo apstrādes datumu un visām ar uzdevumu saistītajām kļūdām un brīdinājumiem. Atlasiet vienumu **Skatīt informāciju**, lai skatītu, kuras entītijas piedalījās atbilstības procesā, kurās tika lietotas kārtulas, un vai atjauninājumi tika sekmīgi publicēti.  
> Uzdevumiem/procesiem ir [seši statusu tipi](system.md#status-types). Turklāt vairums procesu [ir atkarīgi no citiem pakārtotiem procesiem](system.md#refresh-policies).  
> :::image type="content" source="media/process-detail-path.png" alt-text="Rakšanās ceļš uz procesa informāciju no uzdevuma statusa saites.":::

## <a name="next-step"></a>Nākamā darbība

Konfigurējiet opcijas [darbības](activities.md), [bagātināšana](enrichment-hub.md) vai [relācijas](relationships.md), lai gūtu plašāku ieskatu par saviem klientiem.

Ja jau esat konfigurējis darbības, bagātināšanu vai segmentus, tie tiks apstrādāti automātiski, lai izmantotu jaunākos klientu datus.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
