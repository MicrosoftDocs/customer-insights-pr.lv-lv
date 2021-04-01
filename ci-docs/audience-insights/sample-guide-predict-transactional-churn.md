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
ms.openlocfilehash: 251bc26246cee16952e8e4cb08e2ed7aa4d18488
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595435"
---
# <a name="transactional-churn-prediction-preview-sample-guide"></a><span data-ttu-id="827a1-103">Transakciju zudumu parauga prognozes parauga ceļvedis (priekšskatījums)</span><span class="sxs-lookup"><span data-stu-id="827a1-103">Transactional churn prediction (preview) sample guide</span></span>

<span data-ttu-id="827a1-104">Mēs jums paskaidrosim, kā izbeigt transakciju zudumu prognozi programmā Customer Insights, izmantojot tālāk sniegtos datus.</span><span class="sxs-lookup"><span data-stu-id="827a1-104">This guide will walk you through an end to end example of Transactional Churn prediction in Customer Insights using the data provided below.</span></span> <span data-ttu-id="827a1-105">Visi šajā rokasgrāmatā izmantotie dati nav īsti klientu dati, un tie ir daļa no Contoso datu kopas, kas ir atrodama vidē *Demo* jūsu Customer Insights abonementā.</span><span class="sxs-lookup"><span data-stu-id="827a1-105">All data used in this guide is not real customer data and is part of the Contoso dataset found in the *Demo* environment within your Customer Insights Subscription.</span></span>

## <a name="scenario"></a><span data-ttu-id="827a1-106">Scenārijs</span><span class="sxs-lookup"><span data-stu-id="827a1-106">Scenario</span></span>

<span data-ttu-id="827a1-107">Contoso ir uzņēmums, kas ražo kvalitatīvu kafiju un kafijas automātus, ko viņi pārdod, izmantojot savu Contoso Coffee mājaslapu.</span><span class="sxs-lookup"><span data-stu-id="827a1-107">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="827a1-108">To mērķis ir noskaidrot, kuri klienti, kas parasti iegādājas viņu produktus, pārtrauks aktivitāti nākamajās 60 dienās.</span><span class="sxs-lookup"><span data-stu-id="827a1-108">Their goal is to know which customers who typically purchase their products on a regular basis, will stop being active customers in the next 60 days.</span></span> <span data-ttu-id="827a1-109">Zinot, kurš no saviem klientiem varētu **zust**, var palīdzēt ietaupīt mārketinga pasākumus, koncentrējoties uz to saglabāšanu.</span><span class="sxs-lookup"><span data-stu-id="827a1-109">Knowing which of their customers is **likely to churn**, can help them save marketing efforts by focusing on keeping them.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="827a1-110">Priekšnosacījumi</span><span class="sxs-lookup"><span data-stu-id="827a1-110">Prerequisites</span></span>

- <span data-ttu-id="827a1-111">Vismaz [Līdzautora atļaujas](permissions.md) Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="827a1-111">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="827a1-112">Ieteicams ieviest tālāk norādītos soļus [jaunā vidē](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="827a1-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="827a1-113">1.uzdevums - Datu uzņemšana</span><span class="sxs-lookup"><span data-stu-id="827a1-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="827a1-114">Pārskatiet rakstus [par datu uzņemšanu](data-sources.md) un [datu avotu importēšanu, izmantojot](connect-power-query.md) tieši Power Query savienotājus.</span><span class="sxs-lookup"><span data-stu-id="827a1-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="827a1-115">Tālāk sniegtajā informācijā tiek pieņemts, ka esat iepazinies ar datu uzņemšanu kopumā.</span><span class="sxs-lookup"><span data-stu-id="827a1-115">The following information assumes you familiarized with ingesting data in general.</span></span> 

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="827a1-116">Uzņemt klientu datus no e-komercijas platformas</span><span class="sxs-lookup"><span data-stu-id="827a1-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="827a1-117">Izveidojiet datu avotu ar nosaukumu **e-komercija**, izvēlieties importēšanas opciju un atlasiet **Tekstu/CSV** savienotāju.</span><span class="sxs-lookup"><span data-stu-id="827a1-117">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="827a1-118">Ievadiet URL e-komercijas kontaktpersonām https://aka.ms/ciadclasscontacts.</span><span class="sxs-lookup"><span data-stu-id="827a1-118">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="827a1-119">Rediģējot datus, atlasiet **Pārveidot** un pēc tam **Izmantot pirmajā rindā kā galvenes**.</span><span class="sxs-lookup"><span data-stu-id="827a1-119">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="827a1-120">Atjauniniet tālāk uzskaitīto kolonnu datu tipu:</span><span class="sxs-lookup"><span data-stu-id="827a1-120">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="827a1-121">**DateOfBirth**: Datums</span><span class="sxs-lookup"><span data-stu-id="827a1-121">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="827a1-122">**CreatedOn**: Datums/Laiks/Josla</span><span class="sxs-lookup"><span data-stu-id="827a1-122">**CreatedOn**: Date/Time/Zone</span></span>

   [!div class="mx-imgBorder"]
   <span data-ttu-id="827a1-123">![Pārveidot DoB par Datumu](media/ecommerce-dob-date.PNG "Pārveido dzimšanas datumu uz datumu")</span><span class="sxs-lookup"><span data-stu-id="827a1-123">![Transform DoB to Date](media/ecommerce-dob-date.PNG "transform date of birth to date")</span></span>

1. <span data-ttu-id="827a1-124">Labās puses rūts laukā **Nosaukums** pārdēvējiet savu datu avotu no **Vaicājuma** uz **eCommerceContacts**</span><span class="sxs-lookup"><span data-stu-id="827a1-124">In the **Name** field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="827a1-125">Saglabājiet datu avotu.</span><span class="sxs-lookup"><span data-stu-id="827a1-125">Save the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="827a1-126">Tiešsaistes pirkuma datu uzņemšana</span><span class="sxs-lookup"><span data-stu-id="827a1-126">Ingest online purchase data</span></span>

1. <span data-ttu-id="827a1-127">Pievienojiet citas datu kopas tiem pašiem **e-komercijas** datu avotiem.</span><span class="sxs-lookup"><span data-stu-id="827a1-127">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="827a1-128">Vēlreiz izvēlieties **Tekstu/CSV** savienotāju.</span><span class="sxs-lookup"><span data-stu-id="827a1-128">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="827a1-129">Ievadiet **Tiešsaistes pirkumu** datu URL https://aka.ms/ciadclassonline.</span><span class="sxs-lookup"><span data-stu-id="827a1-129">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="827a1-130">Rediģējot datus, atlasiet **Pārveidot** un pēc tam **Izmantot pirmajā rindā kā galvenes**.</span><span class="sxs-lookup"><span data-stu-id="827a1-130">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="827a1-131">Atjauniniet tālāk uzskaitīto kolonnu datu tipu:</span><span class="sxs-lookup"><span data-stu-id="827a1-131">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="827a1-132">**PurchasedOn**: Datums/Laiks</span><span class="sxs-lookup"><span data-stu-id="827a1-132">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="827a1-133">**TotalPrice**: Valūta</span><span class="sxs-lookup"><span data-stu-id="827a1-133">**TotalPrice**: Currency</span></span>
   
1. <span data-ttu-id="827a1-134">Labās puses rūts laukā **Nosaukums** pārdēvējiet savu datu avotu no **Vaicājuma** uz **eCommercePurchases**.</span><span class="sxs-lookup"><span data-stu-id="827a1-134">In the **Name** field on the right-hand pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="827a1-135">Saglabājiet datu avotu.</span><span class="sxs-lookup"><span data-stu-id="827a1-135">Save the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="827a1-136">Klienta datu uzņemšana no lojalitātes shēmas</span><span class="sxs-lookup"><span data-stu-id="827a1-136">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="827a1-137">Izveidojiet datu avotu ar nosaukumu **LoyaltyScheme**, izvēlieties importēšanas opciju un atlasiet **Tekstu/CSV** savienotāju.</span><span class="sxs-lookup"><span data-stu-id="827a1-137">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="827a1-138">Ievadiet URL e-komercijas kontaktpersonām https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="827a1-138">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="827a1-139">Rediģējot datus, atlasiet **Pārveidot** un pēc tam **Izmantot pirmajā rindā kā galvenes**.</span><span class="sxs-lookup"><span data-stu-id="827a1-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="827a1-140">Atjauniniet tālāk uzskaitīto kolonnu datu tipu:</span><span class="sxs-lookup"><span data-stu-id="827a1-140">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="827a1-141">**DateOfBirth**: Datums</span><span class="sxs-lookup"><span data-stu-id="827a1-141">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="827a1-142">**RewardsPoints**: Vesels skaitlis</span><span class="sxs-lookup"><span data-stu-id="827a1-142">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="827a1-143">**CreatedOn**: Datums/Laiks</span><span class="sxs-lookup"><span data-stu-id="827a1-143">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="827a1-144">Labās puses rūts laukā **Nosaukums** pārdēvējiet savu datu avotu no **Vaicājuma** uz **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="827a1-144">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="827a1-145">Saglabājiet datu avotu.</span><span class="sxs-lookup"><span data-stu-id="827a1-145">Save the data source.</span></span>


## <a name="task-2---data-unification"></a><span data-ttu-id="827a1-146">2.uzdevums — Datu apvienošana</span><span class="sxs-lookup"><span data-stu-id="827a1-146">Task 2 - Data unification</span></span>

<span data-ttu-id="827a1-147">Pēc datu uzņemšanas mēs tagad sākam **Kartēt, saskaņot un sapludināt** procesu, lai izveidotu vienotu klientu profilu.</span><span class="sxs-lookup"><span data-stu-id="827a1-147">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="827a1-148">Papildinformāciju skatiet tēmā [Datu apvienošana](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="827a1-148">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="827a1-149">Kartēt</span><span class="sxs-lookup"><span data-stu-id="827a1-149">Map</span></span>

1. <span data-ttu-id="827a1-150">Pēc datu uzņemšanas kartējiet kontaktpersonas no e-komercijas un lojalitātes datiem līdz vispārējiem datu tipiem.</span><span class="sxs-lookup"><span data-stu-id="827a1-150">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="827a1-151">Ejiet uz **Dati** > **Apvienot** > **Kartēt**.</span><span class="sxs-lookup"><span data-stu-id="827a1-151">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="827a1-152">Atlasiet entītijas, kas pārstāv klienta profilu — **eCommerceContacts** un **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="827a1-152">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="apvienot e-komercijas un lojalitātes datu avotus.":::

1. <span data-ttu-id="827a1-154">Atlasiet **ContactId** kā primāro atslēgu **eCommerceContacts** un **LoyaltyID** kā **loyCustomers** primāro atslēgu.</span><span class="sxs-lookup"><span data-stu-id="827a1-154">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="Apvienot LoyaltyId kā primāro atslēgu.":::

### <a name="match"></a><span data-ttu-id="827a1-156">Saskaņot</span><span class="sxs-lookup"><span data-stu-id="827a1-156">Match</span></span>

1. <span data-ttu-id="827a1-157">Dodieties uz cilni **Saskaņot** un atlasiet **Iestatīt secību**.</span><span class="sxs-lookup"><span data-stu-id="827a1-157">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="827a1-158">**Primārajā** nolaižamajā sarakstā izvēlieties **eCommerceContacts : e-komercijas** kā primāro avotu un iekļaujiet visus ierakstus.</span><span class="sxs-lookup"><span data-stu-id="827a1-158">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="827a1-159">Nolaižamajā sarakstā **2.entītija** izvēlieties **loyCustomers: LoyaltyScheme** un iekļaujiet visus ierakstus.</span><span class="sxs-lookup"><span data-stu-id="827a1-159">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   :::image type="content" source="media/unify-match-order.PNG" alt-text="Apvienot e-komercijas un lojalitātes atbilstības.":::

1. <span data-ttu-id="827a1-161">Atlasiet **Jaunas kārtulas izveide**</span><span class="sxs-lookup"><span data-stu-id="827a1-161">Select **Create a new rule**</span></span>

1. <span data-ttu-id="827a1-162">Pievienojiet pirmo nosacījumu, izmantojot FullName.</span><span class="sxs-lookup"><span data-stu-id="827a1-162">Add your first condition using FullName.</span></span>

   * <span data-ttu-id="827a1-163">Nolaižamajā sarakstā atlasiet **FullName** eCommerceContacts.</span><span class="sxs-lookup"><span data-stu-id="827a1-163">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="827a1-164">Nolaižamajā sarakstā atlasiet **FullName** loyCustomers.</span><span class="sxs-lookup"><span data-stu-id="827a1-164">For loyCustomers select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="827a1-165">Atlasiet opciju **Normalizēt** nolaižamo sarakstu un izvēlieties **tipu (tālrunis, nosaukums, adrese,...)**.</span><span class="sxs-lookup"><span data-stu-id="827a1-165">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   * <span data-ttu-id="827a1-166">Iestatiet **Precizitātes līmeni**: **Pamatinformācija** un **Vērtību**: **Augsts**.</span><span class="sxs-lookup"><span data-stu-id="827a1-166">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="827a1-167">Ievadiet jaunās kārtulas nosaukumu **FullName, e-pasts**.</span><span class="sxs-lookup"><span data-stu-id="827a1-167">Enter the name **FullName, Email** for the new rule.</span></span>

   * <span data-ttu-id="827a1-168">Pievienojiet e-pasta adresei otru nosacījumu, atlasot **Pievienot nosacījumu**</span><span class="sxs-lookup"><span data-stu-id="827a1-168">Add a second condition for email address by selecting **Add Condition**</span></span>
   * <span data-ttu-id="827a1-169">Entītijas eCommerceContacts izvēlieties nolaižamajā izvēlnē vienumu **E-pasts**.</span><span class="sxs-lookup"><span data-stu-id="827a1-169">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   * <span data-ttu-id="827a1-170">Entītijai loyCustomers izvēlieties nolaižamajā izvēlnē vienumu **E-pasts**.</span><span class="sxs-lookup"><span data-stu-id="827a1-170">For entity loyCustomers, choose **EMail** in the drop-down.</span></span> 
   * <span data-ttu-id="827a1-171">Atstājiet normalizāciju tukšu.</span><span class="sxs-lookup"><span data-stu-id="827a1-171">Leave Normalize blank.</span></span> 
   * <span data-ttu-id="827a1-172">Iestatiet **Precizitātes līmeni**: **Pamatinformācija** un **Vērtību**: **Augsts**.</span><span class="sxs-lookup"><span data-stu-id="827a1-172">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="Apvienot nosaukuma un e-pasta ziņojuma saskaņošanas kārtulu.":::

7. <span data-ttu-id="827a1-174">Atlasiet vienumu **Saglabāt** un **Palaist**.</span><span class="sxs-lookup"><span data-stu-id="827a1-174">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="827a1-175">Sapludināšana</span><span class="sxs-lookup"><span data-stu-id="827a1-175">Merge</span></span>

1. <span data-ttu-id="827a1-176">Ejiet uz cilni **Sapludināt**.</span><span class="sxs-lookup"><span data-stu-id="827a1-176">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="827a1-177">**ContactId** attiecībā uz **loyCustomers** entītiju mainiet parādāmo nosaukumu uz **ContactIdLOYALTY**, lai atšķirtu to no citiem uzņemtajiem ID.</span><span class="sxs-lookup"><span data-stu-id="827a1-177">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="pārdēvējiet contactid no lojalitātes ID.":::

1. <span data-ttu-id="827a1-179">Atlasiet **Saglabāt** un **Palaist**, lai sāktu sapludināšanas procesu.</span><span class="sxs-lookup"><span data-stu-id="827a1-179">Select **Save** and **Run** to start the Merge Process.</span></span>



## <a name="task-3---configure-transaction-churn-prediction"></a><span data-ttu-id="827a1-180">3.uzdevums — konfigurēt transakciju zudumu prognozi</span><span class="sxs-lookup"><span data-stu-id="827a1-180">Task 3 - Configure transaction churn prediction</span></span>

<span data-ttu-id="827a1-181">Izmantojot vienoto klientu profilus, mēs tagad varam palaist abonēšanas zudumu prognozi.</span><span class="sxs-lookup"><span data-stu-id="827a1-181">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span> <span data-ttu-id="827a1-182">Detalizētas darbības skatiet rakstu [Abonementa zudumu prognoze (priekšskatījums)](predict-subscription-churn.md).</span><span class="sxs-lookup"><span data-stu-id="827a1-182">For detailed steps, see the [Subscription churn prediction (preview)](predict-subscription-churn.md) article.</span></span> 

1. <span data-ttu-id="827a1-183">Atveriet **Informācija** > **Atklāt** un atlasiet, lai izmantotu **Klientu zudumu modeli**.</span><span class="sxs-lookup"><span data-stu-id="827a1-183">Go to **Intelligence** > **Discover** and select to use the **Customer churn model**.</span></span>

1. <span data-ttu-id="827a1-184">Atlasiet opciju **Abonēšana** un atlasiet **Sākt darbu**.</span><span class="sxs-lookup"><span data-stu-id="827a1-184">Select the **Transactional** option and select **Get started**.</span></span>

1. <span data-ttu-id="827a1-185">Nosauciet modeli **OOB Abonementu zudumu prognoze** un izvades entītiju **OOBSubscriptionChurnPrediction**.</span><span class="sxs-lookup"><span data-stu-id="827a1-185">Name the model **OOB eCommerce Transaction Churn Prediction** and the output entity **OOBeCommerceChurnPrediction**.</span></span>

1. <span data-ttu-id="827a1-186">Definējiet divus zuduma modeļa nosacījumus:</span><span class="sxs-lookup"><span data-stu-id="827a1-186">Define two conditions for the churn model:</span></span>

   * <span data-ttu-id="827a1-187">**Prognozes logs**: **vismaz 60** dienas.</span><span class="sxs-lookup"><span data-stu-id="827a1-187">**Prediction window**: **at least 60** days.</span></span> <span data-ttu-id="827a1-188">Šis iestatījums nosaka, cik tālā nākotnē mēs vēlamies prognozēt klientu zudumu.</span><span class="sxs-lookup"><span data-stu-id="827a1-188">This setting defines how far into the future do we want to predict customer churn.</span></span>

   * <span data-ttu-id="827a1-189">**Zuduma definīcija**: **vismaz 60** dienas.</span><span class="sxs-lookup"><span data-stu-id="827a1-189">**Churn definition**: **at least 60** days.</span></span> <span data-ttu-id="827a1-190">Ilgums bez pirkuma, pēc kura klients tiek uzskatīts par zudušu.</span><span class="sxs-lookup"><span data-stu-id="827a1-190">The duration without purchase after which a customer is considered churned.</span></span>

     :::image type="content" source="media/model-levers.PNG" alt-text="Atlasiet modeļa sviras Prognozes logs un Zuduma definīcija.":::

1. <span data-ttu-id="827a1-192">Atlasiet **Pirkuma vēsturi (obligāti)** un atlasiet **Pievienot datus** pirkumu vēsturei.</span><span class="sxs-lookup"><span data-stu-id="827a1-192">Select **Purchase History (required)** and select **Add data** for purchase history.</span></span>

1. <span data-ttu-id="827a1-193">Pievienojiet **eCommercePurchases : e-komercija** entītiju un kartējiet laukus no e-komercijas uz atbilstošiem modelī vajadzīgajiem laukiem.</span><span class="sxs-lookup"><span data-stu-id="827a1-193">Add the **eCommercePurchases : eCommerce** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="827a1-194">Apvienojiet **eCommercePurchases: e-komercijas** entītiju ar **ECommerceContacts: e-komerciju**.</span><span class="sxs-lookup"><span data-stu-id="827a1-194">Join the **eCommercePurchases : eCommerce** entity with **eCommerceContacts : eCommerce**.</span></span>

   :::image type="content" source="media/model-purchase-join.PNG" alt-text="Pievienojieties e-komercijas entītijām.":::

1. <span data-ttu-id="827a1-196">Lai iestatītu modeļa grafiku, atlasiet **Tālāk**.</span><span class="sxs-lookup"><span data-stu-id="827a1-196">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="827a1-197">Modelis ir regulāri jāapmāca, lai apgūtu jaunus rakstus, kad tiek uzņemti jauni dati.</span><span class="sxs-lookup"><span data-stu-id="827a1-197">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="827a1-198">Šajā piemērā atlasiet **Reizi mēnesī**.</span><span class="sxs-lookup"><span data-stu-id="827a1-198">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="827a1-199">Pēc visas detalizētās informācijas pārskatīšanas atlasiet **Saglabāt un palaist**.</span><span class="sxs-lookup"><span data-stu-id="827a1-199">After reviewing all the details, select **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="827a1-200">4.uzdevums — pārskatīt modeļa rezultātus un paskaidrojumus</span><span class="sxs-lookup"><span data-stu-id="827a1-200">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="827a1-201">Ļaujiet modelim pabeigt datu apmācīšanu un skaitīšanu.</span><span class="sxs-lookup"><span data-stu-id="827a1-201">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="827a1-202">Tagad jūs varat pārskatīt abonēšanas zudumu modeļa paskaidrojumus.</span><span class="sxs-lookup"><span data-stu-id="827a1-202">You can now review the subscription churn model explanations.</span></span> <span data-ttu-id="827a1-203">Papildinformāciju skatiet rakstā [Prognozes statusa un rezultātu pārskatīšana](predict-subscription-churn.md#review-a-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="827a1-203">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a><span data-ttu-id="827a1-204">5.uzdevums — Izveidot augsta zudumu riska klientu segmentu</span><span class="sxs-lookup"><span data-stu-id="827a1-204">Task 5 - Create a segment of high churn-risk customers</span></span>

<span data-ttu-id="827a1-205">Palaižot ražošanas modeli, tiek izveidota jauna entītija, ko var redzēt vienumā **Dati** > **Entītijas**.</span><span class="sxs-lookup"><span data-stu-id="827a1-205">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>   

<span data-ttu-id="827a1-206">Varat izveidot jaunu segmentu, par pamatu izmantojot modelī izveidotu entītiju.</span><span class="sxs-lookup"><span data-stu-id="827a1-206">You can create a new segment based on the entity created by the model.</span></span>

1.  <span data-ttu-id="827a1-207">Ejiet uz **Segmenti**.</span><span class="sxs-lookup"><span data-stu-id="827a1-207">Go to **Segments**.</span></span> <span data-ttu-id="827a1-208">Atlasiet vienumu **Jauns** un izvēlieties **Izveidot no** > **Informācija**.</span><span class="sxs-lookup"><span data-stu-id="827a1-208">Select **New** and choose **Create from** > **Intelligence**.</span></span> 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Izveidot segmentu ar modeļa izvadi.":::

1. <span data-ttu-id="827a1-210">Atlasiet **OOBSubscriptionChurnPrediction** galapunktu un definējiet segmentu:</span><span class="sxs-lookup"><span data-stu-id="827a1-210">Select the **OOBSubscriptionChurnPrediction** endpoint and define the segment:</span></span> 
   - <span data-ttu-id="827a1-211">Lauks: ChurnScore</span><span class="sxs-lookup"><span data-stu-id="827a1-211">Field: ChurnScore</span></span>
   - <span data-ttu-id="827a1-212">Operators: ir lielāks nekā</span><span class="sxs-lookup"><span data-stu-id="827a1-212">Operator: greater than</span></span>
   - <span data-ttu-id="827a1-213">Vērtība: 0.6</span><span class="sxs-lookup"><span data-stu-id="827a1-213">Value: 0.6</span></span>
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="Iestatiet abonementu zudumu segmentu.":::

<span data-ttu-id="827a1-215">Tagad jums ir segments, kas tiek dinamiski atjaunināts, kas identificē šā abonēšanas uzņēmuma augsta zudumu riska klientus.</span><span class="sxs-lookup"><span data-stu-id="827a1-215">You now have a segment that is dynamically updated which identifies high churn-risk customers for this subscription business.</span></span>

<span data-ttu-id="827a1-216">Papildinformācijai skatiet [Segmentu izveide un pārvaldība](segments.md).</span><span class="sxs-lookup"><span data-stu-id="827a1-216">For more information, see [Create and manage segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]