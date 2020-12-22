---
title: Atrast AI līdzīgus klientus
description: Atrodiet līdzīgu klientu segmentus, izmantojot mākslīgo intelektu
ms.date: 06/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: jimsonc
manager: shellyha
ms.openlocfilehash: 8cdec4edd599b0249fcf144b5e5c0124504e1e14
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406352"
---
# <a name="similar-customers-preview"></a><span data-ttu-id="a8ea8-103">Līdzīgi klienti (priekšskatījums)</span><span class="sxs-lookup"><span data-stu-id="a8ea8-103">Similar Customers (preview)</span></span>

<span data-ttu-id="a8ea8-104">Šis līdzeklis ļauj atrast līdzīgus klientus jūsu klientu bāzē, izmantojot mākslīgo intelektu.</span><span class="sxs-lookup"><span data-stu-id="a8ea8-104">This feature lets you find similar customers in your customer base using artificial intelligence.</span></span> <span data-ttu-id="a8ea8-105">Lai izmantotu šo līdzekli, ir jābūt izveidotam vismaz vienam segmentam.</span><span class="sxs-lookup"><span data-stu-id="a8ea8-105">You need to have at least one segment created to use this feature.</span></span> <span data-ttu-id="a8ea8-106">Izvēršot esoša segmenta kritērijus, varat atrast šim segmentam līdzīgus klientus.</span><span class="sxs-lookup"><span data-stu-id="a8ea8-106">Expanding the criteria of an existing segment help find customers that are similar to that segment.</span></span>

> [!NOTE]
> <span data-ttu-id="a8ea8-107">*Atrast līdzīgus klientus* izmanto automatizētus līdzekļus, lai izvērtētu datus un veiktu prognozes, pamatojoties uz šiem datiem, un tādējādi šo līdzekli var izmantot kā profilēšanas metodi, saskaņā ar šī jēdziena definīciju Vispārīgajā datu aizsardzības regulā ("VDAR").</span><span class="sxs-lookup"><span data-stu-id="a8ea8-107">*Find similar customers* uses automated means to evaluate data and make predictions based on that data, and therefore has the capability to be used as a method of profiling, as that term is defined by the General Data Protection Regulation (“GDPR”).</span></span> <span data-ttu-id="a8ea8-108">Šī līdzekļa izmantošana klienta datu apstrādei var būt pakļauta VDAR vai citiem likumiem vai noteikumiem.</span><span class="sxs-lookup"><span data-stu-id="a8ea8-108">Customer’s use of this feature to process data may be subject to GDPR or other laws or regulations.</span></span> <span data-ttu-id="a8ea8-109">Jūs esat atbildīgs par to, ka jūsu Dynamics 365 Customer Insights lietojums, ieskaitot prognozes, atbilst visiem piemērojamiem likumiem un noteikumiem, ieskaitot likumus, kas attiecas uz privātumu, personas datiem, biometrijas datiem, datu aizsardzību un saziņas konfidencialitāti.</span><span class="sxs-lookup"><span data-stu-id="a8ea8-109">You are responsible for ensuring that your use of Dynamics 365 Customer Insights, including predictions, complies with all applicable laws and regulations, including laws related to privacy, personal data, biometric data, data protection, and confidentiality of communications.</span></span>

## <a name="finding-similar-customers"></a><span data-ttu-id="a8ea8-110">Līdzīgu klientu atrašana</span><span class="sxs-lookup"><span data-stu-id="a8ea8-110">Finding similar customers</span></span>

1. <span data-ttu-id="a8ea8-111">Sadaļā auditorijas ieskati atveriet sadaļu **Segmenti** un atlasiet segmentu, uz kura vēlaties balstīt jauno segmentu.</span><span class="sxs-lookup"><span data-stu-id="a8ea8-111">In audience insights, go to **Segments** and select the segment you want to base your new segment on.</span></span> <span data-ttu-id="a8ea8-112">Tas būs jūsu *avota segments*.</span><span class="sxs-lookup"><span data-stu-id="a8ea8-112">That's your *source segment*.</span></span>

1. <span data-ttu-id="a8ea8-113">Darbību joslā atlasiet **Atrast līdzīgus klientus**.</span><span class="sxs-lookup"><span data-stu-id="a8ea8-113">In the action bar, select **Find similar customers**.</span></span>

1. <span data-ttu-id="a8ea8-114">Pārskatiet jaunā segmenta ierosināto nosaukumu un, ja nepieciešams, to mainiet.</span><span class="sxs-lookup"><span data-stu-id="a8ea8-114">Review the suggested name for your new segment and change it if necessary.</span></span>

1. <span data-ttu-id="a8ea8-115">Pārskatiet laukus, kuri definē jauno segmentu.</span><span class="sxs-lookup"><span data-stu-id="a8ea8-115">Review the fields that define your new segment.</span></span> <span data-ttu-id="a8ea8-116">Šie lauki definē pamatu, uz kura sistēma centīsies atrast jūsu avota segmentam līdzīgus klientus.</span><span class="sxs-lookup"><span data-stu-id="a8ea8-116">These fields define the basis on which the system will try to find similar customers to your source segment.</span></span> <span data-ttu-id="a8ea8-117">Sistēma pēc noklusējuma atlasīs ieteiktos laukos.</span><span class="sxs-lookup"><span data-stu-id="a8ea8-117">The system will select recommended fields by default.</span></span>
  <span data-ttu-id="a8ea8-118">Lauki, kuri var ievērojami samazināt modeļa veiktspēju, tiek automātiski izslēgti:</span><span class="sxs-lookup"><span data-stu-id="a8ea8-118">Fields that can significantly reduce the model performance are automatically excluded:</span></span>
  
   - <span data-ttu-id="a8ea8-119">Lauki ar šādiem datu tipiem: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType</span><span class="sxs-lookup"><span data-stu-id="a8ea8-119">Fields with the following data types: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType</span></span>
   - <span data-ttu-id="a8ea8-120">Lauki, kuros kardināls (elementu skaits laukā) ir mazāks par 2 vai lielāks par 30</span><span class="sxs-lookup"><span data-stu-id="a8ea8-120">Fields with a cardinality (the number of elements in a field) of less than 2 or more than 30</span></span>

1. <span data-ttu-id="a8ea8-121">Izvēlieties, vai savā jaunajā segmentā vēlaties iekļaut **Visus klientus** vai tikai klientus no **Konkrēta esošā segmenta**.</span><span class="sxs-lookup"><span data-stu-id="a8ea8-121">Choose if you want to include **All customers** or only customers in a **Specific existing segment** in your new segment.</span></span>

1. <span data-ttu-id="a8ea8-122">Izslēdziet klientus no avota segmenta, atlasot izvēles rūtiņu **Izslēgt visus no avota segmenta**.</span><span class="sxs-lookup"><span data-stu-id="a8ea8-122">Exclude customers in your source segment by selecting the **Exclude everyone in source segment** checkbox.</span></span>

1. <span data-ttu-id="a8ea8-123">Sistēma pēc noklusējuma piedāvā iekļaut tikai 20% no jūsu izvades mērķauditorijas apjoma.</span><span class="sxs-lookup"><span data-stu-id="a8ea8-123">By default, the system suggests including only 20% of the target audience size in your output.</span></span> <span data-ttu-id="a8ea8-124">Pēc nepieciešamības rediģējiet šo robežvērtību.</span><span class="sxs-lookup"><span data-stu-id="a8ea8-124">Edit this threshold as needed.</span></span> <span data-ttu-id="a8ea8-125">Robežvērtības palielināšana samazinās precizitāti.</span><span class="sxs-lookup"><span data-stu-id="a8ea8-125">Increasing the threshold will reduce the precision.</span></span>

1. <span data-ttu-id="a8ea8-126">Lapas lejasdaļā atlasiet opciju **Palaist**, lai uzsāktu binārās klasificēšanas uzdevumu (algoritmiskās mācīšanās metode), kas analizē datu kopu.</span><span class="sxs-lookup"><span data-stu-id="a8ea8-126">Select **Run** at the bottom of the page to start a binary classification task (a method of machine learning) which analyzes the dataset.</span></span>

## <a name="view-the-similar-segment"></a><span data-ttu-id="a8ea8-127">Līdzīga segmenta skatīšana</span><span class="sxs-lookup"><span data-stu-id="a8ea8-127">View the similar segment</span></span>

<span data-ttu-id="a8ea8-128">Pēc līdzīga segmenta apstrādes, jaunais segments būs iekļauts lapā **Segmenti**.</span><span class="sxs-lookup"><span data-stu-id="a8ea8-128">After processing the similar segment, you'll find the new segment listed on the **Segments** page.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a8ea8-129">![Līdzīgu klientu segments](media/expanded-segment.png "Līdzīgu klientu segments")</span><span class="sxs-lookup"><span data-stu-id="a8ea8-129">![Similar customers segment](media/expanded-segment.png "Similar customers segment")</span></span>

<span data-ttu-id="a8ea8-130">Lai atvērtu segmenta informāciju, darbību joslā atlasiet **Skatīt**.</span><span class="sxs-lookup"><span data-stu-id="a8ea8-130">Select **View** in the action bar to open the segment detail.</span></span> <span data-ttu-id="a8ea8-131">Šajā skatā ir informācija par rezultātu sadali [līdzības rezultātos](#about-similarity-scores).</span><span class="sxs-lookup"><span data-stu-id="a8ea8-131">This view contains information about the result distribution across [similarity scores](#about-similarity-scores).</span></span> <span data-ttu-id="a8ea8-132">Līdzības rezultāta vērtības ir pieejamas arī **Segmenta elementu priekšskatījumā**.</span><span class="sxs-lookup"><span data-stu-id="a8ea8-132">You'll also find the similarity score values in the **Segment members preview**.</span></span>

## <a name="use-the-output-of-a-similar-segment"></a><span data-ttu-id="a8ea8-133">Līdzīga segmenta izvades izmantošana</span><span class="sxs-lookup"><span data-stu-id="a8ea8-133">Use the output of a similar segment</span></span>

<span data-ttu-id="a8ea8-134">Varat [strādāt ar līdzīga segmenta izvadi](segments.md) tāpat, kā to darāt ar citiem segmentiem.</span><span class="sxs-lookup"><span data-stu-id="a8ea8-134">You can [work with the output of a similar segment](segments.md) as you do with other segments.</span></span> <span data-ttu-id="a8ea8-135">Piemēram, eksportējiet segmentu vai veidojiet mēru.</span><span class="sxs-lookup"><span data-stu-id="a8ea8-135">For example, export the segment or build a measure.</span></span>

## <a name="refresh-and-edit-a-similar-segment"></a><span data-ttu-id="a8ea8-136">Līdzīga segmenta atsvaidzināšana un rediģēšana</span><span class="sxs-lookup"><span data-stu-id="a8ea8-136">Refresh and edit a similar segment</span></span>

<span data-ttu-id="a8ea8-137">Lai atsvaidzinātu līdzīgu segmentu, atlasiet to lapā **Segmenti** un darbību joslā atlasiet **Atsvaidzināt**.</span><span class="sxs-lookup"><span data-stu-id="a8ea8-137">To refresh a similar segment, select it on the **Segments** page and select **Refresh** in the action bar.</span></span>

<span data-ttu-id="a8ea8-138">Rediģējot līdzīgu segmentu, dati tiks pārstrādāti.</span><span class="sxs-lookup"><span data-stu-id="a8ea8-138">Editing a similar segment will reprocess your data.</span></span> <span data-ttu-id="a8ea8-139">Iepriekš izveidotie segmenti tiek atjaunināti ar atsvaidzinātiem datiem.</span><span class="sxs-lookup"><span data-stu-id="a8ea8-139">The previously created segment gets updated with refreshed data.</span></span>    
<span data-ttu-id="a8ea8-140">Lai rediģētu līdzīgu segmentu, atlasiet to lapā **Segmenti** un darbību joslā atlasiet **Rediģēt**.</span><span class="sxs-lookup"><span data-stu-id="a8ea8-140">To edit a similar segment, select it on the **Segments** page and select **Edit** in the action bar.</span></span> <span data-ttu-id="a8ea8-141">Piemērojiet izmaiņas un atlasiet **Palaist**, lai sāktu apstrādi.</span><span class="sxs-lookup"><span data-stu-id="a8ea8-141">Apply your changes and select **Run** to start the processing.</span></span>

## <a name="delete-a-similar-segment"></a><span data-ttu-id="a8ea8-142">Līdzīga segmenta dzēšana</span><span class="sxs-lookup"><span data-stu-id="a8ea8-142">Delete a similar segment</span></span>

<span data-ttu-id="a8ea8-143">Atlasiet segmentu lapā **Segmenti** un darbību joslā atlasiet **Dzēst**.</span><span class="sxs-lookup"><span data-stu-id="a8ea8-143">Select the segment on the **Segments** page and select **Delete** in the action bar.</span></span> <span data-ttu-id="a8ea8-144">Pēc tam apstipriniet dzēšanu.</span><span class="sxs-lookup"><span data-stu-id="a8ea8-144">Then, confirm your deletion.</span></span>

## <a name="about-similarity-scores"></a><span data-ttu-id="a8ea8-145">Par līdzības rezultātiem</span><span class="sxs-lookup"><span data-stu-id="a8ea8-145">About similarity scores</span></span>

<span data-ttu-id="a8ea8-146">Binārās klasificēšanas algoritmiskās mācīšanās modelis piešķir rezultātu lietotājiem līdzīgā segmentā.</span><span class="sxs-lookup"><span data-stu-id="a8ea8-146">The binary classification machine learning model assigns a score to customers in the similar segment.</span></span> <span data-ttu-id="a8ea8-147">Rezultāts balstās līdzībā klientiem no avota segmenta.</span><span class="sxs-lookup"><span data-stu-id="a8ea8-147">The score is based on the similarity to customers in the source segment.</span></span>

- <span data-ttu-id="a8ea8-148">Līdzības rezultāti zem 0,55 ir klienti, kurus sistēma klasificē kā *nelīdzīgus* klientiem no avota segmenta.</span><span class="sxs-lookup"><span data-stu-id="a8ea8-148">Similarity scores below 0.55 are customers the system classified as *not similar* to customers in the source segment</span></span>
- <span data-ttu-id="a8ea8-149">Līdzības rezultāti no 0,55 līdz 0,7 līdz klasificēti kā *nedaudz līdzīgi*</span><span class="sxs-lookup"><span data-stu-id="a8ea8-149">Similarity scores between 0.55 – 0.7 are classified as *somewhat similar*</span></span>
- <span data-ttu-id="a8ea8-150">Līdzības rezultāti no 0,7 līdz 0,85 līdz klasificēti kā *līdzīgi*</span><span class="sxs-lookup"><span data-stu-id="a8ea8-150">Similarity scores between 0.7 – 0.85 are classified as *similar*</span></span>
- <span data-ttu-id="a8ea8-151">Līdzības rezultāti no 0,85 līdz 1 ir klienti, kurus sistēma klasificē kā *ļoti līdzīgus*</span><span class="sxs-lookup"><span data-stu-id="a8ea8-151">Similarity scores between 0.85 – 1 are customers the system classified as *very similar*</span></span>

<span data-ttu-id="a8ea8-152">Klienti ar līdzības rezultātu, kas zemāks par 0,4, netiek iekļauti modeļa izvadē.</span><span class="sxs-lookup"><span data-stu-id="a8ea8-152">Customers with similarity scores below 0.4 aren't included in the model output.</span></span> <span data-ttu-id="a8ea8-153">Sistēma tos neuzskata par pietiekami līdzīgiem avota segmentam.</span><span class="sxs-lookup"><span data-stu-id="a8ea8-153">The system doesn't consider them similar enough to the source segment.</span></span>
