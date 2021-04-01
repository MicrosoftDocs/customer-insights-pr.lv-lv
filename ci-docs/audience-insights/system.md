---
title: Sadaļā Auditorijas ieskati skatiet sistēmas konfigurāciju
description: Informācija par sistēmas iestatījumiem, kas tiek parādīti Dynamics 365 Customer Insights auditorijas ieskatiem.
ms.date: 02/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 87bf8d7b9c23633ebdc929e15ac645c55cc21e4a
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595389"
---
# <a name="system-configuration"></a>Sistēmas konfigurācija

Lapā **Sistēma** ir šādas cilnes:
- [Statuss](#status-tab)
- [Plānot](#schedule-tab)
- [API lietojums](#api-usage-tab)
- [Par](#about-tab)
- [VispārīgI](#general-tab)

> [!div class="mx-imgBorder"]
> ![Sistēmas lapa](media/system-tabs.png "Sistēmas lapa")

## <a name="status-tab"></a>Cilne Statuss

Izmantojot **Statusa cilni**, varat izsekot datu iekļaušanas, datu eksportēšanas un vairākus citus svarīgus produktu procesus. Šajā cilnē pārskatiet informāciju, lai nodrošinātu aktīvo procesu pilnīgumu.

Šajā cilnē ir iekļautas tabulas ar statusu un dažādu procesu apstrādes informāciju. Katrā tabulā tiek izsekots uzdevuma **Nosaukums** un tā atbilstošā entītija, tā pēdējās izpildes **Statuss** un **Pēdējā atjaunināšana**.

Skatīt detalizētu informāciju par pēdējām uzdevuma izpildes reizēm, atlasot tā nosaukumu.

### <a name="status-types"></a>Statusa veidi

Uzdevumiem/procesiem ir seši statusu tipi. Šie statusa tipi tiek rādīti arī lapās *Saskaņot*, *Sapludināt*, *Datu avoti*, *Segmenti*, *Mērījumi*, *Bagātināšana*, *Aktivitātes* un *Prognozes*:

- **Apstrāde:** Uzdevums tiek veikts. Statusu var mainīt uz Sekmīgu vai Kļūdainu.
- **Sekmīgs:** Uzdevums izpildīts sekmīgi.
- **Izlaistais:** uzdevums tika izlaists. Viens vai vairāki pakārtotie procesi, no kuriem atkarīgs šis uzdevums, neizdodas vai tiek izlaisti.
- **Kļūme:** Uzdevuma apstrāde neizdevās.
- **Atcelts:** Lietotājs apstrādi atcēla pirms tās pabeigšanas.
- **Rindā:** apstrāde ir iekļauta rindā, un tā tiks sākta, kad būs pabeigti visi augšupstraumēšanas uzdevumi. Papildinformāciju skatiet rakstā [Atsvaidzināšanas politikas](#refresh-policies).

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

Skatiet detalizētu informāciju par reāllaika API lietošanu un skatiet, kuri notikumi notika konkrētajā laika posmā. Laika periodu varat izvēlēties nolaižamajā izvēlnē **Atlasīt laika posmu**. 

**API lietojumā** ir trīs sadaļas: 
- **API izsaukumi** — diagramma, kas atlasītajā laika posmā vizualizē apkopoto izsaukumu skaitu uz API.

- **Datu pārsūtīšana** — diagramma, kurā redzams datu daudzums, kas atlasītajā laika posmā tika pārsūtīts, izmantojot API.

-  **Darbības** — tabula ar rindām katrai pieejamai API operācijai un detalizēta informācija par operāciju izmantošanu. Varat atlasīt operācijas nosaukumu, lai pārietu [uz API atsauci](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).

   Darbībās, kurās tiek lietota [reāllaika datu iekļaušana](real-time-data-ingestion.md), ir poga ar binokļa simbolu, lai skatītu reāllaika API lietojumu. Atlasiet pogu, lai atvērtu sānu rūti, kurā ir detalizēta lietošanas instrukcija par reāllaika API izmantošanu pašreizējā vidē.   
   Lai izvēlētos, kā vislabāk sniegt reāllaika mijiedarbības, izmantojiet **Grupēt pēc** lodziņu rūtī **Reāllaika API lietojums**. Grupējiet datus pēc API metodes, entītijas nosaukums (izveidotā entītija), izveidoja (notikuma avots), rezultāts (veiksmīgi vai kļūme) vai kļūdu kodi. Dati ir pieejami kā vēstures diagramma un kā tabula.


[!INCLUDE[footer-include](../includes/footer-banner.md)]