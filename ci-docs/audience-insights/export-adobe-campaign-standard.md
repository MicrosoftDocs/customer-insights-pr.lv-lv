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
ms.openlocfilehash: b6c010d84119c2fa8b3ef99017c65f9939bf28c4
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760290"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a><span data-ttu-id="7cd81-103">Customer Insights segmentu izmantošana Adobe Campaign Standard (priekšskatījums)</span><span class="sxs-lookup"><span data-stu-id="7cd81-103">Use Customer Insights segments in Adobe Campaign Standard (preview)</span></span>

<span data-ttu-id="7cd81-104">Kā auditorijas ieskatu lietotājs programmai Dynamics 365 Customer Insights, iespējams, esat izveidojis segmentus, lai mārketinga kampaņas padarītu efektīvākas, vēršoties pie atbilstošas mērķauditorijas.</span><span class="sxs-lookup"><span data-stu-id="7cd81-104">As a user of audience insights for Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="7cd81-105">Lai izmantotu segmentu no auditorijas ieskatiem platformā Adobe Experience Platform un tādās programmās kā Adobe Campaign Standard, ir jāveic dažas šajā rakstā norādītās darbības.</span><span class="sxs-lookup"><span data-stu-id="7cd81-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/ACS-flow.png" alt-text="Šajā rakstā aprakstīto darbību procesa shēma.":::

## <a name="prerequisites"></a><span data-ttu-id="7cd81-107">Priekšnosacījumi</span><span class="sxs-lookup"><span data-stu-id="7cd81-107">Prerequisites</span></span>

-   <span data-ttu-id="7cd81-108">Dynamics 365 Customer Insights licence</span><span class="sxs-lookup"><span data-stu-id="7cd81-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="7cd81-109">Adobe Campaign Standard licence</span><span class="sxs-lookup"><span data-stu-id="7cd81-109">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="7cd81-110">Azure Blob krātuves konts</span><span class="sxs-lookup"><span data-stu-id="7cd81-110">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="7cd81-111">Kampaņas pārskats</span><span class="sxs-lookup"><span data-stu-id="7cd81-111">Campaign Overview</span></span>

<span data-ttu-id="7cd81-112">Lai labāk saprastu, kā var izmantot segmentus no auditorijas ieskatiem Adobe Experience Platform, apskatīsim izdomātu kampaņas paraugu.</span><span class="sxs-lookup"><span data-stu-id="7cd81-112">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="7cd81-113">Pieņemsim, ka jūsu uzņēmums saviem klientiem ASV piedāvā mēneša abonementa servisu.</span><span class="sxs-lookup"><span data-stu-id="7cd81-113">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="7cd81-114">Jūs vēlaties identificēt klientus, kuru abonementi ir jāatjauno nākamajās astoņās dienās, bet kuri vēl nav atjaunojušas savu abonementu.</span><span class="sxs-lookup"><span data-stu-id="7cd81-114">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="7cd81-115">Lai saglabātu šos klientus, jūs vēlaties viņiem nosūtīt reklāmas piedāvājumu pa e-pastu, izmantojot Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="7cd81-115">To keep these customers, you want to send them a promotional offer via email, using Adobe Campaign Standard.</span></span>

<span data-ttu-id="7cd81-116">Šajā piemērā mēs vēlamies vienu reizi palaist reklāmas e-pasta kampaņu.</span><span class="sxs-lookup"><span data-stu-id="7cd81-116">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="7cd81-117">Šajā rakstā nav ietverta kampaņas izmantošana vairākas reizes.</span><span class="sxs-lookup"><span data-stu-id="7cd81-117">This article doesn’t cover the use-case of running the campaign more than once.</span></span> <span data-ttu-id="7cd81-118">Tomēr auditorijas ieskatus un Adobe Campaign Standard darbību var konfigurēt arī periodiskam kampaņas scenārijam.</span><span class="sxs-lookup"><span data-stu-id="7cd81-118">However, audience insights and Adobe Campaign Standard can be configured to work for a recurring campaign scenario too.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="7cd81-119">Mērķa auditorijas identificēšana</span><span class="sxs-lookup"><span data-stu-id="7cd81-119">Identify your target audience</span></span>

<span data-ttu-id="7cd81-120">Mūsu scenārijā mēs pieņemsim, ka klientu e-pasta adreses ir pieejamas auditorijas ieskatos, un viņu reklāmas preferences tika analizētas, lai identificētu segmenta dalībniekus.</span><span class="sxs-lookup"><span data-stu-id="7cd81-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="7cd81-121">[Segments, ko definējāt auditorijas ieskatos](segments.md), tiek saukts par **ChurnProneCustomers**, un jūs plānojat šiem klientiem nosūtīt e-pasta reklāmas kampaņu.</span><span class="sxs-lookup"><span data-stu-id="7cd81-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Segmentu lapas ekrānuzņēmumu, kurā ir izveidots ChurnProneCustomers segments.":::

<span data-ttu-id="7cd81-123">Piedāvājuma e-pasta ziņojumā, kuru vēlaties izsūtīt, būs vārds, uzvārds un klienta abonementa beigu datums.</span><span class="sxs-lookup"><span data-stu-id="7cd81-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="7cd81-124">Tas informē klientus par to, kādu atlaidi viņi saņem, ja abonements tiek atjaunots pirms tā derīgums beidzas.</span><span class="sxs-lookup"><span data-stu-id="7cd81-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="7cd81-125">Mērķa auditorijas eksportēšana</span><span class="sxs-lookup"><span data-stu-id="7cd81-125">Export your target audience</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="7cd81-126">Savienojuma konfigurēšana</span><span class="sxs-lookup"><span data-stu-id="7cd81-126">Configure a connection</span></span>

<span data-ttu-id="7cd81-127">Identificēto mērķauditoriju izmantojot, mēs varam konfigurēt eksportu no auditorijas ieskatiem uz Azure Blob krātuves kontu.</span><span class="sxs-lookup"><span data-stu-id="7cd81-127">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

1. <span data-ttu-id="7cd81-128">Auditorijas ieskatos dodieties uz **Administrators** > **Savienojumi**.</span><span class="sxs-lookup"><span data-stu-id="7cd81-128">In audience insights, go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="7cd81-129">Atlasiet **Pievienot savienojumu** un atlasiet **Adobe Campaign**, lai konfigurētu savienojumu, vai rūtī **Adobe Campaign** atlasiet **Iestatīt**</span><span class="sxs-lookup"><span data-stu-id="7cd81-129">Select **Add connection** and choose **Adobe Campaign** to configure the connection or select **Set up** in the **Adobe Campaign** tile</span></span>

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Konfigurācijā elements programmai Adobe Campaign Standard.":::

1. <span data-ttu-id="7cd81-131">Laukā **Parādāmais nosaukums** piešķiriet savienojumam atpazīstamu nosaukumu.</span><span class="sxs-lookup"><span data-stu-id="7cd81-131">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="7cd81-132">Parādāmais nosaukums un nosaukuma veids raksturo šo savienojumu.</span><span class="sxs-lookup"><span data-stu-id="7cd81-132">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="7cd81-133">Ir ieteicams izvēlēties nosaukumu, kas paskaidro savienojuma nolūku.</span><span class="sxs-lookup"><span data-stu-id="7cd81-133">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="7cd81-134">Izvēlieties, kurš var izmantot šo savienojumu.</span><span class="sxs-lookup"><span data-stu-id="7cd81-134">Choose who can use this connection.</span></span> <span data-ttu-id="7cd81-135">Ja nesāksit nekādas darbības, noklusējums būs Administratori.</span><span class="sxs-lookup"><span data-stu-id="7cd81-135">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="7cd81-136">Papildinformāciju skatiet rakstā [Atļaujas, kas nepieciešamas eksporta konfigurēšanai](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="7cd81-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="7cd81-137">Ievadiet sava Azure Blob krātuves konta, kurā vēlaties eksportēt segmentu, **Konta nosaukumu**, **Konta atslēgu** un **Konteineru**.</span><span class="sxs-lookup"><span data-stu-id="7cd81-137">Enter the **Account name**, **Account key**, and **Container** of the Azure Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Krātuves konta konfigurācijas ekrānuzņēmums."::: 

   - <span data-ttu-id="7cd81-139">Papildinformāciju, kā atrast Azure Blob krātuves konta nosaukumu un konta atslēgu, skatiet sadaļā [Krātuves konta iestatījumu pārvaldība Azure portālā](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="7cd81-139">To learn more about how to find the Azure Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

   - <span data-ttu-id="7cd81-140">Lai uzzinātu, kā izveidot konteineru, skatiet sadaļu [Konteinera izveide](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="7cd81-140">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="7cd81-141">Lai pabeigtu savienošanu, atlasiet **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="7cd81-141">Select **Save** to complete the connection.</span></span>

### <a name="configure-an-export"></a><span data-ttu-id="7cd81-142">Eksporta konfigurēšana</span><span class="sxs-lookup"><span data-stu-id="7cd81-142">Configure an export</span></span>

<span data-ttu-id="7cd81-143">Šo eksportu varat konfigurēt, ja jums ir piekļuve šā veida pieslēgumam.</span><span class="sxs-lookup"><span data-stu-id="7cd81-143">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="7cd81-144">Papildinformāciju skatiet rakstā [Atļaujas, kas nepieciešamas eksporta konfigurēšanai](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="7cd81-144">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="7cd81-145">Pārejiet uz **Dati** > **Eksportēšana**.</span><span class="sxs-lookup"><span data-stu-id="7cd81-145">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="7cd81-146">Lai izveidotu jaunu eksportu, atlasiet **Pievienot eksportu**.</span><span class="sxs-lookup"><span data-stu-id="7cd81-146">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="7cd81-147">Laukā **Savienošana eksportam** atlasiet savienojumu no sadaļas Adobe Campaign.</span><span class="sxs-lookup"><span data-stu-id="7cd81-147">In the **Connection for export** field, choose a connection from the Adobe Campaign section.</span></span> <span data-ttu-id="7cd81-148">Ja šis sadaļas nosaukums nav redzams, šāda veida savienojumi jums nav pieejami.</span><span class="sxs-lookup"><span data-stu-id="7cd81-148">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="7cd81-149">Izvēlieties segmentu, uz kuru vēlaties eksportēt.</span><span class="sxs-lookup"><span data-stu-id="7cd81-149">Choose the segment that you want to export.</span></span> <span data-ttu-id="7cd81-150">Šajā piemērā tas ir **ChurnProneCustomers**.</span><span class="sxs-lookup"><span data-stu-id="7cd81-150">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Segmenta atlases lietotāja interfeisa ekrānuzņēmums, kurā ir atlasīts ChurnProneCustomers segments.":::

1. <span data-ttu-id="7cd81-152">Atlasiet **Tālāk**.</span><span class="sxs-lookup"><span data-stu-id="7cd81-152">Select **Next**.</span></span>

1. <span data-ttu-id="7cd81-153">Tagad mēs kartējam laukus **Avots** no auditorijas ieskatu segmenta uz lauka nosaukumiem **Mērķis** Adobe Campaign Standard profila diagrammā.</span><span class="sxs-lookup"><span data-stu-id="7cd81-153">Now we map the **Source** fields from the audience insights segment to the **Target** field names in the Adobe Campaign Standard profile schema.</span></span>

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Lauka kartēšana programmas Adobe Campaign Standard savienotājam.":::

   <span data-ttu-id="7cd81-155">Ja vēlaties pievienot papildu atribūtus, atlasiet **Pievienot atribūtu**.</span><span class="sxs-lookup"><span data-stu-id="7cd81-155">If you want to add more attributes, select **Add attribute**.</span></span> <span data-ttu-id="7cd81-156">Mērķa nosaukums var atšķirties no avota lauka nosaukuma, lai segmenta izvadi joprojām varētu kartēt no auditorijas ieskatiem uz Adobe Campaign Standard, ja laukiem nav vienāds nosaukums abās sistēmās.</span><span class="sxs-lookup"><span data-stu-id="7cd81-156">The target name can be different from the source field name so you can still map segment output from audience insights to Adobe Campaign Standard if the fields don’t have the same name in the two systems.</span></span>

   > [!NOTE]
   > <span data-ttu-id="7cd81-157">E-pasta adrese tiek izmantota kā identitātes lauks, taču varat izmantot jebkuru citu identifikatoru no sava auditorijas ieskatu klienta profila, lai kartētu datus uz programmu Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="7cd81-157">Email address is used as an identity field but you can use any other identifier from your audience insights customer profile to map data to Adobe Campaign Standard.</span></span>

1. <span data-ttu-id="7cd81-158">Atlasiet vienumu **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="7cd81-158">Select **Save**.</span></span>

<span data-ttu-id="7cd81-159">Pēc eksportēšanas mērķa saglabāšanas, tas būs pieejams lapā **Dati** > **Eksportēšana**.</span><span class="sxs-lookup"><span data-stu-id="7cd81-159">After saving the export destination, you find it on **Data** > **Exports**.</span></span>

<span data-ttu-id="7cd81-160">Tagad varat [eksportēt segmentu pēc pieprasījuma](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="7cd81-160">You can now [export the segment on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="7cd81-161">Eksportēšana arī tiks palaista ar katru [plānoto atsvaidzināšanu](system.md).</span><span class="sxs-lookup"><span data-stu-id="7cd81-161">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="7cd81-162">Nodrošiniet, lai eksportētajā segmentā ierakstu skaits iekļautos jūsu Adobe Campaign Standard licencei atļautajā ierobežojumā.</span><span class="sxs-lookup"><span data-stu-id="7cd81-162">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="7cd81-163">Eksportētie dati tiek glabāti iepriekš konfigurētajā Azure Blob krātuves konteinerā.</span><span class="sxs-lookup"><span data-stu-id="7cd81-163">Exported data is stored in the Azure Blob storage container you configured above.</span></span> <span data-ttu-id="7cd81-164">Konteinerā tiek automātiski izveidots šāds mapes ceļš:</span><span class="sxs-lookup"><span data-stu-id="7cd81-164">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="7cd81-165">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span><span class="sxs-lookup"><span data-stu-id="7cd81-165">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span></span>

<span data-ttu-id="7cd81-166">Piemērs: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span><span class="sxs-lookup"><span data-stu-id="7cd81-166">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span></span>

## <a name="configure-adobe-campaign-standard"></a><span data-ttu-id="7cd81-167">Adobe Campaign Standard konfigurēšana</span><span class="sxs-lookup"><span data-stu-id="7cd81-167">Configure Adobe Campaign Standard</span></span>

<span data-ttu-id="7cd81-168">Ja tiek eksportēts segments no auditorijas ieskatiem, tajā ir ietvertas kolonnas, ko atlasījāt, definējot eksportēšanas mērķi iepriekšējā darbībā.</span><span class="sxs-lookup"><span data-stu-id="7cd81-168">When a segment from audience insights is exported, it contains the columns you selected while defining the export destination in the previous step.</span></span> <span data-ttu-id="7cd81-169">Šos datus var izmantot, lai [veidotu profilus programmā Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span><span class="sxs-lookup"><span data-stu-id="7cd81-169">This data can be used to [create profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span></span>

<span data-ttu-id="7cd81-170">Lai izmantotu segmentu Adobe Campaign Standard, mums ir jāpaplašina profila diagramma programmā Adobe Campaign Standard, ietverot divus papildu laukus.</span><span class="sxs-lookup"><span data-stu-id="7cd81-170">To use the segment in Adobe Campaign Standard, we need to extend the profile schema in Adobe Campaign Standard to include two additional fields.</span></span> <span data-ttu-id="7cd81-171">Informācija par to, kā [paplašināt profila resursu](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) ar jauniem laukiem programmā Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="7cd81-171">Learn how to [extend the profile resource](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) with new fields in Adobe Campaign Standard.</span></span>

<span data-ttu-id="7cd81-172">Mūsu piemērā šie lauki ir *Segmenta nosaukums un Segmenta datums (nav obligāti).*</span><span class="sxs-lookup"><span data-stu-id="7cd81-172">In our example, these fields are *Segment Name and Segment Date (optional).*</span></span>

<span data-ttu-id="7cd81-173">Mēs izmantosim šos laukus, lai identificētu profilus programmā Adobe Campaign Standard, kurus vēlamies sasniegt šīs kampaņas vajadzībām.</span><span class="sxs-lookup"><span data-stu-id="7cd81-173">We will use these fields to identify the profiles in Adobe Campaign Standard we want to target for this campaign.</span></span>

<span data-ttu-id="7cd81-174">Ja Adobe Campaign Standard nav citu ierakstu, izņemot tos, ko plānojat importēt, šo darbību varat izlaist.</span><span class="sxs-lookup"><span data-stu-id="7cd81-174">If there are no other records in Adobe Campaign Standard, other than what you are going to import, you can skip this step.</span></span>

## <a name="import-data-into-adobe-campaign-standard"></a><span data-ttu-id="7cd81-175">Datu importēšana programmā Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="7cd81-175">Import data into Adobe Campaign Standard</span></span>

<span data-ttu-id="7cd81-176">Tagad, kad viss ir izveidots, mums ir jāimportē sagatavotie auditorijas dati no auditorijas ieskatiem uz programmu Adobe Campaign Standard, lai izveidotu profilus.</span><span class="sxs-lookup"><span data-stu-id="7cd81-176">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Campaign Standard to create profiles.</span></span> <span data-ttu-id="7cd81-177">Informācija par to, kā [importēt profilus programmā Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences), izmantojot darbplūsmu.</span><span class="sxs-lookup"><span data-stu-id="7cd81-177">Learn [how to import profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) using a workflow.</span></span>

<span data-ttu-id="7cd81-178">Tālāk redzamajā attēlā importēšanas darbplūsma ir konfigurēta tā, lai tā darbotos ik pēc 8 stundām, un tā meklē eksportētos auditorijas ieskatu segmentus (.csv fails Azure Blob krātuvē).</span><span class="sxs-lookup"><span data-stu-id="7cd81-178">The import workflow in the image below has been configured to run every 8 hours and looks for exported audience insights segments (.csv file in Azure Blob Storage).</span></span> <span data-ttu-id="7cd81-179">Darbplūsma izvelk .csv faila saturu noteiktā kolonnu secībā.</span><span class="sxs-lookup"><span data-stu-id="7cd81-179">The workflow extracts the .csv file content in a specified column order.</span></span> <span data-ttu-id="7cd81-180">Šī darbplūsma ir būvēta, lai veiktu pamata kļūdu apstrādi un nodrošinātu, ka katram ierakstam ir e-pasta adrese, pirms dati tiek iepakoti programmā Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="7cd81-180">This workflow has been built to perform basic error handling and ensure that each record has an email address before hydrating the data in Adobe Campaign Standard.</span></span> <span data-ttu-id="7cd81-181">Darbplūsma arī izvelk segmenta nosaukumu no faila nosaukuma, pirms tas tiek augšupievietots ACS profila datos.</span><span class="sxs-lookup"><span data-stu-id="7cd81-181">The workflow also extracts the segment name from the filename before upserting into ACS Profile data.</span></span>

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Importēšanas darbplūsmas programmas Adobe Campaign Standard lietotāja interfeisā ekrānuzņēmums.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a><span data-ttu-id="7cd81-183">Auditorijas izgūšana programmā Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="7cd81-183">Retrieve the audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="7cd81-184">Kad dati ir importēti programmā Adobe Campaign Standard, varat [izveidot darbplūsmu](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) un [vaicāt](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) klientus, pamatojoties uz *Segmenta nosaukumu* un *Segmenta datumu*, lai atlasītu profilus, kas tika identificēti mūsu piemēra kampaņai.</span><span class="sxs-lookup"><span data-stu-id="7cd81-184">Once the data is imported into Adobe Campaign Standard, you [can create a workflow](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) and [query](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) the customers based on the *Segment Name* and *Segment Date* to select profiles that were identified for our sample campaign.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="7cd81-185">E-pasta ziņojuma izveide un nosūtīšana, izmantojot Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="7cd81-185">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="7cd81-186">Izveidojiet e-pasta saturu un pēc tam [pārbaudiet un nosūtiet](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) e-pasta ziņojumu.</span><span class="sxs-lookup"><span data-stu-id="7cd81-186">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="E-pasta ziņojuma paraugs ar atjaunošanas piedāvājumu no Adobe Campaign Standard.":::
