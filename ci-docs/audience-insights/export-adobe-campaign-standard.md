---
title: Customer Insights datu eksportēšana uz Adobe Campaign Standard
description: Uzziniet, kā auditorijas ieskatu segmentus var izmantot Adobe Campaign Standard.
ms.date: 02/26/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: a5d0154c3d7c473dcba03fac0847bafcf97de2f2
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596324"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a><span data-ttu-id="11a78-103">Customer Insights segmentu izmantošana Adobe Campaign Standard (priekšskatījums)</span><span class="sxs-lookup"><span data-stu-id="11a78-103">Use Customer Insights segments in Adobe Campaign Standard (preview)</span></span>

<span data-ttu-id="11a78-104">Kā auditorijas ieskatu lietotājs programmai Dynamics 365 Customer Insights, iespējams, esat izveidojis segmentus, lai mārketinga kampaņas padarītu efektīvākas, vēršoties pie atbilstošas mērķauditorijas.</span><span class="sxs-lookup"><span data-stu-id="11a78-104">As a user of audience insights for Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="11a78-105">Lai izmantotu segmentu no auditorijas ieskatiem platformā Adobe Experience Platform un tādās programmās kā Adobe Campaign Standard, ir jāveic dažas šajā rakstā norādītās darbības.</span><span class="sxs-lookup"><span data-stu-id="11a78-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/ACS-flow.png" alt-text="Šajā rakstā aprakstīto darbību procesa shēma.":::

## <a name="prerequisites"></a><span data-ttu-id="11a78-107">Priekšnosacījumi</span><span class="sxs-lookup"><span data-stu-id="11a78-107">Prerequisites</span></span>

-   <span data-ttu-id="11a78-108">Dynamics 365 Customer Insights licence</span><span class="sxs-lookup"><span data-stu-id="11a78-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="11a78-109">Adobe Campaign Standard licence</span><span class="sxs-lookup"><span data-stu-id="11a78-109">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="11a78-110">Azure Blob krātuves konts</span><span class="sxs-lookup"><span data-stu-id="11a78-110">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="11a78-111">Kampaņas pārskats</span><span class="sxs-lookup"><span data-stu-id="11a78-111">Campaign Overview</span></span>

<span data-ttu-id="11a78-112">Lai labāk saprastu, kā var izmantot segmentus no auditorijas ieskatiem Adobe Experience Platform, apskatīsim izdomātu kampaņas paraugu.</span><span class="sxs-lookup"><span data-stu-id="11a78-112">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="11a78-113">Pieņemsim, ka jūsu uzņēmums saviem klientiem ASV piedāvā mēneša abonementa servisu.</span><span class="sxs-lookup"><span data-stu-id="11a78-113">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="11a78-114">Jūs vēlaties identificēt klientus, kuru abonementi ir jāatjauno nākamajās astoņās dienās, bet kuri vēl nav atjaunojušas savu abonementu.</span><span class="sxs-lookup"><span data-stu-id="11a78-114">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="11a78-115">Lai saglabātu šos klientus, jūs vēlaties viņiem nosūtīt reklāmas piedāvājumu pa e-pastu, izmantojot Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="11a78-115">To keep these customers, you want to send them a promotional offer via email, using Adobe Campaign Standard.</span></span>

<span data-ttu-id="11a78-116">Šajā piemērā mēs vēlamies vienu reizi palaist reklāmas e-pasta kampaņu.</span><span class="sxs-lookup"><span data-stu-id="11a78-116">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="11a78-117">Šajā rakstā nav ietverta kampaņas izmantošana vairākas reizes.</span><span class="sxs-lookup"><span data-stu-id="11a78-117">This article doesn’t cover the use-case of running the campaign more than once.</span></span> <span data-ttu-id="11a78-118">Tomēr auditorijas ieskatus un Adobe Campaign Standard darbību var konfigurēt arī periodiskam kampaņas scenārijam.</span><span class="sxs-lookup"><span data-stu-id="11a78-118">However, audience insights and Adobe Campaign Standard can be configured to work for a recurring campaign scenario too.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="11a78-119">Mērķa auditorijas identificēšana</span><span class="sxs-lookup"><span data-stu-id="11a78-119">Identify your target audience</span></span>

<span data-ttu-id="11a78-120">Mūsu scenārijā mēs pieņemsim, ka klientu e-pasta adreses ir pieejamas auditorijas ieskatos, un viņu reklāmas preferences tika analizētas, lai identificētu segmenta dalībniekus.</span><span class="sxs-lookup"><span data-stu-id="11a78-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="11a78-121">[Segments, ko definējāt auditorijas ieskatos](segments.md), tiek saukts par **ChurnProneCustomers**, un jūs plānojat šiem klientiem nosūtīt e-pasta reklāmas kampaņu.</span><span class="sxs-lookup"><span data-stu-id="11a78-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Segmentu lapas ekrānuzņēmumu, kurā ir izveidots ChurnProneCustomers segments.":::

<span data-ttu-id="11a78-123">Piedāvājuma e-pasta ziņojumā, kuru vēlaties izsūtīt, būs vārds, uzvārds un klienta abonementa beigu datums.</span><span class="sxs-lookup"><span data-stu-id="11a78-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="11a78-124">Tas informē klientus par to, kādu atlaidi viņi saņem, ja abonements tiek atjaunots pirms tā derīgums beidzas.</span><span class="sxs-lookup"><span data-stu-id="11a78-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="11a78-125">Mērķa auditorijas eksportēšana</span><span class="sxs-lookup"><span data-stu-id="11a78-125">Export your target audience</span></span>

<span data-ttu-id="11a78-126">Identificēto mērķauditoriju izmantojot, mēs varam konfigurēt eksportu no auditorijas ieskatiem uz Azure Blob krātuves kontu.</span><span class="sxs-lookup"><span data-stu-id="11a78-126">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

1. <span data-ttu-id="11a78-127">Sadaļā Auditorijas ieskati ejiet uz **Administrators** > **Eksportēšanas galamērķi**.</span><span class="sxs-lookup"><span data-stu-id="11a78-127">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="11a78-128">Elementā **Adobe kampaņa** atlasiet **Iestatīt**.</span><span class="sxs-lookup"><span data-stu-id="11a78-128">In the **Adobe Campaign** tile, select **Set up**.</span></span>

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Konfigurācijā elements programmai Adobe Campaign Standard.":::

1. <span data-ttu-id="11a78-130">Norādiet šī jaunā eksportēšanas mērķa **Parādāmo nosaukumu** un pēc tam ievadiet tā Azure Blob krātuves konta **Konta nosaukumu**, **Konta atslēgu** un **Konteineru**, uz kuru vēlaties eksportēt segmentu.</span><span class="sxs-lookup"><span data-stu-id="11a78-130">Provide a **Display name** for this new export destination and then enter the **Account name**, **Account key**, and **Container** of the Azure Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Krātuves konta konfigurācijas ekrānuzņēmums."::: 

   - <span data-ttu-id="11a78-132">Papildinformāciju, kā atrast Azure Blob krātuves konta nosaukumu un konta atslēgu, skatiet sadaļā [Krātuves konta iestatījumu pārvaldība Azure portālā](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="11a78-132">To learn more about how to find the Azure Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

   - <span data-ttu-id="11a78-133">Lai uzzinātu, kā izveidot konteineru, skatiet sadaļu [Konteinera izveide](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="11a78-133">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="11a78-134">Atlasiet **Tālāk**.</span><span class="sxs-lookup"><span data-stu-id="11a78-134">Select **Next**.</span></span>

1. <span data-ttu-id="11a78-135">Izvēlieties segmentu, uz kuru vēlaties eksportēt.</span><span class="sxs-lookup"><span data-stu-id="11a78-135">Choose the segment that you want to export.</span></span> <span data-ttu-id="11a78-136">Šajā piemērā tas ir **ChurnProneCustomers**.</span><span class="sxs-lookup"><span data-stu-id="11a78-136">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Segmenta atlases lietotāja interfeisa ekrānuzņēmums, kurā ir atlasīts ChurnProneCustomers segments.":::

1. <span data-ttu-id="11a78-138">Atlasiet **Tālāk**.</span><span class="sxs-lookup"><span data-stu-id="11a78-138">Select **Next**.</span></span>

1. <span data-ttu-id="11a78-139">Tagad mēs kartējam laukus **Avots** no auditorijas ieskatu segmenta uz lauka nosaukumiem **Mērķis** Adobe Campaign Standard profila diagrammā.</span><span class="sxs-lookup"><span data-stu-id="11a78-139">Now we map the **Source** fields from the audience insights segment to the **Target** field names in the Adobe Campaign Standard profile schema.</span></span>

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Lauka kartēšana programmas Adobe Campaign Standard savienotājam.":::

   <span data-ttu-id="11a78-141">Ja vēlaties pievienot papildu atribūtus, atlasiet **Pievienot atribūtu**.</span><span class="sxs-lookup"><span data-stu-id="11a78-141">If you want to add more attributes, select **Add attribute**.</span></span> <span data-ttu-id="11a78-142">Mērķa nosaukums var atšķirties no avota lauka nosaukuma, lai segmenta izvadi joprojām varētu kartēt no auditorijas ieskatiem uz Adobe Campaign Standard, ja laukiem nav vienāds nosaukums abās sistēmās.</span><span class="sxs-lookup"><span data-stu-id="11a78-142">The target name can be different from the source field name so you can still map segment output from audience insights to Adobe Campaign Standard if the fields don’t have the same name in the two systems.</span></span>

   > [!NOTE]
   > <span data-ttu-id="11a78-143">E-pasta adrese tiek izmantota kā identitātes lauks, taču varat izmantot jebkuru citu identifikatoru no sava auditorijas ieskatu klienta profila, lai kartētu datus uz programmu Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="11a78-143">Email address is used as an identity field but you can use any other identifier from your audience insights customer profile to map data to Adobe Campaign Standard.</span></span>

1. <span data-ttu-id="11a78-144">Atlasiet vienumu **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="11a78-144">Select **Save**.</span></span>

<span data-ttu-id="11a78-145">Pēc eksportēšanas mērķa saglabāšanas to atradīsit sadaļā **Administrēšana** > **Ekspotēšana** > **Mani eksportēšanas adresāti**.</span><span class="sxs-lookup"><span data-stu-id="11a78-145">After saving the export destination, you find it on **Admin** > **Exports** > **My export destinations**.</span></span>

:::image type="content" source="media/export-destination-adobe-campaign-standard.png" alt-text="Ekrānuzņēmums, kurā izcelts eksportēšanas saraksts un segmenta paraugs.":::

<span data-ttu-id="11a78-147">Tagad varat [eksportēt segmentu pēc pieprasījuma](export-destinations.md#export-data-on-demand).</span><span class="sxs-lookup"><span data-stu-id="11a78-147">You can now [export the segment on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="11a78-148">Eksportēšana arī tiks palaista ar katru [plānoto atsvaidzināšanu](system.md).</span><span class="sxs-lookup"><span data-stu-id="11a78-148">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="11a78-149">Nodrošiniet, lai eksportētajā segmentā ierakstu skaits iekļautos jūsu Adobe Campaign Standard licencei atļautajā ierobežojumā.</span><span class="sxs-lookup"><span data-stu-id="11a78-149">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="11a78-150">Eksportētie dati tiek glabāti iepriekš konfigurētajā Azure Blob krātuves konteinerā.</span><span class="sxs-lookup"><span data-stu-id="11a78-150">Exported data is stored in the Azure Blob storage container you configured above.</span></span> <span data-ttu-id="11a78-151">Konteinerā tiek automātiski izveidots šāds mapes ceļš:</span><span class="sxs-lookup"><span data-stu-id="11a78-151">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="11a78-152">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span><span class="sxs-lookup"><span data-stu-id="11a78-152">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span></span>

<span data-ttu-id="11a78-153">Piemērs: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span><span class="sxs-lookup"><span data-stu-id="11a78-153">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span></span>

## <a name="configure-adobe-campaign-standard"></a><span data-ttu-id="11a78-154">Adobe Campaign Standard konfigurēšana</span><span class="sxs-lookup"><span data-stu-id="11a78-154">Configure Adobe Campaign Standard</span></span>

<span data-ttu-id="11a78-155">Ja tiek eksportēts segments no auditorijas ieskatiem, tajā ir ietvertas kolonnas, ko atlasījāt, definējot eksportēšanas mērķi iepriekšējā darbībā.</span><span class="sxs-lookup"><span data-stu-id="11a78-155">When a segment from audience insights is exported, it contains the columns you selected while defining the export destination in the previous step.</span></span> <span data-ttu-id="11a78-156">Šos datus var izmantot, lai [veidotu profilus programmā Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span><span class="sxs-lookup"><span data-stu-id="11a78-156">This data can be used to [create profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span></span>

<span data-ttu-id="11a78-157">Lai izmantotu segmentu Adobe Campaign Standard, mums ir jāpaplašina profila diagramma programmā Adobe Campaign Standard, ietverot divus papildu laukus.</span><span class="sxs-lookup"><span data-stu-id="11a78-157">To use the segment in Adobe Campaign Standard, we need to extend the profile schema in Adobe Campaign Standard to include two additional fields.</span></span> <span data-ttu-id="11a78-158">Informācija par to, kā [paplašināt profila resursu](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) ar jauniem laukiem programmā Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="11a78-158">Learn how to [extend the profile resource](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) with new fields in Adobe Campaign Standard.</span></span>

<span data-ttu-id="11a78-159">Mūsu piemērā šie lauki ir *Segmenta nosaukums un Segmenta datums (nav obligāti).*</span><span class="sxs-lookup"><span data-stu-id="11a78-159">In our example, these fields are *Segment Name and Segment Date (optional).*</span></span>

<span data-ttu-id="11a78-160">Mēs izmantosim šos laukus, lai identificētu profilus programmā Adobe Campaign Standard, kurus vēlamies sasniegt šīs kampaņas vajadzībām.</span><span class="sxs-lookup"><span data-stu-id="11a78-160">We will use these fields to identify the profiles in Adobe Campaign Standard we want to target for this campaign.</span></span>

<span data-ttu-id="11a78-161">Ja Adobe Campaign Standard nav citu ierakstu, izņemot tos, ko plānojat importēt, šo darbību varat izlaist.</span><span class="sxs-lookup"><span data-stu-id="11a78-161">If there are no other records in Adobe Campaign Standard, other than what you are going to import, you can skip this step.</span></span>

## <a name="import-data-into-adobe-campaign-standard"></a><span data-ttu-id="11a78-162">Datu importēšana programmā Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="11a78-162">Import data into Adobe Campaign Standard</span></span>

<span data-ttu-id="11a78-163">Tagad, kad viss ir izveidots, mums ir jāimportē sagatavotie auditorijas dati no auditorijas ieskatiem uz programmu Adobe Campaign Standard, lai izveidotu profilus.</span><span class="sxs-lookup"><span data-stu-id="11a78-163">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Campaign Standard to create profiles.</span></span> <span data-ttu-id="11a78-164">Informācija par to, kā [importēt profilus programmā Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences), izmantojot darbplūsmu.</span><span class="sxs-lookup"><span data-stu-id="11a78-164">Learn [how to import profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) using a workflow.</span></span>

<span data-ttu-id="11a78-165">Tālāk redzamajā attēlā importēšanas darbplūsma ir konfigurēta tā, lai tā darbotos ik pēc 8 stundām, un tā meklē eksportētos auditorijas ieskatu segmentus (.csv fails Azure Blob krātuvē).</span><span class="sxs-lookup"><span data-stu-id="11a78-165">The import workflow in the image below has been configured to run every 8 hours and looks for exported audience insights segments (.csv file in Azure Blob Storage).</span></span> <span data-ttu-id="11a78-166">Darbplūsma izvelk .csv faila saturu noteiktā kolonnu secībā.</span><span class="sxs-lookup"><span data-stu-id="11a78-166">The workflow extracts the .csv file content in a specified column order.</span></span> <span data-ttu-id="11a78-167">Šī darbplūsma ir būvēta, lai veiktu pamata kļūdu apstrādi un nodrošinātu, ka katram ierakstam ir e-pasta adrese, pirms dati tiek iepakoti programmā Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="11a78-167">This workflow has been built to perform basic error handling and ensure that each record has an email address before hydrating the data in Adobe Campaign Standard.</span></span> <span data-ttu-id="11a78-168">Darbplūsma arī izvelk segmenta nosaukumu no faila nosaukuma, pirms tas tiek augšupievietots ACS profila datos.</span><span class="sxs-lookup"><span data-stu-id="11a78-168">The workflow also extracts the segment name from the filename before upserting into ACS Profile data.</span></span>

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Importēšanas darbplūsmas programmas Adobe Campaign Standard lietotāja interfeisā ekrānuzņēmums.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a><span data-ttu-id="11a78-170">Auditorijas izgūšana programmā Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="11a78-170">Retrieve the audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="11a78-171">Kad dati ir importēti programmā Adobe Campaign Standard, varat [izveidot darbplūsmu](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) un [vaicāt](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) klientus, pamatojoties uz *Segmenta nosaukumu* un *Segmenta datumu*, lai atlasītu profilus, kas tika identificēti mūsu piemēra kampaņai.</span><span class="sxs-lookup"><span data-stu-id="11a78-171">Once the data is imported into Adobe Campaign Standard, you [can create a workflow](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) and [query](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) the customers based on the *Segment Name* and *Segment Date* to select profiles that were identified for our sample campaign.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="11a78-172">E-pasta ziņojuma izveide un nosūtīšana, izmantojot Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="11a78-172">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="11a78-173">Izveidojiet e-pasta saturu un pēc tam [pārbaudiet un nosūtiet](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) e-pasta ziņojumu.</span><span class="sxs-lookup"><span data-stu-id="11a78-173">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="E-pasta ziņojuma paraugs ar atjaunošanas piedāvājumu no Adobe Campaign Standard.":::