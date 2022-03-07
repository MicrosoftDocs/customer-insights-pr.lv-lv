---
title: Uzvedības datu sadalīšanai izmantojiet demogrāfiskās dimensijas (pārrauga dimensijas)
description: Izmantojiet vienotas profila pārrauga dimensijas, lai iespējotu auditorijas ieskatu klienta profila rekvizītus.
ms.date: 07/27/2021
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 95395e09bc0ba5ba93138957c62105f31c709e91
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 02/16/2022
ms.locfileid: "8233056"
---
# <a name="use-demographic-dimensions-for-splitting-behavioral-data"></a>Uzvedības datu sadalīšanai izmantojiet demogrāfiskās dimensijas

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Izmantojot vienotas profila demogrāfiskās dimensijas, iesaistes ieskatu lietotāji var piekļūt auditorijas ieskatu profila rekvizītiem. Pēc tam šos rekvizītus varat izmantot interaktīvā rīcības datu analīzē, ieskaitot datus, kas iegūva iesaistes ieskati jūsu tīmekļa vietnē vai mobilajā lietotnē.

>[!NOTE]
> Iesaistes ieskati ietver standarta dimensijas notikuma rekvizītos. Papildinformācija: [Dimensiju skatīšana un izveide](dimensions.md)

## <a name="prerequisite"></a>Priekšnosacījums

- Iesaistes ieskatu vide, kurā klienta profila dati ir saistīti ar auditorijas ieskatu vidi, kurā tiek izveidoti klientu profili. Papildinformācija: [Izveidot saiti starp auditorijas ieskatiem un iesaistes ieskatiem](integrate-audience-insights-engagement-insights.md)

> [!NOTE]
> Kad būsiet izveidojis saiti starp auditorijas ieskatu un iesaistes ieskatu vidi, iespējams, vēlēsities izmantot tikai klienta profila rekvizītiem specifiskos datus, kas var būt noderīgi kā iesaistes ieskati. Lai iegūtu papildinformāciju, skatiet [Iespējot auditorijas ieskatu vienotos profilu atribūtus un segmentus](integrate-audience-insights-engagement-insights.md#enable-audience-insights-unified-profiles-attributes-and-segments).

## <a name="create-a-new-custom-report"></a>Izveidojiet jaunu pielāgotu atskaiti

1. Kreisajā rūtī atlasiet **Pielāgots** > **Jauna atskaite** un pēc tam atlasiet metriku. (Šajā piemērā mēs izvēlējāmies **Lapas skati pēc stundas**.)

    :::image type="content" source="media/curated-dimensions1.png" alt-text="Atlasīt metriku.":::

2. Vizualizācijas redaktorā atlasiet **Dimensijas** un pēc tam nolaižamajā izvēlnē **Dimensijas tips** atlasiet **Demogrāfijas**.

    :::image type="content" source="media/curated-dimensions2.png" alt-text="Atlasiet demogrāfiskos datus.":::

3. Atlasiet dimensiju **Signal.Customer.*xxx***. (Šajā piemērā tiek rādīts Signal.Customer.Country.)

    :::image type="content" source="media/curated-dimensions3.png" alt-text="Atlasīt dimensiju.":::
  
## <a name="limitations"></a>Ierobežojumi

Uzvedības datu sadalīšanai tagad var izmantot tikai demogrāfiskās dimensijas.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
