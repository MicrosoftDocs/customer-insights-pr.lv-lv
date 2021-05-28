---
title: Pasākumu izveide un pārvaldība
description: Definējiet pasākumus, lai analizētu un atspoguļotu sava uzņēmuma veiktspēju.
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 402e5ef3515bce0e6f56788781b7bd909738aaa6
ms.sourcegitcommit: b833e333745d321edeaf96d3ed14458cbce02ff1
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 05/17/2021
ms.locfileid: "6049259"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="cc05a-103">Definējiet un pārvaldiet mērus</span><span class="sxs-lookup"><span data-stu-id="cc05a-103">Define and manage measures</span></span>

<span data-ttu-id="cc05a-104">Mērījumi palīdz labāk izprast klientu paradumus un uzņēmuma veiktspēju.</span><span class="sxs-lookup"><span data-stu-id="cc05a-104">Measures help you to better understand customer behaviors and business performance.</span></span> <span data-ttu-id="cc05a-105">Tie aplūko atbilstošās vērtības no [vienotajiem profiliem](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="cc05a-105">They look at relevant values from [unified profiles](data-unification.md).</span></span> <span data-ttu-id="cc05a-106">Piemēram, uzņēmums vēlas aplūkot *kopējos tēriņus uz klientu*, lai izprastu katra atsevišķā klienta pirkumu vēsturi vai mērītu *kopējos uzņēmuma pārdošanas rādītājus*, lai izprastu kopīgos visa uzņēmuma ieņēmumus.</span><span class="sxs-lookup"><span data-stu-id="cc05a-106">For example, a business wants to see the *total spend per customer* to understand individual customer’s purchase history or measure *total sales of the company* to understand the aggregate-level revenue in the whole business.</span></span>  

<span data-ttu-id="cc05a-107">Pasākumi tiek izveidoti, izmantojot pasākumu veidotāju, datu vaicājumu platformu ar dažādiem operatoriem un vienkāršām kartēšanas opcijām.</span><span class="sxs-lookup"><span data-stu-id="cc05a-107">Measures are created using the measure builder, a data query platform with various operators and simple mapping options.</span></span> <span data-ttu-id="cc05a-108">Tas ļauj filtrēt datus, grupēt rezultātus, noteikt [entītiju attiecību ceļus](relationships.md) un priekšskatīt izvadi.</span><span class="sxs-lookup"><span data-stu-id="cc05a-108">It lets you filter the data, group results, detect [entity relationship paths](relationships.md), and preview the output.</span></span>

<span data-ttu-id="cc05a-109">Izmantojiet pasākumu veidotāju, kas tiek plānots biznesa aktivitātēm, vaicājot klientu datus un izvelkot ieskatus.</span><span class="sxs-lookup"><span data-stu-id="cc05a-109">Use the measure builder to plan business activities by querying customer data and extract insights.</span></span> <span data-ttu-id="cc05a-110">Piemēram, *katra klienta kopējo tēriņu* un *katra klienta kopējo ienākumu* pasākumu izveide palīdz identificēt klientu grupu, kuriem ir augsti tēriņi, bet augsti ieņēmumi.</span><span class="sxs-lookup"><span data-stu-id="cc05a-110">For example, creating a measure of *total spend per customer* and *total return per customer* helps identify a group of customers with high spend yet high return.</span></span> <span data-ttu-id="cc05a-111">Varat [izveidot segmentu](segments.md), lai vadītu nākamās, vislabāk piemērotās darbības.</span><span class="sxs-lookup"><span data-stu-id="cc05a-111">You can [create a segment](segments.md) to drive next best actions.</span></span> 

## <a name="build-your-own-measure-from-scratch"></a><span data-ttu-id="cc05a-112">Personīgā mērījuma izveide no nulles</span><span class="sxs-lookup"><span data-stu-id="cc05a-112">Build your own measure from scratch</span></span>

<span data-ttu-id="cc05a-113">Šajā sadaļā ir skatīts, kā izveidot jaunu pasākumu no nulles.</span><span class="sxs-lookup"><span data-stu-id="cc05a-113">This section walks you through creating a new measure from scratch.</span></span> <span data-ttu-id="cc05a-114">Varat izveidot pasākumu ar datu atribūtiem no datu entītijām, kurām ir iestatītas attiecības, lai izveidotu savienojumu ar Klienta entītiju.</span><span class="sxs-lookup"><span data-stu-id="cc05a-114">You can build a measure with data attributes from data entities that have a relationship set up to connect with the Customer entity.</span></span> 

1. <span data-ttu-id="cc05a-115">Sadaļā Auditorijas ieskati ejiet uz **Mēri**.</span><span class="sxs-lookup"><span data-stu-id="cc05a-115">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="cc05a-116">Atlasiet **Jauns** un izvēlieties **Izveidot savu**.</span><span class="sxs-lookup"><span data-stu-id="cc05a-116">Select **New** and choose **Build your own**.</span></span>

1. <span data-ttu-id="cc05a-117">Atlasiet **Rediģēt nosaukumu** un norādiet pasākumam **Nosaukumu**.</span><span class="sxs-lookup"><span data-stu-id="cc05a-117">Select **Edit name** and provide a **Name** for the measure.</span></span> 
   > [!NOTE]
   > <span data-ttu-id="cc05a-118">Ja jaunajā mērvienību konfigurācijā ir tikai divi lauki, piemēram, CustomerID un viens aprēķins, izvade sistēmas ģenerētajā entītijā tiks pievienota kā jauna kolonna ar nosaukumu Customer_Measure.</span><span class="sxs-lookup"><span data-stu-id="cc05a-118">If your new measure configuration has only two fields, for example, CustomerID and one calculation, the output will be added as a new column to the system generated entity called Customer_Measure.</span></span> <span data-ttu-id="cc05a-119">Un pasākuma vērtību varat redzēt vienotā klienta profilā.</span><span class="sxs-lookup"><span data-stu-id="cc05a-119">And you will be able to see the measure’s value in the unified customer profile.</span></span> <span data-ttu-id="cc05a-120">Citi pasākumi radīs savas entītijas.</span><span class="sxs-lookup"><span data-stu-id="cc05a-120">Other measures will generate their own entities.</span></span>

1. <span data-ttu-id="cc05a-121">Konfigurācijas apgabalā izvēlieties apkopošanas funkciju nolaižamajā izvēlnē **Atlasīt funkciju**.</span><span class="sxs-lookup"><span data-stu-id="cc05a-121">In the configuration area, choose the aggregation function from the **Select Function** drop-down menu.</span></span> <span data-ttu-id="cc05a-122">Apkopošanas funkcijas ir šādas:</span><span class="sxs-lookup"><span data-stu-id="cc05a-122">Aggregation functions include:</span></span> 
   - <span data-ttu-id="cc05a-123">**Sum**</span><span class="sxs-lookup"><span data-stu-id="cc05a-123">**Sum**</span></span>
   - <span data-ttu-id="cc05a-124">**Vidējais**</span><span class="sxs-lookup"><span data-stu-id="cc05a-124">**Average**</span></span>
   - <span data-ttu-id="cc05a-125">**Skaits**</span><span class="sxs-lookup"><span data-stu-id="cc05a-125">**Count**</span></span>
   - <span data-ttu-id="cc05a-126">**Skaitīt unikālos vienumus**</span><span class="sxs-lookup"><span data-stu-id="cc05a-126">**Count Unique**</span></span>
   - <span data-ttu-id="cc05a-127">**Maksimums**</span><span class="sxs-lookup"><span data-stu-id="cc05a-127">**Max**</span></span>
   - <span data-ttu-id="cc05a-128">**Minimums**</span><span class="sxs-lookup"><span data-stu-id="cc05a-128">**Min**</span></span>
   - <span data-ttu-id="cc05a-129">**Pirmā**: tiek ņemta pirmā datu ieraksta vērtība</span><span class="sxs-lookup"><span data-stu-id="cc05a-129">**First**: takes the first value of the data record</span></span>
   - <span data-ttu-id="cc05a-130">**Pēdējā**: tiek ņemta pēdējā vērtība, kas tika pievienota datu ierakstam</span><span class="sxs-lookup"><span data-stu-id="cc05a-130">**Last**: takes the last value that was added to the data record</span></span>

   :::image type="content" source="media/measure-operators.png" alt-text="Operatorus pasākumu aprēķiniem.":::

1. <span data-ttu-id="cc05a-132">Atlasiet vienumu **Pievienot atribūtu**, lai atlasītu datus, kas nepieciešami šī pasākuma izveidei.</span><span class="sxs-lookup"><span data-stu-id="cc05a-132">Select **Add attribute** to select the data you need to create this measure.</span></span>
   
   1. <span data-ttu-id="cc05a-133">Atlasiet cilni **Atribūti**.</span><span class="sxs-lookup"><span data-stu-id="cc05a-133">Select the **Attributes** tab.</span></span> 
   1. <span data-ttu-id="cc05a-134">Datu entītija: izvēlieties entītiju, kurā iekļauts mērvienības atribūts, ko vēlaties aprēķināt.</span><span class="sxs-lookup"><span data-stu-id="cc05a-134">Data entity: Choose the entity that includes the attribute you want to measure.</span></span> 
   1. <span data-ttu-id="cc05a-135">Datu atribūts: izvēlieties atribūtu, ko vēlaties izmantot apkopošanas funkcijai, lai aprēķinātu pasākumu.</span><span class="sxs-lookup"><span data-stu-id="cc05a-135">Data attribute: Choose the attribute you want to use in the aggregation function to calculate the measure.</span></span> <span data-ttu-id="cc05a-136">Vienlaikus vienā reizē var atlasīt tikai vienu atribūtu.</span><span class="sxs-lookup"><span data-stu-id="cc05a-136">You can only select one attribute at a time.</span></span>
   1. <span data-ttu-id="cc05a-137">Atlasiet arī esoša pasākuma datu atribūtu, atlasot **Pasākumi** cilni. Varat arī meklēt entītijas vai pasākuma nosaukumu.</span><span class="sxs-lookup"><span data-stu-id="cc05a-137">You can also select a data attribute from an existing measure by selecting the **Measures** tab. Or, you can search for an entity or measure name.</span></span> 
   1. <span data-ttu-id="cc05a-138">Atlasiet vienumu **Pievienot**, lai pasākumam pievienotu atlasīto atribūtu.</span><span class="sxs-lookup"><span data-stu-id="cc05a-138">Select **Add** to add the selected attribute to the measure.</span></span>

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Atlasiet atribūtu, ko izmantot aprēķinos.":::

1. <span data-ttu-id="cc05a-140">Lai izveidotu sarežģītākus pasākumus, pasākumu funkcijai var pievienot papildu atribūtus vai lietot matemātikas operatorus.</span><span class="sxs-lookup"><span data-stu-id="cc05a-140">To build more complex measures, you can add more attributes or use math operators on your measure function.</span></span>

   :::image type="content" source="media/measure-math-operators.png" alt-text="Izveidot sarežģītu pasākumu, izmantojot matemātikas operatorus.":::

1. <span data-ttu-id="cc05a-142">Lai pievienotu filtrus, konfigurācijas apgabalā atlasiet **Filtri**.</span><span class="sxs-lookup"><span data-stu-id="cc05a-142">To add filters, select the **Filter** in the configuration area.</span></span> 
  
   1. <span data-ttu-id="cc05a-143">Rūts **Filtri** sadaļā **Pievienot atribūtu** atlasiet atribūtu, ko vēlaties izmantot, lai izveidotu filtrus.</span><span class="sxs-lookup"><span data-stu-id="cc05a-143">In **Add attribute** section of the **Filters** pane, select the attribute you want to use to create filters.</span></span>
   1. <span data-ttu-id="cc05a-144">Iestatiet filtra operatorus, lai definētu filtru katram atlasītajam atribūtam.</span><span class="sxs-lookup"><span data-stu-id="cc05a-144">Set the filter operators to define the filter for every selected attribute.</span></span>
   1. <span data-ttu-id="cc05a-145">Atlasiet vienumu **Lietot**, lai pasākumam pievienotu filtrus.</span><span class="sxs-lookup"><span data-stu-id="cc05a-145">Select **Apply** to add the filters to the measure.</span></span>

1. <span data-ttu-id="cc05a-146">Lai pievienotu dimensijas, konfigurācijas apgabalā atlasiet **Dimensija**.</span><span class="sxs-lookup"><span data-stu-id="cc05a-146">To add dimensions, select **Dimension** in the configuration area.</span></span> <span data-ttu-id="cc05a-147">Dimensijas tiek rādītas kā kolonnas pasākumu izvades entītijā.</span><span class="sxs-lookup"><span data-stu-id="cc05a-147">Dimensions will show as columns in the measure output entity.</span></span>
   1. <span data-ttu-id="cc05a-148">Atlasiet vienumu **Rediģēt dimensijas**, lai pievienotu datu atribūtus, pēc kuriem vēlaties grupēt pasākumus.</span><span class="sxs-lookup"><span data-stu-id="cc05a-148">Select **Edit dimensions** to add data attributes you want to group the measure values by.</span></span> <span data-ttu-id="cc05a-149">Piemēram, pilsēta vai dzimums.</span><span class="sxs-lookup"><span data-stu-id="cc05a-149">For example, city or gender.</span></span> <span data-ttu-id="cc05a-150">Pēc noklusējuma *CustomerID* dimensija tiek atlasīta, lai izveidotu *klienta līmeņa pasākumus*.</span><span class="sxs-lookup"><span data-stu-id="cc05a-150">By default, the *CustomerID* dimension is selected to create *customer-level measures*.</span></span> <span data-ttu-id="cc05a-151">Ja vēlaties izveidot *uzņēmuma līmeņa pasākumus*, varat noņemt noklusējuma dimensiju.</span><span class="sxs-lookup"><span data-stu-id="cc05a-151">You can remove the default dimension if you want to create *business-level measures*.</span></span>
   1. <span data-ttu-id="cc05a-152">Atlasiet vienumu **Pabeigts**, lai pasākumam pievienotu dimensijas.</span><span class="sxs-lookup"><span data-stu-id="cc05a-152">Select **Done** to add the dimensions to the measure.</span></span>

1. <span data-ttu-id="cc05a-153">Ja jūsu datos ir vērtības, kuras ir jāaizstāj ar veselu skaitli, piemēram, aizstājot *nulle* ar *0*, atlasiet **Kārtulas**.</span><span class="sxs-lookup"><span data-stu-id="cc05a-153">If there are values in your data that you need to replace with an integer, for example, replace *null* with *0*, select **Rules**.</span></span> <span data-ttu-id="cc05a-154">Konfigurējiet kārtulu un pārliecinieties, ka kā aizstājējus izvēlējāties tikai veselus skaitļus.</span><span class="sxs-lookup"><span data-stu-id="cc05a-154">Configure the rule and make sure that you choose only whole numbers as replacements.</span></span>

1. <span data-ttu-id="cc05a-155">Ja starp kartēto datu entītiju un *Klienta* entītiju ir vairāki ceļi, ir jāizvēlas viens no identificētajiem [entītiju attiecību ceļiem](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="cc05a-155">If there are multiple paths between the data entity you mapped and the *Customer* entity, you have to choose one of the identified [entity relationship paths](relationships.md).</span></span> <span data-ttu-id="cc05a-156">Pasākumu rezultāti var atšķirties atkarībā no atlasītā ceļa.</span><span class="sxs-lookup"><span data-stu-id="cc05a-156">Measure results can vary depending on the selected path.</span></span> 
   1. <span data-ttu-id="cc05a-157">Atlasiet **Datu preferences** un izvēlieties entītijas ceļu, kas jāizmanto pasākuma identificēšanai.</span><span class="sxs-lookup"><span data-stu-id="cc05a-157">Select **Data preferences** and choose the entity path that should be used to identify your measure.</span></span> <span data-ttu-id="cc05a-158">Ja entītijai *Klients* ir tikai viens ceļš, šī vadīkla netiks rādīta.</span><span class="sxs-lookup"><span data-stu-id="cc05a-158">If there's only a single path to the *Customer* entity, this control won't show.</span></span>
   1. <span data-ttu-id="cc05a-159">Atlasiet **Pabeigts**, lai lietotu jūsu atlasi.</span><span class="sxs-lookup"><span data-stu-id="cc05a-159">Select **Done** to apply your selection.</span></span> 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Atlasiet entītijas ceļu pasākumam.":::

1. <span data-ttu-id="cc05a-161">Lai pasākumam pievienotu papildu aprēķinus, atlasiet **Jauns aprēķins**.</span><span class="sxs-lookup"><span data-stu-id="cc05a-161">To add more calculations for the measure, select **New calculation**.</span></span> <span data-ttu-id="cc05a-162">Entītijas var izmantot tikai tajā pašā entītijas ceļā jauniem aprēķiniem.</span><span class="sxs-lookup"><span data-stu-id="cc05a-162">You can only use entities on the same entity path for new calculations.</span></span> <span data-ttu-id="cc05a-163">Papildu aprēķini tiek rādīti kā jaunas kolonnas pasākumu izvades entītijā.</span><span class="sxs-lookup"><span data-stu-id="cc05a-163">More calculations will show as new columns in the measure output entity.</span></span>

1. <span data-ttu-id="cc05a-164">Aprēķinā atlasiet **...**, lai **Dublētu**, **Pārsauktu** vai **Noņemtu** aprēķinu no pasākuma.</span><span class="sxs-lookup"><span data-stu-id="cc05a-164">Select **...** on the calculation to **Duplicate**, **Rename**, or **Remove** a calculation from a measure.</span></span>

1. <span data-ttu-id="cc05a-165">**Priekšskatījuma** apgabalā redzēsit izvades entītijas pasākumu datu shēmu, tostarp filtrus un dimensijas.</span><span class="sxs-lookup"><span data-stu-id="cc05a-165">In the **Preview** area, you'll see the data schema of the measure output entity, including filters and dimensions.</span></span> <span data-ttu-id="cc05a-166">Priekšskatījums dinamiski reaģē uz konfigurācijas izmaiņām.</span><span class="sxs-lookup"><span data-stu-id="cc05a-166">The preview reacts dynamically to changes in the configuration.</span></span>

1. <span data-ttu-id="cc05a-167">Atlasiet opciju **Izpildīt**, lai aprēķinātu konfigurētā pasākuma rezultātus.</span><span class="sxs-lookup"><span data-stu-id="cc05a-167">Select **Run** to calculate results for the configured measure.</span></span> <span data-ttu-id="cc05a-168">Atlasiet **Saglabāt un aizvērt**, ja vēlaties saglabāt pašreizējo konfigurāciju un izpildīt pasākumu vēlāk.</span><span class="sxs-lookup"><span data-stu-id="cc05a-168">Select **Save and close** if you want to keep the current configuration and run the measure later.</span></span>

1. <span data-ttu-id="cc05a-169">Dodieties uz **Pasākumi**, lai sarakstā redzētu jaunizveidoto pasākumu.</span><span class="sxs-lookup"><span data-stu-id="cc05a-169">Go to **Measures** to see the newly created measure in the list.</span></span>

## <a name="use-a-template-to-build-a-measure"></a><span data-ttu-id="cc05a-170">Veidnes izmantošana mērījuma veidošanā</span><span class="sxs-lookup"><span data-stu-id="cc05a-170">Use a template to build a measure</span></span>

<span data-ttu-id="cc05a-171">Lai izveidotu bieži izmantotus mērījumus, varat lietot to iepriekš definētās veidnes.</span><span class="sxs-lookup"><span data-stu-id="cc05a-171">You can use predefined templates of commonly used measures to create them.</span></span> <span data-ttu-id="cc05a-172">Detalizēti veidņu apraksti un vadība palīdzēs jums sekmīgi izveidot mērījumu.</span><span class="sxs-lookup"><span data-stu-id="cc05a-172">Detailed descriptions of the templates and a guided experience help you with efficient measure creation.</span></span> <span data-ttu-id="cc05a-173">Veidnes tiek veidotas uz kartētajiem datiem no *Vienotās darbības* entitījas.</span><span class="sxs-lookup"><span data-stu-id="cc05a-173">Templates build on mapped data from the *Unified Activity* entity.</span></span> <span data-ttu-id="cc05a-174">Tāpēc, pirms no veidnes izveidojat mērījumu, pārliecinieties, ka esat konfigurējuši [klientu darbības](activities.md).</span><span class="sxs-lookup"><span data-stu-id="cc05a-174">So make sure you have configured [customer activities](activities.md) before you create a measure from a template.</span></span>

<span data-ttu-id="cc05a-175">Pieejamās mērījumu veidnes:</span><span class="sxs-lookup"><span data-stu-id="cc05a-175">Available measure templates:</span></span> 
- <span data-ttu-id="cc05a-176">Vidējā transakcijas vērtība (ATV)</span><span class="sxs-lookup"><span data-stu-id="cc05a-176">Average transaction value (ATV)</span></span>
- <span data-ttu-id="cc05a-177">Kopējā transakciju vērtība</span><span class="sxs-lookup"><span data-stu-id="cc05a-177">Total transaction value</span></span>
- <span data-ttu-id="cc05a-178">Vidējie ieņēmumi dienā</span><span class="sxs-lookup"><span data-stu-id="cc05a-178">Average daily revenue</span></span>
- <span data-ttu-id="cc05a-179">Gada vidējie ieņēmumi</span><span class="sxs-lookup"><span data-stu-id="cc05a-179">Average yearly revenue</span></span>
- <span data-ttu-id="cc05a-180">Transakciju skaits</span><span class="sxs-lookup"><span data-stu-id="cc05a-180">Transaction count</span></span>
- <span data-ttu-id="cc05a-181">Iegūtie lojalitātes punkti</span><span class="sxs-lookup"><span data-stu-id="cc05a-181">Loyalty points earned</span></span>
- <span data-ttu-id="cc05a-182">Izmantotie lojalitātes punkti</span><span class="sxs-lookup"><span data-stu-id="cc05a-182">Loyalty points redeemed</span></span>
- <span data-ttu-id="cc05a-183">Lojalitātes punktu bilance</span><span class="sxs-lookup"><span data-stu-id="cc05a-183">Loyalty points balance</span></span>
- <span data-ttu-id="cc05a-184">Klienta aktivitātes laika periods</span><span class="sxs-lookup"><span data-stu-id="cc05a-184">Active customer lifespan</span></span>
- <span data-ttu-id="cc05a-185">Dalības ilgums lojalitātes programmā</span><span class="sxs-lookup"><span data-stu-id="cc05a-185">Loyalty membership duration</span></span>
- <span data-ttu-id="cc05a-186">Laiks kopš pēdējā pirkuma</span><span class="sxs-lookup"><span data-stu-id="cc05a-186">Time since last purchase</span></span>

<span data-ttu-id="cc05a-187">Šajā procedūrā aprakstītas darbības jauna mērījuma izveidei, izmantojot veidni.</span><span class="sxs-lookup"><span data-stu-id="cc05a-187">The following procedure outlines the steps to build a new measure using a template.</span></span>

1. <span data-ttu-id="cc05a-188">Sadaļā Auditorijas ieskati ejiet uz **Mēri**.</span><span class="sxs-lookup"><span data-stu-id="cc05a-188">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="cc05a-189">Atlasiet **Jauns** un atlasiet **Izvēlieties veidni**.</span><span class="sxs-lookup"><span data-stu-id="cc05a-189">Select **New** and select **Choose a template**.</span></span>

   :::image type="content" source="media/measure-use-template.png" alt-text="Ekrānuzņēmums nolaižamajai izvēlnei laikā, kad tiek izveidots jauns mērījums ar izceltu veidni..":::

1. <span data-ttu-id="cc05a-191">Atrodiet sev atbilstošo veidni un atlasiet **Izvēlēties veidni**.</span><span class="sxs-lookup"><span data-stu-id="cc05a-191">Find the template that fits your need and select **Choose template**.</span></span>

1. <span data-ttu-id="cc05a-192">Pārskatiet prasītos datus un atlasiet **Sākt darbu**, ja visi dati ir pareizi.</span><span class="sxs-lookup"><span data-stu-id="cc05a-192">Review the required data and select **Get started** if you have all the data in place.</span></span>

1. <span data-ttu-id="cc05a-193">Rūtī **Rediģēt nosaukumu** ievadiet sava mērījuma vārdu un izvades entitīju.</span><span class="sxs-lookup"><span data-stu-id="cc05a-193">In the **Edit name** pane, set the name for your measure and the output entity.</span></span> 

1. <span data-ttu-id="cc05a-194">Atlasiet **Gatavs**.</span><span class="sxs-lookup"><span data-stu-id="cc05a-194">Select **Done**.</span></span>

1. <span data-ttu-id="cc05a-195">Sadaļā **Iestatīt laikposmu** definējiet lietojamo datu laika periodu.</span><span class="sxs-lookup"><span data-stu-id="cc05a-195">In the **Set time period** section, define the time frame of the data to use.</span></span> <span data-ttu-id="cc05a-196">Izvēlieties, vai vēlaties, lai jaunais mērījums ietver visu datu kopu, atlasot **Visu laiku**.</span><span class="sxs-lookup"><span data-stu-id="cc05a-196">Choose if you want the new measure to cover the entire data set by selecting **All time**.</span></span> <span data-ttu-id="cc05a-197">Vai, ja vēlaties, lai mērījums koncentrējas uz **Konkrētu laika periodu**.</span><span class="sxs-lookup"><span data-stu-id="cc05a-197">Or if you want the measure to focus on a **Specific time period**.</span></span>

   :::image type="content" source="media/measure-set-time-period.png" alt-text="Ekrānuzņēmums, kurā redzama laika perioda sadaļa, kad mērījumu konfigurē no veidnes.":::

1. <span data-ttu-id="cc05a-199">Nākamajā sadaļā atlasiet **Pievienot datus**, lai izvēlētos darbībs un kartētu atbilstošos datus no savas *Vienotās darbības* entitījas.</span><span class="sxs-lookup"><span data-stu-id="cc05a-199">In the next section, select **Add data** to choose the activities and map the corresponding data from your *Unified Activity* entity.</span></span>

    1. <span data-ttu-id="cc05a-200">1. darbība no 2: Sadaļā **Darbības veids** izvēlieties entitījas veidu, kuru vēlaties lietot.</span><span class="sxs-lookup"><span data-stu-id="cc05a-200">Step 1 of 2: Under **Activity type**, choose the type of the entity you want to use.</span></span> <span data-ttu-id="cc05a-201">**Darbībām** atlasiet entitījas, kuras vēlaties kartēt.</span><span class="sxs-lookup"><span data-stu-id="cc05a-201">For **Activities**, select the entities you want to map.</span></span>
    1. <span data-ttu-id="cc05a-202">2. darbība no 2: Atlasiet atribūtu no *Vienotās darbības* entitījas formulas prasītajam komponentam.</span><span class="sxs-lookup"><span data-stu-id="cc05a-202">Step 2 of 2: Choose the attribute from the *Unified Activity* entity for the component required by the formula.</span></span> <span data-ttu-id="cc05a-203">Piemēram, vidējai transakcijas vērtībai tas ir komponents, kas apzīmē transakcijas vērtību.</span><span class="sxs-lookup"><span data-stu-id="cc05a-203">For example, for Average transaction value, it's the attribute representing the Transaction value.</span></span> <span data-ttu-id="cc05a-204">**Darbības laikspiedolam** atlasiet atribūtu no Vienotās darbības entitījas, kas apzīmē darbības datumu un laiku.</span><span class="sxs-lookup"><span data-stu-id="cc05a-204">For **Activity timestamp**, choose the attribute from the Unified Activity entity that represents the date and time of the activity.</span></span>
   
1. <span data-ttu-id="cc05a-205">Kad datu kartēšana ir izdevusies, varat redzēt statusu kā **Pabeigts** un kartēto darbību un atribūtu nosaukumu.</span><span class="sxs-lookup"><span data-stu-id="cc05a-205">Once the data mapping is successful, you can see the status as **Complete** and the name of the mapped activities and attributes.</span></span>

   :::image type="content" source="media/measure-template-configured.png" alt-text="Ekrānuzņēmums pabeigtai mērījuma veidnes konfigurēšanai.":::

1. <span data-ttu-id="cc05a-207">Tagad varat atlasīt **Palaist**, lai aprēķinātu mērījuma rezultātus.</span><span class="sxs-lookup"><span data-stu-id="cc05a-207">You can now select **Run** to calculate the results of the measure.</span></span> <span data-ttu-id="cc05a-208">Lai to precizētu vēlāk, atlasiet **Saglabāt melnrakstu**.</span><span class="sxs-lookup"><span data-stu-id="cc05a-208">To refine it later, select **Save draft**.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="cc05a-209">Pārvaldiet savus mērus</span><span class="sxs-lookup"><span data-stu-id="cc05a-209">Manage your measures</span></span>

<span data-ttu-id="cc05a-210">Mērījumu saraksts atrodams lapā **Mērījumi**.</span><span class="sxs-lookup"><span data-stu-id="cc05a-210">You can find the list of measures on the **Measures** page.</span></span>

<span data-ttu-id="cc05a-211">Atradīsiet informāciju par pasākuma tipu, izveidotāju, izveides datumu, statusu un stāvokli.</span><span class="sxs-lookup"><span data-stu-id="cc05a-211">You'll find information about the measure type, the creator, creation date, status, and state.</span></span> <span data-ttu-id="cc05a-212">Kad sarakstā atlasāt kādu pasākumu, varat priekšskatīt izvadi un lejupielādēt .CSV failu.</span><span class="sxs-lookup"><span data-stu-id="cc05a-212">When you select a measure from the list, you can preview the output and download a .CSV file.</span></span>

<span data-ttu-id="cc05a-213">Lai vienlaikus atsvaidzinātu visus mērus, atlasiet **Atsvaidzināt visu**, neatlasot noteiktu mēru.</span><span class="sxs-lookup"><span data-stu-id="cc05a-213">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="cc05a-214">![Darbības, lai pārvaldītu atsevišķus mērus](media/measure-actions.png "Darbības, lai pārvaldītu atsevišķus mērus")</span><span class="sxs-lookup"><span data-stu-id="cc05a-214">![Actions to manage single measures](media/measure-actions.png "Actions to manage single measures")</span></span>

<span data-ttu-id="cc05a-215">Sarakstā atlasiet pasākumu, lai izvēlētos kādu no šīm opcijām:</span><span class="sxs-lookup"><span data-stu-id="cc05a-215">Select a measure from the list for the following options:</span></span>

- <span data-ttu-id="cc05a-216">Atlasiet mēra nosaukumu, lai skatītu tā detalizētu informāciju.</span><span class="sxs-lookup"><span data-stu-id="cc05a-216">Select the measure name to see its details.</span></span>
- <span data-ttu-id="cc05a-217">**Rediģējiet** mēra konfigurāciju.</span><span class="sxs-lookup"><span data-stu-id="cc05a-217">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="cc05a-218">**Atsvaidzināt** pasākumu, pamatojoties uz jaunākajiem datiem.</span><span class="sxs-lookup"><span data-stu-id="cc05a-218">**Refresh** the measure based on the latest data.</span></span>
- <span data-ttu-id="cc05a-219">**Pārdēvējiet** mēru. </span><span class="sxs-lookup"><span data-stu-id="cc05a-219">**Rename** the measure.</span></span>
- <span data-ttu-id="cc05a-220">**Dzēsiet** mēru.</span><span class="sxs-lookup"><span data-stu-id="cc05a-220">**Delete** the measure.</span></span>
- <span data-ttu-id="cc05a-221">**Aktivizēt** vai **Deaktivizēt**.</span><span class="sxs-lookup"><span data-stu-id="cc05a-221">**Activate** or **Deactivate**.</span></span> <span data-ttu-id="cc05a-222">neaktīvie pasākumi netiks netiks atsvaidzināti [plānotās atsvaidzināšanas laikā](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="cc05a-222">Inactive measures won't get refreshed during a [scheduled refresh](system.md#schedule-tab).</span></span>

> [!TIP]
> <span data-ttu-id="cc05a-223">Uzdevumiem/procesiem ir [seši statusu tipi](system.md#status-types).</span><span class="sxs-lookup"><span data-stu-id="cc05a-223">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="cc05a-224">Turklāt vairums procesu [ir atkarīgi no citiem pakārtotiem procesiem](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="cc05a-224">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="cc05a-225">Varat atlasīt procesa statusu, lai skatītu detalizētu informāciju par visa uzdevuma norisi.</span><span class="sxs-lookup"><span data-stu-id="cc05a-225">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="cc05a-226">Pēc tam, kad vienam no darba uzdevumiem esat atlasījis **Skatīt detalizētu informāciju**, jūs redzēsit papildinformāciju: apstrādes laiku, pēdējās apstrādes datumu un visas ar uzdevumu saistītas kļūdas un brīdinājumus.</span><span class="sxs-lookup"><span data-stu-id="cc05a-226">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="cc05a-227">Nākamā darbība</span><span class="sxs-lookup"><span data-stu-id="cc05a-227">Next step</span></span>

<span data-ttu-id="cc05a-228">Jūs varat izmantot esošus pasākumus, lai izveidotu [klientu segmentu](segments.md).</span><span class="sxs-lookup"><span data-stu-id="cc05a-228">You cam use existing measures to create [a customer segment](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
