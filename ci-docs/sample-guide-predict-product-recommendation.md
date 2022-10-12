---
title: Produktu ieteikumu prognozes rokasgrāmatas paraugs
description: Izmantojiet šo parauga ceļvedi, lai izmēģinātu nestandarta produktu ieteikumu prognozes modeli.
ms.date: 09/19/2022
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
ms.openlocfilehash: 2b42a89e3f4ec8cf4f0769128b8536973365f1cb
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610153"
---
# <a name="product-recommendation-prediction-sample-guide"></a>Produktu ieteikumu prognozes rokasgrāmatas paraugs

Šajā ceļvedī ir sniegts visaptverošs piemērs par produktu ieteikumu prognoze datu paraugu izmantošanu. Mēs iesakām izmēģināt šo prognoze [jaunā vidē](manage-environments.md).

## <a name="scenario"></a>Situācija

Contoso ir uzņēmums, kas ražo augstas kvalitātes kafijas un kafijas automātus. Viņi pārdod produktus, izmantojot savu Contoso kafijas vietni. Šo mērķis ir saprast, kādus produktus viņiem ieteikt periodiskajiem klientiem. Zinot, ko klienti **, visticamāk, iegādāsies**, var palīdzēt viņiem ietaupīt mārketinga pasākumus, koncentrējoties uz konkrētām precēm.

## <a name="prerequisites"></a>Priekšnoteikumi

- Vismaz [Līdzautora atļaujas](permissions.md) Customer Insights.

## <a name="task-1---ingest-data"></a>1.uzdevums - Datu uzņemšana

Pārskatiet rakstus [par datu uzņemšanu](data-sources.md) un [savienojuma izveidi ar Power Query datu avots](connect-power-query.md). Tālāk sniegtā informācija pieņem, ka esat iepazinies ar datu uzņemšanu kopumā.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Uzņemt klientu datus no e-komercijas platformas

1. Izveidojiet Power Query datu avots ar nosaukumu **e-komercija un** atlasiet **teksta/CSV savienotāju**.

1. Ievadiet e-komercijas kontaktpersonu vietrādi URL:https://aka.ms/ciadclasscontacts.

1. Rediģējot datus, atlasiet **Pārveidot un pēc tam** izmantot pirmo rindu kā **galvenes**.

1. Atjauniniet tālāk uzskaitīto kolonnu datu tipu:
   - **DateOfBirth**: Datums
   - **CreatedOn**: Datums/Laiks/Josla

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Pārveidojiet dzimšanas datumu uz datumu.":::

1. Labās **puses rūts laukā Nosaukums** pārdēvējiet savu datu avots par **e-komercijaskontaktiem**.

1. **Saglabājiet** datu avotu.

### <a name="ingest-online-purchase-data"></a>Tiešsaistes pirkuma datu uzņemšana

1. Pievienojiet citas datu kopas tiem pašiem **e-komercijas** datu avotiem. Vēlreiz izvēlieties **Tekstu/CSV** savienotāju.

1. Ievadiet tiešsaistes pirkumu datu https://aka.ms/ciadclassonline vietrādi URL.

1. Rediģējot datus, atlasiet **Pārveidot un pēc tam** izmantot pirmo rindu kā **galvenes**.

1. Atjauniniet tālāk uzskaitīto kolonnu datu tipu:
   - **PurchasedOn**: Datums/Laiks
   - **TotalPrice**: Valūta

1. **Sānu rūts laukā Nosaukums** pārdēvējiet savu datu avots par **e-komercijas iepirkumiem**.

1. **Saglabājiet** datu avotu.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Klienta datu uzņemšana no lojalitātes shēmas

1. Izveidojiet datu avots ar nosaukumu **LoyaltyScheme** un atlasiet **teksta/CSV** savienotāju.

1. Ievadiet lojālo klientu vietrādi URL https://aka.ms/ciadclasscustomerloyalty.

1. Rediģējot datus, atlasiet **Pārveidot un pēc tam** izmantot pirmo rindu kā **galvenes**.

1. Atjauniniet tālāk uzskaitīto kolonnu datu tipu:
   - **DateOfBirth**: Datums
   - **RewardsPoints**: Vesels skaitlis
   - **CreatedOn**: Datums/Laiks

1. Labās **puses rūts laukā Nosaukums** pārdēvējiet savu datu avots par **loyCustomers**.

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

## <a name="task-4---configure-product-recommendation-prediction"></a>4. uzdevums — konfigurējiet produktu ieteikumu prognozi

Kad ir ieviesti vienoti klientu profili un izveidota darbība, palaidiet produkta ieteikumu prognoze.

1. Dodieties uz **izlūkošanas** > **prognozēm**.

1. Cilnē **Izveide** atlasiet **Izmantot modeli** elementā **Produkta ieteikumi (priekšskatījums).**

1. Atlasiet **Sākt darbu**.

1. Nosauciet modeļa **OOB produktu ieteikumu modeļa prognozi** un izvades entītiju **OOBProductRecommendationMoproductPrediction**.

1. Atlasiet **Tālāk**.

1. Definējiet modeļa preferences:
   - **Produktu** skaits: **5**, lai definētu, cik daudz produktu vēlaties ieteikt saviem klientiem.
   - **Paredzamie** atkārtotie pirkumi: **jā**, lai ieteikumā iekļautu iepriekš iegādātos produktus.
   - **Atskatīšanās logs:** **365 dienas**, lai definētu, cik tālu modelis atskatīsies atpakaļ, pirms atkal ieteiks produktu.

   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Modeļa preferences produktu ieteikumu modelim.":::

1. Atlasiet **Tālāk**.

1. Darbībā Pievienot **pirkumu vēsturi** atlasiet **Pievienot datus**.

1. Atlasiet **SalesOrderLine** un entītiju e-komercijas pirkumi un atlasiet **Tālāk**. Nepieciešamie dati tiek automātiski aizpildīti no darbības. Atlasiet **Saglabāt** un pēc tam **Tālāk**.

1. **Izlaidiet darbības Pievienot informāciju par** produktu un **Produktu filtri**, jo mums nav informācijas par produktu.

1. **Darbībā Datu atjauninājumi** modeļa grafikam atlasiet **Katru mēnesi**.

1. Atlasiet **Tālāk**.

1. Pēc visas detalizētās informācijas pārskatīšanas atlasiet **Saglabāt un palaist**.

## <a name="task-5---review-model-results-and-explanations"></a>5. uzdevums - modeļa rezultātu un skaidrojumu pārskatīšana

Ļaujiet modelim pabeigt datu apmācīšanu un skaitīšanu. Pārskatiet [produkta ieteikumu modeļa skaidrojumus](predict-transactional-churn.md#view-prediction-results).

## <a name="task-6---create-a-segment-of-high-purchased-products"></a>6. uzdevums — izveidot augstas vērtības iegādātu produktu segmentu

Izpildot modeli, tiek izveidota jauna entītija, kas tiek iekļauta sarakstā **Dati** > **Entītijas**. Varat izveidot jaunu segmentu, par pamatu izmantojot modelī izveidotu entītiju.

1. Rezultātu lapā atlasiet **Izveidot segmentu**.

1. Izveidojiet kārtulu, izmantojot entītiju **OOBProductRecommendationModelPrediction**, un definējiet segmentu:
   - **Lauks**: Produkta ID
   - **Vērtība**: atlasiet trīs labākos produktu ID

1. Atlasiet **Saglabāt** un **palaist** segmentu.

Tagad jums ir dinamiski atjaunināts segments, kas identificē klientus, kuri varētu būt ieinteresēti iegādāties piecus visvairāk ieteiktos produktus. Papildinformācijai skatiet [Segmentu izveide un pārvaldība](segments.md).

> [!TIP]
> Segmentu prognoze modelim var izveidot arī lapā Segmenti **,** atlasot **Jauns** un izvēloties **Izveidot no** > **informācijas**. Papildinformāciju skatiet sadaļā [Jauna segmenta izveide ar ātriem segmentiem](segment-quick.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
