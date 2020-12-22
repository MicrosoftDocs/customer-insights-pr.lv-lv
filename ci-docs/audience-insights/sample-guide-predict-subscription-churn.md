---
title: Abonementa zudumu prognozes parauga ceļvedis
description: Izmantojiet šo parauga ceļvedi, lai izmēģinātu nestandarta abonementa zudumu prognozes modeli.
ms.date: 11/19/2020
ms.reviewer: digranad
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 2537cfb5dde0d1ce1af16f585f0bf91d15ea1870
ms.sourcegitcommit: a6e7df90d61450e00886753eb5db116f2f35bb6c
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 12/01/2020
ms.locfileid: "4653989"
---
# <a name="subscription-churn-prediction-preview-sample-guide"></a><span data-ttu-id="1cb39-103">Abonementa zudumu parauga prognozes parauga ceļvedis (priekšskatījums)</span><span class="sxs-lookup"><span data-stu-id="1cb39-103">Subscription churn prediction (preview) sample guide</span></span>

<span data-ttu-id="1cb39-104">Mēs jums paskaidrosim, kā izbeigt parakstīšanās zudumu prognozi, izmantojot tālāk sniegto datu paraugu.</span><span class="sxs-lookup"><span data-stu-id="1cb39-104">We'll walk you through an end to end example of subscription churn prediction using the sample data provided below.</span></span> 

## <a name="scenario"></a><span data-ttu-id="1cb39-105">Scenārijs</span><span class="sxs-lookup"><span data-stu-id="1cb39-105">Scenario</span></span>

<span data-ttu-id="1cb39-106">Contoso ir uzņēmums, kas ražo kvalitatīvu kafiju un kafijas automātus, ko viņi pārdod, izmantojot savu Contoso Coffee mājaslapu.</span><span class="sxs-lookup"><span data-stu-id="1cb39-106">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="1cb39-107">Viņi nesen uzsāka abonēšanas uzņēmumu, lai viņu klienti regulāri saņemtu kafiju.</span><span class="sxs-lookup"><span data-stu-id="1cb39-107">They recently started a subscription business for their customers to get coffee on a regular basis.</span></span> <span data-ttu-id="1cb39-108">Viņu mērķis ir izprast, kuri abonēšanas klienti tuvāko mēnešu laikā var atcelt savu abonementu.</span><span class="sxs-lookup"><span data-stu-id="1cb39-108">Their goal is to understand, which subscribed customers might cancel their subscription in the next few months.</span></span> <span data-ttu-id="1cb39-109">Zinot, kurš no saviem klientiem varētu **zust**, var palīdzēt ietaupīt mārketinga pasākumus, koncentrējoties uz to saglabāšanu.</span><span class="sxs-lookup"><span data-stu-id="1cb39-109">Knowing which of their customers is **likely to churn**, can help them save marketing efforts by focusing on keeping them.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1cb39-110">Priekšnosacījumi</span><span class="sxs-lookup"><span data-stu-id="1cb39-110">Prerequisites</span></span>

- <span data-ttu-id="1cb39-111">Vismaz [Līdzautora atļaujas](permissions.md) Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="1cb39-111">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="1cb39-112">Ieteicams ieviest tālāk norādītos soļus [jaunā vidē](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="1cb39-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="1cb39-113">1.uzdevums - Datu uzņemšana</span><span class="sxs-lookup"><span data-stu-id="1cb39-113">Task 1 - Ingest Data</span></span>

<span data-ttu-id="1cb39-114">Pārskatiet rakstus [par datu uzņemšanu](data-sources.md) un [datu avotu importēšanu, izmantojot](connect-power-query.md) tieši Power Query savienotājus.</span><span class="sxs-lookup"><span data-stu-id="1cb39-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="1cb39-115">Tālāk sniegtajā informācijā tiek pieņemts, ka esat iepazinies ar datu uzņemšanu kopumā.</span><span class="sxs-lookup"><span data-stu-id="1cb39-115">The following information assumes you familiarized with ingesting data in general.</span></span> 

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="1cb39-116">Uzņemt klientu datus no e-komercijas platformas</span><span class="sxs-lookup"><span data-stu-id="1cb39-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="1cb39-117">Izveidojiet datu avotu ar nosaukumu **e-komercija**, izvēlieties importēšanas opciju un atlasiet **Tekstu/CSV** savienotāju.</span><span class="sxs-lookup"><span data-stu-id="1cb39-117">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="1cb39-118">Ievadiet URL e-komercijas kontaktpersonām https://aka.ms/ciadclasscontacts.</span><span class="sxs-lookup"><span data-stu-id="1cb39-118">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="1cb39-119">Rediģējot datus, atlasiet **Pārveidot** un pēc tam **Izmantot pirmajā rindā kā galvenes**.</span><span class="sxs-lookup"><span data-stu-id="1cb39-119">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="1cb39-120">Atjauniniet tālāk uzskaitīto kolonnu datu tipu:</span><span class="sxs-lookup"><span data-stu-id="1cb39-120">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="1cb39-121">**DateOfBirth**: Datums</span><span class="sxs-lookup"><span data-stu-id="1cb39-121">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="1cb39-122">**CreatedOn**: Datums/Laiks/Josla</span><span class="sxs-lookup"><span data-stu-id="1cb39-122">**CreatedOn**: Date/Time/Zone</span></span>

   [!div class="mx-imgBorder"]
   <span data-ttu-id="1cb39-123">![Pārveidot DoB par Datumu](media/ecommerce-dob-date.PNG "Pārveido dzimšanas datumu uz datumu")</span><span class="sxs-lookup"><span data-stu-id="1cb39-123">![Transform DoB to Date](media/ecommerce-dob-date.PNG "transform date of birth to date")</span></span>

1. <span data-ttu-id="1cb39-124">Labās puses rūts laukā "Nosaukums" pārdēvējiet savu datu avotu no **Vaicājuma** uz **eCommerceContacts**</span><span class="sxs-lookup"><span data-stu-id="1cb39-124">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="1cb39-125">Saglabājiet datu avotu.</span><span class="sxs-lookup"><span data-stu-id="1cb39-125">Save the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="1cb39-126">Klienta datu uzņemšana no lojalitātes shēmas</span><span class="sxs-lookup"><span data-stu-id="1cb39-126">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="1cb39-127">Izveidojiet datu avotu ar nosaukumu **LoyaltyScheme**, izvēlieties importēšanas opciju un atlasiet **Tekstu/CSV** savienotāju.</span><span class="sxs-lookup"><span data-stu-id="1cb39-127">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="1cb39-128">Ievadiet URL e-komercijas kontaktpersonām https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="1cb39-128">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="1cb39-129">Rediģējot datus, atlasiet **Pārveidot** un pēc tam **Izmantot pirmajā rindā kā galvenes**.</span><span class="sxs-lookup"><span data-stu-id="1cb39-129">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="1cb39-130">Atjauniniet tālāk uzskaitīto kolonnu datu tipu:</span><span class="sxs-lookup"><span data-stu-id="1cb39-130">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="1cb39-131">**DateOfBirth**: Datums</span><span class="sxs-lookup"><span data-stu-id="1cb39-131">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="1cb39-132">**RewardsPoints**: Vesels skaitlis</span><span class="sxs-lookup"><span data-stu-id="1cb39-132">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="1cb39-133">**CreatedOn**: Datums/Laiks</span><span class="sxs-lookup"><span data-stu-id="1cb39-133">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="1cb39-134">Labās puses rūts laukā "Nosaukums" pārdēvējiet savu datu avotu no **Vaicājuma** uz **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="1cb39-134">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="1cb39-135">Saglabājiet datu avotu.</span><span class="sxs-lookup"><span data-stu-id="1cb39-135">Save the data source.</span></span>

### <a name="ingest-subscription-information"></a><span data-ttu-id="1cb39-136">Abonenta informācijas uzņemšana</span><span class="sxs-lookup"><span data-stu-id="1cb39-136">Ingest subscription information</span></span>

1. <span data-ttu-id="1cb39-137">Izveidojiet datu avotu ar nosaukumu **SubscriptionHistory**, izvēlieties importēšanas opciju un atlasiet **Tekstu/CSV** savienotāju.</span><span class="sxs-lookup"><span data-stu-id="1cb39-137">Create a data source named **SubscriptionHistory**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="1cb39-138">Ievadiet URL e-komercijas kontaktpersonām https://aka.ms/ciadchurnsubscriptionhistory.</span><span class="sxs-lookup"><span data-stu-id="1cb39-138">Enter the URL for eCommerce contacts https://aka.ms/ciadchurnsubscriptionhistory.</span></span>

1. <span data-ttu-id="1cb39-139">Rediģējot datus, atlasiet **Pārveidot** un pēc tam **Izmantot pirmajā rindā kā galvenes**.</span><span class="sxs-lookup"><span data-stu-id="1cb39-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="1cb39-140">Atjauniniet tālāk uzskaitīto kolonnu datu tipu:</span><span class="sxs-lookup"><span data-stu-id="1cb39-140">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="1cb39-141">**SubscriptioID**: Vesels skaitlis</span><span class="sxs-lookup"><span data-stu-id="1cb39-141">**SubscriptioID**: Whole Number</span></span>
   - <span data-ttu-id="1cb39-142">**SubscriptionAmount**: Valūta</span><span class="sxs-lookup"><span data-stu-id="1cb39-142">**SubscriptionAmount**: Currency</span></span>
   - <span data-ttu-id="1cb39-143">**SubscriptionEndDate**: Datums/Laiks</span><span class="sxs-lookup"><span data-stu-id="1cb39-143">**SubscriptionEndDate**: Date/Time</span></span>
   - <span data-ttu-id="1cb39-144">**SubscriptionStartDate**: Datums/Laiks</span><span class="sxs-lookup"><span data-stu-id="1cb39-144">**SubscriptionStartDate**: Date/Time</span></span>
   - <span data-ttu-id="1cb39-145">**TransactionDate**: Datums/Laiks</span><span class="sxs-lookup"><span data-stu-id="1cb39-145">**TransactionDate**: Date/Time</span></span>
   - <span data-ttu-id="1cb39-146">**IsRecurring**: Patiess/Aplams</span><span class="sxs-lookup"><span data-stu-id="1cb39-146">**IsRecurring**: True/False</span></span>
   - <span data-ttu-id="1cb39-147">**Is_auto_renew**: Patiess/Aplams</span><span class="sxs-lookup"><span data-stu-id="1cb39-147">**Is_auto_renew**: True/False</span></span>
   - <span data-ttu-id="1cb39-148">**RecurringFrequencyInMonths**: Vesels skaitlis</span><span class="sxs-lookup"><span data-stu-id="1cb39-148">**RecurringFrequencyInMonths**: Whole Number</span></span>

1. <span data-ttu-id="1cb39-149">Labās puses rūts laukā "Nosaukums" pārdēvējiet savu datu avotu no **Vaicājuma** uz **SubscriptionHistory**.</span><span class="sxs-lookup"><span data-stu-id="1cb39-149">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **SubscriptionHistory**.</span></span>

1. <span data-ttu-id="1cb39-150">Saglabājiet datu avotu.</span><span class="sxs-lookup"><span data-stu-id="1cb39-150">Save the data source.</span></span>

### <a name="ingest-customer-data-from-website-reviews"></a><span data-ttu-id="1cb39-151">Klientu datu uzņemšana no tīmekļa pārskatiem</span><span class="sxs-lookup"><span data-stu-id="1cb39-151">Ingest customer data from website reviews</span></span>

1. <span data-ttu-id="1cb39-152">Izveidojiet datu avotu ar nosaukumu **e-komercija**, izvēlieties importēšanas opciju un atlasiet **Tekstu/CSV** savienotāju.</span><span class="sxs-lookup"><span data-stu-id="1cb39-152">Create a data source named **Website**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="1cb39-153">Ievadiet URL e-komercijas kontaktpersonām https://aka.ms/ciadclasswebsite.</span><span class="sxs-lookup"><span data-stu-id="1cb39-153">Enter the URL for eCommerce contacts https://aka.ms/ciadclasswebsite.</span></span>

1. <span data-ttu-id="1cb39-154">Rediģējot datus, atlasiet **Pārveidot** un pēc tam **Izmantot pirmajā rindā kā galvenes**.</span><span class="sxs-lookup"><span data-stu-id="1cb39-154">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="1cb39-155">Atjauniniet tālāk uzskaitīto kolonnu datu tipu:</span><span class="sxs-lookup"><span data-stu-id="1cb39-155">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="1cb39-156">**ReviewRating**: Vesels skaitlis</span><span class="sxs-lookup"><span data-stu-id="1cb39-156">**ReviewRating**: Whole Number</span></span>
   - <span data-ttu-id="1cb39-157">**ReviewDate**: Datums</span><span class="sxs-lookup"><span data-stu-id="1cb39-157">**ReviewDate**: Date</span></span>

1. <span data-ttu-id="1cb39-158">Labās puses rūts laukā "Nosaukums" pārdēvējiet savu datu avotu no **Vaicājuma** uz **webReviews**.</span><span class="sxs-lookup"><span data-stu-id="1cb39-158">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **webReviews**.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="1cb39-159">2.uzdevums — Datu apvienošana</span><span class="sxs-lookup"><span data-stu-id="1cb39-159">Task 2 - Data unification</span></span>

<span data-ttu-id="1cb39-160">Pēc datu uzņemšanas mēs tagad sākam **Kartēt, saskaņot un sapludināt** procesu, lai izveidotu vienotu klientu profilu.</span><span class="sxs-lookup"><span data-stu-id="1cb39-160">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="1cb39-161">Papildinformāciju skatiet tēmā [Datu apvienošana](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="1cb39-161">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="1cb39-162">Kartēt</span><span class="sxs-lookup"><span data-stu-id="1cb39-162">Map</span></span>

1. <span data-ttu-id="1cb39-163">Pēc datu uzņemšanas kartējiet kontaktpersonas no e-komercijas un lojalitātes datiem līdz vispārējiem datu tipiem.</span><span class="sxs-lookup"><span data-stu-id="1cb39-163">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="1cb39-164">Ejiet uz **Dati** > **Apvienot** > **Kartēt**.</span><span class="sxs-lookup"><span data-stu-id="1cb39-164">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="1cb39-165">Atlasiet entītijas, kas pārstāv klienta profilu — **eCommerceContacts** un **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="1cb39-165">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="apvienot e-komercijas un lojalitātes datu avotus.":::

1. <span data-ttu-id="1cb39-167">Atlasiet **ContactId** kā primāro atslēgu **eCommerceContacts** un **LoyaltyID** kā **loyCustomers** primāro atslēgu.</span><span class="sxs-lookup"><span data-stu-id="1cb39-167">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="Apvienot LoyaltyId kā primāro atslēgu.":::

### <a name="match"></a><span data-ttu-id="1cb39-169">Saskaņot</span><span class="sxs-lookup"><span data-stu-id="1cb39-169">Match</span></span>

1. <span data-ttu-id="1cb39-170">Dodieties uz cilni **Saskaņot** un atlasiet **Iestatīt secību**.</span><span class="sxs-lookup"><span data-stu-id="1cb39-170">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="1cb39-171">**Primārajā** nolaižamajā sarakstā izvēlieties **eCommerceContacts : e-komercijas** kā primāro avotu un iekļaujiet visus ierakstus.</span><span class="sxs-lookup"><span data-stu-id="1cb39-171">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="1cb39-172">Nolaižamajā sarakstā **2.entītija** izvēlieties **loyCustomers: LoyaltyScheme** un iekļaujiet visus ierakstus.</span><span class="sxs-lookup"><span data-stu-id="1cb39-172">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   :::image type="content" source="media/unify-match-order.PNG" alt-text="Apvienot e-komercijas un lojalitātes atbilstības.":::

1. <span data-ttu-id="1cb39-174">Atlasiet **Jaunas kārtulas izveide**</span><span class="sxs-lookup"><span data-stu-id="1cb39-174">Select **Create a new rule**</span></span>

1. <span data-ttu-id="1cb39-175">Pievienojiet pirmo nosacījumu, izmantojot FullName.</span><span class="sxs-lookup"><span data-stu-id="1cb39-175">Add your first condition using FullName.</span></span>

   * <span data-ttu-id="1cb39-176">Nolaižamajā sarakstā atlasiet **FullName** eCommerceContacts.</span><span class="sxs-lookup"><span data-stu-id="1cb39-176">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="1cb39-177">Nolaižamajā sarakstā atlasiet **FullName** loyCustomers.</span><span class="sxs-lookup"><span data-stu-id="1cb39-177">For loyCustomers select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="1cb39-178">Atlasiet opciju **Normalizēt** nolaižamo sarakstu un izvēlieties **tipu (tālrunis, nosaukums, adrese,...)**.</span><span class="sxs-lookup"><span data-stu-id="1cb39-178">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   * <span data-ttu-id="1cb39-179">Iestatiet **Precizitātes līmeni**: **Pamatinformācija** un **Vērtību**: **Augsts**.</span><span class="sxs-lookup"><span data-stu-id="1cb39-179">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="1cb39-180">Ievadiet jaunās kārtulas nosaukumu **FullName, e-pasts**.</span><span class="sxs-lookup"><span data-stu-id="1cb39-180">Enter the name **FullName, Email** for the new rule.</span></span>

   * <span data-ttu-id="1cb39-181">Pievienojiet e-pasta adresei otru nosacījumu, atlasot **Pievienot nosacījumu**</span><span class="sxs-lookup"><span data-stu-id="1cb39-181">Add a second condition for email address by selecting **Add Condition**</span></span>
   * <span data-ttu-id="1cb39-182">Entītijas eCommerceContacts izvēlieties nolaižamajā izvēlnē vienumu **E-pasts**.</span><span class="sxs-lookup"><span data-stu-id="1cb39-182">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   * <span data-ttu-id="1cb39-183">Entītijai loyCustomers izvēlieties nolaižamajā izvēlnē vienumu **E-pasts**.</span><span class="sxs-lookup"><span data-stu-id="1cb39-183">For entity loyCustomers, choose **EMail** in the drop-down.</span></span> 
   * <span data-ttu-id="1cb39-184">Atstājiet normalizāciju tukšu.</span><span class="sxs-lookup"><span data-stu-id="1cb39-184">Leave Normalize blank.</span></span> 
   * <span data-ttu-id="1cb39-185">Iestatiet **Precizitātes līmeni**: **Pamatinformācija** un **Vērtību**: **Augsts**.</span><span class="sxs-lookup"><span data-stu-id="1cb39-185">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="Apvienot nosaukuma un e-pasta ziņojuma saskaņošanas kārtulu.":::

7. <span data-ttu-id="1cb39-187">Atlasiet vienumu **Saglabāt** un **Palaist**.</span><span class="sxs-lookup"><span data-stu-id="1cb39-187">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="1cb39-188">Sapludināšana</span><span class="sxs-lookup"><span data-stu-id="1cb39-188">Merge</span></span>

1. <span data-ttu-id="1cb39-189">Ejiet uz cilni **Sapludināt**.</span><span class="sxs-lookup"><span data-stu-id="1cb39-189">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="1cb39-190">**ContactId** attiecībā uz **loyCustomers** entītiju mainiet parādāmo nosaukumu uz **ContactIdLOYALTY**, lai atšķirtu to no citiem uzņemtajiem ID.</span><span class="sxs-lookup"><span data-stu-id="1cb39-190">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="pārdēvējiet contactid no lojalitātes ID.":::

1. <span data-ttu-id="1cb39-192">Atlasiet **Saglabāt** un **Palaist**, lai sāktu sapludināšanas procesu.</span><span class="sxs-lookup"><span data-stu-id="1cb39-192">Select **Save** and **Run** to start the Merge Process.</span></span>


## <a name="task-3---configure-the-subscription-churn-prediction"></a><span data-ttu-id="1cb39-193">3.uzdevums — konfigurēt abonēšanas zudumu prognozi</span><span class="sxs-lookup"><span data-stu-id="1cb39-193">Task 3 - Configure the subscription churn prediction</span></span>

<span data-ttu-id="1cb39-194">Izmantojot vienoto klientu profilus, mēs tagad varam palaist abonēšanas zudumu prognozi.</span><span class="sxs-lookup"><span data-stu-id="1cb39-194">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span> <span data-ttu-id="1cb39-195">Detalizētas darbības skatiet rakstu [Abonementa zudumu prognoze (priekšskatījums)](predict-subscription-churn.md).</span><span class="sxs-lookup"><span data-stu-id="1cb39-195">For detailed steps, see the [Subscription churn prediction (preview)](predict-subscription-churn.md) article.</span></span> 

1. <span data-ttu-id="1cb39-196">Atveriet **Informācija** > **Atklāt** un atlasiet, lai izmantotu **Klientu zudumu modeli**.</span><span class="sxs-lookup"><span data-stu-id="1cb39-196">Go to **Intelligence** > **Discover** and select to use the **Customer churn model**.</span></span>

1. <span data-ttu-id="1cb39-197">Atlasiet opciju **Abonēšana** un atlasiet **Sākt darbu**.</span><span class="sxs-lookup"><span data-stu-id="1cb39-197">Select the **Subscription** option and select **Get started**.</span></span>

1. <span data-ttu-id="1cb39-198">Nosauciet modeli **OOB Abonementu zudumu prognoze** un izvades entītiju **OOBSubscriptionChurnPrediction**.</span><span class="sxs-lookup"><span data-stu-id="1cb39-198">Name the model **OOB Subscription Churn Prediction** and the output entity **OOBSubscriptionChurnPrediction**.</span></span>

1. <span data-ttu-id="1cb39-199">Definējiet divus zuduma modeļa nosacījumus:</span><span class="sxs-lookup"><span data-stu-id="1cb39-199">Define two conditions for the churn model:</span></span>

   * <span data-ttu-id="1cb39-200">**Dienas kopš abonementa izbeigšanās**: **vismaz 60** dienas.</span><span class="sxs-lookup"><span data-stu-id="1cb39-200">**Days since subscription ended**: **at least 60** days.</span></span> <span data-ttu-id="1cb39-201">Ja klients nav atjaunojis savu abonementu tik ilgi pēc abonementa beigām, viņš tiek uzskatīts par zaudētu.</span><span class="sxs-lookup"><span data-stu-id="1cb39-201">If a customer doesn't renew the subscription in this period after their subscription ended, they are considered churned.</span></span> 

   * <span data-ttu-id="1cb39-202">**Zuduma definīcija**: **vismaz 93** dienas.</span><span class="sxs-lookup"><span data-stu-id="1cb39-202">**Churn definition**: **at least 93** days.</span></span> <span data-ttu-id="1cb39-203">Modelis prognozē laika posmu, kurā klienti varētu zust.</span><span class="sxs-lookup"><span data-stu-id="1cb39-203">The duration the model predict which customers might churn.</span></span> <span data-ttu-id="1cb39-204">Jo tālākā nākotnē lūkosities, jo neprecīzāki būs rezultāti.</span><span class="sxs-lookup"><span data-stu-id="1cb39-204">The further in the future you look, the less precise the results.</span></span>

     :::image type="content" source="media/model-subs-levers.PNG" alt-text="Atlasiet modeļa sviras Prognozes logs un Zuduma definīcija.":::

1. <span data-ttu-id="1cb39-206">Atlasiet **Pievienot nepieciešamos datus** un atlasiet **Pievienot datus** abonementu vēsturei.</span><span class="sxs-lookup"><span data-stu-id="1cb39-206">Select **Add required data** and select **Add data** for subscription history.</span></span>

1. <span data-ttu-id="1cb39-207">Pievienojiet **Abonementi: SubscriptionHistory** entītiju un kartējiet laukus no e-komercijas uz atbilstošiem modelī vajadzīgajiem laukiem.</span><span class="sxs-lookup"><span data-stu-id="1cb39-207">Add the **Subscription : SubscriptionHistory** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="1cb39-208">Savienojiet **Abonementi: SubscriptionHistory** entītiju ar **eCommerceContacts: e-komercijas**, nosauciet relācijas **eCommerceSubscription**.</span><span class="sxs-lookup"><span data-stu-id="1cb39-208">Join the **Subscription : SubscriptionHistory** entity with **eCommerceContacts : eCommerce**, name the relationship **eCommerceSubscription**.</span></span>

   :::image type="content" source="media/model-subscription-join.PNG" alt-text="Pievienojieties e-komercijas entītijām.":::

1. <span data-ttu-id="1cb39-210">Sadaļā Klientu darbības pievienojiet **webReviews : vietnes** entītiju un kartējiet laukus no webReviews uz modelī vajadzīgajiem atbilstošajiem laukiem.</span><span class="sxs-lookup"><span data-stu-id="1cb39-210">Under Customer Activities, add the **webReviews : Website** entity and map the fields from webReviews to the corresponding fields required by the model.</span></span> 
   - <span data-ttu-id="1cb39-211">Primārā atslēga: ReviewId</span><span class="sxs-lookup"><span data-stu-id="1cb39-211">Primary key: ReviewId</span></span>
   - <span data-ttu-id="1cb39-212">Laikspiedols: ReviewDate</span><span class="sxs-lookup"><span data-stu-id="1cb39-212">Timestamp: ReviewDate</span></span>
   - <span data-ttu-id="1cb39-213">Notikums: ReviewRating</span><span class="sxs-lookup"><span data-stu-id="1cb39-213">Event: ReviewRating</span></span>

1. <span data-ttu-id="1cb39-214">Konfigurējiet darbību vietņu recenzijām.</span><span class="sxs-lookup"><span data-stu-id="1cb39-214">Configure an activity for website reviews.</span></span> <span data-ttu-id="1cb39-215">Atlasiet darbību **Pārskats** un savienojiet **webReviews: vietnes** entītiju ar **eCommerceContacts: e-komercija**.</span><span class="sxs-lookup"><span data-stu-id="1cb39-215">Select the activity **Review** and join the **webReviews : Website** entity with **eCommerceContacts : eCommerce**.</span></span>

1. <span data-ttu-id="1cb39-216">Lai iestatītu modeļa grafiku, atlasiet **Tālāk**.</span><span class="sxs-lookup"><span data-stu-id="1cb39-216">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="1cb39-217">Modelis ir regulāri jāapmāca, lai apgūtu jaunus rakstus, kad tiek uzņemti jauni dati.</span><span class="sxs-lookup"><span data-stu-id="1cb39-217">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="1cb39-218">Šajā piemērā atlasiet **Reizi mēnesī**.</span><span class="sxs-lookup"><span data-stu-id="1cb39-218">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="1cb39-219">Pēc visas detalizētās informācijas pārskatīšanas atlasiet **Saglabāt un palaist**.</span><span class="sxs-lookup"><span data-stu-id="1cb39-219">After reviewing all the details, select **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="1cb39-220">4.uzdevums — pārskatīt modeļa rezultātus un paskaidrojumus</span><span class="sxs-lookup"><span data-stu-id="1cb39-220">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="1cb39-221">Ļaujiet modelim pabeigt datu apmācīšanu un skaitīšanu.</span><span class="sxs-lookup"><span data-stu-id="1cb39-221">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="1cb39-222">Tagad jūs varat pārskatīt abonēšanas zudumu modeļa paskaidrojumus.</span><span class="sxs-lookup"><span data-stu-id="1cb39-222">You can now review the subscription churn model explanations.</span></span> <span data-ttu-id="1cb39-223">Papildinformāciju skatiet rakstā [Prognozes statusa un rezultātu pārskatīšana](predict-subscription-churn.md#review-a-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="1cb39-223">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a><span data-ttu-id="1cb39-224">5.uzdevums — Izveidot augsta zudumu riska klientu segmentu</span><span class="sxs-lookup"><span data-stu-id="1cb39-224">Task 5 - Create a segment of high churn-risk customers</span></span>

<span data-ttu-id="1cb39-225">Palaižot ražošanas modeli, tiek izveidota jauna entītija, ko var redzēt vienumā **Dati** > **Entītijas**.</span><span class="sxs-lookup"><span data-stu-id="1cb39-225">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>   

<span data-ttu-id="1cb39-226">Varat izveidot jaunu segmentu, par pamatu izmantojot modelī izveidotu entītiju.</span><span class="sxs-lookup"><span data-stu-id="1cb39-226">You can create a new segment based on the entity created by the model.</span></span>

1.  <span data-ttu-id="1cb39-227">Ejiet uz **Segmenti**.</span><span class="sxs-lookup"><span data-stu-id="1cb39-227">Go to **Segments**.</span></span> <span data-ttu-id="1cb39-228">Atlasiet vienumu **Jauns** un izvēlieties **Izveidot no** > **Informācija**.</span><span class="sxs-lookup"><span data-stu-id="1cb39-228">Select **New** and choose **Create from** > **Intelligence**.</span></span> 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Izveidot segmentu ar modeļa izvadi.":::

1. <span data-ttu-id="1cb39-230">Atlasiet **OOBSubscriptionChurnPrediction** galapunktu un definējiet segmentu:</span><span class="sxs-lookup"><span data-stu-id="1cb39-230">Select the **OOBSubscriptionChurnPrediction** endpoint and define the segment:</span></span> 
   - <span data-ttu-id="1cb39-231">Lauks: ChurnScore</span><span class="sxs-lookup"><span data-stu-id="1cb39-231">Field: ChurnScore</span></span>
   - <span data-ttu-id="1cb39-232">Operators: ir lielāks nekā</span><span class="sxs-lookup"><span data-stu-id="1cb39-232">Operator: greater than</span></span>
   - <span data-ttu-id="1cb39-233">Vērtība: 0.6</span><span class="sxs-lookup"><span data-stu-id="1cb39-233">Value: 0.6</span></span>
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="Iestatiet abonementu zudumu segmentu.":::

<span data-ttu-id="1cb39-235">Tagad jums ir segments, kas tiek dinamiski atjaunināts, kas identificē šā abonēšanas uzņēmuma augsta zudumu riska klientus.</span><span class="sxs-lookup"><span data-stu-id="1cb39-235">You now have a segment that is dynamically updated which identifies high churn-risk customers for this subscription business.</span></span>

<span data-ttu-id="1cb39-236">Papildinformācijai skatiet [Segmentu izveide un pārvaldība](segments.md).</span><span class="sxs-lookup"><span data-stu-id="1cb39-236">For more information, see [Create and manage segments](segments.md).</span></span>
