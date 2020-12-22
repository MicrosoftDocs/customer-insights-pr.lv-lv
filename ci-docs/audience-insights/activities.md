---
title: Klientu darbības
description: Definējiet klientu darbības un aplūkojiet tās klientu laika skalā.
ms.date: 10/13/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: adkuppa
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 1c95cba333266a73959de0a3afe1c8677130a3ec
ms.sourcegitcommit: 334633cbd58f5659d20b4f87252c1a10cc7130db
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 12/03/2020
ms.locfileid: "4667238"
---
# <a name="customer-activities"></a>Klientu darbības

Kombinējiet klientu darbības no [dažādiem datu avotiem](data-sources.md) Dynamics 365 Customer Insights, lai izveidotu klientu laika skalu, kurā darbības ir uzskaitītas hronoloģiskā secībā. Varat iekļaut laika skalu klientu iesaistes programmās pakalpojumā Dynamics 365, izmantojot [Customer Card pievienojumprogrammu](customer-card-add-in.md) vai Power BI informācijas paneli.

## <a name="define-an-activity"></a>Darbības definēšana

Datu avoti ietver entītijas ar transakciju un darbību datiem no vairākiem datu avotiem. Identificējiet šīs entītijas un atlasiet darbības, kuras vēlaties skatīt klienta laika skalā. Izvēlieties entītiju, kurā ir jūsu mērķa darbība vai darbības.

1. Sadaļā Auditorijas ieskati skatiet **Dati** > **Darbības**.

1. Atlasiet **Pievienot darbību**.

   > [!NOTE]
   > Entītijai ir nepieciešams vismaz viens veida **Datums** atribūts, ko iekļaut klienta laika skalā, un entītijas bez **Datuma** laukiem nevar pievienot. Ja netiek atrasta šāda entitīja, vadīkla **Pievienot darbību** tiek atspējota.

1. Rūtī **Pievienot darbību** iestatiet šādu lauku vērtības:

   - **Entītija**: Atlasiet entītiju, kurā ir transakciju vai darbību dati.
   - **Primārā atslēga**: Atlasīt lauku, kas unikāli identificē ierakstu. Tajā nedrīkst ietvert dublētas vērtības, tukšas vērtības vai trūkstošas vērtības.
   - **Laikspiedols**: Atlasiet lauku, kas norāda darbības sākuma laiku.
   - **Notikums**: Atlasiet lauku, kas ir darbības notikums.
   - **Tīmekļa adrese** : Atlasiet lauku, kas norāda URL, kas nodrošina papildinformāciju par šo darbību. Piemēram, transakciju sistēma, kas ģenerē šo darbību. Šis URL var būt jebkurš lauks no datu avota, vai arī to var būvēt kā jaunu lauku, izmantojot Power Query transformāciju. Šie URL dati tiks saglabāti Vienotās darbības entītijā, ko var patērēt pa straumi, izmantojot API.
   - **Detalizēta informācija**: Pēc izvēles atlasiet lauku, kas tiek pievienots papildu informācijai.
   - **Ikona**: Pēc izvēles atlasiet ikonu, kas apzīmē šo darbību.
   - **Darbības tips**: Definējiet darbības tipa atsauci uz Common Data Model, kas vislabāk apraksta darbības semantisko definīciju.

1. Sadaļā **Relācijas iestatīšana** konfigurējiet detalizēto informāciju, lai savienotu savus darbību datus ar atbilstošo klientu.

   > [!div class="mx-imgBorder"]
   > ![Entītiju relācijas definēšana](media/activities-entities-define.png "Entītiju relācijas definēšana")

    - **Darbības entītijas lauks**: Atlasiet lauku savā darbības entītijā, kurš tiks izmantots relācijas izveidei ar citu entītiju.
    - **Klienta entītija**: Atlasiet atbilstošo avota klienta entītiju, ar kuru jūsu darbības entītijai tiks izveidota relācija. Var saistīt tikai tās avota klienta entītijas, kuras tiek izmantotas datu apvienošanas procesā.
    - **Klienta entītijas lauks**: Šajā laukā ir norādīta avota klienta entītijas primārā atslēga, kas atlasīta kartēšanas procesā. Šis primārās atslēgas lauks avota klienta entītijā tiek izmantots, lai izveidotu relāciju ar darbības entītiju.
    - **Nosaukums**: Ja relācija starp šo darbības entītiju un atlasīto avota klienta entītiju jau pastāv, relācijas nosaukums būs tikai lasāmā režīmā. Ja šādas relācijas nav, tiek izveidota jauna relācija ar šeit norādīto nosaukumu.

1. Lai veiktās izmaiņas stātos spēkā, atlasiet **Saglabāt**.

1. Lapā **Darbības** atlasiet **Palaist**.

> [!TIP]
> Uzdevumiem/procesiem ir [seši statusu tipi](system.md#status-types). Turklāt vairums procesu [ir atkarīgi no citiem pakārtotiem procesiem](system.md#refresh-policies). Varat atlasīt procesa statusu, lai skatītu detalizētu informāciju par visa uzdevuma norisi. Pēc tam, kad vienam no darba uzdevumiem esat atlasījis **Skatīt detalizētu informāciju**, jūs redzēsit papildinformāciju: apstrādes laiku, pēdējās apstrādes datumu un visas kļūdas un brīdinājumus, kas saistīti ar uzdevumu.

## <a name="edit-an-activity"></a>Darbības rediģēšana

1. Sadaļā Auditorijas ieskati skatiet **Dati** > **Darbības**.

2. Atlasiet darbības entītiju, kuru vēlaties rediģēt, un atlasiet **Rediģēt**. Vai arī varat novietot rādītāju virs entītijas rindas un atlasīt ikonu **Rediģēt**.

3. Noklikšķiniet uz ikonas **Rediģēt**.

4. **Rediģēšanas darbības** rūtī atjauniniet vērtības un atlasiet vienumu **Saglabāt**.

5. Lapā **Darbības** atlasiet **Palaist**.

## <a name="delete-an-activity"></a>Darbības dzēšana

1. Sadaļā Auditorijas ieskati skatiet **Dati** > **Darbības**.

2. Atlasiet darbības entītiju, kuru vēlaties noņemt, un atlasiet **Dzēst**. Vai arī varat novietot rādītāju virs entītijas rindas un atlasīt ikonu **Dzēst**. Turklāt vienlaikus varat atlasīt vairākas darbību entītijas, lai izdzēstu tās vienlaicīgi.
   > [!div class="mx-imgBorder"]
   > ![Entītiju attiecību rediģēšana vai dzēšana](media/activities-entities-edit-delete.png "Entītiju attiecību rediģēšana vai dzēšana")

3. Atlasiet ikonu **Dzēst**.

4. Apstipriniet dzēšanu.
