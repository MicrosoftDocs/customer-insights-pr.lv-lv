---
title: Customer Insights datu eksportēšana uz Adobe Campaign Standard
description: Uzziniet, kā kampaņas standartā izmantot segmentus Adobe Customer Insights.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 2a62d2f889f199222eeb8cc969fce62fa89fa6f0
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643454"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a>Customer Insights segmentu izmantošana programmā Adobe Campaign Standard (priekšskatījums)

Iespējams, esat izveidojis segmentus kā lietotājs Dynamics 365 Customer Insights, lai padarītu mārketinga kampaņas efektīvākas, pievēršoties atbilstošajām auditorijām. Lai izmantotu segmentu no Customer Insights programmā Adobe Experience Platform un lietojumprogrammām, piemēram Adobe, Campaign Standard, ir jāveic dažas šajā rakstā aprakstītās darbības.

:::image type="content" source="media/ACS-flow.png" alt-text="Šajā rakstā aprakstīto darbību procesa shēma.":::

## <a name="prerequisites"></a>Priekšnosacījumi

-   Dynamics 365 Customer Insights licence
-   Adobe Campaign Standard licence
-   Azure Blob krātuves konts

## <a name="campaign-overview"></a>Kampaņas pārskats

Lai labāk izprastu, kā programmā Customer Insights varat izmantot segmentus Adobe Experience Platform, apskatīsim fiktīvu kampaņas paraugu.

Pieņemsim, ka jūsu uzņēmums saviem klientiem ASV piedāvā mēneša abonementa servisu. Jūs vēlaties identificēt klientus, kuru abonementi ir jāatjauno nākamajās astoņās dienās, bet kuri vēl nav atjaunojušas savu abonementu. Lai saglabātu šos klientus, jūs vēlaties viņiem nosūtīt reklāmas piedāvājumu pa e-pastu, izmantojot Adobe Campaign Standard.

Šajā piemērā mēs vēlamies vienu reizi palaist reklāmas e-pasta kampaņu. Šajā rakstā nav ietverta kampaņas izmantošana vairākas reizes. Tomēr Customer Insights un Adobe Campaign Standard var konfigurēt darbam arī periodiskam kampaņas scenārijam.

## <a name="identify-your-target-audience"></a>Mērķa auditorijas identificēšana

Mūsu scenārijā mēs pieņemam, ka klientu e-pasta adreses ir pieejamas un viņu reklāmas preferences tika analizētas, lai identificētu segmenta dalībniekus.

Segments, [kuru definējāt customer insights, tiek saukts](segments.md) par **ChurnProneCustomers,** un jūs plānojat nosūtīt šiem klientiem e-pasta paaugstinājumu.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Segmentu lapas ekrānuzņēmumu, kurā ir izveidots ChurnProneCustomers segments.":::

Piedāvājuma e-pasta ziņojumā, kuru vēlaties izsūtīt, būs vārds, uzvārds un klienta abonementa beigu datums. Tas informē klientus par to, kādu atlaidi viņi saņem, ja abonements tiek atjaunots pirms tā derīgums beidzas.

## <a name="export-your-target-audience"></a>Mērķa auditorijas eksportēšana

### <a name="configure-a-connection"></a>Savienojuma konfigurēšana

Identificējot mūsu mērķauditoriju, mēs varam konfigurēt eksportu uz Azure BLOB krātuves kontu.

1. Sadaļā Customer Insights dodieties uz **AdminConnections** > **·**.

1. Atlasiet **Pievienot savienojumu** un atlasiet **Adobe Campaign**, lai konfigurētu savienojumu, vai elementā **Adobe Campaign** atlasiet **Iestatīt**.

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Konfigurācijas elements programmai Adobe Campaign Standard.":::

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

1. Laukam **Savienojums eksportēšanai** izvēlieties savienojumu no Adobe Campaign sadaļas. Ja neredzat šo sadaļas nosaukumu, tad jums nav pieejami šī tipa savienojumi.

1. Izvēlieties segmentu, uz kuru vēlaties eksportēt. Šajā piemērā tas ir **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Segmenta atlases lietotāja interfeisa ekrānuzņēmums, kurā ir atlasīts ChurnProneCustomers segments.":::

1. Atlasiet **Tālāk**.

1. Tagad mēs kartējam **avota** laukus no segmenta Customer Insights uz **kampaņas standarta profila shēmas mērķa** lauku nosaukumiem Adobe.

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Lauka kartējums Adobe Campaign Standard savienotājam.":::

   Ja vēlaties pievienot papildu atribūtus, atlasiet **Pievienot atribūtu**. Mērķa nosaukums var atšķirties no avota lauka nosaukuma, lai segmenta izvadi no Customer Insights uz Campaign Standard joprojām varētu kartēt, Adobe ja laukiem abās sistēmās nav vienāds nosaukums.

   > [!NOTE]
   > E-pasta adrese tiek izmantota kā identitātes lauks, bet varat izmantot jebkuru citu identifikatoru no klienta profila, lai kartētu datus uz Adobe Kampaņas standartu.

1. Atlasiet **Saglabāt**.

Pēc eksportēšanas mērķa saglabāšanas, tas būs pieejams lapā **Dati** > **Eksportēšana**.

Tagad varat [eksportēt segmentu pēc pieprasījuma](export-destinations.md#run-exports-on-demand). Eksportēšana arī tiks palaista ar katru [plānoto atsvaidzināšanu](system.md).

> [!NOTE]
> Pārliecinieties, vai eksportētā segmentā ierakstu skaits atbilst jūsu Adobe Campaign Standard licences atļautajiem ierobežojumiem.

Eksportētie dati tiek glabāti iepriekš konfigurētajā Azure Blob krātuves konteinerā. Konteinerā tiek automātiski izveidots šāds mapes ceļš:

*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*

Piemērs: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv

## <a name="configure-adobe-campaign-standard"></a>Konfigurēt Adobe Campaign Standard

Eksportētajos segmentos ir kolonnas, kuras atlasījāt, definējot eksportēšanas mērķi iepriekšējā solī. Šos datus var izmantot, lai [izveidotu profilus programmā Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).

Lai segmentu izmantotu programmā Adobe Campaign Standard, ir jāpaplašina profila shēma programmā Adobe Campaign Standard, iekļaujot divus papildu laukus. Informācija par to, kā [paplašināt profila resursu](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing), ar jauniem laukiem programmā Adobe Campaign Standard.

Mūsu piemērā šie lauki ir *Segmenta nosaukums un Segmenta datums (nav obligāti)*.

Šos laukus izmantosim, lai identificētu Adobe Campaign Standard profilus, kurus vēlamies atlasīt šīs kampaņas mērķim.

Ja Adobe Campaign Standard nav citu ierakstu, izņemot tos, ko plānojat importēt, šo darbību var izlaist.

## <a name="import-data-into-adobe-campaign-standard"></a>Datu importēšana programmā Adobe Campaign Standard

Tagad, kad viss ir ieviests, mums ir jāimportē sagatavotie auditorijas dati no Customer Insights uz Adobe Campaign Standard, lai izveidotu profilus. Informācija par to, [kā programmā Adobe Campaign Standard importēt profilus](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences), izmantojot darbplūsmu.

Zemāk redzamajā attēlā redzamā importēšanas darbplūsma ir konfigurēta, lai tā darbotos ik pēc astoņām stundām un meklētu eksportētos Customer Insights segmentus (.csv failu Azure Blob krātuvē). Darbplūsma izvelk .csv faila saturu noteiktā kolonnu secībā. Šī darbplūsma ir būvēta, lai veiktu pamata kļūdu apstrādi un nodrošinātu, ka katram ierakstam ir e-pasta adrese pirms datu aizpildīšanas programmā Adobe Campaign Standard. Darbplūsma arī izvelk segmenta nosaukumu no faila nosaukuma, pirms tas tiek ievadīts Adobe Campaign Standard profila datos.

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Importēšanas darbplūsmas Adobe Campaign Standard lietotāja interfeisā ekrānuzņēmums.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a>Auditorijas izgūšana programmā Adobe Campaign Standard

Kad dati ir importēti Adobe Campaign Standard, [varat izveidot darbplūsmu](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) un [vaicāt](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) klientiem, pamatojoties uz *Segmenta nosaukumu* un *Segmenta datumu*, lai atlasītu profilus, kas tika identificēti mūsu kampaņas paraugu vajadzībām.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>E-pasta ziņojuma izveide un nosūtīšana, izmantojot Adobe Campaign Standard

Izveidojiet e-pasta saturu un pēc tam [pārbaudiet un nosūtiet](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) e-pasta ziņojumu.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="E-pasta ziņojuma paraugs ar atjaunošanas piedāvājumu no Adobe Campaign Standard.":::
