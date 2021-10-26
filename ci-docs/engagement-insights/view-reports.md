---
title: Skatīt datu atskaites
description: Izmantojiet pieejamās atskaites, lai skatītu reāllaika darbību savā vietnē.
author: darrinw-docs
ms.reviewer: mhart
ms.author: darrinw
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 5ccdcb47db597154cf79b9f2e8fc238ab75dfde9
ms.sourcegitcommit: d9965f4bfc09391698a34042f6b44367e53819e3
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 09/30/2021
ms.locfileid: "7582931"
---
# <a name="view-reports"></a>Skatīt atskaites

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Atskaite ir datu vizualizāciju apkopojums, kas, izmantojot SDK apkopotos datus, palīdz mērīt un izprast lietotāja uzvedību. Dynamics 365 Customer Insights iesaistes ieskati ietver gatavas (OOB) atskaites tīmekļa un mobilajiem projektiem.  

## <a name="web-reports"></a>Tīmekļa atskaites

Tīmekļa atskaitēm varat piekļūt kreisās puses navigācijas rūts sadaļā **Atklāt**.

:::image type="content" source="media/report-menu.png" alt-text="Navigācija, kurā redzams pieejamo atskaišu saraksts.":::

### <a name="real-time-usage-report"></a>Reāllaika lietojuma atskaite

**Reāllaika lietojuma** atskaite sniedz apskatu par jūsu vietnes pašreizējo darbību, kas automātiski tiek atsvaidzināta ik pēc minūtes. Izmantojiet reāllaika lietojumu, lai pārraudzītu mārketinga kampaņu, preses pasākumu un citu scenāriju ietekmi uz jūsu vietnes datplūsmu.

### <a name="key-metrics-reports"></a>Galveno rādītāju atskaites

- **Lapas skatījumos** ir norādīti atsevišķu lapu skatījumi un arī kopējais lapu skatījumu skaits atlasītajā laika periodā.

- **Apmeklējumos** tiek rādīta informācija par apmeklējumu skaitu un apmeklējuma ilgumu.

- **Apmeklētāji** informē par jauniem un atkārtotiem unikāliem vietnes apmeklētājiem.

### <a name="content-reports"></a>Satura atskaites

- **Saites** tiek rādīta informācija par klikšķu skaitu un veidu.

- **Izvades lapās** ir norādītas saites, uz kurām apmeklētāji uzklikšķina, lai izietu no jūsu vietnes.

### <a name="traffic-sources-reports"></a>Datplūsmas avotu atskaites

- **Nosūtītājos** ir norādīti domēni un vietrāži URL, kas nosūtīja apmeklētājus uz jūsu vietni.

- **Izsekošanas kodi** nodrošina informāciju par izsekošanas kodiem saitēs, kas nosūtīja apmeklētājus uz jūsu vietni.

### <a name="visitor-profiles-reports"></a>Apmeklētāju profilu atskaites

- **Ierīcēs** ir norādītas fiziskas ierīces, kas tika izmantotas, lai piekļūtu jūsu vietnei.

- **Operētājsistēmas un pārlūkprogrammas** nodrošina ieskatu par operētājsistēmām un pārlūkprogrammām, kas darbojās, piekļūstot jūsu vietnei.

- **Atrašanās vietās** tiek rādīta informācija par apmeklētājiem pēc valsts, reģiona un pilsētas.

- **Valodās** ir norādīti lapas skatījumi pēc apmeklētāja vēlamās valodas.

## <a name="mobile-reports"></a>Atskaite mobilajām ierīcēm

Atskaites mobilajam ierīcem tiek grupētas reāllaika lietojuma, programmas un lietotāju kategorijās. Mobilo ierīču atskaitēm varat piekļūt kreisās puses navigācijas rūts sadaļā **Atklāt**.   

:::image type="content" source="media/mobile-reports.png" alt-text="Lietotāja interfeisa iesaistes ieskatā tiek rādīta reāllaika lietojuma atskaite, kas datus atveido diagrammās un sarakstos.":::   

### <a name="real-time-usage"></a>Reāllaika lietojums

**Reāllaika lietojums** nodrošina pārskatu par jūsu mobilās programmas pašreizējo darbību, kas tiek atsvaidzināts automātiski ik pēc minūtes. Izmantojot reāllaika lietojumu, varat pārraudzīt jūsu programmas šobrīd aktīvo lietotāju un sesiju skaitu un lielāko ekrāna skatījumu skaitu.

### <a name="app-reports"></a>Programmas atskaites

- **Ekrāna skatījumos** ir norādīti ekrāna skatījumi atsevišķiem ekrāniem programmā un kopējais ekrāna skatījumu skaits atlasītajā laika periodā. Ekrāna skatījumus var skatīt pēc ekrāna apzīmējuma vai ekrāna nosaukuma.

- **Sesijās** tiek rādīta informācija par sesiju skaitu un sesiju ilgumu.

- **Atgriešanas biežums** grupē sesiju skaitu pēc dienu skaita kopš pēdējās sesijas.

- **Lietotājos** tiek rādīti jūsu mobilās programmas jaunie un atkārtotie lietotāji.

- **Notikumos** ir norādīti visi jūsu programmā apkopotie notikumi, kā arī kopējais katra notikuma skaits.

### <a name="user-reports"></a>Lietotāju atskaites

- **Programmu versijās** ir norādītas jūsu mobilās programmas versijas, ko izmanto lietotāji.

- **Ierīces un operētājsistēmas versijas** nodrošina ieskatus par ierīcēm un operētājsistēmām, kurās darbojas jūsu mobilā programma.

- **Atrašanās vietās** tiek rādīta informācija par programmas lietotājiem pēc valsts, reģiona un pilsētas.

## <a name="filter-by-time-or-date-range"></a>Filtrējiet pēc laika vai datu diapazona

Tīmekļa vai mobilās versijas atskaitē var atlasīt laika periodu vai datumu diapazonu, lai koncentrētos uz vērtību vai laika periodu. 

- Lai atlasītu laika periodu, atskaites skata augšējā labajā stūrī atlasiet vērtību no atskaites nolaižamā saraksta. Varat arī izvēlēties **Fiksētu datu diapazonu**. 

  :::image type="content" source="media/filter-by-time.png" alt-text="Filtrējiet pēc laika vai datu diapazona.":::   

- Lielākajai daļai atskaišu atlasiet vērtību diagrammā vai sarakstā, lai filtrētu atskaiti.

> [!NOTE]
> Laika diapazona atlase reāllaika lietojuma atskaitei ir atspējota; reāllaika lietojuma atskaites laika diapazons ir "tagad."


[!INCLUDE[footer-include](../includes/footer-banner.md)]
