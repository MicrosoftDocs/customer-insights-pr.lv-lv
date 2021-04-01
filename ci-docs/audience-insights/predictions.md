---
title: Daļējo datu aizpildīšana, izmantojot prognozes
description: Izmantojiet prognozes, lai aizpildītu nepilnīgus klientu datus.
ms.date: 05/05/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 3342328b9eead9bdcb8b41f119a1d0a5823001c8
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595910"
---
# <a name="complete-your-partial-data-with-predictions"></a><span data-ttu-id="e40e8-103">Aizpildiet savus daļējos datus ar prognozēm</span><span class="sxs-lookup"><span data-stu-id="e40e8-103">Complete your partial data with predictions</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="e40e8-104">Prognozes ļauj viegli izveidot prognozētās vērtības, kas var uzlabot jūsu izpratni par klientu.</span><span class="sxs-lookup"><span data-stu-id="e40e8-104">Predictions lets you easily create predicted values that can enhance your understanding of a customer.</span></span> <span data-ttu-id="e40e8-105">Lapā **Informācija** > **Prognozes** varat atlasīt **Manas prognozes**, lai skatītu prognozes, ko esat konfigurējis citās auditorijas ieskatu daļās, un ļaut tās papildus pielāgot.</span><span class="sxs-lookup"><span data-stu-id="e40e8-105">On the **Intelligence** > **Predictions** page, you can select **My predictions** to see predictions that you've configured in other parts of audience insights, and allow you to further customize them.</span></span>

> [!NOTE]
> <span data-ttu-id="e40e8-106">Šo līdzekli nevar izmantot, ja jūsu vidē tiek izmantots Azure Data Lake Gen 2 krātuve.</span><span class="sxs-lookup"><span data-stu-id="e40e8-106">You can't use this feature if your environment uses Azure Data Lake Gen 2 storage.</span></span>
>
> <span data-ttu-id="e40e8-107">Līdzeklis Prognozes izmanto automatizētus līdzekļus, lai novērtētu datus un veiktu prognozes, pamatojoties uz šiem datiem, un tāpēc tās ir izmantojamas kā profilēšanas metode, jo šis termins ir definēts vispārīgajā datu aizsardzības regulā ("VDAR").</span><span class="sxs-lookup"><span data-stu-id="e40e8-107">The predictions feature uses automated means to evaluate data and make predictions based on that data, and therefore has the capability to be used as a method of profiling, as that term is defined by the General Data Protection Regulation ("GDPR").</span></span> <span data-ttu-id="e40e8-108">Šī līdzekļa izmantošana klienta datu apstrādei var būt pakļauta VDAR vai citiem likumiem vai noteikumiem.</span><span class="sxs-lookup"><span data-stu-id="e40e8-108">Customer's use of this feature to process data may be subject to GDPR or other laws or regulations.</span></span> <span data-ttu-id="e40e8-109">Jūs esat atbildīgs par to, ka jūsu Dynamics 365 Customer Insights lietojums, ieskaitot prognozes, atbilst visiem piemērojamiem likumiem un noteikumiem, ieskaitot likumus, kas attiecas uz privātumu, personas datiem, biometrijas datiem, datu aizsardzību un saziņas konfidencialitāti.</span><span class="sxs-lookup"><span data-stu-id="e40e8-109">You are responsible for ensuring that your use of Dynamics 365 Customer Insights, including predictions, complies with all applicable laws and regulations, including laws related to privacy, personal data, biometric data, data protection, and confidentiality of communications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e40e8-110">Priekšnosacījumi</span><span class="sxs-lookup"><span data-stu-id="e40e8-110">Prerequisites</span></span>

<span data-ttu-id="e40e8-111">Lai organizācija varētu izmantot prognožu līdzekli, pārliecinieties, vai ir izpildīti šādi priekšnosacījumi:</span><span class="sxs-lookup"><span data-stu-id="e40e8-111">Before your organization can use the predictions feature, the following prerequisites must be met:</span></span>

1. <span data-ttu-id="e40e8-112">Jūsu organizācijai ir iestatīts gadījums [Common Data Service](/ai-builder/build-model#prerequisites), un tā ir tāda pati organizācija kā Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="e40e8-112">Your organization has an instance [set up in the Common Data Service](/ai-builder/build-model#prerequisites) and it's in the same organization as Customer Insights.</span></span>

2. <span data-ttu-id="e40e8-113">Jūsu vide ir piesaistīta jūsu Common Data Service instancei.</span><span class="sxs-lookup"><span data-stu-id="e40e8-113">Your environment is attached to your Common Data Service instance.</span></span>

<span data-ttu-id="e40e8-114">Ja jūs [veidojat pirmo vidi](manage-environments.md), konfigurējiet to dialoglodziņā **Izveidot vidi** un atlasiet **Detalizētāk**.</span><span class="sxs-lookup"><span data-stu-id="e40e8-114">If you're [creating a new environment](manage-environments.md), configure it in the **Create an environment** dialog and select **Advanced**.</span></span> <span data-ttu-id="e40e8-115">Ja esat jau izveidojis vidi, atveriet tā iestatījumus un atlasiet **Detalizētāk**.</span><span class="sxs-lookup"><span data-stu-id="e40e8-115">If you've already created an environment, go to its settings and select **Advanced**.</span></span> <span data-ttu-id="e40e8-116">Jebkurā gadījumā sadaļā **Izmantojiet prognozes** ievadiet Common Data Service instances URL, kurai vēlaties pievienot savu vidi.</span><span class="sxs-lookup"><span data-stu-id="e40e8-116">Either way, in the **Use predictions** section, enter the Common Data Service instance URL to which you want to attach your environment.</span></span>

## <a name="create-a-prediction-in-the-customer-entity"></a><span data-ttu-id="e40e8-117">Prognozēšanas izveide klienta entītijā</span><span class="sxs-lookup"><span data-stu-id="e40e8-117">Create a prediction in the Customer entity</span></span>

1. <span data-ttu-id="e40e8-118">Sadaļā Auditorijas ieskati skatiet **Dati** > **Entītijas**.</span><span class="sxs-lookup"><span data-stu-id="e40e8-118">In audience insights, go to **Data** > **Entities**.</span></span>

2. <span data-ttu-id="e40e8-119">Atlasiet entītiju **Klients**.</span><span class="sxs-lookup"><span data-stu-id="e40e8-119">Select the **Customer** entity.</span></span>

3. <span data-ttu-id="e40e8-120">**Klients: CustomerInsights** entītijā atlasiet cilnē **Lauki**.</span><span class="sxs-lookup"><span data-stu-id="e40e8-120">In the **Customer:CustomerInsights** entity, select on the **Fields** tab.</span></span>

4. <span data-ttu-id="e40e8-121">Atrodiet atribūta nosaukumu, kuram vēlaties prognozēt vērtības, un pēc tam atlasiet ikonu **Pārskats** kolonnā **Kopsavilkums**.</span><span class="sxs-lookup"><span data-stu-id="e40e8-121">Find the attribute name you wish to predict values for, then select the **Overview** icon in the **Summary** column.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e40e8-122">![Ikona Pārskats](media/intelligence-overviewicon.png "Ikona Pārskats")</span><span class="sxs-lookup"><span data-stu-id="e40e8-122">![Overview icon](media/intelligence-overviewicon.png "Overview icon")</span></span>

5. <span data-ttu-id="e40e8-123">Ja jūsu atribūtam ir augsts trūkstošo vērtību līmenis, atlasiet **Prognozēt trūkstošās vērtības**, lai turpinātu jūsu prognozēšanu.</span><span class="sxs-lookup"><span data-stu-id="e40e8-123">If there's a high rate of missing values for your attribute, select **Predict missing values** to continue with your prediction.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e40e8-124">![Tiek parādīts statusa pārskats ar poga Prognozēt trūkstošās vērtības](media/intelligence-overviewpredictmissingvalues.png "Tiek parādīts statusa pārskats ar poga Prognozēt trūkstošās vērtības")</span><span class="sxs-lookup"><span data-stu-id="e40e8-124">![Overview status with predict missing values button shown](media/intelligence-overviewpredictmissingvalues.png "Overview status with predict missing values button shown")</span></span>

6. <span data-ttu-id="e40e8-125">Norādiet **Parādāmo nosaukumu** un **Izvades entītijas nosaukumu** prognozes rezultātiem.</span><span class="sxs-lookup"><span data-stu-id="e40e8-125">Provide a **Display name** and an **Output entity name** for the results of the prediction.</span></span>

7. <span data-ttu-id="e40e8-126">Iepriekš aizpildītu opciju saraksts parāda, kur varat kartēt vērtības uz prognozēto kategoriju.</span><span class="sxs-lookup"><span data-stu-id="e40e8-126">A pre-populated list of options will show where you can map the values to a predicted category.</span></span> <span data-ttu-id="e40e8-127">Šajā gadījumā vienīgās kategorijas opcijas ir 0 vai 1, jo tās kartē uz prognozes patieso/kļūdaino vai bināro raksturu.</span><span class="sxs-lookup"><span data-stu-id="e40e8-127">In this case, your only category options will be 0 or 1, as they map to the true/false or binary nature of the prediction.</span></span> <span data-ttu-id="e40e8-128">Kolonnā Kategorija kartējiet lauku vērtības, kuras vēlaties klasificēt kā "0" gala prognozē "0", un elementus, ko vēlaties klasificēt kā "1" galējā prognozē "1".</span><span class="sxs-lookup"><span data-stu-id="e40e8-128">In the Category column, map the field values you'd like to be classified as "0" in the final prediction to "0", and the items you'd like to be classified as "1" in the final prediction to "1".</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e40e8-129">![Kartēto lauku vērtību rādīšanas piemērs kategorijām](media/intelligence-categorymapping.png "Kartēto lauku vērtību rādīšanas piemērs kategorijām")</span><span class="sxs-lookup"><span data-stu-id="e40e8-129">![Example showing mapped field values to categories](media/intelligence-categorymapping.png "Example showing mapped field values to categories")</span></span>

8. <span data-ttu-id="e40e8-130">Atlasiet **Gatavs**, un prognoze tiks apstrādāta.</span><span class="sxs-lookup"><span data-stu-id="e40e8-130">Select **Done** and the prediction will be processed.</span></span> <span data-ttu-id="e40e8-131">Apstrādei ir vajadzīgs laiks atkarībā no datu lieluma un sarežģītības pakāpes.</span><span class="sxs-lookup"><span data-stu-id="e40e8-131">The processing will take some time, depending on the size and complexity of data.</span></span> <span data-ttu-id="e40e8-132">Rezultāti būs pieejami jaunā entītijā, pamatojoties uz jūsu izveidotās prognozes **Izvades entītijas nosaukumu**.</span><span class="sxs-lookup"><span data-stu-id="e40e8-132">Results will be available in a new entity based on the **Output entity name** of the prediction you created.</span></span>

## <a name="create-a-prediction-while-creating-a-segment"></a><span data-ttu-id="e40e8-133">Izveidot prognozi, veidojot segmentu</span><span class="sxs-lookup"><span data-stu-id="e40e8-133">Create a prediction while creating a segment</span></span>

<span data-ttu-id="e40e8-134">Izveidojot segmentu, var paredzēt arī trūkstošās vērtības konkrētam izvēles atribūtam.</span><span class="sxs-lookup"><span data-stu-id="e40e8-134">Predicting missing values for a specific attribute of choice is also possible when creating a segment.</span></span> <span data-ttu-id="e40e8-135">Īpaši tad, ja ātri izveidojat segmentu, pamatojoties vai nu uz Unified Customer entītiju, vai Customer_Measure entītiju.</span><span class="sxs-lookup"><span data-stu-id="e40e8-135">Specifically, when you quickly create a segment based on either your unified Customer entity or Customer_Measure entity.</span></span>

<span data-ttu-id="e40e8-136">Kā daļu no šīs plūsmas jūs izvēlaties noteiktu atribūtu, lai balstītu savu segmentu, piemēram, klientu apmierinātību vai pirkuma summu.</span><span class="sxs-lookup"><span data-stu-id="e40e8-136">As part of this flow, you'll choose a specific attribute to base your segment on, such as Customer Satisfaction or Purchase Amount.</span></span> <span data-ttu-id="e40e8-137">Pēc segmenta izveides sistēma piedāvās metodi, lai prognozētu šī atribūta trūkstošās vērtības.</span><span class="sxs-lookup"><span data-stu-id="e40e8-137">Upon segment creation, the system will suggest a method for predicting any missing values for this attribute.</span></span>

1. <span data-ttu-id="e40e8-138">Sadaļā auditorijas ieskati atveriet sadaļu **Segmenti** un atlasiet elementu **Profili**.</span><span class="sxs-lookup"><span data-stu-id="e40e8-138">In audience insights, go to **Segments** and select the **Profiles** tile.</span></span>

2. <span data-ttu-id="e40e8-139">Izvēlieties **Lauks**, lai izveidotu segmentu, un atlasiet **Operators**; pēc tam atlasiet vienumu **Pārskatīt**.</span><span class="sxs-lookup"><span data-stu-id="e40e8-139">Choose a **Field** to create a segment on and select an **Operator**, then select **Review**.</span></span>

3. <span data-ttu-id="e40e8-140">Norādiet segmenta **nosaukumu** un **parādāmo vārdu**.</span><span class="sxs-lookup"><span data-stu-id="e40e8-140">Provide a **Name** and a **Display name** for the segment.</span></span>

4. <span data-ttu-id="e40e8-141">Atlasiet vienumu **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="e40e8-141">Select **Save**.</span></span>

5. <span data-ttu-id="e40e8-142">Ja tikko izveidotajam segmentam ir nepilnīgi dati avota laukā, varat izvēlēties prognozēt trūkstošās vērtības.</span><span class="sxs-lookup"><span data-stu-id="e40e8-142">If the segment you created has incomplete data in the source field, you can choose to predict the missing values.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e40e8-143">![Prognozēšanas poga](media/segments-predictoption.png "Prognozēšanas poga")</span><span class="sxs-lookup"><span data-stu-id="e40e8-143">![Prediction button](media/segments-predictoption.png "Prediction button")</span></span>

6. <span data-ttu-id="e40e8-144">Norādiet **Parādāmo nosaukumu** un **Izvades entītijas nosaukumu** prognozes rezultātiem.</span><span class="sxs-lookup"><span data-stu-id="e40e8-144">Provide a **Display name** and an **Output entity name** for the results of the prediction.</span></span>

7. <span data-ttu-id="e40e8-145">Atlasiet **Gatavs**.</span><span class="sxs-lookup"><span data-stu-id="e40e8-145">Select **Done**.</span></span> <span data-ttu-id="e40e8-146">Jūsu prognoze drīzumā tiks ģenerēta jaunajā entītijā ar nosaukumu, ko norādījāt laukā **Izvades entītijas nosaukums**.</span><span class="sxs-lookup"><span data-stu-id="e40e8-146">Your prediction will be generated shortly in a new entity with the name you provided for the **Output entity name**.</span></span>

## <a name="view-a-prediction"></a><span data-ttu-id="e40e8-147">Prognozes skatīšana</span><span class="sxs-lookup"><span data-stu-id="e40e8-147">View a prediction</span></span>

1. <span data-ttu-id="e40e8-148">Sadaļā Auditorijas ieskati ejiet uz **Informācija** > **Prognozes** > **Manas prognozes**.</span><span class="sxs-lookup"><span data-stu-id="e40e8-148">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="e40e8-149">Atlasiet prognozes, kuras vēlaties pārskatīt.</span><span class="sxs-lookup"><span data-stu-id="e40e8-149">Select the prediction you want to review.</span></span>

3. <span data-ttu-id="e40e8-150">Kolonnā **Darbības** atlasiet daudzpunkti un izvēlieties **Skatīt**.</span><span class="sxs-lookup"><span data-stu-id="e40e8-150">Select the ellipsis in the **Actions** column and choose **View**.</span></span>

4. <span data-ttu-id="e40e8-151">Prognozes skatā redzēsit vairākus datu punktus.</span><span class="sxs-lookup"><span data-stu-id="e40e8-151">You'll see a number of data points in the view of your prediction.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e40e8-152">![Prognožu lapa](media/intelligence-predictionsviewpage.png "Prognožu lapa")</span><span class="sxs-lookup"><span data-stu-id="e40e8-152">![Predictions page](media/intelligence-predictionsviewpage.png "Predictions page")</span></span>

   - <span data-ttu-id="e40e8-153">**Prognozētās vērtības** rāda kartēšanu, ko izveidojāt lauka vērtībā uz kategoriju kartēšanas fāzi.</span><span class="sxs-lookup"><span data-stu-id="e40e8-153">**Predicted values** shows the mapping you created during the Field value to Category mapping phase.</span></span> <span data-ttu-id="e40e8-154">Šīs ir datu kopas vērtības, kas ir kartētas uz noteiktu kategoriju.</span><span class="sxs-lookup"><span data-stu-id="e40e8-154">These are the values in your dataset that have been mapped to a specific category.</span></span>
   <span data-ttu-id="e40e8-155">-**Galvenie ietekmētāji** ir jūsu datu kopas faktori, kas, visticamāk, ietekmēja prognozes ticamību tam, ka jūsu lauka vērtība tiek kartēta uz noteiktu kategoriju.</span><span class="sxs-lookup"><span data-stu-id="e40e8-155">-**Top influencers** are the factors within your dataset that were most likely to influence the prediction's confidence of your Field value being mapped to a specific category.</span></span>
   - <span data-ttu-id="e40e8-156">**Veiktspēja** norāda, kā notiek prognozes.</span><span class="sxs-lookup"><span data-stu-id="e40e8-156">**Performance** indicates how the predictions are doing.</span></span> <span data-ttu-id="e40e8-157">Atlasiet saiti, lai uzzinātu vairāk.</span><span class="sxs-lookup"><span data-stu-id="e40e8-157">Select the link to learn more.</span></span>
   - <span data-ttu-id="e40e8-158">**Priekšskatījumā** redzami izvades datu kopas paraugi no jūsu prognozes un varbūtība vai ticamība par prognozēto vērtību, ja 0 ir nenoteikts, un 1 ir drošs.</span><span class="sxs-lookup"><span data-stu-id="e40e8-158">**Preview** shows samples of the output dataset from your prediction and the likelihood, or our confidence, of the predicted value where 0 is uncertain, and 1 is certain.</span></span>

## <a name="update-a-prediction"></a><span data-ttu-id="e40e8-159">Prognožu atjaunināšana</span><span class="sxs-lookup"><span data-stu-id="e40e8-159">Update a prediction</span></span>

1. <span data-ttu-id="e40e8-160">Sadaļā Auditorijas ieskati ejiet uz **Informācija** > **Prognozes** > **Manas prognozes**.</span><span class="sxs-lookup"><span data-stu-id="e40e8-160">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="e40e8-161">Atlasiet prognozi, kuru vēlaties atjaunināt, un atlasiet ikonu **Atjaunināt**.</span><span class="sxs-lookup"><span data-stu-id="e40e8-161">Select the prediction you want to update and select the **Update** icon.</span></span>

3. <span data-ttu-id="e40e8-162">Prognoze tiks ieplānota apstrādei.</span><span class="sxs-lookup"><span data-stu-id="e40e8-162">The prediction will be scheduled for processing.</span></span> <span data-ttu-id="e40e8-163">Varat redzēt, kad pēdējo atjaunināšanas reizi kolonnā **Atjaunināts** lapā **Prognozes**.</span><span class="sxs-lookup"><span data-stu-id="e40e8-163">You can see the time it was last updated in the **Updated** column of the **Predictions** page.</span></span>

## <a name="edit-a-prediction"></a><span data-ttu-id="e40e8-164">Prognozes rediģēšana</span><span class="sxs-lookup"><span data-stu-id="e40e8-164">Edit a prediction</span></span>

<span data-ttu-id="e40e8-165">Pēc tam, kad esat izveidojis prognozi, varat pielāgot modeli AI Builder, lai palielinātu sava modeļa efektivitāti.</span><span class="sxs-lookup"><span data-stu-id="e40e8-165">After you've created a prediction, you can customize the model in the AI Builder to increase the effectiveness of your model.</span></span>  

1. <span data-ttu-id="e40e8-166">Sadaļā Auditorijas ieskati ejiet uz **Informācija** > **Prognozes** > **Manas prognozes**.</span><span class="sxs-lookup"><span data-stu-id="e40e8-166">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="e40e8-167">Atlasiet prognozi, kuru vēlaties rediģēt.</span><span class="sxs-lookup"><span data-stu-id="e40e8-167">Select the prediction you want to edit.</span></span>

3. <span data-ttu-id="e40e8-168">Kolonnā **Darbības** atlasiet daudzpunkti un izvēlieties **Skatīt**.</span><span class="sxs-lookup"><span data-stu-id="e40e8-168">Select the ellipsis in the **Actions** column and choose **View**.</span></span>

4. <span data-ttu-id="e40e8-169">Atlasiet **Pielāgot līdzeklī AI Builder**.</span><span class="sxs-lookup"><span data-stu-id="e40e8-169">Select **Customize in AI Builder**.</span></span>

5. <span data-ttu-id="e40e8-170">Atjauniniet savu modeli līdzeklī AI Builder.</span><span class="sxs-lookup"><span data-stu-id="e40e8-170">Update your model in the AI Builder.</span></span> <span data-ttu-id="e40e8-171">[Uzziniet vairāk par modeļu pārvaldību līdzeklī AI Builder](/ai-builder/manage-model#retrain-and-republish-existing-models).</span><span class="sxs-lookup"><span data-stu-id="e40e8-171">[Learn more about managing models in the AI builder](/ai-builder/manage-model#retrain-and-republish-existing-models).</span></span>

<span data-ttu-id="e40e8-172">Nākamajā jūsu prognozes izpildes gaitā tiks izmantots jūsu izveidotais atjauninātais modelis.</span><span class="sxs-lookup"><span data-stu-id="e40e8-172">The next run of your prediction will use the updated model you've created.</span></span>

> [!NOTE]
> <span data-ttu-id="e40e8-173">Jaunie modeļi, kas izveidoti programmā AI Builder, netiks parādīti auditorijas ieskatos, ja vien šis modelis netika izveidots no iepriekš minētajām iespējām.</span><span class="sxs-lookup"><span data-stu-id="e40e8-173">New models created in AI Builder will not be displayed in audience insights unless the model was created from the experiences listed above.</span></span>

## <a name="remove-a-prediction"></a><span data-ttu-id="e40e8-174">Prognozes noņemšana</span><span class="sxs-lookup"><span data-stu-id="e40e8-174">Remove a prediction</span></span>

1. <span data-ttu-id="e40e8-175">Sadaļā Auditorijas ieskati ejiet uz **Informācija** > **Prognozes** > **Manas prognozes**.</span><span class="sxs-lookup"><span data-stu-id="e40e8-175">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="e40e8-176">Atlasiet prognozi, ko vēlaties izdzēst.</span><span class="sxs-lookup"><span data-stu-id="e40e8-176">Select the prediction you want to delete.</span></span>

3. <span data-ttu-id="e40e8-177">Kolonnā **Darbības** atlasiet daudzpunkti un izvēlieties **Dzēst**.</span><span class="sxs-lookup"><span data-stu-id="e40e8-177">Select the ellipsis in the **Actions** column and choose **Delete**.</span></span>

4. <span data-ttu-id="e40e8-178">Apstipriniet dzēšanu.</span><span class="sxs-lookup"><span data-stu-id="e40e8-178">Confirm the deletion.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="e40e8-179">Problēmu novēršana</span><span class="sxs-lookup"><span data-stu-id="e40e8-179">Troubleshooting</span></span>

<span data-ttu-id="e40e8-180">Ja nevarat pabeigt Common Data Service pievienošanas procesu kļūdas dēļ, varat mēģināt pabeigt procesu manuāli.</span><span class="sxs-lookup"><span data-stu-id="e40e8-180">If you can't complete the attach Common Data Service process due to an error, you can try to complete the process manually.</span></span> <span data-ttu-id="e40e8-181">Ir zināmas divas problēmas, kas var rasties pievienošanas procesā:</span><span class="sxs-lookup"><span data-stu-id="e40e8-181">There are two known issues that can occur in the attach process:</span></span>

- <span data-ttu-id="e40e8-182">Klientu karšu pievienojumprogrammu risinājums nav instalēts.</span><span class="sxs-lookup"><span data-stu-id="e40e8-182">The Customer Card Add-in solution is not installed.</span></span>
    1. <span data-ttu-id="e40e8-183">Izpildiet norādījumus, lai [instalētu un konfigurētu risinājumu](customer-card-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="e40e8-183">Complete the instructions to [install and configure the solution](customer-card-add-in.md).</span></span>

- <span data-ttu-id="e40e8-184">Programmas atļaujas nav piešķirtas.</span><span class="sxs-lookup"><span data-stu-id="e40e8-184">App permissions aren't granted.</span></span>
    1. <span data-ttu-id="e40e8-185">Dodieties uz [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="e40e8-185">Go to [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com).</span></span>
    1. <span data-ttu-id="e40e8-186">Atlasiet **Vides**.</span><span class="sxs-lookup"><span data-stu-id="e40e8-186">Select **Environments**.</span></span>
    1. <span data-ttu-id="e40e8-187">Atlasiet daudzpunkti blakus videi, kurai vēlaties pievienot atļauju un atlasiet **Iestatījumi**.</span><span class="sxs-lookup"><span data-stu-id="e40e8-187">Select the ellipsis next to the environment you want to add the permission to and select **Settings**.</span></span>
    1. <span data-ttu-id="e40e8-188">Izvērsiet **Lietotāji + atļaujas** un atlasiet **Lietotāji**.</span><span class="sxs-lookup"><span data-stu-id="e40e8-188">Expand **Users + permissions** and select **Users**.</span></span>
    1. <span data-ttu-id="e40e8-189">Atlasiet **+ Jauns** un atlasiet **Lietotājs**.</span><span class="sxs-lookup"><span data-stu-id="e40e8-189">Select **+ New** and select **User**.</span></span>
    1. <span data-ttu-id="e40e8-190">Atlasiet **Programmas lietotājs**, ja tas vēl nav atlasīts, un ievadiet šādu informāciju:</span><span class="sxs-lookup"><span data-stu-id="e40e8-190">Select **Application User** if it's not already selected and enter the following information:</span></span>
        - <span data-ttu-id="e40e8-191">**Lietotājvārds:** cihelp@microsoft.com</span><span class="sxs-lookup"><span data-stu-id="e40e8-191">**User Name:** cihelp@microsoft.com</span></span>
        - <span data-ttu-id="e40e8-192">**Programmas ID:** 38c77d00-5fcb-4cce-9d93-af4738258e3c</span><span class="sxs-lookup"><span data-stu-id="e40e8-192">**Application ID:** 38c77d00-5fcb-4cce-9d93-af4738258e3c</span></span>
        - <span data-ttu-id="e40e8-193">**Vārds:** Customer</span><span class="sxs-lookup"><span data-stu-id="e40e8-193">**First Name:** Customer</span></span>
        - <span data-ttu-id="e40e8-194">**Uzvārds:** Insights</span><span class="sxs-lookup"><span data-stu-id="e40e8-194">**Last Name:** Insights</span></span>
        - <span data-ttu-id="e40e8-195">**Primārais e-pasts:** cihelp@microsoft.com</span><span class="sxs-lookup"><span data-stu-id="e40e8-195">**Primary Email:** cihelp@microsoft.com</span></span>
    1. <span data-ttu-id="e40e8-196">Atlasiet vienumu **Saglabāt un aizvērt**.</span><span class="sxs-lookup"><span data-stu-id="e40e8-196">Select **Save & Close**.</span></span>
    1. <span data-ttu-id="e40e8-197">Atlasiet tikko izveidoto lietotāju.</span><span class="sxs-lookup"><span data-stu-id="e40e8-197">Select the user you just created.</span></span>
    1. <span data-ttu-id="e40e8-198">IAugšēja izvēlnes joslā atlasiet **Pārvaldīt lomas**.</span><span class="sxs-lookup"><span data-stu-id="e40e8-198">Select **Manage Roles** in the top menu bar.</span></span>
    1. <span data-ttu-id="e40e8-199">Atlasiet **Sistēmas administrators** un pēc tam atlasiet **Labi**.</span><span class="sxs-lookup"><span data-stu-id="e40e8-199">Select **System Administrator**, then select **OK**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]