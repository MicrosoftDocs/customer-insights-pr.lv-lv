---
title: Pasākumu izveide un pārvaldība
description: Definējiet pasākumus, lai analizētu un atspoguļotu sava uzņēmuma veiktspēju.
ms.date: 02/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: wameng
manager: shellyha
ms.openlocfilehash: 5bcee3b4c51880740715575b18fd7a4dbf87e6d0
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269937"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="89da6-103">Definējiet un pārvaldiet mērus</span><span class="sxs-lookup"><span data-stu-id="89da6-103">Define and manage measures</span></span>

<span data-ttu-id="89da6-104">Pasākumi palīdz labāk izprast klientu uzvedību un biznesa veiktspēju, izgūstot atbilstošas vērtības no [vienotajiem profiliem](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="89da6-104">Measures help you to better understand customer behaviors and business performance by retrieving relevant values from [unified profiles](data-unification.md).</span></span> <span data-ttu-id="89da6-105">Piemēram, uzņēmumam jāizprot *katra klienta kopējie tēriņi*, lai izprastu atsevišķa klienta pirkumu vēsturi.</span><span class="sxs-lookup"><span data-stu-id="89da6-105">For example, a business wants to see the *total spend per customer* to understand individual customer’s purchase history.</span></span> <span data-ttu-id="89da6-106">Vai izmērīt *uzņēmuma kopējos pārdošanas apjomus*, lai izprastu kopējā līmeņa ieņēmumus visā biznesā.</span><span class="sxs-lookup"><span data-stu-id="89da6-106">Or measure *total sales of the company* to understand the aggregate-level revenue in the whole business.</span></span>  

<span data-ttu-id="89da6-107">Pasākumi tiek izveidoti, izmantojot pasākumu veidotāju, datu vaicājumu platformu ar dažādiem operatoriem un vienkāršām kartēšanas opcijām.</span><span class="sxs-lookup"><span data-stu-id="89da6-107">Measures are created using the measure builder, a data query platform with various operators and simple mapping options.</span></span> <span data-ttu-id="89da6-108">Tas ļauj filtrēt datus, grupēt rezultātus, noteikt [entītiju attiecību ceļus](relationships.md) un priekšskatīt izvadi.</span><span class="sxs-lookup"><span data-stu-id="89da6-108">It lets you filter the data, group results, detect [entity relationship paths](relationships.md), and preview the output.</span></span>

<span data-ttu-id="89da6-109">Izmantojiet pasākumu veidotāju, kas tiek plānots biznesa aktivitātēm, vaicājot klientu datus un izvelkot ieskatus.</span><span class="sxs-lookup"><span data-stu-id="89da6-109">Use the measure builder to plan business activities by querying customer data and extract insights.</span></span> <span data-ttu-id="89da6-110">Piemēram, *katra klienta kopējo tēriņu* un *katra klienta kopējo ienākumu* pasākumu izveide palīdz identificēt klientu grupu, kuriem ir augsti tēriņi, bet augsti ieņēmumi.</span><span class="sxs-lookup"><span data-stu-id="89da6-110">For example, creating a measure of *total spend per customer* and *total return per customer* helps identify a group of customers with high spend yet high return.</span></span> <span data-ttu-id="89da6-111">Varat [izveidot segmentu](segments.md), lai vadītu nākamās, vislabāk piemērotās darbības.</span><span class="sxs-lookup"><span data-stu-id="89da6-111">You can [create a segment](segments.md) to drive next best actions.</span></span> 

## <a name="create-a-measure"></a><span data-ttu-id="89da6-112">Mēra izveide</span><span class="sxs-lookup"><span data-stu-id="89da6-112">Create a measure</span></span>

<span data-ttu-id="89da6-113">Šajā sadaļā ir skatīts, kā izveidot jaunu pasākumu no nulles.</span><span class="sxs-lookup"><span data-stu-id="89da6-113">This section walks you through creating a new measure from scratch.</span></span> <span data-ttu-id="89da6-114">Varat izveidot pasākumu ar datu atribūtiem no datu entītijām, kurām ir iestatītas attiecības, lai izveidotu savienojumu ar Klienta entītiju.</span><span class="sxs-lookup"><span data-stu-id="89da6-114">You can build a measure with data attributes from data entities that have a relationship set up to connect with the Customer entity.</span></span> 

1. <span data-ttu-id="89da6-115">Sadaļā Auditorijas ieskati ejiet uz **Mēri**.</span><span class="sxs-lookup"><span data-stu-id="89da6-115">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="89da6-116">Atlasiet **Jauns**.</span><span class="sxs-lookup"><span data-stu-id="89da6-116">Select **New**.</span></span>

1. <span data-ttu-id="89da6-117">Atlasiet **Rediģēt nosaukumu** un norādiet pasākumam **Nosaukumu**.</span><span class="sxs-lookup"><span data-stu-id="89da6-117">Select **Edit name** and provide a **Name** for the measure.</span></span> 
   > [!NOTE]
   > <span data-ttu-id="89da6-118">Ja jaunajā pasākumu konfigurācijā ir tikai divi lauki, piemēram, paplašināmā lauka CustomerID un viens aprēķins, izvade sistēmas ģenerētajā entītijā tiks pievienota kā jauna kolonna ar nosaukumu Customer_Measure.</span><span class="sxs-lookup"><span data-stu-id="89da6-118">If your new measure configuration has only two fields, for exmample, CustomerID and one calculation, the output will be added as a new column to the system generated entity called Customer_Measure.</span></span> <span data-ttu-id="89da6-119">Un pasākuma vērtību varat redzēt vienotā klienta profilā.</span><span class="sxs-lookup"><span data-stu-id="89da6-119">And you will be able to see the measure’s value in the unified customer profile.</span></span> <span data-ttu-id="89da6-120">Citi pasākumi radīs savas entītijas.</span><span class="sxs-lookup"><span data-stu-id="89da6-120">Other measures will generate their own entities.</span></span>

1. <span data-ttu-id="89da6-121">Konfigurācijas apgabalā izvēlieties apkopošanas funkciju nolaižamajā izvēlnē **Atlasīt funkciju**.</span><span class="sxs-lookup"><span data-stu-id="89da6-121">In the configuration area, choose the aggregation function from the **Select Function** drop-down menu.</span></span> <span data-ttu-id="89da6-122">Apkopošanas funkcijas ir šādas:</span><span class="sxs-lookup"><span data-stu-id="89da6-122">Aggregation functions include:</span></span> 
   - <span data-ttu-id="89da6-123">**Sum**</span><span class="sxs-lookup"><span data-stu-id="89da6-123">**Sum**</span></span>
   - <span data-ttu-id="89da6-124">**Vidējais**</span><span class="sxs-lookup"><span data-stu-id="89da6-124">**Average**</span></span>
   - <span data-ttu-id="89da6-125">**Skaits**</span><span class="sxs-lookup"><span data-stu-id="89da6-125">**Count**</span></span>
   - <span data-ttu-id="89da6-126">**Skaitīt unikālos vienumus**</span><span class="sxs-lookup"><span data-stu-id="89da6-126">**Count Unique**</span></span>
   - <span data-ttu-id="89da6-127">**Maksimums**</span><span class="sxs-lookup"><span data-stu-id="89da6-127">**Max**</span></span>
   - <span data-ttu-id="89da6-128">**Minimums**</span><span class="sxs-lookup"><span data-stu-id="89da6-128">**Min**</span></span>
   - <span data-ttu-id="89da6-129">**Pirmā**: tiek ņemta pirmā datu ieraksta vērtība</span><span class="sxs-lookup"><span data-stu-id="89da6-129">**First**: takes the first value of the data record</span></span>
   - <span data-ttu-id="89da6-130">**Pēdējā**: tiek ņemta pēdējā vērtība, kas tika pievienota datu ierakstam</span><span class="sxs-lookup"><span data-stu-id="89da6-130">**Last**: takes the last value that was added to the data record</span></span>

   :::image type="content" source="media/measure-operators.png" alt-text="Operatorus pasākumu aprēķiniem.":::

1. <span data-ttu-id="89da6-132">Atlasiet vienumu **Pievienot atribūtu**, lai atlasītu datus, kas nepieciešami šī pasākuma izveidei.</span><span class="sxs-lookup"><span data-stu-id="89da6-132">Select **Add attribute** to select the data you need to create this measure.</span></span>
   
   1. <span data-ttu-id="89da6-133">Atlasiet cilni **Atribūti**.</span><span class="sxs-lookup"><span data-stu-id="89da6-133">Select the **Attributes** tab.</span></span> 
   1. <span data-ttu-id="89da6-134">Datu entītija: izvēlieties entītiju, kurā iekļauts mērvienības atribūts, ko vēlaties aprēķināt.</span><span class="sxs-lookup"><span data-stu-id="89da6-134">Data entity: Choose the entity that includes the attribute you want to measure.</span></span> 
   1. <span data-ttu-id="89da6-135">Datu atribūts: izvēlieties atribūtu, ko vēlaties izmantot apkopošanas funkcijai, lai aprēķinātu pasākumu.</span><span class="sxs-lookup"><span data-stu-id="89da6-135">Data attribute: Choose the attribute you want to use in the aggregation function to calculate the measure.</span></span> <span data-ttu-id="89da6-136">Vienlaikus vienā reizē var atlasīt tikai vienu atribūtu.</span><span class="sxs-lookup"><span data-stu-id="89da6-136">You can only select one attribute at a time.</span></span>
   1. <span data-ttu-id="89da6-137">Atlasiet arī esoša pasākuma datu atribūtu, atlasot **Pasākumi** cilni. Varat arī meklēt entītijas vai pasākuma nosaukumu.</span><span class="sxs-lookup"><span data-stu-id="89da6-137">You can also select a data attribute from an existing measure by selecting the **Measures** tab. Or, you can search for an entity or measure name.</span></span> 
   1. <span data-ttu-id="89da6-138">Atlasiet vienumu **Pievienot**, lai pasākumam pievienotu atlasīto atribūtu.</span><span class="sxs-lookup"><span data-stu-id="89da6-138">Select **Add** to add the selected attribute to the measure.</span></span>

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Atlasiet atribūtu, ko izmantot aprēķinos.":::

1. <span data-ttu-id="89da6-140">Lai izveidotu sarežģītākus pasākumus, pasākumu funkcijai var pievienot papildu atribūtus vai lietot matemātikas operatorus.</span><span class="sxs-lookup"><span data-stu-id="89da6-140">To build more complex measures, you can add more attributes or use math operators on your measure function.</span></span>

   :::image type="content" source="media/measure-math-operators.png" alt-text="Izveidot sarežģītu pasākumu, izmantojot matemātikas operatorus.":::

1. <span data-ttu-id="89da6-142">Lai pievienotu filtrus, konfigurācijas apgabalā atlasiet **Filtri**.</span><span class="sxs-lookup"><span data-stu-id="89da6-142">To add filters, select the **Filter** in the configuration area.</span></span> 
  
   1. <span data-ttu-id="89da6-143">Rūts **Filtri** sadaļā **Pievienot atribūtu** atlasiet atribūtu, ko vēlaties izmantot, lai izveidotu filtrus.</span><span class="sxs-lookup"><span data-stu-id="89da6-143">In **Add attribute** section of the **Filters** pane, select the attribute you want to use to create filters.</span></span>
   1. <span data-ttu-id="89da6-144">Iestatiet filtra operatorus, lai definētu filtru katram atlasītajam atribūtam.</span><span class="sxs-lookup"><span data-stu-id="89da6-144">Set the filter operators to define the filter for every selected attribute.</span></span>
   1. <span data-ttu-id="89da6-145">Atlasiet vienumu **Lietot**, lai pasākumam pievienotu filtrus.</span><span class="sxs-lookup"><span data-stu-id="89da6-145">Select **Apply** to add the filters to the measure.</span></span>

1. <span data-ttu-id="89da6-146">Lai pievienotu dimensijas, konfigurācijas apgabalā atlasiet **Dimensija**.</span><span class="sxs-lookup"><span data-stu-id="89da6-146">To add dimensions, select **Dimension** in the configuration area.</span></span> <span data-ttu-id="89da6-147">Dimensijas tiek rādītas kā kolonnas pasākumu izvades entītijā.</span><span class="sxs-lookup"><span data-stu-id="89da6-147">Dimensions will show as columns in the measure output entity.</span></span>
   1. <span data-ttu-id="89da6-148">Atlasiet vienumu **Rediģēt dimensijas**, lai pievienotu datu atribūtus, pēc kuriem vēlaties grupēt pasākumus.</span><span class="sxs-lookup"><span data-stu-id="89da6-148">Select **Edit dimensions** to add data attributes you want to group the measure values by.</span></span> <span data-ttu-id="89da6-149">Piemēram, pilsēta vai dzimums.</span><span class="sxs-lookup"><span data-stu-id="89da6-149">For example, city or gender.</span></span> <span data-ttu-id="89da6-150">Pēc noklusējuma *CustomerID* dimensija tiek atlasīta, lai izveidotu *klienta līmeņa pasākumus*.</span><span class="sxs-lookup"><span data-stu-id="89da6-150">By default, the *CustomerID* dimension is selected to create *customer-level measures*.</span></span> <span data-ttu-id="89da6-151">Ja vēlaties izveidot *uzņēmuma līmeņa pasākumus*, varat noņemt noklusējuma dimensiju.</span><span class="sxs-lookup"><span data-stu-id="89da6-151">You can remove the default dimension if you want to create *business-level measures*.</span></span>
   1. <span data-ttu-id="89da6-152">Atlasiet vienumu **Pabeigts**, lai pasākumam pievienotu dimensijas.</span><span class="sxs-lookup"><span data-stu-id="89da6-152">Select **Done** to add the dimensions to the measure.</span></span>

1. <span data-ttu-id="89da6-153">Ja starp kartēto datu entītiju un Klienta entītiju ir vairāki ceļi, ir jāizvēlas viens no identificētajiem [entītiju attiecību ceļiem](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="89da6-153">If there are multiple paths between the data entity you mapped and the Customer entity, you have to choose one of the identified [entity relationship paths](relationships.md).</span></span> <span data-ttu-id="89da6-154">Pasākumu rezultāti var atšķirties atkarībā no atlasītā ceļa.</span><span class="sxs-lookup"><span data-stu-id="89da6-154">Measure results can vary depending on the selected path.</span></span>
   1. <span data-ttu-id="89da6-155">Atlasiet **Datu preferences** un izvēlieties entītijas ceļu, kas jāizmanto pasākuma identificēšanai.</span><span class="sxs-lookup"><span data-stu-id="89da6-155">Select **Data preferences** and choose the entity path that should be used to identify your measure.</span></span>
   1. <span data-ttu-id="89da6-156">Atlasiet **Pabeigts**, lai lietotu jūsu atlasi.</span><span class="sxs-lookup"><span data-stu-id="89da6-156">Select **Done** to apply your selection.</span></span> 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Atlasiet entītijas ceļu pasākumam.":::

1. <span data-ttu-id="89da6-158">Lai pasākumam pievienotu papildu aprēķinus, atlasiet **Jauns aprēķins**.</span><span class="sxs-lookup"><span data-stu-id="89da6-158">To add more calculations for the measure, select **New calculation**.</span></span> <span data-ttu-id="89da6-159">Entītijas var izmantot tikai tajā pašā entītijas ceļā jauniem aprēķiniem.</span><span class="sxs-lookup"><span data-stu-id="89da6-159">You can only use entities on the same entity path for new calculations.</span></span> <span data-ttu-id="89da6-160">Papildu aprēķini tiek rādīti kā jaunas kolonnas pasākumu izvades entītijā.</span><span class="sxs-lookup"><span data-stu-id="89da6-160">More calculations will show as new columns in the measure output entity.</span></span>

1. <span data-ttu-id="89da6-161">Aprēķinā atlasiet **...**, lai **Dublētu**, **Pārsauktu** vai **Noņemtu** aprēķinu no pasākuma.</span><span class="sxs-lookup"><span data-stu-id="89da6-161">Select **...** on the calculation to **Duplicate**, **Rename**, or **Remove** a calculation from a measure.</span></span>

1. <span data-ttu-id="89da6-162">**Priekšskatījuma** apgabalā redzēsit izvades entītijas pasākumu datu shēmu, tostarp filtrus un dimensijas.</span><span class="sxs-lookup"><span data-stu-id="89da6-162">In the **Preview** area, you'll see the data schema of the measure output entity, including filters and dimensions.</span></span> <span data-ttu-id="89da6-163">Priekšskatījums dinamiski reaģē uz konfigurācijas izmaiņām.</span><span class="sxs-lookup"><span data-stu-id="89da6-163">The preview reacts dynamically to changes in the configuration.</span></span>

1. <span data-ttu-id="89da6-164">Atlasiet opciju **Izpildīt**, lai aprēķinātu konfigurētā pasākuma rezultātus.</span><span class="sxs-lookup"><span data-stu-id="89da6-164">Select **Run** to calculate results for the configured measure.</span></span> <span data-ttu-id="89da6-165">Atlasiet **Saglabāt un aizvērt**, ja vēlaties saglabāt pašreizējo konfigurāciju un izpildīt pasākumu vēlāk.</span><span class="sxs-lookup"><span data-stu-id="89da6-165">Select **Save and close** if you want to keep the current configuration and run the measure later.</span></span>

1. <span data-ttu-id="89da6-166">Dodieties uz **Pasākumi**, lai sarakstā redzētu jaunizveidoto pasākumu.</span><span class="sxs-lookup"><span data-stu-id="89da6-166">Go to **Measures** to see the newly created measure in the list.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="89da6-167">Pārvaldiet savus mērus</span><span class="sxs-lookup"><span data-stu-id="89da6-167">Manage your measures</span></span>

<span data-ttu-id="89da6-168">Kad esat [izveidojis pasākumu](#create-a-measure), lapā **Mēri** tiks atainots pasākumu saraksts.</span><span class="sxs-lookup"><span data-stu-id="89da6-168">After [creating a measure](#create-a-measure), you see a list of measures on the **Measures** page.</span></span>

<span data-ttu-id="89da6-169">Atradīsiet informāciju par pasākuma tipu, izveidotāju, izveides datumu, statusu un stāvokli.</span><span class="sxs-lookup"><span data-stu-id="89da6-169">You'll find information about the measure type, the creator, creation date, status, and state.</span></span> <span data-ttu-id="89da6-170">Kad sarakstā atlasāt kādu pasākumu, varat priekšskatīt izvadi un lejupielādēt .CSV failu.</span><span class="sxs-lookup"><span data-stu-id="89da6-170">When you select a measure from the list, you can preview the output and download a .CSV file.</span></span>

<span data-ttu-id="89da6-171">Lai vienlaikus atsvaidzinātu visus mērus, atlasiet **Atsvaidzināt visu**, neatlasot noteiktu mēru.</span><span class="sxs-lookup"><span data-stu-id="89da6-171">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="89da6-172">![Darbības, lai pārvaldītu atsevišķus mērus](media/measure-actions.png "Darbības, lai pārvaldītu atsevišķus mērus")</span><span class="sxs-lookup"><span data-stu-id="89da6-172">![Actions to manage single measures](media/measure-actions.png "Actions to manage single measures")</span></span>

<span data-ttu-id="89da6-173">Sarakstā atlasiet pasākumu, lai izvēlētos kādu no šīm opcijām:</span><span class="sxs-lookup"><span data-stu-id="89da6-173">Select a measure from the list for the following options:</span></span>

- <span data-ttu-id="89da6-174">Atlasiet mēra nosaukumu, lai skatītu tā detalizētu informāciju.</span><span class="sxs-lookup"><span data-stu-id="89da6-174">Select the measure name to see its details.</span></span>
- <span data-ttu-id="89da6-175">**Rediģējiet** mēra konfigurāciju.</span><span class="sxs-lookup"><span data-stu-id="89da6-175">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="89da6-176">**Atsvaidzināt** pasākumu, pamatojoties uz jaunākajiem datiem.</span><span class="sxs-lookup"><span data-stu-id="89da6-176">**Refresh** the measure based on the latest data.</span></span>
- <span data-ttu-id="89da6-177">**Pārdēvējiet** mēru. </span><span class="sxs-lookup"><span data-stu-id="89da6-177">**Rename** the measure.</span></span>
- <span data-ttu-id="89da6-178">**Dzēsiet** mēru.</span><span class="sxs-lookup"><span data-stu-id="89da6-178">**Delete** the measure.</span></span>
- <span data-ttu-id="89da6-179">**Aktivizēt** vai **Deaktivizēt**.</span><span class="sxs-lookup"><span data-stu-id="89da6-179">**Activate** or **Deactivate**.</span></span> <span data-ttu-id="89da6-180">neaktīvie pasākumi netiks netiks atsvaidzināti [plānotās atsvaidzināšanas laikā](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="89da6-180">Inactive measures won't get refreshed during a [scheduled refresh](system.md#schedule-tab).</span></span>

> [!TIP]
> <span data-ttu-id="89da6-181">Uzdevumiem/procesiem ir [seši statusu tipi](system.md#status-types).</span><span class="sxs-lookup"><span data-stu-id="89da6-181">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="89da6-182">Turklāt vairums procesu [ir atkarīgi no citiem pakārtotiem procesiem](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="89da6-182">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="89da6-183">Varat atlasīt procesa statusu, lai skatītu detalizētu informāciju par visa uzdevuma norisi.</span><span class="sxs-lookup"><span data-stu-id="89da6-183">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="89da6-184">Pēc tam, kad vienam no darba uzdevumiem esat atlasījis **Skatīt detalizētu informāciju**, jūs redzēsit papildinformāciju: apstrādes laiku, pēdējās apstrādes datumu un visas ar uzdevumu saistītas kļūdas un brīdinājumus.</span><span class="sxs-lookup"><span data-stu-id="89da6-184">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="89da6-185">Nākamā darbība</span><span class="sxs-lookup"><span data-stu-id="89da6-185">Next step</span></span>

<span data-ttu-id="89da6-186">Jūs varat izmantot esošus pasākumus, lai izveidotu [klientu segmentu](segments.md).</span><span class="sxs-lookup"><span data-stu-id="89da6-186">You cam use existing measures to create [a customer segment](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]