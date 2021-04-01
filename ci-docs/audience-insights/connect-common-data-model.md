---
title: Common Data Model datu savienošana ar Azure Data Lake kontu
description: Darbs ar Common Data Model datiem, izmantojot programmu Azure Data Lake Storage.
ms.date: 05/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 385406b706890d741fec2694c190c0fada7809d7
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596554"
---
# <a name="connect-to-a-common-data-model-folder-using-an-azure-data-lake-account"></a><span data-ttu-id="6b98d-103">Izveidojiet savienojumu ar Common Data Model mapi, izmantojot Azure Data Lake kontu</span><span class="sxs-lookup"><span data-stu-id="6b98d-103">Connect to a Common Data Model folder using an Azure Data Lake account</span></span>

<span data-ttu-id="6b98d-104">Šajā rakstā ir sniegta informācija, kā iegūt datus no Common Data Model mapes, izmantojot jūsu Azure Data Lake Storage Gen2 kontu.</span><span class="sxs-lookup"><span data-stu-id="6b98d-104">This article provides information on how to ingest data from a Common Data Model folder using your Azure Data Lake Storage Gen2 account.</span></span>

## <a name="important-considerations"></a><span data-ttu-id="6b98d-105">Svarīgi ieteikumi</span><span class="sxs-lookup"><span data-stu-id="6b98d-105">Important considerations</span></span>

- <span data-ttu-id="6b98d-106">Azure Data Lake datiem ir jāatbilst Common Data Model standartam.</span><span class="sxs-lookup"><span data-stu-id="6b98d-106">Data in your Azure Data Lake needs to follow the Common Data Model standard.</span></span> <span data-ttu-id="6b98d-107">Citi formāti pašlaik netiek atbalstīti.</span><span class="sxs-lookup"><span data-stu-id="6b98d-107">Other formats aren't supported at the moment.</span></span>

- <span data-ttu-id="6b98d-108">Datu ieguve atbalsta tikai Azure Data Lake *Gen2* krātuves kontus.</span><span class="sxs-lookup"><span data-stu-id="6b98d-108">Data ingestion supports Azure Data Lake *Gen2* storage accounts exclusively.</span></span> <span data-ttu-id="6b98d-109">Jūs nevarat izmantot Azure Data Lake Gen1 krātuves kontus datu ieguvei.</span><span class="sxs-lookup"><span data-stu-id="6b98d-109">You can't use Azure Data Lake Gen1 storage accounts to ingest data.</span></span>

- <span data-ttu-id="6b98d-110">Lai veiktu autentifikāciju ar Azure pakalpojuma primāro nosaukumu, pārliecinieties, vai tas ir konfigurēts jūsu nomniekā.</span><span class="sxs-lookup"><span data-stu-id="6b98d-110">To authenticate with an Azure service principal, make sure it's configured in your tenant.</span></span> <span data-ttu-id="6b98d-111">Papildinformāciju skatiet tēmā [Auditorijas ieskatu savienošana ar Azure Data Lake Storage Gen2 kontu, izmantojot Azure pakalpojuma primāro nosaukumu](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="6b98d-111">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span>

- <span data-ttu-id="6b98d-112">Azure Data Lake, kurā jūs vēlaties savienot un iegūt datus, ir jābūt vienā un tajā pašā Azure reģionā kā Dynamics 365 Customer Insights videi.</span><span class="sxs-lookup"><span data-stu-id="6b98d-112">The Azure Data Lake you want to connect and ingest data from have to be in the same Azure region as the Dynamics 365 Customer Insights environment.</span></span> <span data-ttu-id="6b98d-113">Savienojumi ar Common Data Model mapi no Data Lake citā Azure reģionā netiek atbalstīti.</span><span class="sxs-lookup"><span data-stu-id="6b98d-113">Connections to a Common Data Model folder from a data lake in a different Azure region is not supported.</span></span> <span data-ttu-id="6b98d-114">Lai iepazītu konkrētās vides Azure reģionu, apmeklējiet **Administrators** > **Sistēma** > **Par** sadaļā par auditorijas ieskatiem.</span><span class="sxs-lookup"><span data-stu-id="6b98d-114">To know the Azure region of the environment, go to **Admin** > **System** > **About** in audience insights.</span></span>

- <span data-ttu-id="6b98d-115">Pakalpojumā tiešsaistes pakalpojumos glabātie dati var tikt glabāti citā ietā, nevis tajā, kur tiek apstrādāti vai glabāti dati Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="6b98d-115">Data stored in online services, may be stored in a different location than where data is processed or stored in Dynamics 365 Customer Insights.</span></span><span data-ttu-id="6b98d-116"> Importējot vai savienojot ar tiešsaistes pakalpojumos glabātajiem datiem, jūs piekrītat, ka datus var pārnest uz Dynamics 365 Customer Insights un glabāt tajā. [Papildinformāciju skatiet Microsoft drošības kontroles centrā.](https://www.microsoft.com/trust-center)</span><span class="sxs-lookup"><span data-stu-id="6b98d-116"> By importing or connecting to data stored in online services, you agree that data can be transferred to and stored with Dynamics 365 Customer Insights. [Learn more at the Microsoft Trust Center.](https://www.microsoft.com/trust-center)</span></span>

## <a name="connect-to-a-common-data-model-folder"></a><span data-ttu-id="6b98d-117">Izveidot savienojumu ar mapi Common Data Model</span><span class="sxs-lookup"><span data-stu-id="6b98d-117">Connect to a Common Data Model folder</span></span>

1. <span data-ttu-id="6b98d-118">Sadaļā Auditorijas ieskati skatiet **Dati** > **Datu avoti**.</span><span class="sxs-lookup"><span data-stu-id="6b98d-118">In audience insights, go to **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="6b98d-119">Atlasiet **Pievienot datu avotu**.</span><span class="sxs-lookup"><span data-stu-id="6b98d-119">Select **Add data source**.</span></span>

1. <span data-ttu-id="6b98d-120">Atlasiet **Izveidot savienojumu ar Common Data Model mapi**, ievadiet datu avota **Nosaukumu** un pēc tam atlasiet **Tālāk**.</span><span class="sxs-lookup"><span data-stu-id="6b98d-120">Select **Connect to a Common Data Model folder**, enter a **Name** for the data source, and select **Next**.</span></span> <span data-ttu-id="6b98d-121">Nosaukuma vadlīnijas:</span><span class="sxs-lookup"><span data-stu-id="6b98d-121">Name guidelines:</span></span> 
   - <span data-ttu-id="6b98d-122">Sāciet ar burtu.</span><span class="sxs-lookup"><span data-stu-id="6b98d-122">Start with a letter.</span></span>
   - <span data-ttu-id="6b98d-123">Izmantojiet tikai burtus un ciparus.</span><span class="sxs-lookup"><span data-stu-id="6b98d-123">Use letters and numbers only.</span></span> <span data-ttu-id="6b98d-124">Speciālās rakstzīmes un atstarpes nav atļautas.</span><span class="sxs-lookup"><span data-stu-id="6b98d-124">Special characters and spaces are not allowed.</span></span>
   - <span data-ttu-id="6b98d-125">Izmantojiet no 3 līdz 64 rakstzīmēm.</span><span class="sxs-lookup"><span data-stu-id="6b98d-125">Use between 3 and 64 characters.</span></span>

1. <span data-ttu-id="6b98d-126">Varat izvēlēties, vai, izmantojot opciju, kuras pamatā ir resurss, vai abonementa opciju, lai autentificētos.</span><span class="sxs-lookup"><span data-stu-id="6b98d-126">You can choose between using a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="6b98d-127">Papildinformāciju skatiet tēmā [Auditorijas ieskatu savienošana ar Azure Data Lake Storage Gen2 kontu, izmantojot Azure pakalpojuma primāro nosaukumu](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="6b98d-127">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="6b98d-128">Ievadiet informāciju par **Konteineru** un atlasiet **Tālāk**.</span><span class="sxs-lookup"><span data-stu-id="6b98d-128">Enter the **Container** information and select **Next**.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="6b98d-129">![Dialoglodziņš, lai ievadītu jauna savienojuma detaļas Azure Data Lake](media/enter-new-storage-details.png)
   > </span><span class="sxs-lookup"><span data-stu-id="6b98d-129">![Dialog box to enter new connection details for Azure Data Lake](media/enter-new-storage-details.png)
   > </span></span>[!NOTE]
<span data-ttu-id="6b98d-130">Lai varētu izveidot savienojumu ar konteineri vai krātuves kontu, ir nepieciešama viena no tālāk minētajām lomām, lai varētu izveidot savienojumu ar datu avotu:</span><span class="sxs-lookup"><span data-stu-id="6b98d-130">You need one of the following roles either to the container or the storage account referred above to be able to connect to and create a data source:</span></span>
   >  - <span data-ttu-id="6b98d-131">Krātuves Blob datu lasītājs</span><span class="sxs-lookup"><span data-stu-id="6b98d-131">Storage Blob Data Reader</span></span>
   >  - <span data-ttu-id="6b98d-132">Krātuves Blob datu īpašnieks</span><span class="sxs-lookup"><span data-stu-id="6b98d-132">Storage Blob Data Owner</span></span>
   >  - <span data-ttu-id="6b98d-133">Krātuves Blob datu ieguldītājs</span><span class="sxs-lookup"><span data-stu-id="6b98d-133">Storage Blob Data Contributor</span></span>

1. <span data-ttu-id="6b98d-134">**Atlasiet Common Data Model mapi** dialoglodziņā atlasiet model.json vai manifest.json failu, no kura importēt datus, un atlasiet **Tālāk**.</span><span class="sxs-lookup"><span data-stu-id="6b98d-134">In the **Select a Common Data Model folder** dialog, select the model.json or manifest.json file to import data from, and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="6b98d-135">Jebkurš model.json vai manifest.json fails, kas saistīts ar citu datu avotu vidē, netiks rādīts sarakstā.</span><span class="sxs-lookup"><span data-stu-id="6b98d-135">Any model.json or manifest.json file associated with another data source in the environment won't show in the list.</span></span>

1. <span data-ttu-id="6b98d-136">Atlasītajā model.json vai manifest.json failā tiks parādīts pieejamo entītiju saraksts.</span><span class="sxs-lookup"><span data-stu-id="6b98d-136">You'll get a list of available entities in the selected model.json or manifest.json file.</span></span> <span data-ttu-id="6b98d-137">Jūs varat apskatīt un atlasīt no pieejamo entītiju saraksta un atlasīt **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="6b98d-137">You can review and select from the list of available entities and select **Save**.</span></span> <span data-ttu-id="6b98d-138">Jaunākie dati no atlasītajām entītijām tiks eksportēti katru dienu.</span><span class="sxs-lookup"><span data-stu-id="6b98d-138">All of the selected entities will be ingested from the new data source.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="6b98d-139">![Dialoglodziņš, kurā redzams entītiju saraksts no model.json faila](media/review-entities.png)</span><span class="sxs-lookup"><span data-stu-id="6b98d-139">![Dialog box showing a list of entities from a model.json file](media/review-entities.png)</span></span>

8. <span data-ttu-id="6b98d-140">Norādiet, kurām datu entītijām vēlaties iespējot datu profilēšanu, un atlasiet **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="6b98d-140">Indicate which data entities you want to enable data profiling and select **Save**.</span></span> <span data-ttu-id="6b98d-141">Datu profilēšana iespējo analīzi un citas iespējas.</span><span class="sxs-lookup"><span data-stu-id="6b98d-141">Data profiling enables analytics and other capabilities.</span></span> <span data-ttu-id="6b98d-142">Varat atlasīt visu entītiju, kas atlasa visus entītijas atribūtus, vai atlasiet noteiktus atribūtus pēc jūsu izvēles.</span><span class="sxs-lookup"><span data-stu-id="6b98d-142">You can select the whole entity, which selects all attributes from the entity, or select certain attributes of your choice.</span></span> <span data-ttu-id="6b98d-143">Pēc noklusējuma neviena entītija nav iespējota datu profilēšanai.</span><span class="sxs-lookup"><span data-stu-id="6b98d-143">By default, no entity is enabled for data profiling.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="6b98d-144">![Dialoglodziņš, kurā redzama datu profilēšana](media/dataprofiling-entities.png)</span><span class="sxs-lookup"><span data-stu-id="6b98d-144">![Dialog box showing a data profiling](media/dataprofiling-entities.png)</span></span>

9. <span data-ttu-id="6b98d-145">Kad esat saglabājis savas atlases, tiek atvērta lapa **Datu avoti**.</span><span class="sxs-lookup"><span data-stu-id="6b98d-145">After saving your selections, the **Data sources** page opens.</span></span> <span data-ttu-id="6b98d-146">Tagad jums būtu jāredz mapes Common Data Model savienojums kā datu avots.</span><span class="sxs-lookup"><span data-stu-id="6b98d-146">You should now see the Common Data Model folder connection as a data source.</span></span>

> [!NOTE]
> <span data-ttu-id="6b98d-147">model.json vai manifest.json failu var saistīt tikai ar vienu datu avotu tajā pašā vidē.</span><span class="sxs-lookup"><span data-stu-id="6b98d-147">A model.json file or manifest.json can only associate with one data source in the same environment.</span></span> <span data-ttu-id="6b98d-148">Tomēr tādu pašu model.json vai manifest.json failu var izmantot datu avotiem, kas atrodas vairākās vidēs.</span><span class="sxs-lookup"><span data-stu-id="6b98d-148">However, the same model.json or manifest.json file can be used for data sources in multiple environments.</span></span>

## <a name="edit-a-common-data-model-folder-data-source"></a><span data-ttu-id="6b98d-149">Common Data Model mapes datu avota rediģēšana</span><span class="sxs-lookup"><span data-stu-id="6b98d-149">Edit a Common Data Model folder data source</span></span>

<span data-ttu-id="6b98d-150">Varat atjaunināt tās krātuves konta piekļuves atslēgu, kurā ir ietverta Common Data Model mape.</span><span class="sxs-lookup"><span data-stu-id="6b98d-150">You can update the access key for the storage account containing the Common Data Model folder.</span></span> <span data-ttu-id="6b98d-151">Varat mainīt arī model.json vai manifest.json failu.</span><span class="sxs-lookup"><span data-stu-id="6b98d-151">You may also change the model.json or manifest.json file.</span></span> <span data-ttu-id="6b98d-152">Lai izveidotu savienojumu ar citu konteineru no krātuves konta vai mainītu konta nosaukumu, [izveidojiet jaunu datu avota savienojumu](#connect-to-a-common-data-model-folder).</span><span class="sxs-lookup"><span data-stu-id="6b98d-152">To connect to a different container from your storage account, or change the account name, [create a new data source connection](#connect-to-a-common-data-model-folder).</span></span>

1. <span data-ttu-id="6b98d-153">Sadaļā Auditorijas ieskati skatiet **Dati** > **Datu avoti**.</span><span class="sxs-lookup"><span data-stu-id="6b98d-153">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="6b98d-154">Blakus atjaunināmajam datu avotam atlasiet elipsi.</span><span class="sxs-lookup"><span data-stu-id="6b98d-154">Next to the data source you'd like to update, select the ellipsis.</span></span>

3. <span data-ttu-id="6b98d-155">No saraksta atlasiet opciju **Rediģēt**.</span><span class="sxs-lookup"><span data-stu-id="6b98d-155">Select the **Edit** option from the list.</span></span>

4. <span data-ttu-id="6b98d-156">Pēc izvēles atjauniniet **Piekļuves atslēgu** un atlasiet **Tālāk**.</span><span class="sxs-lookup"><span data-stu-id="6b98d-156">Optionally, update the **Access key** and select **Next**.</span></span>

   ![Dialoglodziņš, lai rediģētu un atjauninātu esoša datu avota piekļuves atslēgu](media/edit-access-key.png)

5. <span data-ttu-id="6b98d-158">Ja vēlaties, varat atjaunināt no uzņēmuma atslēgas savienojuma uz resursu vai abonementa bāzes savienojumu.</span><span class="sxs-lookup"><span data-stu-id="6b98d-158">Optionally, you can update from an account key connection to a resource-based or a subscription-based connection.</span></span> <span data-ttu-id="6b98d-159">Papildinformāciju skatiet tēmā [Auditorijas ieskatu savienošana ar Azure Data Lake Storage Gen2 kontu, izmantojot Azure pakalpojuma primāro nosaukumu](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="6b98d-159">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="6b98d-160">Atjauninot savienojumu, nevar mainīt **Konteinera** informāciju.</span><span class="sxs-lookup"><span data-stu-id="6b98d-160">You can't change **Container** information when updating the connection.</span></span>
   > [!div class="mx-imgBorder"]

   > ![Dialoglodziņš, lai ievadītu Azure Data Lake savienojuma informāciju esošā krātuves kontā](media/enter-existing-storage-details.png)

   > [!NOTE]
   > <span data-ttu-id="6b98d-162">Lai varētu izveidot savienojumu ar konteineri vai krātuves kontu, ir nepieciešama viena no tālāk minētajām lomām, lai varētu izveidot savienojumu ar datu avotu:</span><span class="sxs-lookup"><span data-stu-id="6b98d-162">You need one of the following roles either to the container or the storage account referred above to be able to connect to and create a data source:</span></span>
   >  - <span data-ttu-id="6b98d-163">Krātuves Blob datu lasītājs</span><span class="sxs-lookup"><span data-stu-id="6b98d-163">Storage Blob Data Reader</span></span>
   >  - <span data-ttu-id="6b98d-164">Krātuves Blob datu īpašnieks</span><span class="sxs-lookup"><span data-stu-id="6b98d-164">Storage Blob Data Owner</span></span>
   >  - <span data-ttu-id="6b98d-165">Krātuves Blob datu ieguldītājs</span><span class="sxs-lookup"><span data-stu-id="6b98d-165">Storage Blob Data Contributo</span></span>


6. <span data-ttu-id="6b98d-166">Pēc izvēles izvēlieties citu model.json vai manifest.json failu ar citu entītiju kopu no konteinera.</span><span class="sxs-lookup"><span data-stu-id="6b98d-166">Optionally, choose a different model.json or manifest.json file with a different set of entities from the container.</span></span>

7. <span data-ttu-id="6b98d-167">Ja vēlaties, varat atlasīt papildu entītijas, ko iegūt.</span><span class="sxs-lookup"><span data-stu-id="6b98d-167">Optionally, you can select additional entities to ingest.</span></span> <span data-ttu-id="6b98d-168">Ja nav atkarību, varat noņemt arī jau atlasītās entītijas.</span><span class="sxs-lookup"><span data-stu-id="6b98d-168">You can also remove any already selected entities if there are no dependencies.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="6b98d-169">Ja esošajā model.json vai manifest.json failā un entītiju kopā ir atkarības, tiks parādīts kļūdas ziņojums un nevarēs atlasīt citu model.json vai manifest.json failu.</span><span class="sxs-lookup"><span data-stu-id="6b98d-169">If there are dependencies on the existing model.json or manifest.json file and the set of entities, you'll see an error message and can't select a different model.json or manifest.json file.</span></span> <span data-ttu-id="6b98d-170">Pirms maināt model.json vai manifest.json failu, noņemiet šīs atkarības vai izveidojiet jaunu datu avotu ar model.json vai manifest.json failu, kuru vēlaties izmantot, lai izvairītos no atkarību noņemšanas.</span><span class="sxs-lookup"><span data-stu-id="6b98d-170">Remove those dependencies before changing the model.json or manifest.json file or create a new data source with the model.json or manifest.json file that you want to use to avoid removing the dependencies.</span></span>

8. <span data-ttu-id="6b98d-171">Ja vēlaties, varat atlasīt papildu atribūtus vai entītijas, lai iespējotu datu profilēšanu vai atspējotu jau atlasītos.</span><span class="sxs-lookup"><span data-stu-id="6b98d-171">Optionally, you can select additional attributes or entities to enable data profiling on or disable already selected ones.</span></span>   


[!INCLUDE[footer-include](../includes/footer-banner.md)]