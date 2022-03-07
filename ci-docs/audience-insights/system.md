---
title: Sadaļā Auditorijas ieskati skatiet sistēmas konfigurāciju
description: Informācija par sistēmas iestatījumiem, kas tiek parādīti Dynamics 365 Customer Insights auditorijas ieskatiem.
ms.date: 11/01/2021
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-status
- ci-system-schedule
- ci-system-about
- ci-system-general
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: 2c52f7b8a7d41ae4a985745c7b79bbc62f59bb5a
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 02/25/2022
ms.locfileid: "8354242"
---
# <a name="system-configuration"></a>Sistēmas konfigurācija

Lai piekļūtu sistēmas konfigurācijām auditorijas ieskatos, kreisajā navigācijas joslā atlasiet **AdministratorSystem** > **·**, lai skatītu sistēmas uzdevumu un procesu sarakstu.

Lapā **Sistēma** ir šādas cilnes:
- [Statuss](#status-tab)
- [Plānot](#schedule-tab)
- [API lietojums](#api-usage-tab)
- [Par](#about-tab)
- [VispārīgI](#general-tab)
- [Drošība](#security-tab)

:::image type="content" source="media/system-tabs.png" alt-text="Iestatījumu cilnes sistēmas lapā.":::

## <a name="status-tab"></a>Cilne Statuss

Cilne **Statuss** ļauj izsekot uzdevumu norisei, datu norīšanai, datu eksportam un vairākiem citiem svarīgiem produktu procesiem. Pārskatiet šajā cilnē esošo informāciju, lai nodrošinātu aktīvo uzdevumu un procesu pilnīgumu.

Šajā cilnē ir iekļautas tabulas ar statusu un dažādu procesu apstrādes informāciju. Katrā tabulā tiek izsekots uzdevuma **Nosaukums** un tā atbilstošā entītija, tā pēdējās izpildes **Statuss** un **Pēdējā atjaunināšana**. Detalizētu informāciju par pēdējiem vairākiem braucieniem var skatīt, atlasot uzdevuma vai procesa nosaukumu. 

Atlasiet statusu blakus uzdevumam vai procesam **kolonnā Statuss**, lai atvērtu **rūti Detalizēta informācija par** norisi.

   :::image type="content" source="media/system-progress-details.png" alt-text="Sistēmas norises detalizētas informācijas rūts":::

### <a name="status-definitions"></a>Statusa definīcijas

Sistēma uzdevumiem un procesiem izmanto šādus statusus:

|Statuss  |Definīcija  |
|---------|---------|
|Atcelta |Lietotājs atcēla apstrādi pirms tās pabeigšanas.   |
|Neizdevās   |Veicot datu uzņemšanu, radās kļūdas.         |
|Kļūme  |Apstrāde neizdevās.  |
|Nav sākts   |Datu avots nesatur datus, kas ir uzņemti vai vēl ir melnraksta režīmā.         |
|Apstrāde  |Notiek uzdevums vai process.  |
|Notiek atsvaidzināšana    |Notiek datu uzņemšana. Šo darbību varat atcelt, kolonnā **Darbības** atlasot **Apturēt atsvaidzināšanu**. Apturot datu avota atsvaidzināšanu, tas atkal kļūs tāds pats kā pēdējās atsvaidzināšanas brīdī.       |
|Izlaista  |Uzdevums vai process tika izlaists. Viens vai vairāki pakārtotie procesi, no kuriem atkarīgs šis uzdevums, neizdodas vai tiek izlaisti.|
|Sekmīgs  |Uzdevums vai process ir veiksmīgi pabeigts. Datu avotiem norāda, ka dati ir veiksmīgi uzņemti, ja kolonnā Atsvaidzināts **ir** norādīts laiks.|
|Ievietota rindā | Apstrāde tiek stāvēta rindā un tiks sākta, kad būs pabeigti visi augšupējie uzdevumi un procesi. Papildinformāciju skatiet sadaļā [Atsvaidzināt procesus](#refresh-processes).|

### <a name="refresh-processes"></a>Atsvaidzināšanas procesi

Uzdevumu un procesu atsvaidzināšana tiek palaista saskaņā ar konfigurēto [grafiku](#schedule-tab). 

|Process  |Apraksts  |
|---------|---------|
|Darbības  |Darbojas manuāli (vienreizēja atsvaidzināšana). Atkarīgs no sapludināšanas procesa. Ieskati ir atkarīgi no to apstrādes.|
|Analīzes saistīšana |Darbojas manuāli (vienreizēja atsvaidzināšana). Atkarīgs no segmentiem.  |
|Analīzes sagatavošana |Darbojas manuāli (vienreizēja atsvaidzināšana). Atkarīgs no segmentiem.  |
|Datu sagatavošana   |Atkarīgs no sapludināšanas.   |
|Datu avoti   |Esiet neatkarīgi no citiem procesiem. Atbilstība ir atkarīga no šī procesa sekmīgas pabeigšanas.  |
|Bagātinājumi   |Darbojas manuāli (vienreizēja atsvaidzināšana). Atkarīgs no sapludināšanas procesa. |
|Eksporta galamērķi |Darbojas manuāli (vienreizēja atsvaidzināšana). Atkarīgs no segmentiem.  |
|Ieskati |Darbojas manuāli (vienreizēja atsvaidzināšana). Atkarīgs no segmentiem.  |
|Informācija   |Atkarīgs no sapludināšanas.   |
|Saskaņot |Atkarīga no to datu avotu apstrādes, kuri tiek izmantoti atbilstības definīcijā.      |
|Mērījumi  |Darbojas manuāli (vienreizēja atsvaidzināšana). Atkarīgs no sapludināšanas procesa.  |
|Sapludināšana   |Atkarīga no atbilstības procesa pabeigšanas. Segmenti, mērījumi, bagātināšana, meklēšana, darbības, prognozes un datu sagatavošana ir atkarīga no sekmīgas šī procesa pabeigšanas.   |
|Profili   |Darbojas manuāli (vienreizēja atsvaidzināšana). Atkarīgs no sapludināšanas procesa. |
|Meklējiet   |Darbojas manuāli (vienreizēja atsvaidzināšana). Atkarīgs no sapludināšanas procesa. |
|Segmenti  |Darbojas manuāli (vienreizēja atsvaidzināšana). Atkarīgs no sapludināšanas procesa. Ieskati ir atkarīgi no to apstrādes.|
|Sistēma   |Atkarīga no atbilstības procesa pabeigšanas. Segmenti, mērījumi, bagātināšana, meklēšana, darbības, prognozes un datu sagatavošana ir atkarīga no sekmīgas šī procesa pabeigšanas.   |
|User  |Darbojas manuāli (vienreizēja atsvaidzināšana). Atkarīgs no entītijām.  |

Atlasiet procesa statusu, lai skatītu visa tā darba norises detaļas. Iepriekš minētie atsvaidzināšanas procesi var palīdzēt saprast, ko varat darīt, lai risinātu uzdevumu vai procesu, kurā **ir izlaists** vai **ievietots** rindā.

## <a name="schedule-tab"></a>Plānošanas cilne

Izmantojiet cilni **Grafiks**, lai plānotu visu jūsu uzņemto [datu avotu automātisko atsvaidzināšanu](data-sources.md). Automātiskā atsvaidzināšana palīdz nodrošināt, ka jūsu datu avotu atjauninājumi tiek atspoguļoti vienotajos klientu profilos.

> [!NOTE]
> Jūsu pārvaldītie datu avoti tiek atsvaidzināti pēc saviem grafikiem. Lai ieplānotu jūsu pārvaldīto datu avotu atsvaidzināšanu, konfigurējiet atsvaidzināšanas iestatījumus šajā konkrētajā datu avots lapā **Datu avoti**.
> :::image type="content" source="media/PPDF-edit-refresh.png" alt-text="Power Platform Datu plūsmas atsvaidzināšanas iestatījumi.":::

1. Sadaļā auditorijas ieskati ejiet uz **Administrēšana** > **Sistēma** un atlasiet cilni **Grafiks**.

2. Plānotās atsvaidzināšanas noklusējuma stāvoklis ir **Izslēgts**. Lai iespējotu plānoto atsvaidzināšanu, ekrāna augšdaļā mainiet slēdža pozīciju uz **Ieslēgta**.

3. Izvēlieties starp **Katru nedēļu** (noklusējuma) un **Katru dienu**. Ja plānojat iknedēļas atsvaidzināšanu, atlasiet vienu vai vairākas dienas, kurās vēlaties izpildīt atsvaidzināšanu.

4. Iestatiet **Laika joslu**, tad izmantojiet **Laika** nolaižamo sarakstu, lai iestatītu atsvaidzināšanas laiku. Kad esat pabeidzis, atlasiet **Iestatīt**. Ja vēlaties ieplānot vairākas atsvaidzināšanas vienā dienā, atlasiet **Pievienot citu laiku**.

5. Lai veiktās izmaiņas stātos spēkā, atlasiet **Saglabāt**.

## <a name="about-tab"></a>Cilne Par

Cilnē **Par** ir norādīts jūsu organizācijas **Parādāmais nosaukums**, aktīvais **Vides ID**, **Reģions** un **Sesijas ID**. Ja jums ir vairāk nekā viena darba vide, katrai videi vajadzētu piešķirt viegli identificējamu parādāmo nosaukumu.

## <a name="general-tab"></a>Cilne Vispārīgi

Cilnē **Vispārīgi** varat mainīt valodu un valsts/reģiona formātu.

Customer Insights [atbalsta daudzas valodas](/dynamics365/get-started/availability). Lietotne izmanto Jūsu valodas preferenci, lai rādītu elementus, piemēram, izvēlni, informācijas paneļa apzīmējumu tekstu un ziņojumus vēlamajā valodā.

Manuāli ievadītie importētie dati un informācija netiek tulkota.

### <a name="update-the-settings"></a>Atjaunināt iestatījumus

Lai mainītu vēlamo valodu, nolaižamajā izvēlnē izvēlieties **Valodu**.

Lai mainītu datumu, laika un skaitļu vēlamo formatējumu, izmantojiet nolaižamo izvēlni **Valsts/reģiona formāts**. Šajā laukā tiek rādīts formatēšanas priekšskatījums. Ja izvēlēsities jaunu valodu, sistēma automātiski piedāvās atlasi.

Atlasiet **Saglabāt**, lai apstiprinātu atlases.

## <a name="api-usage-tab"></a>API lietošanas cilne

Skatiet detalizētu informāciju par reāllaika API lietošanu un skatiet, kuri notikumi notika konkrētajā laika posmā. Nolaižamajā izvēlnē izvēlieties laika periodu opcijai **Atlasīt laika periodu**. 

**API lietojumā** ir trīs sadaļas: 
- **API izsaukumi** — diagramma, kas atlasītajā laika posmā vizualizē apkopoto izsaukumu skaitu uz API.

- **Datu pārsūtīšana** — diagramma, kurā redzams datu daudzums, kas atlasītajā laika posmā tika pārsūtīts, izmantojot API.

-  **Darbības** — tabula ar rindām katrai pieejamai API operācijai un detalizēta informācija par operāciju izmantošanu. Varat atlasīt operācijas nosaukumu, lai pārietu [uz API atsauci](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).

   Darbības, kas izmanto [reāllaika datu norīšanu](real-time-data-ingestion.md), satur pogu ar binokļa simbolu, lai skatītu reāllaika API lietojumu. Atlasiet pogu, lai atvērtu sānu rūti, kurā ir detalizēta lietošanas instrukcija par reāllaika API izmantošanu pašreizējā vidē.   
   Lai izvēlētos, kā vislabāk sniegt reāllaika mijiedarbības, izmantojiet **Grupēt pēc** lodziņu rūtī **Reāllaika API lietojums**. Grupējiet datus pēc API metodes, entītijas nosaukums (izveidotā entītija), izveidoja (notikuma avots), rezultāts (veiksmīgi vai kļūme) vai kļūdu kodi. Dati ir pieejami kā vēstures diagramma un kā tabula.

## <a name="security-tab"></a>Drošības cilne

Izmantojot cilni **Drošība**, varat saistīt un pārvaldīt savu [Azure atslēgas akreditācijas datu komplektu](/azure/key-vault/general/basic-concepts) ar vidi.
Īpašo atslēgas akreditācijas datu glabātuvi var izmantot, lai izveidotu un izmantotu slepeno informāciju organizācijas ierobežojošajā robežu ietvaros. Auditorijas ieskati var izmantot slepeno informāciju Azure Key Vault, lai [iestatītu savienojumus](connections.md) ar trešo pušu sistēmām.

Papildinformāciju skatiet [Ievadiet savu Azure Key Vault](use-azure-key-vault.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
