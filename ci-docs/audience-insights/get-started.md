---
title: Darba sākšana ar auditorijas ieskatu iespējām programmā Dynamics 365 Customer Insights
description: Pārskats par auditorijas ieskatiem palīdz resursiem ātri sākt darbu.
ms.reviewer: mhart
ms.author: mhart
author: m-hartmann
ms.date: 08/31/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 5e8545bc9bf0d953150248fa859c6ca71a12f9cf
ms.sourcegitcommit: 53b133a716c73cb71e8bcbedc6273cec70ceba6c
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 10/15/2021
ms.locfileid: "7645273"
---
# <a name="get-started-with-dynamics-365-customer-insights-audience-insights-capability"></a>Darba sākšana ar auditorijas ieskatu iespējām programmā Dynamics 365 Customer Insights

Auditorijas ieskati var palīdzēt jums veidot dziļāku izpratni par klientiem. Savienojiet datus no dažādām transakciju, uzvedības un novērojumu avotiem, lai izveidotu 360 grādu klientu skatā. Izmantojiet šos ieskatus, lai virzītu uz klientu centrētu pieredzi un procesus. Apvienojiet un izprotiet klientu datus un izmantojiet tos inteliģentiem ieskatiem un darbībām.

## <a name="step-1-create-an-environment"></a>1. darbība. Izveidot vidi

Vispirms ir jāizveido vide, kurā strādāt. Ja jūsu organizācija jau ir iegādājusies licenci, skatiet sadaļu [Vides izveide](create-environment.md). Lai sāktu auditorijas ieskatu izmēģinājumversiju, skatiet sadaļu [Izmēģinājumversijas vides iestatīšana](../trial-signup.md). 

## <a name="step-2-explore-audience-insights"></a>2. darbība. Auditorijas ieskatu izpēte

Pirmoreiz apmeklējot auditorijas ieskatus, varat konfigurēt iestatījumus, pārskatīt politikas un izpētīt iespējas.

1. [Piesakieties auditorijas ieskatiem](https://home.ci.ai.dynamics.com), izmantojot savu Microsoft Azure Active Directory (AAD) lietotāja kontu.

1. [Mainiet vidi](manage-environments.md#switch-environments), lai redzētu demonstrācijas datus un [izpētītu auditorijas ieskatus](home.md).

##  <a name="step-3-ingest-unify-and-set-up-relationships-for-your-data"></a>3. darbība. Tvert, apvienot un iestatīt datu attiecības

Vienotie profili ir pamats, lai gūtu ieskatus un veikt darbības ar datiem. Ievadiet datus no dažādiem avotiem un izmantojiet datu apvienošanas procesu, lai apvienotu vienotos profilus. Norādiet attiecības starp nosūtāmajām entītijām, lai profiliem pievienotu informāciju, lietojot bagātinātā teksta līdzekļus. 

1. Datu tveršana, izveidojot datu avotus no vairākām opcijām. Izvēlieties starp [Power Query savienotājiem](connect-power-query.md), [mapi Common Data Model](connect-common-data-model.md) vai [Microsoft Dataverse](connect-common-data-service-lake.md). 

1. Izpildiet [datu unifikācijas procesu](data-unification.md), izmantojot [karti](map-entities.md), [atbilstību](match-entities.md) un [sapludinot ](merge-entities.md) fāzes.

1. Iepazīstiet [entītijas, ko sistēma izveido](entities.md) un izveidojiet attiecības starp [tvertajām entītijām](relationships.md).
    
## <a name="step-4-enhance-unified-profiles-with-predictions-activities-and-measures"></a>4. darbība. Uzlabojiet vienotos profilus, izmantojot prognozes, darbības un pasākumus

Iestatot vienotos profilus, varat uzlabot datus un vēl vairāk palielināt to nodrošināto informāciju.

1. Izvēlieties kādu paplašinātu bagātinātā pakalpojuma sniedzēju bibliotēku, lai [bagātinātu klientu datus](enrichment-hub.md).

1. Izmantojiet [standarta modeļus](predictions-overview.md), lai prognozētu trūkuma varbūtību vai prognozējamus ieņēmumus.

1. [Konfigurējiet darbības](activities.md), pamatojoties uz tvertajiem datiem, un hronoloģiskā laika skalā vizualizējiet saziņu ar klientiem. 

1. [Veidojiet pasākumus](measures.md), lai novērtētu uzņēmējdarbības mērķus un KPI.
 
## <a name="step-5-create-segments-and-activate-data-through-various-export-options"></a>5. darbība. Izveidojiet segmentus un aktivizējiet datus, izmantojot dažādas eksportēšanas opcijas

Tagad, kad dati ir pabeigti un satur plaša diapazona informāciju par klientiem, ir pienācis laiks meklēt veidus, kā veikt darbības ar tiem. 

1. [Izveidojiet segmentus](segments.md), klientu bāzes apakškopas, lai nodrošinātu, ka darbības ir saistītas ar mērķa klientiem.

1. Pārlūkojiet to eksportēšanas opciju [paplašināto katalogu](export-destinations.md), kur var izmantot klientu datus. Piemēram, varat izmantot datus, lai pārvaldītu akcijas un sazinātos ar ciparu mārketingu.

1. Pārskatiet integrācijas opcijas, piemēram, izmantojot [tiešu savienojumu ar iesaistes ieskatiem](../engagement-insights/integrate-audience-insights-engagement-insights.md) vai citām Dynamics 365 programmām, izmantojot [Klienta kartītes pievienojumprogrammu](customer-card-add-in.md).  


[!INCLUDE[footer-include](../includes/footer-banner.md)]
