---
title: Debitora darbmūža prognozes parauga rokasgrāmata
description: Izmantojiet šo parauga rokasgrāmatu, lai izmēģinātu klienta dzīves prognozes modelim.
ms.date: 05/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: yashlundia
ms.author: yalundia
manager: shellyha
ms.openlocfilehash: 705e159f348e876f8a2a0ad3481608c6dd380df3dd74d7e5dba9dd3bebe25e52
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 08/10/2021
ms.locfileid: "7029500"
---
# <a name="customer-lifetime-value-clv-prediction-sample-guide"></a>Debitora darbmūža prognozes (CLV) parauga rokasgrāmata

Šajā rokasgrāmatā jums tiks izskaidrots klienta mūža vērtības (CLV) pilna piemēra prognoze, izmantojot datu paraugus programmā Customer Insights.

## <a name="scenario"></a>Scenārijs

Contoso ir uzņēmums, kas ražo augstas kvalitātes kafijas un kafijas automātus. Viņi pārdod produktus, izmantojot savu Contoso Coffee vietni. Uzņēmums vēlas saprast vērtību (ieņēmumus), ko viņu klienti var radīt nākamo 12 mēnešu laikā. Zinot savu klientu paredzamo vērtību nākamajos 12 mēnešos, viņi varēs virzīt savus mārketinga centienus uz augstvērtības klientiem.

## <a name="prerequisites"></a>Priekšnosacījumi

- Vismaz [līdzstrādnieka atļaujas](permissions.md) Audience Insights.
- Ieteicams ieviest tālāk norādītos soļus [jaunā vidē](manage-environments.md).

## <a name="task-1---ingest-data"></a>1.uzdevums - Datu uzņemšana

Pārskatiet rakstus [par datu ietveršanu](data-sources.md) un [datu avotu importēšanu, izmantojot Power Query savienotājus](connect-power-query.md). Tālāk sniegtajā informācijā tiek pieņemts, ka esat iepazinies ar datu uzņemšanu kopumā.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Uzņemt klientu datus no e-komercijas platformas

1. Izveidojiet datu avotu ar nosaukumu **eCommerce**, izvēlieties importēšanas opciju un atlasiet **Teksta/CSV** savienotāju.

1. Ievadiet URL eCommerce kontaktpersonām [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).

1. Rediģējot datus, atlasiet  **Pārveidot**  un pēc tam  **Izmantot pirmajā rindā kā galvenes**.

1. Atjauniniet tālāk uzskaitīto kolonnu datu tipu:
   - **DateOfBirth**: Datums
   - **CreatedOn**: Datums/Laiks/Josla

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Pārveidojiet dzimšanas datumu uz datumu.":::

1. Labās puses rūts laukā "Nosaukums" pārdēvējiet savu datu avotu no **Vaicājuma** uz **eCommerceContacts**

1. **Saglabājiet** datu avotu.

### <a name="ingest-online-purchase-data"></a>Tiešsaistes pirkuma datu uzņemšana

1. Pievienojiet citas datu kopas tiem pašiem **e-komercijas** datu avotiem. Vēlreiz izvēlieties **Tekstu/CSV** savienotāju.

1. Ievadiet **Tiešsaistes pirkumu** datu URL https://aka.ms/ciadclassonline.

1. Rediģējot datus, atlasiet **Pārveidot** un pēc tam **Izmantot pirmajā rindā kā galvenes**.

1. Atjauniniet tālāk uzskaitīto kolonnu datu tipu:
   - **PurchasedOn**: Datums/Laiks
   - **TotalPrice**: Valūta

1. Labās puses rūts laukā **Nosaukums** pārdēvējiet savu datu avotu no **Vaicājuma** uz **eCommercePurchases**.

1. **Saglabājiet** datu avotu.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Klienta datu uzņemšana no lojalitātes shēmas

1. Izveidojiet datu avotu ar nosaukumu **LoyaltyScheme**, izvēlieties importēšanas opciju un atlasiet **Tekstu/CSV** savienotāju.

1. Ievadiet URL e-komercijas kontaktpersonām https://aka.ms/ciadclasscustomerloyalty.

1. Rediģējot datus, atlasiet **Pārveidot** un pēc tam **Izmantot pirmajā rindā kā galvenes**.

1. Atjauniniet tālāk uzskaitīto kolonnu datu tipu:
   - **DateOfBirth**: Datums
   - **RewardsPoints**: Vesels skaitlis
   - **CreatedOn**: Datums/Laiks

1. Labās puses rūts laukā **Nosaukums** pārdēvējiet savu datu avotu no **Vaicājuma** uz **loyCustomers**.

1. **Saglabājiet** datu avotu.

### <a name="ingest-customer-data-from-website-reviews"></a>Klientu datu uzņemšana no tīmekļa pārskatiem

1. Izveidojiet datu avotu ar nosaukumu **e-komercija**, izvēlieties importēšanas opciju un atlasiet **Tekstu/CSV** savienotāju.

1. Ievadiet URL e-komercijas kontaktpersonām https://aka.ms/CI-ILT/WebReviews.

1. Rediģējot datus, atlasiet **Pārveidot** un pēc tam **Izmantot pirmajā rindā kā galvenes**.

1. Atjauniniet tālāk uzskaitīto kolonnu datu tipu:

   - **ReviewRating**: decimāldaļskaitlis
   - **ReviewDate**: Datums

1. Labās puses rūts laukā Nosaukums pārdēvējiet savu datu avotu no **Vaicājumi** uz **Pārskati**.

1. **Saglabājiet** datu avotu.

## <a name="task-2---data-unification"></a>2.uzdevums — Datu apvienošana

Pēc datu ietveršanas mēs sākam datu apvienošanas procesu, lai izveidotu vienotu klientu profilu. Papildinformāciju skatiet tēmā [Datu apvienošana](data-unification.md).

### <a name="map"></a>Kartēt

1. Pēc datu uzņemšanas kartējiet kontaktpersonas no e-komercijas un lojalitātes datiem līdz vispārējiem datu tipiem. Ejiet uz **Dati** > **Apvienot** > **Kartēt**.

1. Atlasiet entītijas, kas pārstāv klienta profilu — **eCommerceContacts** un **loyCustomers**. Atlasiet vienumu **Piemērot**.

   ![apvienot e-komercijas un lojalitātes datu avotus.](media/unify-ecommerce-loyalty.png)

1. Atlasiet **ContactId** kā primāro atslēgu **eCommerceContacts** un **LoyaltyID** kā **loyCustomers** primāro atslēgu.

   ![Apvienot LoyaltyId kā primāro atslēgu.](media/unify-loyaltyid.png)

1. Atlasiet vienumu **Saglabāt**.

### <a name="match"></a>Saskaņot

1. Dodieties uz cilni **Saskaņot** un atlasiet **Iestatīt secību**.

1. Nolaižamajā sarakstā **Primārs** izvēlieties **eCommerceContacts : eCommerce** kā primāro avotu un iekļaujiet visus ierakstus.

1. Nolaižamajā sarakstā **2. entītija** izvēlieties **loyCustomers :LoyaltyScheme** un iekļaujiet visus ierakstus.

   ![Apvienot e-komercijas un lojalitātes atbilstības.](media/unify-match-order.png)

1. Atlasiet **Pievienot kārtulu**

1. Pievienojiet pirmo nosacījumu, izmantojot FullName.

   - Entītijai eCommerceContacts atlasiet **FullName** nolaižamajā sarakstā.
   - Entītijai loyCustomers atlasiet **FullName** nolaižamajā sarakstā.
   - Atlasiet nolaižamo izvēlni **Normalizēt** un izvēlieties **Tips (Tālrunis, Nosaukums, Adrese, ...)**.
   - Iestatiet **Precizitātes līmeni**: **Pamatinformācija** un **Vērtību**: **Augsts**.

1. Ievadiet jaunās kārtulas nosaukumu **FullName, e-pasts**.

   - Pievienojiet e-pasta adresei otru nosacījumu, atlasot **Pievienot nosacījumu**
   - Entītijai eCommerceContacts nolaižamajā sarakstā izvēlieties **E-pasts**.
   - Entītijai loyCustomers nolaižamajā sarakstā izvēlieties **E-pasts**.
   - Atstājiet normalizāciju tukšu.
   - Iestatiet **Precizitātes līmeni**: **Pamatinformācija** un **Vērtību**: **Augsts**.

   ![Apvienot nosaukuma un e-pasta ziņojuma saskaņošanas kārtulu.](media/unify-match-rule.png)

1. Atlasiet **Gatavs**.

1. Atlasiet vienumu **Saglabāt** un **Palaist**.

### <a name="merge"></a>Sapludināšana

1. Ejiet uz cilni **Sapludināt**.

1. **ContactId** attiecībā uz **loyCustomers** entītiju mainiet parādāmo nosaukumu uz **ContactIdLOYALTY**, lai atšķirtu to no citiem uzņemtajiem ID.

   ![pārdēvējiet contactid no lojalitātes ID.](media/unify-merge-contactid.png)

1. Atlasiet **Saglabāt** un **Palaist sapludināšanas un lejasposma procesus**.

## <a name="task-3---configure-customer-lifetime-value-prediction"></a>3. uzdevums - konfigurēt debitora mūža vērtību prognoze

Tagad, izmantojot vienotos klientu profilus, mēs tagad varam izmantot klienta darbmūža prognozi. Detalizētas darbības skatiet sadaļā [Klienta Darbmūža vērtība prognoze (priekšskatījums)](predict-customer-lifetime-value.md).

1. Dodieties uz **Informācija**  > **Prognozes** un atlasiet **Klienta darbmūža vērtības modelis**.

1. Skatiet informāciju sānu rūtī un atlasiet **Sākt darbu**.

1. Nosauciet modeli **OOB eCommerce CLV prognoze** un izvades entītiju **OOBeCommerceCLVPrediction**.

1. Definēt modeļa preferences CLV modelim:
   - **Prognoze periods**: **12 mēneši vai 1 gads**. Šis iestatījums definē, cik tālu nākotnē ir paredzama klienta darbmūža vērtība.
   - **Aktīvie klienti**: norādiet, kādus aktīvos klientus jūsu uzņēmumam nozīmē. Iestatiet vēsturisko laika periodu, kurā klientam ir jābūt vismaz vienai darbībai, lai to uzskatītu par aktīvu. Modelis prognozēs CLV tikai aktīvajiem klientiem. Izvēlieties, vai šis modelis aprēķina laika periodu, pamatojoties uz vēsturiskiem transakciju datiem, vai sniedziet noteiktu laika periodu. Šajā parauga ceļvedī mēs **ļaujam modelim aprēķināt iegādes intervālu**, kas ir noklusējuma opcija.
   - **Augstas vērtības klienti**: definējiet klientus ar augstu vērtību kā maksātspējīgākajiem klientiem. Modelis izmanto šo ievadi, lai nodrošinātu rezultātus, kas atbilst jūsu uzņēmuma definīcijai ar augstas vērtības klientiem. Jūs varat ļaut modelim definēt vērtīgos klientus. Tā izmanto heiristisko kārtulu, kas atvasina procentili. Jūs varat definēt klientus ar augstu vērtību kā maksātspējīgākos klientus. Šajā parauga ceļvedī klientiem ar augstu vērtību mēs manuāli definējam **kā 30% maksātspējīgāko klientu** un atlasiet **Tālāk**.

    :::image type="content" source="media/clv-model-preferences.png" alt-text="CLV modeļa vadītās pieredzes preferenču solis.":::

1. Darbībā **Nepieciešamie dati** atlasiet vienumu **Pievienot datus**, lai nodrošinātu transakciju vēstures datus.

1. Pievienojiet **eCommercePurchases : eCommerce** un kartējiet modelim nepieciešamos atribūtus:
   - Transakcijas ID: eCommerce.eCommercePurchases.PurchaseId
   - Transakcijas datums: eCommerce.eCommercePurchases.PurchasedOn
   - Transakcijas summa: eCommerce.eCommercePurchases.TotalPrice
   - Produkta ID: eCommerce.eCommercePurchases.ProductId

1. Atlasiet **Tālāk**.

1. Iestatiet attiecības starp entītiju **eCommercePurchases : eCommerce** un **eCommerceContacts : eCommerce**.

1. Izmantojot darbību **Papildu dati (neobligāti)**, varat pievienot papildu klientu darbību datus. Šie dati var palīdzēt iegūt vairāk ieskatu par klientu mijiedarbību ar jūsu uzņēmumu, tādējādi var palīdzēt CLV. Pievienojot galvenās klientu mijiedarbības, piemēram, tīmekļa žurnālus klientu apkalpošana žurnālus vai apbalvojumu programmas vēsturi, var uzlabot sīcīšanas precizitāti. Atlasiet vienumu **Pievienot datus**, lai iekļautu papildu klientu darbību datus.

1. Pievienojiet klienta darbības entītiju un kartējiet tās lauku nosaukumus ar atbilstošajiem modeļa obligātajiem laukiem:
   - Klienta darbības entītija: Reviews:Website
   - Primārā atslēga: Website.Reviews.ReviewId
   - Laikspiedols: Website.Reviews.ReviewDate
   - Notikums (darbības nosaukums): Website.Reviews.ActivityTypeDisplay
   - Detalizēti (summa vai vērtība): Website.Reviews.ReviewRating

1. Atlasiet **Tālāk** un konfigurējiet darbību, kā arī transakciju datu un klienta datu attiecības:  
   - Darbības veids: Izvēlēties esošu
   - Darbības etiķete: Pārskats
   - Atbilstošā etiķete: Website.Reviews.UserId
   - Klienta entītija: eCommerceContacts:eCommerce
   - Attiecības: WebsiteReviews

1. Lai iestatītu modeļa grafiku, atlasiet **Tālāk**.

   Modelim ir regulāri jāmācās, lai apgūtu jaunus paraugus, kad tiek iekļauti jauni dati. Šim piemēram izvēlieties **Ik mēnesi**.

1. Pēc visas detalizētās informācijas pārskatīšanas atlasiet **Saglabāt un palaist**.

## <a name="task-4---review-model-results-and-explanations"></a>4.uzdevums — pārskatīt modeļa rezultātus un paskaidrojumus

Ļaujiet modelim pabeigt datu apmācīšanu un skaitīšanu. Pēc tam varat pārskatīt CLV modeļa rezultātus un paskaidrojumus. Papildinformāciju skatiet rakstā [Prognozes statusa un rezultātu pārskatīšana](predict-customer-lifetime-value.md#review-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-value-customers"></a>5. uzdevums — izveidot augstas vērtības klientu segmentu

Izpildot modeli, tiek izveidota jauna entītija, kas tiek iekļauta sarakstā **Dati** > **Entītijas**. Varat izveidot jaunu klienta segmentu, pamatojoties uz modeļa izveidoto entītiju.

1. Ejiet uz **Segmenti**. 

1. Atlasiet vienumu **Jauns** un izvēlieties **Izveidot no** > **Informācija**.

   ![Izveidot segmentu ar modeļa izvadi.](media/segment-intelligence.png)

1. Atlasiet entītiju **OOBeCommerceCLVPrediction** un definējiet segmentu:
  - Lauks: CLVScore
  - Operators: ir lielāks nekā
  - Vērtība: 1500

1. Atlasiet **Pārskats** un **Saglabāt** segmentu.

Tagad jums ir segments, kas identificē klientus, kuri, pēc prognozēm, nākamajos 12 mēnešos veidos vairāk nekā $1500 lielus ieņēmumus. Ja ietverat vairāk datu, šis segments dinamiski tiek atjaunināts.

Papildinformācijai skatiet [Segmentu izveide un pārvaldība](segments.md).
