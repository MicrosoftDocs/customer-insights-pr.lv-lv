---
title: Customer Insights entītiju shēmas Common Data Model
description: Darba ar entītijām Common Data Model.
ms.date: 04/17/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: e21f8a9422357fbc5c9425f91f3ba241c9dec9d8
ms.sourcegitcommit: 8cc70f30baaae13dfb9c4c201a79691f311634f5
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 07/30/2021
ms.locfileid: "6692314"
---
# <a name="entity-schemas-in-common-data-model"></a>Entītiju shēmas Common Data Model

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

[Common Data Model](/common-data-model/) ir deklaratīva specifikācija, kā arī tādu standarta entītiju definīcija, kas attēlo bieži izmantos konceptus un darbības uzņēmuma un produktivitātes lietojumprogrammās. Šis modelis tiek paplašināts arī uz novērojumu un analītiskiem datiem. Common Data Model nodrošina precīzi definētas, modulāras un paplašināmas biznesa entītijas, piemēram, uzņēmumu, struktūrvienību, pieteikumu, kontaktpersonu, interesentu, iespēju un produktu, kā arī saziņu ar piegādātājiem, darbiniekiem un klientiem, piemēram, darbībām un servisa līmeņa līgumiem. Ikviens var izmantot un paplašināt Common Data Model definīcijas, lai iegūtu darbam raksturīgas papildu idejas.

Šis ir koplietojams datu modelis, kas ļauj lietojumprogrammām un datu integrētājiem daudz vieglāk sadarboties, nodrošinot vienotu datu definīciju. Common Data Model ietver bagātīgu metadatu sistēmu ar standarta entītijām, attiecībām, hierarhijām, īpašībām utt. Tas tika radīts no Dynamics 365 lietotnēm un ir atvērts GitHub ar vairāk nekā 260 standarta entītijām. Liela iekšējo un ārējo partneru sistēma sniedz nozarei raksturīgos jēdzienus Common Data Model.

Vairākas sistēmas un platformas pašlaik ievieš kopējo datu modeli, tostarp Power BI datu plūsmas un Azure datu pakalpojums. Tas jau tiek atbalstīts programmā Microsoft Dataverse, Dynamics 365, Power Apps, Power BI un gaidāmajos Azure datu pakalpojumos, tieši uzkrāšanas vērtība attiecībā pret [Open Data Initiative](https://www.microsoft.com/open-data-initiative).

## <a name="customer-insights-entity-schemas"></a>Customer Insights entītiju shēmas

Lai izveidotu pilnīgu skatu uz klientu un padarītu Customer Insights modeļus pieejamus Common Data Model, mēs esam publicējuši tālāk norādītās entītiju shēmas:

| Entītija | Apraksts |
|---------|---------|
|[CustomerActivity](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customeractivity) | Lietotāja veikta darbība, kurai ir novērojuma vērtība attiecībā pret darbu. |
|[CustomerProfile](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile) | Persona vai organizācija, kas veica vai kurai ir potenciāls iesaistīties komercdarbībā. |
|[MeasureDefinition](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/measuredefinition) | KPI definīcija, kas sadalīta pa nullēm vai vairākām dimensijām (kā piemēram, mēneša aktīvie lietotāji, kopējie izdevumi pēc klienta, vidējā klienta iegādes cena) |
|[Segment](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segment) | Definē dalībnieku grupu ar kopīgām iezīmēm. |
|[SegmentMembership](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segmentmembership) | Dalībnieki, kas piedalās noteiktā segmentā. |

Papildinformāciju skatiet dokumentācijā par [Customer Insights entītiju shēmām Common Data Model](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/overview).

## <a name="view-entities-using-the-common-data-model-entity-navigator"></a>Entītiju skatīšana, izmantojot Common Data Model entītiju navigatoru

Varat skatīt entītijas [Common Data Model entītiju navigatorā](https://microsoft.github.io/CDM/). Atlasiet **Ielādēt no GitHub!** pogu un pārejiet uz **foundationCommon** > **crmCommon** > **solutions** > **customerInsights**, kur atradīsit Customer Insights entītiju sarakstu un to definīcijas.
> [!div class="mx-imgBorder"]
> ![CDM entītiju navigators rāda CustomerActivity entītiju.](media/CDM-entity-navigator.png "CDM entītiju navigators rāda CustomerActivity entītiju")


[!INCLUDE[footer-include](../includes/footer-banner.md)]