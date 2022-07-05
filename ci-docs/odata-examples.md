---
title: OData vaicājumu piemēri Customer Insights API
description: Bieži lietoti atvērto datu protokola (OData) piemēri, lai veiktu vaicājumus Customer Insights API, lai pārskatītu datus.
ms.date: 05/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 54ba9f4e9baeb4b7021bb8c20a706bbb6eb1529f
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 06/29/2022
ms.locfileid: "9083166"
---
# <a name="odata-query-examples-for-customer-insights-apis"></a>OData vaicājumu piemēri Customer Insights API

Atvērto datu protokols (Open Data Protocol — OData) ir datu piekļuves protokols, kura pamatā ir pamata protokoli, piemēram, HTTP. Tas izmanto vispārpieņemtas metodoloģijas, piemēram, REST tīmeklim. Ir dažāda veida bibliotēkas un rīki, kurus var izmantot, lai patērētu OData pakalpojumus.

Šajā rakstā ir uzskaitīti daži bieži pieprasītie vaicājumu piemēri, kas palīdzēs jums izveidot savus ieviešanas gadījumus, [pamatojoties uz Customer Insights API](apis.md).

Ir jāmodificē vaicājumu paraugi, lai tie darbotos mērķa vidēs: 

- {serviceRoot}: `https://api.ci.ai.dynamics.com/v1/instances/{instanceId}` kur {instanceId} atrodas Customer Insights vides GUID, kurā vēlaties veikt vaicājumu. Operācija [ListAllInstances](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances) ļauj jums atrast to, kam {InstanceId} jums ir piekļuve.
- {CID}: vienota klienta ieraksta GUID. Piemērs: `ce759201f786d590bf2134bff576c369`.
- {AlternateKey}: Klienta ieraksta primārās atslēgas identifikators datu avots. Piemērs: `CNTID_1002`
- {DSname}: Virkne ar entītijas nosaukumu datu avots, kas tiek uzņemta programmā Customer Insights. Piemērs: `Website_contacts`.
- {SegmentName}: virkne ar segmenta izvades entītijas nosaukumu programmā Customer Insights. Piemērs: `Male_under_40`.

## <a name="customer"></a>klient

Tālāk esošajā tabulā ir iekļauta vaicājumu paraugu kopa entītijai *Klients*.

|Vaicājuma tips |Piemērs  | Note  |
|---------|---------|---------|
|Viena klienta ID     | `{serviceRoot}/Customer?$filter=CustomerId eq '{CID}'`          |  |
|Alternatīvā atslēga    | `{serviceRoot}/Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} eq '{AlternateKey}'`         |  Vienotajā klienta entītijā saglabājas alternatīvas atslēgas       |
|Select   | `{serviceRoot}/Customer?$select=CustomerId,FullName&$filter=customerid eq '1'`        |         |
|Iekš    | `{serviceRoot}/Customer?$filter=CustomerId in ('{CID1}',’{CID2}’)`        |         |
|Alternatīvā atslēga + Iekšā   | `Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} in ('{AlternateKey}','{AlternateKey}')`         |         |
|Meklējiet  | `{serviceRoot}/Customer?$top=10&$skip=0&$search="string"`        |   Atgriež meklēšanas virknes populārākos 10 rezultātus      |
|Dalība segmentā  | `{serviceRoot}/Customer?select=*&$filter=IsMemberOfSegment('{SegmentName}')&$top=10`     | Atgriež iepriekš iestatītu rindu skaitu no segmentācijas entītijas.      |

## <a name="unified-activity"></a>Vienota darbība

Tālāk esošajā tabulā ir iekļauta parauga vaicājumu kopa entītijai *UnifiedActivity*.

|Vaicājuma tips |Piemērs  | Note  |
|---------|---------|---------|
|CID darbība     | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}'`          | Uzskaita konkrēta klienta profila darbības |
|Aktivitātes laika posms    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityTime gt 2017-01-01T00:00:00.000Z and ActivityTime lt 2020-01-01T00:00:00.000Z`     |  Klienta profila darbības laika posmā       |
|Darbības veids    |   `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityType eq '{ActivityName}'`        |         |
|Darbības pēc parādāmā vārda     | `{serviceRoot}/UnifiedActivity$filter=CustomerId eq ‘{CID}’ and ActivityTypeDisplay eq ‘{ActivityDisplayName}’`        | |
|Darbību šķirošana    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq ‘{CID}’ & $orderby=ActivityTime asc`     |  Darbību kārtošana augošā vai dilstošā secībā       |
|Aktivitātes, kas paplašinātas no dalības segmentā  |   `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId eq '{CID}'`     |         |

## <a name="other-examples"></a>Citi piemēri

Šajā tabulā ir iekļauta vaicājumu paraugu kopa citām entītijām.

|Vaicājuma tips |Piemērs  | Note  |
|---------|---------|---------|
|CID pasākumi    | `{serviceRoot}/Customer_Measure?$filter=CustomerId eq '{CID}'`          |  |
|Bagātināti CID zīmoli    | `{serviceRoot}/BrandShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`  |       |
|CID bagātinātās intereses    |   `{serviceRoot}/InterestShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`       |         |
|Klauzulā + paplašināt     | `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId in ('{CID}', '{CID}')`         | |

## <a name="not-supported-odata-queries"></a>Neatbalstītie OData vaicājumi

Customer Insights neatbalsta tālāk norādītos vaicājumus.

- `$filter` par uzņemtajām avota vienībām. Varat izpildīt tikai $filter vaicājumus par Sistēmas entītijām, ko izveido Customer Insights.
- `$expand` no vaicājuma`$search`. Piemērs: `Customer?$expand=UnifiedActivity$top=10&$skip=0&$search="corey"`
- `$expand` no `$select` tā, vai ir atlasīta tikai atribūtu apakškopa. Piemērs: `Customer?$select=CustomerId,FullName&$expand=UnifiedActivity&$filter=CustomerId eq '{CID}'`
- `$expand` bagātināts zīmols vai interešu radniecība konkrētam klientam. Piemērs: `Customer?$expand=BrandShareOfVoiceFromMicrosoft&$filter=CustomerId eq '518291faaa12f6d853c417835d40eb10'`
- Vaicājums prognoze modeļa izvades entītijas, izmantojot alternatīvā atslēga. Piemērs: `OOBModelOutputEntity?$filter=HotelCustomerID eq '{AK}'`
