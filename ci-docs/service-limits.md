---
title: Pakalpojumu ierobežojumi Dynamics 365 Customer Insights
description: Izprotiet ierobežojumus un aizliegumus.
ms.date: 09/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: eb25e050b8aa768e6e1d8d4c5adce6095cccc346
ms.sourcegitcommit: 31a9b531dacd3a6465b3030c704ff5c085b7e122
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 11/10/2021
ms.locfileid: "7791990"
---
# <a name="service-limits-in-customer-insights-capabilities"></a>Pakalpojumu ierobežojumi Customer Insights iespējām

Šajā rakstā aprakstīti pakalpojuma Customer Insights iebūvētie ierobežojumi, kas izstrādāti, lai nodrošinātu pakalpojuma uzticamību un stabilitāti. Visus izmaiņu pieprasījumus var veikt sadaļā [ideju forums](https://go.microsoft.com/fwlink/?linkid=2074172). 

## <a name="audience-insights"></a>Auditorijas ieskati

### <a name="service-limits-in-dynamics-365-customer-insights-audience-insights-capability"></a>Pakalpojumu ierobežojumi Dynamics 365 Customer Insights auditorijas ieskatu iespēja

| Laukuma  | Ierobežojumi  | Piezīmes |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmenti, mēri un prognozes | 300  | Kopējais segmentu, pasākumu un prognožu skaits [kopā nedrīkst pārsniegt](audience-insights/segments.md)[...](audience-insights/measures.md)[...](audience-insights/predictions.md) 300.  |
| Attiecības | 20 līmeņi ar padziļinātu informāciju par attiecībām entītiju ceļā. | Veidojot [segmentus](audience-insights/segments.md) vai [pasākumus](audience-insights/measures.md), izmantojot būvētāja interfeisu, entītiju ceļiem starp sākuma entītiju un mērķa entītiju var būt līdz 20 attiecībām.  |


## <a name="engagement-insights"></a>Iesaistes ieskati

### <a name="workspace-and-event-quotas"></a>Darbvietas un notikumu kvotas

Iesaistes ieskati ir īpaši mērogojama lietojumprogramma, kas var atbalstīt miljoniem notikumu sekundē. Publiskā priekšskatījuma laikā notikumiem ir apjoma sliekšņa vērtība. Pastāv arī ierobežojums attiecībā uz darbvietu skaitu organizācijā.

### <a name="engagement-insights-limits"></a>Iesaistes ieskatu ierobežojumi

- Maksimālais notikumu apjoms darbvietā = 100 notikumi sekundē

- Maksimālais darbvietu skaits organizācijā = 100

Ja notikumi pārsniedz robežvērtību, tas var izraisīt datu zudumu atskaitēs, pamatojoties uz šiem notikumiem. Jūs varat [sazināties ar atbalstu dienestu](https://go.microsoft.com/fwlink/?linkid=2145734), lai pieprasītu apjoma pieaugumu, pirms pārsniedzat limitu. Mēs strādāsim kopā ar jums, lai noteiktu apjoma palielināšanas nepieciešamību un atbalstītu jūsu pieprasījumu.


[!INCLUDE[footer-include](includes/footer-banner.md)]
