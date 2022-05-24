---
title: Produktu ieteikumu prognozes rokasgrāmatas paraugs
description: Izmantojiet šo parauga ceļvedi, lai izmēģinātu nestandarta produktu ieteikumu prognozes modeli.
ms.date: 05/16/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-predictions
- ci-create-prediction
- customerInsights
ms.openlocfilehash: cc72cce15fa0c9e92dbf202c803e99514c9ce2b1
ms.sourcegitcommit: 82f417cfb0a16600e9f552d7a21d598cc8f5a267
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 05/16/2022
ms.locfileid: "8762695"
---
# <a name="product-recommendation-prediction-sample-guide"></a>Produktu ieteikumu prognozes rokasgrāmatas paraugs

Mēs paskaidrosim, kā izbeigt produktu ieteikumu prognozi, izmantojot tālāk sniegto datu paraugu.

## <a name="scenario"></a>Scenārijs

Contoso ir uzņēmums, kas ražo kvalitatīvu kafiju un kafijas automātus, ko viņi pārdod, izmantojot savu Contoso Coffee mājaslapu. Šo mērķis ir saprast, kādus produktus viņiem ieteikt periodiskajiem klientiem. Zinot, kādi klienti **varētu nopirkt**, var palīdzēt ietaupīt mārketinga pasākumus, koncentrējoties uz konkrētiem produktiem.

## <a name="prerequisites"></a>Priekšnosacījumi

- Vismaz [Līdzautora atļaujas](permissions.md) Customer Insights.
- Ieteicams ieviest tālāk norādītos soļus [jaunā vidē](manage-environments.md).

## <a name="task-1---ingest-data"></a>1.uzdevums - Datu uzņemšana

Pārskatiet rakstus [par datu uzņemšanu](data-sources.md) un [datu avotu importēšanu, izmantojot Power Query savienotājus](connect-power-query.md). Tālāk sniegtajā informācijā tiek pieņemts, ka esat iepazinies ar datu uzņemšanu kopumā.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Uzņemt klientu datus no e-komercijas platformas

1. Izveidojiet datu avotu ar nosaukumu **e-komercija**, izvēlieties importēšanas opciju un atlasiet **Tekstu/CSV** savienotāju.

1. Ievadiet e-komercijas kontaktpersonu URL: [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).

1. Rediģējot datus, atlasiet **Pārveidot** un pēc tam **Izmantot pirmajā rindā kā galvenes**.

1. Atjauniniet tālāk uzskaitīto kolonnu datu tipu:
   - **DateOfBirth**: Datums
   - **CreatedOn**: Datums/Laiks/Josla

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Pārveidojiet dzimšanas datumu uz datumu.":::

1. Labās puses rūts laukā "Nosaukums" pārdēvējiet savu datu avotu no **Vaicājuma** uz **eCommerceContacts**

1. **Saglabājiet** datu avotu.

### <a name="ingest-online-purchase-data"></a>Tiešsaistes pirkuma datu uzņemšana

1. Pievienojiet citas datu kopas tiem pašiem **e-komercijas** datu avotiem. Vēlreiz izvēlieties **Tekstu/CSV** savienotāju.

1. Ievadiet tiešsaistes pirkumu **datu URL**[https://aka.ms/ciadclassonline](https://aka.ms/ciadclassonline).

1. Rediģējot datus, atlasiet **Pārveidot** un pēc tam **Izmantot pirmajā rindā kā galvenes**.

1. Atjauniniet tālāk uzskaitīto kolonnu datu tipu:
   - **PurchasedOn**: Datums/Laiks
   - **TotalPrice**: Valūta

1. Labās puses rūts laukā **Nosaukums** pārdēvējiet savu datu avotu no **Vaicājuma** uz **eCommercePurchases**.

1. **Saglabājiet** datu avotu.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Klienta datu uzņemšana no lojalitātes shēmas

1. Izveidojiet datu avotu ar nosaukumu **LoyaltyScheme**, izvēlieties importēšanas opciju un atlasiet **Tekstu/CSV** savienotāju.

1. Ievadiet e-komercijas kontaktpersonu URL [https://aka.ms/ciadclasscustomerloyalty](https://aka.ms/ciadclasscustomerloyalty).

1. Rediģējot datus, atlasiet **Pārveidot** un pēc tam **Izmantot pirmajā rindā kā galvenes**.

1. Atjauniniet tālāk uzskaitīto kolonnu datu tipu:
   - **DateOfBirth**: Datums
   - **RewardsPoints**: Vesels skaitlis
   - **CreatedOn**: Datums/Laiks

1. Labās puses rūts laukā **Nosaukums** pārdēvējiet savu datu avotu no **Vaicājuma** uz **loyCustomers**.

1. **Saglabājiet** datu avotu.

## <a name="task-2---data-unification"></a>2.uzdevums — Datu apvienošana

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---configure-product-recommendation-prediction"></a>3. uzdevums — konfigurējiet produktu ieteikumu prognozi

Ar vienotiem klientu profiliem mēs tagad varam palaist produktu ieteikumu prognoze.

1. Dodieties uz **Informācija** > **Prognoze**, izvēlieties **Produktu ieteikums**.

1. Atlasiet **Sākt darbu**.

1. Nosauciet modeļa **OOB produktu ieteikumu modeļa prognozi** un izvades entītiju **OOBProductRecommendationMoproductPrediction**.

1. Definējiet trīs modeļa nosacījumus:

   - **Produktu skaits**: iestatiet šo vērtību uz **5**. Šis iestatījums nosaka, cik daudz produktu klientiem vēlaties ieteikt.

   - **Atkārtojiet paredzamos pirkumus**: atlasiet **Jā**, lai norādītu, ka vēlaties iekļaut produktus ieteikumā, ko klienti ir iegādājušies iepriekš.

   - **Atskata logs**: atlasiet vismaz **365 dienas**. Šis iestatījums nosaka, cik tālu modelis atskatīsies uz klienta darbībām, lai izmantotu tās kā ieteikumu ievadi.

   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Modeļa preferences produktu ieteikumu modelim.":::

1. **Darbībā Pievienot nepieciešamos datus** atlasiet **Pievienot datus**.

1. **Rūtī Datu pievienošana** izvēlieties **SalesOrderLine** kā pirkšanas vēstures entītiju. Šajā brīdī tas, visticamāk, vēl nav konfigurēts. Rūtī atveriet saiti, lai izveidotu darbību, veicot šādas darbības:
   1. **Ievadiet aktivitātes nosaukumu** un izvēlieties *eCommercePurchases:eCommerce* kā **darbību entītiju**. Primārā **atslēga** ir *PurchaseId*.
   1. Definējiet un nosauciet saistību ar entītiju *eCommerceContacts*:eCommerce un izvēlieties **ContactId** kā ārējo atslēgu.
   1. Aktivitāšu apvienošanai iestatiet **notikuma aktivitāti** kā *TotalPrice* un Timestamp uz *PurchasedOn*. Varat norādīt citus laukus, kā norādīts [klientu darbībās](activities.md).
   1. Tipam **Aktivitāte** izvēlieties *SalesOrderLine*. Kartējiet šādus aktivitāšu laukus:
      - Pasūtījuma rindas ID: PurchaseId
      - Pasūtījuma ID: PurchaseId
      - Pasūtījuma dati: PurchasedOn
      - Produkta ID: ProductId
      - Summa: Kopējā cena
   1. Pārskatiet un pabeidziet darbību pirms atgriešanās modeļa konfigurācijā.

1. **Atpakaļ solī Atlasīt aktivitātes** izvēlieties jaunizveidoto darbību **sadaļā Aktivitātes**. Atlasiet **Tālāk**, un atribūtu kartējums jau ir aizpildīts. Atlasiet **Saglabāt**.

1. Šajā parauga rokasgrāmatā mēs izlaižam kopu **Pievienot informāciju par** produktu un **produktu filtriem**, jo mums nav informācijas par produktu datu.

1. **Solī Datu atjauninājumi** iestatiet modeļa grafiku.

   Modelis ir regulāri jāapmāca, lai apgūtu jaunus rakstus, kad tiek uzņemti jauni dati. Šajā piemērā atlasiet **Reizi mēnesī**.

1. Pēc visas detalizētās informācijas pārskatīšanas atlasiet **Saglabāt un palaist**. Modeļa palaišanai pirmo reizi būs nepieciešamas dažas minūtes.

## <a name="task-4---review-model-results-and-explanations"></a>4.uzdevums — pārskatīt modeļa rezultātus un paskaidrojumus

Ļaujiet modelim pabeigt datu apmācīšanu un skaitīšanu. Tagad jūs varat pārskatīt produktu ieteikumu modeļa paskaidrojumus. Papildinformāciju skatiet rakstā [Prognozes statusa un rezultātu pārskatīšana](predict-transactional-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-purchased-products"></a>5. uzdevums — izveidot augstas vērtības iegādātu produktu segmentu

Palaižot ražošanas modeli, tiek izveidota jauna entītija, ko var redzēt vienumā **Dati** > **Entītijas**.

Varat izveidot jaunu segmentu, par pamatu izmantojot modelī izveidotu entītiju.

1. Ejiet uz **Segmenti**. Atlasiet **Jauns** un izvēlieties **Izveidot no informācijas**.

   ![Izveidot segmentu ar modeļa izvadi.](media/segment-intelligence.png)

1. Atlasiet **OOBProductRecommendationModelPrediction** galapunktu un definējiet segmentu:

   - Lauks: ProductID
   - Vērtība: atlasiet trīs populārāko produktu ID

   :::image type="content" source="media/product-recommendation-quick-segment.png" alt-text="Izveidojiet segmentu no modeļa rezultātiem.":::

Tagad jums ir segments, kas ir dinamiski atjaunināts, kas identificē klientus, kuri varētu būt ieinteresēti iegādāties trīs ieteiktākos produktus.

Papildinformācijai skatiet [Segmentu izveide un pārvaldība](segments.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
