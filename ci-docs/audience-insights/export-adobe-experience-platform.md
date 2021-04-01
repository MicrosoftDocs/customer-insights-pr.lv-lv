---
title: Customer Insights datu eksportēšana uz Adobe Experience Platform
description: Uzziniet, kā auditorijas ieskatu segmentus var izmantot Adobe Experience Platform.
ms.date: 02/26/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: d1856861562be55c6d1d051050fe965560fa42f8
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596278"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a><span data-ttu-id="95942-103">Customer Insights segmentu izmantošana Adobe Experience Platform (priekšskatījums)</span><span class="sxs-lookup"><span data-stu-id="95942-103">Use Customer Insights segments in Adobe Experience Platform (preview)</span></span>

<span data-ttu-id="95942-104">Kā auditorijas ieskatu lietotājs programmai Dynamics 365 Customer Insights, iespējams, esat izveidojis segmentus, lai mārketinga kampaņas padarītu efektīvākas, vēršoties pie atbilstošas mērķauditorijas.</span><span class="sxs-lookup"><span data-stu-id="95942-104">As a user of audience insights for Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="95942-105">Lai izmantotu segmentu no auditorijas ieskatiem platformā Adobe Experience Platform un tādās programmās kā Adobe Campaign Standard, ir jāveic dažas šajā rakstā norādītās darbības.</span><span class="sxs-lookup"><span data-stu-id="95942-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/AEP-flow.png" alt-text="Šajā rakstā aprakstīto darbību procesa shēma.":::

## <a name="prerequisites"></a><span data-ttu-id="95942-107">Priekšnosacījumi</span><span class="sxs-lookup"><span data-stu-id="95942-107">Prerequisites</span></span>

-   <span data-ttu-id="95942-108">Dynamics 365 Customer Insights licence</span><span class="sxs-lookup"><span data-stu-id="95942-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="95942-109">Adobe Experience Platform licence</span><span class="sxs-lookup"><span data-stu-id="95942-109">Adobe Experience Platform license</span></span>
-   <span data-ttu-id="95942-110">Adobe Campaign Standard licence</span><span class="sxs-lookup"><span data-stu-id="95942-110">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="95942-111">Azure Blob krātuves konts</span><span class="sxs-lookup"><span data-stu-id="95942-111">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="95942-112">Kampaņas pārskats</span><span class="sxs-lookup"><span data-stu-id="95942-112">Campaign Overview</span></span>

<span data-ttu-id="95942-113">Lai labāk saprastu, kā var izmantot segmentus no auditorijas ieskatiem Adobe Experience Platform, apskatīsim izdomātu kampaņas paraugu.</span><span class="sxs-lookup"><span data-stu-id="95942-113">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="95942-114">Pieņemsim, ka jūsu uzņēmums saviem klientiem ASV piedāvā mēneša abonementa servisu.</span><span class="sxs-lookup"><span data-stu-id="95942-114">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="95942-115">Jūs vēlaties identificēt klientus, kuru abonementi ir jāatjauno nākamajās astoņās dienās, bet kuri vēl nav atjaunojušas savu abonementu.</span><span class="sxs-lookup"><span data-stu-id="95942-115">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="95942-116">Lai saglabātu šos klientus, jūs vēlaties viņiem nosūtīt reklāmas piedāvājumu pa e-pastu, izmantojot Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="95942-116">To keep these customers, you want to send them a promotional offer via email, using Adobe Experience Platform.</span></span>

<span data-ttu-id="95942-117">Šajā piemērā mēs vēlamies vienu reizi palaist reklāmas e-pasta kampaņu.</span><span class="sxs-lookup"><span data-stu-id="95942-117">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="95942-118">Šajā rakstā nav ietverta kampaņas izmantošana vairākas reizes.</span><span class="sxs-lookup"><span data-stu-id="95942-118">This article doesn’t cover the use-case of running the campaign more than once.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="95942-119">Mērķa auditorijas identificēšana</span><span class="sxs-lookup"><span data-stu-id="95942-119">Identify your target audience</span></span>

<span data-ttu-id="95942-120">Mūsu scenārijā mēs pieņemsim, ka klientu e-pasta adreses ir pieejamas auditorijas ieskatos, un viņu reklāmas preferences tika analizētas, lai identificētu segmenta dalībniekus.</span><span class="sxs-lookup"><span data-stu-id="95942-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="95942-121">[Segments, ko definējāt auditorijas ieskatos](segments.md), tiek saukts par **ChurnProneCustomers**, un jūs plānojat šiem klientiem nosūtīt e-pasta reklāmas kampaņu.</span><span class="sxs-lookup"><span data-stu-id="95942-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Segmentu lapas ekrānuzņēmumu, kurā ir izveidots ChurnProneCustomers segments.":::

<span data-ttu-id="95942-123">Piedāvājuma e-pasta ziņojumā, kuru vēlaties izsūtīt, būs vārds, uzvārds un klienta abonementa beigu datums.</span><span class="sxs-lookup"><span data-stu-id="95942-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="95942-124">Tas informē klientus par to, kādu atlaidi viņi saņem, ja abonements tiek atjaunots pirms tā derīgums beidzas.</span><span class="sxs-lookup"><span data-stu-id="95942-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="95942-125">Mērķa auditorijas eksportēšana</span><span class="sxs-lookup"><span data-stu-id="95942-125">Export your target audience</span></span>

<span data-ttu-id="95942-126">Identificēto mērķauditoriju izmantojot, mēs varam konfigurēt eksportu no auditorijas ieskatiem uz Azure Blob krātuves kontu.</span><span class="sxs-lookup"><span data-stu-id="95942-126">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

1. <span data-ttu-id="95942-127">Sadaļā Auditorijas ieskati ejiet uz **Administrators** > **Eksportēšanas galamērķi**.</span><span class="sxs-lookup"><span data-stu-id="95942-127">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="95942-128">Elementā **Azure Blob krātuve** atlasiet vienumu **Iestatīt**.</span><span class="sxs-lookup"><span data-stu-id="95942-128">In the **Azure Blob Storage** tile, select **Set up**.</span></span>

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Konfigurācijas elementu Azure Blob krātuvei.":::

1. <span data-ttu-id="95942-130">Norādiet šī jaunā eksportēšanas mērķa **Parādāmo nosaukumu** un pēc tam ievadiet tā Azure Blob krātuves konta **Konta nosaukumu**, **Konta atslēgu** un **Konteineru**, uz kuru vēlaties eksportēt segmentu.</span><span class="sxs-lookup"><span data-stu-id="95942-130">Provide a **Display name** for this new export destination and then enter the **Account name**, **Account key**, and **Container** of the Azure Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Krātuves konta konfigurācijas ekrānuzņēmums."::: 

   - <span data-ttu-id="95942-132">Papildinformāciju, kā atrast Azure Blob krātuves konta nosaukumu un konta atslēgu, skatiet sadaļā [Krātuves konta iestatījumu pārvaldība Azure portālā](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="95942-132">To learn more about how to find the Azure Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

   - <span data-ttu-id="95942-133">Lai uzzinātu, kā izveidot konteineru, skatiet sadaļu [Konteinera izveide](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="95942-133">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="95942-134">Atlasiet **Tālāk**.</span><span class="sxs-lookup"><span data-stu-id="95942-134">Select **Next**.</span></span>

1. <span data-ttu-id="95942-135">Izvēlieties segmentu, uz kuru vēlaties eksportēt.</span><span class="sxs-lookup"><span data-stu-id="95942-135">Choose the segment that you want to export.</span></span> <span data-ttu-id="95942-136">Šajā piemērā tas ir **ChurnProneCustomers**.</span><span class="sxs-lookup"><span data-stu-id="95942-136">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Segmenta atlases lietotāja interfeisa ekrānuzņēmums, kurā ir atlasīts ChurnProneCustomers segments.":::

1. <span data-ttu-id="95942-138">Atlasiet vienumu **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="95942-138">Select **Save**.</span></span>

<span data-ttu-id="95942-139">Pēc eksportēšanas mērķa saglabāšanas to atradīsit sadaļā **Administrēšana** > **Ekspotēšana** > **Mani eksportēšanas adresāti**.</span><span class="sxs-lookup"><span data-stu-id="95942-139">After saving the export destination, you find it on **Admin** > **Exports** > **My export destinations**.</span></span>

:::image type="content" source="media/export-destination-azure-blob-storage.png" alt-text="Ekrānuzņēmums, kurā izcelts eksportēšanas saraksts un segmenta paraugs.":::

<span data-ttu-id="95942-141">Tagad varat [eksportēt segmentu pēc pieprasījuma](export-destinations.md#export-data-on-demand).</span><span class="sxs-lookup"><span data-stu-id="95942-141">You can now [export the segment on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="95942-142">Eksportēšana arī tiks palaista ar katru [plānoto atsvaidzināšanu](system.md).</span><span class="sxs-lookup"><span data-stu-id="95942-142">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="95942-143">Nodrošiniet, lai eksportētajā segmentā ierakstu skaits iekļautos jūsu Adobe Campaign Standard licencei atļautajā ierobežojumā.</span><span class="sxs-lookup"><span data-stu-id="95942-143">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="95942-144">Eksportētie dati tiek glabāti iepriekš konfigurētajā Azure Blob krātuves konteinerā.</span><span class="sxs-lookup"><span data-stu-id="95942-144">Exported data is stored in the Azure Blob storage container you configured above.</span></span> <span data-ttu-id="95942-145">Konteinerā tiek automātiski izveidots šāds mapes ceļš:</span><span class="sxs-lookup"><span data-stu-id="95942-145">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="95942-146">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span><span class="sxs-lookup"><span data-stu-id="95942-146">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span></span>

<span data-ttu-id="95942-147">Piemērs: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span><span class="sxs-lookup"><span data-stu-id="95942-147">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span></span>

<span data-ttu-id="95942-148">Eksportēto entītiju *model.json* atrodas *%ExportDestinationName%* līmenī.</span><span class="sxs-lookup"><span data-stu-id="95942-148">The *model.json* for the exported entities resides at the *%ExportDestinationName%* level.</span></span>

<span data-ttu-id="95942-149">Piemērs: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span><span class="sxs-lookup"><span data-stu-id="95942-149">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span></span>

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a><span data-ttu-id="95942-150">Define Experience Data Model (XDM) definēšana programmā Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="95942-150">Define Experience Data Model (XDM) in Adobe Experience Platform</span></span>

<span data-ttu-id="95942-151">Lai no auditorijas ieskatiem eksportētos datus varētu izmantot Adobe Experience Platform, ir jādefinē Experience Data Model shēma un [jākonfigurē reāllaika klienta profila dati](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span><span class="sxs-lookup"><span data-stu-id="95942-151">Before the exported data from audience insights can be used within Adobe Experience Platform, we need to define the Experience Data Model schema and [configure the data for the Real-time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span></span>

<span data-ttu-id="95942-152">Uzziniet, [kas ir XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) un izprotiet [shēmas veidošanas pamatus](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span><span class="sxs-lookup"><span data-stu-id="95942-152">Learn [what XDM is](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) and understand the [basics of schema composition](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span></span>

## <a name="import-data-into-adobe-experience-platform"></a><span data-ttu-id="95942-153">Datu importēšana Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="95942-153">Import data into Adobe Experience Platform</span></span>

<span data-ttu-id="95942-154">Tagad, kad viss ir izveidots, mums ir jāimportē sagatavotie auditorijas dati no auditorijas ieskatiem uz programmu Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="95942-154">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Experience Platform.</span></span>

<span data-ttu-id="95942-155">Vispirms [izveidojiet Azure Blob krātuves avota savienojumu](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span><span class="sxs-lookup"><span data-stu-id="95942-155">First, [create an Azure Blob Storage source connection](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span></span>    

<span data-ttu-id="95942-156">Pēc avota savienojuma definēšanas [konfigurējiet datu plūsmu](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) mākoņkrātuves pakešu savienojumam, lai importētu segmenta izvadi no auditorijas ieskatiem Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="95942-156">After defining the source connection, [configure a dataflow](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) for a cloud storage batch connection to import the segment output from audience insights into Adobe Experience Platform.</span></span>

## <a name="create-an-audience-in-adobe-campaign-standard"></a><span data-ttu-id="95942-157">Auditorijas izveide programmā Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="95942-157">Create an audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="95942-158">Lai šai kampaņai nosūtītu e-pasta ziņojumu, tiks izmantota programma Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="95942-158">To send the email for this campaign, we will use Adobe Campaign Standard.</span></span> <span data-ttu-id="95942-159">Pēc datu importēšanas Adobe Experience Platform ir [jāizveido auditorija](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) programmā Adobe Campaign Standard, izmantojot datus Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="95942-159">After importing the data into Adobe Experience Platform, we need to [create an audience](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) in Adobe Campaign Standard using the data in Adobe Experience Platform.</span></span>

<span data-ttu-id="95942-160">Uzziniet, kā [lietot segmentu veidotāju](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) programmā Adobe Campaign Standard, lai defindētu auditoriju, pamatojoties uz Adobe Experience Platform esošajiem datiem.</span><span class="sxs-lookup"><span data-stu-id="95942-160">Learn how to [use segment builder](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) in Adobe Campaign Standard to define an audience based on the data in Adobe Experience Platform.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="95942-161">E-pasta ziņojuma izveide un nosūtīšana, izmantojot Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="95942-161">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="95942-162">Izveidojiet e-pasta saturu un pēc tam [pārbaudiet un nosūtiet](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) e-pasta ziņojumu.</span><span class="sxs-lookup"><span data-stu-id="95942-162">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="E-pasta ziņojuma paraugs ar atjaunošanas piedāvājumu no Adobe Campaign Standard.":::