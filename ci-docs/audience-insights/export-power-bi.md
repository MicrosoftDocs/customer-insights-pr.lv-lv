---
title: Power BI savienotājs
description: Uzziniet, kā izmantot Dynamics 365 Customer Insights savienotāju pakalpojumā Power BI.
ms.date: 07/23/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: a0ca431dbea839fe271cf3a512cd3a5dde6d920d396056e91b33bcf7ed84272a
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035516"
---
# <a name="connector-for-power-bi-preview"></a>Power BI savienotājs (priekšskatījums)

Izveidojiet vizualizācijas saviem datiem, izmantojot līdzekli Power BI Desktop. Veidojiet papildu ieskatus un atskaites, izmantojot vienotos klientu datus.

## <a name="prerequisites"></a>Priekšnosacījumi

- Jums ir vienotie klientu profili.
- Jaunākā [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) versija ir instalēta jūsu datorā. [Papildinformācija par Power BI Desktop](/power-bi/desktop-what-is-desktop).

## <a name="configure-the-connector-for-power-bi"></a>Power BI savienotāja konfigurēšana

1. Risinājumā Power BI Desktop atlasiet **Fails** > **Iegūt datus**.

1. Atlasiet **Skatīt vairāk** un meklējiet **Dynamics 365 Customer Insights**.

1. Atlasiet **Izveidot savienojumu**.

1. **Pierakstieties**, izmantojot to pašu organizācijas kontu, ko izmantojat Customer Insights, un atlasiet **Savienot**.
   > [!NOTE]
   > Šajā darbībā norādītais konts tiek izmantots, lai iegūtu datus no Customer Insights, un tiem nav jābūt tādiem pašiem, ar kuriem pierakstījāties Power BI. Lai atiestatītu datus, kas tiek lietoti datu paņemšanai, atveriet Power BI un atveriet **Fails** > **Opcijas** > **Iestatījumi** > **Datu avotu iestatījumi**. Datu avotu sarakstā atlasiet **Dynamics 365 Customer Insights pieteikšanās** un atlasiet **Noņemt atļaujas**.  

1. Dialoglodziņā **Navigators**. Jūs redzēsiet sarakstu ar visām vidēm, kurām Jums ir piekļuve. Izvērsiet vidi un atveriet jebkuru no mapēm (entītijas, mērvienības, segmenti, bagātinājumi). Piemēram, atveriet mapi **Entītijas**, lai skatītu visas entītijas, ko varat importēt.

   ![Power BI savienotāja navigators.](media/power-bi-navigator.png "Power BI savienotāja navigators")

1. Atzīmējiet izvēles rūtiņas, kas atrodas blakus iekļaujamajām entītijām, un atlasiet **Ielādēt**. Varat atlasīt vairākas entītijas no vairākām vidēm.

1. Kamēr notiks entītiju ielāde, tiks rādīts ielādēšanas dialoglodziņš. Kad ir ielādētas visas atlasītās entītijas, varat izmantot Power BI iespējas, lai vizualizētu datus.

## <a name="large-data-sets"></a>Lielas datu kopas

Customer Insights savienotājs Power BI ir paredzēts darbam ar datu kopām, kurās ir līdz 1 000 000 klientu profilu. Lielāku datu kopu importēšana var strādāt, bet tai ir nepieciešams ilgs laiks. Turklāt process var tikt pārtraukts, jo Power BI pastāv ierobežojumi. Papildinformāciju skatiet [Power BI: ieteikumi lielām datu kopām](/power-bi/admin/service-premium-what-is#large-datasets). 

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

### <a name="errors-on-date-fields-when-loading-entities-in-power-bi-desktop"></a>Kļūdas datuma laukos, ielādējot entītijas programmā Power BI Desktop

Ielādējot entītijas, kas ietver laukus ar datuma formātu, piemēram, MM/DD/YYYY, var rasties kļūdas nesaderīgu lokalizācijas formātu dēļ. Šī neatbilstība rodas, ja Power BI Desktop failā ir iestatīta cita lokalizācija, nevis angļu valoda (ASV), jo datuma lauki auditorijas ieskatos tiek saglabāti ASV formātā.

Power BI Desktop failam ir viens lokalizācijas iestatījums, kas tiek lietots, izgūstot datus. Lai šos datuma laukus interpretētu pareizi, iestatiet šī lauka .BPI faila lokalizāciju angļu valodā (ASV). [Informācija par to, kā mainīt Power BI desktop faila lokalizāciju](/power-bi/fundamentals/supported-languages-countries-regions.md#choose-the-locale-for-importing-data-into-power-bi-desktop).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
