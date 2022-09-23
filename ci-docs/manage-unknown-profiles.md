---
title: Nezināmu profilu pārvaldība, izmantojot Customer Insights
description: Darbs ar nezināmiem klientu profiliem, kas ir izveidoti un pārvaldīti Dynamics 365 Customer Insights.
ms.date: 09/14/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: andtapia
ms.author: andreatapia
manager: shellyha
ms.openlocfilehash: d7e5050ee5832df5ecf40a352f7ea8d42830fa45
ms.sourcegitcommit: f6b6a4c4ce9cf12e449488b24aab80a2cbfe0c47
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 09/21/2022
ms.locfileid: "9556405"
---
# <a name="manage-unknown-profiles-with-customer-insights"></a>Nezināmu profilu pārvaldība, izmantojot Customer Insights

Interneta lietotāji bieži vien ir neidentificēti un anonīmi tiešsaistē. Ja viņi nav pieteikušies, jo izmanto dažādas ierīces vai kanālus, tas pat attiecas uz lojālākajiem klientiem. Tā kā trešo pušu sīkfaili, visticamāk, drīz izzudīs, lietotāju preferenču pārvaldība, pamatojoties uz pirmās puses datiem, ir ļoti svarīga, lai panāktu diferencētu personalizētu pieredzi. Daudziem zīmoliem zināmi vai autentificēti lietotāji ir mazākumā, neskatoties uz pieaugošajām klientu vēlmēm saistībā ar personalizāciju. Uzņēmumiem ir lieliski zināt, kas ir viņu klienti, pamatojoties uz uzticamiem, detalizētiem un vienotiem datiem.

Neaizmirstama personalizācija ir atkarīga no jūsu klientu datu bagātības un pilnīguma, un Customer Insights palīdz sasniegt šos mērķus. Jums nav jāierobežo vai jāpārtrauc to datu izmantošana, kas savākti automatizēta kampaņa sākumā. Customer Insights ļauj paņemt līdzi savus datus, lai izveidotu klienta profilu nezināmiem lietotājiem. Pēc tam varat izmantot šo profilu turpmākām darbībām, neskatoties uz to, ka trūkst kontaktinformācijas. Importējiet pirmās puses datus no tādiem avotiem kā tīmekļa, mobilās vai CRM sistēmas customer insights, lai nepārtraukti bagātinātu klientu profilus. Apvienojot vairāk mijiedarbības, [pārvērtiet nezināmo *klientu* par *zināmu* klientu](unknown-to-known.md).

## <a name="sample-scenario"></a>Scenārija paraugs

E-komercija ir visstraujāk augošais kanāls pēdējo desmit gadu laikā. Pieņemsim, ka lietotājs izmanto savu mobilo ierīci, lai pārlūkotu jūsu e-komercijas vietni. Vietne piešķir apmeklētājam "mobile_guest123" kā unikālu identifikatoru, un jūs sākat apkopot uzvedības aktivitātes, pamatojoties uz viņa darbībām tiešsaistē. Piemēram, kuras lapas viņi apmeklēja, cik daudz laika viņi pavadīja šajās lapās vai uz kurām saitēm viņi noklikšķināja. Jūs nezināt viņu vārdu vai e-pasta adresi, taču šie dati var palīdzēt sniegt zīmoliem jēgpilnu ieskatu par šo konkrēto lietotāju. Savukārt jūs varat likt šiem ieskatiem darboties nākamajā reizē, kad lietotājs apmeklēs vietni. Vaicājums Customer Insights par "mobile_guest123", lai izgūtu lietotāja segmentu sarakstu, piemēram, "organiskie", "mobilie priekšpasūtīšanas klienti", "augstvērtīgie klienti" utt., vai izgūt profilu, lai izveidotu personalizētu tīmekļa pieredzi. Varat arī eksportēt datus uz jebkuru aktivizācijas sistēmu, lai darītu to pašu.

## <a name="prerequisites"></a>Priekšnoteikumi

- Pirmās puses datu ienešana programmā Customer Insights
- Katrai entītijai ir unikāls ID, kas ir iestatīts kā primārā atslēga
- Katra entītija ar primāro atslēgu personalizēšanai ir vienota
- Jūsu tīmekļa vietnes satura pārvaldības sistēma spēj izmantot API (tīmekļa personalizēšanai, pamatojoties uz tiešu saziņu ar Customer Insights)

Nākamajā tabulā ir parādīts vienkāršots piemērs tam, kā varētu tikt tverti augstvērtīgi tīmekļa notikumi.

|Notikuma ID|EventTimeStamp|Lietotāja ID|Primārais taustiņš|Notikuma_nosaukums|
|--|--|--|--|--|
|1|09-15-2022 9:00:00|abc123|SīkdatneID1|Produkta skats|
|2|09-18-2022 10:05:00|abc123|SīkdatneID1|Produkta skats|
|3|09-18-2022 10:10:00|abc123|SīkdatneID1|Pievienot pirkumu grozam|
|4|09-21-2022 09:05:00|abc123|SīkdatneID1|Produkta skats|

## <a name="data-ingestion"></a>Datu pieņemšana

Papildinformāciju par pieejamajām datu uzņemšanas opcijām skatiet rakstā [Pārskats par datu avotiem](data-sources.md).

## <a name="data-unification"></a>Datu apvienošana

Papildinformāciju par klientu profilu apvienošanu skatiet rakstā [Datu apvienošanas pārskats](data-unification.md).

## <a name="get-insights"></a>Iegūt ieskatus

[Bagātiniet](enrichment-hub.md) savus datus, veidojiet [mērus](measures.md) un izveidojiet [segmentus](segments.md) turpmākai aktivizēšanai.

Piemēram, varat izveidot nezināmu lietotāju segmentus, kuri pārlūkoja vienas un tās pašas produktu lapas, bet nekad nav pabeiguši norēķināšanos.

## <a name="activation"></a>Aktivizācija

Izmantojot savus Customer Insights datus un ieskatus, kas ir gatavi ķerties pie darba, personalizēšanai varat izmantot Customer Insights:

1. [Izmantojiet OData API](apis.md), lai izgūtu dalību segmentā vai klienta profilu Papildinformāciju skatiet rakstā [OData vaicājumu piemēri Customer Insights API.](odata-examples.md)

1. [Eksportējiet](export-destinations.md) datus uz aktivizācijas sistēmām.

Piemērs: nezināms lietotājs vairākas reizes apmeklē vietni un apmeklē dažādu ādas apavu modeļu produktu lapas. Izmantojot šos datus, kas pieejami programmā Customer Insights, varat iekļaut nezināmo lietotāju to cilvēku segmentā, kurus interesē ādas apavi. Izmantojiet šo segmentu, lai informētu par savas vietnes veidošanas personalizēšanu apmeklētājiem, kas atgriežas. Nākamajā vizītē vietne atpazīst nezināmo lietotāju un varētu piedāvāt viņiem 10% kuponu ādas apaviem.

[!INCLUDE [footer-include](includes/footer-banner.md)]
