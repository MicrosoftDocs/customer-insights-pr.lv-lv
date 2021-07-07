---
title: Adreses uzlabošanas bagātināšana
description: Bagātināt un normalizēt klientu profilu adrešu informāciju, izmantojot Microsoft modeļus.
ms.date: 04/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: e0ca731f944da9a7eaae7c2dc2d7568b6386089f
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305441"
---
# <a name="enrichment-of-customer-profiles-with-enhanced-addresses"></a><span data-ttu-id="9aad9-103">Klientu profilu bagātināšana ar uzlabotām adresēm</span><span class="sxs-lookup"><span data-stu-id="9aad9-103">Enrichment of customer profiles with enhanced addresses</span></span>

<span data-ttu-id="9aad9-104">Datu adreses var būt nestrukturētas, nepilnīgas vai nepareizas.</span><span class="sxs-lookup"><span data-stu-id="9aad9-104">Addresses in your data can be unstructured, incomplete, or incorrect.</span></span> <span data-ttu-id="9aad9-105">Izmantojiet Microsoft modeļus, lai normalizētu un bagātinātu adreses [Common Data Model formātā](/common-data-model/schema/core/applicationcommon/address), lai iegūtu labāku precizitāti un ieskatus.</span><span class="sxs-lookup"><span data-stu-id="9aad9-105">Use Microsoft's models to normalize and enrich your addresses into the [Common Data Model format](/common-data-model/schema/core/applicationcommon/address) for better accuracy and insights.</span></span>

## <a name="how-we-enhance-addresses"></a><span data-ttu-id="9aad9-106">Adrešu uzlabošana</span><span class="sxs-lookup"><span data-stu-id="9aad9-106">How we enhance addresses</span></span>

<span data-ttu-id="9aad9-107">Mūsu modelis iet cauri divsoļu procesam, lai uzlabotu adresi.</span><span class="sxs-lookup"><span data-stu-id="9aad9-107">Our model goes through a two-step process to enhance an address.</span></span> <span data-ttu-id="9aad9-108">Vispirms tiek parsēta adrese, lai identificētu tās komponentus, un tie tiek ievietoti strukturētā formātā.</span><span class="sxs-lookup"><span data-stu-id="9aad9-108">First, it parses the address to identify its components and puts them into a structured format.</span></span> <span data-ttu-id="9aad9-109">Pēc tam izmantojam AI, lai labotu, pabeigtu un standartizētu adreses vērtības.</span><span class="sxs-lookup"><span data-stu-id="9aad9-109">Then, we use AI to correct, complete, and standardize the values in the address.</span></span>

### <a name="example"></a><span data-ttu-id="9aad9-110">Piemērs</span><span class="sxs-lookup"><span data-stu-id="9aad9-110">Example</span></span>

<span data-ttu-id="9aad9-111">Adreses informācija var būt nestandarta formātā un var saturēt pareizrakstības kļūdas.</span><span class="sxs-lookup"><span data-stu-id="9aad9-111">Address information might be in a nonstandard format and contain spelling errors.</span></span> <span data-ttu-id="9aad9-112">Modelis var novērst šīs problēmas un izveidot konsekventas adreses vienotā klientu profilos.</span><span class="sxs-lookup"><span data-stu-id="9aad9-112">The model can fix these issues and create consistent addresses in unified customer profiles.</span></span>

```Input
4567 w main stret californa missouri 54321 us
```

```Output
- Street1: 4567 W Main St
- City: California
- StateOrProvince: MO
- ZipOrPostalCode: 54321
- CountryOrRegion: United States of America

- Address: 4567 W Main St, California, MO, 54321, United States of America
```

### <a name="limitations"></a><span data-ttu-id="9aad9-113">Ierobežojumi</span><span class="sxs-lookup"><span data-stu-id="9aad9-113">Limitations</span></span>

<span data-ttu-id="9aad9-114">Paplašinātās adreses darbojas tikai ar vērtībām, kas jau ir jūsu nosūtāmos adrešu datos.</span><span class="sxs-lookup"><span data-stu-id="9aad9-114">Enhanced addresses only works with the values that already exist in your ingested address data.</span></span> <span data-ttu-id="9aad9-115">Modelis:</span><span class="sxs-lookup"><span data-stu-id="9aad9-115">The model doesn't:</span></span> 

1. <span data-ttu-id="9aad9-116">nepārbauda, vai adrese ir derīga.</span><span class="sxs-lookup"><span data-stu-id="9aad9-116">Verify if the address is a valid address.</span></span>
2. <span data-ttu-id="9aad9-117">nepārbauda, vai ir derīga kāda no vērtībām, piemēram, pasta indeksi vai pasta indeksu nosaukumi.</span><span class="sxs-lookup"><span data-stu-id="9aad9-117">Verify if any of the values, such as ZIP codes or street names, are valid.</span></span>
3. <span data-ttu-id="9aad9-118">nemaina neatpazītās vērtības.</span><span class="sxs-lookup"><span data-stu-id="9aad9-118">Change values it doesn't recognize.</span></span>

<span data-ttu-id="9aad9-119">Modelis izmanto algoritmiskās mācīšanās metodes, lai uzlabotu adreses.</span><span class="sxs-lookup"><span data-stu-id="9aad9-119">The model uses machine learning-based techniques to enhance addresses.</span></span> <span data-ttu-id="9aad9-120">Lai gan mēs piemērojam augstu ticamības slieksni, kad modelis maina ievades vērtību, tāpat kā jebkuram uz algoritmisko mācīšanos balstītam modelim, 100 procentu precizitāte netiek garantēta.</span><span class="sxs-lookup"><span data-stu-id="9aad9-120">While we apply a high confidence threshold for when the model changes an input value, as with any machine learning-based model, 100 percent accuracy is not guaranteed.</span></span>

## <a name="supported-countries-or-regions"></a><span data-ttu-id="9aad9-121">Atbalstītās valstis vai reģioni</span><span class="sxs-lookup"><span data-stu-id="9aad9-121">Supported countries or regions</span></span>

<span data-ttu-id="9aad9-122">Pašlaik mēs atbalstītu adrešu bagātināšanu šajās valstīs vai reģionos:</span><span class="sxs-lookup"><span data-stu-id="9aad9-122">We currently support enriching addresses in these countries or regions:</span></span> 

- <span data-ttu-id="9aad9-123">Austrālija</span><span class="sxs-lookup"><span data-stu-id="9aad9-123">Australia</span></span>
- <span data-ttu-id="9aad9-124">Kanāda</span><span class="sxs-lookup"><span data-stu-id="9aad9-124">Canada</span></span>
- <span data-ttu-id="9aad9-125">Lielbritānija</span><span class="sxs-lookup"><span data-stu-id="9aad9-125">United Kingdom</span></span>
- <span data-ttu-id="9aad9-126">Amerikas Savienotās Valstis</span><span class="sxs-lookup"><span data-stu-id="9aad9-126">United States</span></span>

<span data-ttu-id="9aad9-127">Adresēs jābūt norādītai valsts/reģiona vērtībai.</span><span class="sxs-lookup"><span data-stu-id="9aad9-127">Addresses must contain a country/region value.</span></span> <span data-ttu-id="9aad9-128">Netiek apstrādātas adreses tām valstīm vai reģioniem, kas netiek atbalstīti, un adresēm, kurām nav nodrošināta neviena valsts vai reģions.</span><span class="sxs-lookup"><span data-stu-id="9aad9-128">We don't process addresses for countries or regions that aren't supported and addresses that have no country or region provided.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="9aad9-129">Bagātināto datu konfigurēšana</span><span class="sxs-lookup"><span data-stu-id="9aad9-129">Configure the enrichment</span></span>

1. <span data-ttu-id="9aad9-130">Dodieties uz **Dati** > **Bagātināšana**.</span><span class="sxs-lookup"><span data-stu-id="9aad9-130">Go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="9aad9-131">Elementā **Paplašinātās adreses** atlasiet **Bagātināt savus datus**.</span><span class="sxs-lookup"><span data-stu-id="9aad9-131">Select **Enrich my data** on the **Enhanced addresses** tile.</span></span>

   :::image type="content" source="media/enhanced-addresses-tile.png" alt-text="Elementa Paplašinātās adreses ekrānuzņēmums.":::

1. <span data-ttu-id="9aad9-133">Atlasiet **Klientu datu kopu** un izvēlieties entītiju, kurā ir ietvertas bagātināmās adreses.</span><span class="sxs-lookup"><span data-stu-id="9aad9-133">Select the **Customer data set** and choose the entity containing the addresses you want to enrich.</span></span> <span data-ttu-id="9aad9-134">Varat atlasīt entītiju *Klients*, lai bagātinātu adreses visos klientu profilos, vai atlasīt segmenta entītiju, lai bagātinātu adreses tikai šajā segmentā iekļautajos klientu profilos.</span><span class="sxs-lookup"><span data-stu-id="9aad9-134">You can select the *Customer* entity to enrich addresses in all your customer profiles or select a segment entity to enrich addresses only in customer profiles contained in that segment.</span></span>

1. <span data-ttu-id="9aad9-135">Atlasiet adrešu formatēšanas veidu datu kopā.</span><span class="sxs-lookup"><span data-stu-id="9aad9-135">Select how addresses are formatted in your data set.</span></span> <span data-ttu-id="9aad9-136">Izvēlieties **Viena atribūta adresi**, ja datu adresēs tiek izmantots viens lauks.</span><span class="sxs-lookup"><span data-stu-id="9aad9-136">Choose **Single-attribute address** if addresses in your data use a single field.</span></span> <span data-ttu-id="9aad9-137">Izvēlieties **Vairāku atribūta adresi**, ja datu adresēs tiek izmantots vairāk nekā viens datu lauks.</span><span class="sxs-lookup"><span data-stu-id="9aad9-137">Choose **Multiple-attribute address** if addresses in your data use more than one data field.</span></span>

   > [!NOTE]
   > <span data-ttu-id="9aad9-138">Valsts/reģions ir obligāts gan viena atribūta, gan vairāku atribūtu adresēs.</span><span class="sxs-lookup"><span data-stu-id="9aad9-138">Country/Region is mandatory in both single-attribute and multiple-attribute addresses.</span></span> <span data-ttu-id="9aad9-139">Adreses, kurās nav derīgu vai atbalstītu valsts/reģiona vērtību, netiks bagātinātas.</span><span class="sxs-lookup"><span data-stu-id="9aad9-139">Addresses that don't contain valid or supported country/region values won't be enriched.</span></span>

1.  <span data-ttu-id="9aad9-140">Kartējiet adreses laukus no savas vienotās klienta entītijas.</span><span class="sxs-lookup"><span data-stu-id="9aad9-140">Map the address fields from your unified customer entity.</span></span>

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="Paplašināta adrešu lauku kartējuma lapa.":::

1. <span data-ttu-id="9aad9-142">Lai pabeigtu lauka kartēšanu, atlasiet **Tālāk**.</span><span class="sxs-lookup"><span data-stu-id="9aad9-142">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="9aad9-143">Norādiet bagātināto datu nosaukumu un izvades entitījas nosaukumu.</span><span class="sxs-lookup"><span data-stu-id="9aad9-143">Provide a name for the enrichment and the output entity.</span></span>

1. <span data-ttu-id="9aad9-144">Pēc izvēļu pārskatīšanas atlasiet **Saglabāt vidi**.</span><span class="sxs-lookup"><span data-stu-id="9aad9-144">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="9aad9-145">Bagātināšanas rezultāti</span><span class="sxs-lookup"><span data-stu-id="9aad9-145">Enrichment results</span></span>

<span data-ttu-id="9aad9-146">Lai sāktu bagātināšanas procesu, komandjoslā atlasiet **Palaist**.</span><span class="sxs-lookup"><span data-stu-id="9aad9-146">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="9aad9-147">Varat arī ļaut sistēmai palaist bagātināšanu automātiski kā daļu no [plānotās atsvaidzināšanas](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="9aad9-147">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="9aad9-148">Apstrādes laiks ir atkarīgs no klientu datu lieluma.</span><span class="sxs-lookup"><span data-stu-id="9aad9-148">The processing time depends on the size of your customer data.</span></span>

<span data-ttu-id="9aad9-149">Pēc bagātināšanas procesa noslēgšanas varat pārskatīt tikko bagātinātos klientu profilu datus, dodoties uz sadaļu **Mana bagātināšana**.</span><span class="sxs-lookup"><span data-stu-id="9aad9-149">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="9aad9-150">Turklāt jūs redzēsit pēdējā atjauninājuma laiku un bagātināto profilu skaitu.</span><span class="sxs-lookup"><span data-stu-id="9aad9-150">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="9aad9-151">Jūs varat piekļūt detalizētam katra bagātināta profila skatam, atlasot opciju **Skatīt bagātinātos datus**.</span><span class="sxs-lookup"><span data-stu-id="9aad9-151">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="9aad9-152">Nākamās darbības</span><span class="sxs-lookup"><span data-stu-id="9aad9-152">Next steps</span></span>

<span data-ttu-id="9aad9-153">Pilnveidojiet savus bagātinātos klientu datus.</span><span class="sxs-lookup"><span data-stu-id="9aad9-153">Build on top of your enriched customer data.</span></span> <span data-ttu-id="9aad9-154">Veidojiet [segmentus](segments.md) un [pasākumus](measures.md) un pat [eksportējiet datus](export-destinations.md), lai nodrošinātu klientiem personalizētu pieredzi.</span><span class="sxs-lookup"><span data-stu-id="9aad9-154">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
