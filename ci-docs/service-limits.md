---
title: Pakalpojumu ierobežojumi programmā Customer Insights
description: Izprotiet ierobežojumus un ierobežojumus customer insights SaaS pakalpojumā.
ms.date: 08/30/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 7f38b7d9985368fc38107f1f360f0603a7fcc8e6
ms.sourcegitcommit: 3c7cdfc8bd83ca236e4777240e08a541dc955d34
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 09/07/2022
ms.locfileid: "9411749"
---
# <a name="service-limits-in-customer-insights"></a>Pakalpojumu ierobežojumi programmā Customer Insights

 Customer Insights ir iebūvēti ierobežojumi, kas izstrādāti, lai nodrošinātu pakalpojuma uzticamību un stabilitāti. Visus izmaiņu pieprasījumus var veikt sadaļā [ideju forums](https://go.microsoft.com/fwlink/?linkid=2074172).

## <a name="customer-insights"></a>Customer Insights

| Laukuma  | Ierobežojumi  | Notes |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmenti, mēri un prognozes | 300  | Kopējais segmentu [,](segments.md) mēru [un](measures.md) [prognožu](predictions-overview.md) skaits kopā nedrīkst pārsniegt 300.  |
| Attiecības | 20 līmeņi ar padziļinātu informāciju par attiecībām entītiju ceļā. | Veidojot [segmentus](segments.md) vai [pasākumus](measures.md), izmantojot būvētāja interfeisu, entītiju ceļiem starp sākuma entītiju un mērķa entītiju var būt līdz 20 attiecībām.  |

## <a name="fair-scheduling-of-jobs"></a>Taisnīga darba vietu plānošana

Customer Insights ir SaaS pakalpojums, kas izmanto koplietojamus Azure resursus. Klientiem parasti ir dažādas intensitātes darba slodzes un dažādi grafiki. Lai nodrošinātu taisnīgu piekļuvi pamatā esošajiem resursiem, mēs pārliecināmies, ka sistēmas procesi tiek izpildīti godīgā kārtībā. Sistēmas procesu piemēri ir darbi, kas saistīti ar datu apvienošanu, segmentu atjauninājumiem vai mēra aprēķināšanu. Godīga plānošana aizsargā jūs no rindām pēc resursiem, ja ir liels pieprasīto darbu skaits. Tajā pašā laikā Customer Insights negarantē, ka visi darbi, kurus rindā veicat, tiek apstrādāti paralēli.

[!INCLUDE [footer-include](includes/footer-banner.md)]
