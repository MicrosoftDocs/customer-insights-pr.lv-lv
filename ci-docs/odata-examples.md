---
title: OData piemēri API Dynamics 365 Customer Insights
description: Bieži izmantotie atvērto datu protokola (OData) piemēri, lai veiktu vaicājumu Customer Insights API, lai pārskatītu datus.
ms.date: 05/10/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 007278e1330e1a8e64d524ded8496acaf83b874c
ms.sourcegitcommit: a50c5e70d2baf4db41a349162fd1b1f84c3e03b6
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 05/11/2022
ms.locfileid: "8740070"
---
# <a name="odata-query-examples"></a>OData vaicājumu piemēri

Atvērto datu protokols (OData) ir datu piekļuves protokols, kura pamatā ir tādi pamatprotokoli kā HTTP. Tas izmanto vispārpieņemtas metodes, piemēram, REST tīmeklim. Ir dažāda veida bibliotēkas un rīki, kurus var izmantot OData pakalpojumu patēriņam.

Šajā rakstā ir uzskaitīti daži bieži pieprasīti piemēru vaicājumi, kas palīdzēs jums izveidot savas implementācijas, [pamatojoties uz Customer Insights API](apis.md).

Lai tie darbotos mērķa vidēs, ir jāmodificē vaicājumu paraugi: 

- {serviceRoot}: `https://api.ci.ai.dynamics.com/v1/instances/{instanceId}` kur {instanceId} ir customer insights vides GUID, kurā vēlaties veikt vaicājumu. Operācija [ListAllInstances](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances) ļauj atrast {InstanceId} jums piekļuvi.
- {CID}: vienota klienta ieraksta GUID. Piemērs: `ce759201f786d590bf2134bff576c369`.
- {AlternateKey}: klienta ieraksta primārās atslēgas identifikators datu avots. Piemērs: `CNTID_1002`
- {DSname}: virkne ar entītijas nosaukumu datu avots, kas tiek uzņemta customer insights. Piemērs: `Website_contacts`.
- {SegmentName}: virkne ar segmenta izvades entītijas nosaukumu customer insights. Piemērs: `Male_under_40`.

## <a name="customer"></a>klient

Šajā tabulā ir norādīta entītijas Klients vaicājumu paraugu *kopa*.


|Vaicājuma tips |Piemērs  | Note  |
|---------|---------|---------|
|Viena debitora ID     | `{serviceRoot}/Customer?$filter=CustomerId eq '{CID}'`          |  |
|Alternatīvā atslēga    | `{serviceRoot}/Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} eq '{AlternateKey}' `         |  Vienotā debitora entītijā saglabājas alternatīvās atslēgas       |
|Select   | `{serviceRoot}/Customer?$select=CustomerId,FullName&$filter=customerid eq '1'`        |         |
|Iekš    | `{serviceRoot}/Customer?$filter=CustomerId in ('{CID1}',’{CID2}’)`        |         |
|Alternatīvā atslēga + iekšā   | `Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} in ('{AlternateKey}','{AlternateKey}')`         |         |
|Meklējiet  | `{serviceRoot}/Customer?$top=10&$skip=0&$search="string"`        |   Atgriež meklēšanas virknes 10 labākos rezultātus      |
|Segmenta dalība  | `{serviceRoot}/Customer?select=*&$filter=IsMemberOfSegment('{SegmentName}')&$top=10  `     | Atgriež iepriekš iestatītu rindu skaitu no segmentācijas entītijas.      |

## <a name="unified-activity"></a>Vienota darbība

Šajā tabulā ir norādīta entītijas UnifiedActivity vaicājumu *paraugu kopa*.

|Vaicājuma tips |Piemērs  | Note  |
|---------|---------|---------|
|CID aktivitāte     | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}'`          | Uzskaita noteikta debitora profila aktivitātes |
|Aktivitātes laika grafiks    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityTime gt 2017-01-01T00:00:00.000Z and ActivityTime lt 2020-01-01T00:00:00.000Z`     |  Debitora profila aktivitātes laika periodā       |
|Darbības veids    |   `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityType eq '{ActivityName}'`        |         |
|Aktivitāte pēc parādāmā nosaukuma     | `{serviceRoot}/UnifiedActivity$filter=CustomerId eq ‘{CID}’ and ActivityTypeDisplay eq ‘{ActivityDisplayName}’ `        | |
|Darbību kārtošana    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq ‘{CID}’ & $orderby=ActivityTime asc`     |  Kārtot aktivitātes augošā vai dilstošā secībā       |
|Aktivitāte izvērsta no segmenta dalības  |   `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId eq '{CID}'`     |         |

## <a name="other-examples"></a>Citi piemēri

Šajā tabulā ir norādīta vaicājumu paraugu kopa citām entītijām.

|Vaicājuma tips |Piemērs  | Note  |
|---------|---------|---------|
|CID mērījumi    | `{serviceRoot}/Customer_Measure?$filter=CustomerId eq '{CID}'`          |  |
|Bagātināti CID zīmoli    | `{serviceRoot}/BrandShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`  |       |
|Bagātinātās CID intereses    |   `{serviceRoot}/InterestShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`       |         |
|In-Klauzula + Izvērst     | `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId in ('{CID}', '{CID}')`         | |
