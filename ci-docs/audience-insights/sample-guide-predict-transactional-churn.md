---
title: Transakciju zudumu prognozes parauga ceļvedis
description: Izmantojiet šo parauga ceļvedi, lai izmēģinātu nestandarta transakciju zudumu prognozes modeli.
ms.date: 11/19/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: 72f3bd1f32b813fef04dc14618331e3d707b5052
ms.sourcegitcommit: dab2cbf818fafc9436e685376df94c5e44e4b144
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 07/13/2021
ms.locfileid: "6556270"
---
# <a name="transactional-churn-prediction-preview-sample-guide"></a>Transakciju zudumu parauga prognozes parauga ceļvedis (priekšskatījums)

Mēs jums paskaidrosim, kā izbeigt transakciju zudumu prognozi programmā Customer Insights, izmantojot tālāk sniegtos datus. Visi šajā ceļvedī izmantotie dati nav reāli klientu dati; tie ietilpst Contoso datu kopas *demonstrācijas* vidē, kas atrodas jūsu Customer Insights abonementā.

## <a name="scenario"></a>Scenārijs

Contoso ir uzņēmums, kas ražo augstas kvalitātes kafijas un kafijas automātus, kurus viņi pārdod, izmantojot savu Contoso Coffee vietni. To mērķis ir noskaidrot, kuri klienti, kas parasti iegādājas viņu produktus, pārtrauks aktivitāti nākamajās 60 dienās. Zinot, kurš no saviem klientiem varētu **zust**, var palīdzēt ietaupīt mārketinga pasākumus, koncentrējoties uz to saglabāšanu.

## <a name="prerequisites"></a>Priekšnosacījumi

- Vismaz [Līdzautora atļaujas](permissions.md) Customer Insights.
- Ieteicams ieviest tālāk norādītos soļus [jaunā vidē](manage-environments.md).

## <a name="task-1---ingest-data"></a>1.uzdevums - Datu uzņemšana

Pārskatiet rakstus [par datu uzņemšanu](data-sources.md) un [datu avotu importēšanu, izmantojot](connect-power-query.md) tieši Power Query savienotājus. Tālāk sniegtajā informācijā tiek pieņemts, ka esat iepazinies ar datu uzņemšanu kopumā. 

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Uzņemt klientu datus no e-komercijas platformas

1. Izveidojiet datu avotu ar nosaukumu **e-komercija**, izvēlieties importēšanas opciju un atlasiet **Tekstu/CSV** savienotāju.

1. Ievadiet URL e-komercijas kontaktpersonām https://aka.ms/ciadclasscontacts.

1. Rediģējot datus, atlasiet **Pārveidot** un pēc tam **Izmantot pirmajā rindā kā galvenes**.

1. Atjauniniet tālāk uzskaitīto kolonnu datu tipu:

   - **DateOfBirth**: Datums
   - **CreatedOn**: Datums/Laiks/Josla

   [!div class="mx-imgBorder"]
   ![Pārveidot DoB par Datumu.](media/ecommerce-dob-date.PNG "Pārveido dzimšanas datumu uz datumu")

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

Pēc datu uzņemšanas mēs tagad sākam **Kartēt, saskaņot un sapludināt** procesu, lai izveidotu vienotu klientu profilu. Papildinformāciju skatiet tēmā [Datu apvienošana](data-unification.md).

### <a name="map"></a>Kartēt

1. Pēc datu uzņemšanas kartējiet kontaktpersonas no e-komercijas un lojalitātes datiem līdz vispārējiem datu tipiem. Ejiet uz **Dati** > **Apvienot** > **Kartēt**.

1. Atlasiet entītijas, kas pārstāv klienta profilu — **eCommerceContacts** un **loyCustomers**. 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="apvienot e-komercijas un lojalitātes datu avotus.":::

1. Atlasiet **ContactId** kā primāro atslēgu **eCommerceContacts** un **LoyaltyID** kā **loyCustomers** primāro atslēgu.

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="Apvienot LoyaltyId kā primāro atslēgu.":::

### <a name="match"></a>Saskaņot

1. Dodieties uz cilni **Saskaņot** un atlasiet **Iestatīt secību**.

1. Nolaižamajā sarakstā **Primārs** izvēlieties **eCommerceContacts : eCommerce** kā primāro avotu un iekļaujiet visus ierakstus.

1. Nolaižamajā sarakstā **2. entītija** izvēlieties **loyCustomers :LoyaltyScheme** un iekļaujiet visus ierakstus.

   :::image type="content" source="media/unify-match-order.PNG" alt-text="Apvienot e-komercijas un lojalitātes atbilstības.":::

1. Atlasiet **Jaunas kārtulas izveide**

1. Pievienojiet pirmo nosacījumu, izmantojot FullName.

   * Entītijai eCommerceContacts atlasiet **FullName** nolaižamajā sarakstā.
   * Entītijai loyCustomers atlasiet **FullName** nolaižamajā sarakstā.
   * Atlasiet opciju **Normalizēt** nolaižamo sarakstu un izvēlieties **tipu (tālrunis, nosaukums, adrese,...)**.
   * Iestatiet **Precizitātes līmeni**: **Pamatinformācija** un **Vērtību**: **Augsts**.

1. Ievadiet jaunās kārtulas nosaukumu **FullName, e-pasts**.

   * Pievienojiet e-pasta adresei otru nosacījumu, atlasot **Pievienot nosacījumu**
   * Entītijai eCommerceContacts nolaižamajā sarakstā izvēlieties **E-pasts**.
   * Entītijai loyCustomers nolaižamajā sarakstā izvēlieties **E-pasts**. 
   * Atstājiet normalizāciju tukšu. 
   * Iestatiet **Precizitātes līmeni**: **Pamatinformācija** un **Vērtību**: **Augsts**.

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="Apvienot nosaukuma un e-pasta ziņojuma saskaņošanas kārtulu.":::

7. Atlasiet vienumu **Saglabāt** un **Palaist**.

### <a name="merge"></a>Sapludināšana

1. Ejiet uz cilni **Sapludināt**.

1. **ContactId** attiecībā uz **loyCustomers** entītiju mainiet parādāmo nosaukumu uz **ContactIdLOYALTY**, lai atšķirtu to no citiem uzņemtajiem ID.

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="pārdēvējiet contactid no lojalitātes ID.":::

1. Atlasiet **Saglabāt** un **Palaist**, lai sāktu sapludināšanas procesu.



## <a name="task-3---configure-transaction-churn-prediction"></a>3.uzdevums — konfigurēt transakciju zudumu prognozi

Izmantojot vienoto klientu profilus, mēs tagad varam palaist abonēšanas zudumu prognozi. Detalizētas darbības skatiet rakstu [Abonementa zudumu prognoze (priekšskatījums)](predict-subscription-churn.md). 

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


[!INCLUDE[footer-include](../includes/footer-banner.md)]