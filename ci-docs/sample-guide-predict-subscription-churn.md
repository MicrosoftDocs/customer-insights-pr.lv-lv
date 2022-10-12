---
title: Abonementa zudumu prognozes parauga ceļvedis
description: Izmantojiet šo parauga ceļvedi, lai izmēģinātu nestandarta abonementa zudumu prognozes modeli.
ms.date: 09/19/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-create-prediction
- customerInsights
ms.openlocfilehash: 7e754be9a2cb9450949c6b3667bbd37aa39cf0bf
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610015"
---
# <a name="subscription-churn-prediction-sample-guide"></a>Abonementa zudumu prognozes parauga ceļvedis

Šajā ceļvedī jums tiks izskaidrots pilnīgs piemērs par abonēšanas zuduma prognoze, izmantojot datu paraugus. Mēs iesakām izmēģināt šo prognoze [jaunā vidē](manage-environments.md).

## <a name="scenario"></a>Situācija

Contoso ir uzņēmums, kas ražo augstas kvalitātes kafijas un kafijas automātus. Viņi pārdod produktus, izmantojot savu Contoso kafijas vietni. Viņi nesen uzsāka abonēšanas uzņēmumu, lai viņu klienti regulāri saņemtu kafiju. Viņu mērķis ir saprast, kuri abonētie klienti tuvāko mēnešu laikā varētu atcelt savu abonementu. Zinot, kurš no viņu klientiem **, visticamāk, čurās**, var palīdzēt viņiem ietaupīt mārketinga pasākumus, koncentrējoties uz to saglabāšanu.

## <a name="prerequisites"></a>Priekšnoteikumi

- Vismaz [Līdzautora atļaujas](permissions.md) Customer Insights.

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

1. Saglabājiet datu avotu.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Klienta datu uzņemšana no lojalitātes shēmas

1. Izveidojiet datu avots ar nosaukumu **LoyaltyScheme** un atlasiet **teksta/CSV** savienotāju.

1. Ievadiet vietrādi URL lojalitātes klientiem https://aka.ms/ciadclasscustomerloyalty.

1. Rediģējot datus, atlasiet **Pārveidot un pēc tam** izmantot pirmo rindu kā **galvenes**.

1. Atjauniniet tālāk uzskaitīto kolonnu datu tipu:
   - **DateOfBirth**: Datums
   - **RewardsPoints**: Vesels skaitlis
   - **CreatedOn**: Datums/Laiks

1. Labās **puses rūts laukā Nosaukums** pārdēvējiet savu datu avots par **loyCustomers**.

1. Saglabājiet datu avotu.

### <a name="ingest-subscription-information"></a>Abonenta informācijas uzņemšana

1. Izveidojiet datu avots ar nosaukumu **SubscriptionHistory** un atlasiet **teksta/CSV** savienotāju.

1. Ievadiet abonementu vietrādi URL https://aka.ms/ciadchurnsubscriptionhistory.

1. Rediģējot datus, atlasiet **Pārveidot un pēc tam** izmantot pirmo rindu kā **galvenes**.

1. Atjauniniet tālāk uzskaitīto kolonnu datu tipu:
   - **SubscriptioID**: Vesels skaitlis
   - **SubscriptionAmount**: Valūta
   - **SubscriptionEndDate**: Datums/Laiks
   - **SubscriptionStartDate**: Datums/Laiks
   - **TransactionDate**: Datums/Laiks
   - **IsRecurring**: Patiess/Aplams
   - **Is_auto_renew**: Patiess/Aplams
   - **RecurringFrequencyInMonths**: Vesels skaitlis

1. Labās **puses rūts laukā Nosaukums** pārdēvējiet savu datu avots par **SubscriptionHistory**.

1. Saglabājiet datu avotu.

### <a name="ingest-customer-data-from-website-reviews"></a>Klientu datu uzņemšana no tīmekļa pārskatiem

1. Izveidojiet datu avots ar nosaukumu **Tīmekļa vietne** un atlasiet **teksta/CSV** savienotāju.

1. Ievadiet vietņu atsauksmju https://aka.ms/ciadclasswebsite vietrādi URL.

1. Rediģējot datus, atlasiet **Pārveidot un pēc tam** izmantot pirmo rindu kā **galvenes**.

1. Atjauniniet tālāk uzskaitīto kolonnu datu tipu:
   - **ReviewRating**: Vesels skaitlis
   - **ReviewDate**: Datums

1. Labās **puses rūts laukā Nosaukums** pārdēvējiet savu datu avots par **webReviews**.

## <a name="task-2---data-unification"></a>2.uzdevums — Datu apvienošana

Pārskatiet rakstu [par datu apvienošanu](data-unification.md). Tālāk sniegtā informācija pieņem, ka esat iepazinies ar datu apvienošanu kopumā.

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---create-transaction-history-activity"></a>3. uzdevums — darījumu vēstures darbības izveide

Pārskatiet rakstu [par klientu darbībām](activities.md). Tālāk sniegtā informācija pieņem, ka esat iepazinies ar darbību izveidi kopumā.

1. Izveidojiet darbību ar nosaukumu **SubscriptionHistory** ar abonementa *entītiju* un tās primāro atslēgu **CustomerId**.

1. Izveidojiet relāciju starp *SubscriptionHistory:Subscription* un *e-komercijaskontaktiem:e-komercija* ar **CustomerID** kā ārējo atslēgu, lai savienotu abas entītijas.

1. Atlasiet **SubscriptionType** for the **EventActivity** un **SubscriptionEndDate** for the **TimeStamp**.

1. Atlasiet **Darbības veida** abonements **un** semantiski kartējiet aktivitātes datus.

1. Palaidiet aktivitāti.

1. Pievienojiet citu darbību un kartējiet tās lauku nosaukumus atbilstošajos laukos:
   - Klienta darbības entītija: Reviews:Website
   - Primārā atslēga: Website.Reviews.ReviewId
   - Laikspiedols: Website.Reviews.ReviewDate
   - Notikums (darbības nosaukums): Website.Reviews.ActivityTypeDisplay
   - Detalizēti (summa vai vērtība): Website.Reviews.ReviewRating

1. Palaidiet aktivitāti.

## <a name="task-4---configure-the-subscription-churn-prediction"></a>4. uzdevums - konfigurējiet abonēšanas prognoze

Kad ir ieviesti vienoti klientu profili un izveidota darbība, palaidiet abonēšanas prognoze. Detalizētas darbības skatiet sadaļā [Abonēšanas zuduma prognoze](predict-subscription-churn.md).

1. Dodieties uz **izlūkošanas** > **prognozēm**.

1. **Cilnē Izveide** atlasiet **Izmantot modeli** elementā **Customer churn modelis**.

1. Atlasiet **Abonēšana**, lai noteiktu zuduma veidu, un pēc tam **sāciet darbu**.

1. Nosauciet modeli **OOB Abonementu zudumu prognoze** un izvades entītiju **OOBSubscriptionChurnPrediction**.

1. Definējiet modeļa preferences:
   - **Dienas kopš abonēšanas beigām**: **60** dienas, lai norādītu, ka klients tiek uzskatīts par aizturētu, ja viņš neatjauno abonementu šajā periodā pēc abonementa beigām.
   - **Dienas, lai izpētītu nākotni, lai prognozētu zudumu**: **93** dienas, kas ir ilgums, cik ilgi modelis paredz, kuri klienti varētu čurāt. Jo tālākā nākotnē lūkosities, jo neprecīzāki būs rezultāti.

   :::image type="content" source="media/model-subs-levers.PNG" alt-text="Atlasiet modeļa preferences un zuduma definīciju.":::

1. Atlasiet **Tālāk**.

1. **Darbībā Obligātie dati** atlasiet **Pievienot datus**, lai nodrošinātu abonementu vēsturi.

1. Atlasiet **Abonements** un entītiju SubscriptionHistory un atlasiet **Tālāk**. Nepieciešamie dati tiek automātiski aizpildīti no darbības. Atlasiet **Saglabāt**.

1. Sadaļā Klientu darbības atlasiet **Pievienot datus**.

1. Šajā piemērā pievienojiet tīmekļa pārskatīšanas darbību.

1. Atlasiet **Tālāk**.

1. **Darbībā Datu atjauninājumi** modeļa grafikam atlasiet **Katru mēnesi**.

1. Pēc visas detalizētās informācijas pārskatīšanas atlasiet **Saglabāt un palaist**.

## <a name="task-5---review-model-results-and-explanations"></a>5. uzdevums - modeļa rezultātu un skaidrojumu pārskatīšana

Ļaujiet modelim pabeigt datu apmācīšanu un skaitīšanu. Pārskatiet abonēšanas zuduma modeļa skaidrojumus. Papildinformāciju skatiet sadaļā [prognoze rezultātu](predict-subscription-churn.md#view-prediction-results) skatīšana.

## <a name="task-6---create-a-segment-of-high-churn-risk-customers"></a>6. uzdevums - Izveidot augsta zuduma riska klientu segmentu

Izpildot modeli, tiek izveidota jauna entītija, kas tiek iekļauta sarakstā **Dati** > **Entītijas**. Varat izveidot jaunu segmentu, par pamatu izmantojot modelī izveidotu entītiju.

1. Rezultātu lapā atlasiet **Izveidot segmentu**.

1. Izveidojiet kārtulu, **izmantojot entītiju OOBSubscriptionChurnPrediction**, un definējiet segmentu:
   - **Lauks**: ChurnScore
   - **Operators**: lielāks par
   - **Vērtība**: 0,6

1. Atlasiet **Saglabāt** un **palaist** segmentu.

Tagad jums ir segments, kas tiek dinamiski atjaunināts, kas identificē šā abonēšanas uzņēmuma augsta zudumu riska klientus. Papildinformācijai skatiet [Segmentu izveide un pārvaldība](segments.md).

> [!TIP]
> Segmentu prognoze modelim var izveidot arī lapā Segmenti **,** atlasot **Jauns** un izvēloties **Izveidot no** > **informācijas**. Papildinformāciju skatiet sadaļā [Jauna segmenta izveide ar ātriem segmentiem](segment-quick.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
