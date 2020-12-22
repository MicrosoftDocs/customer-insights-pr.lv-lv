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
# <a name="custom-machine-learning-models"></a>Pielāgoti algoritmiskās mācīšanās modeļi

**Informācija** > **Pielāgotie modeļi** ļauj pārvaldīt darbplūsmas, pamatojoties uz Azure algoritmiskās mācīšanās modeļiem. Darbplūsmas palīdz izvēlēties datus, no kuriem vēlaties ģenerēt ieskatus, un kartēt rezultātus vienotajos klientu datos. Papildinformāciju par pielāgotu algoritmiskās mācīšanās modeļu būvēšanu skatiet tēmā [Azure algoritmiskās mācīšanās modeļu izmantošana](azure-machine-learning-experiments.md).

## <a name="responsible-ai"></a>Atbildīgais AI

Prognozes piedāvā iespējas, kas ļauj izveidot labākas iespējas klientiem, uzlabot biznesa iespējas un ieņēmumu plūsmas. Stingri ieteicams sabalansēt prognoze vērtību pret tās ietekmi un aizspriedumiem, ko var ieviest ētiskā veidā. Uzziniet vairāk par to, kā Microsoft [aplūko atbildīgu AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6). Jūs varat uzzināt arī par [attiecīgo algoritmiskās mācīšanās tehniku un procesiem](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml), kas ir raksturīgi Azure algoritmiskajai mācīšanās.

## <a name="prerequisites"></a>Priekšnosacījumi

- Patlaban šis līdzeklis atbalsta tīmekļa pakalpojumus, kas tiek publicēti [algoritmiskās mācīšanās studijā (klasiskais)](https://studio.azureml.net) un [Azure algoritmiskā mācīšanās paketes konveijerā](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines).

- Lai izmantotu šo līdzekli, ir nepieciešams Azure Data Lake Gen2 krātuves konts, kas saistīts ar jūsu Azure Studio instanci. Papildinformāciju skatiet [Azure Data Lake Storage Gen2 krātuves konta izveide](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)

## <a name="add-a-new-workflow"></a>Pievienojiet jaunu darbplūsmu

1. Dodieties uz **Informācija** > **Pielāgotie modeļi** un atlasiet **Jauna darbplūsma**.

1. Piešķiriet jūsu pielāgotajam modelim atpazīstamu nosaukumu laukā **Nosaukums**.

   > [!div class="mx-imgBorder"]
   > ![Jaunās darbplūsmas rūts ekrānuzņēmums](media/new-workflowv2.png "Jaunās darbplūsmas rūts ekrānuzņēmums")

1. Atlasiet organizāciju, kurā ir iekļauts tīmekļa pakalpojums opcijā **Nomnieks, kas ietver jūsu tīmekļa servisu**.

1. Ja jūsu Azure algoritmiskās mācīšanās abonements ir citā nomnieka, nekā Customer Insights, atlasiet **Pieteikties** ar saviem akreditācijas datiem atlasītajai organizācijai.

1. Atlasiet **Darbvietas**, kas saistītas ar jūsu tīmekļa pakalpojumu. Ir uzskaitītas divas sadaļas — viena Azure algoritmiskā mācīšanās v1 (algoritmiskā mācīšanās studija (klasiskais)) un Azure algoritmiskā mācīšanās v2 (Azure algoritmiskā mācīšanās). Ja neesat pārliecināts, kura ir īstā darbvieta jūsu algoritmiskās mācīšanās studijai (klasisks) tīmekļa pakalpojumam, atlasiet **Jebkurš**.

1. Izvēlieties algoritmiskās mācīšanās studija (klasisks) tīmekļa pakalpojumu vai Azure algoritmiskā mācīšanās konveijeru nolaižamajā sarakstā **Tīmekļa pakalpojums, kurā ir jūsu modelis**. Pēc tam atlasiet **Tālāk**.
   - Papildinformācija par [tīmekļa pakalpojuma publicēšanu algoritmiskā mācīšanās studijā (klasiskais)](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)
   - Informācija, kā [publicēt konveijeru Azure algoritmiskajās mācībās, izmantojot noformētāju](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) vai [SDK](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk). 
     > [!NOTE]
     > Jūsu konveijers ir jāpublicē zem [konveijera galapunkta](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).

1. Katrai **Tīmekļa pakalpojuma ievadei** atlasiet atbilstošo **Entītiju** no auditorijas ieskatiem un atlasiet **Tālāk**.

   > [!div class="mx-imgBorder"]
   > ![Konfigurēt darbplūsmu](media/intelligence-screen2-updated.png "Konfigurēt darbplūsmu")

1. Iestatiet tālāk norādītos rekvizītus solī **Modeļa izvades parametri**:
   - Algoritmiskā mācīšanās studija (klasiskais)
      1. Ievadiet izvades **Entītijas nosaukumu**, kurā jāievieto tīmekļa pakalpojuma izvades rezultāti.
   - Azure algoritmiskā mācīšanās
      1. Ievadiet izvades **Entītijas nosaukumu**, kurā jāievieto konveijera izvades rezultāti.
      1. Atlasiet nolaižamajā sarakstā jūsu paketes konveijera **Izvades datu krātuves parametra nosaukumu**.
      1. Atlasiet nolaižamajā sarakstā jūsu paketes konveijera **Izvades ceļa parametra nosaukumu**.
      
      > [!div class="mx-imgBorder"]
      > ![Modeļa izvades parametra rūts](media/intelligence-screen3-outputparameters.png "Modeļa izvades parametrs rūts")

1. Atlasiet atbilstošo atribūtu nolaižamajā sarakstā **Klienta ID rezultātos**, kas identificē klientus, un atlasiet **Saglabāt**.
   
   > [!div class="mx-imgBorder"]
   > ![Rezultātu saistīšana ar rūti Klienta dati](media/intelligence-screen4-relatetocustomer.png "Rezultātu saistīšana ar rūti Klienta dati")

1. Jūs redzēsiet **Darbplūsma saglabāta** ekrānu ar detalizētu informāciju par darbplūsmu.    
   Ja konfigurējāt darbplūsmu Azure algoritmiskās mācīšanās konveijeram, auditorijas ieskati tiks pievienoti darbvietai, kurā ir konveijers. Auditorijas ieskati iegūs **Līdzstrādnieka** lomu Azure darbvietā.

1. Atlasiet **Gatavs**.

1. Tagad darbplūsmu var palaist no lapas **Pielāgotie modeļi**.

## <a name="edit-a-workflow"></a>Darbplūsmas rediģēšana

1. Lapā **Pielāgotie modeļi** atlasiet vertikālās daudzpunktes kolonnā **Darbības** blakus iepriekš izveidotajai darbplūsmai un atlasiet vienumu **Rediģēt**.

1. Darbplūsmas atpazīstamo nosaukumu var atjaunināt laukā **Parādāmais nosaukums**, taču konfigurēto tīmekļa pakalpojumu vai konveijeru nevar mainīt. Atlasiet **Tālāk**.

1. Katrai **Tīmekļa pakalpojuma ievadei** atjauniniet atbilstošo **Entītiju** no auditorijas ieskatiem. Pēc tam atlasiet **Tālāk**.

1. Iestatiet tālāk norādītos rekvizītus solī **Modeļa izvades parametri**:
   - Algoritmiskā mācīšanās studija (klasiskais)
      1. Ievadiet izvades **Entītijas nosaukumu**, kurā jāievieto tīmekļa pakalpojuma izvades rezultāti.
   - Azure algoritmiskā mācīšanās
      1. Ievadiet izvades **Entītijas nosaukumu**, kurā jāievieto konveijera izvades rezultāti.
      1. Atlasiet **Izvades datu krātuves parametra nosaukumu** savam testa konveijeram.
      1. Atlasiet **Izvades ceļa parametra nosaukumu** savam testa konveijeram.

1. Atlasiet atbilstošo atribūtu nolaižamajā sarakstā **Klienta ID rezultātos**, kas identificē klientus, un atlasiet **Saglabāt**.
   Jums ir nepieciešams izvēlēties atribūtu no izvedumapmācību izvades ar vērtībām, kas līdzinās Klienta entītijas kolonnai Klienta ID. Ja datu komplektā nav šādas kolonnas, izvēlieties atribūtu, kas unikāli identificē rindu.

## <a name="run-a-workflow"></a>Darbplūsmas palaišana

1. Lapā **Pielāgotie modeļi** atlasiet vertikālās daudzpunktes kolonnā **Darbības** jūsu blakus iepriekš izveidotajai darbplūsmai.

1. Atlasiet **Izpildīt**.

Jūsu darbplūsma arī tiek palaista automātiski ar katru plānoto atsvaidzināšanu. Papildinformācija par [ieplānotas atsvaidzināšanas iestatīšanu](system.md#schedule-tab).

## <a name="delete-a-workflow"></a>Dzēst darbplūsmu

1. Lapā **Pielāgotie modeļi** atlasiet vertikālās daudzpunktes kolonnā **Darbības** blakus iepriekš jūsu izveidotajai darbplūsmai.

1. Atlasiet **Dzēst** un apstipriniet dzēšanu.

Jūsu darbplūsma tiks izdzēsta. [Entītija](entities.md), kas tika izveidota darbplūsmas izveides laikā, joprojām pastāv un to var skatīt lapā **Entītijas**.
