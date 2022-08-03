---
title: Segmentu eksportēšana uz Adobe Experience Platform (priekšskatījums)
description: Uzziniet, kā izmantot Customer Insights segmentus sadaļā Adobe Experience Platform.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: fcb43e0956c6d1f0ef36b222dd2b718906364244
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195299"
---
# <a name="export-segments-to-adobe-experience-platform-preview"></a>Segmentu eksportēšana uz Adobe Experience Platform (priekšskatījums)

Eksportējiet segmentus, kuru mērķauditorija ir atbilstoša Adobe Experience Platform.

:::image type="content" source="media/AEP-flow.png" alt-text="Šajā rakstā aprakstīto darbību procesa shēma.":::

## <a name="prerequisites"></a>Priekšnoteikumi

- Licence Adobe Experience Platform.
- Kampaņas Adobe standarta licence.
- [Azure Blob krātuves konta](/azure/storage/blobs/create-data-lake-storage-account) nosaukums un konta atslēga. Lai atrastu nosaukumu un atslēgu, skatiet rakstu [Krātuves konta iestatījumu pārvaldība Azure portālā](/azure/storage/common/storage-account-manage).
- Azure [Blob krātuves konteiners](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

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

Mēs konfigurēsim eksportēšanu no Customer Insights uz Azure Blob krātuves kontu.

### <a name="set-up-connection-to-azure-blob-storage"></a>Savienojuma ar Azure Blob krātuvi iestatīšana

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Dodieties uz **Administrators** > **Savienojumi**.

1. Atlasiet **Pievienot savienojumu** un izvēlieties **Azure Blob krātuve**.

1. Laukā **Parādāmais nosaukums** piešķiriet savienojumam atpazīstamu nosaukumu. Parādāmais nosaukums un nosaukuma veids raksturo šo savienojumu. Ir ieteicams izvēlēties nosaukumu, kas paskaidro savienojuma nolūku.

1. Izvēlieties, kurš var izmantot šo savienojumu. Pēc noklusējuma tie ir tikai administratori. Papildinformāciju skatiet rakstā [Atļaut līdzstrādniekiem izmantot savienojumu eksportam](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Ievadiet sava Blob krātuves konta **Konta nosaukumu**, **Konta atslēgu** un **Konteineru**, kurā vēlaties eksportēt segmentu.  

   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Krātuves konta konfigurācijas ekrānuzņēmums.":::

1. Pārskatiet datu privātumu [un atbilstību](connections.md#data-privacy-and-compliance) un atlasiet **Es piekrītu**.

1. Lai pabeigtu savienošanu, atlasiet **Saglabāt**.

### <a name="configure-an-export"></a>Eksporta konfigurēšana

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Pārejiet uz **Dati** > **Eksportēšana**.

1. Atlasiet **Pievienot eksportēšanu**.

1. Laukā **Savienošana eksportam** atlasiet savienojumu no sadaļas Azure Blob Storage. Ja nav pieejamu savienojumu, sazinieties ar administratoru.

1. Ievadiet eksportēšanas nosaukumu.

1. Izvēlieties segmentu, uz kuru vēlaties eksportēt. Šajā piemērā tas ir **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Segmenta atlases lietotāja interfeisa ekrānuzņēmums, kurā ir atlasīts ChurnProneCustomers segments.":::

1. Atlasiet **Saglabāt**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

> [!NOTE]
> Pārliecinieties, vai eksportētā segmentā ierakstu skaits atbilst jūsu Adobe Campaign Standard licences atļautajiem ierobežojumiem.

Eksportētie dati tiek glabāti konfigurētajā Azure Blob krātuves konteinerā. Konteinerā automātiski tiek izveidoti šādi mapju ceļi:

- Avota entītijām un sistēmas ģenerētajām entītijām: 

  *%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*

  Piemērs: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv

- Eksportēto entītiju *model.json* atrodas *%ExportDestinationName%* līmenī.

  Piemērs: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a>Pieredzes datu modeļa (Experience Data Model - XDM) definēšana programmā Adobe Experience Platform

Pirms programmā Customer Insights var izmantot eksportētos Adobe Experience Platform datus, definējiet ērtību datu modeļa shēmu un [konfigurējiet reāllaika klienta profila](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials) datus.

Uzziniet, [kas ir XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) un izprotiet [shēmas veidošanas pamatus](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).

## <a name="import-data-into-adobe-experience-platform"></a>Datu importēšana uz Adobe Experience Platform

Importējiet sagatavotos auditorijas datus no Customer Insights uz Adobe Experience Platform.

1. [Izveidojiet Azure Blob krātuves avota savienojumu](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).

1. [Konfigurējiet datu plūsmu](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) mākoņkrātuves pakešu savienojumam, lai importētu segmenta izvadi no Customer Insights Adobe Experience Platform.

## <a name="create-an-audience-in-adobe-campaign-standard"></a>Auditorijas izveide programmā Adobe Campaign Standard

Lai šai kampaņai nosūtītu e-pasta ziņojumu, tiks izmantots Adobe Campaign Standard.

1. [Izveidojiet mērķauditoriju](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) kampaņas standartā Adobe, izmantojot datus sadaļā Adobe Experience Platform.

1. [Izmantojiet segmentu veidotāju](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html) kampaņas standartā Adobe, lai definētu mērķauditoriju, pamatojoties uz datiem.Adobe Experience Platform

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>E-pasta ziņojuma izveide un nosūtīšana, izmantojot Adobe Campaign Standard

Izveidojiet e-pasta saturu un pēc tam [pārbaudiet un nosūtiet](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) e-pasta ziņojumu.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="E-pasta ziņojuma paraugs ar atjaunošanas piedāvājumu no Adobe Campaign Standard.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
