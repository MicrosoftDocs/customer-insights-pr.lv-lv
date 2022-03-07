---
title: Tīmekļa SDK parauga palaišana
description: Informācija par to, kā personalizēt un palaist tīmekļa SDK paraugu.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: a50a10db784ec7c1943c94e74000713309787e5c
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 02/16/2022
ms.locfileid: "8225340"
---
# <a name="run-the-web-sdk-sample-for-dynamics-365-customer-insights-engagement-insights-capability"></a>Tīmekļa SDK parauga palaišana Dynamics 365 Customer Insights iesaistes ieskatu iespējai

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Iesaistes ieskatu iespēju tīmekļa SDK bibliotēka ir JavaScript bibliotēka ar koda paraugu, ko varat izmantot savā vietnē.

## <a name="prerequisites"></a>Priekšnosacījumi

- Instalējiet [Visual Studio kodu](https://code.visualstudio.com/).
- [Instalējiet Live Server paplašinājumu](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) Visual Studio kodā un iepazīstieties ar Live Server palaišanu.
- Jums ir jābūt [iesaistes ieskatu darbvietai](create-workspace.md).

## <a name="run-sample"></a>Parauga palaišana

1. [Lejupielādējiet tīmekļa SDK paraugu](https://download.pi.dynamics.com/sdk/EngagementInsightsSamples/ei_websdk_sample.zip).

1. Atarhivēt saspiesto failu `ei_websdk_sample.zip`.

1. Atveriet atarhivēto mapi Visual Studio kodā.

1. Dodieties uz darbvietas iesaistes ieskatu portālu. Atlasiet **Administrators** > **Darbvieta** un pēc tam **Instalēšanas rokasgrāmata**. Izpildiet pirmo opciju un atlasiet **Kopēt kodu**, lai kopētu JavaScript koda fragmentu.

1. Failā `ei_websdk_sample.html` ielīmējiet koda fragmentu, kas tikko kopēts zem šīs rindas:

   - <-- IELĪMĒJIET JAVASCRIPT KODA FRAGMENTU NO IESAISTES IESKATU PORTĀLA ŠEIT, ZEM ŠĪS RINDAS -->

1. Atveriet `ei_websdk_sample.html` failu, izmantojot Live Server Visual Studio kodā, statusa joslā atlasot vienumu **Go Live**.

1. Atverot lapu, automātiski tiek nosūtīts skata notikums. Noklikšķinot uz jebkuras lapas pogas, tiks sūtīti darbību notikumi. Poga **Sekot notikumiem** arī nosūtīs pielāgotus notikumus. Atlasot pogu **Doties uz Bing**, pirms navigēšanas uz Bing vietni tiks nosūtīts darbības notikums.

1. Apskatiet plūstošos notikumus, pārejot uz savu darbvietu. Šī darbvieta tiek saistīta ar 4. darbībā ievadīto ievades atslēgu.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
