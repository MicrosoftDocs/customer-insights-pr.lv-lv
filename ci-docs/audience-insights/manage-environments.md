---
title: Vižu izveide un pārvaldība
description: Uzziniet, kā pierakstīties pakalpojumā un kā pārvaldīt vides.
ms.date: 11/10/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
ms.reviewer: nimagen
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 010336445d0825a7ff82d1b7a65702fc12245788
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644142"
---
# <a name="manage-environments"></a><span data-ttu-id="792a3-103">Pārvaldīt vides</span><span class="sxs-lookup"><span data-stu-id="792a3-103">Manage environments</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="792a3-104">Šajā rakstā ir paskaidrots, kā izveidot jaunu organizāciju un kā nodrošināt vidi.</span><span class="sxs-lookup"><span data-stu-id="792a3-104">This article explains how to create a new organization and how to provision an environment.</span></span>

## <a name="sign-up-and-create-an-organization"></a><span data-ttu-id="792a3-105">Pierakstīšanās un organizācijas izveide</span><span class="sxs-lookup"><span data-stu-id="792a3-105">Sign up and create an organization</span></span>

1. <span data-ttu-id="792a3-106">Dodieties uz [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/) tīmekļa vietni.</span><span class="sxs-lookup"><span data-stu-id="792a3-106">Go to the [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/) website.</span></span>

2. <span data-ttu-id="792a3-107">Atlasiet **Sākt**.</span><span class="sxs-lookup"><span data-stu-id="792a3-107">Select **Get Started**.</span></span>

3. <span data-ttu-id="792a3-108">Izvēlieties vēlamo reģistrēšanās scenāriju un atlasiet atbilstošo saiti.</span><span class="sxs-lookup"><span data-stu-id="792a3-108">Choose your preferred sign-up scenario and select the corresponding link.</span></span>

4. <span data-ttu-id="792a3-109">Piekrītiet noteikumiem un nosacījumiem un atlasiet **Turpināt**, lai sāktu organizācijas izveidi.</span><span class="sxs-lookup"><span data-stu-id="792a3-109">Accept the terms and conditions and select **Continue** to start creating the organization.</span></span>

5. <span data-ttu-id="792a3-110">Pēc vides izveides jūs novirzīs uz [Customer Insights](https://home.ci.ai.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="792a3-110">After the environment is created, you'll be redirected to [Customer Insights](https://home.ci.ai.dynamics.com).</span></span>

6. <span data-ttu-id="792a3-111">Izmantojiet demonstrācijas vidi, lai iepazītu programmu vai izveidotu jaunu vidi, veicot nākamajā sadaļā norādītās darbības.</span><span class="sxs-lookup"><span data-stu-id="792a3-111">Use the demo environment to explore the app, or create a new environment by following the steps in the next section.</span></span>

7. <span data-ttu-id="792a3-112">Pēc vides iestatījumu norādīšanas atlasiet **Izveidot**.</span><span class="sxs-lookup"><span data-stu-id="792a3-112">After specifying the environment settings, select **Create**.</span></span>

8. <span data-ttu-id="792a3-113">Jūs būsit pieteicies pēc vides sekmīgas izveides.</span><span class="sxs-lookup"><span data-stu-id="792a3-113">You'll be signed in after the environment was created successfully.</span></span>

## <a name="create-an-environment-in-an-existing-organization"></a><span data-ttu-id="792a3-114">Vides izveide esošā organizācijā</span><span class="sxs-lookup"><span data-stu-id="792a3-114">Create an environment in an existing organization</span></span>

<span data-ttu-id="792a3-115">Pastāv divi veidi, ka izveidot jaunu vidi.</span><span class="sxs-lookup"><span data-stu-id="792a3-115">There are two ways to create a new environment.</span></span> <span data-ttu-id="792a3-116">Varat norādīt pilnīgi jaunu konfigurāciju vai arī var kopēt dažus konfigurācijas iestatījumus no esošas vides.</span><span class="sxs-lookup"><span data-stu-id="792a3-116">You can either specify an entirely new configuration, or you can copy some configuration settings from an existing environment.</span></span>

<span data-ttu-id="792a3-117">Lai izveidotu vidi:</span><span class="sxs-lookup"><span data-stu-id="792a3-117">To create an environment:</span></span>

1. <span data-ttu-id="792a3-118">Lietotnes galvenē atlasiet simbolu **Iestatījumi**.</span><span class="sxs-lookup"><span data-stu-id="792a3-118">Select the **Settings** symbol in the header of the app.</span></span>

1. <span data-ttu-id="792a3-119">Atlasiet **Jauna vide**.</span><span class="sxs-lookup"><span data-stu-id="792a3-119">Select **New environment**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="792a3-120">![Vides iestatījumi](media/environment-settings-dialog.png)</span><span class="sxs-lookup"><span data-stu-id="792a3-120">![Environment settings](media/environment-settings-dialog.png)</span></span>

1. <span data-ttu-id="792a3-121">Dialoglodziņā **Jaunas vides izveide** atlasiet **Jauna vide**.</span><span class="sxs-lookup"><span data-stu-id="792a3-121">In the **Create new environment** dialog, select **New environment**.</span></span>

   <span data-ttu-id="792a3-122">Ja vēlaties [kopēt datus no pašreizējās vides](#additional-considerations-for-copy-configuration-preview), atlasiet **Kopēt no esošās vides**.</span><span class="sxs-lookup"><span data-stu-id="792a3-122">If you want to [copy data from the current environment](#additional-considerations-for-copy-configuration-preview), select **Copy from existing environment**.</span></span> <span data-ttu-id="792a3-123">Jūs redzēsiet sarakstu, kurā ir visas jūsu organizācijā pieejamās vides, no kurām varat kopēt datus.</span><span class="sxs-lookup"><span data-stu-id="792a3-123">You'll see a list of all available environments in your organization where you can copy data from.</span></span>

1. <span data-ttu-id="792a3-124">Sniedziet šādu informāciju:</span><span class="sxs-lookup"><span data-stu-id="792a3-124">Provide the following details:</span></span>
   - <span data-ttu-id="792a3-125">**Nosaukums**: Šīs vides nosaukums.</span><span class="sxs-lookup"><span data-stu-id="792a3-125">**Name**: The name for this environment.</span></span> <span data-ttu-id="792a3-126">Šis lauks jau ir aizpildīts, ja esat kopējis no esošas vides, bet varat to mainīt.</span><span class="sxs-lookup"><span data-stu-id="792a3-126">This field is already filled in if you've copied an existing environment, but you can change it.</span></span>
   - <span data-ttu-id="792a3-127">**Reģions**: Reģions, kurā tiek izvietots un viesots pakalpojums.</span><span class="sxs-lookup"><span data-stu-id="792a3-127">**Region**: The region into which the service is deployed and hosted.</span></span>
   - <span data-ttu-id="792a3-128">**Veids**: Atlasiet, vai vēlaties veidot ražošanas vai smilškastes vidi.</span><span class="sxs-lookup"><span data-stu-id="792a3-128">**Type**: Select whether you want to create a Production or Sandbox environment.</span></span>

2. <span data-ttu-id="792a3-129">Pēc izvēles varat arī atlasīt **Papildu iestatījumus**:</span><span class="sxs-lookup"><span data-stu-id="792a3-129">Optionally, you can select **Advanced settings**:</span></span>

   - <span data-ttu-id="792a3-130">**Saglabāt visus datus uz** : Norāda, kur saglabāt no Customer Insights ģenerētos izvades datus.</span><span class="sxs-lookup"><span data-stu-id="792a3-130">**Save all data to**: Specifies where you want to store the output data generated from Customer Insights.</span></span> <span data-ttu-id="792a3-131">Jums ir divas opcijas: **Customer Insights krātuve** (Azure Data Lake, ko pārvalda Customer Insights darba grupa) un **Azure Data Lake Storage Gen2** (jūsu Azure Data Lake Storage).</span><span class="sxs-lookup"><span data-stu-id="792a3-131">You'll have two options: **Customer Insights storage** (an Azure Data Lake managed by the Customer Insights team) and **Azure Data Lake Storage Gen2** (your own Azure Data Lake Storage).</span></span> <span data-ttu-id="792a3-132">Pēc noklusējuma tiek atlasīta opcija Customer Insights krātuve.</span><span class="sxs-lookup"><span data-stu-id="792a3-132">By default, the Customer Insights storage option is selected.</span></span>

   > [!NOTE]
   > <span data-ttu-id="792a3-133">Saglabājot datus Azure Data Lake Storage, jūs piekrītat, ka dati tiks pārsūtīti uz un uzglabāti šī Azure krātuves konta atbilstošajā ģeogrāfiskajā atrašanās vietā, kas var atšķirties no vietas, kur dati tiek glabāti programmā Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="792a3-133">By saving data to Azure Data Lake Storage, you agree that data will be transferred to and stored in the appropriate geographic location for that Azure storage account, which may differ from where data is stored in Dynamics 365 Customer Insights.</span></span> [<span data-ttu-id="792a3-134">Uzziniet vairāk Microsoft Trust Center.</span><span class="sxs-lookup"><span data-stu-id="792a3-134">Learn more at the Microsoft Trust Center.</span></span>](https://www.microsoft.com/trust-center)
   >
   > <span data-ttu-id="792a3-135">Pašlaik pārņemtās entītijas vienmēr tiek glabātas Customer Insights pārvaldītajā datu ezerā.</span><span class="sxs-lookup"><span data-stu-id="792a3-135">Currently, ingested entities are always stored in the Customer Insights managed data lake.</span></span>
   > <span data-ttu-id="792a3-136">Mēs atbalstām tikai Azure Data Lake Gen2 krātuves kontus tajā pašā Azure reģionā, kas atlasīts, veidojot vidi.</span><span class="sxs-lookup"><span data-stu-id="792a3-136">We support only Azure Data Lake Gen2 storage accounts from the same Azure region you selected when creating the environment.</span></span>
   > <span data-ttu-id="792a3-137">Mēs atbalstām tikai Azure Data Lake Gen2 Hierarchical Name Space (HNS) iespējotos krātuves kontus.</span><span class="sxs-lookup"><span data-stu-id="792a3-137">We support only Azure Data Lake Gen2 Hierarchical Name Space (HNS) enabled storage accounts.</span></span>

   - <span data-ttu-id="792a3-138">Azure Data Lake Storage Gen2 iespējai varat izvēlēties, vai, izmantojot opciju, kuras pamatā ir resurss, vai abonementa opciju, lai autentificētos.</span><span class="sxs-lookup"><span data-stu-id="792a3-138">For the Azure Data Lake Storage Gen2 option, you can choose between a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="792a3-139">Papildinformāciju skatiet tēmā [Auditorijas ieskatu savienošana ar Azure Data Lake Storage Gen2 kontu, izmantojot Azure pakalpojuma primāro nosaukumu](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="792a3-139">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="792a3-140">**Konteinera** nosaukumu nevar mainīt, un tas būs "customerinsights".</span><span class="sxs-lookup"><span data-stu-id="792a3-140">The **Container** name can't be changed and will be "customerinsights".</span></span>
   
   - <span data-ttu-id="792a3-141">Ja vēlaties izmantot [prognozes](predictions.md), ievadiet Common Data Service instances URL **Servera adreses** laukā sadaļā **Lietot prognozes**.</span><span class="sxs-lookup"><span data-stu-id="792a3-141">If you want to use [predictions](predictions.md), enter the Common Data Service instance URL in the **Server address** field under **Use predictions**.</span></span>

   <span data-ttu-id="792a3-142">Palaižot procesus, piemēram, datu uzņemšanas vai segmenta izveidi, tiek izveidotas atbilstošas mapes jūsu norādītajā krātuves kontā.</span><span class="sxs-lookup"><span data-stu-id="792a3-142">When you run processes, such as data ingestion or segment creation, corresponding folders will be created in the storage account you specified above.</span></span> <span data-ttu-id="792a3-143">Datu faili un model.json faili tiks izveidoti un pievienoti attiecīgajām apakšmapēm, pamatojoties uz jūsu palaisto procesu.</span><span class="sxs-lookup"><span data-stu-id="792a3-143">Data files and model.json files will be created and added to the respective subfolders based on the process you run.</span></span>

   <span data-ttu-id="792a3-144">Ja izveidojat vairāku veidu Customer Insights un izvēlaties saglabāt izvades entītijas, izmantojot savas krātuves konta vides, katrai videi, kurai ir ci_ konteinerā, tiks izveidotas atsevišķas mapes <environmentid>.</span><span class="sxs-lookup"><span data-stu-id="792a3-144">If you create multiple environments of Customer Insights and choose to save the output entities from those environments in your storage account, separate folders will be created for each environment with ci_<environmentid> in the container.</span></span>

### <a name="additional-considerations-for-copy-configuration-preview"></a><span data-ttu-id="792a3-145">Papildu apsvērumi kopēšanas konfigurācijai (priekšskatījums)</span><span class="sxs-lookup"><span data-stu-id="792a3-145">Additional considerations for copy configuration (preview)</span></span>

<span data-ttu-id="792a3-146">Tiek kopēti tālāk norādītie konfigurācijas iestatījumi.</span><span class="sxs-lookup"><span data-stu-id="792a3-146">The following configuration settings are copied:</span></span>

- <span data-ttu-id="792a3-147">Līdzekļu konfigurācija</span><span class="sxs-lookup"><span data-stu-id="792a3-147">Feature configurations</span></span>
- <span data-ttu-id="792a3-148">Inegsted/importētie datu avoti</span><span class="sxs-lookup"><span data-stu-id="792a3-148">Inegsted/imported data sources</span></span>
- <span data-ttu-id="792a3-149">Datu apvienošanas (kartējums, atbilstība, sapludināšana) konfigurācija</span><span class="sxs-lookup"><span data-stu-id="792a3-149">Data unification (Map, Match, Merge) configuration</span></span>
- <span data-ttu-id="792a3-150">Segmenti</span><span class="sxs-lookup"><span data-stu-id="792a3-150">Segments</span></span>
- <span data-ttu-id="792a3-151">Mēri</span><span class="sxs-lookup"><span data-stu-id="792a3-151">Measures</span></span>
- <span data-ttu-id="792a3-152">Attiecības</span><span class="sxs-lookup"><span data-stu-id="792a3-152">Relationships</span></span>
- <span data-ttu-id="792a3-153">Darbības</span><span class="sxs-lookup"><span data-stu-id="792a3-153">Activities</span></span>
- <span data-ttu-id="792a3-154">Meklēšanas un filtrēšanas rādītājs</span><span class="sxs-lookup"><span data-stu-id="792a3-154">Search & filter Index</span></span>
- <span data-ttu-id="792a3-155">Eksportēšanas galamērķi</span><span class="sxs-lookup"><span data-stu-id="792a3-155">Export destinations</span></span>
- <span data-ttu-id="792a3-156">Plānotā atsvaidzināšana</span><span class="sxs-lookup"><span data-stu-id="792a3-156">Scheduled refresh</span></span>
- <span data-ttu-id="792a3-157">Bagātinājumi</span><span class="sxs-lookup"><span data-stu-id="792a3-157">Enrichments</span></span>
- <span data-ttu-id="792a3-158">Modeļu pārvaldība</span><span class="sxs-lookup"><span data-stu-id="792a3-158">Model management</span></span>
- <span data-ttu-id="792a3-159">Lomu piešķīrumi</span><span class="sxs-lookup"><span data-stu-id="792a3-159">Role assignments</span></span>

<span data-ttu-id="792a3-160">*Netiek* kopēti tālāk norādītie konfigurācijas iestatījumi.</span><span class="sxs-lookup"><span data-stu-id="792a3-160">The following settings are *not* copied:</span></span>

- <span data-ttu-id="792a3-161">Klientu profili.</span><span class="sxs-lookup"><span data-stu-id="792a3-161">Customer profiles.</span></span>
- <span data-ttu-id="792a3-162">Datu avota akreditācijas dati.</span><span class="sxs-lookup"><span data-stu-id="792a3-162">Data source credentials.</span></span> <span data-ttu-id="792a3-163">Jums būs jāsniedz akreditācijas dati katram datu avotam un manuāli jāatsvaidzina datu avoti.</span><span class="sxs-lookup"><span data-stu-id="792a3-163">You'll have to provide the credentials for every data source and refresh the data sources manually.</span></span>
- <span data-ttu-id="792a3-164">Datu avoti no Common Data Model mapes un Common Data Service pārvaldīta datu ezera.</span><span class="sxs-lookup"><span data-stu-id="792a3-164">Data sources from Common Data Model folder and Common Data Service managed lake.</span></span> <span data-ttu-id="792a3-165">Šos datu avotus ir jāizveido manuāli, izmantojot tādu pašu nosaukumu kā avota vidē.</span><span class="sxs-lookup"><span data-stu-id="792a3-165">You'll have to create those data sources manually with the same name as in the source environment.</span></span>

<span data-ttu-id="792a3-166">Kopējot vidi, tiks parādīts apstiprinājuma ziņojums par to, ka ir izveidota jauna vide.</span><span class="sxs-lookup"><span data-stu-id="792a3-166">When you copy an environment, you'll see a confirmation message that the new environment has been created.</span></span> <span data-ttu-id="792a3-167">Atlasiet **Doties uz datu avotiem**, lai skatītu datu avotu sarakstu.</span><span class="sxs-lookup"><span data-stu-id="792a3-167">Select **Go to data sources** to see the list of data sources.</span></span>

<span data-ttu-id="792a3-168">Visiem datu avotiem būs redzams statuss **Nepieciešami akreditācijas dati**.</span><span class="sxs-lookup"><span data-stu-id="792a3-168">All the data sources will show a **Credentials Required** status.</span></span> <span data-ttu-id="792a3-169">Rediģējiet datu avotus un ievadiet akreditācijas datus, lai tos atsvaidzinātu.</span><span class="sxs-lookup"><span data-stu-id="792a3-169">Edit the data sources and enter the credentials to refresh them.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="792a3-170">![Kopēti datu avoti](media/data-sources-copied.png)</span><span class="sxs-lookup"><span data-stu-id="792a3-170">![Data sources copied](media/data-sources-copied.png)</span></span>

<span data-ttu-id="792a3-171">Pēc datu avotu atsvaidzināšanas dodieties uz **Dati** > **Apvienot**.</span><span class="sxs-lookup"><span data-stu-id="792a3-171">After refreshing the data sources, go to **Data** > **Unify**.</span></span> <span data-ttu-id="792a3-172">Šeit atradīsit avota vides iestatījumus.</span><span class="sxs-lookup"><span data-stu-id="792a3-172">Here you'll find settings from the source environment.</span></span> <span data-ttu-id="792a3-173">Rediģējiet tos pēc nepieciešamības vai atlasiet **Izpildīt**, lai sāktu datu unificēšanas procesu un izveidotu unificētu klienta entītiju.</span><span class="sxs-lookup"><span data-stu-id="792a3-173">Edit them as needed or select **Run** to start the data unification process and create the unified customer entity.</span></span>

<span data-ttu-id="792a3-174">Kad datu unificēšana ir pabeigta, dodieties uz **Pasākumi** un **Segmenti**, lai atsvaidzinātu arī tos.</span><span class="sxs-lookup"><span data-stu-id="792a3-174">When the data unification is complete, go to **Measures** and **Segments** to refresh them too.</span></span>

## <a name="edit-an-existing-environment"></a><span data-ttu-id="792a3-175">Esošas vides rediģēšana</span><span class="sxs-lookup"><span data-stu-id="792a3-175">Edit an existing environment</span></span>

<span data-ttu-id="792a3-176">Jūs varat rediģēt dažas esošās vides detaļas.</span><span class="sxs-lookup"><span data-stu-id="792a3-176">You can edit some of the details of existing environments.</span></span>

1. <span data-ttu-id="792a3-177">Dodieties uz **Administrators** > **Sistēma** > **Par**.</span><span class="sxs-lookup"><span data-stu-id="792a3-177">Go to **Admin** > **System** > **About**.</span></span>

2. <span data-ttu-id="792a3-178">Atlasiet **Rediģēt**.</span><span class="sxs-lookup"><span data-stu-id="792a3-178">Select **Edit**.</span></span>

3. <span data-ttu-id="792a3-179">Varat atjaunināt vides **Parādāmo nosaukumu**, taču **Reģionu** vai **Veidu** mainīt nevar.</span><span class="sxs-lookup"><span data-stu-id="792a3-179">You can update the environment's **Display name**, but you can't change the **Region** or **Type**.</span></span>

4. <span data-ttu-id="792a3-180">Ja vide ir konfigurēta saglabāt datus pakalpojumā Azure Data Lake Storage Gen2, jūs varat atjaunināt **Konta atslēgu**.</span><span class="sxs-lookup"><span data-stu-id="792a3-180">If an environment is configured to store data in Azure Data Lake Storage Gen2, you can update the **Account key**.</span></span> <span data-ttu-id="792a3-181">Taču nevar mainīt **Konta nosaukumu** vai **Konteinera** nosaukumu.</span><span class="sxs-lookup"><span data-stu-id="792a3-181">However, you can't change the **Account name** or **Container** name.</span></span>

5. <span data-ttu-id="792a3-182">Ja vēlaties, varat atjaunināt no uzņēmuma atslēgas savienojuma uz resursu vai abonementa bāzes savienojumu.</span><span class="sxs-lookup"><span data-stu-id="792a3-182">Optionally, you can update from an account key based connection to a resource-based or subscription-based connection.</span></span> <span data-ttu-id="792a3-183">Pēc jaunināšanas jūs nevarat atgriezties pie uzņēmuma atslēgas pēc atjaunināšanas.</span><span class="sxs-lookup"><span data-stu-id="792a3-183">Once upgraded, you cannot revert to account key after the update.</span></span> <span data-ttu-id="792a3-184">Papildinformāciju skatiet tēmā [Auditorijas ieskatu savienošana ar Azure Data Lake Storage Gen2 kontu, izmantojot Azure pakalpojuma primāro nosaukumu](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="792a3-184">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="792a3-185">Atjauninot savienojumu, nevar mainīt **Konteinera** informāciju.</span><span class="sxs-lookup"><span data-stu-id="792a3-185">You can't change **Container** information when updating the connection.</span></span>

## <a name="reset-an-existing-environment"></a><span data-ttu-id="792a3-186">Esošās vides atiestatīšana</span><span class="sxs-lookup"><span data-stu-id="792a3-186">Reset an existing environment</span></span>

<span data-ttu-id="792a3-187">Vidi var atiestatīt tukšā stāvoklī, ja vēlaties dzēst visas konfigurācijas un noņemt uzņemtos datus.</span><span class="sxs-lookup"><span data-stu-id="792a3-187">You can reset an environment to an empty state if you want to delete all configurations and remove the ingested data.</span></span>

1.  <span data-ttu-id="792a3-188">Dodieties uz **Administrators** > **Sistēma** > **Par**.</span><span class="sxs-lookup"><span data-stu-id="792a3-188">Go to **Admin** > **System** > **About**.</span></span>

2.  <span data-ttu-id="792a3-189">Atlasiet **Atiestatīt**.</span><span class="sxs-lookup"><span data-stu-id="792a3-189">Select **Reset**.</span></span> 

3.  <span data-ttu-id="792a3-190">Lai apstiprinātu dzēšanu, ievadiet vides nosaukumu un atlasiet **Atiestatīt**.</span><span class="sxs-lookup"><span data-stu-id="792a3-190">To confirm the deletion, enter the environment name and select **Reset**.</span></span>


## <a name="delete-an-existing-environment"></a><span data-ttu-id="792a3-191">Esošas vides dzēšana</span><span class="sxs-lookup"><span data-stu-id="792a3-191">Delete an existing environment</span></span>

1. <span data-ttu-id="792a3-192">Dodieties uz **Administrators** > **Sistēma** > **Par**.</span><span class="sxs-lookup"><span data-stu-id="792a3-192">Go to **Admin** > **System** > **About**.</span></span>

1. <span data-ttu-id="792a3-193">Atlasiet **Dzēst**.</span><span class="sxs-lookup"><span data-stu-id="792a3-193">Select **Delete**.</span></span>

1. <span data-ttu-id="792a3-194">Lai apstiprinātu dzēšanu, ievadiet vides nosaukumu un atlasiet **Dzēst**.</span><span class="sxs-lookup"><span data-stu-id="792a3-194">To confirm the deletion, enter the environment name and select **Delete**.</span></span>
