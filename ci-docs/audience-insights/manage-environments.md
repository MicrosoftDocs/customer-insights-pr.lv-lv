---
title: Vižu izveide un pārvaldība
description: Uzziniet, kā pierakstīties pakalpojumā un kā pārvaldīt vides.
ms.date: 03/26/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 8cc1401251ed7c45c598bd4a8fb33a9709fabbc8
ms.sourcegitcommit: d89b19b2a3497722b78362aeee688ae7e94915d9
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 04/13/2021
ms.locfileid: "5887995"
---
# <a name="manage-environments"></a><span data-ttu-id="3b609-103">Pārvaldīt vides</span><span class="sxs-lookup"><span data-stu-id="3b609-103">Manage environments</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="3b609-104">Šajā rakstā ir paskaidrots, kā izveidot jaunu organizāciju un kā nodrošināt vidi.</span><span class="sxs-lookup"><span data-stu-id="3b609-104">This article explains how to create a new organization and how to provision an environment.</span></span>

## <a name="sign-up-and-create-an-organization"></a><span data-ttu-id="3b609-105">Pierakstīšanās un organizācijas izveide</span><span class="sxs-lookup"><span data-stu-id="3b609-105">Sign up and create an organization</span></span>

1. <span data-ttu-id="3b609-106">Dodieties uz [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/) tīmekļa vietni.</span><span class="sxs-lookup"><span data-stu-id="3b609-106">Go to the [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/) website.</span></span>

2. <span data-ttu-id="3b609-107">Atlasiet **Sākt**.</span><span class="sxs-lookup"><span data-stu-id="3b609-107">Select **Get Started**.</span></span>

3. <span data-ttu-id="3b609-108">Izvēlieties vēlamo reģistrēšanās scenāriju un atlasiet atbilstošo saiti.</span><span class="sxs-lookup"><span data-stu-id="3b609-108">Choose your preferred sign-up scenario and select the corresponding link.</span></span>

4. <span data-ttu-id="3b609-109">Piekrītiet noteikumiem un nosacījumiem un atlasiet **Turpināt**, lai sāktu organizācijas izveidi.</span><span class="sxs-lookup"><span data-stu-id="3b609-109">Accept the terms and conditions and select **Continue** to start creating the organization.</span></span>

5. <span data-ttu-id="3b609-110">Pēc vides izveides jūs novirzīs uz [Customer Insights](https://home.ci.ai.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="3b609-110">After the environment is created, you'll be redirected to [Customer Insights](https://home.ci.ai.dynamics.com).</span></span>

6. <span data-ttu-id="3b609-111">Izmantojiet demonstrācijas vidi, lai iepazītu programmu vai izveidotu jaunu vidi, veicot nākamajā sadaļā norādītās darbības.</span><span class="sxs-lookup"><span data-stu-id="3b609-111">Use the demo environment to explore the app, or create a new environment by following the steps in the next section.</span></span>

7. <span data-ttu-id="3b609-112">Pēc vides iestatījumu norādīšanas atlasiet **Izveidot**.</span><span class="sxs-lookup"><span data-stu-id="3b609-112">After specifying the environment settings, select **Create**.</span></span>

8. <span data-ttu-id="3b609-113">Jūs būsit pieteicies pēc vides sekmīgas izveides.</span><span class="sxs-lookup"><span data-stu-id="3b609-113">You'll be signed in after the environment was created successfully.</span></span>

## <a name="create-an-environment-in-an-existing-organization"></a><span data-ttu-id="3b609-114">Vides izveide esošā organizācijā</span><span class="sxs-lookup"><span data-stu-id="3b609-114">Create an environment in an existing organization</span></span>

<span data-ttu-id="3b609-115">Pastāv divi veidi, ka izveidot jaunu vidi.</span><span class="sxs-lookup"><span data-stu-id="3b609-115">There are two ways to create a new environment.</span></span> <span data-ttu-id="3b609-116">Varat norādīt pilnīgi jaunu konfigurāciju vai arī var kopēt dažus konfigurācijas iestatījumus no esošas vides.</span><span class="sxs-lookup"><span data-stu-id="3b609-116">You can either specify an entirely new configuration, or you can copy some configuration settings from an existing environment.</span></span>

> [!NOTE]
> <span data-ttu-id="3b609-117">Organizācijas katrai Customer Insights licencei var izveidot *divas* vides.</span><span class="sxs-lookup"><span data-stu-id="3b609-117">Organizations can create *two* environments for every Customer Insights license.</span></span> <span data-ttu-id="3b609-118">Ja jūsu organizācija iegādājas vairāk nekā vienu licenci, [sazinieties ar mūsu atbalsta komandu](https://go.microsoft.com/fwlink/?linkid=2079641), lai tiktu paaugstināts pieejamo vižu skaists.</span><span class="sxs-lookup"><span data-stu-id="3b609-118">If your organization purchases more than once license, please [contact our support team](https://go.microsoft.com/fwlink/?linkid=2079641) to increase the number of available environments.</span></span> <span data-ttu-id="3b609-119">Papildinformāciju par noslodzi un pievienojumprogrammu noslodzi skatiet [Dynamics 365 licencēšanas rokasgrāmatā](https://go.microsoft.com/fwlink/?LinkId=866544).</span><span class="sxs-lookup"><span data-stu-id="3b609-119">For more information about capacity and add-on capacity, download [Dynamics 365 licensing guide](https://go.microsoft.com/fwlink/?LinkId=866544).</span></span>

<span data-ttu-id="3b609-120">Lai izveidotu vidi:</span><span class="sxs-lookup"><span data-stu-id="3b609-120">To create an environment:</span></span>

1. <span data-ttu-id="3b609-121">Programmas galvenē atlasiet **Vides** atlasītāju.</span><span class="sxs-lookup"><span data-stu-id="3b609-121">Select the **Environment** picker in the header of the app.</span></span>

1. <span data-ttu-id="3b609-122">Atlasiet **Jauns**.</span><span class="sxs-lookup"><span data-stu-id="3b609-122">Select **New**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3b609-123">![Vides iestatījumi](media/environment-settings-dialog.png)</span><span class="sxs-lookup"><span data-stu-id="3b609-123">![Environment settings](media/environment-settings-dialog.png)</span></span>

1. <span data-ttu-id="3b609-124">Dialoglodziņā **Jaunas vides izveide** atlasiet **Jauna vide**.</span><span class="sxs-lookup"><span data-stu-id="3b609-124">In the **Create new environment** dialog, select **New environment**.</span></span>

   <span data-ttu-id="3b609-125">Ja vēlaties [kopēt datus no pašreizējās vides](#considerations-for-copy-configuration-preview), atlasiet **Kopēt no esošās vides**.</span><span class="sxs-lookup"><span data-stu-id="3b609-125">If you want to [copy data from the current environment](#considerations-for-copy-configuration-preview), select **Copy from existing environment**.</span></span> <span data-ttu-id="3b609-126">Jūs redzēsiet sarakstu, kurā ir visas jūsu organizācijā pieejamās vides, no kurām varat kopēt datus.</span><span class="sxs-lookup"><span data-stu-id="3b609-126">You'll see a list of all available environments in your organization where you can copy data from.</span></span>

1. <span data-ttu-id="3b609-127">Sniedziet šādu informāciju:</span><span class="sxs-lookup"><span data-stu-id="3b609-127">Provide the following details:</span></span>
   - <span data-ttu-id="3b609-128">**Nosaukums**: Šīs vides nosaukums.</span><span class="sxs-lookup"><span data-stu-id="3b609-128">**Name**: The name for this environment.</span></span> <span data-ttu-id="3b609-129">Šis lauks jau ir aizpildīts, ja esat kopējis no esošas vides, bet varat to mainīt.</span><span class="sxs-lookup"><span data-stu-id="3b609-129">This field is already filled in if you've copied an existing environment, but you can change it.</span></span>
   - <span data-ttu-id="3b609-130">**Reģions**: Reģions, kurā tiek izvietots un viesots pakalpojums.</span><span class="sxs-lookup"><span data-stu-id="3b609-130">**Region**: The region into which the service is deployed and hosted.</span></span>
   - <span data-ttu-id="3b609-131">**Veids**: Atlasiet, vai vēlaties veidot ražošanas vai smilškastes vidi.</span><span class="sxs-lookup"><span data-stu-id="3b609-131">**Type**: Select whether you want to create a Production or Sandbox environment.</span></span>

1. <span data-ttu-id="3b609-132">Pēc izvēles varat arī atlasīt **Papildu iestatījumus**:</span><span class="sxs-lookup"><span data-stu-id="3b609-132">Optionally, you can select **Advanced settings**:</span></span>

   - <span data-ttu-id="3b609-133">**Saglabāt visus datus uz** : Norāda, kur saglabāt no Customer Insights ģenerētos izvades datus.</span><span class="sxs-lookup"><span data-stu-id="3b609-133">**Save all data to**: Specifies where you want to store the output data generated from Customer Insights.</span></span> <span data-ttu-id="3b609-134">Jums ir divas opcijas: **Customer Insights krātuve** (Azure Data Lake, ko pārvalda Customer Insights darba grupa) un **Azure Data Lake Storage Gen2** (jūsu Azure Data Lake Storage).</span><span class="sxs-lookup"><span data-stu-id="3b609-134">You'll have two options: **Customer Insights storage** (an Azure Data Lake managed by the Customer Insights team) and **Azure Data Lake Storage Gen2** (your own Azure Data Lake Storage).</span></span> <span data-ttu-id="3b609-135">Pēc noklusējuma tiek atlasīta opcija Customer Insights krātuve.</span><span class="sxs-lookup"><span data-stu-id="3b609-135">By default, the Customer Insights storage option is selected.</span></span>

   > [!NOTE]
   > <span data-ttu-id="3b609-136">Saglabājot datus Azure Data Lake Storage, jūs piekrītat, ka dati tiks pārsūtīti uz un uzglabāti šī Azure krātuves konta atbilstošajā ģeogrāfiskajā atrašanās vietā, kas var atšķirties no vietas, kur dati tiek glabāti programmā Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="3b609-136">By saving data to Azure Data Lake Storage, you agree that data will be transferred to and stored in the appropriate geographic location for that Azure storage account, which may differ from where data is stored in Dynamics 365 Customer Insights.</span></span> [<span data-ttu-id="3b609-137">Uzziniet vairāk Microsoft Trust Center.</span><span class="sxs-lookup"><span data-stu-id="3b609-137">Learn more at the Microsoft Trust Center.</span></span>](https://www.microsoft.com/trust-center)
   >
   > <span data-ttu-id="3b609-138">Pašlaik pārņemtās entītijas vienmēr tiek glabātas Customer Insights pārvaldītajā datu ezerā.</span><span class="sxs-lookup"><span data-stu-id="3b609-138">Currently, ingested entities are always stored in the Customer Insights managed data lake.</span></span>
   > <span data-ttu-id="3b609-139">Mēs atbalstām tikai Azure Data Lake Gen2 krātuves kontus tajā pašā Azure reģionā, kas atlasīts, veidojot vidi.</span><span class="sxs-lookup"><span data-stu-id="3b609-139">We support only Azure Data Lake Gen2 storage accounts from the same Azure region you selected when creating the environment.</span></span>
   > <span data-ttu-id="3b609-140">Mēs atbalstām tikai Azure Data Lake Gen2 Hierarchical Name Space (HNS) iespējotos krātuves kontus.</span><span class="sxs-lookup"><span data-stu-id="3b609-140">We support only Azure Data Lake Gen2 Hierarchical Name Space (HNS) enabled storage accounts.</span></span>

   - <span data-ttu-id="3b609-141">Azure Data Lake Storage Gen2 iespējai varat izvēlēties, vai, izmantojot opciju, kuras pamatā ir resurss, vai abonementa opciju, lai autentificētos.</span><span class="sxs-lookup"><span data-stu-id="3b609-141">For the Azure Data Lake Storage Gen2 option, you can choose between a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="3b609-142">Papildinformāciju skatiet tēmā [Auditorijas ieskatu savienošana ar Azure Data Lake Storage Gen2 kontu, izmantojot Azure pakalpojuma primāro nosaukumu](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="3b609-142">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="3b609-143">**Konteinera** nosaukumu nevar mainīt, un tas būs "customerinsights".</span><span class="sxs-lookup"><span data-stu-id="3b609-143">The **Container** name can't be changed and will be "customerinsights".</span></span>
   
   - <span data-ttu-id="3b609-144">Ja vēlaties izmantot [prognozes](predictions.md), konfigurējiet datu kopīgošanu ar lietojumprogrammām un risinājumiem, balstoties Microsoft Dataverse, vai iespējojiet datu uzņemšanu no lokāliem datu avotiem, sadaļā **Konfigurēt datu kopīgošanu ar Microsoft Dataverse un iespējojiet papildu iespējas** norādiet Microsoft Dataverse vides URL.</span><span class="sxs-lookup"><span data-stu-id="3b609-144">If you want to use [predictions](predictions.md), configure data sharing with applications and solutions based on Microsoft Dataverse, or enable data ingestion from on-premises data sources, provide the Microsoft Dataverse environment URL under **Configure data sharing with Microsoft Dataverse and enable additional capabilities**.</span></span> <span data-ttu-id="3b609-145">Atlasiet opciju **Iespējot datu kopīgošanu**, lai kopīgotu Customer Insights izvades datus ar Microsoft Dataverse Managed Data Lake.</span><span class="sxs-lookup"><span data-stu-id="3b609-145">Select **Enable data sharing** to share Customer Insights output data with a Microsoft Dataverse Managed Data Lake.</span></span>

     > [!NOTE]
     > - <span data-ttu-id="3b609-146">Datu kopīgošana ar Microsoft Dataverse Managed Data Lake pašlaik netiek atbalstīta, saglabājot visus savus datus jūsu Azure Data Lake Storage.</span><span class="sxs-lookup"><span data-stu-id="3b609-146">Data sharing with Microsoft Dataverse Managed Data Lake is currently not supported when you save all data to your own Azure Data Lake Storage.</span></span>
     > - <span data-ttu-id="3b609-147">[Trūkstošo vērtību prognoze entītijā](predictions.md) pašlaik netiek atbalstīta, iespējojot datu kopīgošanu ar Microsoft Dataverse Managed Data Lake.</span><span class="sxs-lookup"><span data-stu-id="3b609-147">[Prediction of missing values in an entity](predictions.md) is not currently supported when you enable data sharing with Microsoft Dataverse Managed Data Lake.</span></span>

     > [!div class="mx-imgBorder"]
     > <span data-ttu-id="3b609-148">![Konfigurēšanas opcijas, lai iespējotu datu kopīgošanu ar Microsoft Dataverse](media/datasharing-with-DataverseMDL.png)</span><span class="sxs-lookup"><span data-stu-id="3b609-148">![Configuration options to enable data sharing with Microsoft Dataverse](media/datasharing-with-DataverseMDL.png)</span></span>

   <span data-ttu-id="3b609-149">Palaižot procesus, piemēram, datu uzņemšanas vai segmenta izveidi, tiek izveidotas atbilstošas mapes jūsu norādītajā krātuves kontā.</span><span class="sxs-lookup"><span data-stu-id="3b609-149">When you run processes, such as data ingestion or segment creation, corresponding folders will be created in the storage account you specified above.</span></span> <span data-ttu-id="3b609-150">Datu faili un model.json faili tiks izveidoti un pievienoti attiecīgajām apakšmapēm, pamatojoties uz jūsu palaisto procesu.</span><span class="sxs-lookup"><span data-stu-id="3b609-150">Data files and model.json files will be created and added to the respective subfolders based on the process you run.</span></span>

   <span data-ttu-id="3b609-151">Ja izveidojat vairāku veidu Customer Insights un izvēlaties saglabāt izvades entītijas, izmantojot savas krātuves konta vides, katrai videi, kurai ir ci_ konteinerā, tiks izveidotas atsevišķas mapes <environmentid>.</span><span class="sxs-lookup"><span data-stu-id="3b609-151">If you create multiple environments of Customer Insights and choose to save the output entities from those environments in your storage account, separate folders will be created for each environment with ci_<environmentid> in the container.</span></span>

### <a name="considerations-for-copy-configuration-preview"></a><span data-ttu-id="3b609-152">Konfigurēšanas kopēšanas apsvērumi (priekšskatījums)</span><span class="sxs-lookup"><span data-stu-id="3b609-152">Considerations for copy configuration (preview)</span></span>

<span data-ttu-id="3b609-153">Tiek kopēti tālāk norādītie konfigurācijas iestatījumi.</span><span class="sxs-lookup"><span data-stu-id="3b609-153">The following configuration settings are copied:</span></span>

- <span data-ttu-id="3b609-154">Līdzekļu konfigurācija</span><span class="sxs-lookup"><span data-stu-id="3b609-154">Feature configurations</span></span>
- <span data-ttu-id="3b609-155">Ievadītie/importētie datu avoti</span><span class="sxs-lookup"><span data-stu-id="3b609-155">Ingested/imported data sources</span></span>
- <span data-ttu-id="3b609-156">Datu apvienošanas (kartējums, atbilstība, sapludināšana) konfigurācija</span><span class="sxs-lookup"><span data-stu-id="3b609-156">Data unification (Map, Match, Merge) configuration</span></span>
- <span data-ttu-id="3b609-157">Segmenti</span><span class="sxs-lookup"><span data-stu-id="3b609-157">Segments</span></span>
- <span data-ttu-id="3b609-158">Mēri</span><span class="sxs-lookup"><span data-stu-id="3b609-158">Measures</span></span>
- <span data-ttu-id="3b609-159">Attiecības</span><span class="sxs-lookup"><span data-stu-id="3b609-159">Relationships</span></span>
- <span data-ttu-id="3b609-160">Darbības</span><span class="sxs-lookup"><span data-stu-id="3b609-160">Activities</span></span>
- <span data-ttu-id="3b609-161">Meklēšanas un filtrēšanas rādītājs</span><span class="sxs-lookup"><span data-stu-id="3b609-161">Search & filter Index</span></span>
- <span data-ttu-id="3b609-162">Eksportēšanas galamērķi</span><span class="sxs-lookup"><span data-stu-id="3b609-162">Export destinations</span></span>
- <span data-ttu-id="3b609-163">Plānotā atsvaidzināšana</span><span class="sxs-lookup"><span data-stu-id="3b609-163">Scheduled refresh</span></span>
- <span data-ttu-id="3b609-164">Bagātinājumi</span><span class="sxs-lookup"><span data-stu-id="3b609-164">Enrichments</span></span>
- <span data-ttu-id="3b609-165">Modeļu pārvaldība</span><span class="sxs-lookup"><span data-stu-id="3b609-165">Model management</span></span>
- <span data-ttu-id="3b609-166">Lomu piešķīrumi</span><span class="sxs-lookup"><span data-stu-id="3b609-166">Role assignments</span></span>

<span data-ttu-id="3b609-167">*Netiek* kopēti tālāk norādītie konfigurācijas iestatījumi.</span><span class="sxs-lookup"><span data-stu-id="3b609-167">The following settings are *not* copied:</span></span>

- <span data-ttu-id="3b609-168">Klientu profili.</span><span class="sxs-lookup"><span data-stu-id="3b609-168">Customer profiles.</span></span>
- <span data-ttu-id="3b609-169">Datu avota akreditācijas dati.</span><span class="sxs-lookup"><span data-stu-id="3b609-169">Data source credentials.</span></span> <span data-ttu-id="3b609-170">Jums būs jāsniedz akreditācijas dati katram datu avotam un manuāli jāatsvaidzina datu avoti.</span><span class="sxs-lookup"><span data-stu-id="3b609-170">You'll have to provide the credentials for every data source and refresh the data sources manually.</span></span>
- <span data-ttu-id="3b609-171">Datu avoti no Common Data Model mapes un Common Data Service pārvaldīta datu ezera.</span><span class="sxs-lookup"><span data-stu-id="3b609-171">Data sources from Common Data Model folder and Common Data Service managed lake.</span></span> <span data-ttu-id="3b609-172">Šos datu avotus ir jāizveido manuāli, izmantojot tādu pašu nosaukumu kā avota vidē.</span><span class="sxs-lookup"><span data-stu-id="3b609-172">You'll have to create those data sources manually with the same name as in the source environment.</span></span>

<span data-ttu-id="3b609-173">Kopējot vidi, tiks parādīts apstiprinājuma ziņojums par to, ka ir izveidota jauna vide.</span><span class="sxs-lookup"><span data-stu-id="3b609-173">When you copy an environment, you'll see a confirmation message that the new environment has been created.</span></span> <span data-ttu-id="3b609-174">Atlasiet **Doties uz datu avotiem**, lai skatītu datu avotu sarakstu.</span><span class="sxs-lookup"><span data-stu-id="3b609-174">Select **Go to data sources** to see the list of data sources.</span></span>

<span data-ttu-id="3b609-175">Visiem datu avotiem būs redzams statuss **Nepieciešami akreditācijas dati**.</span><span class="sxs-lookup"><span data-stu-id="3b609-175">All the data sources will show a **Credentials Required** status.</span></span> <span data-ttu-id="3b609-176">Rediģējiet datu avotus un ievadiet akreditācijas datus, lai tos atsvaidzinātu.</span><span class="sxs-lookup"><span data-stu-id="3b609-176">Edit the data sources and enter the credentials to refresh them.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="3b609-177">![Kopēti datu avoti](media/data-sources-copied.png)</span><span class="sxs-lookup"><span data-stu-id="3b609-177">![Data sources copied](media/data-sources-copied.png)</span></span>

<span data-ttu-id="3b609-178">Pēc datu avotu atsvaidzināšanas dodieties uz **Dati** > **Apvienot**.</span><span class="sxs-lookup"><span data-stu-id="3b609-178">After refreshing the data sources, go to **Data** > **Unify**.</span></span> <span data-ttu-id="3b609-179">Šeit atradīsit avota vides iestatījumus.</span><span class="sxs-lookup"><span data-stu-id="3b609-179">Here you'll find settings from the source environment.</span></span> <span data-ttu-id="3b609-180">Rediģējiet tos pēc nepieciešamības vai atlasiet **Izpildīt**, lai sāktu datu unificēšanas procesu un izveidotu unificētu klienta entītiju.</span><span class="sxs-lookup"><span data-stu-id="3b609-180">Edit them as needed or select **Run** to start the data unification process and create the unified customer entity.</span></span>

<span data-ttu-id="3b609-181">Kad datu unificēšana ir pabeigta, dodieties uz **Pasākumi** un **Segmenti**, lai atsvaidzinātu arī tos.</span><span class="sxs-lookup"><span data-stu-id="3b609-181">When the data unification is complete, go to **Measures** and **Segments** to refresh them too.</span></span>

## <a name="edit-an-existing-environment"></a><span data-ttu-id="3b609-182">Esošas vides rediģēšana</span><span class="sxs-lookup"><span data-stu-id="3b609-182">Edit an existing environment</span></span>

<span data-ttu-id="3b609-183">Jūs varat rediģēt dažas esošās vides detaļas.</span><span class="sxs-lookup"><span data-stu-id="3b609-183">You can edit some of the details of existing environments.</span></span>

1.  <span data-ttu-id="3b609-184">Programmas galvenē atlasiet **Vides** atlasītāju.</span><span class="sxs-lookup"><span data-stu-id="3b609-184">Select the **Environment** picker in the header of the app.</span></span>

2.  <span data-ttu-id="3b609-185">Atlasiet **Rediģēt** ikonu.</span><span class="sxs-lookup"><span data-stu-id="3b609-185">Select the **Edit** icon.</span></span>

3. <span data-ttu-id="3b609-186">Lodziņā **Rediģēt vidi** var atjaunināt vides **Parādāmo nosaukumu**, taču nevar mainīt lauku **Reģions** vai **Tips**.</span><span class="sxs-lookup"><span data-stu-id="3b609-186">In the **Edit environment** box, you can update the environment's **Display name**, but you can't change the **Region** or **Type**.</span></span>

4. <span data-ttu-id="3b609-187">Ja vide ir konfigurēta saglabāt datus pakalpojumā Azure Data Lake Storage Gen2, jūs varat atjaunināt **Konta atslēgu**.</span><span class="sxs-lookup"><span data-stu-id="3b609-187">If an environment is configured to store data in Azure Data Lake Storage Gen2, you can update the **Account key**.</span></span> <span data-ttu-id="3b609-188">Taču nevar mainīt **Konta nosaukumu** vai **Konteinera** nosaukumu.</span><span class="sxs-lookup"><span data-stu-id="3b609-188">However, you can't change the **Account name** or **Container** name.</span></span>

5. <span data-ttu-id="3b609-189">Ja vēlaties, varat atjaunināt no uzņēmuma atslēgas savienojuma uz resursu vai abonementa bāzes savienojumu.</span><span class="sxs-lookup"><span data-stu-id="3b609-189">Optionally, you can update from an account key based connection to a resource-based or subscription-based connection.</span></span> <span data-ttu-id="3b609-190">Pēc jaunināšanas jūs nevarat atgriezties pie uzņēmuma atslēgas pēc atjaunināšanas.</span><span class="sxs-lookup"><span data-stu-id="3b609-190">Once upgraded, you cannot revert to account key after the update.</span></span> <span data-ttu-id="3b609-191">Papildinformāciju skatiet tēmā [Auditorijas ieskatu savienošana ar Azure Data Lake Storage Gen2 kontu, izmantojot Azure pakalpojuma primāro nosaukumu](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="3b609-191">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="3b609-192">Atjauninot savienojumu, nevar mainīt **Konteinera** informāciju.</span><span class="sxs-lookup"><span data-stu-id="3b609-192">You can't change **Container** information when updating the connection.</span></span>

6. <span data-ttu-id="3b609-193">Ja vēlaties, varat sniegt Microsoft Dataverse vides URL sadaļā **Konfigurēt datu kopīgošanu ar Microsoft Dataverse un iespējot papildu iespējas**.</span><span class="sxs-lookup"><span data-stu-id="3b609-193">Optionally, you can provide a Microsoft Dataverse environment URL under **Configure data sharing with Microsoft Dataverse and enable additional capabilities**.</span></span> <span data-ttu-id="3b609-194">Šīs iespējas ietver datu kopīgošanu ar lietojumprogrammām un risinājumiem, balstoties Microsoft Dataverse, datu uzņemšanā no lokālajiem datu avotiem vai [prognožu](predictions.md) lietošanā.</span><span class="sxs-lookup"><span data-stu-id="3b609-194">These capabilities inlcude data sharing with applications and solutions based on Microsoft Dataverse, data ingestion from on-premises data sources, or the use [predictions](predictions.md).</span></span> <span data-ttu-id="3b609-195">Atlasiet opciju **Iespējot datu kopīgošanu**, lai kopīgotu Customer Insights izvades datus ar Microsoft Dataverse Managed Data Lake.</span><span class="sxs-lookup"><span data-stu-id="3b609-195">Select **Enable data sharing** to share Customer Insights output data with a Microsoft Dataverse Managed Data lake.</span></span>

   > [!NOTE]
   > - <span data-ttu-id="3b609-196">Datu kopīgošana ar Microsoft Dataverse Managed Data Lake pašlaik netiek atbalstīta, saglabājot visus savus datus jūsu Azure Data Lake Storage.</span><span class="sxs-lookup"><span data-stu-id="3b609-196">Data sharing with Microsoft Dataverse Managed Data Lake is currently not supported when you save all data to your own Azure Data Lake Storage.</span></span>
   > - <span data-ttu-id="3b609-197">[Entitījā trūkstošo vērtību prognozēšana](predictions.md) pašlaik netiek atbalstīta, ja iespējojat datu kopīgošanu ar Microsoft Dataverse Managed Data Lake.</span><span class="sxs-lookup"><span data-stu-id="3b609-197">[Prediction of missing values in an entity](predictions.md) is currently not supported when you enable data sharing with Microsoft Dataverse Managed Data Lake.</span></span>

   <span data-ttu-id="3b609-198">Kolīdz ir iespējota datu kopīgošana ar Microsoft Dataverse, tiks aktivizēta pilnā jūsu datu avotu atsvaidzināšana un citi procesi.</span><span class="sxs-lookup"><span data-stu-id="3b609-198">Once you enable data sharing with Microsoft Dataverse, a full refresh of your data sources and other processes will be triggered.</span></span> <span data-ttu-id="3b609-199">Ja procesi pašlaik ir palaisti un gaida rindā, jums nebūs redzama opcija iespējot datu kopīgošanu ar Microsoft Dataverse.</span><span class="sxs-lookup"><span data-stu-id="3b609-199">If processes are currently running and queued, you will not see the option to enable data sharing with Microsoft Dataverse.</span></span> <span data-ttu-id="3b609-200">Lai iespējotu datu kopīgošanu, varat pagaidīt, kamēr šie procesi tiek pabeigti, vai tos atcelt.</span><span class="sxs-lookup"><span data-stu-id="3b609-200">You can wait for those processes to complete or cancel them to enable data sharing.</span></span> 
   
   :::image type="content" source="media/datasharing-with-DataverseMDL.png" alt-text="Konfigurēšanas opcijas, lai iespējotu datu kopīgošanu ar Microsoft Dataverse.":::
   
   <span data-ttu-id="3b609-202">Palaižot procesus, piemēram, datu uzņemšanas vai segmenta izveidi, tiek izveidotas atbilstošas mapes jūsu norādītajā krātuves kontā.</span><span class="sxs-lookup"><span data-stu-id="3b609-202">When you run processes, such as data ingestion or segment creation, corresponding folders will be created in the storage account you specified above.</span></span> <span data-ttu-id="3b609-203">Datu faili un model.json faili tiks izveidoti un pievienoti atbilstošajām apakšmapēm atkarībā no procesa, kuru palaižat.</span><span class="sxs-lookup"><span data-stu-id="3b609-203">Data files and model.json files will be created and added to the respective subfolders, depending on the process you run.</span></span>

## <a name="reset-an-existing-environment"></a><span data-ttu-id="3b609-204">Esošās vides atiestatīšana</span><span class="sxs-lookup"><span data-stu-id="3b609-204">Reset an existing environment</span></span>

<span data-ttu-id="3b609-205">Kā administrators jūs varat atiestatīt vidi tukšā stāvoklī, ja vēlaties dzēst visas konfigurācijas un noņemt uzņemtos datus.</span><span class="sxs-lookup"><span data-stu-id="3b609-205">As an administrator, you can reset an environment to an empty state if you want to delete all configurations and remove the ingested data.</span></span>

1.  <span data-ttu-id="3b609-206">Programmas galvenē atlasiet **Vides** atlasītāju.</span><span class="sxs-lookup"><span data-stu-id="3b609-206">Select the **Environment** picker in the header of the app.</span></span> 

2.  <span data-ttu-id="3b609-207">Atlasiet vidi, kuru vēlaties atiestatīt, un atlasiet daudzpunkti **...**.</span><span class="sxs-lookup"><span data-stu-id="3b609-207">Select the environment you want to reset and select the ellipsis **...**.</span></span> 

3. <span data-ttu-id="3b609-208">Izvēlieties opciju **Atiestatīt**.</span><span class="sxs-lookup"><span data-stu-id="3b609-208">Choose the **Reset** option.</span></span> 

4.  <span data-ttu-id="3b609-209">Lai apstiprinātu dzēšanu, ievadiet vides nosaukumu un atlasiet **Atiestatīt**.</span><span class="sxs-lookup"><span data-stu-id="3b609-209">To confirm the deletion, enter the environment name and select **Reset**.</span></span>

## <a name="delete-an-existing-environment-available-only-for-admins"></a><span data-ttu-id="3b609-210">Esošas vides dzēšana (pieejama tikai administratoriem)</span><span class="sxs-lookup"><span data-stu-id="3b609-210">Delete an existing environment (available only for admins)</span></span>

<span data-ttu-id="3b609-211">Jūs kā administrators varat dzēst jūsu administrētu vidi.</span><span class="sxs-lookup"><span data-stu-id="3b609-211">As an administrator, you can delete an environment you administer.</span></span>

1.  <span data-ttu-id="3b609-212">Programmas galvenē atlasiet **Vides** atlasītāju.</span><span class="sxs-lookup"><span data-stu-id="3b609-212">Select the **Environment** picker in the header of the app.</span></span>

2.  <span data-ttu-id="3b609-213">Atlasiet vidi, kuru vēlaties atiestatīt, un atlasiet daudzpunkti **...**.</span><span class="sxs-lookup"><span data-stu-id="3b609-213">Select the environment you want to reset and select the ellipsis **...**.</span></span> 

3. <span data-ttu-id="3b609-214">Izvēlieties opciju **Dzēst**.</span><span class="sxs-lookup"><span data-stu-id="3b609-214">Choose the **Delete** option.</span></span> 

4.  <span data-ttu-id="3b609-215">Lai apstiprinātu dzēšanu, ievadiet vides nosaukumu un atlasiet **Dzēst**.</span><span class="sxs-lookup"><span data-stu-id="3b609-215">To confirm the deletion, enter the environment name and select **Delete**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
