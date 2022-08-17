---
title: Izmantojiet klienta piekrišanu
description: Ievērojiet klientu piekrišanas preferences programmā Customer Insights, importējot piekrišanas datus.
ms.date: 06/07/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 6c951219410b55adc34691f677158b574cea1e01
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245704"
---
# <a name="use-customer-consent"></a>Izmantojiet klienta piekrišanu

Datu aizsardzības un privātuma noteikumi nodrošina personām tiesības reglamentēt, kā organizācija izmanto viņu personas datus. Šādu noteikumu piemēri ir Vispārīgā datu aizsardzības regula Eiropas Savienībā vai Kalifornijas Patērētāju konfidencialitātes likums Amerikas Savienotajās Valstīs. Šie noteikumi ļauj cilvēkiem atteikties no viņu personas datu vākšanas, apstrādes vai kopīgošanas ar trešajām pusēm.  

Klienti var izvēlēties atsaukt vai nesniegt savu piekrišanu konkrētiem saziņas veidiem. Viņi var arī pieprasīt, lai jūs atteiktos no viņu personas datu vākšanas, glabāšanas, izmantošanas vai pārdošanas. Ir svarīgi, lai jūsu organizācija ievērotu visu klientu piekrišanu un konfidencialitātes preferences.  

Dynamics 365 Customer Insights palīdz izpildīt klientu pieprasījumus, importējot un saglabājot viņu preferences kā daļu no vienotajiem klientu profiliem.

Ja piekrišanas dati tiek glabāti atsevišķi no jūsu klientu profiliem, [pievienojiet savus piekrišanas datus kā jaunu datu avots](#import-and-unify-consent-data). Datu avots, kas satur piekrišanas datus, tiek pievienots datu apvienošanas procesam. Veiksmīga piekrišanas datu un klientu profilu apvienošana noved pie vienotiem klientu profiliem, kas satur piekrišanas informāciju. Klientu profiliem, kuros jau ir piekrišanas informācija, dodieties tieši uz [sadaļu Piekrišanas datu](#use-consent-data) izmantošana.

## <a name="prerequisites"></a>Priekšnoteikumi

Lai piekrišanas datus apvienotu ar citiem klientu profiliem, jūsu avota datos ir jābūt pieejamai tālāk norādītajai informācijai.

- Alternatīvā atslēga kartēt piekrišanas informāciju uz customer insights lietotāju profiliem. Piemēram, e-pasta adrese vai tālruņa numurs.
- Piekrišanas vērtība, lai noteiktu klienta piekrišanas statusu.

Apsveriet iespēju pievienot šādu *neobligātu* informāciju:

- Primārā atslēga, lai atjauninātu piekrišanas statusu, ja klients pieprasa izmaiņas.
- Piekrišanas veids, ja ir vairāki veidi, kā apstrādāt klientu informāciju.
- Piekrišanas datums vai jebkāda cita veida dati, kas attiecas uz jūsu piekrišanas scenārijiem.

Vienkāršas piekrišanas datu bāzes ar vairākām piekrišanas opcijām tabulas piemērs:

|Piekrišanas ID (primārā atslēga)   |E-pasts (alternatīvā atslēga)  |Piekrišanas iespēja  |Piekrišanas vērtība  |
|---------|---------|---------|---------|
|1    |  holly@contoso.com       |  Biļetenu       |  Nepatiess       |
|2    |  holly@contoso.com       |  Produktu atjauninājumi       |  Patiess       |
|3    |  frank@contoso.com       |  Biļetenu       | Patiess        |
|4    |  frank@contoso.com       |  Produktu atjauninājumi       |  Nepatiess       |

## <a name="import-and-unify-consent-data"></a>Piekrišanas datu importēšana un apvienošana

Importējiet piekrišanas datus tāpat, kā jūs uzņemat citus datu avotus programmā Customer Insights. Papildinformāciju par atbalstītajiem datu avotiem un to importēšanu skatiet rakstā [Pārskats par datu avotiem](data-sources.md).

Papildinformāciju par datu avotu apvienošanu skatiet rakstā [Pārskats par](data-unification.md) datu apvienošanu.

## <a name="use-consent-data"></a>Piekrišanas datu izmantošana

Kad jūsu piekrišanas dati ir daļa no jūsu vienotajiem klientu profiliem, varat tos izmantot programmā Customer Insights. Piemēram, izveidojiet segmentu ar kārtulu, lai nodrošinātu, ka ievērojat klientu konfidencialitātes un datu aizsardzības preferences. Kārtulas, kas atbalsta piekrišanas preferences, tiek izmantotas, lai izslēgtu lietotājus no segmenta, kura pamatā ir profila atribūti. Pievienojiet kārtulu segmentam, kas izslēdz klientu profilus, kuri nesniedza piekrišanu sazināties.

Atsaucoties uz iepriekš minēto izlases tabulu, segmentā varētu būt šāds noteikums:`Consent option=Newsletter & Consent value=True`. Šīs konfigurācijas rezultātā tiek izveidots segments, kurā tiek ievērotas saziņas preferences, lai nosūtītu biļetenu.

Papildinformāciju par ēku segmentiem skatiet sadaļā [Segmentu](segment-builder.md) izveide.

Kad segments ir izveidots, varat izmantot vienu no daudzajām [eksportēšanas opcijām](export-destinations.md), lai segmentu izmantotu citās lietojumprogrammās.

## <a name="ensure-updated-consent-status"></a>Atjauninātas piekrišanas statusa nodrošināšana

Ir svarīgi, lai jūsu klientiem tiktu atjaunināts piekrišanas statuss. Programmā Customer Insights plānotā atsvaidzināšana vienmēr importē jūsu datu avotu jaunāko stāvokli. Pēc tam šī informācija tiek apstrādāta, apvienojot datus, un tās rezultātā tiek atjaunināti klientu profili. Pēc tam šie atjauninātie profili tiek izmantoti, lai atsvaidzinātu segmentus un pārliecinātos, ka strādājat ar visjaunāko informāciju.

Citiem vārdiem sakot, pārliecinieties, vai avota datos, kas tiek importēti programmā Customer Insights, vienmēr ir jaunākā informācija.

Papildinformāciju skatiet sadaļā [Segmentu](segments.md#refresh-segments) manuāla atsvaidzināšana vai [ieplānotas atsvaidzināšanas](schedule-refresh.md) konfigurēšana.

[!INCLUDE [footer-include](includes/footer-banner.md)]
