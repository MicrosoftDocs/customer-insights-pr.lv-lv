---
title: Nezināmu profilu pārvaldība, izmantojot Customer Insights
description: Darbs ar nezināmiem klientu profiliem, kas ir izveidoti un pārvaldīti pakalpojumā Dynamics 365 Customer Insights.
ms.date: 09/14/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: andtapia
ms.author: andreatapia
manager: shellyha
ms.openlocfilehash: 0e12f64a22b93d117009fb8aee76d02a7583e699
ms.sourcegitcommit: 24627d53dcdf607baaab1cc3c299a3584c386173
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 11/15/2022
ms.locfileid: "9776830"
---
# <a name="manage-unknown-profiles-with-customer-insights"></a>Nezināmu profilu pārvaldība, izmantojot Customer Insights

Interneta lietotāji tiešsaistē bieži vien ir neidentificēti vai anonīmi. Pat lojālākie klienti var šķist "nezināmi", ja viņi nav pierakstījušies dažādās ierīcēs. Daudziem zīmoliem zināmi vai autentificēti lietotāji ir mazākums, neskatoties uz pieaugošajām klientu vēlmēm saistībā ar personalizāciju. Ņemot vērā attiecīgo trešo pušu sīkfailu nākotni, lietotāju preferenču pārvaldība, pamatojoties uz pirmās puses datiem, ir būtiska, lai sasniegtu personalizētu pieredzi.

Neaizmirstama personalizēšana ir atkarīga no tā, cik labi pazīstat savu klientu, un programma Customer Insights palīdz to izdarīt, izsekojot visus klientus.  Jums nav jāierobežo vai jāpārtrauc automatizēta kampaņa sākumā savākto datu izmantošana. Customer Insights ļauj jums izmantot savus datus, lai izveidotu klientu profilu nezināmiem lietotājiem. Pēc tam varat izmantot šo profilu turpmākām darbībām, ja trūkst kontaktinformācijas. Importējiet pirmās puses datus no tādiem avotiem kā tīmekļa, mobilās vai CRM sistēmas programmā Customer Insights, lai nepārtraukti bagātinātu klientu profilus. Apvienojot vairāk mijiedarbību, [pārvērtiet nezināmo *klientu* par *zināmu* klientu](unknown-to-known.md).

## <a name="sample-scenario"></a>Scenārija paraugs

Pieņemsim, ka lietotājs izmanto savu mobilo ierīci, lai pārlūkotu jūsu e-komercijas vietni. Vietne piešķir apmeklētājam "mobile_guest123" kā unikālu identifikatoru, un jūs sākat apkopot uzvedības aktivitātes, pamatojoties uz viņu tiešsaistes darbībām. Piemēram, kuras lapas viņi apmeklēja, cik daudz laika viņi pavadīja šajās lapās vai uz kurām saitēm viņi noklikšķināja. Jūs nezināt viņu vārdu vai e-pasta adresi, taču šie dati var palīdzēt zīmoliem sniegt jēgpilnus ieskatus par šo konkrēto lietotāju. Savukārt varat likt šiem ieskatiem darboties nākamreiz, kad lietotājs apmeklēs vietni. Pieprasiet Customer Insights līdzeklim "mobile_guest123", lai izgūtu lietotāja segmentu sarakstu, piemēram, "organiskie", "mobilie priekšpasūtīšanas klienti", "augstvērtīgie klienti" utt., vai izgūtu profilu, lai izveidotu personalizētu tīmekļa pieredzi. Varat arī eksportēt datus uz jebkuru aktivizācijas sistēmu, lai to izdarītu.

## <a name="prerequisites"></a>Priekšnoteikumi

- Pirmās puses datu uzņemšana programmā Customer Insights
- Katrai entītijai ir unikāls ID, kas ir iestatīts kā primārā atslēga
- Katra entītija ar primāro atslēgu personalizēšanai ir vienota
- Jūsu tīmekļa vietnes satura pārvaldības sistēma var izmantot API (tīmekļa personalizēšanai, kuras pamatā ir tieša saziņa ar Customer Insights)

Tālāk esošajā tabulā ir parādīts vienkāršots piemērs, kā var tvert augstvērtīgus tīmekļa notikumus.

|Notikuma ID|EventTimeStamp|UserID|PrimaryKey|Notikuma nosaukums|
|--|--|--|--|--|
|1|09-15-2022 9:00:00|ABC123|CookieID1|Produkta skats|
|2|09-18-2022 10:05:00|ABC123|CookieID1|Produkta skats|
|3|09-18-2022 10:10:00|ABC123|CookieID1|Pievienot pirkumu grozam|
|4|09-21-2022 09:05:00|ABC123|CookieID1|Produkta skats|

## <a name="data-ingestion"></a>Datu pieņemšana

Papildinformāciju par pieejamajām datu uzņemšanas opcijām skatiet rakstā [Datu avotu pārskats](data-sources.md).

## <a name="data-unification"></a>Datu apvienošana

Papildinformāciju par klientu profilu apvienošanu skatiet rakstā [Datu apvienošanas pārskats](data-unification.md).

## <a name="get-insights"></a>Iegūt ieskatus

[Bagātiniet](enrichment-hub.md) savus datus, veidojiet [mērus](measures.md) un izveidojiet [segmentus](segments.md) turpmākai aktivizēšanai.

Piemēram, varat izveidot nezināmu lietotāju segmentus, kuri pārlūkoja vienas un tās pašas produktu lapas, bet nekad nepabeidza norēķināšanos.

## <a name="activation"></a>Aktivizācija

Tā kā jūsu dati programmā Customer Insights un ieskati ir gatavi darbam, personalizēšanai varat izmantot Customer Insights:

1. [OData API izmantošana, lai izgūtu segmenta dalību vai klienta profilu Papildinformāciju skatiet rakstā](apis.md) OData vaicājumu piemēri Customer Insights [API](odata-examples.md).

1. [Eksportējiet](export-destinations.md) datus uz aktivizācijas sistēmām.

Piemērs: nezināms lietotājs apmeklē vietni vairākas reizes un apmeklē dažādu ādas apavu modeļu produktu lapas. Izmantojot šos datus, kas pieejami programmā Customer Insights, varat iekļaut nezināmo lietotāju to cilvēku segmentā, kurus interesē ādas apavi. Izmantojiet šo segmentu, lai informētu par savas vietnes izveides personalizāciju apmeklētājiem, kas atgriežas. Nākamajā apmeklējumā vietne atpazīst nezināmo lietotāju un varētu viņiem piedāvāt 10% kuponu ādas apaviem.

[!INCLUDE [footer-include](includes/footer-banner.md)]
