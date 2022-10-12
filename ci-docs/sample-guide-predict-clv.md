---
title: Debitora darbmūža prognozes (CLV) parauga rokasgrāmata
description: Izmantojiet šo parauga rokasgrāmatu, lai izmēģinātu klienta dzīves prognozes modelim.
ms.date: 09/15/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: tutorial
author: yashlundia
ms.author: yalundia
manager: shellyha
ms.openlocfilehash: fec43b279326daa17fb179181f5e310c99d48bb7
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609647"
---
# <a name="customer-lifetime-value-clv-prediction-sample-guide"></a>Debitora darbmūža prognozes (CLV) parauga rokasgrāmata

Šajā ceļvedī ir sniegts visaptverošs piemērs par klienta mūža vērtību (Customer Lifetime Value — CLV), prognoze programmā Customer Insights, izmantojot parauga datus. Mēs iesakām izmēģināt šo prognoze [jaunā vidē](manage-environments.md).

## <a name="scenario"></a>Situācija

Contoso ir uzņēmums, kas ražo augstas kvalitātes kafijas un kafijas automātus. Viņi pārdod produktus, izmantojot savu Contoso kafijas vietni. Uzņēmums vēlas saprast vērtību (ieņēmumus), ko viņu klienti var radīt nākamo 12 mēnešu laikā. Zinot savu klientu paredzamo vērtību nākamajos 12 mēnešos, viņi varēs virzīt savus mārketinga centienus uz augstvērtības klientiem.

## <a name="prerequisites"></a>Priekšnoteikumi

- Vismaz [Līdzdalībnieka atļaujas](permissions.md).

## <a name="task-1---ingest-data"></a>1.uzdevums - Datu uzņemšana

Pārskatiet rakstus [par datu uzņemšanu](data-sources.md) un [savienojuma izveidi ar Power Query datu avots](connect-power-query.md). Tālāk sniegtā informācija pieņem, ka esat iepazinies ar datu uzņemšanu kopumā.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Uzņemt klientu datus no e-komercijas platformas

1. Izveidojiet Power Query datu avots ar nosaukumu **e-komercija un** atlasiet **teksta/CSV savienotāju**.

1. Ievadiet URL e-komercijas kontaktpersonām https://aka.ms/ciadclasscontacts.

1. Rediģējot datus, atlasiet **Pārveidot un pēc tam** izmantot pirmo rindu kā **galvenes**.

1. Atjauniniet tālāk uzskaitīto kolonnu datu tipu:
   - **DateOfBirth**: Datums
   - **CreatedOn**: Datums/Laiks/Josla

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Pārveidojiet dzimšanas datumu uz datumu.":::

1. Labās **puses rūts laukā Nosaukums** pārdēvējiet savu datu avots par **e-komercijaskontaktiem**

1. **Saglabājiet** datu avotu.

### <a name="ingest-online-purchase-data"></a>Tiešsaistes pirkuma datu uzņemšana

1. Pievienojiet citas datu kopas tiem pašiem **e-komercijas** datu avotiem. Vēlreiz izvēlieties **Tekstu/CSV** savienotāju.

1. Ievadiet **Tiešsaistes pirkumu** datu URL https://aka.ms/ciadclassonline.

1. Rediģējot datus, atlasiet **Pārveidot un pēc tam** izmantot pirmo rindu kā **galvenes**.

1. Atjauniniet tālāk uzskaitīto kolonnu datu tipu:
   - **PurchasedOn**: Datums/Laiks
   - **TotalPrice**: Valūta

1. **Sānu rūts laukā Nosaukums** pārdēvējiet savu datu avots par **e-komercijas iepirkumiem**.

1. **Saglabājiet** datu avotu.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Klienta datu uzņemšana no lojalitātes shēmas

1. Izveidojiet datu avots ar nosaukumu **LoyaltyScheme** un atlasiet **teksta/CSV** savienotāju.

1. Ievadiet vietrādi URL lojalitātes klientiem https://aka.ms/ciadclasscustomerloyalty.

1. Rediģējot datus, atlasiet **Pārveidot un pēc tam** izmantot pirmo rindu kā **galvenes**.

1. Atjauniniet tālāk uzskaitīto kolonnu datu tipu:
   - **DateOfBirth**: Datums
   - **RewardsPoints**: Vesels skaitlis
   - **CreatedOn**: Datums/Laiks

1. Labās **puses rūts laukā Nosaukums** pārdēvējiet savu datu avots par **loyCustomers**.

1. **Saglabājiet** datu avotu.

### <a name="ingest-customer-data-from-website-reviews"></a>Klientu datu uzņemšana no tīmekļa pārskatiem

1. Izveidojiet datu avots ar nosaukumu **Tīmekļa vietne** un atlasiet **teksta/CSV** savienotāju.

1. Ievadiet vietņu atsauksmju https://aka.ms/CI-ILT/WebReviews vietrādi URL.

1. Rediģējot datus, atlasiet **Pārveidot un pēc tam** izmantot pirmo rindu kā **galvenes**.

1. Atjauniniet tālāk uzskaitīto kolonnu datu tipu:
   - **ReviewRating**: decimāldaļskaitlis
   - **ReviewDate**: Datums

1. Labās **puses rūts laukā Nosaukums** pārdēvējiet savu datu avots par **Atsauksmes**.

1. **Saglabājiet** datu avotu.

## <a name="task-2---data-unification"></a>2.uzdevums — Datu apvienošana

Pārskatiet rakstu [par datu apvienošanu](data-unification.md). Tālāk sniegtā informācija pieņem, ka esat iepazinies ar datu apvienošanu kopumā.

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---create-transaction-history-activity"></a>3. uzdevums — darījumu vēstures darbības izveide

Pārskatiet rakstu [par klientu darbībām](activities.md). Tālāk sniegtā informācija pieņem, ka esat iepazinies ar darbību izveidi kopumā.

1. Izveidojiet darbību, ko sauc par **e-komercijas iepirkumiem**, izmantojot *e-komercijas iepirkumu:e-komercijas* entītiju un tās primāro atslēgu **PurchaseId**.

1. Izveidojiet relāciju starp *e-komercijas iepirkumiem:e-komercija* un *e-komercijaskontakti:e-komercija* **Ar ContactID** kā ārējo atslēgu, lai savienotu abas entītijas.

1. Atlasiet **TotalPrice** priekš **EventActivity** un **PurchasedOn** for the **TimeStamp**.

1. Aktivitātes **tipam** atlasiet **SalesOrderLine** un semantiski kartējiet aktivitātes datus.

1. Palaidiet aktivitāti.

1. Pievienojiet citu darbību un kartējiet tās lauku nosaukumus atbilstošajos laukos:
   - **Darbības entītija**: Atsauksmes:Tīmekļa vietne
   - **Primārā atslēga**: ReviewId
   - **Laikspiedols**: ReviewDate
   - **Pasākuma aktivitāte**: ActivityTypeDisplay
   - **Papildu informācija**: ReviewRating
   - **Aktivitātes veids**: pārskats

1. Palaidiet aktivitāti.

## <a name="task-4---configure-customer-lifetime-value-prediction"></a>4. uzdevums - konfigurēt debitora mūža vērtību prognoze

Kad ir ieviesti vienotie klientu profili un izveidotā darbība, palaidiet klienta mūža vērtību (CLV) prognoze. Detalizētu informāciju par darbībām skatiet sadaļā [Klienta mūža vērtība prognoze](predict-customer-lifetime-value.md).

1. Dodieties uz **izlūkošanas** > **prognozēm**.

1. Cilnē Izveide elementā **Klienta mūža vērtība** atlasiet **Lietot modeli** **.**

1. Atlasiet **Sākt darbu**.

1. Nosauciet modeli **OOB eCommerce CLV prognoze** un izvades entītiju **OOBeCommerceCLVPrediction**.

1. Definējiet modeļa preferences:
   - **prognoze laika periods**: **12 mēneši vai 1 gads**, lai noteiktu, cik tālu nākotnē prognozēt CLV.
   - **Aktīvie klienti**: **ļaujiet modelim aprēķināt pirkšanas intervālu**, kas ir laika posms, kurā klientam ir jābūt vismaz vienam darījumam, lai to uzskatītu par aktīvu.
   - **Augstas vērtības klients**: manuāli definējiet augstvērtīgus klientus kā **30% no aktīvajiem klientiem**.

    :::image type="content" source="media/clv-model-preferences.png" alt-text="CLV modeļa vadītās pieredzes preferenču solis.":::

1. Atlasiet **Tālāk**.

1. Darbībā **Nepieciešamie dati** atlasiet vienumu **Pievienot datus**, lai nodrošinātu transakciju vēstures datus.

    :::image type="content" source="media/clv-model-required.png" alt-text="Pievienojiet nepieciešamos datus CLV modeļa vadītajā pieredzē.":::

1. Atlasiet **SalesOrderLine** un entītiju e-komercijas pirkumi un atlasiet **Tālāk**. Nepieciešamie dati tiek automātiski aizpildīti no darbības. Atlasiet **Saglabāt** un pēc tam **Tālāk**.

1. Veicot **papildu datu (neobligāto)** darbību, varat pievienot vairāk datu par klientu darbībām, lai iegūtu vairāk ieskatu par mijiedarbību ar klientiem. Šajā piemērā atlasiet **Pievienot datus** un pievienojiet tīmekļa recenzijas darbību.

1. Atlasiet **Tālāk**.

1. **Darbībā Datu atjauninājumi** modeļa grafikam atlasiet **Katru mēnesi**.

1. Atlasiet **Tālāk**.

1. Pēc visas detalizētās informācijas pārskatīšanas atlasiet **Saglabāt un palaist**.

## <a name="task-5---review-model-results-and-explanations"></a>5. uzdevums - modeļa rezultātu un skaidrojumu pārskatīšana

Ļaujiet modelim pabeigt datu apmācīšanu un skaitīšanu. Pārskatiet [CLV modeļa rezultātus un paskaidrojumus](predict-customer-lifetime-value.md#view-prediction-results).

## <a name="task-6---create-a-segment-of-high-value-customers"></a>6. uzdevums — izveidot augstas vērtības klientu segmentu

Izpildot modeli, tiek izveidota jauna entītija, kas tiek iekļauta sarakstā **Dati** > **Entītijas**. Varat izveidot jaunu klienta segmentu, pamatojoties uz modeļa izveidoto entītiju.

1. Rezultātu lapā atlasiet **Izveidot segmentu**.

1. Izveidojiet kārtulu, izmantojot entītiju **OOBeCommerceCLVPrediction**, un definējiet segmentu:
   - **Lauks**: CLVScore
   - **Operators**: lielāks par
   - **Vērtība**: 1500

1. Atlasiet **Saglabāt** un **palaist** segmentu.

Tagad jums ir segments, kas identificē klientus, kuri, pēc prognozēm, nākamajos 12 mēnešos veidos vairāk nekā $1500 lielus ieņēmumus. Ja ietverat vairāk datu, šis segments dinamiski tiek atjaunināts. Papildinformācijai skatiet [Segmentu izveide un pārvaldība](segments.md).

> [!TIP]
> Segmentu prognoze modelim var izveidot arī lapā Segmenti **,** atlasot **Jauns** un izvēloties **Izveidot no** > **informācijas**. Papildinformāciju skatiet sadaļā [Jauna segmenta izveide ar ātriem segmentiem](segment-quick.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
