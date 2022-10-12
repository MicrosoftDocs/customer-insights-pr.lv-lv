---
title: Izmantojiet Azure algoritmiskās mācības modeļus.
description: Izmantojiet Azure algoritmiskās mācības modeļus programmā Dynamics 365 Customer Insights.
ms.date: 09/22/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: naravill
ms.author: naravill
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 8d9c9324ea4840b585b9af1a58d505ccaea6f18e
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609834"
---
# <a name="use-azure-machine-learning-based-models"></a>Izmantojiet Azure algoritmiskās mācības modeļus.

Vienotie dati Dynamics 365 Customer Insights ir avots, kas paredzēts algoritmiskās mācīšanās modeļu izveidei, kas var radīt papildu biznesa ieskatus. Customer Insights integrējas ar Azure algoritmisko mācīšanos, lai jūs izmantotu paši savus pielāgotos modeļus.

## <a name="prerequisites"></a>Priekšnosacījumi

- Piekļuve Customer Insights
- Aktīvs Azure Enterprise abonements
- [Vienoti klientu profili](data-unification.md)
- [Entītijas eksportēšana uz Azure BLOB krātuvi](export-azure-blob-storage.md) ir konfigurēta

## <a name="set-up-azure-machine-learning-workspace"></a>Iestatīt Azure algoritmiskās mācīšanās darbvietu

1. Skatiet sadaļu [Azure algoritmiskās mācīšanās darbvietas izveide](/azure/machine-learning/concept-workspace#-create-a-workspace) dažādām darbvietas izveides opcijām. Lai nodrošinātu vislabākos rezultātus, izveidojiet darbvietu Azure reģionā, kas ģeogrāfiski ir vistuvāk jūsu Customer Insights videi.

1. Piekļūstiet darbvietai, lietojot [Azure algoritmiskās mācīšanās studiju](https://ml.azure.com/). Pastāv vairāki [veidi, kā mijiedarboties](/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) ar darbvietu.

## <a name="work-with-azure-machine-learning-designer"></a>Darbs ar Azure algoritmiskās mācīšanās noformētāju

Azure algoritmiskā mācīšanās noformētājs nodrošina vizuālu audeklu, kurā varat vilkt un nomest datu kopas un moduļus. No noformētāja izveidotu paketes konveijeru var integrēt Customer Insights, ja tie ir attiecīgi konfigurēti. 

## <a name="working-with-azure-machine-learning-sdk"></a>Darbs ar Azure algoritmiskās mācīšanās noformētāju SDK

Datu zinātnieki un AI izstrādātāji izmanto [Azure algoritmiskās mācīšanās SDK](/python/api/overview/azure/ml/?preserve-view=true&view=azure-ml-py), lai būvētu algoritmiskās mācīšanās darbplūsmas. Pašlaik modeļus, kas ir apmācīti, izmantojot SDK, nevar tieši integrēt ar Customer Insights. Paketes izvedumkonveijers, kas patērē konkrēto modeli, ir nepieciešams integrācijai ar Customer Insights.

## <a name="batch-pipeline-requirements-to-integrate-with-customer-insights"></a>Paketes konveijeru prasības integrēšanai ar Customer Insights

### <a name="dataset-configuration"></a>Datu kopas konfigurācija

Izveidojiet datu kopas, lai izmantotu entītiju datus no Customer Insights savam pakešu secinājumu konveijeram. Reģistrējiet šīs datu kopas darbvietā. Pašlaik tiek atbalstīti tikai [tabulu datu kopas](/azure/machine-learning/how-to-create-register-datasets#tabulardataset) .csv formātā. Parametrizējiet datu kopas, kas atbilst entītijas datiem, kā konveijera parametru.

- Datu kopas parametri noformētājā

  Noformētājā atveriet **Atlasīt kolonnas datu kopā** un atlasiet **Iestatīt kā konveijera parametru**, kur norādīsit parametra nosaukumu.

  :::image type="content" source="media/intelligence-designer-dataset-parameters.png" alt-text="Datu kopas parametri noformētājā.":::

- Datu kopas parametrs SDK (Python)

   ```python
   HotelStayActivity_dataset = Dataset.get_by_name(ws, name='Hotel Stay Activity Data')
   HotelStayActivity_pipeline_param = PipelineParameter(name="HotelStayActivity_pipeline_param", default_value=HotelStayActivity_dataset)
   HotelStayActivity_ds_consumption = DatasetConsumptionConfig("HotelStayActivity_dataset", HotelStayActivity_pipeline_param)
   ```

### <a name="batch-inference-pipeline"></a>Paketes izvedumkonveijers
  
- Noformētājā izmantojiet apmācības konveijeru, lai izveidotu vai atjauninātu secinājumu konveijeru. Pašlaik tiek atbalstīti tikai pakešu izvedumkonveijeri.

- Izmantojot SDK, publicējiet konveijeru galapunktā. Pašlaik Customer Insights ir integrēti ar noklusējuma konveijeru pakešu konveijera galapunktā algoritmiskās mācīšanās darbvietā.

   ```python
   published_pipeline = pipeline.publish(name="ChurnInferencePipeline", description="Published Churn Inference pipeline")
   pipeline_endpoint = PipelineEndpoint.get(workspace=ws, name="ChurnPipelineEndpoint") 
   pipeline_endpoint.add_default(pipeline=published_pipeline)
   ```

### <a name="import-pipeline-data-into-customer-insights"></a>Konveijera datu importēšana Customer Insights

- Noformētājs nodrošina [Datu moduļa eksportēšanu](/azure/machine-learning/algorithm-module-reference/export-data), kas ļauj eksportēt konveijera izvadi uz Azure krātuvi. Pašlaik modulim ir jāizmanto datu uzglabāšanas veidu **Azure BLOB krātuve** un iedalīt pēc parametriem **Datu krātuvi** un relatīvo **Ceļu**. Customer Insights ignorē gan šos parametrus konveijera izpildes laikā ar produktam pieejamo datu krātuvi un ceļu.

  :::image type="content" source="media/intelligence-designer-importdata.png" alt-text="Portāla konfigurācijas datu eksportēšana.":::

- Rakstot secinājumu izvadi, izmantojot kodu, augšupielādējiet izvadi uz ceļa, kas *atrodas reģistrētā datu krātuvē* darbvietā. Ja ceļš un datu krātuve ir iedalīta pēc parametriem konveijerā, Customer Insights varēs lasīt un importēt izvades slēdzienu. Patlaban tiek atbalstīta vienkārša tabulārā izvade CSV formātā. Ceļam ir jāiekļauj direktorija un faila nosaukums.

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


[!INCLUDE [footer-include](includes/footer-banner.md)]