---
title: Izmantot debitora piekrišanu
description: Ievērojiet klientu piekrišanas preferences customer insights, importējot piekrišanas datus.
ms.date: 06/07/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 77b09b6eb0a916e724542d503d96d19c5581aca1
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 06/14/2022
ms.locfileid: "8947525"
---
# <a name="use-customer-consent"></a>Izmantot debitora piekrišanu

Datu aizsardzības un privātuma noteikumi nodrošina privātpersonām tiesības reglamentēt, kā organizācija izmanto viņu personas datus. Šādu noteikumu piemēri ir Vispārīgā datu aizsardzības regula Eiropas Savienībā vai Kalifornijas Patērētāju privātuma likums Amerikas Savienotajās Valstīs. Šie noteikumi ļauj cilvēkiem atteikties no personas datu vākšanas, apstrādes vai kopīgošanas ar trešām personām.  

Klienti var izvēlēties atsaukt vai nedot piekrišanu konkrētiem saziņas veidiem. Viņi var arī pieprasīt, lai jūs atsakāties no viņu personas datu vākšanas, glabāšanas, izmantošanas vai pārdošanas. Ir svarīgi, lai jūsu organizācija ievērotu visu klientu piekrišanu un konfidencialitātes preferences.  

Dynamics 365 Customer Insights palīdz apmierināt klientu pieprasījumus, importējot un saglabājot viņu preferences kā daļu no vienotajiem klientu profiliem.

Ja piekrišanas dati tiek glabāti atsevišķi no jūsu klientu profiliem, [pievienojiet piekrišanas datus kā jaunu datu avots](#import-and-unify-consent-data). Datu apvienošanas procesam tiek pievienota datu avots, kas satur piekrišanas datus. Veiksmīga piekrišanas datu un klientu profilu apvienošana pēc tam noved pie vienotiem klientu profiliem, kas satur piekrišanas informāciju. Klientu profiliem, kuros jau ir informācija par piekrišanu, dodieties tieši uz sadaļu Piekrišanas [datu](#use-consent-data) izmantošana.

## <a name="prerequisites"></a>Priekšnoteikumi

Lai apvienotu piekrišanas datus ar citiem klientu profiliem, avota datos jābūt pieejamai šādai informācijai:

- Alternatīvā atslēga, lai kartētu piekrišanas informāciju uz lietotāju profiliem customer insights. Piemēram, e-pasta adrese vai tālruņa numurs.
- Piekrišanas vērtība, lai noteiktu klienta piekrišanas statusu.

Apsveriet iespēju pievienot šādu *neobligātu* informāciju:

- Primārā atslēga piekrišanas statusa atjaunināšanai, ja klients pieprasa izmaiņas.
- Piekrišanas veids, ja ir vairāki veidi, kā apstrādāt klientu informāciju.
- Piekrišanas datums vai jebkāda cita veida dati, kas attiecas uz jūsu piekrišanas scenārijiem.

Vienkāršas piekrišanas datu bāzes tabulas piemērs ar vairākām piekrišanas opcijām:

|Piekrišanas ID (primārā atslēga)   |E-pasts (alternatīvā atslēga)  |Piekrišanas opcija  |Piekrišanas vērtība  |
|---------|---------|---------|---------|
|1    |  holly@contoso.com       |  Biļetenu       |  Nepatiess       |
|2    |  holly@contoso.com       |  Produktu atjauninājumi       |  Patiess       |
|3    |  frank@contoso.com       |  Biļetenu       | Patiess        |
|4    |  frank@contoso.com       |  Produktu atjauninājumi       |  Nepatiess       |

## <a name="import-and-unify-consent-data"></a>Piekrišanas datu importēšana un vienādošana

Piekrišanas datus var importēt tāpat kā citus datu avotus pakalpojumā Customer Insights. Papildinformāciju par atbalstītajiem datu avotiem un to importēšanu skatiet sadaļā [Datu avotu pārskats](data-sources.md).

Papildinformāciju par datu avotu apvienošanu skatiet rakstā [Datu apvienošanas pārskats](data-unification.md).

## <a name="use-consent-data"></a>Piekrišanas datu izmantošana

Kad jūsu piekrišanas dati ir daļa no jūsu vienotajiem klientu profiliem, varat tos izmantot customer insights. Piemēram, izveidojiet segmentu ar kārtulu, lai nodrošinātu klientu konfidencialitātes un datu aizsardzības preferenču ievērošanu. Kārtulas, kas atbalsta piekrišanas preferences, tiek izmantotas, lai izslēgtu lietotājus no segmenta, kura pamatā ir profila atribūti. Kārtulas pievienošana segmentam, kas izslēdz klientu profilus, kuri nesniedza piekrišanu saziņai.

Atsaucoties uz iepriekš redzamo paraugu tabulu, segmentā var būt šis noteikums:`Consent option=Newsletter & Consent value=True`. Šīs konfigurācijas rezultātā tiek izveidots segments, kas ievēro kontaktpersonu preferences, lai nosūtītu biļetenu.

Papildinformāciju par segmentu veidošanu skatiet rakstā [Segmentu](segment-builder.md) izveide.

Kad segments ir izveidots, varat izmantot vienu no daudzajām [eksportēšanas opcijām](export-destinations.md), lai segmentu izmantotu citās lietojumprogrammās.

## <a name="ensure-updated-consent-status"></a>Nodrošināt atjauninātu piekrišanas statusu

Ir svarīgi atjaunināt klientu piekrišanas statusu. Programmā Customer Insights ieplānotā atsvaidzināšana vienmēr importē jūsu datu avotu jaunāko stāvokli. Pēc tam šī informācija tiek apstrādāta, apvienojot datus, un tās rezultātā tiek atjaunināti klientu profili. Pēc tam šie atjauninātie profili tiek izmantoti segmentu atsvaidzināšanai, lai pārliecinātos, ka strādājat ar visjaunāko informāciju.

Citiem vārdiem sakot, pārliecinieties, vai avota datiem, kas tiek importēti pakalpojumā Customer Insights, vienmēr ir jaunākā informācija.

Papildinformāciju skatiet rakstā [Segmentu atsvaidzināšana manuāli](segments.md#refresh-segments) vai [ieplānotas atsvaidzināšanas](system.md#schedule-tab) konfigurēšana.
