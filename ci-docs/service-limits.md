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
ms.openlocfilehash: 9bf8f03b785fb3035e3fc979a3304d4e98fd8d28
ms.sourcegitcommit: 1946d7af0bd2ca216885bec3c5c95009996d9a28
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 02/25/2022
ms.locfileid: "8350416"
---
# <a name="service-limits-in-customer-insights-capabilities"></a>Pakalpojumu ierobežojumi Customer Insights iespējām

Šajā rakstā aprakstīti pakalpojuma Customer Insights iebūvētie ierobežojumi, kas izstrādāti, lai nodrošinātu pakalpojuma uzticamību un stabilitāti. Visus izmaiņu pieprasījumus var veikt sadaļā [ideju forums](https://go.microsoft.com/fwlink/?linkid=2074172). 

## <a name="audience-insights"></a>Auditorijas ieskati

| Laukuma  | Ierobežojumi  | Notes |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmenti, mēri un prognozes | 300  | Kopējais [segmentu](audience-insights/segments.md), [pasākumu](audience-insights/measures.md) un [prognožu](audience-insights/predictions.md) skaits kopā nevar pārsniegt 300.  |
| Attiecības | 20 līmeņi ar padziļinātu informāciju par attiecībām entītiju ceļā. | Veidojot [segmentus](audience-insights/segments.md) vai [pasākumus](audience-insights/measures.md), izmantojot būvētāja interfeisu, entītiju ceļiem starp sākuma entītiju un mērķa entītiju var būt līdz 20 attiecībām.  |

<!--
## Engagement insights

### Workspace and event quotas

Engagement insights is a highly scalable application that can support millions of events per second. During public preview, events have a volume threshold. There's also a limit to the number of workspaces in an organization.

### Engagement insights limits

- Maximum event volume per workspace  = 100 events per second

- Maximum number of workspaces per organization = 100

When events exceed the threshold, it can lead to loss of data in reports based on those events. You can [contact support](https://go.microsoft.com/fwlink/?linkid=2145734) to request a volume increase before you exceed limits. We'll work with you to determine your need for a volume increase and support your request.
-->

[!INCLUDE[footer-include](includes/footer-banner.md)]
