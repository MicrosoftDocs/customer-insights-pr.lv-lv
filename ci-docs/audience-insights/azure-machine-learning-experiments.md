---
title: Azure algoritmiskās mācīšanās eksperimenti
description: Izmantojiet Azure algoritmiskās mācības modeļus programmā Dynamics 365 Customer Insights.
ms.date: 11/30/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: naravill
ms.author: mhart
ms.reviewer: m-hartmann
manager: shellyha
ms.openlocfilehash: 6f00d3202dc29d810bdd218d06c7d04e551846e8
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668777"
---
# <a name="use-azure-machine-learning-based-models"></a><span data-ttu-id="5d83d-103">Izmantojiet Azure algoritmiskās mācības modeļus.</span><span class="sxs-lookup"><span data-stu-id="5d83d-103">Use Azure Machine Learning-based models</span></span>

<span data-ttu-id="5d83d-104">Vienotie dati Dynamics 365 Customer Insights ir avots, kas paredzēts algoritmiskās mācīšanās modeļu izveidei, kas var radīt papildu biznesa ieskatus.</span><span class="sxs-lookup"><span data-stu-id="5d83d-104">The unified data in Dynamics 365 Customer Insights is a source for building machine learning models that can generate additional business insights.</span></span> <span data-ttu-id="5d83d-105">Customer Insights integrējas ar algoritmiskās mācīšanās studiju (klasiskais) un Azure algoritmisko mācīšanos, lai izmantotu savus pielāgotos modeļus.</span><span class="sxs-lookup"><span data-stu-id="5d83d-105">Customer Insights integrates with Machine Learning Studio (classic) and Azure Machine Learning to use your own custom models.</span></span> <span data-ttu-id="5d83d-106">Skatiet [Algoritmiskās mācīšanās studijas (klasiskais) eksperimentus](machine-learning-studio-experiments.md), kas attiecas uz algoritmiskās mācīšanās studijā būvētajiem eksperimentiem (klasiskie).</span><span class="sxs-lookup"><span data-stu-id="5d83d-106">Refer to [Machine Learning Studio (classic) experiments](machine-learning-studio-experiments.md) for examples of experiments built on Machine Learning Studio (classic).</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="5d83d-107">Priekšnosacījumi</span><span class="sxs-lookup"><span data-stu-id="5d83d-107">Prerequisites</span></span>

- <span data-ttu-id="5d83d-108">Piekļuve Customer Insights</span><span class="sxs-lookup"><span data-stu-id="5d83d-108">Access to Customer Insights</span></span>
- <span data-ttu-id="5d83d-109">Aktīvs Azure Enterprise abonements</span><span class="sxs-lookup"><span data-stu-id="5d83d-109">Active Azure Enterprise subscription</span></span>
- [<span data-ttu-id="5d83d-110">Vienoti klientu profili</span><span class="sxs-lookup"><span data-stu-id="5d83d-110">Unified customer profiles</span></span>](data-unification.md)
- <span data-ttu-id="5d83d-111">[Entītijas eksportēšana uz Azure BLOB krātuvi](export-azure-blob-storage.md) ir konfigurēta</span><span class="sxs-lookup"><span data-stu-id="5d83d-111">[Entity export to Azure Blob storage](export-azure-blob-storage.md) configured</span></span>

## <a name="set-up-azure-machine-learning-workspace"></a><span data-ttu-id="5d83d-112">Iestatīt Azure algoritmiskās mācīšanās darbvietu</span><span class="sxs-lookup"><span data-stu-id="5d83d-112">Set up Azure Machine Learning workspace</span></span>

1. <span data-ttu-id="5d83d-113">Skatiet sadaļu [Azure algoritmiskās mācīšanās darbvietas izveide](https://docs.microsoft.com/azure/machine-learning/concept-workspace#-create-a-workspace) dažādām darbvietas izveides opcijām.</span><span class="sxs-lookup"><span data-stu-id="5d83d-113">See [create a Azure Machine Learning workspace](https://docs.microsoft.com/azure/machine-learning/concept-workspace#-create-a-workspace) for different options to create the workspace.</span></span> <span data-ttu-id="5d83d-114">Lai nodrošinātu vislabākos rezultātus, izveidojiet darbvietu Azure reģionā, kas ģeogrāfiski ir vistuvāk jūsu Customer Insights videi.</span><span class="sxs-lookup"><span data-stu-id="5d83d-114">For best performance, create the workspace in an Azure region that is geographically closest to your Customer Insights environment.</span></span>

1. <span data-ttu-id="5d83d-115">Piekļūstiet darbvietai, lietojot [Azure algoritmiskās mācīšanās studiju](https://ml.azure.com/).</span><span class="sxs-lookup"><span data-stu-id="5d83d-115">Access your workspace through the [Azure Machine Learning Studio](https://ml.azure.com/).</span></span> <span data-ttu-id="5d83d-116">Pastāv vairāki [veidi, kā mijiedarboties](https://docs.microsoft.com/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) ar darbvietu.</span><span class="sxs-lookup"><span data-stu-id="5d83d-116">There are several [ways to interact](https://docs.microsoft.com/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) with your workspace.</span></span>

## <a name="work-with-azure-machine-learning-designer"></a><span data-ttu-id="5d83d-117">Darbs ar Azure algoritmiskās mācīšanās noformētāju</span><span class="sxs-lookup"><span data-stu-id="5d83d-117">Work with Azure Machine Learning designer</span></span>

<span data-ttu-id="5d83d-118">Azure algoritmiskās mācīšanās noformētājs nodrošina vizuālu pamatni, kurā var aizvilkt un nomest datu kopas un moduļus, līdzīgi kā algoritmiskā mācīšanās studijā (klasiskais).</span><span class="sxs-lookup"><span data-stu-id="5d83d-118">Azure Machine Learning designer provides a visual canvas where you can drag and drop datasets and modules, similar to Machine Learning Studio (classic).</span></span> <span data-ttu-id="5d83d-119">No noformētāja izveidotu paketes konveijeru var integrēt Customer Insights, ja tie ir attiecīgi konfigurēti.</span><span class="sxs-lookup"><span data-stu-id="5d83d-119">A batch pipeline created from the designer can be integrated into Customer Insights if they are configured accordingly.</span></span> 
   
## <a name="working-with-azure-machine-learning-sdk"></a><span data-ttu-id="5d83d-120">Darbs ar Azure algoritmiskās mācīšanās noformētāju SDK</span><span class="sxs-lookup"><span data-stu-id="5d83d-120">Working with Azure Machine Learning SDK</span></span>

<span data-ttu-id="5d83d-121">Datu zinātnieki un AI izstrādātāji izmanto [Azure algoritmiskās mācīšanās SDK](https://docs.microsoft.com/python/api/overview/azure/ml/?view=azure-ml-py&preserve-view=true), lai būvētu algoritmiskās mācīšanās darbplūsmas.</span><span class="sxs-lookup"><span data-stu-id="5d83d-121">Data scientists and AI developers use the [Azure Machine Learning SDK](https://docs.microsoft.com/python/api/overview/azure/ml/?view=azure-ml-py&preserve-view=true) to build machine learning workflows.</span></span> <span data-ttu-id="5d83d-122">Pašlaik modeļus, kas ir apmācīti, izmantojot SDK, nevar tieši integrēt ar Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="5d83d-122">Currently, models trained using the SDK can't be integrated directly with Customer Insights.</span></span> <span data-ttu-id="5d83d-123">Paketes izvedumkonveijers, kas patērē konkrēto modeli, ir nepieciešams integrācijai ar Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="5d83d-123">A batch inference pipeline that consumes that model is required for integration with Customer Insights.</span></span>

## <a name="batch-pipeline-requirements-to-integrate-with-customer-insights"></a><span data-ttu-id="5d83d-124">Paketes konveijeru prasības integrēšanai ar Customer Insights</span><span class="sxs-lookup"><span data-stu-id="5d83d-124">Batch pipeline requirements to integrate with Customer Insights</span></span>

### <a name="dataset-configuration"></a><span data-ttu-id="5d83d-125">Konfigurācijas datu kopa</span><span class="sxs-lookup"><span data-stu-id="5d83d-125">Dataset Configuration</span></span>

<span data-ttu-id="5d83d-126">Jums ir nepieciešams izveidot datu kopas, lai izmantotu entītijas datus no Customer Insights uz jūsu paketes izvedumkonveijeru.</span><span class="sxs-lookup"><span data-stu-id="5d83d-126">You need to create datasets to use entity data from Customer Insights to your batch inference pipeline.</span></span> <span data-ttu-id="5d83d-127">Šīm datu kopām ir jābūt reģistrētām darbvietā.</span><span class="sxs-lookup"><span data-stu-id="5d83d-127">These datasets need to be registered in the workspace.</span></span> <span data-ttu-id="5d83d-128">Pašlaik tiek atbalstīti tikai [tabulu datu kopas](https://docs.microsoft.com/azure/machine-learning/how-to-create-register-datasets#tabulardataset) .csv formātā.</span><span class="sxs-lookup"><span data-stu-id="5d83d-128">Currently, we only support [tabular datasets](https://docs.microsoft.com/azure/machine-learning/how-to-create-register-datasets#tabulardataset) in .csv format.</span></span> <span data-ttu-id="5d83d-129">Datu kopām, kas atbilst entītiju datiem, ir jābūt iedalītām pēc parametriem kā konveijera parametram.</span><span class="sxs-lookup"><span data-stu-id="5d83d-129">The datasets that correspond to entity data need to be parameterized as a pipeline parameter.</span></span>
   
* <span data-ttu-id="5d83d-130">Datu kopas parametri noformētājā</span><span class="sxs-lookup"><span data-stu-id="5d83d-130">Dataset parameters in Designer</span></span>
   
     <span data-ttu-id="5d83d-131">Noformētājā atveriet **Atlasīt kolonnas datu kopā** un atlasiet **Iestatīt kā konveijera parametru**, kur norādīsit parametra nosaukumu.</span><span class="sxs-lookup"><span data-stu-id="5d83d-131">In the designer, open **Select Columns in Dataset** and select **Set as pipeline parameter** where you provide a name for the parameter.</span></span>

     > [!div class="mx-imgBorder"]
     > <span data-ttu-id="5d83d-132">![Datu kopas parametri noformētājā](media/intelligence-designer-dataset-parameters.png "Datu kopas parametri noformētājā")</span><span class="sxs-lookup"><span data-stu-id="5d83d-132">![Dataset parameterization in designer](media/intelligence-designer-dataset-parameters.png "Dataset parameterization in designer")</span></span>
   
* <span data-ttu-id="5d83d-133">Datu kopas parametrs SDK (Python)</span><span class="sxs-lookup"><span data-stu-id="5d83d-133">Dataset parameter in SDK (Python)</span></span>
   
   ```python
   HotelStayActivity_dataset = Dataset.get_by_name(ws, name='Hotel Stay Activity Data')
   HotelStayActivity_pipeline_param = PipelineParameter(name="HotelStayActivity_pipeline_param", default_value=HotelStayActivity_dataset)
   HotelStayActivity_ds_consumption = DatasetConsumptionConfig("HotelStayActivity_dataset", HotelStayActivity_pipeline_param)
   ```

### <a name="batch-inference-pipeline"></a><span data-ttu-id="5d83d-134">Paketes izvedumkonveijers</span><span class="sxs-lookup"><span data-stu-id="5d83d-134">Batch inference pipeline</span></span>
  
* <span data-ttu-id="5d83d-135">Noformētājā mācību konveijeru var izmantot izvedumkonveijeru izveidei vai atjaunināšanai.</span><span class="sxs-lookup"><span data-stu-id="5d83d-135">In the designer, a training pipeline can be used to create or update an inference pipeline.</span></span> <span data-ttu-id="5d83d-136">Pašlaik tiek atbalstīti tikai pakešu izvedumkonveijeri.</span><span class="sxs-lookup"><span data-stu-id="5d83d-136">Currently, only batch inference pipelines are supported.</span></span>

* <span data-ttu-id="5d83d-137">Izmantojot SDK, varat publicēt konveijeru galapunktā.</span><span class="sxs-lookup"><span data-stu-id="5d83d-137">Using the SDK, you can publish the pipeline to an endpoint.</span></span> <span data-ttu-id="5d83d-138">Pašlaik Customer Insights ir integrēti ar noklusējuma konveijeru pakešu konveijera galapunktā algoritmiskās mācīšanās darbvietā.</span><span class="sxs-lookup"><span data-stu-id="5d83d-138">Currently, Customer Insights integrates with the default pipeline in a batch pipeline endpoint in the Machine Learning workspace.</span></span>
   
   ```python
   published_pipeline = pipeline.publish(name="ChurnInferencePipeline", description="Published Churn Inference pipeline")
   pipeline_endpoint = PipelineEndpoint.get(workspace=ws, name="ChurnPipelineEndpoint") 
   pipeline_endpoint.add_default(pipeline=published_pipeline)
   ```

### <a name="import-pipeline-data-into-customer-insights"></a><span data-ttu-id="5d83d-139">Konveijera datu importēšana Customer Insights</span><span class="sxs-lookup"><span data-stu-id="5d83d-139">Import pipeline data into Customer Insights</span></span>

* <span data-ttu-id="5d83d-140">Noformētājs nodrošina [Datu moduļa eksportēšanu](https://docs.microsoft.com/azure/machine-learning/algorithm-module-reference/export-data), kas ļauj eksportēt konveijera izvadi uz Azure krātuvi.</span><span class="sxs-lookup"><span data-stu-id="5d83d-140">The designer provides the [Export Data module](https://docs.microsoft.com/azure/machine-learning/algorithm-module-reference/export-data) that allows the output of a pipeline to be exported to Azure storage.</span></span> <span data-ttu-id="5d83d-141">Pašlaik modulim ir jāizmanto datu uzglabāšanas veidu **Azure BLOB krātuve** un iedalīt pēc parametriem **Datu krātuvi** un relatīvo **Ceļu**.</span><span class="sxs-lookup"><span data-stu-id="5d83d-141">Currently, the module must use the datastore type **Azure Blob Storage** and parameterize the **Datastore** and relative **Path**.</span></span> <span data-ttu-id="5d83d-142">Customer Insights ignorē gan šos parametrus konveijera izpildes laikā ar produktam pieejamo datu krātuvi un ceļu.</span><span class="sxs-lookup"><span data-stu-id="5d83d-142">Customer Insights overrides both these parameters during pipeline execution with a datastore and path that is accessible to the product.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="5d83d-143">![Portāla konfigurācijas datu eksportēšana](media/intelligence-designer-importdata.png "Datu moduļa konfigurācijas eksportēšana")</span><span class="sxs-lookup"><span data-stu-id="5d83d-143">![Export Data Module Configuration](media/intelligence-designer-importdata.png "Export Data Module Configuration")</span></span>
   
* <span data-ttu-id="5d83d-144">Rakstot slēdzienu par izvadi, izmantojot kodu, varat augšupielādēt izvadi, kas atrodas darbvietā *reģistrētā datu krātuvē*.</span><span class="sxs-lookup"><span data-stu-id="5d83d-144">When writing the inference output using code, you can upload the output to the a path within a *registered datastore* in the workspace.</span></span> <span data-ttu-id="5d83d-145">Ja ceļš un datu krātuve ir iedalīta pēc parametriem konveijerā, Customer Insights varēs lasīt un importēt izvades slēdzienu.</span><span class="sxs-lookup"><span data-stu-id="5d83d-145">If the path and datastore are parameterized in the pipeline, Customer insights will be able to read and import the inference output.</span></span> <span data-ttu-id="5d83d-146">Patlaban tiek atbalstīta vienkārša tabulārā izvade CSV formātā.</span><span class="sxs-lookup"><span data-stu-id="5d83d-146">Currently, a single tabular output in csv format is supported.</span></span> <span data-ttu-id="5d83d-147">Ceļam ir jāiekļauj direktorija un faila nosaukums.</span><span class="sxs-lookup"><span data-stu-id="5d83d-147">The path must include the directory and filename.</span></span>

   ```python
   # In Pipeline setup script
      OutputPathParameter = PipelineParameter(name="output_path", default_value="HotelChurnOutput/HotelChurnOutput.csv")
      OutputDatastoreParameter = PipelineParameter(name="output_datastore", default_value="workspaceblobstore")
   ...
   # In pipeline execution script
      run = Run.get_context()
      ws = run.experiment.workspace
      datastore = Datastore.get(ws, output_datastore) # output_datastore is parameterized
      directory_name =  os.path.dirname(output_path)  # output_path is parameterized.
      
      # Datastore.upload() or Dataset.File.upload_directory() are supported methods to uplaod the data
      # datastore.upload(src_dir=<<working directory>>, target_path=directory_name, overwrite=False, show_progress=True)
      output_dataset = Dataset.File.upload_directory(src_dir=<<working directory>>, target = (datastore, directory_name)) # Remove trailing "/" from directory_name
   ```
