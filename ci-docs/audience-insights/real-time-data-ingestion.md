---
title: Reāllaika datu uzņemšana un ierobežojumi
description: Vispārīga informācija par reāllaika iespējām rīkā auditorijas ieskati.
ms.date: 10/27/2020
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b00a72e6a67e33c8e70ccc6139c5e62020f9d3e1
ms.sourcegitcommit: b50c754481d0af6d0cf4b550775d7b31d95846ef
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 12/06/2020
ms.locfileid: "4689184"
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

- [netieši](#connect-via-the-dynamics-365-customer-insights-connector), izmantojot [Dynamics 365 Customer Insights savienotāju](https://docs.microsoft.com/connectors/customerinsights/)
- [tieši](#connect-directly-to-the-real-time-api), ar kodu

Abiem veidiem ir šādi priekšnosacījumi:

- Customer Insights vide
- Vienoti klientu profili
- Konfigurētās un palaistās darbības
- Līdzstrādnieka vai administratora atļauja jūsu uzņēmuma autentificēšanai

## <a name="connect-via-the-dynamics-365-customer-insights-connector"></a>Pieslēdzieties, izmantojot Dynamics 365 Customer Insights savienotāju

Reāllaika API var uzņemt datus no īpaša Power Platform savienotāja, [Dynamics 365 Customer Insights savienotāja ](https://docs.microsoft.com/connectors/customerinsights/) bez vajadzības rakstīt un izvietot kodu.    
Savienotājs var veikt tādas pašas reāllaika darbības kā API. Premium savienotājiem ir nepieciešama derīga licence. Papildinformāciju skatiet sadaļā [Power Apps un Power Automate licencēšanas BUJ](https://docs.microsoft.com/power-platform/admin/powerapps-flow-licensing-faq).

- Power Platform [Power Apps un/vai Power Automate](https://docs.microsoft.com/connectors/)
- Azure [Logic Apps](https://docs.microsoft.com/azure/connectors/apis-list)

Papildinformāciju par plūsmu izveidi skatiet [Power Automate dokumentācijā](https://docs.microsoft.com/power-automate/).

## <a name="connect-directly-to-the-real-time-api"></a>Tieša savienojuma izveide ar reāllaika API

Varat izmantot reāllaika iespējas, veidojot savu konveijeru un izveidojot savienojumu tieši ar reāllaika API.    
Darbību varat publicēt savas avotsistēmas formātā vai UnifiedActivity formātā. Iegūstiet formātu, veicot API izsaukumu uz /api/instances/{instanceId}/manage/entities/UnifiedActivity.

Detalizēta informācija par šo API, ieskaitot parametrus un atbildes, ir atrodama **EntityData** sadaļā [Customer Insights API atsauce](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). Papildinformāciju skatiet tēmā [Darbs ar Customer Insights API](apis.md).

## <a name="understand-your-real-time-usage-with-telemetry"></a>Reāllaika lietojuma izprašana, izmantojot telemetriju

Iegūstiet pārskatu par reāllaika API pieprasījumu apjomu un informāciju par problēmām, kas sistēmai var rasties. Varat [piekļūt reāllaika telemetrijai](system.md#api-usage-tab), atverot **Administrators** > **Sistēma** > **API lietojums**. Tabulā **Darbības** API darbību rindās, kas izmanto reāllaika metodes, ir poga, lai skatītu reāllaika API izmantošanu. Poga tiek vizualizēta ar tālskati. Atlasiet pogu, lai atvērtu sānu rūti, kurā ir detalizēta lietošanas instrukcija par reāllaika API izmantošanu pašreizējā vidē.

Lietojiet **Grupēt pēc** atlasītāju, lai izvēlētos, kā vislabāk attēlot reāllaika mijiedarbības laika skalā, sākot no pēdējām 24 stundām līdz pēdējām 30 dienām. Grupējiet datus pēc API metodes, entītijas nosaukums (izveidotā entītija), izveidoja (notikuma avots), rezultāts (veiksmīgi vai kļūme) vai kļūdu kodi. Dati ir pieejami kā vēstures diagramma un kā tabula.
