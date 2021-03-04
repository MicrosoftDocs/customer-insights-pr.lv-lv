---
title: Pielāgoti algoritmiskās mācīšanās modeļi | Microsoft Docs
description: Darbs ar pielāgotiem modeļiem no Azure algoritmiskās mācīšanās pakalpojumā Dynamics 365 Customer Insights.
ms.date: 11/19/2020
ms.reviewer: zacook
ms.service: dynamics-365-ai
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 34489faaecc5da1ce3dd68d799b3e0e0d9672ab7
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267243"
---
# <a name="custom-machine-learning-models"></a><span data-ttu-id="a12ab-103">Pielāgoti algoritmiskās mācīšanās modeļi</span><span class="sxs-lookup"><span data-stu-id="a12ab-103">Custom machine learning models</span></span>

<span data-ttu-id="a12ab-104">**Informācija** > **Pielāgotie modeļi** ļauj pārvaldīt darbplūsmas, pamatojoties uz Azure algoritmiskās mācīšanās modeļiem.</span><span class="sxs-lookup"><span data-stu-id="a12ab-104">**Intelligence** > **Custom models** lets you manage workflows based on Azure Machine Learning models.</span></span> <span data-ttu-id="a12ab-105">Darbplūsmas palīdz izvēlēties datus, no kuriem vēlaties ģenerēt ieskatus, un kartēt rezultātus vienotajos klientu datos.</span><span class="sxs-lookup"><span data-stu-id="a12ab-105">Workflows help you choose the data you want to generate insights from and map the results to your unified customer data.</span></span> <span data-ttu-id="a12ab-106">Papildinformāciju par pielāgotu algoritmiskās mācīšanās modeļu būvēšanu skatiet tēmā [Azure algoritmiskās mācīšanās modeļu izmantošana](azure-machine-learning-experiments.md).</span><span class="sxs-lookup"><span data-stu-id="a12ab-106">For more information about building custom ML models, see [Use Azure Machine Learning-based models](azure-machine-learning-experiments.md).</span></span>

## <a name="responsible-ai"></a><span data-ttu-id="a12ab-107">Atbildīgais AI</span><span class="sxs-lookup"><span data-stu-id="a12ab-107">Responsible AI</span></span>

<span data-ttu-id="a12ab-108">Prognozes piedāvā iespējas, kas ļauj izveidot labākas iespējas klientiem, uzlabot biznesa iespējas un ieņēmumu plūsmas.</span><span class="sxs-lookup"><span data-stu-id="a12ab-108">Predictions offer capabilities to create better customer experiences, improve business capabilities, and revenue streams.</span></span> <span data-ttu-id="a12ab-109">Stingri ieteicams sabalansēt prognoze vērtību pret tās ietekmi un aizspriedumiem, ko var ieviest ētiskā veidā.</span><span class="sxs-lookup"><span data-stu-id="a12ab-109">We strongly recommend you balance the value of your prediction against the impact it has and biases that may be introduced in an ethical manner.</span></span> <span data-ttu-id="a12ab-110">Uzziniet vairāk par to, kā Microsoft [aplūko atbildīgu AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span><span class="sxs-lookup"><span data-stu-id="a12ab-110">Learn more about how Microsoft is [addressing Responsible AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span></span> <span data-ttu-id="a12ab-111">Jūs varat uzzināt arī par [attiecīgo algoritmiskās mācīšanās tehniku un procesiem](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml), kas ir raksturīgi Azure algoritmiskajai mācīšanās.</span><span class="sxs-lookup"><span data-stu-id="a12ab-111">You can also learn about [techniques and processes for responsible machine learning](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml) specific to Azure Machine Learning.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a12ab-112">Priekšnosacījumi</span><span class="sxs-lookup"><span data-stu-id="a12ab-112">Prerequisites</span></span>

- <span data-ttu-id="a12ab-113">Patlaban šis līdzeklis atbalsta tīmekļa pakalpojumus, kas tiek publicēti [algoritmiskās mācīšanās studijā (klasiskais)](https://studio.azureml.net) un [Azure algoritmiskā mācīšanās paketes konveijerā](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines).</span><span class="sxs-lookup"><span data-stu-id="a12ab-113">Currently, this feature supports web services published through [Machine Learning Studio (classic)](https://studio.azureml.net) and [Azure Machine Learning batch pipelines](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines).</span></span>

- <span data-ttu-id="a12ab-114">Lai izmantotu šo līdzekli, ir nepieciešams Azure Data Lake Gen2 krātuves konts, kas saistīts ar jūsu Azure Studio instanci.</span><span class="sxs-lookup"><span data-stu-id="a12ab-114">You need an Azure Data Lake Gen2 storage account associated with your Azure Studio instance to use this feature.</span></span> <span data-ttu-id="a12ab-115">Papildinformāciju skatiet [Azure Data Lake Storage Gen2 krātuves konta izveide](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)</span><span class="sxs-lookup"><span data-stu-id="a12ab-115">For more information, see [Create an Azure Data Lake Storage Gen2 storage account](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)</span></span>

## <a name="add-a-new-workflow"></a><span data-ttu-id="a12ab-116">Pievienojiet jaunu darbplūsmu</span><span class="sxs-lookup"><span data-stu-id="a12ab-116">Add a new workflow</span></span>

1. <span data-ttu-id="a12ab-117">Dodieties uz **Informācija** > **Pielāgotie modeļi** un atlasiet **Jauna darbplūsma**.</span><span class="sxs-lookup"><span data-stu-id="a12ab-117">Go to **Intelligence** > **Custom models** and select **New workflow**.</span></span>

1. <span data-ttu-id="a12ab-118">Piešķiriet jūsu pielāgotajam modelim atpazīstamu nosaukumu laukā **Nosaukums**.</span><span class="sxs-lookup"><span data-stu-id="a12ab-118">Give your custom model a recognizable name in the **Name** field.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a12ab-119">![Jaunās darbplūsmas rūts ekrānuzņēmums](media/new-workflowv2.png "Jaunās darbplūsmas rūts ekrānuzņēmums")</span><span class="sxs-lookup"><span data-stu-id="a12ab-119">![Screenshot of the New workflow pane](media/new-workflowv2.png "Screenshot of the New workflow pane")</span></span>

1. <span data-ttu-id="a12ab-120">Atlasiet organizāciju, kurā ir iekļauts tīmekļa pakalpojums opcijā **Nomnieks, kas ietver jūsu tīmekļa servisu**.</span><span class="sxs-lookup"><span data-stu-id="a12ab-120">Select the organization that contains the web service in **Tenant that contains your web service**.</span></span>

1. <span data-ttu-id="a12ab-121">Ja jūsu Azure algoritmiskās mācīšanās abonements ir citā nomnieka, nekā Customer Insights, atlasiet **Pieteikties** ar saviem akreditācijas datiem atlasītajai organizācijai.</span><span class="sxs-lookup"><span data-stu-id="a12ab-121">If your Azure Machine Learning subscription is in a different tenant than Customer Insights, select **Sign in** with your credentials for the selected organization.</span></span>

1. <span data-ttu-id="a12ab-122">Atlasiet **Darbvietas**, kas saistītas ar jūsu tīmekļa pakalpojumu.</span><span class="sxs-lookup"><span data-stu-id="a12ab-122">Select the **Workspaces** associated with your web service.</span></span> <span data-ttu-id="a12ab-123">Ir uzskaitītas divas sadaļas — viena Azure algoritmiskā mācīšanās v1 (algoritmiskā mācīšanās studija (klasiskais)) un Azure algoritmiskā mācīšanās v2 (Azure algoritmiskā mācīšanās).</span><span class="sxs-lookup"><span data-stu-id="a12ab-123">There are two sections listed, one for Azure Machine Learning v1 (Machine Learning Studio (classic)) and Azure Machine Learning v2 (Azure Machine Learning).</span></span> <span data-ttu-id="a12ab-124">Ja neesat pārliecināts, kura ir īstā darbvieta jūsu algoritmiskās mācīšanās studijai (klasisks) tīmekļa pakalpojumam, atlasiet **Jebkurš**.</span><span class="sxs-lookup"><span data-stu-id="a12ab-124">If you're not sure which workspace is the right one for your Machine Learning Studio (classic) web service, select **Any**.</span></span>

1. <span data-ttu-id="a12ab-125">Izvēlieties algoritmiskās mācīšanās studija (klasisks) tīmekļa pakalpojumu vai Azure algoritmiskā mācīšanās konveijeru nolaižamajā sarakstā **Tīmekļa pakalpojums, kurā ir jūsu modelis**.</span><span class="sxs-lookup"><span data-stu-id="a12ab-125">Choose the Machine Learning Studio (classic) web service or Azure Machine Learning pipeline in the **Web service that contains your model** dropdown.</span></span> <span data-ttu-id="a12ab-126">Pēc tam atlasiet **Tālāk**.</span><span class="sxs-lookup"><span data-stu-id="a12ab-126">Then, select **Next**.</span></span>
   - <span data-ttu-id="a12ab-127">Papildinformācija par [tīmekļa pakalpojuma publicēšanu algoritmiskā mācīšanās studijā (klasiskais)](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span><span class="sxs-lookup"><span data-stu-id="a12ab-127">Learn more about [publishing a web service in Machine Learning Studio (classic)](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span></span>
   - <span data-ttu-id="a12ab-128">Informācija, kā [publicēt konveijeru Azure algoritmiskajās mācībās, izmantojot noformētāju](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) vai [SDK](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).</span><span class="sxs-lookup"><span data-stu-id="a12ab-128">Learn more about [publishing a pipeline in Azure Machine Learning using the designer](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) or [SDK](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).</span></span> <span data-ttu-id="a12ab-129">Jūsu konveijers ir jāpublicē zem [konveijera galapunkta](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span><span class="sxs-lookup"><span data-stu-id="a12ab-129">Your pipeline must be published under a [pipeline endpoint](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span></span>

1. <span data-ttu-id="a12ab-130">Katrai **Tīmekļa pakalpojuma ievadei** atlasiet atbilstošo **Entītiju** no auditorijas ieskatiem un atlasiet **Tālāk**.</span><span class="sxs-lookup"><span data-stu-id="a12ab-130">For each **Web service input**, select the matching **Entity** from audience insights and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="a12ab-131">Pielāgotā modeļa darbplūsma lietos heiristiku, lai tīmekļa pakalpojuma ievades laukus kartētu uz entītijas atribūtiem, pamatojoties uz lauka nosaukumu un datu tipu.</span><span class="sxs-lookup"><span data-stu-id="a12ab-131">The custom model workflow will apply heuristics to map the web service input fields to the entity attributes based on the name and data type of the field.</span></span> <span data-ttu-id="a12ab-132">Ja tīmekļa pakalpojuma lauku nevar kartēt ar entītiju, tiks parādīts kļūdas ziņojums.</span><span class="sxs-lookup"><span data-stu-id="a12ab-132">You'll see an error if a web service field can't be mapped to an entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a12ab-133">![Konfigurēt darbplūsmu](media/intelligence-screen2-updated.png "Konfigurēt darbplūsmu")</span><span class="sxs-lookup"><span data-stu-id="a12ab-133">![Configure a workflow](media/intelligence-screen2-updated.png "Configure a workflow")</span></span>
   
1. <span data-ttu-id="a12ab-134">Iestatiet tālāk norādītos rekvizītus solī **Modeļa izvades parametri**:</span><span class="sxs-lookup"><span data-stu-id="a12ab-134">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="a12ab-135">Algoritmiskā mācīšanās studija (klasiskais)</span><span class="sxs-lookup"><span data-stu-id="a12ab-135">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="a12ab-136">Ievadiet izvades **Entītijas nosaukumu**, kurā jāievieto tīmekļa pakalpojuma izvades rezultāti.</span><span class="sxs-lookup"><span data-stu-id="a12ab-136">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="a12ab-137">Azure algoritmiskā mācīšanās</span><span class="sxs-lookup"><span data-stu-id="a12ab-137">Azure Machine Learning</span></span>
      1. <span data-ttu-id="a12ab-138">Ievadiet izvades **Entītijas nosaukumu**, kurā jāievieto konveijera izvades rezultāti.</span><span class="sxs-lookup"><span data-stu-id="a12ab-138">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="a12ab-139">Atlasiet nolaižamajā sarakstā jūsu paketes konveijera **Izvades datu krātuves parametra nosaukumu**.</span><span class="sxs-lookup"><span data-stu-id="a12ab-139">Select the **Output data store parameter name** of your batch pipeline from the dropdown.</span></span>
      1. <span data-ttu-id="a12ab-140">Atlasiet nolaižamajā sarakstā jūsu paketes konveijera **Izvades ceļa parametra nosaukumu**.</span><span class="sxs-lookup"><span data-stu-id="a12ab-140">Select the **Output Path parameter name** of your batch pipeline from the dropdown.</span></span>
      
      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="a12ab-141">![Modeļa izvades parametra rūts](media/intelligence-screen3-outputparameters.png "Modeļa izvades parametrs rūts")</span><span class="sxs-lookup"><span data-stu-id="a12ab-141">![Model Output Parameter Pane](media/intelligence-screen3-outputparameters.png "Model Output Parameter Pane")</span></span>

1. <span data-ttu-id="a12ab-142">Atlasiet atbilstošo atribūtu nolaižamajā sarakstā **Klienta ID rezultātos**, kas identificē klientus, un atlasiet **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="a12ab-142">Select the matching attribute from the **Customer ID in results** drop-down list that identifies customers and select **Save**.</span></span>
   
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a12ab-143">![Rezultātu saistīšana ar rūti Klienta dati](media/intelligence-screen4-relatetocustomer.png "Rezultātu saistīšana ar rūti Klienta dati")</span><span class="sxs-lookup"><span data-stu-id="a12ab-143">![Relate results to Customer data pane](media/intelligence-screen4-relatetocustomer.png "Relate results to Customer data pane")</span></span>

1. <span data-ttu-id="a12ab-144">Jūs redzēsiet **Darbplūsma saglabāta** ekrānu ar detalizētu informāciju par darbplūsmu.</span><span class="sxs-lookup"><span data-stu-id="a12ab-144">You'll see the **Workflow Saved** screen with details about the workflow.</span></span>    
   <span data-ttu-id="a12ab-145">Ja konfigurējāt darbplūsmu Azure algoritmiskās mācīšanās konveijeram, auditorijas ieskati tiks pievienoti darbvietai, kurā ir konveijers.</span><span class="sxs-lookup"><span data-stu-id="a12ab-145">If you configured a workflow for an Azure Machine Learning pipeline, audience insights will attach to the workspace that contains the pipeline.</span></span> <span data-ttu-id="a12ab-146">Auditorijas ieskati iegūs **Līdzstrādnieka** lomu Azure darbvietā.</span><span class="sxs-lookup"><span data-stu-id="a12ab-146">Audience insights will get a **Contributor** role on the Azure workspace.</span></span>

1. <span data-ttu-id="a12ab-147">Atlasiet **Gatavs**.</span><span class="sxs-lookup"><span data-stu-id="a12ab-147">Select **Done**.</span></span>

1. <span data-ttu-id="a12ab-148">Tagad darbplūsmu var palaist no lapas **Pielāgotie modeļi**.</span><span class="sxs-lookup"><span data-stu-id="a12ab-148">You can now run the workflow from the **Custom Models** page.</span></span>

## <a name="edit-a-workflow"></a><span data-ttu-id="a12ab-149">Darbplūsmas rediģēšana</span><span class="sxs-lookup"><span data-stu-id="a12ab-149">Edit a workflow</span></span>

1. <span data-ttu-id="a12ab-150">Lapā **Pielāgotie modeļi** atlasiet vertikālās daudzpunktes kolonnā **Darbības** blakus iepriekš izveidotajai darbplūsmai un atlasiet vienumu **Rediģēt**.</span><span class="sxs-lookup"><span data-stu-id="a12ab-150">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created and select **Edit**.</span></span>

1. <span data-ttu-id="a12ab-151">Darbplūsmas atpazīstamo nosaukumu var atjaunināt laukā **Parādāmais nosaukums**, taču konfigurēto tīmekļa pakalpojumu vai konveijeru nevar mainīt.</span><span class="sxs-lookup"><span data-stu-id="a12ab-151">You can update your workflow's recognizable name in the **Display name** field, but you can't change the configured web service or pipeline.</span></span> <span data-ttu-id="a12ab-152">Atlasiet **Tālāk**.</span><span class="sxs-lookup"><span data-stu-id="a12ab-152">Select **Next**.</span></span>

1. <span data-ttu-id="a12ab-153">Katrai **Tīmekļa pakalpojuma ievadei** atjauniniet atbilstošo **Entītiju** no auditorijas ieskatiem.</span><span class="sxs-lookup"><span data-stu-id="a12ab-153">For each **Web service input**, you can update the matching **Entity** from audience insights.</span></span> <span data-ttu-id="a12ab-154">Pēc tam atlasiet **Tālāk**.</span><span class="sxs-lookup"><span data-stu-id="a12ab-154">Then, select **Next**.</span></span>

1. <span data-ttu-id="a12ab-155">Iestatiet tālāk norādītos rekvizītus solī **Modeļa izvades parametri**:</span><span class="sxs-lookup"><span data-stu-id="a12ab-155">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="a12ab-156">Algoritmiskā mācīšanās studija (klasiskais)</span><span class="sxs-lookup"><span data-stu-id="a12ab-156">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="a12ab-157">Ievadiet izvades **Entītijas nosaukumu**, kurā jāievieto tīmekļa pakalpojuma izvades rezultāti.</span><span class="sxs-lookup"><span data-stu-id="a12ab-157">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="a12ab-158">Azure algoritmiskā mācīšanās</span><span class="sxs-lookup"><span data-stu-id="a12ab-158">Azure Machine Learning</span></span>
      1. <span data-ttu-id="a12ab-159">Ievadiet izvades **Entītijas nosaukumu**, kurā jāievieto konveijera izvades rezultāti.</span><span class="sxs-lookup"><span data-stu-id="a12ab-159">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="a12ab-160">Atlasiet **Izvades datu krātuves parametra nosaukumu** savam testa konveijeram.</span><span class="sxs-lookup"><span data-stu-id="a12ab-160">Select the **Output data store parameter name** for your test pipeline.</span></span>
      1. <span data-ttu-id="a12ab-161">Atlasiet **Izvades ceļa parametra nosaukumu** savam testa konveijeram.</span><span class="sxs-lookup"><span data-stu-id="a12ab-161">Select the **Output Path parameter name** for your test pipeline.</span></span>

1. <span data-ttu-id="a12ab-162">Atlasiet atbilstošo atribūtu nolaižamajā sarakstā **Klienta ID rezultātos**, kas identificē klientus, un atlasiet **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="a12ab-162">Select the matching attribute from the **Customer ID in results** drop-down list that identifies customers and select **Save**.</span></span>
   <span data-ttu-id="a12ab-163">Jums ir nepieciešams izvēlēties atribūtu no izvedumapmācību izvades ar vērtībām, kas līdzinās Klienta entītijas kolonnai Klienta ID.</span><span class="sxs-lookup"><span data-stu-id="a12ab-163">You need to choose an attribute from the inference output with values similar to the Customer ID column of the Customer entity.</span></span> <span data-ttu-id="a12ab-164">Ja datu komplektā nav šādas kolonnas, izvēlieties atribūtu, kas unikāli identificē rindu.</span><span class="sxs-lookup"><span data-stu-id="a12ab-164">If don't have such a column in your data set, choose an attribute that uniquely identifies the row.</span></span>

## <a name="run-a-workflow"></a><span data-ttu-id="a12ab-165">Darbplūsmas palaišana</span><span class="sxs-lookup"><span data-stu-id="a12ab-165">Run a workflow</span></span>

1. <span data-ttu-id="a12ab-166">Lapā **Pielāgotie modeļi** atlasiet vertikālās daudzpunktes kolonnā **Darbības** jūsu blakus iepriekš izveidotajai darbplūsmai.</span><span class="sxs-lookup"><span data-stu-id="a12ab-166">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="a12ab-167">Atlasiet **Izpildīt**.</span><span class="sxs-lookup"><span data-stu-id="a12ab-167">Select **Run**.</span></span>

<span data-ttu-id="a12ab-168">Jūsu darbplūsma arī tiek palaista automātiski ar katru plānoto atsvaidzināšanu.</span><span class="sxs-lookup"><span data-stu-id="a12ab-168">Your workflow also runs automatically with every scheduled refresh.</span></span> <span data-ttu-id="a12ab-169">Papildinformācija par [ieplānotas atsvaidzināšanas iestatīšanu](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="a12ab-169">Learn more about [setting up scheduled refreshes](system.md#schedule-tab).</span></span>

## <a name="delete-a-workflow"></a><span data-ttu-id="a12ab-170">Dzēst darbplūsmu</span><span class="sxs-lookup"><span data-stu-id="a12ab-170">Delete a workflow</span></span>

1. <span data-ttu-id="a12ab-171">Lapā **Pielāgotie modeļi** atlasiet vertikālās daudzpunktes kolonnā **Darbības** blakus iepriekš jūsu izveidotajai darbplūsmai.</span><span class="sxs-lookup"><span data-stu-id="a12ab-171">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="a12ab-172">Atlasiet **Dzēst** un apstipriniet dzēšanu.</span><span class="sxs-lookup"><span data-stu-id="a12ab-172">Select **Delete** and confirm your deletion.</span></span>

<span data-ttu-id="a12ab-173">Jūsu darbplūsma tiks izdzēsta.</span><span class="sxs-lookup"><span data-stu-id="a12ab-173">Your workflow will be deleted.</span></span> <span data-ttu-id="a12ab-174">[Entītija](entities.md), kas tika izveidota darbplūsmas izveides laikā, joprojām pastāv un to var skatīt lapā **Entītijas**.</span><span class="sxs-lookup"><span data-stu-id="a12ab-174">The [entity](entities.md) that was created when you created the workflow persists, and can be viewed from the **Entities** page.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]