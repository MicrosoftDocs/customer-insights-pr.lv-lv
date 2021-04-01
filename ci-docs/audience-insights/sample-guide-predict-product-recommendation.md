---
title: Produktu ieteikumu prognozes rokasgrāmatas paraugs
description: Izmantojiet šo parauga ceļvedi, lai izmēģinātu nestandarta produktu ieteikumu prognozes modeli.
ms.date: 02/10/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: 20072d14b160e54f5ad044adc1de6c079bf790e4
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595282"
---
# <a name="product-recommendation-prediction-preview-sample-guide"></a>Produktu ieteikumu prognozes (priekšskatījums) rokasgrāmatas paraugs

Mēs paskaidrosim, kā izbeigt produktu ieteikumu prognozi, izmantojot tālāk sniegto datu paraugu.

## <a name="scenario"></a>Scenārijs

Contoso ir uzņēmums, kas ražo kvalitatīvu kafiju un kafijas automātus, ko viņi pārdod, izmantojot savu Contoso Coffee mājaslapu. Šo mērķis ir saprast, kādus produktus viņiem ieteikt periodiskajiem klientiem. Zinot, kādi klienti **varētu nopirkt**, var palīdzēt ietaupīt mārketinga pasākumus, koncentrējoties uz konkrētiem produktiem.

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

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Pārveidojiet dzimšanas datumu uz datumu.":::

5. Labās puses rūts laukā "Nosaukums" pārdēvējiet savu datu avotu no **Vaicājuma** uz **eCommerceContacts**

6. **Saglabājiet** datu avotu.

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

2. Atlasiet entītijas, kas pārstāv klienta profilu — **eCommerceContacts** un **loyCustomers**.

   ![apvienot e-komercijas un lojalitātes datu avotus.](media/unify-ecommerce-loyalty.png)

3. Atlasiet **ContactId** kā primāro atslēgu **eCommerceContacts** un **LoyaltyID** kā **loyCustomers** primāro atslēgu.

   ![Apvienot LoyaltyId kā primāro atslēgu.](media/unify-loyaltyid.png)

### <a name="match"></a>Saskaņot

1. Dodieties uz cilni **Saskaņot** un atlasiet **Iestatīt secību**.

2. **Primārajā** nolaižamajā sarakstā izvēlieties **eCommerceContacts : e-komercijas** kā primāro avotu un iekļaujiet visus ierakstus.

3. Nolaižamajā sarakstā **2.entītija** izvēlieties **loyCustomers: LoyaltyScheme** un iekļaujiet visus ierakstus.

   ![Apvienot e-komercijas un lojalitātes atbilstības.](media/unify-match-order.png)

4. Atlasiet **Jaunas kārtulas izveide**

5. Pievienojiet pirmo nosacījumu, izmantojot FullName.

   - Nolaižamajā sarakstā atlasiet **FullName** eCommerceContacts.
   - Nolaižamajā sarakstā atlasiet **FullName** loyCustomers.
   - Atlasiet opciju **Normalizēt** nolaižamo sarakstu un izvēlieties **tipu (tālrunis, nosaukums, adrese,...)**.
   - Iestatiet **Precizitātes līmeni**: **Pamatinformācija** un **Vērtību**: **Augsts**.

6. Ievadiet jaunās kārtulas nosaukumu **FullName, e-pasts**.

   - Pievienojiet e-pasta adresei otru nosacījumu, atlasot **Pievienot nosacījumu**
   - Entītijas eCommerceContacts izvēlieties nolaižamajā izvēlnē vienumu **E-pasts**.
   - Entītijai loyCustomers izvēlieties nolaižamajā izvēlnē vienumu **E-pasts**.
   - Atstājiet normalizāciju tukšu.
   - Iestatiet **Precizitātes līmeni**: **Pamatinformācija** un **Vērtību**: **Augsts**.

   ![Apvienot nosaukuma un e-pasta ziņojuma saskaņošanas kārtulu.](media/unify-match-rule.png)

7. Atlasiet vienumu **Saglabāt** un **Palaist**.

### <a name="merge"></a>Sapludināšana

1. Ejiet uz cilni **Sapludināt**.

1. **ContactId** attiecībā uz **loyCustomers** entītiju mainiet parādāmo nosaukumu uz **ContactIdLOYALTY**, lai atšķirtu to no citiem uzņemtajiem ID.

   ![pārdēvējiet contactid no lojalitātes ID.](media/unify-merge-contactid.png)

1. Atlasiet **Saglabāt** un **Palaist**, lai sāktu sapludināšanas procesu.

## <a name="task-3---configure-product-recommendation-prediction"></a>3. uzdevums — konfigurējiet produktu ieteikumu prognozi

Izmantojot vienoto klientu profilus, mēs tagad varam palaist abonēšanas zudumu prognozi.

1. Dodieties uz **Informācija** > **Prognoze**, izvēlieties **Produktu ieteikums**.

1. Atlasiet **Sākt darbu**.

1. Nosauciet modeļa **OOB produktu ieteikumu modeļa prognozi** un izvades entītiju **OOBProductRecommendationMoproductPrediction**.

1. Definējiet trīs modeļa nosacījumus:

   - **Produktu skaits**: iestatiet šo vērtību uz **5**. Šis iestatījums nosaka, cik daudz produktu klientiem vēlaties ieteikt.

   - **Vai ieteikt produktus, ko klienti nesen ir iegādājušies?** Atlasiet **Jā**, lai norādītu, ka produktus vēlaties iekļaut iepriekš ieteikumu, par klientu iepriekšējiem pirkumiem.

   - **Atskata logs**: atlasiet vismaz **365 dienas**. Šis iestatījums nosaka, cik tālu modelis atskatīsies uz klienta darbībām, lai izmantotu tās kā ieteikumu ievadi.
   
   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Modeļa preferences produktu ieteikumu modelim.":::

1. Atlasiet **Nepieciešamie dati** un atlasiet **Pievienot datus** pirkumu vēsturei.

1. Pievienojiet **eCommercePurchases : e-komercija** entītiju un kartējiet laukus no e-komercijas uz atbilstošiem modelī vajadzīgajiem laukiem.

1. Apvienojiet **eCommercePurchases: e-komercijas** entītiju ar **ECommerceContacts: e-komerciju**.

   ![Pievienojieties e-komercijas entītijām.](media/model-purchase-join.png)

1. Lai iestatītu modeļa grafiku, atlasiet **Tālāk**.

   Modelis ir regulāri jāapmāca, lai apgūtu jaunus rakstus, kad tiek uzņemti jauni dati. Šajā piemērā atlasiet **Reizi mēnesī**.

1. Pēc visas detalizētās informācijas pārskatīšanas atlasiet **Saglabāt un palaist**.


## <a name="task-4---review-model-results-and-explanations"></a>4.uzdevums — pārskatīt modeļa rezultātus un paskaidrojumus

Ļaujiet modelim pabeigt datu apmācīšanu un skaitīšanu. Tagad jūs varat pārskatīt produktu ieteikumu modeļa paskaidrojumus. Papildinformāciju skatiet rakstā [Prognozes statusa un rezultātu pārskatīšana](predict-subscription-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-purchased-products"></a>5. uzdevums — izveidot augstas vērtības iegādātu produktu segmentu

Palaižot ražošanas modeli, tiek izveidota jauna entītija, ko var redzēt vienumā **Dati** > **Entītijas**.

Varat izveidot jaunu segmentu, par pamatu izmantojot modelī izveidotu entītiju.

1. Ejiet uz **Segmenti**. Atlasiet vienumu **Jauns** un izvēlieties **Izveidot no** > **Informācija**.

   ![Izveidot segmentu ar modeļa izvadi.](media/segment-intelligence.png)

1. Atlasiet **OOBProductRecommendationModelPrediction** galapunktu un definējiet segmentu:

   - Lauks: ProductID
   - Operators: Vērtība
   - Vērtība: atlasiet trīs populārāko produktu ID

   :::image type="content" source="media/product-recommendation-quick-segment.png" alt-text="Izveidojiet segmentu no modeļa rezultātiem.":::

Tagad jums ir dinamiski atjaunināts segments, kas identificē klientus, kuri ļoti vēlas iegādāties trīs visvairāk ieteiktos produktus 

Papildinformācijai skatiet [Segmentu izveide un pārvaldība](segments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]