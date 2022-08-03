---
title: Izveidojiet vienkāršus segmentus ar ātriem segmentiem
description: Izveidojiet vienkāršus klientu segmentus, lai tos grupētu, pamatojoties uz dažādiem atribūtiem.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-segments
- ci-segment-builder
- ci-segment-details
- customerInsights
ms.openlocfilehash: 98260371a17ff8a05912cc1bc08c67fbe9755727
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 07/18/2022
ms.locfileid: "9171160"
---
# <a name="create-simple-segments-with-quick-segments"></a>Izveidojiet vienkāršus segmentus ar ātriem segmentiem

Izmantojot ātros segmentus, varat ātri izveidot vienkāršus segmentus, izmantojot vienu operatoru, lai gūtu ātrākus ieskatus. Ātrie segmenti tiek atbalstīti tikai vidēs, kas ir pieejamas **atsevišķiem klientiem**.

## <a name="create-a-new-segment-with-quick-segments"></a>Jauna segmenta izveide ar ātriem segmentiem

1. Ejiet uz **Segmenti**.

1. Atlasiet **Jauns** > **izveidot no**.
   - Atlasiet opciju **Profili**, lai izveidotu segmentu, kura pamatā ir *vienotā klienta* entītija.
   - Atlasiet opciju **Pasākumi**, lai izveidotu segmentu ap iepriekš izveidotajiem pasākumiem.
   - Atlasiet opciju **Informācijas apkopošana**, lai izveidotu segmentu ap vienu no izvades entitījām, kuras izveidojāt, izmantojot iespēju **Prognozes** vai **Pielāgotie modeļi**.

1. Dialoglodziņā **Jauns ātrais segments** atlasiet atribūtu no nolaižamā saraksta **Lauks**. Pamatojoties uz jūsu izvēli, sistēma nodrošina dažādas vērtības.
   - Kategoriskiem laukiem tiek parādīts 10 populārākais klientu skaits. Izvēlieties **Vērtība** un atlasiet **Pārskatīt**.
   - Skaitliskajam atribūtam sistēma parāda, kāda atribūta vērtība ietilpst katra klienta procentilē. Izvēlieties **Operators** un **Vērtība** un pēc tam atlasiet vienumu **Pārskatīt**.

1. Sistēma nodrošina aptuveno segmenta **lielumu**. Izvēlieties, vai ģenerēt definēto segmentu, vai atgriezieties, lai izvēlētos citu lauku.

   :::image type="content" source="media/quick-segment-name.png" alt-text="Ātrā segmenta nosaukums un novērtējums.":::

1. **Norādiet nosaukuma** un **izvades entītijas nosaukumu** savam segmentam. Pēc izvēles pievienojiet [atzīmes](work-with-tags-columns.md#manage-tags).

1. Lai izveidotu segmentu, atlasiet opciju **Saglabāt**. Tiek **parādīta lapa Segmenti**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="next-steps"></a>Nākamās darbības

[Eksportējiet segmentu](export-destinations.md) un izpētiet [Klienta kartes integrāciju](customer-card-add-in.md), lai izmantotu segmentus citās lietojumprogrammās.

[!INCLUDE [footer-include](includes/footer-banner.md)]
