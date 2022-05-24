---
title: Darba sākšana ar Dynamics 365 Customer Insights
description: Customer Insights pārskats palīdz resursiem ātri sākt darbu.
ms.reviewer: v-wendysmith
ms.author: mhart
author: m-hartmann
ms.date: 04/12/2022
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: 1a19d83930d667bdca5301dcc5a3ffa5db6a7bdc
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741142"
---
# <a name="get-started-with-dynamics-365-customer-insights"></a>Darba sākšana ar Dynamics 365 Customer Insights

Customer Insights var palīdzēt jums veidot dziļāku izpratni par saviem klientiem. Savienojiet datus no dažādām transakciju, uzvedības un novērojumu avotiem, lai izveidotu 360 grādu klientu skatā. Izmantojiet šos ieskatus, lai virzītu uz klientu centrētu pieredzi un procesus. Apvienojiet un izprotiet klientu datus un izmantojiet tos inteliģentiem ieskatiem un darbībām.

## <a name="step-1-create-an-environment"></a>1. darbība. Izveidot vidi

Vispirms ir jāizveido vide, kurā strādāt. Ja jūsu organizācija jau ir iegādājusies licenci, skatiet sadaļu [Vides izveide](create-environment.md). Lai sāktu Customer Insights izmēģinājumversiju, skatiet rakstu [Izmēģinājuma vides iestatīšana](trial-signup.md).

## <a name="step-2-explore-customer-insights"></a>2. darbība: izpētiet klientu ieskatus

Pirmo reizi piesakoties Customer Insights, varat konfigurēt iestatījumus un izpētīt produktu.

1. [piesakieties Customer Insights](https://home.ci.ai.dynamics.com), izmantojot savu Microsoft Azure Active Directory (AAD) lietotāja kontu.

1. [Mainiet vidi](manage-environments.md#switch-environments), lai skatītu demonstrācijas datus, un [izpētiet Customer Insights](home.md).

## <a name="step-3-ingest-unify-and-set-up-relationships-for-your-data"></a>3. darbība. Tvert, apvienot un iestatīt datu attiecības

Vienotie profili ir pamats, lai gūtu ieskatus un veikt darbības ar datiem. Ievadiet datus no dažādiem avotiem un izmantojiet datu apvienošanas procesu, lai apvienotu vienotos profilus. Norādiet attiecības starp nosūtāmajām entītijām, lai profiliem pievienotu informāciju, lietojot bagātinātā teksta līdzekļus.

1. Datu tveršana, izveidojot datu avotus no vairākām opcijām. Izvēlieties starp [Power Query savienotājiem](connect-power-query.md), koplietojamu [datu modeļa mapi](connect-common-data-model.md) vai [Microsoft Dataverse](connect-dataverse-managed-lake.md). 

1. Palaidiet datu apvienošanas procesu, [identificējot avota laukus](data-unification.md)[, noņemot](map-entities.md) dublikātus, [atbilstošos](remove-duplicates.md) nosacījumus [un](match-entities.md) vienojot laukus [.](merge-entities.md)

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

1. Pārskatiet integrācijas opcijas, piemēram, citas Dynamics 365 programmas, izmantojot pievienojumprogrammu [Klienta](customer-card-add-in.md) karte.  


[!INCLUDE [footer-include](includes/footer-banner.md)]
