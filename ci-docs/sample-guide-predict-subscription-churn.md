---
title: Abonementa zudumu prognozes parauga ceļvedis
description: Izmantojiet šo parauga ceļvedi, lai izmēģinātu nestandarta abonementa zudumu prognozes modeli.
ms.date: 03/31/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-create-prediction
- customerInsights
ms.openlocfilehash: 5a8eeafecacef3d0bb4a798b698cf490423ca98d
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741420"
---
# <a name="subscription-churn-prediction-sample-guide"></a>Abonementa zudumu prognozes parauga ceļvedis

Mēs jums paskaidrosim, kā izbeigt parakstīšanās zudumu prognozi, izmantojot tālāk sniegto datu paraugu. 

## <a name="scenario"></a>Scenārijs

Contoso ir uzņēmums, kas ražo kvalitatīvu kafiju un kafijas automātus, ko viņi pārdod, izmantojot savu Contoso Coffee mājaslapu. Viņi nesen uzsāka abonēšanas uzņēmumu, lai viņu klienti regulāri saņemtu kafiju. Viņu mērķis ir izprast, kuri abonēšanas klienti tuvāko mēnešu laikā var atcelt savu abonementu. Zinot, kurš no saviem klientiem varētu **zust**, var palīdzēt ietaupīt mārketinga pasākumus, koncentrējoties uz to saglabāšanu.

## <a name="prerequisites"></a>Priekšnosacījumi

- Vismaz [Līdzautora atļaujas](permissions.md) Customer Insights.
- Ieteicams ieviest tālāk norādītos soļus [jaunā vidē](manage-environments.md).

## <a name="task-1---ingest-data"></a>1.uzdevums - Datu uzņemšana

Pārskatiet rakstus [par datu uzņemšanu](data-sources.md) un [datu avotu importēšanu, izmantojot Power Query savienotājus](connect-power-query.md). Tālāk sniegtajā informācijā tiek pieņemts, ka esat iepazinies ar datu uzņemšanu kopumā. 

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Uzņemt klientu datus no e-komercijas platformas

1. Izveidojiet datu avotu ar nosaukumu **e-komercija**, izvēlieties importēšanas opciju un atlasiet **Tekstu/CSV** savienotāju.

1. Ievadiet URL e-komercijas kontaktpersonām https://aka.ms/ciadclasscontacts.

1. Rediģējot datus, atlasiet **Pārveidot** un pēc tam **Izmantot pirmajā rindā kā galvenes**.

1. Atjauniniet tālāk uzskaitīto kolonnu datu tipu:

   - **DateOfBirth**: Datums
   - **CreatedOn**: Datums/Laiks/Josla

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Pārveidojiet dzimšanas datumu uz datumu.":::

1. Labās puses rūts laukā **Nosaukums** pārdēvējiet savu datu avotu no **Vaicājuma** uz **eCommerceContacts**

1. Saglabājiet datu avotu.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Klienta datu uzņemšana no lojalitātes shēmas

1. Izveidojiet datu avotu ar nosaukumu **LoyaltyScheme**, izvēlieties importēšanas opciju un atlasiet **Tekstu/CSV** savienotāju.

1. Ievadiet URL e-komercijas kontaktpersonām https://aka.ms/ciadclasscustomerloyalty.

1. Rediģējot datus, atlasiet **Pārveidot** un pēc tam **Izmantot pirmajā rindā kā galvenes**.

1. Atjauniniet tālāk uzskaitīto kolonnu datu tipu:

   - **DateOfBirth**: Datums
   - **RewardsPoints**: Vesels skaitlis
   - **CreatedOn**: Datums/Laiks

1. Labās puses rūts laukā **Nosaukums** pārdēvējiet savu datu avotu no **Vaicājuma** uz **loyCustomers**.

1. Saglabājiet datu avotu.

### <a name="ingest-subscription-information"></a>Abonenta informācijas uzņemšana

1. Izveidojiet datu avotu ar nosaukumu **SubscriptionHistory**, izvēlieties importēšanas opciju un atlasiet **Tekstu/CSV** savienotāju.

1. Ievadiet URL e-komercijas kontaktpersonām https://aka.ms/ciadchurnsubscriptionhistory.

1. Rediģējot datus, atlasiet **Pārveidot** un pēc tam **Izmantot pirmajā rindā kā galvenes**.

1. Atjauniniet tālāk uzskaitīto kolonnu datu tipu:

   - **SubscriptioID**: Vesels skaitlis
   - **SubscriptionAmount**: Valūta
   - **SubscriptionEndDate**: Datums/Laiks
   - **SubscriptionStartDate**: Datums/Laiks
   - **TransactionDate**: Datums/Laiks
   - **IsRecurring**: Patiess/Aplams
   - **Is_auto_renew**: Patiess/Aplams
   - **RecurringFrequencyInMonths**: Vesels skaitlis

1. Labās puses rūts laukā **Nosaukums** pārdēvējiet savu datu avotu no **Vaicājuma** uz **SubscriptionHistory**.

1. Saglabājiet datu avotu.

### <a name="ingest-customer-data-from-website-reviews"></a>Klientu datu uzņemšana no tīmekļa pārskatiem

1. Izveidojiet datu avotu ar nosaukumu **e-komercija**, izvēlieties importēšanas opciju un atlasiet **Tekstu/CSV** savienotāju.

1. Ievadiet URL e-komercijas kontaktpersonām https://aka.ms/ciadclasswebsite.

1. Rediģējot datus, atlasiet **Pārveidot** un pēc tam **Izmantot pirmajā rindā kā galvenes**.

1. Atjauniniet tālāk uzskaitīto kolonnu datu tipu:

   - **ReviewRating**: Vesels skaitlis
   - **ReviewDate**: Datums

1. Labās puses rūts laukā "Nosaukums" pārdēvējiet savu datu avotu no **Vaicājuma** uz **webReviews**.

## <a name="task-2---data-unification"></a>2.uzdevums — Datu apvienošana

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---configure-the-subscription-churn-prediction"></a>3.uzdevums — konfigurēt abonēšanas zudumu prognozi

Izmantojot vienoto klientu profilus, mēs tagad varam palaist abonēšanas zudumu prognozi. Detalizētas darbības skatiet [rakstā Abonēšanas prognoze](predict-subscription-churn.md). 

1. Atveriet **Informācija** > **Atklāt** un atlasiet, lai izmantotu **Klientu zudumu modeli**.

1. Atlasiet opciju **Abonēšana** un atlasiet **Sākt darbu**.

1. Nosauciet modeli **OOB Abonementu zudumu prognoze** un izvades entītiju **OOBSubscriptionChurnPrediction**.

1. Definējiet divus zuduma modeļa nosacījumus:

   * **Dienas kopš abonementa izbeigšanās**: **vismaz 60** dienas. Ja klients nav atjaunojis savu abonementu tik ilgi pēc abonementa beigām, viņš tiek uzskatīts par zaudētu. 

   * **Zuduma definīcija**: **vismaz 93** dienas. Modelis prognozē laika posmu, kurā klienti varētu zust. Jo tālākā nākotnē lūkosities, jo neprecīzāki būs rezultāti.

     :::image type="content" source="media/model-subs-levers.PNG" alt-text="Atlasiet modeļa sviras Prognozes logs un Zuduma definīcija.":::

1. Atlasiet **Pievienot nepieciešamos datus** un atlasiet **Pievienot datus** abonementu vēsturei.

1. Pievienojiet **Abonementi: SubscriptionHistory** entītiju un kartējiet laukus no e-komercijas uz atbilstošiem modelī vajadzīgajiem laukiem.

1. Savienojiet **Abonementi: SubscriptionHistory** entītiju ar **eCommerceContacts: e-komercijas**, nosauciet relācijas **eCommerceSubscription**.

   :::image type="content" source="media/model-subscription-join.PNG" alt-text="Pievienojieties e-komercijas entītijām.":::

1. Sadaļā Klientu darbības pievienojiet **webReviews : vietnes** entītiju un kartējiet laukus no webReviews uz modelī vajadzīgajiem atbilstošajiem laukiem. 
   - Primārā atslēga: ReviewId
   - Laikspiedols: ReviewDate
   - Notikums: ReviewRating

1. Konfigurējiet darbību vietņu recenzijām. Atlasiet darbību **Pārskats** un savienojiet **webReviews: vietnes** entītiju ar **eCommerceContacts: e-komercija**.

1. Lai iestatītu modeļa grafiku, atlasiet **Tālāk**.

   Modelis ir regulāri jāapmāca, lai apgūtu jaunus rakstus, kad tiek uzņemti jauni dati. Šajā piemērā atlasiet **Reizi mēnesī**.

1. Pēc visas detalizētās informācijas pārskatīšanas atlasiet **Saglabāt un palaist**.

## <a name="task-4---review-model-results-and-explanations"></a>4.uzdevums — pārskatīt modeļa rezultātus un paskaidrojumus

Ļaujiet modelim pabeigt datu apmācīšanu un skaitīšanu. Tagad jūs varat pārskatīt abonēšanas zudumu modeļa paskaidrojumus. Papildinformāciju skatiet rakstā [Prognozes statusa un rezultātu pārskatīšana](predict-subscription-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a>5.uzdevums — Izveidot augsta zudumu riska klientu segmentu

Palaižot ražošanas modeli, tiek izveidota jauna entītija, ko var redzēt vienumā **Dati** > **Entītijas**.   

Varat izveidot jaunu segmentu, par pamatu izmantojot modelī izveidotu entītiju.

1.  Ejiet uz **Segmenti**. Atlasiet vienumu **Jauns** un izvēlieties **Izveidot no** > **Informācija**. 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Izveidot segmentu ar modeļa izvadi.":::

1. Atlasiet **OOBSubscriptionChurnPrediction** galapunktu un definējiet segmentu: 
   - Lauks: ChurnScore
   - Operators: ir lielāks nekā
   - Vērtība: 0.6
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="Iestatiet abonementu zudumu segmentu.":::

Tagad jums ir segments, kas tiek dinamiski atjaunināts, kas identificē šā abonēšanas uzņēmuma augsta zudumu riska klientus.

Papildinformācijai skatiet [Segmentu izveide un pārvaldība](segments.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]