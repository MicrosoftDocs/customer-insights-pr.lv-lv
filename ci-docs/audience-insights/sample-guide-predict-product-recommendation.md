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
ms.openlocfilehash: a85ee598ec747d0594755314e83a127ce0f2af95
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 06/24/2021
ms.locfileid: "6306175"
---
# <a name="product-recommendation-prediction-preview-sample-guide"></a><span data-ttu-id="7610d-103">Produktu ieteikumu prognozes (priekšskatījums) rokasgrāmatas paraugs</span><span class="sxs-lookup"><span data-stu-id="7610d-103">Product recommendation prediction (preview) sample guide</span></span>

<span data-ttu-id="7610d-104">Mēs paskaidrosim, kā izbeigt produktu ieteikumu prognozi, izmantojot tālāk sniegto datu paraugu.</span><span class="sxs-lookup"><span data-stu-id="7610d-104">We'll walk you through an end to end example of product recommendation prediction using the sample data provided below.</span></span>

## <a name="scenario"></a><span data-ttu-id="7610d-105">Scenārijs</span><span class="sxs-lookup"><span data-stu-id="7610d-105">Scenario</span></span>

<span data-ttu-id="7610d-106">Contoso ir uzņēmums, kas ražo augstas kvalitātes kafijas un kafijas automātus, kurus viņi pārdod, izmantojot savu Contoso Coffee vietni.</span><span class="sxs-lookup"><span data-stu-id="7610d-106">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="7610d-107">Šo mērķis ir saprast, kādus produktus viņiem ieteikt periodiskajiem klientiem.</span><span class="sxs-lookup"><span data-stu-id="7610d-107">Their goal is to understand which products should they recommend to their recurring customers.</span></span> <span data-ttu-id="7610d-108">Zinot, kādi klienti **varētu nopirkt**, var palīdzēt ietaupīt mārketinga pasākumus, koncentrējoties uz konkrētiem produktiem.</span><span class="sxs-lookup"><span data-stu-id="7610d-108">Knowing what customers are more **likely to purchase**, can help them save marketing efforts by focusing on specific items.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="7610d-109">Priekšnosacījumi</span><span class="sxs-lookup"><span data-stu-id="7610d-109">Prerequisites</span></span>

- <span data-ttu-id="7610d-110">Vismaz [Līdzautora atļaujas](permissions.md) Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="7610d-110">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="7610d-111">Ieteicams ieviest tālāk norādītos soļus [jaunā vidē](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="7610d-111">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="7610d-112">1.uzdevums - Datu uzņemšana</span><span class="sxs-lookup"><span data-stu-id="7610d-112">Task 1 - Ingest data</span></span>

<span data-ttu-id="7610d-113">Pārskatiet rakstus [par datu uzņemšanu](data-sources.md) un [datu avotu importēšanu, izmantojot](connect-power-query.md) tieši Power Query savienotājus.</span><span class="sxs-lookup"><span data-stu-id="7610d-113">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="7610d-114">Tālāk sniegtajā informācijā tiek pieņemts, ka esat iepazinies ar datu uzņemšanu kopumā.</span><span class="sxs-lookup"><span data-stu-id="7610d-114">The following information assumes you familiarized with ingesting data in general.</span></span>

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="7610d-115">Uzņemt klientu datus no e-komercijas platformas</span><span class="sxs-lookup"><span data-stu-id="7610d-115">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="7610d-116">Izveidojiet datu avotu ar nosaukumu **e-komercija**, izvēlieties importēšanas opciju un atlasiet **Tekstu/CSV** savienotāju.</span><span class="sxs-lookup"><span data-stu-id="7610d-116">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="7610d-117">Ievadiet URL e-komercijas kontaktpersonām https://aka.ms/ciadclasscontacts.</span><span class="sxs-lookup"><span data-stu-id="7610d-117">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="7610d-118">Rediģējot datus, atlasiet **Pārveidot** un pēc tam **Izmantot pirmajā rindā kā galvenes**.</span><span class="sxs-lookup"><span data-stu-id="7610d-118">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="7610d-119">Atjauniniet tālāk uzskaitīto kolonnu datu tipu:</span><span class="sxs-lookup"><span data-stu-id="7610d-119">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="7610d-120">**DateOfBirth**: Datums</span><span class="sxs-lookup"><span data-stu-id="7610d-120">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="7610d-121">**CreatedOn**: Datums/Laiks/Josla</span><span class="sxs-lookup"><span data-stu-id="7610d-121">**CreatedOn**: Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Pārveidojiet dzimšanas datumu uz datumu.":::

5. <span data-ttu-id="7610d-123">Labās puses rūts laukā "Nosaukums" pārdēvējiet savu datu avotu no **Vaicājuma** uz **eCommerceContacts**</span><span class="sxs-lookup"><span data-stu-id="7610d-123">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

6. <span data-ttu-id="7610d-124">**Saglabājiet** datu avotu.</span><span class="sxs-lookup"><span data-stu-id="7610d-124">**Save** the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="7610d-125">Tiešsaistes pirkuma datu uzņemšana</span><span class="sxs-lookup"><span data-stu-id="7610d-125">Ingest online purchase data</span></span>

1. <span data-ttu-id="7610d-126">Pievienojiet citas datu kopas tiem pašiem **e-komercijas** datu avotiem.</span><span class="sxs-lookup"><span data-stu-id="7610d-126">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="7610d-127">Vēlreiz izvēlieties **Tekstu/CSV** savienotāju.</span><span class="sxs-lookup"><span data-stu-id="7610d-127">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="7610d-128">Ievadiet **Tiešsaistes pirkumu** datu URL https://aka.ms/ciadclassonline.</span><span class="sxs-lookup"><span data-stu-id="7610d-128">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="7610d-129">Rediģējot datus, atlasiet **Pārveidot** un pēc tam **Izmantot pirmajā rindā kā galvenes**.</span><span class="sxs-lookup"><span data-stu-id="7610d-129">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="7610d-130">Atjauniniet tālāk uzskaitīto kolonnu datu tipu:</span><span class="sxs-lookup"><span data-stu-id="7610d-130">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="7610d-131">**PurchasedOn**: Datums/Laiks</span><span class="sxs-lookup"><span data-stu-id="7610d-131">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="7610d-132">**TotalPrice**: Valūta</span><span class="sxs-lookup"><span data-stu-id="7610d-132">**TotalPrice**: Currency</span></span>

1. <span data-ttu-id="7610d-133">Labās puses rūts laukā **Nosaukums** pārdēvējiet savu datu avotu no **Vaicājuma** uz **eCommercePurchases**.</span><span class="sxs-lookup"><span data-stu-id="7610d-133">In the **Name** field on the side pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="7610d-134">**Saglabājiet** datu avotu.</span><span class="sxs-lookup"><span data-stu-id="7610d-134">**Save** the data source.</span></span>


### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="7610d-135">Klienta datu uzņemšana no lojalitātes shēmas</span><span class="sxs-lookup"><span data-stu-id="7610d-135">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="7610d-136">Izveidojiet datu avotu ar nosaukumu **LoyaltyScheme**, izvēlieties importēšanas opciju un atlasiet **Tekstu/CSV** savienotāju.</span><span class="sxs-lookup"><span data-stu-id="7610d-136">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="7610d-137">Ievadiet URL e-komercijas kontaktpersonām https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="7610d-137">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="7610d-138">Rediģējot datus, atlasiet **Pārveidot** un pēc tam **Izmantot pirmajā rindā kā galvenes**.</span><span class="sxs-lookup"><span data-stu-id="7610d-138">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="7610d-139">Atjauniniet tālāk uzskaitīto kolonnu datu tipu:</span><span class="sxs-lookup"><span data-stu-id="7610d-139">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="7610d-140">**DateOfBirth**: Datums</span><span class="sxs-lookup"><span data-stu-id="7610d-140">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="7610d-141">**RewardsPoints**: Vesels skaitlis</span><span class="sxs-lookup"><span data-stu-id="7610d-141">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="7610d-142">**CreatedOn**: Datums/Laiks</span><span class="sxs-lookup"><span data-stu-id="7610d-142">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="7610d-143">Labās puses rūts laukā **Nosaukums** pārdēvējiet savu datu avotu no **Vaicājuma** uz **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="7610d-143">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="7610d-144">**Saglabājiet** datu avotu.</span><span class="sxs-lookup"><span data-stu-id="7610d-144">**Save** the data source.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="7610d-145">2.uzdevums — Datu apvienošana</span><span class="sxs-lookup"><span data-stu-id="7610d-145">Task 2 - Data unification</span></span>

<span data-ttu-id="7610d-146">Pēc datu ietveršanas mēs sākam datu apvienošanas procesu, lai izveidotu vienotu klientu profilu.</span><span class="sxs-lookup"><span data-stu-id="7610d-146">After ingesting the data, we now begin the data unification process to create a unified customer profile.</span></span> <span data-ttu-id="7610d-147">Papildinformāciju skatiet tēmā [Datu apvienošana](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="7610d-147">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="7610d-148">Kartēt</span><span class="sxs-lookup"><span data-stu-id="7610d-148">Map</span></span>

1. <span data-ttu-id="7610d-149">Pēc datu uzņemšanas kartējiet kontaktpersonas no e-komercijas un lojalitātes datiem līdz vispārējiem datu tipiem.</span><span class="sxs-lookup"><span data-stu-id="7610d-149">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="7610d-150">Ejiet uz **Dati** > **Apvienot** > **Kartēt**.</span><span class="sxs-lookup"><span data-stu-id="7610d-150">Go to **Data** > **Unify** > **Map**.</span></span>

2. <span data-ttu-id="7610d-151">Atlasiet entītijas, kas pārstāv klienta profilu — **eCommerceContacts** un **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="7610d-151">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span>

   ![apvienot e-komercijas un lojalitātes datu avotus.](media/unify-ecommerce-loyalty.png)

3. <span data-ttu-id="7610d-153">Atlasiet **ContactId** kā primāro atslēgu **eCommerceContacts** un **LoyaltyID** kā **loyCustomers** primāro atslēgu.</span><span class="sxs-lookup"><span data-stu-id="7610d-153">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   ![Apvienot LoyaltyId kā primāro atslēgu.](media/unify-loyaltyid.png)

### <a name="match"></a><span data-ttu-id="7610d-155">Saskaņot</span><span class="sxs-lookup"><span data-stu-id="7610d-155">Match</span></span>

1. <span data-ttu-id="7610d-156">Dodieties uz cilni **Saskaņot** un atlasiet **Iestatīt secību**.</span><span class="sxs-lookup"><span data-stu-id="7610d-156">Go to the **Match** tab and select **Set Order**.</span></span>

2. <span data-ttu-id="7610d-157">Nolaižamajā sarakstā **Primārs** izvēlieties **eCommerceContacts : eCommerce** kā primāro avotu un iekļaujiet visus ierakstus.</span><span class="sxs-lookup"><span data-stu-id="7610d-157">In the **Primary** dropdown list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

3. <span data-ttu-id="7610d-158">Nolaižamajā sarakstā **2. entītija** izvēlieties **loyCustomers :LoyaltyScheme** un iekļaujiet visus ierakstus.</span><span class="sxs-lookup"><span data-stu-id="7610d-158">In the **Entity 2** dropdown list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   ![Apvienot e-komercijas un lojalitātes atbilstības.](media/unify-match-order.png)

4. <span data-ttu-id="7610d-160">Atlasiet **Jaunas kārtulas izveide**</span><span class="sxs-lookup"><span data-stu-id="7610d-160">Select **Create a new rule**</span></span>

5. <span data-ttu-id="7610d-161">Pievienojiet pirmo nosacījumu, izmantojot FullName.</span><span class="sxs-lookup"><span data-stu-id="7610d-161">Add your first condition using FullName.</span></span>

   - <span data-ttu-id="7610d-162">Entītijai eCommerceContacts atlasiet **FullName** nolaižamajā sarakstā.</span><span class="sxs-lookup"><span data-stu-id="7610d-162">For eCommerceContacts select **FullName** in the dropdown.</span></span>
   - <span data-ttu-id="7610d-163">Entītijai loyCustomers atlasiet **FullName** nolaižamajā sarakstā.</span><span class="sxs-lookup"><span data-stu-id="7610d-163">For loyCustomers select **FullName** in the dropdown.</span></span>
   - <span data-ttu-id="7610d-164">Atlasiet opciju **Normalizēt** nolaižamo sarakstu un izvēlieties **tipu (tālrunis, nosaukums, adrese,...)**.</span><span class="sxs-lookup"><span data-stu-id="7610d-164">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   - <span data-ttu-id="7610d-165">Iestatiet **Precizitātes līmeni**: **Pamatinformācija** un **Vērtību**: **Augsts**.</span><span class="sxs-lookup"><span data-stu-id="7610d-165">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

6. <span data-ttu-id="7610d-166">Ievadiet jaunās kārtulas nosaukumu **FullName, e-pasts**.</span><span class="sxs-lookup"><span data-stu-id="7610d-166">Enter the name **FullName, Email** for the new rule.</span></span>

   - <span data-ttu-id="7610d-167">Pievienojiet e-pasta adresei otru nosacījumu, atlasot **Pievienot nosacījumu**</span><span class="sxs-lookup"><span data-stu-id="7610d-167">Add a second condition for email address by selecting **Add Condition**</span></span>
   - <span data-ttu-id="7610d-168">Entītijai eCommerceContacts nolaižamajā sarakstā izvēlieties **E-pasts**.</span><span class="sxs-lookup"><span data-stu-id="7610d-168">For entity eCommerceContacts, choose **EMail** in dropdown.</span></span>
   - <span data-ttu-id="7610d-169">Entītijai loyCustomers nolaižamajā sarakstā izvēlieties **E-pasts**.</span><span class="sxs-lookup"><span data-stu-id="7610d-169">For entity loyCustomers, choose **EMail** in the dropdown.</span></span>
   - <span data-ttu-id="7610d-170">Atstājiet normalizāciju tukšu.</span><span class="sxs-lookup"><span data-stu-id="7610d-170">Leave Normalize blank.</span></span>
   - <span data-ttu-id="7610d-171">Iestatiet **Precizitātes līmeni**: **Pamatinformācija** un **Vērtību**: **Augsts**.</span><span class="sxs-lookup"><span data-stu-id="7610d-171">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   ![Apvienot nosaukuma un e-pasta ziņojuma saskaņošanas kārtulu.](media/unify-match-rule.png)

7. <span data-ttu-id="7610d-173">Atlasiet vienumu **Saglabāt** un **Palaist**.</span><span class="sxs-lookup"><span data-stu-id="7610d-173">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="7610d-174">Sapludināšana</span><span class="sxs-lookup"><span data-stu-id="7610d-174">Merge</span></span>

1. <span data-ttu-id="7610d-175">Ejiet uz cilni **Sapludināt**.</span><span class="sxs-lookup"><span data-stu-id="7610d-175">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="7610d-176">**ContactId** attiecībā uz **loyCustomers** entītiju mainiet parādāmo nosaukumu uz **ContactIdLOYALTY**, lai atšķirtu to no citiem uzņemtajiem ID.</span><span class="sxs-lookup"><span data-stu-id="7610d-176">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   ![pārdēvējiet contactid no lojalitātes ID.](media/unify-merge-contactid.png)

1. <span data-ttu-id="7610d-178">Atlasiet **Saglabāt** un **Palaist**, lai sāktu sapludināšanas procesu.</span><span class="sxs-lookup"><span data-stu-id="7610d-178">Select **Save** and **Run** to start the Merge Process.</span></span>

## <a name="task-3---configure-product-recommendation-prediction"></a><span data-ttu-id="7610d-179">3. uzdevums — konfigurējiet produktu ieteikumu prognozi</span><span class="sxs-lookup"><span data-stu-id="7610d-179">Task 3 - Configure product recommendation prediction</span></span>

<span data-ttu-id="7610d-180">Izmantojot vienoto klientu profilus, mēs tagad varam palaist abonēšanas zudumu prognozi.</span><span class="sxs-lookup"><span data-stu-id="7610d-180">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span>

1. <span data-ttu-id="7610d-181">Dodieties uz **Informācija** > **Prognoze**, izvēlieties **Produktu ieteikums**.</span><span class="sxs-lookup"><span data-stu-id="7610d-181">Go to **Intelligence** > **Prediction** choose **Product recommendation**.</span></span>

1. <span data-ttu-id="7610d-182">Atlasiet **Sākt darbu**.</span><span class="sxs-lookup"><span data-stu-id="7610d-182">Select **Get started**.</span></span>

1. <span data-ttu-id="7610d-183">Nosauciet modeļa **OOB produktu ieteikumu modeļa prognozi** un izvades entītiju **OOBProductRecommendationMoproductPrediction**.</span><span class="sxs-lookup"><span data-stu-id="7610d-183">Name the model **OOB Product Recommendation Model Prediction** and the output entity **OOBProductRecommendationModelPrediction**.</span></span>

1. <span data-ttu-id="7610d-184">Definējiet trīs modeļa nosacījumus:</span><span class="sxs-lookup"><span data-stu-id="7610d-184">Define three conditions for the model:</span></span>

   - <span data-ttu-id="7610d-185">**Produktu skaits**: iestatiet šo vērtību uz **5**.</span><span class="sxs-lookup"><span data-stu-id="7610d-185">**Number of products**: Set this value to **5**.</span></span> <span data-ttu-id="7610d-186">Šis iestatījums nosaka, cik daudz produktu klientiem vēlaties ieteikt.</span><span class="sxs-lookup"><span data-stu-id="7610d-186">This setting defines how many products you want to recommend to your customers.</span></span>

   - <span data-ttu-id="7610d-187">**Atkārtojiet paredzamos pirkumus**: atlasiet **Jā**, lai norādītu, ka vēlaties iekļaut produktus ieteikumā, ko klienti ir iegādājušies iepriekš.</span><span class="sxs-lookup"><span data-stu-id="7610d-187">**Repeat purchases expected**: Select **Yes** to indicate that you want to include products in the recommendation that your customers have purchased before.</span></span>

   - <span data-ttu-id="7610d-188">**Atskata logs**: atlasiet vismaz **365 dienas**.</span><span class="sxs-lookup"><span data-stu-id="7610d-188">**Look back window:** Select at least **365 days**.</span></span> <span data-ttu-id="7610d-189">Šis iestatījums nosaka, cik tālu modelis atskatīsies uz klienta darbībām, lai izmantotu tās kā ieteikumu ievadi.</span><span class="sxs-lookup"><span data-stu-id="7610d-189">This setting defines how far the model will look back at the customer's activity to use it as input to their recommendations.</span></span>
   
   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Modeļa preferences produktu ieteikumu modelim.":::

1. <span data-ttu-id="7610d-191">Atlasiet **Nepieciešamie dati** un atlasiet **Pievienot datus** pirkumu vēsturei.</span><span class="sxs-lookup"><span data-stu-id="7610d-191">Select **Required data** and select **Add data** for purchase history.</span></span>

1. <span data-ttu-id="7610d-192">Pievienojiet **eCommercePurchases : e-komercija** entītiju un kartējiet laukus no e-komercijas uz atbilstošiem modelī vajadzīgajiem laukiem.</span><span class="sxs-lookup"><span data-stu-id="7610d-192">Add the **eCommercePurchases : eCommerce** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="7610d-193">Apvienojiet **eCommercePurchases: e-komercijas** entītiju ar **ECommerceContacts: e-komerciju**.</span><span class="sxs-lookup"><span data-stu-id="7610d-193">Join the **eCommercePurchases : eCommerce** entity with **eCommerceContacts : eCommerce**.</span></span>

   ![Pievienojieties e-komercijas entītijām.](media/model-purchase-join.png)

1. <span data-ttu-id="7610d-195">Lai iestatītu modeļa grafiku, atlasiet **Tālāk**.</span><span class="sxs-lookup"><span data-stu-id="7610d-195">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="7610d-196">Modelis ir regulāri jāapmāca, lai apgūtu jaunus rakstus, kad tiek uzņemti jauni dati.</span><span class="sxs-lookup"><span data-stu-id="7610d-196">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="7610d-197">Šajā piemērā atlasiet **Reizi mēnesī**.</span><span class="sxs-lookup"><span data-stu-id="7610d-197">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="7610d-198">Pēc visas detalizētās informācijas pārskatīšanas atlasiet **Saglabāt un palaist**.</span><span class="sxs-lookup"><span data-stu-id="7610d-198">After reviewing all the details, select **Save and Run**.</span></span>


## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="7610d-199">4.uzdevums — pārskatīt modeļa rezultātus un paskaidrojumus</span><span class="sxs-lookup"><span data-stu-id="7610d-199">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="7610d-200">Ļaujiet modelim pabeigt datu apmācīšanu un skaitīšanu.</span><span class="sxs-lookup"><span data-stu-id="7610d-200">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="7610d-201">Tagad jūs varat pārskatīt produktu ieteikumu modeļa paskaidrojumus.</span><span class="sxs-lookup"><span data-stu-id="7610d-201">You can now review the product recommendation model explanations.</span></span> <span data-ttu-id="7610d-202">Papildinformāciju skatiet rakstā [Prognozes statusa un rezultātu pārskatīšana](predict-subscription-churn.md#review-a-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="7610d-202">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-purchased-products"></a><span data-ttu-id="7610d-203">5. uzdevums — izveidot augstas vērtības iegādātu produktu segmentu</span><span class="sxs-lookup"><span data-stu-id="7610d-203">Task 5 - Create a segment of high purchased products</span></span>

<span data-ttu-id="7610d-204">Palaižot ražošanas modeli, tiek izveidota jauna entītija, ko var redzēt vienumā **Dati** > **Entītijas**.</span><span class="sxs-lookup"><span data-stu-id="7610d-204">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>

<span data-ttu-id="7610d-205">Varat izveidot jaunu segmentu, par pamatu izmantojot modelī izveidotu entītiju.</span><span class="sxs-lookup"><span data-stu-id="7610d-205">You can create a new segment based on the entity created by the model.</span></span>

1. <span data-ttu-id="7610d-206">Ejiet uz **Segmenti**.</span><span class="sxs-lookup"><span data-stu-id="7610d-206">Go to **Segments**.</span></span> <span data-ttu-id="7610d-207">Atlasiet vienumu **Jauns** un izvēlieties **Izveidot no** > **Informācija**.</span><span class="sxs-lookup"><span data-stu-id="7610d-207">Select **New** and choose **Create from** > **Intelligence**.</span></span>

   ![Izveidot segmentu ar modeļa izvadi.](media/segment-intelligence.png)

1. <span data-ttu-id="7610d-209">Atlasiet **OOBProductRecommendationModelPrediction** galapunktu un definējiet segmentu:</span><span class="sxs-lookup"><span data-stu-id="7610d-209">Select the **OOBProductRecommendationModelPrediction** endpoint and define the segment:</span></span>

   - <span data-ttu-id="7610d-210">Lauks: ProductID</span><span class="sxs-lookup"><span data-stu-id="7610d-210">Field: ProductID</span></span>
   - <span data-ttu-id="7610d-211">Operators: Vērtība</span><span class="sxs-lookup"><span data-stu-id="7610d-211">Operator: Value</span></span>
   - <span data-ttu-id="7610d-212">Vērtība: atlasiet trīs populārāko produktu ID</span><span class="sxs-lookup"><span data-stu-id="7610d-212">Value: Select the top three product IDs</span></span>

   :::image type="content" source="media/product-recommendation-quick-segment.png" alt-text="Izveidojiet segmentu no modeļa rezultātiem.":::

<span data-ttu-id="7610d-214">Tagad jums ir dinamiski atjaunināts segments, kas identificē klientus, kuri ļoti vēlas iegādāties trīs visvairāk ieteiktos produktus</span><span class="sxs-lookup"><span data-stu-id="7610d-214">You now have a segment that is dynamically updated which identifies the customers who are more willing to purchase the three most recommended products</span></span> 

<span data-ttu-id="7610d-215">Papildinformācijai skatiet [Segmentu izveide un pārvaldība](segments.md).</span><span class="sxs-lookup"><span data-stu-id="7610d-215">For more information, see [Create and manage segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
