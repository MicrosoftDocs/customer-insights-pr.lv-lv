---
title: Pielāgoti algoritmiskās mācīšanās modeļi | Microsoft Docs
description: Darbs ar pielāgotiem modeļiem no Azure algoritmiskās mācīšanās pakalpojumā Dynamics 365 Customer Insights.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 87fb517e9f0b380f9721f77470dceb3bcb7e5616
ms.sourcegitcommit: 55c00ea61c78db7b3b54894c01afb3246dff31c8
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 03/22/2021
ms.locfileid: "5700677"
---
# <a name="custom-machine-learning-models"></a><span data-ttu-id="85edb-103">Pielāgoti algoritmiskās mācīšanās modeļi</span><span class="sxs-lookup"><span data-stu-id="85edb-103">Custom machine learning models</span></span>

<span data-ttu-id="85edb-104">**Informācija** > **Pielāgotie modeļi** ļauj pārvaldīt darbplūsmas, pamatojoties uz Azure algoritmiskās mācīšanās modeļiem.</span><span class="sxs-lookup"><span data-stu-id="85edb-104">**Intelligence** > **Custom models** lets you manage workflows based on Azure Machine Learning models.</span></span> <span data-ttu-id="85edb-105">Darbplūsmas palīdz izvēlēties datus, no kuriem vēlaties ģenerēt ieskatus, un kartēt rezultātus vienotajos klientu datos.</span><span class="sxs-lookup"><span data-stu-id="85edb-105">Workflows help you choose the data you want to generate insights from and map the results to your unified customer data.</span></span> <span data-ttu-id="85edb-106">Papildinformāciju par pielāgotu algoritmiskās mācīšanās modeļu būvēšanu skatiet tēmā [Azure algoritmiskās mācīšanās modeļu izmantošana](azure-machine-learning-experiments.md).</span><span class="sxs-lookup"><span data-stu-id="85edb-106">For more information about building custom ML models, see [Use Azure Machine Learning-based models](azure-machine-learning-experiments.md).</span></span>

## <a name="responsible-ai"></a><span data-ttu-id="85edb-107">Atbildīgais AI</span><span class="sxs-lookup"><span data-stu-id="85edb-107">Responsible AI</span></span>

<span data-ttu-id="85edb-108">Prognozes piedāvā iespējas, kas ļauj izveidot labākas iespējas klientiem, uzlabot biznesa iespējas un ieņēmumu plūsmas.</span><span class="sxs-lookup"><span data-stu-id="85edb-108">Predictions offer capabilities to create better customer experiences, improve business capabilities, and revenue streams.</span></span> <span data-ttu-id="85edb-109">Stingri ieteicams sabalansēt prognoze vērtību pret tās ietekmi un aizspriedumiem, ko var ieviest ētiskā veidā.</span><span class="sxs-lookup"><span data-stu-id="85edb-109">We strongly recommend you balance the value of your prediction against the impact it has and biases that may be introduced in an ethical manner.</span></span> <span data-ttu-id="85edb-110">Uzziniet vairāk par to, kā Microsoft [aplūko atbildīgu AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span><span class="sxs-lookup"><span data-stu-id="85edb-110">Learn more about how Microsoft is [addressing Responsible AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span></span> <span data-ttu-id="85edb-111">Jūs varat uzzināt arī par [attiecīgo algoritmiskās mācīšanās tehniku un procesiem](/azure/machine-learning/concept-responsible-ml), kas ir raksturīgi Azure algoritmiskajai mācīšanās.</span><span class="sxs-lookup"><span data-stu-id="85edb-111">You can also learn about [techniques and processes for responsible machine learning](/azure/machine-learning/concept-responsible-ml) specific to Azure Machine Learning.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="85edb-112">Priekšnosacījumi</span><span class="sxs-lookup"><span data-stu-id="85edb-112">Prerequisites</span></span>

- <span data-ttu-id="85edb-113">Patlaban šis līdzeklis atbalsta tīmekļa pakalpojumus, kas tiek publicēti [algoritmiskās mācīšanās studijā (klasiskais)](https://studio.azureml.net) un [Azure algoritmiskā mācīšanās paketes konveijerā](/azure/machine-learning/concept-ml-pipelines).</span><span class="sxs-lookup"><span data-stu-id="85edb-113">Currently, this feature supports web services published through [Machine Learning Studio (classic)](https://studio.azureml.net) and [Azure Machine Learning batch pipelines](/azure/machine-learning/concept-ml-pipelines).</span></span>

- <span data-ttu-id="85edb-114">Lai izmantotu šo līdzekli, ir nepieciešams Azure Data Lake Gen2 krātuves konts, kas saistīts ar jūsu Azure Studio instanci.</span><span class="sxs-lookup"><span data-stu-id="85edb-114">You need an Azure Data Lake Gen2 storage account associated with your Azure Studio instance to use this feature.</span></span> <span data-ttu-id="85edb-115">Papildinformāciju skatiet [Azure Data Lake Storage 2. paaudzes krātuves konta izveide](/azure/storage/blobs/data-lake-storage-quickstart-create-account).</span><span class="sxs-lookup"><span data-stu-id="85edb-115">For more information, see [Create an Azure Data Lake Storage Gen2 storage account](/azure/storage/blobs/data-lake-storage-quickstart-create-account).</span></span>

- <span data-ttu-id="85edb-116">Lai nodrošinātu algoritmisko mācīšanos darbvietām ar konveijeriem, ir nepieciešamas īpašnieka vai lietotāja piekļuves administratora atļaujas Azure algoritmiskās mācīšanās darbvietai.</span><span class="sxs-lookup"><span data-stu-id="85edb-116">For Azure Machine Learning workspaces with pipelines, you need Owner or User Access Administrator permissions to the Azure Machine Learning Workspace.</span></span>

   > [!NOTE]
   > <span data-ttu-id="85edb-117">Dati tiek pārsūtīti starp Customer Insights instancēm un darbplūsmā atlasītajiem Azure tīmekļa pakalpojumiem vai konveijeriem.</span><span class="sxs-lookup"><span data-stu-id="85edb-117">Data is transferred between your Customer Insights instances and the selected Azure web services or pipelines in the workflow.</span></span> <span data-ttu-id="85edb-118">Kad pārsūtāt datus uz pakalpojumu Azure, gādājiet, lai pakalpojums ir konfigurēts tā, ka dati tiek apstrādāti tādā veidā un vietā, kas atbilst jūsu organizācijai noteiktajām juridiskajām vai regulatīvajām prasībām attiecībā uz šiem datiem.</span><span class="sxs-lookup"><span data-stu-id="85edb-118">When you transfer data to an Azure service, please ensure that service is configured to process data in the manner and location necessary to comply with any legal or regulatory requirements for that data for your organization.</span></span>

## <a name="add-a-new-workflow"></a><span data-ttu-id="85edb-119">Pievienojiet jaunu darbplūsmu</span><span class="sxs-lookup"><span data-stu-id="85edb-119">Add a new workflow</span></span>

1. <span data-ttu-id="85edb-120">Dodieties uz **Informācija** > **Pielāgotie modeļi** un atlasiet **Jauna darbplūsma**.</span><span class="sxs-lookup"><span data-stu-id="85edb-120">Go to **Intelligence** > **Custom models** and select **New workflow**.</span></span>

1. <span data-ttu-id="85edb-121">Piešķiriet jūsu pielāgotajam modelim atpazīstamu nosaukumu laukā **Nosaukums**.</span><span class="sxs-lookup"><span data-stu-id="85edb-121">Give your custom model a recognizable name in the **Name** field.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="85edb-122">![Jaunās darbplūsmas rūts ekrānuzņēmums](media/new-workflowv2.png "Jaunās darbplūsmas rūts ekrānuzņēmums")</span><span class="sxs-lookup"><span data-stu-id="85edb-122">![Screenshot of the New workflow pane](media/new-workflowv2.png "Screenshot of the New workflow pane")</span></span>

1. <span data-ttu-id="85edb-123">Atlasiet organizāciju, kurā ir iekļauts tīmekļa pakalpojums opcijā **Nomnieks, kas ietver jūsu tīmekļa servisu**.</span><span class="sxs-lookup"><span data-stu-id="85edb-123">Select the organization that contains the web service in **Tenant that contains your web service**.</span></span>

1. <span data-ttu-id="85edb-124">Ja jūsu Azure algoritmiskās mācīšanās abonements ir citā nomnieka, nekā Customer Insights, atlasiet **Pieteikties** ar saviem akreditācijas datiem atlasītajai organizācijai.</span><span class="sxs-lookup"><span data-stu-id="85edb-124">If your Azure Machine Learning subscription is in a different tenant than Customer Insights, select **Sign in** with your credentials for the selected organization.</span></span>

1. <span data-ttu-id="85edb-125">Atlasiet **Darbvietas**, kas saistītas ar jūsu tīmekļa pakalpojumu.</span><span class="sxs-lookup"><span data-stu-id="85edb-125">Select the **Workspaces** associated with your web service.</span></span> <span data-ttu-id="85edb-126">Ir uzskaitītas divas sadaļas — viena Azure algoritmiskā mācīšanās v1 (algoritmiskā mācīšanās studija (klasiskais)) un Azure algoritmiskā mācīšanās v2 (Azure algoritmiskā mācīšanās).</span><span class="sxs-lookup"><span data-stu-id="85edb-126">There are two sections listed, one for Azure Machine Learning v1 (Machine Learning Studio (classic)) and Azure Machine Learning v2 (Azure Machine Learning).</span></span> <span data-ttu-id="85edb-127">Ja neesat pārliecināts, kura ir īstā darbvieta jūsu algoritmiskās mācīšanās studijai (klasisks) tīmekļa pakalpojumam, atlasiet **Jebkurš**.</span><span class="sxs-lookup"><span data-stu-id="85edb-127">If you're not sure which workspace is the right one for your Machine Learning Studio (classic) web service, select **Any**.</span></span>

1. <span data-ttu-id="85edb-128">Izvēlieties algoritmiskās mācīšanās studija (klasisks) tīmekļa pakalpojumu vai Azure algoritmiskā mācīšanās konveijeru nolaižamajā sarakstā **Tīmekļa pakalpojums, kurā ir jūsu modelis**.</span><span class="sxs-lookup"><span data-stu-id="85edb-128">Choose the Machine Learning Studio (classic) web service or Azure Machine Learning pipeline in the **Web service that contains your model** dropdown.</span></span> <span data-ttu-id="85edb-129">Pēc tam atlasiet **Tālāk**.</span><span class="sxs-lookup"><span data-stu-id="85edb-129">Then, select **Next**.</span></span>
   - <span data-ttu-id="85edb-130">Papildinformācija par [tīmekļa pakalpojuma publicēšanu algoritmiskā mācīšanās studijā (klasiskais)](/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span><span class="sxs-lookup"><span data-stu-id="85edb-130">Learn more about [publishing a web service in Machine Learning Studio (classic)](/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span></span>
   - <span data-ttu-id="85edb-131">Informācija, kā [publicēt konveijeru Azure algoritmiskajās mācībās, izmantojot noformētāju](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) vai [SDK](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).</span><span class="sxs-lookup"><span data-stu-id="85edb-131">Learn more about [publishing a pipeline in Azure Machine Learning using the designer](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) or [SDK](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).</span></span> <span data-ttu-id="85edb-132">Jūsu konveijers ir jāpublicē zem [konveijera galapunkta](/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span><span class="sxs-lookup"><span data-stu-id="85edb-132">Your pipeline must be published under a [pipeline endpoint](/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span></span>

1. <span data-ttu-id="85edb-133">Katrai **Tīmekļa pakalpojuma ievadei** atlasiet atbilstošo **Entītiju** no auditorijas ieskatiem un atlasiet **Tālāk**.</span><span class="sxs-lookup"><span data-stu-id="85edb-133">For each **Web service input**, select the matching **Entity** from audience insights and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="85edb-134">Pielāgotā modeļa darbplūsma lietos heiristiku, lai tīmekļa pakalpojuma ievades laukus kartētu uz entītijas atribūtiem, pamatojoties uz lauka nosaukumu un datu tipu.</span><span class="sxs-lookup"><span data-stu-id="85edb-134">The custom model workflow will apply heuristics to map the web service input fields to the entity attributes based on the name and data type of the field.</span></span> <span data-ttu-id="85edb-135">Ja tīmekļa pakalpojuma lauku nevar kartēt ar entītiju, tiks parādīts kļūdas ziņojums.</span><span class="sxs-lookup"><span data-stu-id="85edb-135">You'll see an error if a web service field can't be mapped to an entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="85edb-136">![Konfigurēt darbplūsmu](media/intelligence-screen2-updated.png "Konfigurēt darbplūsmu")</span><span class="sxs-lookup"><span data-stu-id="85edb-136">![Configure a workflow](media/intelligence-screen2-updated.png "Configure a workflow")</span></span>

1. <span data-ttu-id="85edb-137">Iestatiet tālāk norādītos rekvizītus solī **Modeļa izvades parametri**:</span><span class="sxs-lookup"><span data-stu-id="85edb-137">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="85edb-138">Algoritmiskā mācīšanās studija (klasiskais)</span><span class="sxs-lookup"><span data-stu-id="85edb-138">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="85edb-139">Ievadiet izvades **Entītijas nosaukumu**, kurā jāievieto tīmekļa pakalpojuma izvades rezultāti.</span><span class="sxs-lookup"><span data-stu-id="85edb-139">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="85edb-140">Azure algoritmiskā mācīšanās</span><span class="sxs-lookup"><span data-stu-id="85edb-140">Azure Machine Learning</span></span>
      1. <span data-ttu-id="85edb-141">Ievadiet izvades **Entītijas nosaukumu**, kurā jāievieto konveijera izvades rezultāti.</span><span class="sxs-lookup"><span data-stu-id="85edb-141">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="85edb-142">Atlasiet nolaižamajā sarakstā jūsu paketes konveijera **Izvades datu krātuves parametra nosaukumu**.</span><span class="sxs-lookup"><span data-stu-id="85edb-142">Select the **Output data store parameter name** of your batch pipeline from the dropdown.</span></span>
      1. <span data-ttu-id="85edb-143">Atlasiet nolaižamajā sarakstā jūsu paketes konveijera **Izvades ceļa parametra nosaukumu**.</span><span class="sxs-lookup"><span data-stu-id="85edb-143">Select the **Output Path parameter name** of your batch pipeline from the dropdown.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="85edb-144">![Modeļa izvades parametra rūts](media/intelligence-screen3-outputparameters.png "Modeļa izvades parametrs rūts")</span><span class="sxs-lookup"><span data-stu-id="85edb-144">![Model Output Parameter Pane](media/intelligence-screen3-outputparameters.png "Model Output Parameter Pane")</span></span>

1. <span data-ttu-id="85edb-145">Atlasiet atbilstošo atribūtu nolaižamajā sarakstā **Klienta ID rezultātos**, kas identificē klientus, un atlasiet **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="85edb-145">Select the matching attribute from the **Customer ID in results** drop-down list that identifies customers and select **Save**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="85edb-146">![Rezultātu saistīšana ar rūti Klienta dati](media/intelligence-screen4-relatetocustomer.png "Rezultātu saistīšana ar rūti Klienta dati")</span><span class="sxs-lookup"><span data-stu-id="85edb-146">![Relate results to Customer data pane](media/intelligence-screen4-relatetocustomer.png "Relate results to Customer data pane")</span></span>

1. <span data-ttu-id="85edb-147">Jūs redzēsiet **Darbplūsma saglabāta** ekrānu ar detalizētu informāciju par darbplūsmu.</span><span class="sxs-lookup"><span data-stu-id="85edb-147">You'll see the **Workflow Saved** screen with details about the workflow.</span></span>    
   <span data-ttu-id="85edb-148">Ja konfigurējāt darbplūsmu Azure algoritmiskās mācīšanās konveijeram, auditorijas ieskati tiks pievienoti darbvietai, kurā ir konveijers.</span><span class="sxs-lookup"><span data-stu-id="85edb-148">If you configured a workflow for an Azure Machine Learning pipeline, audience insights will attach to the workspace that contains the pipeline.</span></span> <span data-ttu-id="85edb-149">Auditorijas ieskati iegūs **Līdzstrādnieka** lomu Azure darbvietā.</span><span class="sxs-lookup"><span data-stu-id="85edb-149">Audience insights will get a **Contributor** role on the Azure workspace.</span></span>

1. <span data-ttu-id="85edb-150">Atlasiet **Gatavs**.</span><span class="sxs-lookup"><span data-stu-id="85edb-150">Select **Done**.</span></span>

1. <span data-ttu-id="85edb-151">Tagad darbplūsmu var palaist no lapas **Pielāgotie modeļi**.</span><span class="sxs-lookup"><span data-stu-id="85edb-151">You can now run the workflow from the **Custom Models** page.</span></span>

## <a name="edit-a-workflow"></a><span data-ttu-id="85edb-152">Darbplūsmas rediģēšana</span><span class="sxs-lookup"><span data-stu-id="85edb-152">Edit a workflow</span></span>

1. <span data-ttu-id="85edb-153">Lapā **Pielāgotie modeļi** atlasiet vertikālās daudzpunktes kolonnā **Darbības** blakus iepriekš izveidotajai darbplūsmai un atlasiet vienumu **Rediģēt**.</span><span class="sxs-lookup"><span data-stu-id="85edb-153">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created and select **Edit**.</span></span>

1. <span data-ttu-id="85edb-154">Darbplūsmas atpazīstamo nosaukumu var atjaunināt laukā **Parādāmais nosaukums**, taču konfigurēto tīmekļa pakalpojumu vai konveijeru nevar mainīt.</span><span class="sxs-lookup"><span data-stu-id="85edb-154">You can update your workflow's recognizable name in the **Display name** field, but you can't change the configured web service or pipeline.</span></span> <span data-ttu-id="85edb-155">Atlasiet **Tālāk**.</span><span class="sxs-lookup"><span data-stu-id="85edb-155">Select **Next**.</span></span>

1. <span data-ttu-id="85edb-156">Katrai **Tīmekļa pakalpojuma ievadei** atjauniniet atbilstošo **Entītiju** no auditorijas ieskatiem.</span><span class="sxs-lookup"><span data-stu-id="85edb-156">For each **Web service input**, you can update the matching **Entity** from audience insights.</span></span> <span data-ttu-id="85edb-157">Pēc tam atlasiet **Tālāk**.</span><span class="sxs-lookup"><span data-stu-id="85edb-157">Then, select **Next**.</span></span>

1. <span data-ttu-id="85edb-158">Iestatiet tālāk norādītos rekvizītus solī **Modeļa izvades parametri**:</span><span class="sxs-lookup"><span data-stu-id="85edb-158">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="85edb-159">Algoritmiskā mācīšanās studija (klasiskais)</span><span class="sxs-lookup"><span data-stu-id="85edb-159">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="85edb-160">Ievadiet izvades **Entītijas nosaukumu**, kurā jāievieto tīmekļa pakalpojuma izvades rezultāti.</span><span class="sxs-lookup"><span data-stu-id="85edb-160">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="85edb-161">Azure algoritmiskā mācīšanās</span><span class="sxs-lookup"><span data-stu-id="85edb-161">Azure Machine Learning</span></span>
      1. <span data-ttu-id="85edb-162">Ievadiet izvades **Entītijas nosaukumu**, kurā jāievieto konveijera izvades rezultāti.</span><span class="sxs-lookup"><span data-stu-id="85edb-162">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="85edb-163">Atlasiet **Izvades datu krātuves parametra nosaukumu** savam testa konveijeram.</span><span class="sxs-lookup"><span data-stu-id="85edb-163">Select the **Output data store parameter name** for your test pipeline.</span></span>
      1. <span data-ttu-id="85edb-164">Atlasiet **Izvades ceļa parametra nosaukumu** savam testa konveijeram.</span><span class="sxs-lookup"><span data-stu-id="85edb-164">Select the **Output Path parameter name** for your test pipeline.</span></span>

1. <span data-ttu-id="85edb-165">Atlasiet atbilstošo atribūtu nolaižamajā sarakstā **Klienta ID rezultātos**, kas identificē klientus, un atlasiet **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="85edb-165">Select the matching attribute from the **Customer ID in results** drop-down list that identifies customers and select **Save**.</span></span>
   <span data-ttu-id="85edb-166">Izvēlieties atribūtu no izvedumapmācību izvades ar vērtībām, kas līdzinās Klienta entītijas kolonnai Klienta ID.</span><span class="sxs-lookup"><span data-stu-id="85edb-166">Choose an attribute from the inference output with values similar to the Customer ID column of the Customer entity.</span></span> <span data-ttu-id="85edb-167">Ja datu komplektā nav šādas kolonnas, izvēlieties atribūtu, kas unikāli identificē rindu.</span><span class="sxs-lookup"><span data-stu-id="85edb-167">If don't have such a column in your data set, choose an attribute that uniquely identifies the row.</span></span>

## <a name="run-a-workflow"></a><span data-ttu-id="85edb-168">Darbplūsmas palaišana</span><span class="sxs-lookup"><span data-stu-id="85edb-168">Run a workflow</span></span>

1. <span data-ttu-id="85edb-169">Lapā **Pielāgotie modeļi** atlasiet vertikālās daudzpunktes kolonnā **Darbības** jūsu blakus iepriekš izveidotajai darbplūsmai.</span><span class="sxs-lookup"><span data-stu-id="85edb-169">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="85edb-170">Atlasiet **Izpildīt**.</span><span class="sxs-lookup"><span data-stu-id="85edb-170">Select **Run**.</span></span>

<span data-ttu-id="85edb-171">Jūsu darbplūsma arī tiek palaista automātiski ar katru plānoto atsvaidzināšanu.</span><span class="sxs-lookup"><span data-stu-id="85edb-171">Your workflow also runs automatically with every scheduled refresh.</span></span> <span data-ttu-id="85edb-172">Papildinformācija par [ieplānotas atsvaidzināšanas iestatīšanu](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="85edb-172">Learn more about [setting up scheduled refreshes](system.md#schedule-tab).</span></span>

## <a name="delete-a-workflow"></a><span data-ttu-id="85edb-173">Dzēst darbplūsmu</span><span class="sxs-lookup"><span data-stu-id="85edb-173">Delete a workflow</span></span>

1. <span data-ttu-id="85edb-174">Lapā **Pielāgotie modeļi** atlasiet vertikālās daudzpunktes kolonnā **Darbības** blakus iepriekš jūsu izveidotajai darbplūsmai.</span><span class="sxs-lookup"><span data-stu-id="85edb-174">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="85edb-175">Atlasiet **Dzēst** un apstipriniet dzēšanu.</span><span class="sxs-lookup"><span data-stu-id="85edb-175">Select **Delete** and confirm your deletion.</span></span>

<span data-ttu-id="85edb-176">Jūsu darbplūsma tiks izdzēsta.</span><span class="sxs-lookup"><span data-stu-id="85edb-176">Your workflow will be deleted.</span></span> <span data-ttu-id="85edb-177">[Entītija](entities.md), kas tika izveidota darbplūsmas izveides laikā, joprojām pastāv un to var skatīt lapā **Entītijas**.</span><span class="sxs-lookup"><span data-stu-id="85edb-177">The [entity](entities.md) that was created when you created the workflow persists, and can be viewed from the **Entities** page.</span></span>

## <a name="results"></a><span data-ttu-id="85edb-178">Rezultāti</span><span class="sxs-lookup"><span data-stu-id="85edb-178">Results</span></span>

<span data-ttu-id="85edb-179">Darbplūsmas rezultāti tiek glabāti entītijā, kas ir konfigurēta modeļa izvades parametra posmā.</span><span class="sxs-lookup"><span data-stu-id="85edb-179">Results from a workflow are stored in the entity configured during the Model Output Parameter phase.</span></span> <span data-ttu-id="85edb-180">Varat piekļūt šiem datiem no [entītiju lapas](entities.md) vai ar [API piekļuvi](apis.md).</span><span class="sxs-lookup"><span data-stu-id="85edb-180">You can access this data from the [entities page](entities.md) or with [API access](apis.md).</span></span>

### <a name="api-access"></a><span data-ttu-id="85edb-181">AP piekļuve</span><span class="sxs-lookup"><span data-stu-id="85edb-181">API Access</span></span>

<span data-ttu-id="85edb-182">Lai iegūtu datus no pielāgotas modeļa entītijas, noteiktam OData vaicājumam izmantojiet tālāk norādīto formātu.</span><span class="sxs-lookup"><span data-stu-id="85edb-182">For the specific OData query to get data from a custom model entity, use the following format:</span></span>

`https://api.ci.ai.dynamics.com/v1/instances/<your instance id>/data/<custom model output entity name>%3Ffilter%3DCustomerId%20eq%20'<guid value>'`

1. <span data-ttu-id="85edb-183">Aizstājiet `<your instance id>` ar savas Customer Insights vides ID, kas ir atrodams pārlūkprogrammas adreses joslā, piekļūstot Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="85edb-183">Replace `<your instance id>` with the ID of your Customer Insights environment, which you find in the in the address bar of your browser when accessing Customer Insights.</span></span>

1. <span data-ttu-id="85edb-184">Aizstājiet `<custom model output entity>` ar entītijas nosaukumu, ko nodrošinājāt pielāgotā modeļa konfigurācijas modeļa izvades parametru darbībā.</span><span class="sxs-lookup"><span data-stu-id="85edb-184">Replace `<custom model output entity>` with the entity name you provided during the Model Output Parameters step of the custom model configuration.</span></span>

1. <span data-ttu-id="85edb-185">Aizstājiet `<guid value>` ar tā klienta ID, kura ierakstam vēlaties piekļūt.</span><span class="sxs-lookup"><span data-stu-id="85edb-185">Replace `<guid value>` with the Customer ID of the customer you'd like to access the record for.</span></span> <span data-ttu-id="85edb-186">Šo ID parasti var atrast [klientu profilu lapas](customer-profiles.md) laukā CustomerID .</span><span class="sxs-lookup"><span data-stu-id="85edb-186">You can usually find this ID on the [customer profiles page](customer-profiles.md) in the CustomerID field.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="85edb-187">Bieži uzdotie jautājumi</span><span class="sxs-lookup"><span data-stu-id="85edb-187">Frequently Asked Questions</span></span>

- <span data-ttu-id="85edb-188">Kāpēc, iestatot pielāgotu modeļa darbplūsmu, es neredzu savu konveijeru?</span><span class="sxs-lookup"><span data-stu-id="85edb-188">Why can't I see my pipeline when setting up a custom model workflow?</span></span>    
  <span data-ttu-id="85edb-189">Šo problēmu bieži izraisa konveijera konfigurācijas problēma.</span><span class="sxs-lookup"><span data-stu-id="85edb-189">This issue is frequently caused by a configuration issue in the pipeline.</span></span> <span data-ttu-id="85edb-190">Nodrošiniet, ka [ievades parametrs ir konfigurēts](azure-machine-learning-experiments.md#dataset-configuration) un tiek konfigurēti arī [izvades datu krātuves un ceļa parametri](azure-machine-learning-experiments.md#import-pipeline-data-into-customer-insights).</span><span class="sxs-lookup"><span data-stu-id="85edb-190">Ensure the [input parameter is configured](azure-machine-learning-experiments.md#dataset-configuration), and the [output datastore and path parameters](azure-machine-learning-experiments.md#import-pipeline-data-into-customer-insights) are also configured.</span></span>

- <span data-ttu-id="85edb-191">Ko nozīmē kļūda "Nevarēja saglabāt informācijas darbplūsmu"?</span><span class="sxs-lookup"><span data-stu-id="85edb-191">What does the error "Couldn't save intelligence workflow" mean?</span></span>    
  <span data-ttu-id="85edb-192">Lietotāji parasti redz šo kļūdas ziņojumu, ja viņiem darbvietā nav īpašnieka vai lietotāja piekļuves administratora atļauju.</span><span class="sxs-lookup"><span data-stu-id="85edb-192">Users usually see this error message if they don't have Owner or User Access Administrator privileges on the workspace.</span></span> <span data-ttu-id="85edb-193">Lai Customer Insights darbplūsmu apstrādātu kā servisu, lietotājam ir nepieciešams augstāks atļauju līmenis, nevis lietotāja akreditācijas datu izmantošana turpmākajām darbplūsmas izpildēm.</span><span class="sxs-lookup"><span data-stu-id="85edb-193">The user needs a higher level of permissions to enable Customer Insights to process the workflow as a service rather than using the user credentials for subsequent runs of the workflow.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
