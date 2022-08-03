---
title: Inkrementāla atsvaidzināšana Power Query un Azure Data Lake datu avoti
description: Atsvaidziniet jaunus un atjauninātus datus lieliem datu avotiem, kuru pamatā Power Query ir vai Azure datu ezera datu avoti.
ms.date: 05/30/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-schedule
- customerInsights
ms.openlocfilehash: de39743eb8728fac34e417724c5f73bf44309c89
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 07/28/2022
ms.locfileid: "9207146"
---
# <a name="incremental-refresh-for-power-query-and-azure-data-lake-data-sources"></a>Inkrementāla atsvaidzināšana Power Query un Azure Data Lake datu avoti

Pakāpeniska atsvaidzināšana datu avotiem, kuru pamatā Power Query ir vai Azure data lake, nodrošina šādas priekšrocības:

- **Ātrāka atsvaidzināšana** — Tiek atsvaidzināti tikai tie dati, kas tika mainīti. Piemēram, jūs varat atsvaidzināt tikai pēdējās piecas vēstures datu kopas dienas.
- **Lielāka uzticamība** — Ar mazākiem atsvaidzināšanas savienojumiem nav nepieciešams uzturēt savienojumus ar netveramām avota sistēmām tik ilgi, samazinot savienojuma problēmu risku.
- **Samazināts resursu patēriņš** — Atsvaidzinot tikai datu apakškopu no jūsu datu kopapjoma, tiek efektīvāk izmantoti skaitļošanas resursi un samazināta ietekme uz vidi.

## <a name="configure-incremental-refresh-for-data-sources-based-on-power-query"></a>Datu avotu inkrementālās atsvaidzināšanas konfigurēšana, pamatojoties uz Power Query

Customer Insights ļauj pakāpeniski atsvaidzināt datu avotus, kas importēti, izmantojot Power Query šo atbalsta inkrementālo norīšanu. Piemēram, Azure SQL datu bāzes ar datuma un laika laukiem, kas norāda, kad pēdējo reizi tika atjaunināti datu ieraksti.

1. [Izveidojiet jaunu datu avots, pamatojoties uz Power Query](connect-power-query.md).

1. Atlasiet datu avots, kas atbalsta inkrementālu atsvaidzināšanu, piemēram [, Azure SQL datu bāzi](/power-query/connectors/azuresqldatabase).

1. Atlasiet uzņemamās entitījas vai tabulas.

1. Pabeidziet transformācijas darbības un atlasiet **Tālāk**.

1. Dialoglodziņā **Iestatīt inkrementālo atsvaidzināšanu** atlasiet **Iestatīt**, lai atvērtu sadaļu **Inkrementālā atsvaidzināšanas iestatījumi**. Ja atlasīsiet **Izlaist**, datu avots atsvaidzinās viss datu kopu.
   > [!TIP]
   > Inkrementālo atsvaidzināšanu var lietot arī vēlāk, rediģējot esošu datu avotu.

1. Sadaļā **Inkrementālās atsvaidzināšanas iestatījumi** jūs konfigurēsiet inkrementālo atsvaidzināšanu visām entītijām, ko atlasījāt, veidojot datu avotu.

   :::image type="content" source="media/incremental-refresh-settings.png" alt-text="Konfigurējiet inkrementālos atsvaidzināšanas iestatījumus.":::

1. Atlasiet entītiju un norādiet šādu informāciju:

   - **Definēt primāro atslēgu**: Atlasiet entītijas vai tabulas primāro atslēgu.
   - **Definēt lauku “pēdējoreiz atjaunināts”**: Šajā laukā tiek parādīti tikai datuma un laika tipa atribūti. Atlasiet atribūtu, kas norāda, kad ieraksti tika atjaunināti pēdējoreiz. To izmantos, lai identificētu ierakstus, kuri ietilpst inkrementālās atsvaidzināšanas laika periodā.
   - **Pārbaudīt, vai ir pieejami atjauninājumi**: Norādiet, cik ilgam ir jābūt inkrementālās atsvaidzināšanas laika periodam.

1. Atlasiet **Saglabāt**, lai pabeigtu datu avota izveidi. Sākotnējā datu atsvaidzināšana būs pilna atsvaidzināšana. Pēc tam inkrementālā datu atsvaidzināšana notiek, kā tas ir konfigurēts iepriekšējā darbībā.

## <a name="configure-incremental-refresh-for-azure-data-lake-data-sources"></a>Inkrementālās atsvaidzināšanas konfigurēšana Azure datu ezera datu avotiem

Customer Insights ļauj pakāpeniski atsvaidzināt datu avotus, kas savienoti Azure Data Lake Storage ar. Lai entītijai izmantotu inkrementālu norīšanu un atsvaidzināšanu, konfigurējiet šo entītiju, pievienojot Azure datu ezera datu avots vai jaunāku versiju, rediģējot datu avots. Entītijas datu mapē jābūt šādām mapēm:

- **FullData**: mape ar datu failiem, kas satur sākotnējos ierakstus
- **IncrementalData**: mape ar datuma/laika hierarhijas mapēm **gggg/mm/dd/hh** formātā, kurā ir inkrementālie atjauninājumi. **hh** apzīmē atjauninājumu UTC stundu un satur **mapes Upserts** un **Deletes**. **Upserts** satur datu failus ar esošo ierakstu vai jaunu ierakstu atjauninājumiem. **Deletes** satur datu failus ar ierakstiem, kas jānoņem.

1. Pievienojot vai rediģējot datu avots, naviģējiet uz **entītijas rūti Atribūti**.

1. Pārskatiet atribūtus. Pārliecinieties, vai izveidots vai pēdējo reizi atjaunināts datuma atribūts ir iestatīts *ar dateTime* **Data formātu** un *kalendāra.datuma* **semantisko tipu**. Ja nepieciešams, rediģējiet atribūtu un atlasiet **Gatavs**.

1. **Rūtī Atlasīt entītijas** rediģējiet entītiju. Ir atzīmēta izvēles **rūtiņa Inkrementālā norīšana**.

   :::image type="content" source="media/ADLS_inc_refresh.png" alt-text="Entītiju konfigurēšana datu avotā inkrementālajai atsvaidzināšanai.":::

   1. Pārlūkojot atrodiet saknes mapi, kurā ir .csv vai .parketa faili, lai iegūtu pilnus datus, papildu datu palielinājumus un papildu datu dzēšanu.
   1. Ievadiet pilno datu paplašinājumu un abus inkrementālos failus (\. csv vai \. parketu).
   1. .csv failiem atlasiet kolonnu norobežotāju un, ja vēlaties, lai faila pirmā rinda būtu kolonnas galvene.
   1. Atlasiet **Saglabāt**.

1. Pēdējās **atjaunināšanas** gadījumā atlasiet datuma laikspiedola atribūtu.

1. **Ja primārā atslēga** nav atlasīta, atlasiet primāro atslēgu. Primārā atslēga ir entītijai unikāls atribūts. Lai atribūts būtu derīga primārā atslēga, tajā nedrīkst ietvert vērtību dublikātus, trūkstošās vērtības vai nulles vērtības. Virknes, vesela skaitļa un GUID datu tipa atribūti tiek atbalstīti kā primārās atslēgas.

1. Atlasiet **Aizvērt**, lai saglabātu un aizvērtu rūti.

1. Turpiniet ar datu avots pievienošanu vai rediģēšanu.

[!INCLUDE [footer-include](includes/footer-banner.md)]
