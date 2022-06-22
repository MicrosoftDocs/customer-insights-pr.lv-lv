---
title: Pakalpojumu ierobežojumi customer insights
description: Izprotiet ierobežojumus un ierobežojumus pakalpojumā Customer Insights SaaS.
ms.date: 05/28/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 6d1b761a5c9f67bfdc7c5b152132c618db3ea36a
ms.sourcegitcommit: 78ef22cd39a1ebd7525f96829cd79d95f34438b9
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 06/07/2022
ms.locfileid: "8940677"
---
# <a name="service-limits-in-customer-insights"></a>Pakalpojumu ierobežojumi customer insights

Šajā rakstā aprakstīti pakalpojuma Customer Insights iebūvētie ierobežojumi, kas izstrādāti, lai nodrošinātu pakalpojuma uzticamību un stabilitāti. Visus izmaiņu pieprasījumus var veikt sadaļā [ideju forums](https://go.microsoft.com/fwlink/?linkid=2074172).

## <a name="customer-insights"></a>Customer Insights

| Laukuma  | Ierobežojumi  | Notes |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmenti, mēri un prognozes | 300  | Kopējais segmentu [,](segments.md) mēru [un](measures.md) [prognožu](predictions.md) skaits kopā nedrīkst pārsniegt 300.  |
| Attiecības | 20 līmeņi ar padziļinātu informāciju par attiecībām entītiju ceļā. | Veidojot [segmentus](segments.md) vai [pasākumus](measures.md), izmantojot būvētāja interfeisu, entītiju ceļiem starp sākuma entītiju un mērķa entītiju var būt līdz 20 attiecībām.  |

## <a name="fair-scheduling-of-jobs"></a>Taisnīga darbu plānošana

Customer Insights ir SaaS pakalpojums, kas izmanto koplietojamos Azure resursus. Klientiem parasti ir mainīgas intensitātes slodze un dažādi grafiki. Lai nodrošinātu taisnīgu piekļuvi pamatā esošajiem resursiem, mēs pārliecināmies, ka sistēmas procesi tiek izpildīti taisnīgā kārtībā. Sistēmas procesu piemēri ir darbi, kas saistīti ar datu apvienošanu, segmentu atjauninājumiem vai mērījumu aprēķināšanu. Izstādes plānošana pasargā jūs no rindām pēc resursiem, ja ir daudz pieprasīto darbu. Tajā pašā laikā Customer Insights negarantē, ka visi darbi, kurus rindā ievietojat, tiek apstrādāti paralēli.

[!INCLUDE [footer-include](includes/footer-banner.md)]
