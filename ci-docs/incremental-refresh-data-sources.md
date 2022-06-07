---
title: Inkrementāla atsvaidzināšana Power Query datu avotiem, kuru pamatā ir
description: Atsvaidzināt jaunus un atjauninātus datus lieliem datu avotiem, pamatojoties uz Power Query.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
searchScope:
- ci-system-schedule
- customerInsights
ms.openlocfilehash: 3d21baf9804f300802b066df0183fc8f01abba9a
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643669"
---
# <a name="incremental-refresh-for-data-sources-based-on-power-query"></a>Inkrementāla atsvaidzināšana datu avotiem, pamatojoties uz Power Query

Šajā rakstā aplūkots, kā konfigurēt inkrementālo atsvaidzināšanu datu avotiem, pamatojoties uz Power Query.

Inkrementālajai datu avotu atsvaidzināšanai ir šādas priekšrocības:

- **Ātrāka atsvaidzināšana** — Tiek atsvaidzināti tikai tie dati, kas tika mainīti. Piemēram, jūs varat atsvaidzināt tikai pēdējās piecas vēstures datu kopas dienas.
- **Lielāka uzticamība** — Ar mazākiem atsvaidzināšanas savienojumiem nav nepieciešams uzturēt savienojumus ar netveramām avota sistēmām tik ilgi, samazinot savienojuma problēmu risku.
- **Samazināts resursu patēriņš** — atsvaidzinot tikai datu apakškopu no jūsu datu kopapjoma, tiek efektīvāk izmantoti skaitļošanas resursi un tiek samazināta ietekme uz vidi.

## <a name="configure-incremental-refresh"></a>Konfigurēt inkrementālo atsvaidzināšanu

Customer Insights ļauj pakāpeniski atsvaidzināt datu avotus, kas importēti, izmantojot Power Query šo atbalsta inkrementālo uzņemšanu. Piemēram, Azure SQL datu bāzes ar datuma un laika laukiem, kas norāda, kad pēdējo reizi tika atjaunināti datu ieraksti.

1. [Izveidojiet jaunu datu avots pamatojoties uz Power Query](connect-power-query.md).

1. Norādiet **datu avots nosaukumu**.

1. Atlasiet datu avots, kas atbalsta inkrementālu atsvaidzināšanu, piemēram [, Azure SQL datu bāzi](/power-query/connectors/azuresqldatabase).

1. Atlasiet uzņemamās entitījas vai tabulas.

1. Pabeidziet transformācijas darbības un atlasiet **Tālāk**.

1. Dialoglodziņā **Iestatīt inkrementālo atsvaidzināšanu** atlasiet **Iestatīt**, lai atvērtu sadaļu **Inkrementālā atsvaidzināšanas iestatījumi**. Ja atlasīsiet **Izlaist**, datu avots atsvaidzinās viss datu kopu.
   > [!TIP]
   > Inkrementālo atsvaidzināšanu var lietot arī vēlāk, rediģējot esošu datu avotu.

1. Sadaļā **Inkrementālās atsvaidzināšanas iestatījumi** jūs konfigurēsiet inkrementālo atsvaidzināšanu visām entītijām, ko atlasījāt, veidojot datu avotu.

   :::image type="content" source="media/incremental-refresh-settings.png" alt-text="Entītiju konfigurēšana datu avotā inkrementālajai atsvaidzināšanai.":::

1. Atlasiet entītiju un norādiet šādu informāciju:

   - **Definēt primāro atslēgu**: Atlasiet entītijas vai tabulas primāro atslēgu.
   - **Definēt lauku “pēdējoreiz atjaunināts”**: Šajā laukā tiek parādīti tikai datuma un laika tipa atribūti. Atlasiet atribūtu, kas norāda, kad ieraksti tika atjaunināti pēdējoreiz. To izmantos, lai identificētu ierakstus, kuri ietilpst inkrementālās atsvaidzināšanas laika periodā.
   - **Pārbaudīt, vai ir pieejami atjauninājumi**: Norādiet, cik ilgam ir jābūt inkrementālās atsvaidzināšanas laika periodam.

1. Atlasiet **Saglabāt**, lai pabeigtu datu avota izveidi. Sākotnējā datu atsvaidzināšana būs pilna atsvaidzināšana. Pēc tam inkrementālā datu atsvaidzināšana notiek, kā tas ir konfigurēts iepriekšējā darbībā.


[!INCLUDE [footer-include](includes/footer-banner.md)]