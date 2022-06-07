---
title: Power BI savienotājs
description: Uzziniet, kā izmantot Dynamics 365 Customer Insights savienotāju pakalpojumā Power BI.
ms.date: 07/23/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: e901114703a43b4b4e751e0a93eb4876d7636c00
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643632"
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

Savienotājā [nebūs pieejamas vides, kurām programmā Customer Insights ir definētas vairākas](relationships.md) identiskas Power BI entītijas starp divām identiskām entītijām.

Varat identificēt un noņemt dublicētās attiecības.

1. Dodieties uz **DataRelations** > **par** vidi, kurā trūkst Power BI.
2. Nosakiet dublicētās attiecības:
   - Pārbaudiet, vai starp vienām un tām pašām divām entītijām ir definētas vairākas attiecības.
   - Pārbaudiet, vai ir izveidotas attiecības starp divām entītijām, kas ir iekļautas apvienošanas procesā. Pastāv netiešas attiecības, kas tiek definētas starp visām entītijām, kas ir iekļautas apvienošanas procesā.
3. Noņemiet visus identificēto attiecību dublikātus.

Pēc dublicēto attiecību noņemšanas mēģiniet vēlreiz konfigurēt Power BI savienotāju. Videi tagad ir jābūt pieejamai.

### <a name="errors-on-date-fields-when-loading-entities-in-power-bi-desktop"></a>Kļūdas datuma laukos, ielādējot entītijas programmā Power BI Desktop

Ielādējot entītijas, kas ietver laukus ar datuma formātu, piemēram, MM/DD/YYYY, var rasties kļūdas nesaderīgu lokalizācijas formātu dēļ. Šī neatbilstība rodas, ja fails Power BI Desktop ir iestatīts uz citu lokalizāciju, nevis angļu valodu (Amerikas Savienotās Valstis), jo datumu lauki Customer Insights tiek saglabāti ASV formātā.

Power BI Desktop failam ir viens lokalizācijas iestatījums, kas tiek lietots, izgūstot datus. Lai šos datuma laukus interpretētu pareizi, iestatiet šī lauka .BPI faila lokalizāciju angļu valodā (ASV). [Informācija par to, kā mainīt Power BI desktop faila lokalizāciju](/power-bi/fundamentals/supported-languages-countries-regions#choose-the-language-or-locale-of-power-bi-desktop).

[!INCLUDE [footer-include](includes/footer-banner.md)]