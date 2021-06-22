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
ms.openlocfilehash: 73d294a285b4ad706bec7fe925c1daa0b839ddd6
ms.sourcegitcommit: 7b6189e47ed1f87e7ce35d40e4cf7a6730f31ef2
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 06/01/2021
ms.locfileid: "6129954"
---
# <a name="customer-lifetime-value-clv-prediction-sample-guide"></a><span data-ttu-id="5e39d-103">Debitora darbmūža prognozes (CLV) parauga rokasgrāmata</span><span class="sxs-lookup"><span data-stu-id="5e39d-103">Customer lifetime value (CLV) prediction sample guide</span></span>

<span data-ttu-id="5e39d-104">Šajā rokasgrāmatā jums tiks izskaidrots klienta mūža vērtības (CLV) pilna piemēra prognoze, izmantojot datu paraugus programmā Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="5e39d-104">This guide will walk you through an end to end example of Customer lifetime value (CLV) prediction in Customer Insights using sample data.</span></span>

## <a name="scenario"></a><span data-ttu-id="5e39d-105">Scenārijs</span><span class="sxs-lookup"><span data-stu-id="5e39d-105">Scenario</span></span>

<span data-ttu-id="5e39d-106">Contoso ir uzņēmums, kas ražo augstas kvalitātes kafijas un kafijas automātus.</span><span class="sxs-lookup"><span data-stu-id="5e39d-106">Contoso is a company that produces high-quality coffee and coffee machines.</span></span> <span data-ttu-id="5e39d-107">Viņi pārdod produktus, izmantojot savu Contoso Coffee vietni.</span><span class="sxs-lookup"><span data-stu-id="5e39d-107">They sell the products through their Contoso Coffee website.</span></span> <span data-ttu-id="5e39d-108">Uzņēmums vēlas saprast vērtību (ieņēmumus), ko viņu klienti var radīt nākamo 12 mēnešu laikā.</span><span class="sxs-lookup"><span data-stu-id="5e39d-108">The company wants to understand the value (revenue) that their customers can generate in the next 12 months.</span></span> <span data-ttu-id="5e39d-109">Zinot savu klientu paredzamo vērtību nākamajos 12 mēnešos, viņi varēs virzīt savus mārketinga centienus uz augstvērtības klientiem.</span><span class="sxs-lookup"><span data-stu-id="5e39d-109">Knowing the expected value of their customers in the next 12 months will help them steer their marketing efforts on high value customers.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5e39d-110">Priekšnosacījumi</span><span class="sxs-lookup"><span data-stu-id="5e39d-110">Prerequisites</span></span>

- <span data-ttu-id="5e39d-111">Vismaz [līdzstrādnieka atļaujas](permissions.md) Audience Insights.</span><span class="sxs-lookup"><span data-stu-id="5e39d-111">At least [Contributor permissions](permissions.md) in audience insights.</span></span>
- <span data-ttu-id="5e39d-112">Ieteicams ieviest tālāk norādītos soļus [jaunā vidē](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="5e39d-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="5e39d-113">1.uzdevums - Datu uzņemšana</span><span class="sxs-lookup"><span data-stu-id="5e39d-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="5e39d-114">Pārskatiet rakstus [par datu ietveršanu](data-sources.md) un [datu avotu importēšanu, izmantojot Power Query savienotājus](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="5e39d-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md).</span></span> <span data-ttu-id="5e39d-115">Tālāk sniegtajā informācijā tiek pieņemts, ka esat iepazinies ar datu uzņemšanu kopumā.</span><span class="sxs-lookup"><span data-stu-id="5e39d-115">The following information assumes you familiarized with ingesting data in general.</span></span>

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="5e39d-116">Uzņemt klientu datus no e-komercijas platformas</span><span class="sxs-lookup"><span data-stu-id="5e39d-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="5e39d-117">Izveidojiet datu avotu ar nosaukumu **eCommerce**, izvēlieties importēšanas opciju un atlasiet **Teksta/CSV** savienotāju.</span><span class="sxs-lookup"><span data-stu-id="5e39d-117">Create a data source named  **eCommerce** , choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="5e39d-118">Ievadiet URL eCommerce kontaktpersonām [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).</span><span class="sxs-lookup"><span data-stu-id="5e39d-118">Enter the URL for eCommerce contacts [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).</span></span>

1. <span data-ttu-id="5e39d-119">Rediģējot datus, atlasiet  **Pārveidot**  un pēc tam  **Izmantot pirmajā rindā kā galvenes**.</span><span class="sxs-lookup"><span data-stu-id="5e39d-119">While editing the data, select  **Transform**  and then  **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="5e39d-120">Atjauniniet tālāk uzskaitīto kolonnu datu tipu:</span><span class="sxs-lookup"><span data-stu-id="5e39d-120">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="5e39d-121">**DateOfBirth**: Datums</span><span class="sxs-lookup"><span data-stu-id="5e39d-121">**DateOfBirth** : Date</span></span>
   - <span data-ttu-id="5e39d-122">**CreatedOn**: Datums/Laiks/Josla</span><span class="sxs-lookup"><span data-stu-id="5e39d-122">**CreatedOn** : Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Pārveidojiet dzimšanas datumu uz datumu.":::

1. <span data-ttu-id="5e39d-124">Labās puses rūts laukā "Nosaukums" pārdēvējiet savu datu avotu no **Vaicājuma** uz **eCommerceContacts**</span><span class="sxs-lookup"><span data-stu-id="5e39d-124">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="5e39d-125">**Saglabājiet** datu avotu.</span><span class="sxs-lookup"><span data-stu-id="5e39d-125">**Save** the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="5e39d-126">Tiešsaistes pirkuma datu uzņemšana</span><span class="sxs-lookup"><span data-stu-id="5e39d-126">Ingest online purchase data</span></span>

1. <span data-ttu-id="5e39d-127">Pievienojiet citas datu kopas tiem pašiem **e-komercijas** datu avotiem.</span><span class="sxs-lookup"><span data-stu-id="5e39d-127">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="5e39d-128">Vēlreiz izvēlieties **Tekstu/CSV** savienotāju.</span><span class="sxs-lookup"><span data-stu-id="5e39d-128">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="5e39d-129">Ievadiet **Tiešsaistes pirkumu** datu URL https://aka.ms/ciadclassonline.</span><span class="sxs-lookup"><span data-stu-id="5e39d-129">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="5e39d-130">Rediģējot datus, atlasiet **Pārveidot** un pēc tam **Izmantot pirmajā rindā kā galvenes**.</span><span class="sxs-lookup"><span data-stu-id="5e39d-130">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="5e39d-131">Atjauniniet tālāk uzskaitīto kolonnu datu tipu:</span><span class="sxs-lookup"><span data-stu-id="5e39d-131">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="5e39d-132">**PurchasedOn**: Datums/Laiks</span><span class="sxs-lookup"><span data-stu-id="5e39d-132">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="5e39d-133">**TotalPrice**: Valūta</span><span class="sxs-lookup"><span data-stu-id="5e39d-133">**TotalPrice**: Currency</span></span>

1. <span data-ttu-id="5e39d-134">Labās puses rūts laukā **Nosaukums** pārdēvējiet savu datu avotu no **Vaicājuma** uz **eCommercePurchases**.</span><span class="sxs-lookup"><span data-stu-id="5e39d-134">In the **Name** field on the side pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="5e39d-135">**Saglabājiet** datu avotu.</span><span class="sxs-lookup"><span data-stu-id="5e39d-135">**Save** the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="5e39d-136">Klienta datu uzņemšana no lojalitātes shēmas</span><span class="sxs-lookup"><span data-stu-id="5e39d-136">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="5e39d-137">Izveidojiet datu avotu ar nosaukumu **LoyaltyScheme**, izvēlieties importēšanas opciju un atlasiet **Tekstu/CSV** savienotāju.</span><span class="sxs-lookup"><span data-stu-id="5e39d-137">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="5e39d-138">Ievadiet URL e-komercijas kontaktpersonām https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="5e39d-138">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="5e39d-139">Rediģējot datus, atlasiet **Pārveidot** un pēc tam **Izmantot pirmajā rindā kā galvenes**.</span><span class="sxs-lookup"><span data-stu-id="5e39d-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="5e39d-140">Atjauniniet tālāk uzskaitīto kolonnu datu tipu:</span><span class="sxs-lookup"><span data-stu-id="5e39d-140">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="5e39d-141">**DateOfBirth**: Datums</span><span class="sxs-lookup"><span data-stu-id="5e39d-141">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="5e39d-142">**RewardsPoints**: Vesels skaitlis</span><span class="sxs-lookup"><span data-stu-id="5e39d-142">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="5e39d-143">**CreatedOn**: Datums/Laiks</span><span class="sxs-lookup"><span data-stu-id="5e39d-143">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="5e39d-144">Labās puses rūts laukā **Nosaukums** pārdēvējiet savu datu avotu no **Vaicājuma** uz **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="5e39d-144">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="5e39d-145">**Saglabājiet** datu avotu.</span><span class="sxs-lookup"><span data-stu-id="5e39d-145">**Save** the data source.</span></span>

### <a name="ingest-customer-data-from-website-reviews"></a><span data-ttu-id="5e39d-146">Klientu datu uzņemšana no tīmekļa pārskatiem</span><span class="sxs-lookup"><span data-stu-id="5e39d-146">Ingest customer data from website reviews</span></span>

1. <span data-ttu-id="5e39d-147">Izveidojiet datu avotu ar nosaukumu **e-komercija**, izvēlieties importēšanas opciju un atlasiet **Tekstu/CSV** savienotāju.</span><span class="sxs-lookup"><span data-stu-id="5e39d-147">Create a data source named **Website**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="5e39d-148">Ievadiet URL e-komercijas kontaktpersonām https://aka.ms/CI-ILT/WebReviews.</span><span class="sxs-lookup"><span data-stu-id="5e39d-148">Enter the URL for eCommerce contacts https://aka.ms/CI-ILT/WebReviews.</span></span>

1. <span data-ttu-id="5e39d-149">Rediģējot datus, atlasiet **Pārveidot** un pēc tam **Izmantot pirmajā rindā kā galvenes**.</span><span class="sxs-lookup"><span data-stu-id="5e39d-149">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="5e39d-150">Atjauniniet tālāk uzskaitīto kolonnu datu tipu:</span><span class="sxs-lookup"><span data-stu-id="5e39d-150">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="5e39d-151">**ReviewRating**: decimāldaļskaitlis</span><span class="sxs-lookup"><span data-stu-id="5e39d-151">**ReviewRating**: Decimal number</span></span>
   - <span data-ttu-id="5e39d-152">**ReviewDate**: Datums</span><span class="sxs-lookup"><span data-stu-id="5e39d-152">**ReviewDate**: Date</span></span>

1. <span data-ttu-id="5e39d-153">Labās puses rūts laukā Nosaukums pārdēvējiet savu datu avotu no **Vaicājumi** uz **Pārskati**.</span><span class="sxs-lookup"><span data-stu-id="5e39d-153">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **Reviews**.</span></span>

1. <span data-ttu-id="5e39d-154">**Saglabājiet** datu avotu.</span><span class="sxs-lookup"><span data-stu-id="5e39d-154">**Save** the data source.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="5e39d-155">2.uzdevums — Datu apvienošana</span><span class="sxs-lookup"><span data-stu-id="5e39d-155">Task 2 - Data unification</span></span>

<span data-ttu-id="5e39d-156">Pēc datu ietveršanas mēs sākam datu apvienošanas procesu, lai izveidotu vienotu klientu profilu.</span><span class="sxs-lookup"><span data-stu-id="5e39d-156">After ingesting the data, we now begin the data unification process to create a unified customer profile.</span></span> <span data-ttu-id="5e39d-157">Papildinformāciju skatiet tēmā [Datu apvienošana](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="5e39d-157">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="5e39d-158">Kartēt</span><span class="sxs-lookup"><span data-stu-id="5e39d-158">Map</span></span>

1. <span data-ttu-id="5e39d-159">Pēc datu uzņemšanas kartējiet kontaktpersonas no e-komercijas un lojalitātes datiem līdz vispārējiem datu tipiem.</span><span class="sxs-lookup"><span data-stu-id="5e39d-159">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="5e39d-160">Ejiet uz **Dati** > **Apvienot** > **Kartēt**.</span><span class="sxs-lookup"><span data-stu-id="5e39d-160">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="5e39d-161">Atlasiet entītijas, kas pārstāv klienta profilu — **eCommerceContacts** un **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="5e39d-161">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> <span data-ttu-id="5e39d-162">Atlasiet vienumu **Piemērot**.</span><span class="sxs-lookup"><span data-stu-id="5e39d-162">Then, select **Apply**.</span></span>

   ![apvienot e-komercijas un lojalitātes datu avotus.](media/unify-ecommerce-loyalty.png)

1. <span data-ttu-id="5e39d-164">Atlasiet **ContactId** kā primāro atslēgu **eCommerceContacts** un **LoyaltyID** kā **loyCustomers** primāro atslēgu.</span><span class="sxs-lookup"><span data-stu-id="5e39d-164">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   ![Apvienot LoyaltyId kā primāro atslēgu.](media/unify-loyaltyid.png)

1. <span data-ttu-id="5e39d-166">Atlasiet vienumu **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="5e39d-166">Select **Save**.</span></span>

### <a name="match"></a><span data-ttu-id="5e39d-167">Saskaņot</span><span class="sxs-lookup"><span data-stu-id="5e39d-167">Match</span></span>

1. <span data-ttu-id="5e39d-168">Dodieties uz cilni **Saskaņot** un atlasiet **Iestatīt secību**.</span><span class="sxs-lookup"><span data-stu-id="5e39d-168">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="5e39d-169">**Primārajā** nolaižamajā sarakstā izvēlieties **eCommerceContacts : e-komercijas** kā primāro avotu un iekļaujiet visus ierakstus.</span><span class="sxs-lookup"><span data-stu-id="5e39d-169">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="5e39d-170">Nolaižamajā sarakstā **2.entītija** izvēlieties **loyCustomers: LoyaltyScheme** un iekļaujiet visus ierakstus.</span><span class="sxs-lookup"><span data-stu-id="5e39d-170">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   ![Apvienot e-komercijas un lojalitātes atbilstības.](media/unify-match-order.png)

1. <span data-ttu-id="5e39d-172">Atlasiet **Pievienot kārtulu**</span><span class="sxs-lookup"><span data-stu-id="5e39d-172">Select **Add rule**</span></span>

1. <span data-ttu-id="5e39d-173">Pievienojiet pirmo nosacījumu, izmantojot FullName.</span><span class="sxs-lookup"><span data-stu-id="5e39d-173">Add your first condition using FullName.</span></span>

   - <span data-ttu-id="5e39d-174">Nolaižamajā sarakstā atlasiet **FullName** eCommerceContacts.</span><span class="sxs-lookup"><span data-stu-id="5e39d-174">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="5e39d-175">Nolaižamajā sarakstā atlasiet **FullName** loyCustomers.</span><span class="sxs-lookup"><span data-stu-id="5e39d-175">For loyCustomers select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="5e39d-176">Atlasiet opciju **Normalizēt** nolaižamo sarakstu un izvēlieties **Tipu (tālrunis, nosaukums, adrese,...)**.</span><span class="sxs-lookup"><span data-stu-id="5e39d-176">Select the **Normalize** drop-down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   - <span data-ttu-id="5e39d-177">Iestatiet **Precizitātes līmeni**: **Pamatinformācija** un **Vērtību**: **Augsts**.</span><span class="sxs-lookup"><span data-stu-id="5e39d-177">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="5e39d-178">Ievadiet jaunās kārtulas nosaukumu **FullName, e-pasts**.</span><span class="sxs-lookup"><span data-stu-id="5e39d-178">Enter the name **FullName, Email** for the new rule.</span></span>

   - <span data-ttu-id="5e39d-179">Pievienojiet e-pasta adresei otru nosacījumu, atlasot **Pievienot nosacījumu**</span><span class="sxs-lookup"><span data-stu-id="5e39d-179">Add a second condition for email address by selecting **Add Condition**</span></span>
   - <span data-ttu-id="5e39d-180">Entītijas eCommerceContacts izvēlieties nolaižamajā izvēlnē vienumu **E-pasts**.</span><span class="sxs-lookup"><span data-stu-id="5e39d-180">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   - <span data-ttu-id="5e39d-181">Entītijai loyCustomers izvēlieties nolaižamajā izvēlnē vienumu **E-pasts**.</span><span class="sxs-lookup"><span data-stu-id="5e39d-181">For entity loyCustomers, choose **EMail** in the drop-down.</span></span>
   - <span data-ttu-id="5e39d-182">Atstājiet normalizāciju tukšu.</span><span class="sxs-lookup"><span data-stu-id="5e39d-182">Leave Normalize blank.</span></span>
   - <span data-ttu-id="5e39d-183">Iestatiet **Precizitātes līmeni**: **Pamatinformācija** un **Vērtību**: **Augsts**.</span><span class="sxs-lookup"><span data-stu-id="5e39d-183">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   ![Apvienot nosaukuma un e-pasta ziņojuma saskaņošanas kārtulu.](media/unify-match-rule.png)

1. <span data-ttu-id="5e39d-185">Atlasiet **Gatavs**.</span><span class="sxs-lookup"><span data-stu-id="5e39d-185">Select **Done**.</span></span>

1. <span data-ttu-id="5e39d-186">Atlasiet vienumu **Saglabāt** un **Palaist**.</span><span class="sxs-lookup"><span data-stu-id="5e39d-186">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="5e39d-187">Sapludināšana</span><span class="sxs-lookup"><span data-stu-id="5e39d-187">Merge</span></span>

1. <span data-ttu-id="5e39d-188">Ejiet uz cilni **Sapludināt**.</span><span class="sxs-lookup"><span data-stu-id="5e39d-188">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="5e39d-189">**ContactId** attiecībā uz **loyCustomers** entītiju mainiet parādāmo nosaukumu uz **ContactIdLOYALTY**, lai atšķirtu to no citiem uzņemtajiem ID.</span><span class="sxs-lookup"><span data-stu-id="5e39d-189">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   ![pārdēvējiet contactid no lojalitātes ID.](media/unify-merge-contactid.png)

1. <span data-ttu-id="5e39d-191">Atlasiet **Saglabāt** un **Palaist sapludināšanas un lejasposma procesus**.</span><span class="sxs-lookup"><span data-stu-id="5e39d-191">Select **Save** and **Run merge and downstream processes**.</span></span>

## <a name="task-3---configure-customer-lifetime-value-prediction"></a><span data-ttu-id="5e39d-192">3. uzdevums - konfigurēt debitora mūža vērtību prognoze</span><span class="sxs-lookup"><span data-stu-id="5e39d-192">Task 3 - Configure customer lifetime value prediction</span></span>

<span data-ttu-id="5e39d-193">Tagad, izmantojot vienotos klientu profilus, mēs tagad varam izmantot klienta darbmūža prognozi.</span><span class="sxs-lookup"><span data-stu-id="5e39d-193">With the unified customer profiles in place, we can now run the customer lifetime value prediction.</span></span> <span data-ttu-id="5e39d-194">Detalizētas darbības skatiet sadaļā [Klienta Darbmūža vērtība prognoze (priekšskatījums)](predict-customer-lifetime-value.md).</span><span class="sxs-lookup"><span data-stu-id="5e39d-194">For detailed steps, see [Customer Lifetime Value prediction (preview)](predict-customer-lifetime-value.md).</span></span>

1. <span data-ttu-id="5e39d-195">Dodieties uz **Informācija**  > **Prognozes** un atlasiet **Klienta darbmūža vērtības modelis**.</span><span class="sxs-lookup"><span data-stu-id="5e39d-195">Go to  **Intelligence**  > **Predictions**  and select the **Customer lifetime value model**.</span></span>

1. <span data-ttu-id="5e39d-196">Skatiet informāciju sānu rūtī un atlasiet **Sākt darbu**.</span><span class="sxs-lookup"><span data-stu-id="5e39d-196">Go through the information in the side pane and select **Get started**.</span></span>

1. <span data-ttu-id="5e39d-197">Nosauciet modeli **OOB eCommerce CLV prognoze** un izvades entītiju **OOBeCommerceCLVPrediction**.</span><span class="sxs-lookup"><span data-stu-id="5e39d-197">Name the model **OOB eCommerce CLV Prediction** and the output entity  **OOBeCommerceCLVPrediction**.</span></span>

1. <span data-ttu-id="5e39d-198">Definēt modeļa preferences CLV modelim:</span><span class="sxs-lookup"><span data-stu-id="5e39d-198">Define model preferences for the CLV model:</span></span>
   - <span data-ttu-id="5e39d-199">**Prognoze periods**: **12 mēneši vai 1 gads**.</span><span class="sxs-lookup"><span data-stu-id="5e39d-199">**Prediction time period**: **12 months or 1 year**.</span></span> <span data-ttu-id="5e39d-200">Šis iestatījums definē, cik tālu nākotnē ir paredzama klienta darbmūža vērtība.</span><span class="sxs-lookup"><span data-stu-id="5e39d-200">This setting defines how far into the future to predict customer lifetime value.</span></span>
   - <span data-ttu-id="5e39d-201">**Aktīvie klienti**: norādiet, kādus aktīvos klientus jūsu uzņēmumam nozīmē.</span><span class="sxs-lookup"><span data-stu-id="5e39d-201">**Active customers**: Specify what active customers mean for your business.</span></span> <span data-ttu-id="5e39d-202">Iestatiet vēsturisko laika periodu, kurā klientam ir jābūt vismaz vienai darbībai, lai to uzskatītu par aktīvu.</span><span class="sxs-lookup"><span data-stu-id="5e39d-202">Set the historical time frame in which a customer must have had at least one transaction to be considered active.</span></span> <span data-ttu-id="5e39d-203">Modelis prognozēs CLV tikai aktīvajiem klientiem.</span><span class="sxs-lookup"><span data-stu-id="5e39d-203">The model will only predict CLV for active customers.</span></span> <span data-ttu-id="5e39d-204">Izvēlieties, vai šis modelis aprēķina laika periodu, pamatojoties uz vēsturiskiem transakciju datiem, vai sniedziet noteiktu laika periodu.</span><span class="sxs-lookup"><span data-stu-id="5e39d-204">Choose between letting the model calculate the time period based on historical transaction data or provide a specific time frame.</span></span> <span data-ttu-id="5e39d-205">Šajā parauga ceļvedī mēs **ļaujam modelim aprēķināt iegādes intervālu**, kas ir noklusējuma opcija.</span><span class="sxs-lookup"><span data-stu-id="5e39d-205">In this sample guide, we **let the model calculate purchase interval**, which is the default option.</span></span>
   - <span data-ttu-id="5e39d-206">**Augstas vērtības klienti**: definējiet klientus ar augstu vērtību kā maksātspējīgākajiem klientiem.</span><span class="sxs-lookup"><span data-stu-id="5e39d-206">**High value customers**: Define high value customers as a percentile of top-paying customers.</span></span> <span data-ttu-id="5e39d-207">Modelis izmanto šo ievadi, lai nodrošinātu rezultātus, kas atbilst jūsu uzņēmuma definīcijai ar augstas vērtības klientiem.</span><span class="sxs-lookup"><span data-stu-id="5e39d-207">The model uses this input to provide results that fit your business definition of high value customers.</span></span> <span data-ttu-id="5e39d-208">Jūs varat ļaut modelim definēt vērtīgos klientus.</span><span class="sxs-lookup"><span data-stu-id="5e39d-208">You can choose to let the model define high value customers.</span></span> <span data-ttu-id="5e39d-209">Tā izmanto heiristisko kārtulu, kas atvasina procentili.</span><span class="sxs-lookup"><span data-stu-id="5e39d-209">It uses a heuristic rule that derives the percentile.</span></span> <span data-ttu-id="5e39d-210">Jūs varat definēt klientus ar augstu vērtību kā maksātspējīgākos klientus.</span><span class="sxs-lookup"><span data-stu-id="5e39d-210">You can also define high value customers as a percentile of top future paying customers.</span></span> <span data-ttu-id="5e39d-211">Šajā parauga ceļvedī klientiem ar augstu vērtību mēs manuāli definējam **kā 30% maksātspējīgāko klientu** un atlasiet **Tālāk**.</span><span class="sxs-lookup"><span data-stu-id="5e39d-211">In this sample guide, we manually define high value customers as **top 30% of active paying customers** and select **Next**.</span></span>

    :::image type="content" source="media/clv-model-preferences.png" alt-text="CLV modeļa vadītās pieredzes preferenču solis.":::

1. <span data-ttu-id="5e39d-213">Darbībā **Nepieciešamie dati** atlasiet vienumu **Pievienot datus**, lai nodrošinātu transakciju vēstures datus.</span><span class="sxs-lookup"><span data-stu-id="5e39d-213">In the **Required Data** step, select **Add data** to provide the transaction history data.</span></span>

1. <span data-ttu-id="5e39d-214">Pievienojiet **eCommercePurchases : eCommerce** un kartējiet modelim nepieciešamos atribūtus:</span><span class="sxs-lookup"><span data-stu-id="5e39d-214">Add the **eCommercePurchases : eCommerce** entity and map the attributes that are required by the model:</span></span>
   - <span data-ttu-id="5e39d-215">Transakcijas ID: eCommerce.eCommercePurchases.PurchaseId</span><span class="sxs-lookup"><span data-stu-id="5e39d-215">Transaction ID: eCommerce.eCommercePurchases.PurchaseId</span></span>
   - <span data-ttu-id="5e39d-216">Transakcijas datums: eCommerce.eCommercePurchases.PurchasedOn</span><span class="sxs-lookup"><span data-stu-id="5e39d-216">Transaction date: eCommerce.eCommercePurchases.PurchasedOn</span></span>
   - <span data-ttu-id="5e39d-217">Transakcijas summa: eCommerce.eCommercePurchases.TotalPrice</span><span class="sxs-lookup"><span data-stu-id="5e39d-217">Transaction amount: eCommerce.eCommercePurchases.TotalPrice</span></span>
   - <span data-ttu-id="5e39d-218">Produkta ID: eCommerce.eCommercePurchases.ProductId</span><span class="sxs-lookup"><span data-stu-id="5e39d-218">Product ID: eCommerce.eCommercePurchases.ProductId</span></span>

1. <span data-ttu-id="5e39d-219">Atlasiet **Tālāk**.</span><span class="sxs-lookup"><span data-stu-id="5e39d-219">Select **Next**.</span></span>

1. <span data-ttu-id="5e39d-220">Iestatiet attiecības starp entītiju **eCommercePurchases : eCommerce** un **eCommerceContacts : eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="5e39d-220">Set up the relationship between the **eCommercePurchases : eCommerce** entity and  **eCommerceContacts : eCommerce**.</span></span>

1. <span data-ttu-id="5e39d-221">Izmantojot darbību **Papildu dati (neobligāti)**, varat pievienot papildu klientu darbību datus.</span><span class="sxs-lookup"><span data-stu-id="5e39d-221">The **Additional data (optional)** step allows you to add more customer activity data.</span></span> <span data-ttu-id="5e39d-222">Šie dati var palīdzēt iegūt vairāk ieskatu par klientu mijiedarbību ar jūsu uzņēmumu, tādējādi var palīdzēt CLV.</span><span class="sxs-lookup"><span data-stu-id="5e39d-222">This data can help to get more insights for customer interactions with your business, which can contribute to CLV.</span></span> <span data-ttu-id="5e39d-223">Pievienojot galvenās klientu mijiedarbības, piemēram, tīmekļa žurnālus klientu apkalpošana žurnālus vai apbalvojumu programmas vēsturi, var uzlabot sīcīšanas precizitāti.</span><span class="sxs-lookup"><span data-stu-id="5e39d-223">Adding key customer interactions like web logs, customer service logs, or rewards program history can improve the accuracy of predictions.</span></span> <span data-ttu-id="5e39d-224">Atlasiet vienumu **Pievienot datus**, lai iekļautu papildu klientu darbību datus.</span><span class="sxs-lookup"><span data-stu-id="5e39d-224">Select **Add data** to include more customer activity data.</span></span>

1. <span data-ttu-id="5e39d-225">Pievienojiet klienta darbības entītiju un kartējiet tās lauku nosaukumus ar atbilstošajiem modeļa obligātajiem laukiem:</span><span class="sxs-lookup"><span data-stu-id="5e39d-225">Add the customer activity entity and map its fields names to the corresponding fields required by the model:</span></span>
   - <span data-ttu-id="5e39d-226">Klienta darbības entītija: Reviews:Website</span><span class="sxs-lookup"><span data-stu-id="5e39d-226">Customer activity entity: Reviews:Website</span></span>
   - <span data-ttu-id="5e39d-227">Primārā atslēga: Website.Reviews.ReviewId</span><span class="sxs-lookup"><span data-stu-id="5e39d-227">Primary key: Website.Reviews.ReviewId</span></span>
   - <span data-ttu-id="5e39d-228">Laikspiedols: Website.Reviews.ReviewDate</span><span class="sxs-lookup"><span data-stu-id="5e39d-228">Timestamp: Website.Reviews.ReviewDate</span></span>
   - <span data-ttu-id="5e39d-229">Notikums (darbības nosaukums): Website.Reviews.ActivityTypeDisplay</span><span class="sxs-lookup"><span data-stu-id="5e39d-229">Event (activity name): Website.Reviews.ActivityTypeDisplay</span></span>
   - <span data-ttu-id="5e39d-230">Detalizēti (summa vai vērtība): Website.Reviews.ReviewRating</span><span class="sxs-lookup"><span data-stu-id="5e39d-230">Details (amount or value): Website.Reviews.ReviewRating</span></span>

1. <span data-ttu-id="5e39d-231">Atlasiet **Tālāk** un konfigurējiet darbību, kā arī transakciju datu un klienta datu attiecības:</span><span class="sxs-lookup"><span data-stu-id="5e39d-231">Select **Next** and configure the activity and the relationship between the transaction data and the customer data:</span></span>  
   - <span data-ttu-id="5e39d-232">Darbības veids: Izvēlēties esošu</span><span class="sxs-lookup"><span data-stu-id="5e39d-232">Activity type: Choose existing</span></span>
   - <span data-ttu-id="5e39d-233">Darbības etiķete: Pārskats</span><span class="sxs-lookup"><span data-stu-id="5e39d-233">Activity label: Review</span></span>
   - <span data-ttu-id="5e39d-234">Atbilstošā etiķete: Website.Reviews.UserId</span><span class="sxs-lookup"><span data-stu-id="5e39d-234">Corresponding label: Website.Reviews.UserId</span></span>
   - <span data-ttu-id="5e39d-235">Klienta entītija: eCommerceContacts:eCommerce</span><span class="sxs-lookup"><span data-stu-id="5e39d-235">Customer entity: eCommerceContacts:eCommerce</span></span>
   - <span data-ttu-id="5e39d-236">Attiecības: WebsiteReviews</span><span class="sxs-lookup"><span data-stu-id="5e39d-236">Relationship: WebsiteReviews</span></span>

1. <span data-ttu-id="5e39d-237">Lai iestatītu modeļa grafiku, atlasiet **Tālāk**.</span><span class="sxs-lookup"><span data-stu-id="5e39d-237">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="5e39d-238">Modelim ir regulāri jāmācās, lai apgūtu jaunus paraugus, kad tiek iekļauti jauni dati.</span><span class="sxs-lookup"><span data-stu-id="5e39d-238">The model needs to train regularly to learn new patterns when there's new data ingested.</span></span> <span data-ttu-id="5e39d-239">Šim piemēram izvēlieties **Ik mēnesi**.</span><span class="sxs-lookup"><span data-stu-id="5e39d-239">For this example, choose **Monthly**.</span></span>

1. <span data-ttu-id="5e39d-240">Pēc visas detalizētās informācijas pārskatīšanas atlasiet **Saglabāt un palaist**.</span><span class="sxs-lookup"><span data-stu-id="5e39d-240">After reviewing all the details, select  **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="5e39d-241">4.uzdevums — pārskatīt modeļa rezultātus un paskaidrojumus</span><span class="sxs-lookup"><span data-stu-id="5e39d-241">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="5e39d-242">Ļaujiet modelim pabeigt datu apmācīšanu un skaitīšanu.</span><span class="sxs-lookup"><span data-stu-id="5e39d-242">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="5e39d-243">Pēc tam varat pārskatīt CLV modeļa rezultātus un paskaidrojumus.</span><span class="sxs-lookup"><span data-stu-id="5e39d-243">Next, you can review the CLV model results and explanations.</span></span> <span data-ttu-id="5e39d-244">Papildinformāciju skatiet rakstā [Prognozes statusa un rezultātu pārskatīšana](predict-customer-lifetime-value.md#review-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="5e39d-244">For more information, see [Review a prediction status and results](predict-customer-lifetime-value.md#review-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-value-customers"></a><span data-ttu-id="5e39d-245">5. uzdevums — izveidot augstas vērtības klientu segmentu</span><span class="sxs-lookup"><span data-stu-id="5e39d-245">Task 5 - Create a segment of high value customers</span></span>

<span data-ttu-id="5e39d-246">Izpildot modeli, tiek izveidota jauna entītija, kas tiek iekļauta sarakstā **Dati** > **Entītijas**.</span><span class="sxs-lookup"><span data-stu-id="5e39d-246">Running the model creates a new entity, which is listed on **Data** > **Entities**.</span></span> <span data-ttu-id="5e39d-247">Varat izveidot jaunu klienta segmentu, pamatojoties uz modeļa izveidoto entītiju.</span><span class="sxs-lookup"><span data-stu-id="5e39d-247">You can create a new customer segment based on the entity created by the model.</span></span>

1. <span data-ttu-id="5e39d-248">Ejiet uz **Segmenti**.</span><span class="sxs-lookup"><span data-stu-id="5e39d-248">Go to **Segments**.</span></span> 

1. <span data-ttu-id="5e39d-249">Atlasiet vienumu **Jauns** un izvēlieties **Izveidot no** > **Informācija**.</span><span class="sxs-lookup"><span data-stu-id="5e39d-249">Select  **New** and choose **Create from** > **Intelligence**.</span></span>

   ![Izveidot segmentu ar modeļa izvadi.](media/segment-intelligence.png)

1. <span data-ttu-id="5e39d-251">Atlasiet entītiju **OOBeCommerceCLVPrediction** un definējiet segmentu:</span><span class="sxs-lookup"><span data-stu-id="5e39d-251">Select the  **OOBeCommerceCLVPrediction** entity and define the segment:</span></span>
  - <span data-ttu-id="5e39d-252">Lauks: CLVScore</span><span class="sxs-lookup"><span data-stu-id="5e39d-252">Field: CLVScore</span></span>
  - <span data-ttu-id="5e39d-253">Operators: ir lielāks nekā</span><span class="sxs-lookup"><span data-stu-id="5e39d-253">Operator: greater than</span></span>
  - <span data-ttu-id="5e39d-254">Vērtība: 1500</span><span class="sxs-lookup"><span data-stu-id="5e39d-254">Value: 1500</span></span>

1. <span data-ttu-id="5e39d-255">Atlasiet **Pārskats** un **Saglabāt** segmentu.</span><span class="sxs-lookup"><span data-stu-id="5e39d-255">Select **Review** and **Save** the segment.</span></span>

<span data-ttu-id="5e39d-256">Tagad jums ir segments, kas identificē klientus, kuri, pēc prognozēm, nākamajos 12 mēnešos veidos vairāk nekā $1500 lielus ieņēmumus.</span><span class="sxs-lookup"><span data-stu-id="5e39d-256">You now have a segment that identifies customers who are predicted to generate more than $1500 of revenue in the next 12 months.</span></span> <span data-ttu-id="5e39d-257">Ja ietverat vairāk datu, šis segments dinamiski tiek atjaunināts.</span><span class="sxs-lookup"><span data-stu-id="5e39d-257">This segment gets updated dynamically if more data is ingested.</span></span>

<span data-ttu-id="5e39d-258">Papildinformācijai skatiet [Segmentu izveide un pārvaldība](segments.md).</span><span class="sxs-lookup"><span data-stu-id="5e39d-258">For more information, see [Create and manage segments](segments.md).</span></span>
