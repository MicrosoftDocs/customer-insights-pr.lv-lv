---
title: Power BI savienotājs (priekšskatījums)
description: Uzziniet, kā izmantot Dynamics 365 Customer Insights savienotāju pakalpojumā Power BI.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 656a695b8b3f1ec2b5fbaad69feba7f1f0b73dee
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196679"
---
# <a name="power-bi-connector-preview"></a>Power BI savienotājs (priekšskatījums)

Izveidojiet datu vizualizācijas, izmantojot darbvirsmu Microsoft Power BI. Veidojiet papildu ieskatus un atskaites, izmantojot vienotos klientu datus.

## <a name="prerequisites"></a>Priekšnoteikumi

- Vienoti klientu profili.
- Jaunākā [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) versija ir instalēta jūsu datorā. [Papildinformācija par Power BI Desktop](/power-bi/desktop-what-is-desktop).

## <a name="configure-the-connector-for-power-bi"></a>Power BI savienotāja konfigurēšana

1. Risinājumā Power BI Desktop atlasiet **Fails** > **Iegūt datus**.

1. Atlasiet **Skatīt vairāk** un meklējiet **Dynamics 365 Customer Insights**.

1. Atlasiet **Izveidot savienojumu**.

1. **Pierakstieties**, izmantojot to pašu organizācijas kontu, ko izmantojat Customer Insights, un atlasiet **Savienot**.
   > [!NOTE]
   > Šajā darbībā norādītais konts tiek izmantots, lai iegūtu datus no Customer Insights, un tiem nav jābūt tādiem pašiem, ar kuriem pierakstījāties Power BI. Lai atiestatītu datus, kas tiek lietoti datu paņemšanai, atveriet Power BI un atveriet **Fails** > **Opcijas** > **Iestatījumi** > **Datu avotu iestatījumi**. Datu avotu sarakstā atlasiet **Dynamics 365 Customer Insights pieteikšanās** un atlasiet **Noņemt atļaujas**.  

1. **Dialoglodziņā Navigācija** skatiet visu to vides sarakstu, kurām jums ir piekļuve. Izvērsiet vidi un atveriet jebkuru no mapēm (entītijas, mērvienības, segmenti, bagātinājumi). Piemēram, atveriet mapi **Entītijas**, lai skatītu visas entītijas, ko varat importēt.

   :::image type="content" source="media/power-bi-navigator.png" alt-text="Power BI savienotāja navigators.":::

1. Atzīmējiet izvēles rūtiņas, kas atrodas blakus iekļaujamajām entītijām, un atlasiet **Ielādēt**. Varat atlasīt vairākas entītijas no vairākām vidēm.

   Ielādes dialoglodziņš tiek parādīts entītiju ielādes laikā. Kad visas atlasītās entītijas ir ielādētas, izmantojiet datu vizualizēšanas Power BI iespējas.

## <a name="large-data-sets"></a>Lielas datu kopas

Customer Insights savienotājs Power BI ir paredzēts darbam ar datu kopām, kurās ir līdz 1 000 000 klientu profilu. Lielāku datu kopu importēšana var darboties, taču tai var būt nepieciešams ilgs laiks, un ierobežojumu dēļ tā var pārtraukt taimautu Power BI. Papildinformāciju skatiet [Power BI: ieteikumi lielām datu kopām](/power-bi/admin/service-premium-what-is#large-datasets).

### <a name="work-with-a-subset-of-data"></a>Darbs ar datu apakškopu

Apsveriet iespēju strādāt ar datu apakškopu. Piemēram, izveidojiet [segmentus](segments.md), nevis eksportējiet visus debitoru ierakstus uz Power BI.

## <a name="troubleshooting"></a>Problēmu novēršana

### <a name="customer-insights-environment-doesnt-show-in-power-bi"></a>Customer Insights vide netiek rādīta programmā Power BI

Vides, kurās ir vairākas [relācijas](relationships.md), kas definētas starp divām identiskām entītijām programmā Customer Insights, savienotājā Power BI nebūs pieejamas.

Identificējiet un noņemiet dublētās relācijas.

1. Dodieties uz sadaļu Datu **relācijas** > **vidē, kuras jums trūkst**.Power BI
1. Nosakiet dublicētās attiecības:
   - Pārbaudiet, vai starp vienām un tām pašām divām entītijām ir definētas vairākas attiecības.
   - Pārbaudiet, vai ir izveidotas attiecības starp divām entītijām, kas ir iekļautas apvienošanas procesā. Pastāv netiešas attiecības, kas tiek definētas starp visām entītijām, kas ir iekļautas apvienošanas procesā.
1. Noņemiet visus identificēto attiecību dublikātus.

Pēc dublicēto attiecību noņemšanas mēģiniet vēlreiz konfigurēt Power BI savienotāju.

### <a name="errors-on-date-fields-when-loading-entities-in-power-bi-desktop"></a>Kļūdas datuma laukos, ielādējot entītijas programmā Power BI Desktop

Ielādējot entītijas, kurās ir lauki ar datuma formātu, piemēram, MM/DD/GGGG, var rasties kļūdas neatbilstošu lokalizācijas formātu dēļ. Šī neatbilstība rodas, ja Power BI Desktop failam ir iestatīta cita lokalizācija, nevis angļu valoda (Amerikas Savienotās Valstis), jo datuma lauki customer insights tiek saglabāti ASV formātā.

Power BI Desktop failam ir viens lokalizācijas iestatījums, kas tiek lietots, izgūstot datus. Lai labotu datuma kļūdas, [iestatiet . BPI fails](/power-bi/fundamentals/supported-languages-countries-regions#choose-the-language-or-locale-of-power-bi-desktop) angļu valodā (Amerikas Savienotās Valstis).

[!INCLUDE [footer-include](includes/footer-banner.md)]
