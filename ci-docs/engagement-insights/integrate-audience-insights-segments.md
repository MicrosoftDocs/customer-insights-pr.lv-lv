---
title: Auditorijas ieskatu segmentu izmantošana, lai filtrētu iesaistes ieskatu atskaites
description: Izmantojiet auditorijas ieskatu segmentos, veicot interaktīvu analīzi par darbības datiem, kas iegūti ar iesaistes ieskatiem.
ms.date: 07/27/2021
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 9c8c7a1a9216e04ebee100c548afbc745af396ec
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 02/16/2022
ms.locfileid: "8230495"
---
# <a name="use-audience-insights-segments-to-filter-engagement-insights-reports"></a>Auditorijas ieskatu segmentu izmantošana, lai filtrētu iesaistes ieskatu atskaites

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Ar iesaistes ieskatiem var izmantot auditorijas ieskatu segmentos, veicot interaktīvu analīzi par darbības datiem, kas iegūti ar iesaistes ieskatiem jūsu tīmekļa vietnē.

## <a name="prerequisite"></a>Priekšnosacījums

- Iesaistes ieskatu vide, kurā auditorijas ieskatu segmentu dati ir saistīti ar auditorijas ieskatu vidi, kurā tiek izveidoti segmenti un klientu profili. Papildinformācija: [Izveidot saiti starp auditorijas ieskatiem un iesaistes ieskatiem](integrate-audience-insights-engagement-insights.md)

## <a name="create-audience-insights-segments"></a>Auditorijas ieskatu segmentu izveide 

> [!IMPORTANT]
> Lai auditorijas ieskatu segmenti tiktu rādīti iesaistes ieskatos, vispirms ir [jāveic sapludināšana un lejupstraumes procesi](../audience-insights/merge-entities.md). Lejupstraumes procesi ir svarīgi, jo tie ģenerē unikālu tabulu, kas sagatavo auditorijas ieskatu segmentus, lai tos kopīgotu ar iesaistes ieskatiem. (Ja ir ieplānota sistēmas atsvaidzināšana, tajā automātiski tiks iekļauti lejupstraumes procesi.)

Auditorijas ieskatu segmentus var izmantot iesaistes ieskatu oriģinālās atskaitēs vai izveidotās pielāgotās atskaitēs. Lai iegūtu papildinformāciju, atveriet [Oriģinālās profila atskaites](profile-reports.md) un [Izveidojiet un rediģējiet pielāgotas atskaites](custom-reports.md).

**Lai izmantotu auditorijas ieskatu segmentus, iesaistes ieskatu atskaitēs**

1. Lapā **Darbvieta** atlasiet **Dati** un pēc tam atlasiet cilni **Segmenti**.

    :::image type="content" source="media/integrate-audience-insights-segments1.png" alt-text="Atlasiet cilni Segmenti.":::

   >[!NOTE]
   > Atlasot auditorijas ieskatu segmentu, varat skatīt auditorijas ieskatus, kuros varat uzzināt, kā šis segments tika izveidots kārtulu un loģikas ziņā. Lai iegūtu papildinformāciju par auditorijas ieskatu segmentiem, skatiet [Skatīt un veidot segmentus](../audience-insights/segments.md).

2. Atlasiet oriģinālo atskaiti vai [izveidojiet pielāgotu atskaiti](custom-reports.md) un pēc tam atlasiet **Pievienot nosacījumu**. (Šajā piemērā mēs izvēlējāmies atskaiti **Lapas skati**.)

    :::image type="content" source="media/integrate-audience-insights-segments2.png" alt-text="Pievienot kārtulu.":::

3. Atlasiet vienumu **Filtrēt pēc segmenta**, izvērsiet sarakstu **Segmenta tips** un pēc tam atlasiet **Demogrāfiskais**.

    :::image type="content" source="media/integrate-audience-insights-segments3.png" alt-text="Atlasiet segmenta tipu Demogrāfiskais.":::

4. Izvērsiet sarakstu **Segmenta nosaukums** un pēc tam atlasiet auditorijas ieskatu segmentu.

    :::image type="content" source="media/integrate-audience-insights-segments4.png" alt-text="Izvēlieties segmentu.":::

5. Varat lietot vienu vai vairākus segmentus, tostarp darbības (iesaistes ieskatus) un demogrāfiskos (auditorijas ieskatus) segmentus. 

    :::image type="content" source="media/integrate-audience-insights-segments6.png" alt-text="Lapu skatu atskaite tiek ierobežota līdz ASV klientiem un sākumlapas segmentiem.":::

Iepriekšējā attēlā ir atlasīti segmenti **ASV klienti** un **Sākumlapas** , kas ierobežo atskaiti **Lapu skati**, lai rādītu tikai šos divus segmentus. 


>[!NOTE]
> Auditorijas ieskatu segmentus var izmantot, lai filtrētu oriģinālās atskaitēs, pielāgotās atskaitēs un un piltuves iesaistes ieskatos. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]