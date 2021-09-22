---
title: Tīmekļa SDK parauga palaišana
description: Informācija par to, kā personalizēt un palaist tīmekļa SDK paraugu.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 10/30/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 97e50a51231bcf05f3e381397f0cf41e49afc10e3c3674d7c709c8f521979e12
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036612"
---
# <a name="run-the-web-sdk-sample-for-dynamics-365-customer-insights-engagement-insights-capability"></a>Tīmekļa SDK parauga palaišana Dynamics 365 Customer Insights iesaistes ieskatu iespējai

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Iesaistes ieskatu iespēju tīmekļa SDK bibliotēka ir JavaScript bibliotēka ar koda paraugu, ko varat izmantot savā vietnē.

## <a name="prerequisites"></a>Priekšnosacījumi

- Instalējiet [Visual Studio kodu](https://code.visualstudio.com/).
- [Instalējiet Live Server paplašinājumu](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) Visual Studio kodā un iepazīstieties ar Live Server palaišanu.
- Jums ir jābūt [ievades atslēgai](instrument-website.md).

## <a name="run-sample"></a>Parauga palaišana

1. [Lejupielādējiet tīmekļa SDK paraugu](https://download.pi.dynamics.com/sdk/EngagementInsightsSamples/ei_websdk_sample.zip).

1. Atarhivēt saspiesto failu `ei_websdk_sample.zip`.

1. Atveriet atarhivēto mapi Visual Studio kodā.

1. `ei_websdk_sample.html` failā aizstājiet virkni “INGESTION_KEY” ar jūsu ievades atslēgu no iesaistes ieskatu iespējas portāla un virkni “NAME” ar globālo nosaukumu, kurā vēlaties izveidot SDK. Pārliecinieties, vai tiek aizstāti visi notikumi.

1. Atveriet `ei_websdk_sample.html` failu, izmantojot Live Server Visual Studio kodā, statusa joslā atlasot vienumu **Go Live**.

1. Atverot lapu, automātiski tiek nosūtīts skata notikums. Noklikšķinot uz jebkuras lapas pogas, tiks sūtīti darbību notikumi. Poga **Sekot notikumiem** arī nosūtīs pielāgotus notikumus. Atlasot pogu **Doties uz Bing**, pirms navigēšanas uz Bing vietni tiks nosūtīts darbības notikums.

1. Apskatiet plūstošos notikumus, pārejot uz savu darbvietu. Šī darbvieta tiek saistīta ar 4. darbībā ievadīto ievades atslēgu.


[!INCLUDE[footer-include](../includes/footer-banner.md)]