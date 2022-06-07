---
title: Transakciju zudumu prognozes parauga ceļvedis
description: Izmantojiet šo parauga ceļvedi, lai izmēģinātu nestandarta transakciju zudumu prognozes modeli.
ms.date: 05/11/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 3edbf2a471313379c28db874d7f19c3265a23299
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741328"
---
# <a name="transactional-churn-prediction-sample-guide"></a>Transakciju zudumu prognozes parauga ceļvedis

Mēs jums paskaidrosim, kā izbeigt transakciju zudumu prognozi programmā Customer Insights, izmantojot tālāk sniegtos datus. Visi šajā rokasgrāmatā izmantotie dati nav īsti klientu dati, un tie ir daļa no Contoso datu kopas, kas ir atrodama vidē *Demo* jūsu Customer Insights abonementā.

## <a name="scenario"></a>Scenārijs

Contoso ir uzņēmums, kas ražo kvalitatīvu kafiju un kafijas automātus, ko viņi pārdod, izmantojot savu Contoso Coffee mājaslapu. To mērķis ir noskaidrot, kuri klienti, kas parasti iegādājas viņu produktus, pārtrauks aktivitāti nākamajās 60 dienās. Zinot, kurš no saviem klientiem varētu **zust**, var palīdzēt ietaupīt mārketinga pasākumus, koncentrējoties uz to saglabāšanu.

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

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Pārveidot DoB par Datumu.":::

1. Labās puses rūts laukā **Nosaukums** pārdēvējiet savu datu avotu no **Vaicājuma** uz **eCommerceContacts**

1. Saglabājiet datu avotu.

### <a name="ingest-online-purchase-data"></a>Tiešsaistes pirkuma datu uzņemšana

1. Pievienojiet citas datu kopas tiem pašiem **e-komercijas** datu avotiem. Vēlreiz izvēlieties **Tekstu/CSV** savienotāju.

1. Ievadiet **Tiešsaistes pirkumu** datu URL https://aka.ms/ciadclassonline.

1. Rediģējot datus, atlasiet **Pārveidot** un pēc tam **Izmantot pirmajā rindā kā galvenes**.

1. Atjauniniet tālāk uzskaitīto kolonnu datu tipu:

   - **PurchasedOn**: Datums/Laiks
   - **TotalPrice**: Valūta
   
1. Labās puses rūts laukā **Nosaukums** pārdēvējiet savu datu avotu no **Vaicājuma** uz **eCommercePurchases**.

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

## <a name="task-2---data-unification"></a>2.uzdevums — Datu apvienošana

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---configure-transaction-churn-prediction"></a>3.uzdevums — konfigurēt transakciju zudumu prognozi

Ja ir ieviesti vienotie klientu profili, mēs tagad varam palaist transakcijas prognoze. Detalizētus soļus skatiet rakstā Transakcijas [čurkste prognoze](predict-transactional-churn.md). 

1. Atveriet **Informācija** > **Atklāt** un atlasiet, lai izmantotu **Klientu zudumu modeli**.

1. Atlasiet opciju **Abonēšana** un atlasiet **Sākt darbu**.

1. Nosauciet modeli **OOB Abonementu zudumu prognoze** un izvades entītiju **OOBSubscriptionChurnPrediction**.

1. Definējiet divus zuduma modeļa nosacījumus:

   * **Prognozes logs**: **vismaz 60** dienas. Šis iestatījums nosaka, cik tālā nākotnē mēs vēlamies prognozēt klientu zudumu.

   * **Zuduma definīcija**: **vismaz 60** dienas. Ilgums bez pirkuma, pēc kura klients tiek uzskatīts par zudušu.

     :::image type="content" source="media/model-levers.PNG" alt-text="Atlasiet modeļa sviras Prognozes logs un Zuduma definīcija.":::

1. Atlasiet **Pirkuma vēsturi (obligāti)** un atlasiet **Pievienot datus** pirkumu vēsturei.

1. Pievienojiet **eCommercePurchases : e-komercija** entītiju un kartējiet laukus no e-komercijas uz atbilstošiem modelī vajadzīgajiem laukiem.

1. Apvienojiet **eCommercePurchases: e-komercijas** entītiju ar **ECommerceContacts: e-komerciju**.

   :::image type="content" source="media/model-purchase-join.PNG" alt-text="Pievienojieties e-komercijas entītijām.":::

1. Lai iestatītu modeļa grafiku, atlasiet **Tālāk**.

   Modelis ir regulāri jāapmāca, lai apgūtu jaunus rakstus, kad tiek uzņemti jauni dati. Šajā piemērā atlasiet **Reizi mēnesī**.

1. Pēc visas detalizētās informācijas pārskatīšanas atlasiet **Saglabāt un palaist**.

## <a name="task-4---review-model-results-and-explanations"></a>4.uzdevums — pārskatīt modeļa rezultātus un paskaidrojumus

Ļaujiet modelim pabeigt datu apmācīšanu un skaitīšanu. Tagad varat pārskatīt čurkstes modeļa skaidrojumus. Papildinformāciju skatiet rakstā [Prognozes statusa un rezultātu pārskatīšana](predict-transactional-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a>5.uzdevums — Izveidot augsta zudumu riska klientu segmentu

Palaižot ražošanas modeli, tiek izveidota jauna entītija, ko var redzēt vienumā **Dati** > **Entītijas**.   

Varat izveidot jaunu segmentu, par pamatu izmantojot modelī izveidotu entītiju.

1.  Ejiet uz **Segmenti**. Atlasiet vienumu **Jauns** un izvēlieties **Izveidot no** > **Informācija**. 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Izveidot segmentu ar modeļa izvadi.":::

1. **Atlasiet OOBeCommerceChurnPrediction** galapunktu un definējiet segmentu: 
   - Lauks: ChurnScore
   - Operators: ir lielāks nekā
   - Vērtība: 0.6

Tagad jums ir segments, kas ir dinamiski atjaunināts un kas identificē klientus ar augstu čurkstes risku.

Papildinformācijai skatiet [Segmentu izveide un pārvaldība](segments.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]