---
title: Skatīt sistēmas konfigurāciju
description: Informācija par sistēmas iestatījumiem pakalpojumā Dynamics 365 Customer Insights.
ms.date: 08/09/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-status
- ci-system-about
- ci-system-general
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: 2498814a3d2e6330124fb97c036b9b310bcf1f7a
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 08/10/2022
ms.locfileid: "9246256"
---
# <a name="view-system-configuration"></a>Skatīt sistēmas konfigurāciju

Skatiet sistēmas informāciju, sistēmas statusu un API lietojumu.

## <a name="view-api-usage"></a>Skatīt API lietojumu

Skatiet detalizētu informāciju par reāllaika API lietojumu un uzziniet, kuri notikumi ir notikuši noteiktā laika posmā.

1. Dodieties uz administrēšanas sistēma un atlasiet **cilni API lietojums** > **.** **·**

1. **Atlasiet skatāmo laika posmu**.

   **API lietojuma** lapā ir trīs sadaļas:

   - **API izsaukumi** — diagramma, kas atlasītajā laika posmā vizualizē apkopoto izsaukumu skaitu uz API.
   - **Datu pārsūtīšana** — diagramma, kurā redzams datu daudzums, kas atlasītajā laika posmā tika pārsūtīts, izmantojot API.
   - **Darbības** — tabula ar rindām katrai pieejamai API operācijai un detalizēta informācija par operāciju izmantošanu. Atlasiet operācijas nosaukumu, lai pārietu [uz API atsauci](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).

   Operācijas, kurās tiek izmantota [reāllaika datu norīšana](real-time-data-ingestion.md), satur binokulāru simbolu, lai skatītu reāllaika API lietojumu.

   1. Atlasiet binokli, lai atvērtu reāllaika **API lietošanas** rūti, kurā ir detalizēta informācija par operācijas lietojumu.
   1. **Atlasiet skatāmo laika posmu**.
   1. Izmantojiet **lodziņu Grupēt pēc**, lai izvēlētos, kā vislabāk parādīt reāllaika mijiedarbību. Grupēt datus pēc API **metodes**, **juridiskās personas kvalificēta nosaukuma** (pieņemtās juridiskās personas), **Izveidotā (** notikuma avota), **rezultāta** (veiksmes vai neveiksmes) vai **kļūdu kodiem**. Dati ir pieejami kā vēstures diagramma un kā tabula.

## <a name="view-system-information"></a>Skatīt sistēmas informāciju

Skatiet vides parādāmo nosaukumu, ID, reģionu, veidu un sesijas ID.

1. Dodieties uz **administrēšanas** > **sistēma** un atlasiet **cilni Par**.

1. Lai skatītu valodu un valsti/reģionu, atlasiet **cilni Vispārīgi**.

### <a name="update-preferred-language-or-countryregion"></a>Vēlamās valodas vai valsts/reģiona atjaunināšana

Customer Insights [atbalsta daudzas valodas](/dynamics365/get-started/availability). Lietotne izmanto Jūsu valodas preferenci, lai rādītu elementus, piemēram, izvēlni, informācijas paneļa apzīmējumu tekstu un ziņojumus vēlamajā valodā.

Manuāli ievadītie importētie dati un informācija netiek tulkota.

1. Dodieties uz **administrēšanas** > **sistēma** un atlasiet **cilni Vispārīgi**.

1. Lai mainītu vēlamo valodu, nolaižamajā izvēlnē izvēlieties **Valodu**.

1. Lai mainītu datumu, laika un skaitļu vēlamo formatējumu, izmantojiet nolaižamo izvēlni **Valsts/reģiona formāts**. Tiek parādīts formatēšanas priekšskatījums. Sistēma automātiski iesaka atlasi, kad izvēlaties jaunu valodu.

1. Atlasiet **Saglabāt**.

## <a name="view-system-status"></a>Skatīt sistēmas statusu

Sekojiet līdzi uzdevumu norīšanas, datu norīšanas, datu eksportēšanas un vairāku citu svarīgu produktu procesu norisei. Pārskatiet informāciju, lai pārliecinātos par savu aktīvo uzdevumu un procesu pilnīgumu.

1. Dodieties uz **administrēšanas** > **sistēma** un atlasiet **cilni Statuss**.

   Statuss un informācijas apstrāde dažādiem procesiem. **Skatiet uzdevuma nosaukumu**, **tā pēdējās izpildes statusu** un to, kad tas pēdējo reizi tika **atjaunināts**.

1. Lai skatītu detalizētu informāciju par pēdējām vairākām reizēm, atlasiet uzdevumu vai procesa nosaukumu.

1. Lai skatītu detalizētu informāciju par uzdevuma norisi, atlasiet statusu. Tiek **parādīta progresa detalizētās informācijas** rūts.

   :::image type="content" source="media/system-progress-details.png" alt-text="Detalizētas informācijas par sistēmas progresu rūts":::

1. Lai skatītu detalizētu informāciju par visu uzdevumu norisi, atlasiet **Visa darbplūsma**.

### <a name="status-definitions"></a>Statusa definīcijas

Sistēma uzdevumiem un procesiem izmanto šādus statusus:

|Statuss  |Definīcija  |
|---------|---------|
|Atcelta |Lietotājs atcēla uzdevumu vai procesu, pirms tas tika pabeigts.   |
|Neizdevās   |Uzdevumā vai procesā radās kļūdas.         |
|Kļūme  |Uzdevums vai process nav izdevies.  |
|Nav sākts   |Datu avots vēl nav uzņemti dati vai uzdevums joprojām ir melnraksta režīmā.         |
|Apstrāde  |Notiek uzdevums vai process.  |
|Notiek atsvaidzināšana    |Notiek uzdevums vai process. Lai atceltu šo darbību, atlasiet **Atsvaidzināt** un **atcelt darbu**. Pārtraucot uzdevuma vai procesa atsvaidzināšanu, tas tiks atgriezts pēdējā atsvaidzināšanas stāvoklī.       |
|Izlaista  |Uzdevums vai process tika izlaists. Viens vai vairāki pakārtotie procesi, no kuriem atkarīgs šis uzdevums, neizdodas vai tiek izlaisti.|
|Sekmīgs  |Uzdevums vai process veiksmīgi pabeigts. Datu avotiem norāda, ka dati ir veiksmīgi norīti, ja kolonnā Atsvaidzināts **ir minēts** laiks.|
|Ievietota rindā | Apstrāde ir rindas kārtībā un sāksies, kad būs pabeigti visi augšupējie uzdevumi un procesi. Papildinformāciju skatiet sadaļā [Atsvaidzināšanas procesi](#refresh-processes).|

### <a name="refresh-processes"></a>Atsvaidzināšanas procesi

Uzdevumu un procesu atsvaidzināšana tiek izpildīta saskaņā ar konfigurēto [grafiku](schedule-refresh.md).

|Process  |Apraksts  |
|---------|---------|
|Darbības  |Darbojas manuāli (vienreizēja atsvaidzināšana). Atkarīgs no sapludināšanas procesa. Ieskati ir atkarīgi no to apstrādes.|
|Analīzes saistīšana |Darbojas manuāli (vienreizēja atsvaidzināšana). Atkarīgs no segmentiem.  |
|Analīzes sagatavošana |Darbojas manuāli (vienreizēja atsvaidzināšana). Atkarīgs no segmentiem.  |
|Datu sagatavošana   |Nepieciešama entītija, ar kuru darboties. Datu avots entītijas ir atkarīgas no norīšanas. Bagātinātas vienības ir atkarīgas no bagātināšanas. Klienta entītija ir atkarīga no sapludināšanas.  |
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

Atlasiet procesa statusu, lai skatītu detalizētu informāciju par visa tā darba norisi, kurā tas bija. Iepriekš minētie atsvaidzināšanas procesi var palīdzēt saprast, ko varat darīt, lai risinātu izlaistu **vai** **rindas** uzdevumu vai procesu.


[!INCLUDE [footer-include](includes/footer-banner.md)]
