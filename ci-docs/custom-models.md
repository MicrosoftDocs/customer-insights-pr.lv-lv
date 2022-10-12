---
title: Pielāgoti algoritmiskās mācīšanās modeļi | Microsoft Docs
description: Darbs ar pielāgotiem modeļiem no Azure algoritmiskās mācīšanās pakalpojumā Dynamics 365 Customer Insights.
ms.date: 09/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: zacookmsft
ms.author: zacook
manager: shellyha
searchScope:
- ci-custom-models
- customerInsights
ms.openlocfilehash: 89553b511d249fd586e36a1c4944a977513b0643
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609755"
---
# <a name="custom-machine-learning-models"></a>Pielāgoti algoritmiskās mācīšanās modeļi

> [!NOTE]
> Atbalsts algoritmiskā mācīšanās Studio (klasika) beigsies 2024. gada 31. augustā. Līdz šim datumam ieteicams pāriet uz [Azure algoritmiskā mācīšanās](/azure/machine-learning/overview-what-is-azure-machine-learning).
>
> Sākot ar 2021. gada 1. decembri, jūs nevarēsit izveidot jaunus algoritmiskā mācīšanās Studio (klasisko) resursus. Līdz 2024. gada 31. augustam varat turpināt izmantot esošos algoritmiskā mācīšanās Studio (klasisko) resursus. Papildinformāciju skatiet sadaļā [Migrēšana uz Azure algoritmiskā mācīšanās](/azure/machine-learning/migrate-overview).

Pielāgotie modeļi ļauj pārvaldīt darbplūsmas, kuru pamatā ir Azure algoritmiskā mācīšanās modeļi. Darbplūsmas palīdz izvēlēties datus, no kuriem vēlaties ģenerēt ieskatus, un kartēt rezultātus vienotajos klientu datos. Papildinformāciju par pielāgotu algoritmiskās mācīšanās modeļu būvēšanu skatiet tēmā [Azure algoritmiskās mācīšanās modeļu izmantošana](azure-machine-learning-experiments.md).

## <a name="prerequisites"></a>Priekšnoteikumi

- Tīmekļa pakalpojumi, kas publicēti, izmantojot [Azure, algoritmiskā mācīšanās pakešu konveijerus](/azure/machine-learning/concept-ml-pipelines).
- Konveijers ir jāpublicē zem konveijera [galapunkta](/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).
- Azure Data Lake Gen2 krātuves [konts,](/azure/storage/blobs/data-lake-storage-quickstart-create-account) kas saistīts ar jūsu Azure Studio instanci.
- Azure algoritmiskā mācīšanās darbvietas ar konveijeriem, īpašnieka vai lietotāja piekļuves administratora atļaujas Azure algoritmiskā mācīšanās Workspace.

  > [!NOTE]
  > Dati tiek pārsūtīti starp Customer Insights instancēm un darbplūsmā atlasītajiem Azure tīmekļa pakalpojumiem vai konveijeriem. Kad pārsūtāt datus uz pakalpojumu Azure, gādājiet, lai pakalpojums ir konfigurēts tā, ka dati tiek apstrādāti tādā veidā un vietā, kas atbilst jūsu organizācijai noteiktajām juridiskajām vai regulatīvajām prasībām attiecībā uz šiem datiem.

## <a name="add-a-new-workflow"></a>Pievienojiet jaunu darbplūsmu

1. Dodieties uz **Informācija** > **Pielāgotie modeļi** un atlasiet **Jauna darbplūsma**.

1. Norādiet atpazīstamu **Vārdu**.

   :::image type="content" source="media/new-workflowv2.png" alt-text="Jaunās darbplūsmas rūts ekrānuzņēmums.":::

1. Atlasiet organizāciju, kurā ir iekļauts tīmekļa pakalpojums opcijā **Nomnieks, kas ietver jūsu tīmekļa servisu**.

1. Ja jūsu Azure algoritmiskās mācīšanās abonements ir citā nomnieka, nekā Customer Insights, atlasiet **Pieteikties** ar saviem akreditācijas datiem atlasītajai organizācijai.

1. Atlasiet **Darbvietas**, kas saistītas ar jūsu tīmekļa pakalpojumu.

1. Web pakalpojumā izvēlieties Azure algoritmiskā mācīšanās konveijeru **, kurā ir nolaižamā modeļa** izvēlne. Pēc tam atlasiet **Tālāk**.
   Informācija, kā [publicēt konveijeru Azure algoritmiskajās mācībās, izmantojot noformētāju](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) vai [SDK](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).

1. Katrai **tīmekļa pakalpojuma ievadei** atlasiet atbilstošo **entītiju** no Customer Insights. Pēc tam atlasiet **Tālāk**.
   > [!NOTE]
   > Pielāgotā modeļa darbplūsma lietos heiristiku, lai tīmekļa pakalpojuma ievades laukus kartētu uz entītijas atribūtiem, pamatojoties uz lauka nosaukumu un datu tipu. Ja tīmekļa pakalpojuma lauku nevar kartēt ar entītiju, tiks parādīts kļūdas ziņojums.

   :::image type="content" source="media/intelligence-screen2-updated.png" alt-text="Konfigurēt darbplūsmu.":::

1. Modeļa **izvades parametriem** iestatiet šādus rekvizītus:
   - **Konveijera izvades rezultātu entītijas nosaukums**
   - **Pakešu konveijera izvades datu krātuve parametra nosaukums**
   - **Izvades ceļa parametra nosaukums** pakešveijeram

   :::image type="content" source="media/intelligence-screen3-outputparameters.png" alt-text="Modeļa izvades parametra rūts.":::

1. Rezultātos atlasiet atbilstošo atribūtu no **Klienta ID**, kas identificē klientus, un atlasiet **Saglabāt**.

   :::image type="content" source="media/intelligence-screen4-relatetocustomer.png" alt-text="Rezultātu saistīšana ar rūti Klienta dati.":::

   Ekrānā Darbplūsmas **saglabāšana** tiek parādīta detalizēta informācija par darbplūsmu. Ja konfigurējāt darbplūsmu Azure algoritmiskā mācīšanās konveijeram, Customer Insights tiek pievienots darbvietai, kurā ir konveijers. Customer Insights iegūs līdzstrādnieka **lomu** Azure darbvietā.

1. Atlasiet **Gatavs**. Tiek **parādīta lapa Pielāgotie modeļi**.

1. Atlasiet darbplūsmas vertikālo elipsi (&vellip;) un atlasiet **Palaist**. Darbplūsma tiek izpildīta arī automātiski ar katru [ieplānoto atsvaidzināšanu](schedule-refresh.md).

## <a name="manage-an-existing-workflow"></a>Esošas darbplūsmas pārvaldība

Dodieties uz **Intelligence** > **Custom modeļiem**, lai skatītu izveidotās darbplūsmas.

Atlasiet darbplūsmu, lai skatītu pieejamās darbības.

- **Darbplūsmas rediģēšana**
- **Darbplūsmas palaišana**
- [**Darbplūsmas dzēšana**](#delete-a-workflow)

### <a name="edit-a-workflow"></a>Darbplūsmas rediģēšana

1. Dodieties uz **Sadaļu Inteliģences** > **pielāgotie modeļi**.

1. Blakus darbplūsmai, kuru vēlaties atjaunināt, atlasiet vertikālo daudzpunkti (&vellip;) un atlasiet **Rediģēt**.

1. Ja nepieciešams, mainiet **parādāmo vārdu** un atlasiet **Tālāk**.

1. **Katrai Tīmekļa pakalpojuma ievadei**, ja nepieciešams, atjauniniet atbilstošo **entītiju** no Customer Insights. Pēc tam atlasiet **Tālāk**.

1. Modeļa **izvades parametriem** mainiet kādu no šīm darbībām:
   - **Konveijera izvades rezultātu entītijas nosaukums**
   - **Pakešu konveijera izvades datu krātuve parametra nosaukums**
   - **Izvades ceļa parametra nosaukums** pakešveijeram

1. Rezultātos **mainiet atbilstošo atribūtu no** Klienta ID, lai identificētu klientus. Izvēlieties atribūtu no izvedumapmācību izvades ar vērtībām, kas līdzinās Klienta entītijas kolonnai Klienta ID. Ja datu kopā nav šādas kolonnas, izvēlieties atribūtu, kas unikāli identificē rindu.

1. Atlasiet vienumu **Saglabāt**

### <a name="delete-a-workflow"></a>Dzēst darbplūsmu

1. Dodieties uz **Sadaļu Inteliģences** > **pielāgotie modeļi**.

1. Blakus darbplūsmai, kuru vēlaties dzēst, atlasiet vertikālo daudzpunkti (&vellip;) un atlasiet **Dzēst**.

1. Apstipriniet dzēšanu.

Jūsu darbplūsma tiks izdzēsta. Entītija [, kas tika izveidota, izveidojot darbplūsmu, saglabājas, un to var skatīt no](entities.md) lapas Datu **elementi** > **.**

## <a name="view-the-results"></a>Skatīt rezultātus

Darbplūsmas rezultāti tiek saglabāti entītijas nosaukumā, kas definēts modeļa **izvades parametriem**. Piekļūstiet šiem datiem no [**lapas** > **Datu** elementi](entities.md) vai ar [API piekļuvi](apis.md).

### <a name="api-access"></a>AP piekļuve

Lai iegūtu datus no pielāgotas modeļa entītijas, noteiktam OData vaicājumam izmantojiet tālāk norādīto formātu.

`https://api.ci.ai.dynamics.com/v1/instances/<your instance id>/data/<custom model output entity name>%3Ffilter%3DCustomerId%20eq%20'<guid value>'`

1. Aizstājiet `<your instance id>` ar savas Customer Insights vides ID, kas, piekļūstot Customer Insights, tiek rādīta pārlūkprogrammas adreses joslā.

1. Aizstājiet `<custom model output entity>` ar entītijas nosaukumu, ko norādījāt **modeļa izvades parametriem**.

1. Aizstājiet `<guid value>` ar tā klienta ID, kuram vēlaties piekļūt. Šis ID tiek parādīts [klienta profilu lapā](customer-profiles.md) laukā CustomerID.

## <a name="frequently-asked-questions"></a>Biežāk uzdotie jautājumi

- Kāpēc, iestatot pielāgotu modeļa darbplūsmu, es neredzu savu konveijeru?
  Šo problēmu bieži izraisa konveijera konfigurācijas problēma. Nodrošiniet, ka [ievades parametrs ir konfigurēts](azure-machine-learning-experiments.md#dataset-configuration) un tiek konfigurēti arī [izvades datu krātuves un ceļa parametri](azure-machine-learning-experiments.md#import-pipeline-data-into-customer-insights).

- Ko nozīmē kļūda "Nevarēja saglabāt informācijas darbplūsmu"? 
  Lietotāji parasti redz šo kļūdas ziņojumu, ja viņiem darbvietā nav īpašnieka vai lietotāja piekļuves administratora atļauju. Lai Customer Insights darbplūsmu apstrādātu kā servisu, lietotājam ir nepieciešams augstāks atļauju līmenis, nevis lietotāja akreditācijas datu izmantošana turpmākajām darbplūsmas izpildēm.

- Vai tiek atbalstīta privāta galapunkta/privāta saite manai pielāgotā modeļa darbplūsmai?
  Customer Insights pašlaik neatbalsta privāto galapunktu pielāgotiem modeļiem, kas nav piemēroti, taču ir pieejams manuāls risinājums. Lūdzu, sazinieties ar atbalsta dienestu, lai iegūtu sīkāku informāciju.

## <a name="responsible-ai"></a>Atbildīgais AI

Prognozes piedāvā iespējas, kas ļauj izveidot labākas iespējas klientiem, uzlabot biznesa iespējas un ieņēmumu plūsmas. Stingri ieteicams sabalansēt prognoze vērtību pret tās ietekmi un aizspriedumiem, ko var ieviest ētiskā veidā. Uzziniet vairāk par to, kā Microsoft [aplūko atbildīgu AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6). Jūs varat uzzināt arī par [attiecīgo algoritmiskās mācīšanās tehniku un procesiem](/azure/machine-learning/concept-responsible-ml), kas ir raksturīgi Azure algoritmiskajai mācīšanās.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWRElk]

[!INCLUDE [footer-include](includes/footer-banner.md)]
