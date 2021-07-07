---
title: Mēru izveide un pārvaldība
description: Definējiet mērus, lai analizētu un atspoguļotu sava uzņēmuma veiktspēju.
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: a83caf2428f3dbd9791b9f746d00d370362a508c
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304808"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="ab2e3-103">Mēru definēšana un pārvaldība</span><span class="sxs-lookup"><span data-stu-id="ab2e3-103">Define and manage measures</span></span>

<span data-ttu-id="ab2e3-104">Mēri palīdz labāk izprast klientu paradumus un uzņēmuma veiktspēju.</span><span class="sxs-lookup"><span data-stu-id="ab2e3-104">Measures help you to better understand customer behaviors and business performance.</span></span> <span data-ttu-id="ab2e3-105">Tie aplūko atbilstošās vērtības no [vienotajiem profiliem](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="ab2e3-105">They look at relevant values from [unified profiles](data-unification.md).</span></span> <span data-ttu-id="ab2e3-106">Piemēram, uzņēmums vēlas redzēt *kopējos tēriņus uz klientu*, lai izprastu katra klienta pirkumu vēsturi vai izmērīt *uzņēmuma kopējos pārdošanas apjomus*, lai izprastu kopējā līmeņa ieņēmumus visā uzņēmumā.</span><span class="sxs-lookup"><span data-stu-id="ab2e3-106">For example, a business wants to see the *total spend per customer* to understand an individual customer’s purchase history or measure *total sales of the company* to understand the aggregate-level revenue in the whole business.</span></span>  

<span data-ttu-id="ab2e3-107">Mēri tiek izveidoti, izmantojot mērījumu veidotāju, datu vaicājumu platformu ar dažādiem operatoriem un vienkāršām kartēšanas opcijām.</span><span class="sxs-lookup"><span data-stu-id="ab2e3-107">Measures are created using the measure builder, a data query platform with various operators and simple mapping options.</span></span> <span data-ttu-id="ab2e3-108">Tas ļauj filtrēt datus, grupēt rezultātus, noteikt [entītiju attiecību ceļus](relationships.md) un priekšskatīt izvadi.</span><span class="sxs-lookup"><span data-stu-id="ab2e3-108">It lets you filter the data, group results, detect [entity relationship paths](relationships.md), and preview the output.</span></span>

<span data-ttu-id="ab2e3-109">Izmantojiet mērījumu veidotāju, lai plānotu uzņēmuma aktivitātes, vaicājot klientu datus un izgūstot ieskatus.</span><span class="sxs-lookup"><span data-stu-id="ab2e3-109">Use the measure builder to plan business activities by querying customer data and extract insights.</span></span> <span data-ttu-id="ab2e3-110">Piemēram, *katra klienta kopējo tēriņu* un *katra klienta kopējo ienākumu* mēra izveide palīdz identificēt klientu grupu, kuriem ir augsti tēriņi, bet arī augsti ieņēmumi.</span><span class="sxs-lookup"><span data-stu-id="ab2e3-110">For example, creating a measure of *total spend per customer* and *total return per customer* helps identify a group of customers with high spend yet high return.</span></span> <span data-ttu-id="ab2e3-111">Varat [izveidot segmentu](segments.md), lai vadītu nākamās, vislabāk piemērotās darbības.</span><span class="sxs-lookup"><span data-stu-id="ab2e3-111">You can [create a segment](segments.md) to drive next best actions.</span></span> 

## <a name="build-your-own-measure-from-scratch"></a><span data-ttu-id="ab2e3-112">Personīgā mērījuma izveide no nulles</span><span class="sxs-lookup"><span data-stu-id="ab2e3-112">Build your own measure from scratch</span></span>

<span data-ttu-id="ab2e3-113">Šajā sadaļā ir paskaidrots, kā izveidot jaunu mērījumu no nulles.</span><span class="sxs-lookup"><span data-stu-id="ab2e3-113">This section walks you through creating a new measure from scratch.</span></span> <span data-ttu-id="ab2e3-114">Varat izveidot mērījumu ar datu atribūtiem no datu entītijām, kurām ir iestatītas attiecības, lai izveidotu savienojumu ar Klienta entītiju.</span><span class="sxs-lookup"><span data-stu-id="ab2e3-114">You can build a measure with data attributes from data entities that have a relationship set up to connect with the Customer entity.</span></span> 

1. <span data-ttu-id="ab2e3-115">Auditorijas ieskatu sadaļā ejiet uz **Mēri**.</span><span class="sxs-lookup"><span data-stu-id="ab2e3-115">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="ab2e3-116">Atlasiet **Jauns** un izvēlieties **Izveidot savu**.</span><span class="sxs-lookup"><span data-stu-id="ab2e3-116">Select **New** and choose **Build your own**.</span></span>

1. <span data-ttu-id="ab2e3-117">Atlasiet **Rediģēt nosaukumu** un norādiet mēra **Nosaukumu**.</span><span class="sxs-lookup"><span data-stu-id="ab2e3-117">Select **Edit name** and provide a **Name** for the measure.</span></span> 
   > [!NOTE]
   > <span data-ttu-id="ab2e3-118">Ja jaunajā mērījuma konfigurācijā ir tikai divi lauki – CustomerID un viens aprēķins – izvade sistēmas ģenerētajā entītijā tiks pievienota kā jauna kolonna ar nosaukumu Customer_Measure.</span><span class="sxs-lookup"><span data-stu-id="ab2e3-118">If your new measure configuration has only two fields—for example, CustomerID and one calculation—the output will be added as a new column to the system-generated entity called Customer_Measure.</span></span> <span data-ttu-id="ab2e3-119">Un mēra vērtību varēsit redzēt vienotā klienta profilā.</span><span class="sxs-lookup"><span data-stu-id="ab2e3-119">And you will be able to see the measure’s value in the unified customer profile.</span></span> <span data-ttu-id="ab2e3-120">Citi mērījumi ģenerēs savas entītijas.</span><span class="sxs-lookup"><span data-stu-id="ab2e3-120">Other measures will generate their own entities.</span></span>

1. <span data-ttu-id="ab2e3-121">Konfigurācijas apgabalā izvēlieties apkopošanas funkciju no **Atlasīt funkciju** nolaižamās izvēlnes.</span><span class="sxs-lookup"><span data-stu-id="ab2e3-121">In the configuration area, choose the aggregation function from the **Select Function** dropdown menu.</span></span> <span data-ttu-id="ab2e3-122">Apkopošanas funkcijas ir šādas:</span><span class="sxs-lookup"><span data-stu-id="ab2e3-122">Aggregation functions include:</span></span> 
   - <span data-ttu-id="ab2e3-123">**Sum**</span><span class="sxs-lookup"><span data-stu-id="ab2e3-123">**Sum**</span></span>
   - <span data-ttu-id="ab2e3-124">**Vidējais**</span><span class="sxs-lookup"><span data-stu-id="ab2e3-124">**Average**</span></span>
   - <span data-ttu-id="ab2e3-125">**Skaits**</span><span class="sxs-lookup"><span data-stu-id="ab2e3-125">**Count**</span></span>
   - <span data-ttu-id="ab2e3-126">**Skaitīt unikālos vienumus**</span><span class="sxs-lookup"><span data-stu-id="ab2e3-126">**Count Unique**</span></span>
   - <span data-ttu-id="ab2e3-127">**Maksimums**</span><span class="sxs-lookup"><span data-stu-id="ab2e3-127">**Max**</span></span>
   - <span data-ttu-id="ab2e3-128">**Minimums**</span><span class="sxs-lookup"><span data-stu-id="ab2e3-128">**Min**</span></span>
   - <span data-ttu-id="ab2e3-129">**Pirmā**: tiek ņemta pirmā datu ieraksta vērtība</span><span class="sxs-lookup"><span data-stu-id="ab2e3-129">**First**: takes the first value of the data record</span></span>
   - <span data-ttu-id="ab2e3-130">**Pēdējā**: tiek ņemta pēdējā vērtība, kas tika pievienota datu ierakstam</span><span class="sxs-lookup"><span data-stu-id="ab2e3-130">**Last**: takes the last value that was added to the data record</span></span>

   :::image type="content" source="media/measure-operators.png" alt-text="Mēru aprēķinu operatori.":::

1. <span data-ttu-id="ab2e3-132">Atlasiet vienumu **Pievienot atribūtu**, lai atlasītu datus, kas nepieciešami šī mēra izveidei.</span><span class="sxs-lookup"><span data-stu-id="ab2e3-132">Select **Add attribute** to select the data you need to create this measure.</span></span>
   
   1. <span data-ttu-id="ab2e3-133">Atlasiet cilni **Atribūti**.</span><span class="sxs-lookup"><span data-stu-id="ab2e3-133">Select the **Attributes** tab.</span></span> 
   1. <span data-ttu-id="ab2e3-134">Datu entītija: izvēlieties entītiju, kurā iekļauts mēra atribūts, ko vēlaties aprēķināt.</span><span class="sxs-lookup"><span data-stu-id="ab2e3-134">Data entity: Choose the entity that includes the attribute you want to measure.</span></span> 
   1. <span data-ttu-id="ab2e3-135">Datu atribūts: izvēlieties atribūtu, ko vēlaties izmantot apkopošanas funkcijai, lai aprēķinātu mēru.</span><span class="sxs-lookup"><span data-stu-id="ab2e3-135">Data attribute: Choose the attribute you want to use in the aggregation function to calculate the measure.</span></span> <span data-ttu-id="ab2e3-136">Vienlaikus vienā reizē var atlasīt tikai vienu atribūtu.</span><span class="sxs-lookup"><span data-stu-id="ab2e3-136">You can only select one attribute at a time.</span></span>
   1. <span data-ttu-id="ab2e3-137">Atlasiet arī esoša mēra datu atribūtu, atlasot **Mērījumi** cilni. Varat arī meklēt entītijas vai mēra nosaukumu.</span><span class="sxs-lookup"><span data-stu-id="ab2e3-137">You can also select a data attribute from an existing measure by selecting the **Measures** tab. Or, you can search for an entity or measure name.</span></span> 
   1. <span data-ttu-id="ab2e3-138">Atlasiet vienumu **Pievienot**, lai mēram pievienotu atlasīto atribūtu.</span><span class="sxs-lookup"><span data-stu-id="ab2e3-138">Select **Add** to add the selected attribute to the measure.</span></span>

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Atlasiet atribūtu, ko izmantot mērījumā.":::

1. <span data-ttu-id="ab2e3-140">Lai izveidotu sarežģītākus mērījumus, to funkcijai var pievienot papildu atribūtus vai lietot matemātikas operatorus.</span><span class="sxs-lookup"><span data-stu-id="ab2e3-140">To build more complex measures, you can add more attributes or use math operators on your measure function.</span></span>

   :::image type="content" source="media/measure-math-operators.png" alt-text="Sarežģītu mērījumu izveide, izmantojot matemātikas operatorus.":::

1. <span data-ttu-id="ab2e3-142">Lai pievienotu filtrus, konfigurācijas apgabalā atlasiet **Filtri**.</span><span class="sxs-lookup"><span data-stu-id="ab2e3-142">To add filters, select the **Filter** in the configuration area.</span></span> 
  
   1. <span data-ttu-id="ab2e3-143">Sadaļā **Pievienot atribūtu**, kas atrodas **Filtru** rūtī, atlasiet atribūtu, ko vēlaties izmantot, lai izveidotu filtru.</span><span class="sxs-lookup"><span data-stu-id="ab2e3-143">In the **Add attribute** section of the **Filters** pane, select the attribute you want to use to create filters.</span></span>
   1. <span data-ttu-id="ab2e3-144">Iestatiet filtra operatorus, lai definētu filtru katram atlasītajam atribūtam.</span><span class="sxs-lookup"><span data-stu-id="ab2e3-144">Set the filter operators to define the filter for every selected attribute.</span></span>
   1. <span data-ttu-id="ab2e3-145">Atlasiet vienumu **Lietot**, lai mērījumam pievienotu filtrus.</span><span class="sxs-lookup"><span data-stu-id="ab2e3-145">Select **Apply** to add the filters to the measure.</span></span>

1. <span data-ttu-id="ab2e3-146">Lai pievienotu dimensijas, konfigurācijas apgabalā atlasiet **Dimensija**.</span><span class="sxs-lookup"><span data-stu-id="ab2e3-146">To add dimensions, select **Dimension** in the configuration area.</span></span> <span data-ttu-id="ab2e3-147">Dimensijas tiek rādītas kā kolonnas mērījuma izvades entītijā.</span><span class="sxs-lookup"><span data-stu-id="ab2e3-147">Dimensions will show as columns in the measure output entity.</span></span>
 
   1. <span data-ttu-id="ab2e3-148">Atlasiet vienumu **Rediģēt dimensijas**, lai pievienotu datu atribūtus, pēc kuriem vēlaties grupēt mērus.</span><span class="sxs-lookup"><span data-stu-id="ab2e3-148">Select **Edit dimensions** to add data attributes you want to group the measure values by.</span></span> <span data-ttu-id="ab2e3-149">Piemēram, pilsēta vai dzimums.</span><span class="sxs-lookup"><span data-stu-id="ab2e3-149">For example, city or gender.</span></span> <span data-ttu-id="ab2e3-150">Pēc noklusējuma *CustomerID* dimensija tiek atlasīta, lai izveidotu *klienta līmeņa mērījumus*.</span><span class="sxs-lookup"><span data-stu-id="ab2e3-150">By default, the *CustomerID* dimension is selected to create *customer-level measures*.</span></span> <span data-ttu-id="ab2e3-151">Ja vēlaties izveidot *uzņēmuma līmeņa mērījumus*, varat noņemt noklusējuma dimensiju.</span><span class="sxs-lookup"><span data-stu-id="ab2e3-151">You can remove the default dimension if you want to create *business-level measures*.</span></span>
   1. <span data-ttu-id="ab2e3-152">Atlasiet vienumu **Pabeigts**, lai mērījumam pievienotu dimensijas.</span><span class="sxs-lookup"><span data-stu-id="ab2e3-152">Select **Done** to add the dimensions to the measure.</span></span>

1. <span data-ttu-id="ab2e3-153">Ja jūsu datos ir vērtības, kuras ir jāaizstāj ar veselu skaitli, piemēram, aizstājot *nulle* ar *0*, atlasiet **Kārtulas**.</span><span class="sxs-lookup"><span data-stu-id="ab2e3-153">If there are values in your data that you need to replace with an integer—for example, replace *null* with *0*—select **Rules**.</span></span> <span data-ttu-id="ab2e3-154">Konfigurējiet kārtulu un pārliecinieties, ka kā aizstājējus izvēlējāties tikai veselus skaitļus.</span><span class="sxs-lookup"><span data-stu-id="ab2e3-154">Configure the rule and make sure that you choose only whole numbers as replacements.</span></span>

1. <span data-ttu-id="ab2e3-155">Ja starp kartēto datu entītiju un *Klienta* entītiju ir vairāki ceļi, ir jāizvēlas viens no identificētajiem [entītiju attiecību ceļiem](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="ab2e3-155">If there are multiple paths between the data entity you mapped and the *Customer* entity, you have to choose one of the identified [entity relationship paths](relationships.md).</span></span> <span data-ttu-id="ab2e3-156">Mērījumu rezultāti var atšķirties atkarībā no atlasītā ceļa.</span><span class="sxs-lookup"><span data-stu-id="ab2e3-156">Measure results can vary depending on the selected path.</span></span> 
   
   1. <span data-ttu-id="ab2e3-157">Atlasiet **Datu preferences** un izvēlieties entītijas ceļu, kas jāizmanto mēra identificēšanai.</span><span class="sxs-lookup"><span data-stu-id="ab2e3-157">Select **Data preferences** and choose the entity path that should be used to identify your measure.</span></span> <span data-ttu-id="ab2e3-158">Ja entītijai *Klients* ir tikai viens ceļš, šī vadīkla netiks rādīta.</span><span class="sxs-lookup"><span data-stu-id="ab2e3-158">If there's only a single path to the *Customer* entity, this control won't show.</span></span>
   1. <span data-ttu-id="ab2e3-159">Atlasiet **Pabeigts**, lai lietotu jūsu atlasi.</span><span class="sxs-lookup"><span data-stu-id="ab2e3-159">Select **Done** to apply your selection.</span></span> 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Atlasiet entītijas ceļu mēram.":::

1. <span data-ttu-id="ab2e3-161">Lai mērījumam pievienotu papildu aprēķinus, atlasiet **Jauns aprēķins**.</span><span class="sxs-lookup"><span data-stu-id="ab2e3-161">To add more calculations for the measure, select **New calculation**.</span></span> <span data-ttu-id="ab2e3-162">Entītijas var izmantot tikai tajā pašā entītijas ceļā jauniem aprēķiniem.</span><span class="sxs-lookup"><span data-stu-id="ab2e3-162">You can only use entities on the same entity path for new calculations.</span></span> <span data-ttu-id="ab2e3-163">Papildu aprēķini tiek rādīti kā jaunas kolonnas mērījumu izvades entītijā.</span><span class="sxs-lookup"><span data-stu-id="ab2e3-163">More calculations will show as new columns in the measure output entity.</span></span>

1. <span data-ttu-id="ab2e3-164">Aprēķinā atlasiet **...**, lai **Dublētu**, **Pārdēvētu** vai **Noņemtu** aprēķinu no mērījuma.</span><span class="sxs-lookup"><span data-stu-id="ab2e3-164">Select **...** on the calculation to **Duplicate**, **Rename**, or **Remove** a calculation from a measure.</span></span>

1. <span data-ttu-id="ab2e3-165">**Priekšskatījuma** apgabalā redzēsit izvades entītijas mērījuma datu shēmu, tostarp filtrus un dimensijas.</span><span class="sxs-lookup"><span data-stu-id="ab2e3-165">In the **Preview** area, you'll see the data schema of the measure output entity, including filters and dimensions.</span></span> <span data-ttu-id="ab2e3-166">Priekšskatījums dinamiski reaģē uz konfigurācijas izmaiņām.</span><span class="sxs-lookup"><span data-stu-id="ab2e3-166">The preview reacts dynamically to changes in the configuration.</span></span>

1. <span data-ttu-id="ab2e3-167">Atlasiet opciju **Izpildīt**, lai aprēķinātu konfigurētā mērījuma rezultātus.</span><span class="sxs-lookup"><span data-stu-id="ab2e3-167">Select **Run** to calculate results for the configured measure.</span></span> <span data-ttu-id="ab2e3-168">Atlasiet **Saglabāt un aizvērt**, ja vēlaties saglabāt pašreizējo konfigurāciju un izpildīt mērījumu vēlāk.</span><span class="sxs-lookup"><span data-stu-id="ab2e3-168">Select **Save and close** if you want to keep the current configuration and run the measure later.</span></span>

1. <span data-ttu-id="ab2e3-169">Dodieties uz **Mērījumi**, lai sarakstā redzētu jaunizveidoto mērījumu.</span><span class="sxs-lookup"><span data-stu-id="ab2e3-169">Go to **Measures** to see the newly created measure in the list.</span></span>

## <a name="use-a-template-to-build-a-measure"></a><span data-ttu-id="ab2e3-170">Veidnes izmantošana mērījuma veidošanā</span><span class="sxs-lookup"><span data-stu-id="ab2e3-170">Use a template to build a measure</span></span>

<span data-ttu-id="ab2e3-171">Lai izveidotu bieži izmantotus mērījumus, varat lietot to iepriekš definētās veidnes.</span><span class="sxs-lookup"><span data-stu-id="ab2e3-171">You can use predefined templates of commonly used measures to create them.</span></span> <span data-ttu-id="ab2e3-172">Detalizēti veidņu apraksti un vadība palīdzēs jums sekmīgi izveidot mērījumu.</span><span class="sxs-lookup"><span data-stu-id="ab2e3-172">Detailed descriptions of the templates and a guided experience help you with efficient measure creation.</span></span> <span data-ttu-id="ab2e3-173">Veidnes tiek veidotas uz kartētajiem datiem no *Vienotās darbības* entitījas.</span><span class="sxs-lookup"><span data-stu-id="ab2e3-173">Templates build on mapped data from the *Unified Activity* entity.</span></span> <span data-ttu-id="ab2e3-174">Tāpēc, pirms no veidnes izveidojat mērījumu, pārliecinieties, ka esat konfigurējuši [klientu darbības](activities.md).</span><span class="sxs-lookup"><span data-stu-id="ab2e3-174">So make sure you have configured [customer activities](activities.md) before you create a measure from a template.</span></span>

<span data-ttu-id="ab2e3-175">Pieejamās mērījumu veidnes:</span><span class="sxs-lookup"><span data-stu-id="ab2e3-175">Available measure templates:</span></span> 
- <span data-ttu-id="ab2e3-176">Vidējā transakcijas vērtība (ATV)</span><span class="sxs-lookup"><span data-stu-id="ab2e3-176">Average transaction value (ATV)</span></span>
- <span data-ttu-id="ab2e3-177">Kopējā transakciju vērtība</span><span class="sxs-lookup"><span data-stu-id="ab2e3-177">Total transaction value</span></span>
- <span data-ttu-id="ab2e3-178">Vidējie ieņēmumi dienā</span><span class="sxs-lookup"><span data-stu-id="ab2e3-178">Average daily revenue</span></span>
- <span data-ttu-id="ab2e3-179">Gada vidējie ieņēmumi</span><span class="sxs-lookup"><span data-stu-id="ab2e3-179">Average yearly revenue</span></span>
- <span data-ttu-id="ab2e3-180">Transakciju skaits</span><span class="sxs-lookup"><span data-stu-id="ab2e3-180">Transaction count</span></span>
- <span data-ttu-id="ab2e3-181">Iegūtie lojalitātes punkti</span><span class="sxs-lookup"><span data-stu-id="ab2e3-181">Loyalty points earned</span></span>
- <span data-ttu-id="ab2e3-182">Izmantotie lojalitātes punkti</span><span class="sxs-lookup"><span data-stu-id="ab2e3-182">Loyalty points redeemed</span></span>
- <span data-ttu-id="ab2e3-183">Lojalitātes punktu bilance</span><span class="sxs-lookup"><span data-stu-id="ab2e3-183">Loyalty points balance</span></span>
- <span data-ttu-id="ab2e3-184">Klienta aktivitātes laika periods</span><span class="sxs-lookup"><span data-stu-id="ab2e3-184">Active customer lifespan</span></span>
- <span data-ttu-id="ab2e3-185">Dalības ilgums lojalitātes programmā</span><span class="sxs-lookup"><span data-stu-id="ab2e3-185">Loyalty membership duration</span></span>
- <span data-ttu-id="ab2e3-186">Laiks kopš pēdējā pirkuma</span><span class="sxs-lookup"><span data-stu-id="ab2e3-186">Time since last purchase</span></span>

<span data-ttu-id="ab2e3-187">Šajā procedūrā aprakstītas darbības jauna mērījuma izveidei, izmantojot veidni.</span><span class="sxs-lookup"><span data-stu-id="ab2e3-187">The following procedure outlines the steps to build a new measure using a template.</span></span>

1. <span data-ttu-id="ab2e3-188">Sadaļā Auditorijas ieskati ejiet uz **Mēri**.</span><span class="sxs-lookup"><span data-stu-id="ab2e3-188">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="ab2e3-189">Atlasiet **Jauns** un atlasiet **Izvēlieties veidni**.</span><span class="sxs-lookup"><span data-stu-id="ab2e3-189">Select **New** and select **Choose a template**.</span></span>

   :::image type="content" source="media/measure-use-template.png" alt-text="Nolaižamās izvēlnes ekrānuzņēmums, veidojot jaunu mērījumu ar iezīmētu veidni.":::

1. <span data-ttu-id="ab2e3-191">Atrodiet sev atbilstošo veidni un atlasiet **Izvēlēties veidni**.</span><span class="sxs-lookup"><span data-stu-id="ab2e3-191">Find the template that fits your need and select **Choose template**.</span></span>

1. <span data-ttu-id="ab2e3-192">Pārskatiet prasītos datus un atlasiet **Sākt darbu**, ja visi dati ir pareizi.</span><span class="sxs-lookup"><span data-stu-id="ab2e3-192">Review the required data and select **Get started** if you have all the data in place.</span></span>

1. <span data-ttu-id="ab2e3-193">Rūtī **Rediģēt nosaukumu** ievadiet sava mērījuma nosaukumu un izvades entitīju.</span><span class="sxs-lookup"><span data-stu-id="ab2e3-193">In the **Edit name** pane, set the name for your measure and the output entity.</span></span> 

1. <span data-ttu-id="ab2e3-194">Atlasiet **Gatavs**.</span><span class="sxs-lookup"><span data-stu-id="ab2e3-194">Select **Done**.</span></span>

1. <span data-ttu-id="ab2e3-195">Sadaļā **Iestatīt laikposmu** definējiet lietojamo datu laika periodu.</span><span class="sxs-lookup"><span data-stu-id="ab2e3-195">In the **Set time period** section, define the time frame of the data to use.</span></span> <span data-ttu-id="ab2e3-196">Izvēlieties, vai jaunajam mērījumam jāaptver visa datu kopa, atlasot **Viss laiks**, vai vēlaties, lai mērījums koncentrētos uz **Noteiktu laika periodu**.</span><span class="sxs-lookup"><span data-stu-id="ab2e3-196">Choose if you want the new measure to cover the entire dataset by selecting **All time**, or if you want the measure to focus on a **Specific time period**.</span></span>

   :::image type="content" source="media/measure-set-time-period.png" alt-text="Ekrānuzņēmums, kurā redzama laika perioda sadaļa, kad mērījumu konfigurē no veidnes.":::

1. <span data-ttu-id="ab2e3-198">Nākamajā sadaļā atlasiet **Pievienot datus**, lai izvēlētos darbībs un kartētu atbilstošos datus no savas *Vienotās darbības* entitījas.</span><span class="sxs-lookup"><span data-stu-id="ab2e3-198">In the next section, select **Add data** to choose the activities and map the corresponding data from your *Unified Activity* entity.</span></span>

    1. <span data-ttu-id="ab2e3-199">1. darbība no 2: Sadaļā **Darbības veids** izvēlieties entitījas veidu, kuru vēlaties lietot.</span><span class="sxs-lookup"><span data-stu-id="ab2e3-199">Step 1 of 2: Under **Activity type**, choose the type of the entity you want to use.</span></span> <span data-ttu-id="ab2e3-200">**Darbībām** atlasiet entitījas, kuras vēlaties kartēt.</span><span class="sxs-lookup"><span data-stu-id="ab2e3-200">For **Activities**, select the entities you want to map.</span></span>
    1. <span data-ttu-id="ab2e3-201">2. darbība no 2: Atlasiet atribūtu no *Vienotās darbības* entitījas formulas prasītajam komponentam.</span><span class="sxs-lookup"><span data-stu-id="ab2e3-201">Step 2 of 2: Choose the attribute from the *Unified Activity* entity for the component required by the formula.</span></span> <span data-ttu-id="ab2e3-202">Piemēram, vidējai transakcijas vērtībai tas ir komponents, kas apzīmē transakcijas vērtību.</span><span class="sxs-lookup"><span data-stu-id="ab2e3-202">For example, for Average transaction value, it's the attribute representing the Transaction value.</span></span> <span data-ttu-id="ab2e3-203">**Darbības laikspiedolam** atlasiet atribūtu no Vienotās darbības entitījas, kas apzīmē darbības datumu un laiku.</span><span class="sxs-lookup"><span data-stu-id="ab2e3-203">For **Activity timestamp**, choose the attribute from the Unified Activity entity that represents the date and time of the activity.</span></span>
   
1. <span data-ttu-id="ab2e3-204">Kad datu kartēšana ir izdevusies, varat redzēt statusu kā **Pabeigts** un kartēto darbību un atribūtu nosaukumu.</span><span class="sxs-lookup"><span data-stu-id="ab2e3-204">Once the data mapping is successful, you can see the status as **Complete** and the name of the mapped activities and attributes.</span></span>

   :::image type="content" source="media/measure-template-configured.png" alt-text="Ekrānuzņēmums pabeigtai mērījuma veidnes konfigurēšanai.":::

1. <span data-ttu-id="ab2e3-206">Tagad varat atlasīt **Palaist**, lai aprēķinātu mērījuma rezultātus.</span><span class="sxs-lookup"><span data-stu-id="ab2e3-206">You can now select **Run** to calculate the results of the measure.</span></span> <span data-ttu-id="ab2e3-207">Lai to precizētu vēlāk, atlasiet **Saglabāt melnrakstu**.</span><span class="sxs-lookup"><span data-stu-id="ab2e3-207">To refine it later, select **Save draft**.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="ab2e3-208">Pārvaldiet savus mērus</span><span class="sxs-lookup"><span data-stu-id="ab2e3-208">Manage your measures</span></span>

<span data-ttu-id="ab2e3-209">Mērījumu saraksts atrodams lapā **Mērījumi**.</span><span class="sxs-lookup"><span data-stu-id="ab2e3-209">You can find the list of measures on the **Measures** page.</span></span>

<span data-ttu-id="ab2e3-210">Atradīsiet informāciju par mēra tipu, izveidotāju, izveides datumu, statusu un stāvokli.</span><span class="sxs-lookup"><span data-stu-id="ab2e3-210">You'll find information about the measure type, the creator, creation date, status, and state.</span></span> <span data-ttu-id="ab2e3-211">Kad sarakstā atlasāt kādu mēru, varat priekšskatīt izvadi un lejupielādēt CSV failu.</span><span class="sxs-lookup"><span data-stu-id="ab2e3-211">When you select a measure from the list, you can preview the output and download a CSV file.</span></span>

<span data-ttu-id="ab2e3-212">Lai vienlaikus atsvaidzinātu visus mērus, atlasiet **Atsvaidzināt visu**, neatlasot noteiktu mēru.</span><span class="sxs-lookup"><span data-stu-id="ab2e3-212">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ab2e3-213">![Darbības, lai pārvaldītu atsevišķus mērus.](media/measure-actions.png "Darbības, lai pārvaldītu atsevišķus mērus.")</span><span class="sxs-lookup"><span data-stu-id="ab2e3-213">![Actions to manage single measures.](media/measure-actions.png "Actions to manage single measures.")</span></span>

<span data-ttu-id="ab2e3-214">Sarakstā atlasiet mēru, lai izvēlētos kādu no šīm opcijām:</span><span class="sxs-lookup"><span data-stu-id="ab2e3-214">Select a measure from the list for the following options:</span></span>

- <span data-ttu-id="ab2e3-215">Atlasiet mēra nosaukumu, lai skatītu tā detalizētu informāciju.</span><span class="sxs-lookup"><span data-stu-id="ab2e3-215">Select the measure name to see its details.</span></span>
- <span data-ttu-id="ab2e3-216">**Rediģējiet** mēra konfigurāciju.</span><span class="sxs-lookup"><span data-stu-id="ab2e3-216">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="ab2e3-217">**Atsvaidzināt** mēru, pamatojoties uz jaunākajiem datiem.</span><span class="sxs-lookup"><span data-stu-id="ab2e3-217">**Refresh** the measure based on the latest data.</span></span>
- <span data-ttu-id="ab2e3-218">**Pārdēvējiet** mēru.</span><span class="sxs-lookup"><span data-stu-id="ab2e3-218">**Rename** the measure.</span></span>
- <span data-ttu-id="ab2e3-219">**Dzēsiet** mēru.</span><span class="sxs-lookup"><span data-stu-id="ab2e3-219">**Delete** the measure.</span></span>
- <span data-ttu-id="ab2e3-220">**Aktivizēt** vai **Deaktivizēt**.</span><span class="sxs-lookup"><span data-stu-id="ab2e3-220">**Activate** or **Deactivate**.</span></span> <span data-ttu-id="ab2e3-221">Neaktīvie mēri netiks atsvaidzināti [plānotās atsvaidzināšanas laikā](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="ab2e3-221">Inactive measures won't get refreshed during a [scheduled refresh](system.md#schedule-tab).</span></span>

> [!TIP]
> <span data-ttu-id="ab2e3-222">Uzdevumiem/procesiem ir [seši statusu tipi](system.md#status-types).</span><span class="sxs-lookup"><span data-stu-id="ab2e3-222">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="ab2e3-223">Turklāt vairums procesu [ir atkarīgi no citiem pakārtotiem procesiem](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="ab2e3-223">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="ab2e3-224">Varat atlasīt procesa statusu, lai skatītu detalizētu informāciju par visa uzdevuma norisi.</span><span class="sxs-lookup"><span data-stu-id="ab2e3-224">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="ab2e3-225">Atlasot opciju **Skatīt detalizētu informāciju** par kādu no uzdevumiem, jums tiks sniegta papildinformācija: apstrādes laiks, pēdējās apstrādes datums un visas ar uzdevumu saistītās kļūdas un brīdinājumi.</span><span class="sxs-lookup"><span data-stu-id="ab2e3-225">After selecting **See details** for one of the job's tasks, you'll find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="ab2e3-226">Nākamā darbība</span><span class="sxs-lookup"><span data-stu-id="ab2e3-226">Next step</span></span>

<span data-ttu-id="ab2e3-227">Esošus mērus var izmantot, lai izveidotu [klientu segmentu](segments.md).</span><span class="sxs-lookup"><span data-stu-id="ab2e3-227">You can use existing measures to create [a customer segment](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
