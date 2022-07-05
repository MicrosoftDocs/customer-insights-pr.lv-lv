---
title: Reāllaika datu uzņemšana (priekšskatījums)
description: Vispārīga informācija par reāllaika iespējām programmā Customer Insights.
ms.date: 10/27/2020
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
searchScope:
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: 39d68011df9e4341244af627bb71f4e3635256bb
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 06/29/2022
ms.locfileid: "9083187"
---
# <a name="real-time-data-ingestion-preview"></a>Reāllaika datu uzņemšana (priekšskatījums)

Teju reāllaika funkcionalitāte ļauj sekunžu laikā redzēt pēdējo mijiedarbību, kura jūsu klientiem ir bijusi ar jūsu precēm vai pakalpojumiem.

[Plānotā atjaunināšana](system.md#schedule-tab) ietver lielu skaitu ierakstu un vairākas sarežģītas operācijas. Vispirms dati tiek izvilkti no datu avota. Pēc tam dati ir apvienoti un bagātināti ar papildinformāciju. Katra šī procesa palaišana var aizņemt vairākas minūtes vai stundas.

Reāllaika funkcionalitāte nodrošina tūlītēju datu patēriņu, kamēr turpmāk plānotā atsvaidzināšana izrauj šos datus no datu avota.

Reāllaika atjauninājumiem ir derīguma laiks, pēc kura tie vairs nepārlabo vērtību no datu avota:

- Profila atjauninājumi tiks saglabāti 4 stundas
- Darbības tiks saglabātas 30 dienas

Šīs vērtības ir API izsaukuma parametri, kuras varat mainīt. To mērķis ir nodrošināt, lai avota dati paliktu jūsu patiesības avots. Ja vēlaties, lai reāllaika atjauninājumi tiktu iekļauti ilgāku laiku, tie ir jāpievieno datu avotam tā, lai tie tiktu vilkti nākamajā plānotajā atsvaidzināšanas laikā.

## <a name="real-time-update-of-the-unified-customer-profile-fields"></a>Vienotā klienta profila lauku atjaunināšana reāllaikā

Atjauninātie profili tiks parādīti klienta kartīšu skatā vai jebkurā citā vizualizācijā dažu sekunžu laikā.

Tā kā reāllaika operācijas notiek pēc tam, kad ir notikusi datu apvienošana, tās attiecas vienīgi uz vienotiem klientu profiliem. Līdz ar to reāllaika profila izmaiņas neatjauninās mērus, segmentu elementus vai bagātināšanu.

### <a name="limitations"></a>Ierobežojumi

- Klientu profilus var atjaunināt, taču ne izveidot vai dzēst.
- Reāllaika atjauninājumu eksportēšana ārējās sistēmās, piemēram Power BI, pašlaik nav iespējama.

## <a name="real-time-creation-of-activities"></a>Darbību izveide reāllaikā

Reāllaika API ļauj publicēt jaunu darbību no avota sistēmas (atsevišķa avota ieraksta) uz vienoto klienta profilu. Jaunā darbība dažu sekunžu laikā būs pieejama kā vienota darbība šī vienota klienta profila laika skalā. Laika skalu varat skatīt klienta kartes skatā vai jebkurā citā jūsu konfigurētajā laika skalas integrācijā.

> [!NOTE]
>
> - Darbības ir nemaināmas. Pēc savas izveidošanas tās nemainās.
> - Pašlaik segmenti un mēri netiks atjaunināti, pamatojoties uz jaunām darbībām.
> - Darbības, kas pievienotas vienīgi ar reāllaika API, nav daļa no eksporta un netiks rādītas PowerBI.

Ir divi paņēmieni, kā izveidot savienojumu ar reāllaika API.

- [netieši](#connect-via-the-dynamics-365-customer-insights-connector), izmantojot [Dynamics 365 Customer Insights savienotāju](/connectors/customerinsights/)
- [tieši](#connect-directly-to-the-real-time-api), ar kodu

Abiem veidiem ir šādi priekšnosacījumi:

- Customer Insights vide
- Vienoti klientu profili
- Konfigurētās un palaistās darbības
- Līdzstrādnieka vai administratora atļauja jūsu uzņēmuma autentificēšanai

## <a name="connect-via-the-dynamics-365-customer-insights-connector"></a>Pieslēdzieties, izmantojot Dynamics 365 Customer Insights savienotāju

Reāllaika API var uzņemt datus no īpaša Power Platform savienotāja, [Dynamics 365 Customer Insights savienotāja ](/connectors/customerinsights/) bez vajadzības rakstīt un izvietot kodu.    
Savienotājs var veikt tādas pašas reāllaika darbības kā API. Premium savienotājiem ir nepieciešama derīga licence. Papildinformāciju skatiet sadaļā [Power Apps un Power Automate licencēšanas BUJ](/power-platform/admin/powerapps-flow-licensing-faq).

- Power Platform [Power Apps un/vai Power Automate](/connectors/)
- Azure [Logic Apps](/azure/connectors/apis-list)

Papildinformāciju par plūsmu izveidi skatiet [Power Automate dokumentācijā](/power-automate/).

## <a name="connect-directly-to-the-real-time-api"></a>Tieša savienojuma izveide ar reāllaika API

Varat izmantot reāllaika iespējas, veidojot savu konveijeru un izveidojot savienojumu tieši ar reāllaika API.    
Darbību varat publicēt savas avotsistēmas formātā vai UnifiedActivity formātā. Iegūstiet formātu, veicot API izsaukumu uz /api/instances/{instanceId}/manage/entities/UnifiedActivity.

Detalizēta informācija par šo API, ieskaitot parametrus un atbildes, ir atrodama **EntityData** sadaļā [Customer Insights API atsauce](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). Papildinformāciju skatiet tēmā [Darbs ar Customer Insights API](apis.md).

## <a name="understand-your-real-time-usage-with-telemetry"></a>Reāllaika lietojuma izprašana, izmantojot telemetriju

Iegūstiet pārskatu par reāllaika API pieprasījumu apjomu un informāciju par problēmām, kas sistēmai var rasties. Varat piekļūt [reāllaika telemetrijai](system.md#api-usage-tab). 


[!INCLUDE [footer-include](includes/footer-banner.md)]
