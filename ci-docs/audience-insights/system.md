---
title: Sadaļā Auditorijas ieskati skatiet sistēmas konfigurāciju
description: Informācija par sistēmas iestatījumiem, kas tiek parādīti Dynamics 365 Customer Insights auditorijas ieskatiem.
ms.date: 06/02/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: nimagen
manager: shellyha
ms.openlocfilehash: 7dd72e6512cd87ac70235d21667399298408db21
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406364"
---
# <a name="system-configuration"></a>Sistēmas konfigurācija

Lapā **Sistēmas** ir iekļautas četras cilnes: **Statuss**, **Grafiks**, **Par** un **Vispārīgi**.

> [!div class="mx-imgBorder"]
> ![Sistēmas lapa](media/system-tabs.png "Sistēmas lapa")

## <a name="status-tab"></a>Cilne Statuss

**Statusa cilnē** var izsekot datu pieņemšanas norisei, datu eksportiem un vairākiem svarīgiem preces procesiem. Šajā cilnē pārskatiet informāciju, lai nodrošinātu aktīvo procesu pilnīgumu.

Šī cilne ietver statusa tabulas **Datu avotiem**, **Sistēmas procesiem** un **Datu sagatavošanai**. Katrā tabulā tiek izsekots uzdevuma **Nosaukums** un tā atbilstošā entītija, tā pēdējās izpildes **Statuss** un **Pēdējā atjaunināšana**.

Skatīt detalizētu informāciju par pēdējām uzdevuma izpildes reizēm, atlasot tā nosaukumu.

### <a name="status-types"></a>Statusa veidi

Uzdevumiem/procesiem ir seši statusu tipi. Šie statusa tipi tiek rādīti arī lapās *Saskaņot*, *Sapludināt*, *Datu avoti*, *Segmenti*, *Mērījumi*, *Bagātināšana*, *Aktivitātes* un *Prognozes*:

- **Apstrāde:** Uzdevums tiek veikts. Statusu var mainīt uz Sekmīgu vai Kļūdainu.
- **Sekmīgs:** Uzdevums izpildīts sekmīgi.
- **Izlaistais:** uzdevums tika izlaists. Viens vai vairāki pakārtotie procesi, no kuriem atkarīgs šis uzdevums, neizdodas vai tiek izlaisti.
- **Kļūme:** Uzdevuma apstrāde neizdevās.
- **Atcelts:** Lietotājs apstrādi atcēla pirms tās pabeigšanas.
- **Rindā:** Apstrāde ir rindā un sāksies pēc visu pakārtoto uzdevumu pabeigšanas. Papildinformāciju skatiet rakstā [Atsvaidzināšanas politikas](#refresh-policies).

### <a name="refresh-policies"></a>Atsvaidzināšanas politikas

Šajā sarakstā ir parādīta atsvaidzināšanas politika attiecībā uz katru no galvenajiem procesiem:

- **Datu avoti:** Darbojas atbilstoši [konfigurētajam grafikam ](#schedule-tab). Esiet neatkarīgi no citiem procesiem. Atbilstība ir atkarīga no šī procesa sekmīgas pabeigšanas.
- **Atbilstība:** Darbojas atbilstoši [konfigurētajam grafikam ](#schedule-tab). Atkarīga no to datu avotu apstrādes, kuri tiek izmantoti atbilstības definīcijā. Sapludināšana ir atkarīga no šī procesa sekmīgas pabeigšanas.
- **Sapludināšana**: Darbojas atbilstoši [konfigurētajam grafikam ](#schedule-tab). Atkarīga no atbilstības procesa pabeigšanas. Segmenti, mērījumi, bagātināšana, meklēšana, darbības, prognozes un datu sagatavošana ir atkarīga no sekmīgas šī procesa pabeigšanas.
- **Segmenti** : Darbojas manuāli (vienreizēja atsvaidzināšana) un atbilstoši [konfigurētajam grafikam](#schedule-tab). Atkarīgi no sapludināšanas. Ieskati ir atkarīgi no to apstrādes.
- **Mērījumi**: Darbojas manuāli (vienreizēja atsvaidzināšana) un atbilstoši [konfigurētajam grafikam](#schedule-tab). Atkarīgi no sapludināšanas.
- **Darbības**: Darbojas manuāli (vienreizēja atsvaidzināšana) un atbilstoši [konfigurētajam grafikam](#schedule-tab). Atkarīgi no sapludināšanas.
- **Bagātināšana**: Darbojas manuāli (vienreizēja atsvaidzināšana) un atbilstoši [konfigurētajam grafikam](#schedule-tab). Atkarīgi no sapludināšanas.
- **Meklēšana**: Darbojas manuāli (vienreizēja atsvaidzināšana) un atbilstoši [konfigurētajam grafikam](#schedule-tab). Atkarīgi no sapludināšanas.
- **Datu sagatavošana**: Darbojas atbilstoši [konfigurētajam grafikam ](#schedule-tab). Atkarīgi no sapludināšanas.
- **Ieskati** : Darbojas manuāli (vienreizēja atsvaidzināšana) un atbilstoši [konfigurētajam grafikam](#schedule-tab). Atkarīgi no segmentiem.

Atlasiet uzdevuma statusu, lai redzētu detalizētu informāciju par to, kāda ir norise visam darbam, kurā tas ietilpa. Iepriekš minētās atsvaidzināšanas politikas var palīdzēt izprast, ko varat darīt, atrisinātu uzdevumu, kas ir **Izlaists** vai **Rindā**.

## <a name="schedule-tab"></a>Plānošanas cilne

Izmantojiet cilni **Grafiks**, lai plānotu visu jūsu uzņemto [datu avotu automātisko atsvaidzināšanu](data-sources.md). Automātiskā atsvaidzināšana palīdz nodrošināt, ka jūsu datu avotu atjauninājumi tiek atspoguļoti vienotajos klientu profilos.

1. Sadaļā auditorijas ieskati ejiet uz **Administrēšana** > **Sistēma** un atlasiet cilni **Grafiks**.

2. Plānotās atsvaidzināšanas noklusējuma stāvoklis ir **Izslēgts**. Lai iespējotu plānoto atsvaidzināšanu, ekrāna augšdaļā mainiet slēdža pozīciju uz **Ieslēgta**.

3. Izvēlieties starp **Katru nedēļu** (noklusējuma) un **Katru dienu**. Ja plānojat iknedēļas atsvaidzināšanu, atlasiet vienu vai vairākas dienas, kurās vēlaties izpildīt atsvaidzināšanu.

4. Iestatiet **Laika joslu**, tad izmantojiet **Laika** nolaižamo sarakstu, lai iestatītu atsvaidzināšanas laiku. Kad esat pabeidzis, atlasiet **Iestatīt**. Ja vēlaties ieplānot vairākas atsvaidzināšanas vienā dienā, atlasiet **Pievienot citu laiku**.

5. Lai veiktās izmaiņas stātos spēkā, atlasiet **Saglabāt**.

## <a name="about-tab"></a>Cilne Par

Cilnē **Par** ir norādīts jūsu organizācijas **Parādāmais nosaukums**, aktīvais **Vides ID**, **Reģions** un **Sesijas ID**. Ja jums ir vairāk nekā viena darba vide, katrai videi vajadzētu piešķirt viegli identificējamu parādāmo nosaukumu.

## <a name="general-tab"></a>Cilne Vispārīgi

Cilnē **Vispārīgi** ir divas opcijas — **Valoda** un **Valsts/reģiona formāts**.

Programma [atbalsta vairākas valodas](supported-languages.md). Lai mainītu vēlamo valodu, nolaižamajā izvēlnē izvēlieties **Valodu**.

Lai mainītu datumu, laika un skaitļu vēlamo formatējumu, izmantojiet nolaižamo izvēlni **Valsts/reģiona formāts**. Šajā laukā tiek rādīts formatēšanas priekšskatījums. Ja izvēlēsities jaunu valodu, sistēma automātiski piedāvās atlasi.

Atlasiet **Saglabāt**, lai apstiprinātu atlases.

## <a name="api-usage-tab"></a>API lietošanas cilne

Detalizēta informācija par API reāllaika izmantošanu un informācija par to, kādi notikumi tika parādīti noteiktā laika diapazonā. Papildinformāciju skatiet [Reāllaika darbplūsmu lietošana](real-time-data-ingestion.md).
