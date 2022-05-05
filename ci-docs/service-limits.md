---
title: Servisa ierobežojumi programmā Dynamics 365 Customer Insights
description: Izprotiet ierobežojumus un aizliegumus.
ms.date: 09/03/2021
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: e2e7fc3033c25646693831d4c4c800d84ae6d6da
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 04/27/2022
ms.locfileid: "8641771"
---
# <a name="service-limits-in-customer-insights"></a>Pakalpojumu ierobežojumi customer insights

Šajā rakstā aprakstīti pakalpojuma Customer Insights iebūvētie ierobežojumi, kas izstrādāti, lai nodrošinātu pakalpojuma uzticamību un stabilitāti. Visus izmaiņu pieprasījumus var veikt sadaļā [ideju forums](https://go.microsoft.com/fwlink/?linkid=2074172). 

## <a name="customer-insights"></a>Customer Insights

| Laukuma  | Ierobežojumi  | Notes |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmenti, mēri un prognozes | 300  | Kopējais segmentu [,](segments.md) mēru [un](measures.md) [prognožu](predictions.md) skaits kopā nedrīkst pārsniegt 300.  |
| Attiecības | 20 līmeņi ar padziļinātu informāciju par attiecībām entītiju ceļā. | Veidojot [segmentus](segments.md) vai [pasākumus](measures.md), izmantojot būvētāja interfeisu, entītiju ceļiem starp sākuma entītiju un mērķa entītiju var būt līdz 20 attiecībām.  |


[!INCLUDE [footer-include](includes/footer-banner.md)]
