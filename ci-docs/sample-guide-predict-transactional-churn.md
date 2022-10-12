---
title: Transakciju zudumu prognozes parauga ceļvedis
description: Izmantojiet šo parauga ceļvedi, lai izmēģinātu nestandarta transakciju zudumu prognozes modeli.
ms.date: 09/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0ccc32b6e5e96adf6f2fa8c6d52960a07d1513f3
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609693"
---
# <a name="transactional-churn-prediction-sample-guide"></a>Transakciju zudumu prognozes parauga ceļvedis

Šajā ceļvedī jums tiks izskaidrots visaptverošs piemērs par transakciju zuduma prognoze, izmantojot datu paraugus. Mēs iesakām izmēģināt šo prognoze [jaunā vidē](manage-environments.md).

## <a name="scenario"></a>Situācija

Contoso ir uzņēmums, kas ražo augstas kvalitātes kafijas un kafijas automātus. Viņi pārdod produktus, izmantojot savu Contoso kafijas vietni. To mērķis ir noskaidrot, kuri klienti, kas parasti iegādājas viņu produktus, pārtrauks aktivitāti nākamajās 60 dienās. Zinot, kurš no saviem klientiem varētu **zust**, var palīdzēt ietaupīt mārketinga pasākumus, koncentrējoties uz to saglabāšanu.

## <a name="prerequisites"></a>Priekšnoteikumi

- Vismaz [Līdzdalībnieka atļaujas](permissions.md).

## <a name="task-1---ingest-data"></a>1.uzdevums - Datu uzņemšana

Pārskatiet rakstus [par datu uzņemšanu](data-sources.md) un [savienojuma izveidi ar Power Query datu avots](connect-power-query.md). Tālāk sniegtā informācija pieņem, ka esat iepazinies ar datu uzņemšanu kopumā.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Uzņemt klientu datus no e-komercijas platformas

1. Izveidojiet datu avots ar nosaukumu **e-komercija** un atlasiet **teksta/CSV** savienotāju.

1. Ievadiet URL e-komercijas kontaktpersonām https://aka.ms/ciadclasscontacts.

1. Rediģējot datus, atlasiet **Pārveidot un pēc tam** izmantot pirmo rindu kā **galvenes**.

1. Atjauniniet tālāk uzskaitīto kolonnu datu tipu:

   - **DateOfBirth**: Datums
   - **CreatedOn**: Datums/Laiks/Josla

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Pārveidot DoB par Datumu.":::

1. Labās **puses rūts laukā Nosaukums** pārdēvējiet savu datu avots par **e-komercijaskontaktiem**

1. Saglabājiet datu avotu.

### <a name="ingest-online-purchase-data"></a>Tiešsaistes pirkuma datu uzņemšana

1. Pievienojiet citas datu kopas tiem pašiem **e-komercijas** datu avotiem. Vēlreiz izvēlieties **Tekstu/CSV** savienotāju.

1. Ievadiet tiešsaistes pirkumu datu https://aka.ms/ciadclassonline vietrādi URL.

1. Rediģējot datus, atlasiet **Pārveidot un pēc tam** izmantot pirmo rindu kā **galvenes**.

1. Atjauniniet tālāk uzskaitīto kolonnu datu tipu:

   - **PurchasedOn**: Datums/Laiks
   - **TotalPrice**: Valūta

1. Labās **puses rūts laukā Nosaukums** pārdēvējiet savu datu avots par **e-komercijas iepirkumiem**.

1. Saglabājiet datu avotu.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Klienta datu uzņemšana no lojalitātes shēmas

1. Izveidojiet datu avots ar nosaukumu **LoyaltyScheme** un atlasiet **teksta/CSV** savienotāju.

1. Ievadiet URL e-komercijas kontaktpersonām https://aka.ms/ciadclasscustomerloyalty.

1. Rediģējot datus, atlasiet **Pārveidot un pēc tam** izmantot pirmo rindu kā **galvenes**.

1. Atjauniniet tālāk uzskaitīto kolonnu datu tipu:

   - **DateOfBirth**: Datums
   - **RewardsPoints**: Vesels skaitlis
   - **CreatedOn**: Datums/Laiks

1. Labās **puses rūts laukā Nosaukums** pārdēvējiet savu datu avots par **loyCustomers**.

1. Saglabājiet datu avotu.

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

## <a name="task-4---configure-transaction-churn-prediction"></a>4. uzdevums - konfigurējiet transakciju prognoze

Kad ir ieviesti un tiek veikti vienoti klientu profili, palaidiet transakciju prognoze.

1. Dodieties uz **izlūkošanas** > **prognozēm**.

1. **Cilnē Izveide** atlasiet **Izmantot modeli** **klienta zuduma modelī**.

1. Atlasiet **Transakcijas**, lai noteiktu zuduma veidu, un pēc tam **sākt darbu**.

1. Nosauciet modeli **OOB Abonementu zudumu prognoze** un izvades entītiju **OOBSubscriptionChurnPrediction**.

1. Atlasiet **Tālāk**.

1. Definējiet modeļa preferences:

   - **prognoze logs**: **60** dienas, lai definētu, cik tālu nākotnē mēs vēlamies paredzēt klientu aizplūšanu.

   - **Zuduma definīcija**: **60** dienas, lai norādītu ilgumu bez pirkuma, pēc kura klients tiek uzskatīts par sačakarētu.

     :::image type="content" source="media/model-levers.PNG" alt-text="Atlasiet modeļa preferences prognoze Logu un Zuduma definīciju.":::

1. Atlasiet **Tālāk**.

1. Atlasiet **Pirkuma vēsturi (obligāti)** un atlasiet **Pievienot datus** pirkumu vēsturei.

1. Atlasiet **SalesOrderLine** un entītiju e-komercijas pirkumi un atlasiet **Tālāk**. Nepieciešamie dati tiek automātiski aizpildīti no darbības. Atlasiet **Saglabāt** un pēc tam **Tālāk**.

   :::image type="content" source="media/model-purchase-join.PNG" alt-text="Pievienojieties e-komercijas entītijām.":::

1. Izlaidiet **darbību Papildu dati (neobligāti).**

1. **Darbībā Datu atjauninājumi** modeļa grafikam atlasiet **Katru mēnesi**.

1. Pēc visas detalizētās informācijas pārskatīšanas atlasiet **Saglabāt un palaist**.

## <a name="task-5---review-model-results-and-explanations"></a>5. uzdevums - modeļa rezultātu un skaidrojumu pārskatīšana

Ļaujiet modelim pabeigt datu apmācīšanu un skaitīšanu. Pārskatiet zuduma modeļa skaidrojumus. Papildinformāciju skatiet sadaļā [prognoze rezultātu](predict-transactional-churn.md#view-prediction-results) skatīšana.

## <a name="task-6---create-a-segment-of-high-churn-risk-customers"></a>6. uzdevums - Izveidot augsta zuduma riska klientu segmentu

Palaižot ražošanas modeli, tiek izveidota jauna entītija, kas ir norādīta sadaļā **Datu** > **elementi**. Varat izveidot jaunu segmentu, par pamatu izmantojot modelī izveidotu entītiju.

1. Rezultātu lapā atlasiet **Izveidot segmentu**.

1. Izveidojiet kārtulu, **izmantojot entītiju OOBeCommerceChurnPrediction**, un definējiet segmentu:
   - **Lauks**: ChurnScore
   - **Operators**: lielāks par
   - **Vērtība**: 0,6

1. Atlasiet **Saglabāt** un **palaist** segmentu.

Tagad jums ir segments, kas ir dinamiski atjaunināts un kas identificē augsta zuduma riska klientus. Papildinformācijai skatiet [Segmentu izveide un pārvaldība](segments.md).

> [!TIP]
> Segmentu prognoze modelim var izveidot arī lapā Segmenti **,** atlasot **Jauns** un izvēloties **Izveidot no** > **informācijas**. Papildinformāciju skatiet sadaļā [Jauna segmenta izveide ar ātriem segmentiem](segment-quick.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
