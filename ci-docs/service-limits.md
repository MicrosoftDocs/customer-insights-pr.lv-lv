---
title: Servisa ierobežojumi programmā Dynamics 365 Customer Insights
description: Izprotiet ierobežojumus un aizliegumus.
ms.date: 09/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: eba7871faf304d5945191b5b9bc215243b4f8a05
ms.sourcegitcommit: 5704002484cdf85ebbcf4e7e4fd12470fd8e259f
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 09/08/2021
ms.locfileid: "7483687"
---
# <a name="service-limits-in-customer-insights-capabilities"></a>Pakalpojumu ierobežojumi Customer Insights iespējām

Šajā rakstā aprakstīti pakalpojuma Customer Insights iebūvētie ierobežojumi, kas izstrādāti, lai nodrošinātu pakalpojuma uzticamību un stabilitāti. Visus izmaiņu pieprasījumus var veikt sadaļā [ideju forums](https://go.microsoft.com/fwlink/?linkid=2074172). 

## <a name="audience-insights"></a>Auditorijas ieskati

### <a name="service-limits-in-dynamics-365-customer-insights-audience-insights-capability"></a>Pakalpojuma ierobežojumi Dynamics 365 Customer Insights auditorijas ieskatu iespējas

| Laukuma  | Ierobežojumi  | Piezīmes |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmenti un mēri | 100 segmenti vai mēri. | Kopējais aktīvo [segmentu skaits](audience-insights/segments.md) un [pasākumi](audience-insights/measures.md) kopā nedrīkst pārsniegt 100.  |
| Attiecības | 20 līmeņi ar padziļinātu informāciju par attiecībām entītiju ceļā. | Veidojot [segmentus](audience-insights/segments.md) vai [pasākumus](audience-insights/measures.md), izmantojot būvētāja interfeisu, entītiju ceļiem starp sākuma entītiju un mērķa entītiju var būt līdz 20 attiecībām.  |


## <a name="engagement-insights"></a>Iesaistes ieskati

### <a name="workspace-and-event-quotas"></a>Darbvietas un notikumu kvotas

Iesaistes ieskati ir īpaši mērogojama lietojumprogramma, kas var atbalstīt miljoniem notikumu sekundē. Publiskā priekšskatījuma laikā notikumiem ir apjoma sliekšņa vērtība. Pastāv arī ierobežojums attiecībā uz darbvietu skaitu organizācijā.

### <a name="engagement-insights-limits"></a>Iesaistes ieskatu ierobežojumi

- Maksimālais notikumu apjoms darbvietā = 100 notikumi sekundē

- Maksimālais darbvietu skaits organizācijā = 100

Ja notikumi pārsniedz robežvērtību, tas var izraisīt datu zudumu atskaitēs, pamatojoties uz šiem notikumiem. Jūs varat [sazināties ar atbalstu dienestu](https://go.microsoft.com/fwlink/?linkid=2145734), lai pieprasītu apjoma pieaugumu, pirms pārsniedzat limitu. Mēs strādāsim kopā ar jums, lai noteiktu apjoma palielināšanas nepieciešamību un atbalstītu jūsu pieprasījumu.


[!INCLUDE[footer-include](includes/footer-banner.md)]