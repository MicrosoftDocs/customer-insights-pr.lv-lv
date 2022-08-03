---
title: Pasākumu pārskats
description: Uzziniet, kā pasākumi palīdz analizēt un atspoguļot jūsu uzņēmuma veiktspēju.
ms.date: 03/24/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.author: wameng
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-measures
- ci-measure-builder
- ci-measure-template
- ci-enrichment-details
- customerInsights
ms.openlocfilehash: ead57ccbdcaf9f86ee54d1f15de71a63f2e1081b
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170830"
---
# <a name="measures-overview"></a>Pasākumu pārskats

Mēri palīdz labāk izprast klientu paradumus un uzņēmuma veiktspēju. Tie aplūko atbilstošās vērtības no [vienotajiem profiliem](data-unification.md). Piemēram, uzņēmums vēlas redzēt *kopējos tēriņus uz klientu*, lai izprastu katra klienta pirkumu vēsturi vai izmērīt *uzņēmuma kopējos pārdošanas apjomus*, lai izprastu kopējā līmeņa ieņēmumus visā uzņēmumā.

Izveidojiet pasākumus, lai plānotu biznesa aktivitātes, veicot vaicājumus klientu datos un izgūstot ieskatus. Piemēram, izveidojiet kopējo tēriņu uz vienu klientu *un* kopējās atdeves uz vienu klientu *mēru*, lai palīdzētu identificēt klientu grupu ar lielu tēriņu, bet lielu atdevi. Pēc tam izveidojiet segmentu [,](segments.md) pamatojoties uz šiem pasākumiem, lai veiktu nākamās labākās darbības.

## <a name="create-a-measure"></a>Mēra izveide

Izvēlieties, kā izveidot mēru, pamatojoties uz savu mērķauditoriju.

# <a name="individual-consumers-b-to-c"></a>[Atsevišķi patērētāji (B2C)](#tab/b2c)

- No nulles ar mērījumu veidotāju: [Izveidojiet savu](measure-builder.md).
- No bieži izmantotajiem mēriem: [izmantojiet iepriekš definētas](measure-templates.md) veidnes.

# <a name="business-accounts-b-to-b"></a>[Uzņēmumu konti (B2B)](#tab/b2b)

No nulles ar mērījumu veidotāju: [Izveidojiet savu](measure-builder.md).

---

## <a name="manage-existing-measures"></a>Esošo pasākumu pārvaldība

Dodieties uz **lapu Mēri**, lai skatītu izveidotos mērus, to statusu, mēra tipu un pēdējo reizi, kad dati tika atsvaidzināti. Mēru sarakstu var kārtot pēc jebkuras kolonnas vai izmantot meklēšanas lodziņu, lai atrastu pārvaldāmo mēru.

Atlasiet blakus mēram, lai skatītu pieejamās darbības. Atlasiet mēra nosaukumu, lai priekšskatītu izvadi un lejupielādētu CSV failu.

:::image type="content" source="media/measures-actions.png" alt-text="Darbības, lai pārvaldītu atsevišķus mērus."lightbox="media/measures-actions.png":::

- **Rediģējiet** mēru, lai mainītu tā rekvizītus.
- **Atsvaidziniet** mēru, lai iekļautu jaunākos datus.
- **Pārdēvējiet** mēru.
- **Aktivizējiet** vai **deaktivizējiet** mēru. Neaktīvie mēri netiks atsvaidzināti ieplānotas [atsvaidzināšanas](system.md#schedule-tab) laikā, un statuss **tiks** norādīts kā **izlaists**, kas norāda, ka atsvaidzināšana pat netika mēģināta.
- **Atzīmējiet** tagus, lai [pārvaldītu pasākuma tagus](work-with-tags-columns.md#manage-tags).
- **Dzēsiet** mēru.
- **Kolonnas**, lai [pielāgotu parādītās kolonnas](work-with-tags-columns.md#customize-columns).
- **Filtrējiet**, lai filtrētu [tagus](work-with-tags-columns.md#filter-on-tags).
- **Meklējiet vārdu**, lai meklētu pēc mēra nosaukuma.

## <a name="refresh-measures"></a>Atsvaidzināšanas pasākumi

Mērus var atsvaidzināt pēc automātiska grafika vai atsvaidzināt manuāli pēc pieprasījuma. Lai manuāli atsvaidzinātu vienu vai vairākus mērus, atlasiet tos un izvēlieties **Atsvaidzināt**. Lai [ieplānotu automātisku atsvaidzināšanu](system.md#schedule-tab), dodieties uz **administrēšanas** > **sistēmas** > **grafiku**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
