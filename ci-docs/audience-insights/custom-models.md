---
title: Pielāgoti algoritmiskās mācīšanās modeļi | Microsoft Docs
description: Darbs ar pielāgotiem modeļiem no Azure algoritmiskās mācīšanās pakalpojumā Dynamics 365 Customer Insights.
ms.date: 11/19/2020
ms.reviewer: zacook
ms.service: dynamics-365-ai
ms.topic: article
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ef248086b30b870359970529a7bfb37792be62d5
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668912"
---
# <a name="custom-machine-learning-models"></a><span data-ttu-id="23b14-103">Pielāgoti algoritmiskās mācīšanās modeļi</span><span class="sxs-lookup"><span data-stu-id="23b14-103">Custom machine learning models</span></span>

<span data-ttu-id="23b14-104">**Informācija** > **Pielāgotie modeļi** ļauj pārvaldīt darbplūsmas, pamatojoties uz Azure algoritmiskās mācīšanās modeļiem.</span><span class="sxs-lookup"><span data-stu-id="23b14-104">**Intelligence** > **Custom models** lets you manage workflows based on Azure Machine Learning models.</span></span> <span data-ttu-id="23b14-105">Darbplūsmas palīdz izvēlēties datus, no kuriem vēlaties ģenerēt ieskatus, un kartēt rezultātus vienotajos klientu datos.</span><span class="sxs-lookup"><span data-stu-id="23b14-105">Workflows help you choose the data you want to generate insights from and map the results to your unified customer data.</span></span> <span data-ttu-id="23b14-106">Papildinformāciju par pielāgotu algoritmiskās mācīšanās modeļu būvēšanu skatiet tēmā [Azure algoritmiskās mācīšanās modeļu izmantošana](azure-machine-learning-experiments.md).</span><span class="sxs-lookup"><span data-stu-id="23b14-106">For more information about building custom ML models, see [Use Azure Machine Learning-based models](azure-machine-learning-experiments.md).</span></span>

## <a name="responsible-ai"></a><span data-ttu-id="23b14-107">Atbildīgais AI</span><span class="sxs-lookup"><span data-stu-id="23b14-107">Responsible AI</span></span>

<span data-ttu-id="23b14-108">Prognozes piedāvā iespējas, kas ļauj izveidot labākas iespējas klientiem, uzlabot biznesa iespējas un ieņēmumu plūsmas.</span><span class="sxs-lookup"><span data-stu-id="23b14-108">Predictions offer capabilities to create better customer experiences, improve business capabilities, and revenue streams.</span></span> <span data-ttu-id="23b14-109">Stingri ieteicams sabalansēt prognoze vērtību pret tās ietekmi un aizspriedumiem, ko var ieviest ētiskā veidā.</span><span class="sxs-lookup"><span data-stu-id="23b14-109">We strongly recommend you balance the value of your prediction against the impact it has and biases that may be introduced in an ethical manner.</span></span> <span data-ttu-id="23b14-110">Uzziniet vairāk par to, kā Microsoft [aplūko atbildīgu AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span><span class="sxs-lookup"><span data-stu-id="23b14-110">Learn more about how Microsoft is [addressing Responsible AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span></span> <span data-ttu-id="23b14-111">Jūs varat uzzināt arī par [attiecīgo algoritmiskās mācīšanās tehniku un procesiem](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml), kas ir raksturīgi Azure algoritmiskajai mācīšanās.</span><span class="sxs-lookup"><span data-stu-id="23b14-111">You can also learn about [techniques and processes for responsible machine learning](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml) specific to Azure Machine Learning.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="23b14-112">Priekšnosacījumi</span><span class="sxs-lookup"><span data-stu-id="23b14-112">Prerequisites</span></span>

- <span data-ttu-id="23b14-113">Patlaban šis līdzeklis atbalsta tīmekļa pakalpojumus, kas tiek publicēti [algoritmiskās mācīšanās studijā (klasiskais)](https://studio.azureml.net) un [Azure algoritmiskā mācīšanās paketes konveijerā](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines).</span><span class="sxs-lookup"><span data-stu-id="23b14-113">Currently, this feature supports web services published through [Machine Learning Studio (classic)](https://studio.azureml.net) and [Azure Machine Learning batch pipelines](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines).</span></span>

- <span data-ttu-id="23b14-114">Lai izmantotu šo līdzekli, ir nepieciešams Azure Data Lake Gen2 krātuves konts, kas saistīts ar jūsu Azure Studio instanci.</span><span class="sxs-lookup"><span data-stu-id="23b14-114">You need an Azure Data Lake Gen2 storage account associated with your Azure Studio instance to use this feature.</span></span> <span data-ttu-id="23b14-115">Papildinformāciju skatiet [Azure Data Lake Storage Gen2 krātuves konta izveide](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)</span><span class="sxs-lookup"><span data-stu-id="23b14-115">For more information, see [Create an Azure Data Lake Storage Gen2 storage account](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)</span></span>

## <a name="add-a-new-workflow"></a><span data-ttu-id="23b14-116">Pievienojiet jaunu darbplūsmu</span><span class="sxs-lookup"><span data-stu-id="23b14-116">Add a new workflow</span></span>

1. <span data-ttu-id="23b14-117">Dodieties uz **Informācija** > **Pielāgotie modeļi** un atlasiet **Jauna darbplūsma**.</span><span class="sxs-lookup"><span data-stu-id="23b14-117">Go to **Intelligence** > **Custom models** and select **New workflow**.</span></span>

1. <span data-ttu-id="23b14-118">Piešķiriet jūsu pielāgotajam modelim atpazīstamu nosaukumu laukā **Nosaukums**.</span><span class="sxs-lookup"><span data-stu-id="23b14-118">Give your custom model a recognizable name in the **Name** field.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="23b14-119">![Jaunās darbplūsmas rūts ekrānuzņēmums](media/new-workflowv2.png "Jaunās darbplūsmas rūts ekrānuzņēmums")</span><span class="sxs-lookup"><span data-stu-id="23b14-119">![Screenshot of the New workflow pane](media/new-workflowv2.png "Screenshot of the New workflow pane")</span></span>

1. <span data-ttu-id="23b14-120">Atlasiet organizāciju, kurā ir iekļauts tīmekļa pakalpojums opcijā **Nomnieks, kas ietver jūsu tīmekļa servisu**.</span><span class="sxs-lookup"><span data-stu-id="23b14-120">Select the organization that contains the web service in **Tenant that contains your web service**.</span></span>

1. <span data-ttu-id="23b14-121">Ja jūsu Azure algoritmiskās mācīšanās abonements ir citā nomnieka, nekā Customer Insights, atlasiet **Pieteikties** ar saviem akreditācijas datiem atlasītajai organizācijai.</span><span class="sxs-lookup"><span data-stu-id="23b14-121">If your Azure Machine Learning subscription is in a different tenant than Customer Insights, select **Sign in** with your credentials for the selected organization.</span></span>

1. <span data-ttu-id="23b14-122">Atlasiet **Darbvietas**, kas saistītas ar jūsu tīmekļa pakalpojumu.</span><span class="sxs-lookup"><span data-stu-id="23b14-122">Select the **Workspaces** associated with your web service.</span></span> <span data-ttu-id="23b14-123">Ir uzskaitītas divas sadaļas — viena Azure algoritmiskā mācīšanās v1 (algoritmiskā mācīšanās studija (klasiskais)) un Azure algoritmiskā mācīšanās v2 (Azure algoritmiskā mācīšanās).</span><span class="sxs-lookup"><span data-stu-id="23b14-123">There are two sections listed, one for Azure Machine Learning v1 (Machine Learning Studio (classic)) and Azure Machine Learning v2 (Azure Machine Learning).</span></span> <span data-ttu-id="23b14-124">Ja neesat pārliecināts, kura ir īstā darbvieta jūsu algoritmiskās mācīšanās studijai (klasisks) tīmekļa pakalpojumam, atlasiet **Jebkurš**.</span><span class="sxs-lookup"><span data-stu-id="23b14-124">If you're not sure which workspace is the right one for your Machine Learning Studio (classic) web service, select **Any**.</span></span>

1. <span data-ttu-id="23b14-125">Izvēlieties algoritmiskās mācīšanās studija (klasisks) tīmekļa pakalpojumu vai Azure algoritmiskā mācīšanās konveijeru nolaižamajā sarakstā **Tīmekļa pakalpojums, kurā ir jūsu modelis**.</span><span class="sxs-lookup"><span data-stu-id="23b14-125">Choose the Machine Learning Studio (classic) web service or Azure Machine Learning pipeline in the **Web service that contains your model** dropdown.</span></span> <span data-ttu-id="23b14-126">Pēc tam atlasiet **Tālāk**.</span><span class="sxs-lookup"><span data-stu-id="23b14-126">Then, select **Next**.</span></span>
   - <span data-ttu-id="23b14-127">Papildinformācija par [tīmekļa pakalpojuma publicēšanu algoritmiskā mācīšanās studijā (klasiskais)](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span><span class="sxs-lookup"><span data-stu-id="23b14-127">Learn more about [publishing a web service in Machine Learning Studio (classic)](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span></span>
   - <span data-ttu-id="23b14-128">Informācija, kā [publicēt konveijeru Azure algoritmiskajās mācībās, izmantojot noformētāju](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) vai [SDK](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).</span><span class="sxs-lookup"><span data-stu-id="23b14-128">Learn more about [publishing a pipeline in Azure Machine Learning using the designer](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) or [SDK](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).</span></span> 
     > [!NOTE]
     > <span data-ttu-id="23b14-129">Jūsu konveijers ir jāpublicē zem [konveijera galapunkta](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span><span class="sxs-lookup"><span data-stu-id="23b14-129">Your pipeline must be published under a [pipeline endpoint](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span></span>

1. <span data-ttu-id="23b14-130">Katrai **Tīmekļa pakalpojuma ievadei** atlasiet atbilstošo **Entītiju** no auditorijas ieskatiem un atlasiet **Tālāk**.</span><span class="sxs-lookup"><span data-stu-id="23b14-130">For each **Web service input**, select the matching **Entity** from audience insights and select **Next**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="23b14-131">![Konfigurēt darbplūsmu](media/intelligence-screen2-updated.png "Konfigurēt darbplūsmu")</span><span class="sxs-lookup"><span data-stu-id="23b14-131">![Configure a workflow](media/intelligence-screen2-updated.png "Configure a workflow")</span></span>

1. <span data-ttu-id="23b14-132">Iestatiet tālāk norādītos rekvizītus solī **Modeļa izvades parametri**:</span><span class="sxs-lookup"><span data-stu-id="23b14-132">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="23b14-133">Algoritmiskā mācīšanās studija (klasiskais)</span><span class="sxs-lookup"><span data-stu-id="23b14-133">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="23b14-134">Ievadiet izvades **Entītijas nosaukumu**, kurā jāievieto tīmekļa pakalpojuma izvades rezultāti.</span><span class="sxs-lookup"><span data-stu-id="23b14-134">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="23b14-135">Azure algoritmiskā mācīšanās</span><span class="sxs-lookup"><span data-stu-id="23b14-135">Azure Machine Learning</span></span>
      1. <span data-ttu-id="23b14-136">Ievadiet izvades **Entītijas nosaukumu**, kurā jāievieto konveijera izvades rezultāti.</span><span class="sxs-lookup"><span data-stu-id="23b14-136">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="23b14-137">Atlasiet nolaižamajā sarakstā jūsu paketes konveijera **Izvades datu krātuves parametra nosaukumu**.</span><span class="sxs-lookup"><span data-stu-id="23b14-137">Select the **Output data store parameter name** of your batch pipeline from the dropdown.</span></span>
      1. <span data-ttu-id="23b14-138">Atlasiet nolaižamajā sarakstā jūsu paketes konveijera **Izvades ceļa parametra nosaukumu**.</span><span class="sxs-lookup"><span data-stu-id="23b14-138">Select the **Output Path parameter name** of your batch pipeline from the dropdown.</span></span>
      
      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="23b14-139">![Modeļa izvades parametra rūts](media/intelligence-screen3-outputparameters.png "Modeļa izvades parametrs rūts")</span><span class="sxs-lookup"><span data-stu-id="23b14-139">![Model Output Parameter Pane](media/intelligence-screen3-outputparameters.png "Model Output Parameter Pane")</span></span>

1. <span data-ttu-id="23b14-140">Atlasiet atbilstošo atribūtu nolaižamajā sarakstā **Klienta ID rezultātos**, kas identificē klientus, un atlasiet **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="23b14-140">Select the matching attribute from the **Customer ID in results** drop-down list that identifies customers and select **Save**.</span></span>
   
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="23b14-141">![Rezultātu saistīšana ar rūti Klienta dati](media/intelligence-screen4-relatetocustomer.png "Rezultātu saistīšana ar rūti Klienta dati")</span><span class="sxs-lookup"><span data-stu-id="23b14-141">![Relate results to Customer data pane](media/intelligence-screen4-relatetocustomer.png "Relate results to Customer data pane")</span></span>

1. <span data-ttu-id="23b14-142">Jūs redzēsiet **Darbplūsma saglabāta** ekrānu ar detalizētu informāciju par darbplūsmu.</span><span class="sxs-lookup"><span data-stu-id="23b14-142">You'll see the **Workflow Saved** screen with details about the workflow.</span></span>    
   <span data-ttu-id="23b14-143">Ja konfigurējāt darbplūsmu Azure algoritmiskās mācīšanās konveijeram, auditorijas ieskati tiks pievienoti darbvietai, kurā ir konveijers.</span><span class="sxs-lookup"><span data-stu-id="23b14-143">If you configured a workflow for an Azure Machine Learning pipeline, audience insights will attach to the workspace that contains the pipeline.</span></span> <span data-ttu-id="23b14-144">Auditorijas ieskati iegūs **Līdzstrādnieka** lomu Azure darbvietā.</span><span class="sxs-lookup"><span data-stu-id="23b14-144">Audience insights will get a **Contributor** role on the Azure workspace.</span></span>

1. <span data-ttu-id="23b14-145">Atlasiet **Gatavs**.</span><span class="sxs-lookup"><span data-stu-id="23b14-145">Select **Done**.</span></span>

1. <span data-ttu-id="23b14-146">Tagad darbplūsmu var palaist no lapas **Pielāgotie modeļi**.</span><span class="sxs-lookup"><span data-stu-id="23b14-146">You can now run the workflow from the **Custom Models** page.</span></span>

## <a name="edit-a-workflow"></a><span data-ttu-id="23b14-147">Darbplūsmas rediģēšana</span><span class="sxs-lookup"><span data-stu-id="23b14-147">Edit a workflow</span></span>

1. <span data-ttu-id="23b14-148">Lapā **Pielāgotie modeļi** atlasiet vertikālās daudzpunktes kolonnā **Darbības** blakus iepriekš izveidotajai darbplūsmai un atlasiet vienumu **Rediģēt**.</span><span class="sxs-lookup"><span data-stu-id="23b14-148">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created and select **Edit**.</span></span>

1. <span data-ttu-id="23b14-149">Darbplūsmas atpazīstamo nosaukumu var atjaunināt laukā **Parādāmais nosaukums**, taču konfigurēto tīmekļa pakalpojumu vai konveijeru nevar mainīt.</span><span class="sxs-lookup"><span data-stu-id="23b14-149">You can update your workflow's recognizable name in the **Display name** field, but you can't change the configured web service or pipeline.</span></span> <span data-ttu-id="23b14-150">Atlasiet **Tālāk**.</span><span class="sxs-lookup"><span data-stu-id="23b14-150">Select **Next**.</span></span>

1. <span data-ttu-id="23b14-151">Katrai **Tīmekļa pakalpojuma ievadei** atjauniniet atbilstošo **Entītiju** no auditorijas ieskatiem.</span><span class="sxs-lookup"><span data-stu-id="23b14-151">For each **Web service input**, you can update the matching **Entity** from audience insights.</span></span> <span data-ttu-id="23b14-152">Pēc tam atlasiet **Tālāk**.</span><span class="sxs-lookup"><span data-stu-id="23b14-152">Then, select **Next**.</span></span>

1. <span data-ttu-id="23b14-153">Iestatiet tālāk norādītos rekvizītus solī **Modeļa izvades parametri**:</span><span class="sxs-lookup"><span data-stu-id="23b14-153">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="23b14-154">Algoritmiskā mācīšanās studija (klasiskais)</span><span class="sxs-lookup"><span data-stu-id="23b14-154">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="23b14-155">Ievadiet izvades **Entītijas nosaukumu**, kurā jāievieto tīmekļa pakalpojuma izvades rezultāti.</span><span class="sxs-lookup"><span data-stu-id="23b14-155">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="23b14-156">Azure algoritmiskā mācīšanās</span><span class="sxs-lookup"><span data-stu-id="23b14-156">Azure Machine Learning</span></span>
      1. <span data-ttu-id="23b14-157">Ievadiet izvades **Entītijas nosaukumu**, kurā jāievieto konveijera izvades rezultāti.</span><span class="sxs-lookup"><span data-stu-id="23b14-157">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="23b14-158">Atlasiet **Izvades datu krātuves parametra nosaukumu** savam testa konveijeram.</span><span class="sxs-lookup"><span data-stu-id="23b14-158">Select the **Output data store parameter name** for your test pipeline.</span></span>
      1. <span data-ttu-id="23b14-159">Atlasiet **Izvades ceļa parametra nosaukumu** savam testa konveijeram.</span><span class="sxs-lookup"><span data-stu-id="23b14-159">Select the **Output Path parameter name** for your test pipeline.</span></span>

1. <span data-ttu-id="23b14-160">Atlasiet atbilstošo atribūtu nolaižamajā sarakstā **Klienta ID rezultātos**, kas identificē klientus, un atlasiet **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="23b14-160">Select the matching attribute from the **Customer ID in results** drop-down list that identifies customers and select **Save**.</span></span>
   <span data-ttu-id="23b14-161">Jums ir nepieciešams izvēlēties atribūtu no izvedumapmācību izvades ar vērtībām, kas līdzinās Klienta entītijas kolonnai Klienta ID.</span><span class="sxs-lookup"><span data-stu-id="23b14-161">You need to choose an attribute from the inference output with values similar to the Customer ID column of the Customer entity.</span></span> <span data-ttu-id="23b14-162">Ja datu komplektā nav šādas kolonnas, izvēlieties atribūtu, kas unikāli identificē rindu.</span><span class="sxs-lookup"><span data-stu-id="23b14-162">If don't have such a column in your data set, choose an attribute that uniquely identifies the row.</span></span>

## <a name="run-a-workflow"></a><span data-ttu-id="23b14-163">Darbplūsmas palaišana</span><span class="sxs-lookup"><span data-stu-id="23b14-163">Run a workflow</span></span>

1. <span data-ttu-id="23b14-164">Lapā **Pielāgotie modeļi** atlasiet vertikālās daudzpunktes kolonnā **Darbības** jūsu blakus iepriekš izveidotajai darbplūsmai.</span><span class="sxs-lookup"><span data-stu-id="23b14-164">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="23b14-165">Atlasiet **Izpildīt**.</span><span class="sxs-lookup"><span data-stu-id="23b14-165">Select **Run**.</span></span>

<span data-ttu-id="23b14-166">Jūsu darbplūsma arī tiek palaista automātiski ar katru plānoto atsvaidzināšanu.</span><span class="sxs-lookup"><span data-stu-id="23b14-166">Your workflow also runs automatically with every scheduled refresh.</span></span> <span data-ttu-id="23b14-167">Papildinformācija par [ieplānotas atsvaidzināšanas iestatīšanu](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="23b14-167">Learn more about [setting up scheduled refreshes](system.md#schedule-tab).</span></span>

## <a name="delete-a-workflow"></a><span data-ttu-id="23b14-168">Dzēst darbplūsmu</span><span class="sxs-lookup"><span data-stu-id="23b14-168">Delete a workflow</span></span>

1. <span data-ttu-id="23b14-169">Lapā **Pielāgotie modeļi** atlasiet vertikālās daudzpunktes kolonnā **Darbības** blakus iepriekš jūsu izveidotajai darbplūsmai.</span><span class="sxs-lookup"><span data-stu-id="23b14-169">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="23b14-170">Atlasiet **Dzēst** un apstipriniet dzēšanu.</span><span class="sxs-lookup"><span data-stu-id="23b14-170">Select **Delete** and confirm your deletion.</span></span>

<span data-ttu-id="23b14-171">Jūsu darbplūsma tiks izdzēsta.</span><span class="sxs-lookup"><span data-stu-id="23b14-171">Your workflow will be deleted.</span></span> <span data-ttu-id="23b14-172">[Entītija](entities.md), kas tika izveidota darbplūsmas izveides laikā, joprojām pastāv un to var skatīt lapā **Entītijas**.</span><span class="sxs-lookup"><span data-stu-id="23b14-172">The [entity](entities.md) that was created when you created the workflow persists, and can be viewed from the **Entities** page.</span></span>
