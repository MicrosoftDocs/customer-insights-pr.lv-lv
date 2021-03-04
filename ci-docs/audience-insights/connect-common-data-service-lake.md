---
title: Savienojuma izveide ar entītijām Common Data Service pārvaldītajā ezerā
description: Datu importēšana no Common Data Service pārvaldītā datu ezera.
ms.date: 09/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.reviewer: adkuppa
ms.openlocfilehash: 18b6cd3fdaf5b738877a73b520b91dbc6ded40de
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267823"
---
# <a name="connect-to-data-in-a-common-data-service-managed-data-lake"></a><span data-ttu-id="43c46-103">Savienojuma izveide ar datiem Common Data Service pārvaldītā datu ezerā</span><span class="sxs-lookup"><span data-stu-id="43c46-103">Connect to data in a Common Data Service managed data lake</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="43c46-104">Šajā rakstā sniegta informācija, kā esošie Dynamics 365 klienti var ātri pieslēgties analītiskajām entitījām Common Data Service pārvaldītā ezerā.</span><span class="sxs-lookup"><span data-stu-id="43c46-104">This article provides information on how existing Dynamics 365 customers can quickly connect to their analytical entities in the Common Data Service managed lake.</span></span> <span data-ttu-id="43c46-105">Lai turpinātu un skatītu pārvaldītajā ezerā pieejamo entītiju sarakstu, ir jābūt Common Data Service organizācijas administratoram.</span><span class="sxs-lookup"><span data-stu-id="43c46-105">You must be an admin on the Common Data Service organization to proceed and see the list of entities available in the managed lake.</span></span>

## <a name="important-considerations"></a><span data-ttu-id="43c46-106">Svarīgi ieteikumi</span><span class="sxs-lookup"><span data-stu-id="43c46-106">Important considerations</span></span>

<span data-ttu-id="43c46-107">Dati, kas tiek glabāti tiešsaistes pakalpojumos, piemēram, Azure Data Lake Storage, var tikt glabāti citā atrašanās vietā, nevis tajā, kur dati tiek apstrādāti vai glabāti programmā Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="43c46-107">Data stored in online services, such as Azure Data Lake Storage, may be stored in a different location than where data is processed or stored in Dynamics 365 Customer Insights.</span></span><span data-ttu-id="43c46-108"> Importējot vai savienojot ar tiešsaistes pakalpojumos glabātajiem datiem, jūs piekrītat, ka datus var pārnest uz Dynamics 365 Customer Insights un glabāt tajā. [Papildinformāciju skatiet Microsoft drošības kontroles centrā.](https://www.microsoft.com/trust-center)</span><span class="sxs-lookup"><span data-stu-id="43c46-108"> By importing or connecting to data stored in online services, you agree that data can be transferred to and stored with Dynamics 365 Customer Insights. [Learn more at the Microsoft Trust Center.](https://www.microsoft.com/trust-center)</span></span>

## <a name="connect-to-a-common-data-service-managed-lake"></a><span data-ttu-id="43c46-109">Savienojuma izveide ar Common Data Service pārvaldīto datu ezeru</span><span class="sxs-lookup"><span data-stu-id="43c46-109">Connect to a Common Data Service managed lake</span></span>

1. <span data-ttu-id="43c46-110">Sadaļā Auditorijas ieskati skatiet **Dati** > **Datu avoti**.</span><span class="sxs-lookup"><span data-stu-id="43c46-110">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="43c46-111">Atlasiet **Pievienot datu avotu**.</span><span class="sxs-lookup"><span data-stu-id="43c46-111">Select **Add data source**.</span></span>

3. <span data-ttu-id="43c46-112">Atlasiet opciju **Izveidot savienojumu ar Common Data Service** un atlasiet **Tālāk**.</span><span class="sxs-lookup"><span data-stu-id="43c46-112">Select **Connect to Common Data Service** and select **Next**.</span></span>

4. <span data-ttu-id="43c46-113">Ievadiet **Nosaukumu** datu avotam un atlasiet **Tālāk**.</span><span class="sxs-lookup"><span data-stu-id="43c46-113">Enter a **Name** for the data source and select **Next**.</span></span> <span data-ttu-id="43c46-114">Nosaukuma vadlīnijas:</span><span class="sxs-lookup"><span data-stu-id="43c46-114">Name guidelines:</span></span> 
   - <span data-ttu-id="43c46-115">Sāciet ar burtu.</span><span class="sxs-lookup"><span data-stu-id="43c46-115">Start with a letter.</span></span>
   - <span data-ttu-id="43c46-116">Izmantojiet tikai burtus un ciparus.</span><span class="sxs-lookup"><span data-stu-id="43c46-116">Use letters and numbers only.</span></span> <span data-ttu-id="43c46-117">Speciālās rakstzīmes un atstarpes nav atļautas.</span><span class="sxs-lookup"><span data-stu-id="43c46-117">Special characters and spaces are not allowed.</span></span>
   - <span data-ttu-id="43c46-118">Izmantojiet no 3 līdz 64 rakstzīmēm.</span><span class="sxs-lookup"><span data-stu-id="43c46-118">Use between 3 and 64 characters.</span></span>

5. <span data-ttu-id="43c46-119">Norādiet **Servera adrese** jūsu Common Data Service organizācijai un atlasiet **Pierakstīties**.</span><span class="sxs-lookup"><span data-stu-id="43c46-119">Provide the **Server address** for your Common Data Service organization, and select **Sign in**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="43c46-120">![Dialoglodziņš, lai ievadītu Common Data Service servera adresi](media/enter-CDS-org-details.png)</span><span class="sxs-lookup"><span data-stu-id="43c46-120">![Dialog box to enter Common Data Service server address](media/enter-CDS-org-details.png)</span></span>

6. <span data-ttu-id="43c46-121">Atlasiet entītijas, ko vēlaties iegūt no pieejamo saraksta.</span><span class="sxs-lookup"><span data-stu-id="43c46-121">Select the entities you want to ingest from the available list.</span></span>    

   > [!NOTE]
   > <span data-ttu-id="43c46-122">Ja dažas entītijas jau ir atlasītas, iespējams, tās izmanto citas Dynamics 365 lietojumprogrammas (piemēram, Dynamics 365 Sales Insights vai Customer Service Insights).</span><span class="sxs-lookup"><span data-stu-id="43c46-122">If some entities are already selected, they might be used by other Dynamics 365 applications (such as Dynamics 365 Sales Insights or Customer Service Insights).</span></span> <span data-ttu-id="43c46-123">Atlasi nevar mainīt.</span><span class="sxs-lookup"><span data-stu-id="43c46-123">You can't change the selection.</span></span> <span data-ttu-id="43c46-124">Šīs entītijas būs pieejamas, kolīdz tiks izveidots datu avots.</span><span class="sxs-lookup"><span data-stu-id="43c46-124">These entities will be available once the data source is created.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="43c46-125">![Dialoglodziņš, kurā redzams entītiju saraksts Common Data Service organizācijā](media/select-analytical-entities.png)</span><span class="sxs-lookup"><span data-stu-id="43c46-125">![Dialog box showing a list of entities in the Common Data Service org](media/select-analytical-entities.png)</span></span>

7. <span data-ttu-id="43c46-126">Saglabājiet atlasi, lai sāktu atlasīto entītiju sinhronizēšanu ar Common Data Service pārvaldīto datu ezeru.</span><span class="sxs-lookup"><span data-stu-id="43c46-126">Save your selection to start syncing the selected entities to the Common Data Service managed lake.</span></span> <span data-ttu-id="43c46-127">Tikko izveidotais savienojums ir atrodams lapā **Datu avoti**.</span><span class="sxs-lookup"><span data-stu-id="43c46-127">You'll find the newly added connection on the **Data sources** page.</span></span> <span data-ttu-id="43c46-128">Tas tiks ievietots rindā atsvaidzināšanai un rādīs entītiju skaitu kā 0, līdz visas entītijas būs sinhronizētas.</span><span class="sxs-lookup"><span data-stu-id="43c46-128">It will be queued for refresh and show the entities count as 0 until all the entities are synced.</span></span>

<span data-ttu-id="43c46-129">Tikai vienas vides datu avots var vienlaikus izmantot to pašu Common Data Service pārvaldīto ezeru.</span><span class="sxs-lookup"><span data-stu-id="43c46-129">Only one data source of an environment can simultaneously use the same Common Data Service managed lake.</span></span>

## <a name="edit-a-common-data-service-managed-lake-data-source"></a><span data-ttu-id="43c46-130">Common Data Service pārvaldītā datu ezera datu avota rediģēšana</span><span class="sxs-lookup"><span data-stu-id="43c46-130">Edit a Common Data Service managed lake data source</span></span>

<span data-ttu-id="43c46-131">Entītijas atlasi var rediģēt tikai pēc datu avota izveides.</span><span class="sxs-lookup"><span data-stu-id="43c46-131">You only edit the entity selection after creating the data source.</span></span> <span data-ttu-id="43c46-132">Piemēram, ja Common Data Service tika pievienotas papildu entītijas un jūs vēlaties importēt arī tās.</span><span class="sxs-lookup"><span data-stu-id="43c46-132">For example, if additional entities were added to Common Data Service and you want to import them too.</span></span>    
<span data-ttu-id="43c46-133">Lai izveidotu savienojumu ar citu Common Data Service, [izveidojiet jaunu datu avotu](#connect-to-a-common-data-service-managed-lake).</span><span class="sxs-lookup"><span data-stu-id="43c46-133">To connect to a different Common Data Service, [create a new data source](#connect-to-a-common-data-service-managed-lake).</span></span>

1. <span data-ttu-id="43c46-134">Sadaļā Auditorijas ieskati skatiet **Dati** > **Datu avoti**.</span><span class="sxs-lookup"><span data-stu-id="43c46-134">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="43c46-135">Blakus atjaunināmajam datu avotam atlasiet elipsi.</span><span class="sxs-lookup"><span data-stu-id="43c46-135">Next to the data source you'd like to update, select the ellipsis.</span></span>

3. <span data-ttu-id="43c46-136">No saraksta atlasiet opciju **Rediģēt**.</span><span class="sxs-lookup"><span data-stu-id="43c46-136">Select the **Edit** option from the list.</span></span>

4. <span data-ttu-id="43c46-137">Pieejamo entītiju sarakstā atlasiet papildu entītijas un atlasiet **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="43c46-137">Select additional entities from the available list of entities and select **Save**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]