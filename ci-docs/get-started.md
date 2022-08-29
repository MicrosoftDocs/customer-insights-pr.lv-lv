---
title: Darba sākšana ar Dynamics 365 Customer Insights
description: Customer Insights pārskats palīdz resursiem ātri sākt darbu.
ms.reviewer: mhart
ms.author: mhart
author: m-hartmann
ms.date: 08/31/2021
ms.subservice: audience-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: ce0336c4bf853bc81ec01c45410169a63b69eb03
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304620"
---
# <a name="get-started-with-dynamics-365-customer-insights"></a>Darba sākšana ar Dynamics 365 Customer Insights

Customer Insights var palīdzēt jums veidot dziļāku izpratni par saviem klientiem. Savienojiet datus no dažādām transakciju, uzvedības un novērojumu avotiem, lai izveidotu 360 grādu klientu skatā. Izmantojiet šos ieskatus, lai virzītu uz klientu centrētu pieredzi un procesus. Apvienojiet un izprotiet klientu datus un izmantojiet tos inteliģentiem ieskatiem un darbībām.

## <a name="step-1-create-an-environment"></a>1. darbība. Izveidot vidi

Pirmkārt, izveidojiet vidi, kurā strādāt. Ja jūsu organizācija jau ir iegādājusies licenci, skatiet sadaļu [Vides izveide](create-environment.md). Lai sāktu Customer Insights izmēģinājumversiju, skatiet rakstu [Izmēģinājumversijas vides iestatīšana](trial-signup.md).

## <a name="step-2-explore-customer-insights"></a>2. darbība: izpētiet klientu ieskatus

Pirmo reizi piesakoties programmā Customer Insights, konfigurējiet iestatījumus un izpētiet produktu.

1. [piesakieties programmā Customer Insights](https://home.ci.ai.dynamics.com), izmantojot savu Microsoft Azure Active Directory (AAD) lietotāja kontu.

1. Mainiet vidi, lai skatītu demonstrācijas datus un [izpētītu Customer Insights](home.md).

## <a name="step-3-ingest-unify-and-set-up-relationships-for-your-data"></a>3. darbība. Tvert, apvienot un iestatīt datu attiecības

Vienotie profili ir pamats, lai gūtu ieskatus un veikt darbības ar datiem. Ievadiet datus no dažādiem avotiem un izmantojiet datu apvienošanas procesu, lai apvienotu vienotos profilus. Norādiet relācijas starp uzņemtajām entītijām un izmantojiet bagātināšanas līdzekļus, lai profiliem pievienotu informāciju.

1. Datu tveršana, izveidojot datu avotus no vairākām opcijām. Izvēlieties starp [Azure Data Lake Storage, ieskaitot common data model](connect-common-data-model.md), [Azure Synapse Analytics](connect-synapse.md), [Microsoft Dataverse](connect-dataverse-managed-lake.md), vai [Power Query savienotājiem](connect-power-query.md).

1. Palaidiet [datu apvienošanas procesu](data-unification.md), identificējot [avota laukus](map-entities.md), noņemot [dublikātus,](remove-duplicates.md) atbilstošos [nosacījumus](match-entities.md) un [apvienojot laukus](merge-entities.md).

1. Iepazīstiet [entītijas, ko sistēma izveido](entities.md) un izveidojiet attiecības starp [tvertajām entītijām](relationships.md).

## <a name="step-4-enhance-unified-profiles-with-predictions-activities-and-measures"></a>4. darbība. Uzlabojiet vienotos profilus, izmantojot prognozes, darbības un pasākumus

Iestatot vienotus profilus, uzlabojiet savus datus un vēl vairāk palieliniet to sniegto informāciju.

1. Izvēlieties kādu paplašinātu bagātinātā pakalpojuma sniedzēju bibliotēku, lai [bagātinātu klientu datus](enrichment-hub.md).

1. Izmantojiet [standarta modeļus](predictions-overview.md), lai prognozētu trūkuma varbūtību vai prognozējamus ieņēmumus.

1. [Konfigurējiet darbības](activities.md), pamatojoties uz tvertajiem datiem, un hronoloģiskā laika skalā vizualizējiet saziņu ar klientiem.

1. [Veidojiet pasākumus](measures.md), lai novērtētu uzņēmējdarbības mērķus un KPI.

## <a name="step-5-create-segments-and-activate-data-through-various-export-options"></a>5. darbība. Izveidojiet segmentus un aktivizējiet datus, izmantojot dažādas eksportēšanas opcijas

Tagad, kad jūsu dati ir pabeigti un satur plašu informācijas klāstu par jūsu klientiem, meklējiet veidus, kā rīkoties ar šiem datiem.

1. [Izveidojiet segmentus](segments.md), klientu bāzes apakškopas, lai nodrošinātu, ka darbības ir saistītas ar mērķa klientiem.

1. Pārlūkojiet to eksportēšanas opciju [paplašināto katalogu](export-destinations.md), kur var izmantot klientu datus. Piemēram, varat izmantot datus, lai pārvaldītu akcijas un sazinātos ar ciparu mārketingu.

1. Pārskatiet integrācijas opcijas, piemēram, uz citām Dynamics 365 programmām ar pievienojumprogrammu [Customer](customer-card-add-in.md) Card.  


[!INCLUDE [footer-include](includes/footer-banner.md)]
