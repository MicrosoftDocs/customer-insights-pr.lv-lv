---
title: Customer Insights datu eksportēšana uz Adobe Campaign Standard
description: Uzziniet, kā auditorijas ieskatu segmentus var izmantot Adobe Campaign Standard.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 917ab9559416f3ee0ffd66e471e590e8da3faffc
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305395"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a>Customer Insights segmentu izmantošana Adobe Campaign Standard (priekšskatījums)

Kā Dynamics 365 Customer Insights auditorijas ieskatu lietotājs, iespējams, esat izveidojis segmentus, lai mārketinga kampaņas padarītu efektīvākas, izvēloties atbilstošu mērķauditoriju. Lai izmantotu segmentu no auditorijas ieskatiem platformā Adobe Experience Platform un tādās programmās kā Adobe Campaign Standard, ir jāveic dažas šajā rakstā norādītās darbības.

:::image type="content" source="media/ACS-flow.png" alt-text="Šajā rakstā aprakstīto darbību procesa shēma.":::

## <a name="prerequisites"></a>Priekšnosacījumi

-   Dynamics 365 Customer Insights licence
-   Adobe Campaign Standard licence
-   Azure Blob krātuves konts

## <a name="campaign-overview"></a>Kampaņas pārskats

Lai labāk saprastu, kā var izmantot segmentus no auditorijas ieskatiem Adobe Experience Platform, apskatīsim izdomātu kampaņas paraugu.

Pieņemsim, ka jūsu uzņēmums saviem klientiem ASV piedāvā mēneša abonementa servisu. Jūs vēlaties identificēt klientus, kuru abonementi ir jāatjauno nākamajās astoņās dienās, bet kuri vēl nav atjaunojušas savu abonementu. Lai saglabātu šos klientus, jūs vēlaties viņiem nosūtīt reklāmas piedāvājumu pa e-pastu, izmantojot Adobe Campaign Standard.

Šajā piemērā mēs vēlamies vienu reizi palaist reklāmas e-pasta kampaņu. Šajā rakstā nav ietverta kampaņas izmantošana vairākas reizes. Tomēr auditorijas ieskatus un Adobe Campaign Standard darbību var konfigurēt arī periodiskam kampaņas scenārijam.

## <a name="identify-your-target-audience"></a>Mērķa auditorijas identificēšana

Mūsu scenārijā mēs pieņemsim, ka klientu e-pasta adreses ir pieejamas auditorijas ieskatos, un viņu reklāmas preferences tika analizētas, lai identificētu segmenta dalībniekus.

[Segments, ko definējāt auditorijas ieskatos](segments.md), tiek saukts par **ChurnProneCustomers**, un jūs plānojat šiem klientiem nosūtīt e-pasta reklāmas kampaņu.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Segmentu lapas ekrānuzņēmumu, kurā ir izveidots ChurnProneCustomers segments.":::

Piedāvājuma e-pasta ziņojumā, kuru vēlaties izsūtīt, būs vārds, uzvārds un klienta abonementa beigu datums. Tas informē klientus par to, kādu atlaidi viņi saņem, ja abonements tiek atjaunots pirms tā derīgums beidzas.

## <a name="export-your-target-audience"></a>Mērķa auditorijas eksportēšana

### <a name="configure-a-connection"></a>Savienojuma konfigurēšana

Identificēto mērķauditoriju izmantojot, mēs varam konfigurēt eksportu no auditorijas ieskatiem uz Azure Blob krātuves kontu.

1. Auditorijas ieskatos dodieties uz **Administrators** > **Savienojumi**.

1. Atlasiet **Pievienot savienojumu** un atlasiet **Adobe Campaign**, lai konfigurētu savienojumu, vai elementā **Adobe Campaign** atlasiet **Iestatīt**.

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Konfigurācijā elements programmai Adobe Campaign Standard.":::

1. Laukā **Parādāmais nosaukums** piešķiriet savienojumam atpazīstamu nosaukumu. Parādāmais nosaukums un nosaukuma veids raksturo šo savienojumu. Ir ieteicams izvēlēties nosaukumu, kas paskaidro savienojuma nolūku.

1. Izvēlieties, kurš var izmantot šo savienojumu. Ja nesāksit nekādas darbības, noklusējums būs Administratori. Papildinformāciju skatiet rakstā [Atļaujas, kas nepieciešamas eksporta konfigurēšanai](export-destinations.md#set-up-a-new-export).

1. Ievadiet sava Azure Blob krātuves konta, kurā vēlaties eksportēt segmentu, **Konta nosaukumu**, **Konta atslēgu** un **Konteineru**.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Krātuves konta konfigurācijas ekrānuzņēmums."::: 

   - Papildinformāciju, kā atrast Azure Blob krātuves konta nosaukumu un konta atslēgu, skatiet sadaļā [Krātuves konta iestatījumu pārvaldība Azure portālā](/azure/storage/common/storage-account-manage).

   - Lai uzzinātu, kā izveidot konteineru, skatiet sadaļu [Konteinera izveide](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Lai pabeigtu savienošanu, atlasiet **Saglabāt**.

### <a name="configure-an-export"></a>Eksporta konfigurēšana

Šo eksportu varat konfigurēt, ja jums ir piekļuve šā veida pieslēgumam. Papildinformāciju skatiet rakstā [Atļaujas, kas nepieciešamas eksporta konfigurēšanai](export-destinations.md#set-up-a-new-export).

1. Pārejiet uz **Dati** > **Eksportēšana**.

1. Lai izveidotu jaunu eksportu, atlasiet **Pievienot eksportu**.

1. Laukā **Savienošana eksportam** atlasiet savienojumu no sadaļas Adobe Campaign. Ja neredzat šo sadaļas nosaukumu, tad jums nav pieejami šī tipa savienojumi.

1. Izvēlieties segmentu, uz kuru vēlaties eksportēt. Šajā piemērā tas ir **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Segmenta atlases lietotāja interfeisa ekrānuzņēmums, kurā ir atlasīts ChurnProneCustomers segments.":::

1. Atlasiet **Tālāk**.

1. Tagad mēs kartējam laukus **Avots** no auditorijas ieskatu segmenta uz lauka nosaukumiem **Mērķis** Adobe Campaign Standard profila diagrammā.

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Lauka kartēšana programmas Adobe Campaign Standard savienotājam.":::

   Ja vēlaties pievienot papildu atribūtus, atlasiet **Pievienot atribūtu**. Mērķa nosaukums var atšķirties no avota lauka nosaukuma, lai segmenta izvadi joprojām varētu kartēt no auditorijas ieskatiem uz Adobe Campaign Standard, ja laukiem nav vienāds nosaukums abās sistēmās.

   > [!NOTE]
   > E-pasta adrese tiek izmantota kā identitātes lauks, taču varat izmantot jebkuru citu identifikatoru no sava auditorijas ieskatu klienta profila, lai kartētu datus uz programmu Adobe Campaign Standard.

1. Atlasiet vienumu **Saglabāt**.

Pēc eksportēšanas mērķa saglabāšanas, tas būs pieejams lapā **Dati** > **Eksportēšana**.

Tagad varat [eksportēt segmentu pēc pieprasījuma](export-destinations.md#run-exports-on-demand). Eksportēšana arī tiks palaista ar katru [plānoto atsvaidzināšanu](system.md).

> [!NOTE]
> Nodrošiniet, lai eksportētajā segmentā ierakstu skaits iekļautos jūsu Adobe Campaign Standard licencei atļautajā ierobežojumā.

Eksportētie dati tiek glabāti iepriekš konfigurētajā Azure Blob krātuves konteinerā. Konteinerā tiek automātiski izveidots šāds mapes ceļš:

*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*

Piemērs: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv

## <a name="configure-adobe-campaign-standard"></a>Adobe Campaign Standard konfigurēšana

Ja tiek eksportēts segments no auditorijas ieskatiem, tajā ir ietvertas kolonnas, ko atlasījāt, definējot eksportēšanas mērķi iepriekšējā darbībā. Šos datus var izmantot, lai [veidotu profilus programmā Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).

Lai izmantotu segmentu Adobe Campaign Standard, mums ir jāpaplašina profila diagramma programmā Adobe Campaign Standard, ietverot divus papildu laukus. Informācija par to, kā [paplašināt profila resursu](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) ar jauniem laukiem programmā Adobe Campaign Standard.

Mūsu piemērā šie lauki ir *Segmenta nosaukums un Segmenta datums (nav obligāti)*.

Mēs izmantosim šos laukus, lai identificētu profilus programmā Adobe Campaign Standard, kurus vēlamies sasniegt šīs kampaņas vajadzībām.

Ja Adobe Campaign Standard nav citu ierakstu, izņemot tos, ko plānojat importēt, šo darbību varat izlaist.

## <a name="import-data-into-adobe-campaign-standard"></a>Datu importēšana programmā Adobe Campaign Standard

Tagad, kad viss ir izveidots, mums ir jāimportē sagatavotie auditorijas dati no auditorijas ieskatiem uz programmu Adobe Campaign Standard, lai izveidotu profilus. Informācija par to, kā [importēt profilus programmā Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences), izmantojot darbplūsmu.

Tālāk redzamajā attēlā ir konfigurēta importēšanas darbplūsma, lai tā darbotos ik pēc astoņām stundām un meklētu eksportētās auditorijas ieskatu segmentus (.csv fails Azure Blob krātuvē). Darbplūsma izvelk .csv faila saturu noteiktā kolonnu secībā. Šī darbplūsma ir būvēta, lai veiktu pamata kļūdu apstrādi un nodrošinātu, ka katram ierakstam ir e-pasta adrese, pirms dati tiek iepakoti programmā Adobe Campaign Standard. Darbplūsma arī izvelk segmenta nosaukumu no faila nosaukuma, pirms tas tiek ievadīts Adobe Campaign Standard profila datos.

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Importēšanas darbplūsmas programmas Adobe Campaign Standard lietotāja interfeisā ekrānuzņēmums.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a>Auditorijas izgūšana programmā Adobe Campaign Standard

Kad dati ir importēti programmā Adobe Campaign Standard, varat [izveidot darbplūsmu](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) un [vaicāt](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) klientus, pamatojoties uz *Segmenta nosaukumu* un *Segmenta datumu*, lai atlasītu profilus, kas tika identificēti mūsu piemēra kampaņai.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>E-pasta ziņojuma izveide un nosūtīšana, izmantojot Adobe Campaign Standard

Izveidojiet e-pasta saturu un pēc tam [pārbaudiet un nosūtiet](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) e-pasta ziņojumu.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="E-pasta ziņojuma paraugs ar atjaunošanas piedāvājumu no Adobe Campaign Standard.":::
