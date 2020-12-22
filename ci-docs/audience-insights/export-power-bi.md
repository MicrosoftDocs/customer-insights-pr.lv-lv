---
title: Power BI savienotājs
description: Uzziniet, kā izmantot Dynamics 365 Customer Insights savienotāju pakalpojumā Power BI.
ms.date: 09/21/2020
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d497ca779a337c512a7254524f597cff226bcb45
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406325"
---
# <a name="connector-for-power-bi-preview"></a>Power BI savienotājs (priekšskatījums)

Izveidojiet vizualizācijas saviem datiem, izmantojot līdzekli Power BI Desktop. Veidojiet papildu ieskatus un atskaites, izmantojot vienotos klientu datus.

## <a name="prerequisites"></a>Priekšnosacījumi

- Jums ir vienotie klientu profili.
- Jūsu datorā ir instalēta jaunākā [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) versija. [Papildinformācija par Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).

## <a name="configure-the-connector-for-power-bi"></a>Power BI savienotāja konfigurēšana

1. Risinājumā Power BI Desktop atlasiet **Fails** > **Iegūt datus**.

1. Atlasiet **Skatīt vairāk** un meklējiet **Dynamics 365 Customer Insights**.

1. Atlasiet rezultātu un atlasiet **Savienot**.

1. **Pierakstieties**, izmantojot to pašu organizācijas kontu, ko izmantojat Customer Insights, un atlasiet **Savienot**.
   > [!NOTE]
   > Šajā darbībā norādītais konts tiek izmantots, lai iegūtu datus no Customer Insights, un tiem nav jābūt tādiem pašiem, ar kuriem pierakstījāties Power BI. Lai atiestatītu datus, kas tiek lietoti datu paņemšanai, atveriet Power BI un atveriet **Fails** > **Opcijas** > **Iestatījumi** > **Datu avotu iestatījumi**. Datu avotu sarakstā atlasiet **Dynamics 365 Customer Insights pieteikšanās** un atlasiet **Noņemt atļaujas**.  

1. Dialoglodziņā **Navigators**. Jūs redzēsiet sarakstu ar visām vidēm, kurām Jums ir piekļuve. Izvērsiet vidi un atveriet jebkuru no mapēm (entītijas, mērvienības, segmenti, bagātinājumi). Piemēram, atveriet mapi **Entītijas**, lai skatītu visas entītijas, ko varat importēt.

   ![Power BI savienotāja navigators](media/power-bi-navigator.png "Power BI savienotāja navigators")

1. Atzīmējiet izvēles rūtiņas, kas atrodas blakus iekļaujamajām entītijām, un atlasiet **Ielādēt**. Varat atlasīt vairākas entītijas no vairākām vidēm.

1. Kamēr notiks entītiju ielāde, tiks rādīts ielādēšanas dialoglodziņš. Kad ir ielādētas visas atlasītās entītijas, varat izmantot Power BI iespējas, lai vizualizētu datus.

## <a name="large-data-sets"></a>Lielas datu kopas

Customer Insights savienotājs Power BI ir paredzēts darbam ar datu kopām, kurās ir līdz 1 000 000 klientu profilu. Lielāku datu kopu importēšana var strādāt, bet tai ir nepieciešams ilgs laiks. Turklāt process var tikt pārtraukts, jo Power BI pastāv ierobežojumi. Papildinformāciju skatiet [Power BI: ieteikumi lielām datu kopām](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets). 

### <a name="work-with-a-subset-of-data"></a>Darbs ar datu apakškopu

Apsveriet iespēju strādāt ar datu apakškopu. Piemēram, varat izveidot [segmentus](segments.md), nevis visu klientu ierakstu eksportēšanu uz Power BI.
