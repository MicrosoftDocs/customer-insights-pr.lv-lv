---
title: Power Query esošu datu avotu inkrementālā atsvaidzināšana.
description: Atsvaidziniet jaunus un atjauninātus datus lieliem datu avotiem, kas balstīti Power Query.
ms.date: 09/28/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.openlocfilehash: 1af2e4c42dc5890556c90bb3e5ef1aeb0621fda0
ms.sourcegitcommit: dab2cbf818fafc9436e685376df94c5e44e4b144
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 07/13/2021
ms.locfileid: "6554168"
---
# <a name="incremental-refresh-for-data-sources-based-on-power-query"></a>Inkrementālā atsvaidzināšana Power Query bāzes datu avotiem

Inkrementālajai datu avotu atsvaidzināšanai ir šādas priekšrocības:

- **Ātrāka atsvaidzināšana** — Tiek atsvaidzināti tikai tie dati, kas tika mainīti. Piemēram, jūs varat atsvaidzināt tikai pēdējās piecas vēstures datu kopas dienas.
- **Lielāka uzticamība** — Ar mazākiem atsvaidzināšanas savienojumiem nav nepieciešams uzturēt savienojumus ar netveramām avota sistēmām tik ilgi, samazinot savienojuma problēmu risku.
- **Samazināts resursu patēriņš** — Atsvaidzinot tikai datu apakškopu no jūsu datu kopapjoma, tiek efektīvāk izmantoti skaitļošanas resursi un samazināta ietekme uz vidi.

## <a name="configure-incremental-refresh"></a>Konfigurēt inkrementālo atsvaidzināšanu

Auditorijas ieskati ļauj inkrementāli atsvaidzināt datus, kuri ir importēti, izmantojot Power Query, kas atbalsta inkrementālu uzņemšanu. Piemēram, Azure SQL datu bāzes ar datuma un laika laukiem, kas norāda, kad pēdējo reizi tika atjaunināti datu ieraksti.

1. [Jauna Power Query bāzes datu avota izveide](connect-power-query.md).

1. Ierakstiet datu avota nosaukumu.

1. Atlasiet datu avotu, kas atbalsta inkrementālo atsvaidzināšanu, piemēram, Azure SQL datu bāzi.

1. Atlasiet uzņemamās entitījas vai tabulas.

1. Pabeidziet transformācijas darbības un atlasiet **Tālāk**.

1. Dialoglodziņā **Iestatīt inkrementālo atsvaidzināšanu** atlasiet **Iestatīt**, lai atvērtu sadaļu **Inkrementālā atsvaidzināšanas iestatījumi**. Ja atlasīsiet **Izlaist**, datu avots atsvaidzinās viss datu kopu.
   > [!TIP]
   > Inkrementālo atsvaidzināšanu var lietot arī vēlāk, rediģējot esošu datu avotu.

1. Sadaļā **Inkrementālās atsvaidzināšanas iestatījumi** jūs konfigurēsiet inkrementālo atsvaidzināšanu visām entītijām, ko atlasījāt, veidojot datu avotu.

   > [!div class="mx-imgBorder"]
   > ![Entītiju konfigurēšana datu avotā inkrementālajai atsvaidzināšanai.](media/incremental-refresh-settings.png "Entītiju konfigurēšana datu avotā inkrementālajai atsvaidzināšanai")

1. Atlasiet entītiju un norādiet šādu informāciju:

   - **Definēt primāro atslēgu**: Atlasiet entītijas vai tabulas primāro atslēgu.
   - **Definēt lauku “pēdējoreiz atjaunināts”**: Šajā laukā tiek parādīti tikai datuma un laika tipa atribūti. Atlasiet atribūtu, kas norāda, kad ieraksti tika atjaunināti pēdējoreiz. To izmantos, lai identificētu ierakstus, kuri ietilpst inkrementālās atsvaidzināšanas laika periodā.
   - **Pārbaudīt, vai ir pieejami atjauninājumi**: Norādiet, cik ilgam ir jābūt inkrementālās atsvaidzināšanas laika periodam.

1. Atlasiet **Saglabāt**, lai pabeigtu datu avota izveidi. Sākotnējā datu atsvaidzināšana būs pilna atsvaidzināšana. Pēc tam inkrementālā datu atsvaidzināšana notiek, kā tas ir konfigurēts iepriekšējā darbībā.


[!INCLUDE[footer-include](../includes/footer-banner.md)]