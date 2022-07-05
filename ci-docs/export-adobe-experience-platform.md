---
title: Segmentu eksportēšana uz Adobe Experience Platform (priekšskatījums)
description: Uzziniet, kā izmantot Customer Insights segmentus sadaļā Adobe Experience Platform.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: c29b8264019669ffd954a298ce3a633c852477fa
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 06/29/2022
ms.locfileid: "9052520"
---
# <a name="export-segments-to-adobe-experience-platform-preview"></a>Segmentu eksportēšana uz Adobe Experience Platform (priekšskatījums)

Kā lietotājs Dynamics 365 Customer Insights, iespējams, esat izveidojis segmentus, lai padarītu savas mārketinga kampaņas efektīvākas, orientējoties uz atbilstošām mērķauditorijām. Lai izmantotu segmentu no Customer Insights un Adobe Experience Platform lietojumprogrammām, piemēram Adobe, Campaign Standard, jums ir jāveic dažas šajā rakstā aprakstītās darbības.

:::image type="content" source="media/AEP-flow.png" alt-text="Šajā rakstā aprakstīto darbību procesa shēma.":::

## <a name="prerequisites"></a>Priekšnosacījumi

-   Dynamics 365 Customer Insights licence
-   Adobe Experience Platform licence
-   Adobe Campaign Standard licence
-   Azure Blob krātuves konts

## <a name="campaign-overview"></a>Kampaņas pārskats

Lai labāk izprastu, kā varat izmantot segmentus no Customer Insights, Adobe Experience Platform apskatīsim fiktīvu kampaņas paraugu.

Pieņemsim, ka jūsu uzņēmums saviem klientiem ASV piedāvā mēneša abonementa servisu. Jūs vēlaties identificēt klientus, kuru abonementi ir jāatjauno nākamajās astoņās dienās, bet kuri vēl nav atjaunojušas savu abonementu. Lai saglabātu šos klientus, jūs vēlaties viņiem nosūtīt reklāmas piedāvājumu pa e-pastu, izmantojot Adobe Experience Platform.

Šajā piemērā mēs vēlamies vienu reizi palaist reklāmas e-pasta kampaņu. Šajā rakstā nav ietverta kampaņas izmantošana vairākas reizes.

## <a name="identify-your-target-audience"></a>Mērķa auditorijas identificēšana

Mūsu scenārijā mēs pieņemam, ka klientu e-pasta adreses ir pieejamas programmā Customer Insights un viņu reklāmas preferences tika analizētas, lai identificētu segmenta dalībniekus.

Segments [, kuru definējāt programmā Customer Insights, tiek saukts](segments.md) par **ChurnProneCustomers**, un jūs plānojat nosūtīt šiem klientiem e-pasta akciju.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Segmentu lapas ekrānuzņēmumu, kurā ir izveidots ChurnProneCustomers segments.":::

Piedāvājuma e-pasta ziņojumā, kuru vēlaties izsūtīt, būs vārds, uzvārds un klienta abonementa beigu datums. Tas informē klientus par to, kādu atlaidi viņi saņem, ja abonements tiek atjaunots pirms tā derīgums beidzas.

## <a name="export-your-target-audience"></a>Mērķa auditorijas eksportēšana

Kad mūsu mērķauditorija ir identificēta, mēs varam konfigurēt eksportēšanu no Customer Insights uz Azure Blob krātuves kontu.

### <a name="configure-a-connection"></a>Savienojuma konfigurēšana

1. Dodieties uz **Administrators** > **Savienojumi**.

1. Atlasiet **Pievienot savienojumu** un izvēlieties **Azure Blob Storage** vai atlasiet **Iestatīt** elementā **Azure Blob Storage**, lai configurētu savienojumu.

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Konfigurācijas elementu Azure Blob krātuvei."::: 

1. Laukā **Parādāmais nosaukums** piešķiriet savienojumam atpazīstamu nosaukumu. Parādāmais nosaukums un nosaukuma veids raksturo šo savienojumu. Ir ieteicams izvēlēties nosaukumu, kas paskaidro savienojuma nolūku.

1. Izvēlieties, kurš var izmantot šo savienojumu. Ja nesāksit nekādas darbības, noklusējums būs Administratori. Papildinformāciju skatiet rakstā [Atļaut līdzstrādniekiem izmantot savienojumu eksportam](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Ievadiet sava Blob krātuves konta **Konta nosaukumu**, **Konta atslēgu** un **Konteineru**, kurā vēlaties eksportēt segmentu.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Krātuves konta konfigurācijas ekrānuzņēmums."::: 
   
    - Papildinformāciju par Blob krātuves konta nosaukuma un konta atslēgas meklēšanu skatiet sadaļā [Krātuves konta iestatījumu pārvaldība Azure portālā](/azure/storage/common/storage-account-manage).
    - Lai uzzinātu, kā izveidot konteineru, skatiet sadaļu [Konteinera izveide](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Lai pabeigtu savienošanu, atlasiet **Saglabāt**. 

### <a name="configure-an-export"></a>Eksporta konfigurēšana

Šo eksportu varat konfigurēt, ja jums ir piekļuve šā veida pieslēgumam. Papildinformāciju skatiet rakstā [Atļaujas, kas nepieciešamas eksporta konfigurēšanai](export-destinations.md#set-up-a-new-export).

1. Pārejiet uz **Dati** > **Eksportēšana**.

1. Lai izveidotu jaunu eksportu, atlasiet **Pievienot eksportu**.

1. Laukā **Savienošana eksportam** atlasiet savienojumu no sadaļas Azure Blob Storage. Ja neredzat šo sadaļas nosaukumu, tad jums nav pieejami šī tipa savienojumi.

1. Izvēlieties segmentu, uz kuru vēlaties eksportēt. Šajā piemērā tas ir **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Segmenta atlases lietotāja interfeisa ekrānuzņēmums, kurā ir atlasīts ChurnProneCustomers segments.":::

1. Atlasiet vienumu **Saglabāt**.

Pēc eksportēšanas mērķa saglabāšanas, tas būs pieejams lapā **Dati** > **Eksportēšana**.

Tagad varat [eksportēt segmentu pēc pieprasījuma](export-destinations.md#run-exports-on-demand). Eksportēšana arī tiks palaista ar katru [plānoto atsvaidzināšanu](system.md).

> [!NOTE]
> Pārliecinieties, vai eksportētā segmentā ierakstu skaits atbilst jūsu Adobe Campaign Standard licences atļautajiem ierobežojumiem.

Eksportētie dati tiek glabāti iepriekš konfigurētajā Azure Blob krātuves konteinerā. Konteinerā tiek automātiski izveidots šāds mapes ceļš:

*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*

Piemērs: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv

Eksportēto entītiju *model.json* atrodas *%ExportDestinationName%* līmenī.

Piemērs: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a>Pieredzes datu modeļa (Experience Data Model - XDM) definēšana programmā Adobe Experience Platform

Lai programmā Customer Insights eksportētos datus varētu izmantot Adobe Experience Platform, mums ir jādefinē ērtību datu modeļa shēma un [jākonfigurē reāllaika klienta profila](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials) dati.

Uzziniet, [kas ir XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) un izprotiet [shēmas veidošanas pamatus](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).

## <a name="import-data-into-adobe-experience-platform"></a>Datu importēšana uz Adobe Experience Platform

Tagad, kad viss ir sakārtots, mums ir jāimportē sagatavotie mērķauditorijas dati no Customer Insights Adobe Experience Platform uz.

Vispirms [izveidojiet Azure Blob krātuves avota savienojumu](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).    

Pēc avota savienojuma definēšanas konfigurējiet datu plūsmu mākoņkrātuves pakešs savienojumam, [lai importētu segmenta izvadi no Customer Insights](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials).Adobe Experience Platform

## <a name="create-an-audience-in-adobe-campaign-standard"></a>Auditorijas izveide programmā Adobe Campaign Standard

Lai šai kampaņai nosūtītu e-pasta ziņojumu, tiks izmantots Adobe Campaign Standard. Pēc datu importēšanas programmā Adobe Experience Platform, mums ir [jāizveido auditorija](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) programmā Adobe Campaign Standard, izmantojot datus programmā Adobe Experience Platform.


Informācija par to, kā Adobe Campaign Standard [lietot segmenta veidotāju](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html), lai definētu auditoriju, pamatojoties uz datiem programmā Adobe Experience Platform.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>E-pasta ziņojuma izveide un nosūtīšana, izmantojot Adobe Campaign Standard

Izveidojiet e-pasta saturu un pēc tam [pārbaudiet un nosūtiet](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) e-pasta ziņojumu.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="E-pasta ziņojuma paraugs ar atjaunošanas piedāvājumu no Adobe Campaign Standard.":::
