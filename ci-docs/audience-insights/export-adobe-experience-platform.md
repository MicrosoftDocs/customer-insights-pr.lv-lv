---
title: Customer Insights datu eksportēšana uz Adobe Experience Platform
description: Uzziniet, kā izmantot auditorijas ieskatu segmentus Adobe pieredzes platformā.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 1045d0e373fd5ea8987684e51bd9a07b7b535ee3
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305533"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a><span data-ttu-id="e0957-103">Customer Insights segmentu izmantošana Adobe Experience Platform (priekšskatījums)</span><span class="sxs-lookup"><span data-stu-id="e0957-103">Use Customer Insights segments in Adobe Experience Platform (preview)</span></span>

<span data-ttu-id="e0957-104">Kā Dynamics 365 Customer Insights auditorijas ieskatu lietotājs, iespējams, esat izveidojis segmentus, lai mārketinga kampaņas padarītu efektīvākas, izvēloties atbilstošu mērķauditoriju.</span><span class="sxs-lookup"><span data-stu-id="e0957-104">As a user of audience insights in Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="e0957-105">Lai izmantotu segmentu no auditorijas ieskatiem platformā Adobe Experience Platform un tādās programmās kā Adobe Campaign Standard, ir jāveic dažas šajā rakstā norādītās darbības.</span><span class="sxs-lookup"><span data-stu-id="e0957-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/AEP-flow.png" alt-text="Šajā rakstā aprakstīto darbību procesa shēma.":::

## <a name="prerequisites"></a><span data-ttu-id="e0957-107">Priekšnosacījumi</span><span class="sxs-lookup"><span data-stu-id="e0957-107">Prerequisites</span></span>

-   <span data-ttu-id="e0957-108">Dynamics 365 Customer Insights licence</span><span class="sxs-lookup"><span data-stu-id="e0957-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="e0957-109">Adobe Experience Platform licence</span><span class="sxs-lookup"><span data-stu-id="e0957-109">Adobe Experience Platform license</span></span>
-   <span data-ttu-id="e0957-110">Adobe Campaign Standard licence</span><span class="sxs-lookup"><span data-stu-id="e0957-110">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="e0957-111">Azure Blob krātuves konts</span><span class="sxs-lookup"><span data-stu-id="e0957-111">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="e0957-112">Kampaņas pārskats</span><span class="sxs-lookup"><span data-stu-id="e0957-112">Campaign Overview</span></span>

<span data-ttu-id="e0957-113">Lai labāk saprastu, kā var izmantot segmentus no auditorijas ieskatiem Adobe Experience Platform, apskatīsim izdomātu kampaņas paraugu.</span><span class="sxs-lookup"><span data-stu-id="e0957-113">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="e0957-114">Pieņemsim, ka jūsu uzņēmums saviem klientiem ASV piedāvā mēneša abonementa servisu.</span><span class="sxs-lookup"><span data-stu-id="e0957-114">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="e0957-115">Jūs vēlaties identificēt klientus, kuru abonementi ir jāatjauno nākamajās astoņās dienās, bet kuri vēl nav atjaunojušas savu abonementu.</span><span class="sxs-lookup"><span data-stu-id="e0957-115">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="e0957-116">Lai saglabātu šos klientus, jūs vēlaties viņiem nosūtīt reklāmas piedāvājumu pa e-pastu, izmantojot Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="e0957-116">To keep these customers, you want to send them a promotional offer via email, using Adobe Experience Platform.</span></span>

<span data-ttu-id="e0957-117">Šajā piemērā mēs vēlamies vienu reizi palaist reklāmas e-pasta kampaņu.</span><span class="sxs-lookup"><span data-stu-id="e0957-117">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="e0957-118">Šajā rakstā nav ietverta kampaņas izmantošana vairākas reizes.</span><span class="sxs-lookup"><span data-stu-id="e0957-118">This article doesn’t cover the use-case of running the campaign more than once.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="e0957-119">Mērķa auditorijas identificēšana</span><span class="sxs-lookup"><span data-stu-id="e0957-119">Identify your target audience</span></span>

<span data-ttu-id="e0957-120">Mūsu scenārijā mēs pieņemsim, ka klientu e-pasta adreses ir pieejamas auditorijas ieskatos, un viņu reklāmas preferences tika analizētas, lai identificētu segmenta dalībniekus.</span><span class="sxs-lookup"><span data-stu-id="e0957-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="e0957-121">[Segments, ko definējāt auditorijas ieskatos](segments.md), tiek saukts par **ChurnProneCustomers**, un jūs plānojat šiem klientiem nosūtīt e-pasta reklāmas kampaņu.</span><span class="sxs-lookup"><span data-stu-id="e0957-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Segmentu lapas ekrānuzņēmumu, kurā ir izveidots ChurnProneCustomers segments.":::

<span data-ttu-id="e0957-123">Piedāvājuma e-pasta ziņojumā, kuru vēlaties izsūtīt, būs vārds, uzvārds un klienta abonementa beigu datums.</span><span class="sxs-lookup"><span data-stu-id="e0957-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="e0957-124">Tas informē klientus par to, kādu atlaidi viņi saņem, ja abonements tiek atjaunots pirms tā derīgums beidzas.</span><span class="sxs-lookup"><span data-stu-id="e0957-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="e0957-125">Mērķa auditorijas eksportēšana</span><span class="sxs-lookup"><span data-stu-id="e0957-125">Export your target audience</span></span>

<span data-ttu-id="e0957-126">Identificēto mērķauditoriju izmantojot, mēs varam konfigurēt eksportu no auditorijas ieskatiem uz Azure Blob krātuves kontu.</span><span class="sxs-lookup"><span data-stu-id="e0957-126">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="e0957-127">Savienojuma konfigurēšana</span><span class="sxs-lookup"><span data-stu-id="e0957-127">Configure a connection</span></span>

1. <span data-ttu-id="e0957-128">Dodieties uz **Administrators** > **Savienojumi**.</span><span class="sxs-lookup"><span data-stu-id="e0957-128">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="e0957-129">Atlasiet **Pievienot savienojumu** un izvēlieties **Azure Blob Storage** vai atlasiet **Iestatīt** elementā **Azure Blob Storage**, lai configurētu savienojumu.</span><span class="sxs-lookup"><span data-stu-id="e0957-129">Select **Add connection** and choose **Azure Blob Storage** or select **Set up** in the **Azure Blob Storage** tile to configure the connection.</span></span>

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Konfigurācijas elementu Azure Blob krātuvei."::: 

1. <span data-ttu-id="e0957-131">Laukā **Parādāmais nosaukums** piešķiriet savienojumam atpazīstamu nosaukumu.</span><span class="sxs-lookup"><span data-stu-id="e0957-131">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="e0957-132">Parādāmais nosaukums un nosaukuma veids raksturo šo savienojumu.</span><span class="sxs-lookup"><span data-stu-id="e0957-132">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="e0957-133">Ir ieteicams izvēlēties nosaukumu, kas paskaidro savienojuma nolūku.</span><span class="sxs-lookup"><span data-stu-id="e0957-133">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="e0957-134">Izvēlieties, kurš var izmantot šo savienojumu.</span><span class="sxs-lookup"><span data-stu-id="e0957-134">Choose who can use this connection.</span></span> <span data-ttu-id="e0957-135">Ja nesāksit nekādas darbības, noklusējums būs Administratori.</span><span class="sxs-lookup"><span data-stu-id="e0957-135">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="e0957-136">Papildinformāciju skatiet rakstā [Atļaut līdzstrādniekiem izmantot savienojumu eksportam](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="e0957-136">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="e0957-137">Ievadiet sava Blob krātuves konta **Konta nosaukumu**, **Konta atslēgu** un **Konteineru**, kurā vēlaties eksportēt segmentu.</span><span class="sxs-lookup"><span data-stu-id="e0957-137">Enter **Account name**, **Account key**, and **Container** for your Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Krātuves konta konfigurācijas ekrānuzņēmums."::: 
   
    - <span data-ttu-id="e0957-139">Papildinformāciju par Blob krātuves konta nosaukuma un konta atslēgas meklēšanu skatiet sadaļā [Krātuves konta iestatījumu pārvaldība Azure portālā](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="e0957-139">To learn more about how to find the Blob Storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>
    - <span data-ttu-id="e0957-140">Lai uzzinātu, kā izveidot konteineru, skatiet sadaļu [Konteinera izveide](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="e0957-140">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="e0957-141">Lai pabeigtu savienošanu, atlasiet **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="e0957-141">Select **Save** to complete the connection.</span></span> 

### <a name="configure-an-export"></a><span data-ttu-id="e0957-142">Eksporta konfigurēšana</span><span class="sxs-lookup"><span data-stu-id="e0957-142">Configure an export</span></span>

<span data-ttu-id="e0957-143">Šo eksportu varat konfigurēt, ja jums ir piekļuve šā veida pieslēgumam.</span><span class="sxs-lookup"><span data-stu-id="e0957-143">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="e0957-144">Papildinformāciju skatiet rakstā [Atļaujas, kas nepieciešamas eksporta konfigurēšanai](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="e0957-144">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="e0957-145">Pārejiet uz **Dati** > **Eksportēšana**.</span><span class="sxs-lookup"><span data-stu-id="e0957-145">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="e0957-146">Lai izveidotu jaunu eksportu, atlasiet **Pievienot eksportu**.</span><span class="sxs-lookup"><span data-stu-id="e0957-146">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="e0957-147">Laukā **Savienošana eksportam** atlasiet savienojumu no sadaļas Azure Blob Storage.</span><span class="sxs-lookup"><span data-stu-id="e0957-147">In the **Connection for export** field, choose a connection from the Azure Blob Storage section.</span></span> <span data-ttu-id="e0957-148">Ja neredzat šo sadaļas nosaukumu, tad jums nav pieejami šī tipa savienojumi.</span><span class="sxs-lookup"><span data-stu-id="e0957-148">If you don't see this section name, then no connections of this type are available to you.</span></span>

1. <span data-ttu-id="e0957-149">Izvēlieties segmentu, uz kuru vēlaties eksportēt.</span><span class="sxs-lookup"><span data-stu-id="e0957-149">Choose the segment that you want to export.</span></span> <span data-ttu-id="e0957-150">Šajā piemērā tas ir **ChurnProneCustomers**.</span><span class="sxs-lookup"><span data-stu-id="e0957-150">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Segmenta atlases lietotāja interfeisa ekrānuzņēmums, kurā ir atlasīts ChurnProneCustomers segments.":::

1. <span data-ttu-id="e0957-152">Atlasiet vienumu **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="e0957-152">Select **Save**.</span></span>

<span data-ttu-id="e0957-153">Pēc eksportēšanas mērķa saglabāšanas, tas būs pieejams lapā **Dati** > **Eksportēšana**.</span><span class="sxs-lookup"><span data-stu-id="e0957-153">After saving the export destination, you find it on **Data** > **Exports**.</span></span>

<span data-ttu-id="e0957-154">Tagad varat [eksportēt segmentu pēc pieprasījuma](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="e0957-154">You can now [export the segment on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="e0957-155">Eksportēšana arī tiks palaista ar katru [plānoto atsvaidzināšanu](system.md).</span><span class="sxs-lookup"><span data-stu-id="e0957-155">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="e0957-156">Nodrošiniet, lai eksportētajā segmentā ierakstu skaits iekļautos jūsu Adobe Campaign Standard licencei atļautajā ierobežojumā.</span><span class="sxs-lookup"><span data-stu-id="e0957-156">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="e0957-157">Eksportētie dati tiek glabāti iepriekš konfigurētajā Azure Blob krātuves konteinerā.</span><span class="sxs-lookup"><span data-stu-id="e0957-157">Exported data is stored in the Azure Blob Storage container you configured above.</span></span> <span data-ttu-id="e0957-158">Konteinerā tiek automātiski izveidots šāds mapes ceļš:</span><span class="sxs-lookup"><span data-stu-id="e0957-158">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="e0957-159">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span><span class="sxs-lookup"><span data-stu-id="e0957-159">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span></span>

<span data-ttu-id="e0957-160">Piemērs: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span><span class="sxs-lookup"><span data-stu-id="e0957-160">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span></span>

<span data-ttu-id="e0957-161">Eksportēto entītiju *model.json* atrodas *%ExportDestinationName%* līmenī.</span><span class="sxs-lookup"><span data-stu-id="e0957-161">The *model.json* for the exported entities resides at the *%ExportDestinationName%* level.</span></span>

<span data-ttu-id="e0957-162">Piemērs: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span><span class="sxs-lookup"><span data-stu-id="e0957-162">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span></span>

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a><span data-ttu-id="e0957-163">Define Experience Data Model (XDM) definēšana programmā Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="e0957-163">Define Experience Data Model (XDM) in Adobe Experience Platform</span></span>

<span data-ttu-id="e0957-164">Lai no auditorijas ieskatiem eksportētos datus varētu izmantot Adobe Experience Platform, ir jādefinē Experience Data Model shēma un [jākonfigurē reāllaika klienta profila dati](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span><span class="sxs-lookup"><span data-stu-id="e0957-164">Before the exported data from audience insights can be used within Adobe Experience Platform, we need to define the Experience Data Model schema and [configure the data for the Real-time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span></span>

<span data-ttu-id="e0957-165">Uzziniet, [kas ir XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) un izprotiet [shēmas veidošanas pamatus](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span><span class="sxs-lookup"><span data-stu-id="e0957-165">Learn [what XDM is](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) and understand the [basics of schema composition](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span></span>

## <a name="import-data-into-adobe-experience-platform"></a><span data-ttu-id="e0957-166">Datu importēšana Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="e0957-166">Import data into Adobe Experience Platform</span></span>

<span data-ttu-id="e0957-167">Tagad, kad viss ir izveidots, mums ir jāimportē sagatavotie auditorijas dati no auditorijas ieskatiem uz programmu Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="e0957-167">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Experience Platform.</span></span>

<span data-ttu-id="e0957-168">Vispirms [izveidojiet Azure Blob krātuves avota savienojumu](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span><span class="sxs-lookup"><span data-stu-id="e0957-168">First, [create an Azure Blob Storage source connection](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span></span>    

<span data-ttu-id="e0957-169">Pēc avota savienojuma definēšanas [konfigurējiet datu plūsmu](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) mākoņkrātuves pakešu savienojumam, lai importētu segmenta izvadi no auditorijas ieskatiem Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="e0957-169">After defining the source connection, [configure a dataflow](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) for a cloud storage batch connection to import the segment output from audience insights into Adobe Experience Platform.</span></span>

## <a name="create-an-audience-in-adobe-campaign-standard"></a><span data-ttu-id="e0957-170">Auditorijas izveide programmā Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="e0957-170">Create an audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="e0957-171">Lai šai kampaņai nosūtītu e-pasta ziņojumu, tiks izmantots Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="e0957-171">To send the email for this campaign, we'll use Adobe Campaign Standard.</span></span> <span data-ttu-id="e0957-172">Pēc datu importēšanas Adobe Experience Platform ir [jāizveido auditorija](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) programmā Adobe Campaign Standard, izmantojot datus Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="e0957-172">After importing the data into Adobe Experience Platform, we need to [create an audience](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) in Adobe Campaign Standard using the data in Adobe Experience Platform.</span></span>


<span data-ttu-id="e0957-173">Uzziniet, kā [lietot segmentu veidotāju](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html) programmā Adobe Campaign Standard, lai defindētu auditoriju, pamatojoties uz Adobe Experience Platform esošajiem datiem.</span><span class="sxs-lookup"><span data-stu-id="e0957-173">Learn how to [use segment builder](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html) in Adobe Campaign Standard to define an audience based on the data in Adobe Experience Platform.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="e0957-174">E-pasta ziņojuma izveide un nosūtīšana, izmantojot Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="e0957-174">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="e0957-175">Izveidojiet e-pasta saturu un pēc tam [pārbaudiet un nosūtiet](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) e-pasta ziņojumu.</span><span class="sxs-lookup"><span data-stu-id="e0957-175">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="E-pasta ziņojuma paraugs ar atjaunošanas piedāvājumu no Adobe Campaign Standard.":::
