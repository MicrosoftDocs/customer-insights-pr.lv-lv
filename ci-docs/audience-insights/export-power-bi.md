---
title: Power BI savienotājs
description: Uzziniet, kā izmantot Dynamics 365 Customer Insights savienotāju pakalpojumā Power BI.
ms.date: 09/21/2020
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0607a4644ac7d7beb19e4faecf012efcd197d48c
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477097"
---
# <a name="connector-for-power-bi-preview"></a>Power BI savienotājs (priekšskatījums)

Izveidojiet vizualizācijas saviem datiem, izmantojot līdzekli Power BI Desktop. Veidojiet papildu ieskatus un atskaites, izmantojot vienotos klientu datus.

## <a name="prerequisites"></a>Priekšnosacījumi

- Jums ir vienotie klientu profili.
- Jūsu datorā ir instalēta jaunākā [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) versija. [Papildinformācija par Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).

## <a name="configure-the-connector-for-power-bi"></a>Power BI savienotāja konfigurēšana

1. Risinājumā Power BI Desktop atlasiet **Fails** > **Iegūt datus**.

1. Atlasiet **Skatīt vairāk** un meklējiet **Dynamics 365 Customer Insights**.

1. Atlasiet **Izveidot savienojumu**.

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

## <a name="troubleshooting"></a>Problēmu novēršana

### <a name="customer-insights-environment-doesnt-show-in-power-bi"></a>Customer Insights vide netiek rādīta programmā Power BI

Vidēs, kurās ir definētas vairāk nekā vienas [attiecības](relationships.md) starp divām vienādām entītijām auditorijas ieskatos, savienotājā Power BI nebūs pieejamas.

Varat identificēt un noņemt dublicētās attiecības.

1. Auditorijas ieskatos dodieties uz **Dati** > **Attiecības** Power BI pazudušajā vidē.
2. Nosakiet dublicētās attiecības:
   - Pārbaudiet, vai starp vienām un tām pašām divām entītijām ir definētas vairākas attiecības.
   - Pārbaudiet, vai ir izveidotas attiecības starp divām entītijām, kas ir iekļautas apvienošanas procesā. Pastāv netiešas attiecības, kas tiek definētas starp visām entītijām, kas ir iekļautas apvienošanas procesā.
3. Noņemiet visus identificēto attiecību dublikātus.

Pēc dublicēto attiecību noņemšanas mēģiniet vēlreiz konfigurēt Power BI savienotāju. Videi tagad ir jābūt pieejamai.

[!INCLUDE[footer-include](../includes/footer-banner.md)]

