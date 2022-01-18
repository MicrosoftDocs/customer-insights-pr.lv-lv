---
title: Pielāgoti algoritmiskās mācīšanās modeļi | Microsoft Docs
description: Darbs ar pielāgotiem modeļiem no Azure algoritmiskās mācīšanās pakalpojumā Dynamics 365 Customer Insights.
ms.date: 12/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 8ca30193ae4f4ef3ed9c60f2d694cd11fad46c76
ms.sourcegitcommit: 15b1521041149716f8031cfa6d0dc61a56a5e2ff
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 01/13/2022
ms.locfileid: "7967664"
---
# <a name="custom-machine-learning-models"></a>Pielāgoti algoritmiskās mācīšanās modeļi

> [!NOTE]
> Atbalsts algoritmiskā mācīšanās Studio (klasika) noslēgsies 2024. gada 31. augustā. Ieteicams pāriet uz [Azure algoritmiskā mācīšanās](/azure/machine-learning/overview-what-is-azure-machine-learning) līdz šim datumam.
>
> Sākot ar 2021. gada 1. decembri, jūs nevarēsiet izveidot jaunus algoritmiskā mācīšanās Studio (klasiskos) resursus. Līdz 2024. gada 31. augustam jūs varat turpināt izmantot esošos algoritmiskā mācīšanās Studio (klasiskos) resursus. Papildinformāciju skatiet rakstā [Migrēšana uz Azure algoritmiskā mācīšanās](/azure/machine-learning/migrate-overview).


**Informācija** > **Pielāgotie modeļi** ļauj pārvaldīt darbplūsmas, pamatojoties uz Azure algoritmiskās mācīšanās modeļiem. Darbplūsmas palīdz izvēlēties datus, no kuriem vēlaties ģenerēt ieskatus, un kartēt rezultātus vienotajos klientu datos. Papildinformāciju par pielāgotu algoritmiskās mācīšanās modeļu būvēšanu skatiet tēmā [Azure algoritmiskās mācīšanās modeļu izmantošana](azure-machine-learning-experiments.md).

## <a name="responsible-ai"></a>Atbildīgais AI

Prognozes piedāvā iespējas, kas ļauj izveidot labākas iespējas klientiem, uzlabot biznesa iespējas un ieņēmumu plūsmas. Stingri ieteicams sabalansēt prognoze vērtību pret tās ietekmi un aizspriedumiem, ko var ieviest ētiskā veidā. Uzziniet vairāk par to, kā Microsoft [aplūko atbildīgu AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6). Jūs varat uzzināt arī par [attiecīgo algoritmiskās mācīšanās tehniku un procesiem](/azure/machine-learning/concept-responsible-ml), kas ir raksturīgi Azure algoritmiskajai mācīšanās.

## <a name="prerequisites"></a>Priekšnoteikumi

- Šis līdzeklis atbalsta tīmekļa pakalpojumus, kas publicēti, izmantojot [Azure algoritmiskā mācīšanās pakešu konveijerus](/azure/machine-learning/concept-ml-pipelines).

- Lai izmantotu šo līdzekli, ir nepieciešams Azure Data Lake Gen2 krātuves konts, kas saistīts ar jūsu Azure Studio instanci. Papildinformāciju skatiet [Azure Data Lake Storage Gen2 krātuves konta izveide](/azure/storage/blobs/data-lake-storage-quickstart-create-account).

- Lai nodrošinātu algoritmisko mācīšanos darbvietām ar konveijeriem, ir nepieciešamas īpašnieka vai lietotāja piekļuves administratora atļaujas Azure algoritmiskās mācīšanās darbvietai.

   > [!NOTE]
   > Dati tiek pārsūtīti starp Customer Insights instancēm un darbplūsmā atlasītajiem Azure tīmekļa pakalpojumiem vai konveijeriem. Kad pārsūtāt datus uz pakalpojumu Azure, gādājiet, lai pakalpojums ir konfigurēts tā, ka dati tiek apstrādāti tādā veidā un vietā, kas atbilst jūsu organizācijai noteiktajām juridiskajām vai regulatīvajām prasībām attiecībā uz šiem datiem.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWRElk]

## <a name="add-a-new-workflow"></a>Pievienojiet jaunu darbplūsmu

1. Dodieties uz **Informācija** > **Pielāgotie modeļi** un atlasiet **Jauna darbplūsma**.

1. Piešķiriet jūsu pielāgotajam modelim atpazīstamu nosaukumu laukā **Nosaukums**.

   > [!div class="mx-imgBorder"]
   > ![Jaunās darbplūsmas rūts ekrānuzņēmums.](media/new-workflowv2.png "Jaunās darbplūsmas rūts ekrānuzņēmums")

1. Atlasiet organizāciju, kurā ir iekļauts tīmekļa pakalpojums opcijā **Nomnieks, kas ietver jūsu tīmekļa servisu**.

1. Ja jūsu Azure algoritmiskās mācīšanās abonements ir citā nomnieka, nekā Customer Insights, atlasiet **Pieteikties** ar saviem akreditācijas datiem atlasītajai organizācijai.

1. Atlasiet **Darbvietas**, kas saistītas ar jūsu tīmekļa pakalpojumu. 

1. Izvēlieties Azure algoritmiskā mācīšanās konveijeru **tīmekļa pakalpojumā, kurā ir jūsu modeļa** nolaižamais izvēlne. Pēc tam atlasiet **Tālāk**.    
   Informācija, kā [publicēt konveijeru Azure algoritmiskajās mācībās, izmantojot noformētāju](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) vai [SDK](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk). Jūsu konveijers ir jāpublicē zem [konveijera galapunkta](/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).

1. Katrai **Tīmekļa pakalpojuma ievadei** atlasiet atbilstošo **Entītiju** no auditorijas ieskatiem un atlasiet **Tālāk**.
   > [!NOTE]
   > Pielāgotā modeļa darbplūsma lietos heiristiku, lai tīmekļa pakalpojuma ievades laukus kartētu uz entītijas atribūtiem, pamatojoties uz lauka nosaukumu un datu tipu. Ja tīmekļa pakalpojuma lauku nevar kartēt ar entītiju, tiks parādīts kļūdas ziņojums.

   > [!div class="mx-imgBorder"]
   > ![Konfigurēt darbplūsmu.](media/intelligence-screen2-updated.png "Konfigurēt darbplūsmu")

1. Iestatiet tālāk norādītos rekvizītus solī **Modeļa izvades parametri**:
      1. Ievadiet izvades **Entītijas nosaukumu**, kurā jāievieto konveijera izvades rezultāti.
      1. Atlasiet nolaižamajā sarakstā jūsu paketes konveijera **Izvades datu krātuves parametra nosaukumu**.
      1. Atlasiet nolaižamajā sarakstā jūsu paketes konveijera **Izvades ceļa parametra nosaukumu**.

      > [!div class="mx-imgBorder"]
      > ![Modeļa izvades parametra rūts.](media/intelligence-screen3-outputparameters.png "Modeļa izvades parametrs rūts")

1. Atlasiet atbilstošo atribūtu **Klienta ID rezultātu** nolaižamajā sarakstā, kurā tiek identificēti klienti un atlasiet **Saglabāt**.

   > [!div class="mx-imgBorder"]
   > ![Rezultātu saistīšana ar rūti Klienta dati.](media/intelligence-screen4-relatetocustomer.png "Rezultātu saistīšana ar rūti Klienta dati")

1. Jūs redzēsiet **Darbplūsma saglabāta** ekrānu ar detalizētu informāciju par darbplūsmu.    
   Ja konfigurējāt darbplūsmu Azure algoritmiskās mācīšanās konveijeram, auditorijas ieskati tiks pievienoti darbvietai, kurā ir konveijers. Auditorijas ieskati iegūs **Līdzstrādnieka** lomu Azure darbvietā.

1. Atlasiet **Gatavs**.

1. Tagad darbplūsmu var palaist no lapas **Pielāgotie modeļi**.

## <a name="edit-a-workflow"></a>Darbplūsmas rediģēšana

1. Lapā **Pielāgotie modeļi** atlasiet vertikālās daudzpunktes kolonnā **Darbības** blakus iepriekš izveidotajai darbplūsmai un atlasiet vienumu **Rediģēt**.

1. Darbplūsmas atpazīstamo nosaukumu var atjaunināt laukā **Parādāmais nosaukums**, taču konfigurēto tīmekļa pakalpojumu vai konveijeru nevar mainīt. Atlasiet **Tālāk**.

1. Katrai **Tīmekļa pakalpojuma ievadei** atjauniniet atbilstošo **Entītiju** no auditorijas ieskatiem. Pēc tam atlasiet **Tālāk**.

1. Iestatiet tālāk norādītos rekvizītus solī **Modeļa izvades parametri**:
      1. Ievadiet izvades **Entītijas nosaukumu**, kurā jāievieto konveijera izvades rezultāti.
      1. Atlasiet **Izvades datu krātuves parametra nosaukumu** savam testa konveijeram.
      1. Atlasiet **Izvades ceļa parametra nosaukumu** savam testa konveijeram.

1. Atlasiet atbilstošo atribūtu **Klienta ID rezultātu** nolaižamajā sarakstā, kurā tiek identificēti klienti un atlasiet **Saglabāt**.
   Izvēlieties atribūtu no izvedumapmācību izvades ar vērtībām, kas līdzinās Klienta entītijas kolonnai Klienta ID. Ja datu komplektā nav šādas kolonnas, izvēlieties atribūtu, kas unikāli identificē rindu.

## <a name="run-a-workflow"></a>Darbplūsmas palaišana

1. Lapā **Pielāgotie modeļi** atlasiet vertikālās daudzpunktes kolonnā **Darbības** jūsu blakus iepriekš izveidotajai darbplūsmai.

1. Atlasiet **Izpildīt**.

Jūsu darbplūsma arī tiek palaista automātiski ar katru plānoto atsvaidzināšanu. Papildinformācija par [ieplānotas atsvaidzināšanas iestatīšanu](system.md#schedule-tab).

## <a name="delete-a-workflow"></a>Dzēst darbplūsmu

1. Lapā **Pielāgotie modeļi** atlasiet vertikālās daudzpunktes kolonnā **Darbības** blakus iepriekš jūsu izveidotajai darbplūsmai.

1. Atlasiet **Dzēst** un apstipriniet dzēšanu.

Jūsu darbplūsma tiks izdzēsta. [Entītija](entities.md), kas tika izveidota darbplūsmas izveides laikā, joprojām pastāv un to var skatīt lapā **Entītijas**.

## <a name="results"></a>Rezultāti

Darbplūsmas rezultāti tiek glabāti entītijā, kas ir konfigurēta modeļa izvades parametra posmā. Varat piekļūt šiem datiem no [entītiju lapas](entities.md) vai ar [API piekļuvi](apis.md).

### <a name="api-access"></a>AP piekļuve

Lai iegūtu datus no pielāgotas modeļa entītijas, noteiktam OData vaicājumam izmantojiet tālāk norādīto formātu.

`https://api.ci.ai.dynamics.com/v1/instances/<your instance id>/data/<custom model output entity name>%3Ffilter%3DCustomerId%20eq%20'<guid value>'`

1. Aizstājiet `<your instance id>` ar savas Customer Insights vides ID, kas ir atrodams pārlūkprogrammas adreses joslā, piekļūstot Customer Insights.

1. Aizstājiet `<custom model output entity>` ar entītijas nosaukumu, ko nodrošinājāt pielāgotā modeļa konfigurācijas modeļa izvades parametru darbībā.

1. Aizstājiet `<guid value>` ar tā klienta ID, kura ierakstam vēlaties piekļūt. Šo ID parasti var atrast [klientu profilu lapas](customer-profiles.md) laukā CustomerID .

## <a name="frequently-asked-questions"></a>Bieži uzdotie jautājumi

- Kāpēc, iestatot pielāgotu modeļa darbplūsmu, es neredzu savu konveijeru?    
  Šo problēmu bieži izraisa konveijera konfigurācijas problēma. Nodrošiniet, ka [ievades parametrs ir konfigurēts](azure-machine-learning-experiments.md#dataset-configuration) un tiek konfigurēti arī [izvades datu krātuves un ceļa parametri](azure-machine-learning-experiments.md#import-pipeline-data-into-customer-insights).

- Ko nozīmē kļūda "Nevarēja saglabāt informācijas darbplūsmu"?    
  Lietotāji parasti redz šo kļūdas ziņojumu, ja viņiem darbvietā nav īpašnieka vai lietotāja piekļuves administratora atļauju. Lai Customer Insights darbplūsmu apstrādātu kā servisu, lietotājam ir nepieciešams augstāks atļauju līmenis, nevis lietotāja akreditācijas datu izmantošana turpmākajām darbplūsmas izpildēm.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
