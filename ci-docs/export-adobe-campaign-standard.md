---
title: Customer Insights segmentu eksportēšana uz Adobe campaign standard (priekšskatījums)
description: Uzziniet, kā izmantot Customer Insights segmentus kampaņas standartā Adobe.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 834880cac9c5023157983081ff2513d9b051491f
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195529"
---
# <a name="export-customer-insights-segments-to-adobe-campaign-standard-preview"></a>Customer Insights segmentu eksportēšana uz Adobe campaign standard (priekšskatījums)

Eksportējiet segmentus, kuru mērķauditorija ir atbilstošas mērķauditorijas, uz Adobe kampaņas standartu.

:::image type="content" source="media/ACS-flow.png" alt-text="Šajā rakstā aprakstīto darbību procesa shēma.":::

## <a name="prerequisites"></a>Priekšnoteikumi

- Kampaņas Adobe standarta licence.
- [Azure Blob krātuves konta](/azure/storage/blobs/create-data-lake-storage-account) nosaukums un konta atslēga. Lai atrastu nosaukumu un atslēgu, skatiet rakstu [Krātuves konta iestatījumu pārvaldība Azure portālā](/azure/storage/common/storage-account-manage).
- Azure [Blob krātuves konteiners](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

## <a name="campaign-overview"></a>Kampaņas pārskats

Lai labāk izprastu, kā varat izmantot segmentus no Customer Insights, Adobe Experience Platform apskatīsim fiktīvu kampaņas paraugu.

Pieņemsim, ka jūsu uzņēmums saviem klientiem ASV piedāvā mēneša abonementa servisu. Jūs vēlaties identificēt klientus, kuru abonementi ir jāatjauno nākamajās astoņās dienās, bet kuri vēl nav atjaunojušas savu abonementu. Lai saglabātu šos klientus, jūs vēlaties viņiem nosūtīt reklāmas piedāvājumu pa e-pastu, izmantojot Adobe Campaign Standard.

Šajā piemērā mēs vēlamies vienu reizi palaist reklāmas e-pasta kampaņu. Šajā rakstā nav ietverta kampaņas izmantošana vairākas reizes. Tomēr Customer Insights un Adobe Campaign Standard var konfigurēt tā, lai tie darbotos arī periodiskas kampaņas scenārijā.

## <a name="identify-your-target-audience"></a>Mērķa auditorijas identificēšana

Mūsu scenārijā mēs pieņemam, ka klientu e-pasta adreses ir pieejamas programmā Customer Insights un viņu reklāmas preferences tika analizētas, lai identificētu segmenta dalībniekus.

Segments [, kuru definējāt programmā Customer Insights, tiek saukts](segments.md) par **ChurnProneCustomers**, un jūs plānojat nosūtīt šiem klientiem e-pasta akciju.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Segmentu lapas ekrānuzņēmumu, kurā ir izveidots ChurnProneCustomers segments.":::

Piedāvājuma e-pasta ziņojumā, kuru vēlaties izsūtīt, būs vārds, uzvārds un klienta abonementa beigu datums. Tas informē klientus par to, kādu atlaidi viņi saņem, ja abonements tiek atjaunots pirms tā derīgums beidzas.

## <a name="export-your-target-audience"></a>Mērķa auditorijas eksportēšana

### <a name="set-up-connection-to-adobe-campaign"></a>Savienojuma ar kampaņu Adobe iestatīšana

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Dodieties uz **Administrators** > **Savienojumi**.

1. Atlasiet **Pievienot savienojumu** un izvēlieties **Adobe Kampaņa**.

1. Laukā **Parādāmais nosaukums** piešķiriet savienojumam atpazīstamu nosaukumu. Parādāmais nosaukums un nosaukuma veids raksturo šo savienojumu. Ir ieteicams izvēlēties nosaukumu, kas paskaidro savienojuma nolūku.

1. Izvēlieties, kurš var izmantot šo savienojumu. Pēc noklusējuma tie ir tikai administratori. Papildinformāciju skatiet rakstā [Atļaut līdzstrādniekiem izmantot savienojumu eksportam](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. **Ievadiet sava Blob krātuves konta nosaukumu** **, konta atslēgu** un **konteineru**.  

   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Krātuves konta konfigurācijas ekrānuzņēmums.":::

1. Pārskatiet datu privātumu [un atbilstību](connections.md#data-privacy-and-compliance) un atlasiet **Es piekrītu**.

1. Lai pabeigtu savienošanu, atlasiet **Saglabāt**.

### <a name="configure-an-export"></a>Eksporta konfigurēšana

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Pārejiet uz **Dati** > **Eksportēšana**.

1. Atlasiet **Pievienot eksportēšanu**.

1. Laukam **Savienojums eksportēšanai** izvēlieties savienojumu no Adobe Campaign sadaļas. Ja nav pieejamu savienojumu, sazinieties ar administratoru.

1. Ievadiet eksportēšanas nosaukumu.

1. Izvēlieties segmentu, uz kuru vēlaties eksportēt. Šajā piemērā tas ir **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Segmenta atlases lietotāja interfeisa ekrānuzņēmums, kurā ir atlasīts ChurnProneCustomers segments.":::

1. Atlasiet **Tālāk**.

1. Kartējiet **avota** laukus no segmenta Customer Insights uz **mērķa** lauku nosaukumiem kampaņas Adobe standarta profila shēmā.

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Lauka kartējums Adobe Campaign Standard savienotājam.":::

   Ja vēlaties pievienot papildu atribūtus, atlasiet **Pievienot atribūtu**. Mērķa nosaukums var atšķirties no avota lauka nosaukuma, lai joprojām varētu kartēt segmenta izvadi no Customer Insights uz Adobe Campaign Standard, ja laukiem abās sistēmās nav tāda paša nosaukuma.

   > [!NOTE]
   > E-pasta adrese tiek izmantota kā identitātes lauks, taču varat izmantot jebkuru citu klienta profila identifikatoru, lai kartētu datus uz Adobe Campaign Standard.

1. Atlasiet **Saglabāt**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

> [!NOTE]
> Pārliecinieties, vai eksportētā segmentā ierakstu skaits atbilst jūsu Adobe Campaign Standard licences atļautajiem ierobežojumiem.

Eksportētie dati tiek glabāti iepriekš konfigurētajā Azure Blob krātuves konteinerā. Konteinerā automātiski tiek izveidots šāds mapes ceļš: *%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*

Piemērs: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv

## <a name="configure-adobe-campaign-standard"></a>Konfigurēt Adobe Campaign Standard

Eksportētie segmenti satur kolonnas, kuras atlasījāt, konfigurējot eksportēšanu. Šos datus var izmantot, lai [izveidotu profilus programmā Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).

Lai izmantotu segmentu kampaņas standartā Adobe, [izvērsiet kampaņas](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) standarta profila shēmu Adobe, iekļaujot tajā divus papildu laukus.

Mūsu piemērā šie lauki ir segmenta nosaukums un segmenta datums. Šos laukus izmantosim, lai identificētu Adobe Campaign Standard profilus, kurus vēlamies atlasīt šīs kampaņas mērķim.

Ja kampaņas standartā Adobe nav citu ierakstu, izņemot to, ko gatavojaties importēt, izlaidiet šo darbību.

## <a name="import-data-into-adobe-campaign-standard"></a>Datu importēšana programmā Adobe Campaign Standard

Importējiet sagatavotos mērķauditorijas datus no Customer Insights kampaņas standartā Adobe, lai [izveidotu profilus, izmantojot darbplūsmu](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences).

Importēšanas darbplūsma tālāk redzamajā attēlā ir konfigurēta tā, lai tā darbotos ik pēc astoņām stundām un meklētu eksportētos Customer Insights segmentus (.csv failu Azure Blob krātuvē). Darbplūsma izvelk .csv faila saturu noteiktā kolonnu secībā. Šī darbplūsma ir būvēta, lai veiktu pamata kļūdu apstrādi un nodrošinātu, ka katram ierakstam ir e-pasta adrese pirms datu aizpildīšanas programmā Adobe Campaign Standard. Darbplūsma arī izvelk segmenta nosaukumu no faila nosaukuma, pirms tas tiek ievadīts Adobe Campaign Standard profila datos.

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Importēšanas darbplūsmas Adobe Campaign Standard lietotāja interfeisā ekrānuzņēmums.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a>Auditorijas izgūšana programmā Adobe Campaign Standard

Kad dati ir importēti kampaņas standartā Adobe, izveidojiet darbplūsmu [un](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) veiciet vaicājumus [klientiem,](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) pamatojoties uz segmenta nosaukumu un segmenta datumu, lai atlasītu profilus, kas tika identificēti mūsu kampaņas izlasei.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>E-pasta ziņojuma izveide un nosūtīšana, izmantojot Adobe Campaign Standard

Izveidojiet e-pasta saturu un pēc tam [pārbaudiet un nosūtiet](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) e-pasta ziņojumu.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="E-pasta ziņojuma paraugs ar atjaunošanas piedāvājumu no Adobe Campaign Standard.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
