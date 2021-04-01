---
title: Kartēt entītijas datu apvienošanai
description: Kartējiet datus, lai izveidotu vienotus klientu profilus.
ms.date: 09/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 36b7f7b2fac9497245cf6759506c53753972f173
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596002"
---
# <a name="map-entities-and-attributes"></a><span data-ttu-id="e19b0-103">Kartējiet entītijas un atribūtus</span><span class="sxs-lookup"><span data-stu-id="e19b0-103">Map entities and attributes</span></span>

<span data-ttu-id="e19b0-104">**Karte** ir pirmais posms auditorijas ieskatu datu apvienošanas procesā.</span><span class="sxs-lookup"><span data-stu-id="e19b0-104">**Map** is the first stage in the data unification process of audience insights.</span></span> <span data-ttu-id="e19b0-105">Kartēšana sastāv no trim posmiem:</span><span class="sxs-lookup"><span data-stu-id="e19b0-105">Mapping consists of three phases:</span></span>

- <span data-ttu-id="e19b0-106">*Entītijas atlase*: Norādiet savienojamās entītijas, kas aizved pie datu kopas ar pilnīgāku informāciju par jūsu klientiem.</span><span class="sxs-lookup"><span data-stu-id="e19b0-106">*Entity selection*: Identify the combinable entities that lead to a dataset with more complete information about your customers.</span></span>
- <span data-ttu-id="e19b0-107">*Atribūtu atlase*: katrai entītijai norādiet kolonnas, ko vēlaties kombinēt un saskaņot *atbilstības noteikšanas* un *sapludināšanas* posmos.</span><span class="sxs-lookup"><span data-stu-id="e19b0-107">*Attribute selection*: For each entity, identify the columns you want to combine and reconcile in the *match* and *merge* phases.</span></span> <span data-ttu-id="e19b0-108">Šīs kolonnas sauc par *Atribūtiem*.</span><span class="sxs-lookup"><span data-stu-id="e19b0-108">These columns are called *Attributes*.</span></span>
- <span data-ttu-id="e19b0-109">*Primārā atslēga un semantiskā tipa atlase*: Katrai entītijai norādiet atribūtu, ko vēlaties definēt kā šīs entītijas primāro atslēgu, un katram atribūtam norādiet semantisko tipu, kas vislabāk raksturo šo atribūtu.</span><span class="sxs-lookup"><span data-stu-id="e19b0-109">*Primary key and semantic type selection*: For each entity, identify an attribute you want to define as the primary key for that entity, and for each attribute, identify a semantic type that best describes that attribute.</span></span>

<span data-ttu-id="e19b0-110">Papildinformāciju par datu apvienošanās vispārīgo plūsmu skatiet rakstā [Apvienošana](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="e19b0-110">For more information about the general flow of data unification, see [Unify](data-unification.md).</span></span>

## <a name="select-the-first-entities"></a><span data-ttu-id="e19b0-111">Pirmo entītiju atlase</span><span class="sxs-lookup"><span data-stu-id="e19b0-111">Select the first entities</span></span>

1. <span data-ttu-id="e19b0-112">Sadaļā Auditorijas ieskati ejiet uz **Dati** > **Apvienot** > **Kartēt**.</span><span class="sxs-lookup"><span data-stu-id="e19b0-112">In audience insights, go to **Data** > **Unify** > **Map**.</span></span>

2. <span data-ttu-id="e19b0-113">Sāciet kartēšanas posmu, atlasot **Atlasīt entītijas**.</span><span class="sxs-lookup"><span data-stu-id="e19b0-113">Start the map phase by selecting **Select entities**.</span></span>

3. <span data-ttu-id="e19b0-114">Atlasiet entītijas un atribūtus, ko vēlaties izmantot posmos *saskaņot* un *sapludināt*.</span><span class="sxs-lookup"><span data-stu-id="e19b0-114">Select the entities and attributes you want to use in the *match* and *merge* phases.</span></span> <span data-ttu-id="e19b0-115">No entītijas varat atlasīt nepieciešamos atribūtus pa vienam vai iekļaut visus, entītijas līmenī atlasot izvēles rūtiņu **Iekļaut visus laukus**.</span><span class="sxs-lookup"><span data-stu-id="e19b0-115">You can select the required attributes individually from an entity or include all attributes from an entity by selecting the **Include all fields** checkbox on the entity level.</span></span> <span data-ttu-id="e19b0-116">Lai gūtu labumu no datu apvienošanas procesa, ieteicams atlasīt vismaz divas entītijas.</span><span class="sxs-lookup"><span data-stu-id="e19b0-116">We recommend selecting at least two entities to benefit from the data unification process.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e19b0-117">![Entītiju pievienošanas piemērs](media/data-manager-configure-map-add-entities-example.png "Entītiju pievienošanas piemērs")</span><span class="sxs-lookup"><span data-stu-id="e19b0-117">![Add entities example](media/data-manager-configure-map-add-entities-example.png "Add entities example")</span></span>

   <span data-ttu-id="e19b0-118">Šajā piemērā mēs pievienojam entītijas **eCommerceContacts** un **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="e19b0-118">In this example, we're adding the **eCommerceContacts** and **loyCustomers** entities.</span></span> <span data-ttu-id="e19b0-119">Izvēloties šīs entītijas, varat gūt ieskatu par to, kuri tiešsaistes biznesa klienti ir lojalitātes programmas dalībnieki.</span><span class="sxs-lookup"><span data-stu-id="e19b0-119">By choosing these entities, you can derive insights on which of the online business customers are loyalty program members.</span></span>
   
   <span data-ttu-id="e19b0-120">Visos atribūtos un entītijās varat meklēt atslēgvārdus, lai atlasītu nepieciešamos atribūtus, ko vēlaties kartēt.</span><span class="sxs-lookup"><span data-stu-id="e19b0-120">You can search on keywords across all attributes and entities to select the required attributes you want to map.</span></span>
   
     > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e19b0-121">![Meklēšanas lauku piemērs](media/data-manager-configure-map-search-fields-example.png "Meklēšanas lauku piemērs")</span><span class="sxs-lookup"><span data-stu-id="e19b0-121">![Search fields example](media/data-manager-configure-map-search-fields-example.png "Search fields example")</span></span>

4. <span data-ttu-id="e19b0-122">Atlasiet **Lietot**, lai apstiprinātu atlasi.</span><span class="sxs-lookup"><span data-stu-id="e19b0-122">Select **Apply** to confirm your selections.</span></span>

## <a name="select-primary-key-and-semantic-type-for-attributes"></a><span data-ttu-id="e19b0-123">Atribūtu primārās atslēgas un semantiskā tipa atlasīšana</span><span class="sxs-lookup"><span data-stu-id="e19b0-123">Select primary key and semantic type for attributes</span></span>

<span data-ttu-id="e19b0-124">Pēc entītiju atlasīšanas lapā **Kartēšana** pārbaudei ir uzskaitītas atlasītās entītijas.</span><span class="sxs-lookup"><span data-stu-id="e19b0-124">After selecting your entities, the **Map** page lists the selected entities for your review.</span></span> <span data-ttu-id="e19b0-125">Definējiet entītijas primāro atslēgu un nosakiet entītijas atribūta semantisko tipu.</span><span class="sxs-lookup"><span data-stu-id="e19b0-125">Define the primary key for an entity and identify the semantic type for an attribute in the entity.</span></span>

- <span data-ttu-id="e19b0-126">**Primārā atslēga**: atlasiet vienu atribūtu kā primāro atslēgu katrai entītijai.</span><span class="sxs-lookup"><span data-stu-id="e19b0-126">**Primary key**: Select one attribute as a primary key for each of your entities.</span></span> <span data-ttu-id="e19b0-127">Lai atribūts būtu derīga primārā atslēga, tajā nedrīkst ietvert vērtību dublikātus, trūkstošās vērtības vai nulles vērtības.</span><span class="sxs-lookup"><span data-stu-id="e19b0-127">For an attribute to be a valid primary key, it shouldn't include duplicate values, missing values, or null values.</span></span> <span data-ttu-id="e19b0-128">Virknes, vesela skaitļa un GUID datu tipu atribūti tiek atbalstīti kā primārās atslēgas un tiks parādīti laukā, no kura iespējams veikt atlasi.</span><span class="sxs-lookup"><span data-stu-id="e19b0-128">String, integer, and GUID data type attributes are supported as primary keys and will be displayed in a field for you to select from.</span></span>

- <span data-ttu-id="e19b0-129">**Atribūta semantiskais tips**: Jūsu atribūtu kategorijas, piemēram, e-pasta adrese vai nosaukums.</span><span class="sxs-lookup"><span data-stu-id="e19b0-129">**Attribute semantic type**: Categories of your attributes, such as email address or name.</span></span> <span data-ttu-id="e19b0-130">Lai semantikas viedajai prognozēšanai izmantotu mākslīgā intelekta modeļus, ietaupītu laiku un uzlabotu precizitāti, iestatiet **Inteliģento kartēšanu** uz pozīciju **ON**.</span><span class="sxs-lookup"><span data-stu-id="e19b0-130">To use AI models for smart prediction of semantics, save time and improve accuracy, set **Intelligent mapping** to **ON**.</span></span> <span data-ttu-id="e19b0-131">Inteliģentā kartēšana izceļ mākslīgā intelekta semantikas ieteikumu laukā **Veids**.</span><span class="sxs-lookup"><span data-stu-id="e19b0-131">Intelligent mapping highlights AI-based semantics recommendation in the **Type** field.</span></span> <span data-ttu-id="e19b0-132">Ja to iestatāt uz pozīciju **OFF**, jūs redzēsit regulāros kartēšanas ieteikumus.</span><span class="sxs-lookup"><span data-stu-id="e19b0-132">If you set it to **OFF**, you will see our regular mapping recommendations.</span></span> <span data-ttu-id="e19b0-133">No pieejamā opciju saraksta varat atlasīt jebkuru semantisko veidu un pārlabot esošo atlasi.</span><span class="sxs-lookup"><span data-stu-id="e19b0-133">You can select any semantic type from the available list of options and override the suggested selection.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="e19b0-134">![Atribūta veids un semantiskā prognoze](media/data-manager-configure-map-add-attributes-semantic-prediction.png "Atribūta veids un semantiskā prognoze")</span><span class="sxs-lookup"><span data-stu-id="e19b0-134">![Attribute type and semantic prediction](media/data-manager-configure-map-add-attributes-semantic-prediction.png "Attribute type and semantic prediction")</span></span>

<span data-ttu-id="e19b0-135">Ir iespējams pievienot arī pielāgotu semantisko tipu.</span><span class="sxs-lookup"><span data-stu-id="e19b0-135">Adding a custom semantic type is also possible.</span></span> <span data-ttu-id="e19b0-136">Atlasiet atribūta lauka tipu un ierakstiet pielāgotā semantiskā atribūta tipa nosaukumu.</span><span class="sxs-lookup"><span data-stu-id="e19b0-136">Select the type field for an attribute, and type your custom semantic type name.</span></span> <span data-ttu-id="e19b0-137">Tādējādi varat arī mainīt sistēmas noteiktos atribūtu tipus.</span><span class="sxs-lookup"><span data-stu-id="e19b0-137">This way, you can also change the attribute types that were identified by the system.</span></span>

<span data-ttu-id="e19b0-138">Visi atribūti, kam automātiski tiek noteikts semantiskais tips, tiek grupēti sadaļā **Pārbaudīt kartētos laukus**.</span><span class="sxs-lookup"><span data-stu-id="e19b0-138">All attributes for which a semantic type is automatically identified are grouped in the **Review mapped fields** section.</span></span> <span data-ttu-id="e19b0-139">Pārbaudiet šos atribūtus un to semantiskos tipus, jo tie tiks izmantoti, lai apvienotu jūsu entītijas datu apvienošanas sapludināšanas darbībā.</span><span class="sxs-lookup"><span data-stu-id="e19b0-139">Review these attributes and their semantic types because they'll be used to combine your entities in the merge step of data unification.</span></span>

<span data-ttu-id="e19b0-140">Atribūti, kas netiek automātiski kartēti uz semantisko tipu, tiek grupēti sadaļā **Definēt datus nekartētajos laukos**.</span><span class="sxs-lookup"><span data-stu-id="e19b0-140">Attributes that aren't automatically mapped to a semantic type are grouped in the **Define the data in the unmapped fields** section.</span></span> <span data-ttu-id="e19b0-141">Atlasiet nekartēto atribūtu semantisko tipu lauku vai ievadiet savu pielāgoto atribūta tipa nosaukumu.</span><span class="sxs-lookup"><span data-stu-id="e19b0-141">Select the semantic type field for the unmapped attributes, or enter your custom attribute-type name.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="e19b0-142">![Primārā atslēga un atribūta tips](media/data-manager-configure-map-add-attributes.png "Primārā atslēga un atribūta tips")</span><span class="sxs-lookup"><span data-stu-id="e19b0-142">![Primary key and attribute type](media/data-manager-configure-map-add-attributes.png "Primary key and attribute type")</span></span>

> [!NOTE]
> <span data-ttu-id="e19b0-143">Viens lauks ir jākartē uz semantisko tipu Person.FullName, lai klienta kartē aizpildītu klienta vārdu.</span><span class="sxs-lookup"><span data-stu-id="e19b0-143">One field should map to the semantic type Person.FullName to populate the customer name in customer card.</span></span> <span data-ttu-id="e19b0-144">Pretējā gadījumā klientu kartes tiks rādītas kā anonīmas.</span><span class="sxs-lookup"><span data-stu-id="e19b0-144">Otherwise, the customer cards will appear nameless.</span></span> 

## <a name="add-and-remove-attributes-and-entities"></a><span data-ttu-id="e19b0-145">Atribūtu un entītiju pievienošana un noņemšana</span><span class="sxs-lookup"><span data-stu-id="e19b0-145">Add and remove attributes and entities</span></span>

1. <span data-ttu-id="e19b0-146">Sadaļā **Apvienot** > **Kartēšana**, atlasiet **Rediģēt laukus**.</span><span class="sxs-lookup"><span data-stu-id="e19b0-146">On **Unify** > **Map**, select **Edit fields**.</span></span>

2. <span data-ttu-id="e19b0-147">Rūtī **Rediģēt laukus** pievienojiet vai noņemiet atribūtus un entītijas.</span><span class="sxs-lookup"><span data-stu-id="e19b0-147">In the **Edit fields** pane, add or remove attributes and entities.</span></span> <span data-ttu-id="e19b0-148">Izmantojiet meklēšanu vai ritiniet, lai atrastu un atlasītu interesējošos atribūtus un entītijas.</span><span class="sxs-lookup"><span data-stu-id="e19b0-148">Use the search or scroll to find and select your attributes and entities of interest.</span></span> <span data-ttu-id="e19b0-149">Nevar noņemt atribūtu vai entītiju, ja tie jau ir saskaņoti.</span><span class="sxs-lookup"><span data-stu-id="e19b0-149">You can't remove an attribute or an entity if they've already been matched.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e19b0-150">![Atribūtu pievienošana vai noņemšana](media/configure-data-map-edit.png "Atribūtu pievienošana vai noņemšana")</span><span class="sxs-lookup"><span data-stu-id="e19b0-150">![Add or remove attributes](media/configure-data-map-edit.png "Add or remove attributes")</span></span>

3. <span data-ttu-id="e19b0-151">Atlasiet vienumu **Piemērot**.</span><span class="sxs-lookup"><span data-stu-id="e19b0-151">Select **Apply**.</span></span>

## <a name="add-images-to-profiles"></a><span data-ttu-id="e19b0-152">Pievienojiet profiliem attēlus</span><span class="sxs-lookup"><span data-stu-id="e19b0-152">Add images to profiles</span></span>

<span data-ttu-id="e19b0-153">Ja entitīja satur vietrāžus URL uz publiski pieejamiem profila attēliem vai logotipiem, varat tos pievienot vienotajam klienta profilam.</span><span class="sxs-lookup"><span data-stu-id="e19b0-153">If an entity contains URLs to publicly available profile images or logos, you can add them to the unified customer profile.</span></span>

<span data-ttu-id="e19b0-154">Atlasiet entitīju un atrodiet lauku, kas satur vietrādi URL uz profila attēlu.</span><span class="sxs-lookup"><span data-stu-id="e19b0-154">Select the entity and find the field that contains the URL to the profile image.</span></span> <span data-ttu-id="e19b0-155">Ievades laukā **Veids** manuāli ievadiet tālāk norādīto vērtību:</span><span class="sxs-lookup"><span data-stu-id="e19b0-155">In the **Type** input field, manually enter the following value:</span></span> 
- <span data-ttu-id="e19b0-156">Personai: Person.ProfileImage</span><span class="sxs-lookup"><span data-stu-id="e19b0-156">For a person: Person.ProfileImage</span></span>
- <span data-ttu-id="e19b0-157">Organizācijai: Organization.LogoImage</span><span class="sxs-lookup"><span data-stu-id="e19b0-157">For an organization: Organization.LogoImage</span></span>

<span data-ttu-id="e19b0-158">Turpiniet ar apvienošanās darbībām un nodrošiniet, ka darbībā [Sapludināt](merge-entities.md) tiek pievienots arī atribūts, kas satur attēla URL.</span><span class="sxs-lookup"><span data-stu-id="e19b0-158">Continue with the unification steps and ensure the attribute that contains the image URL is also added in the [Merge](merge-entities.md) step.</span></span>

## <a name="set-attributes-for-organizations"></a><span data-ttu-id="e19b0-159">Atribūtu iestatīšana organizācijām</span><span class="sxs-lookup"><span data-stu-id="e19b0-159">Set attributes for organizations</span></span>

<span data-ttu-id="e19b0-160">Organizācijām (priekšskatījums) atribūta tipam ir jābūt kartētam uz “Organization.Name”.</span><span class="sxs-lookup"><span data-stu-id="e19b0-160">For organizations (Preview), the attribute type should be mapped to "Organization.Name"</span></span>
> [!div class="mx-imgBorder"]
> <span data-ttu-id="e19b0-161">![Primārā atslēga un atribūta tips B2B](media/configure-data-map-edit-b2b.png "Primārā atslēga un atribūta tips B2B")</span><span class="sxs-lookup"><span data-stu-id="e19b0-161">![Primary key and attribute type B2B](media/configure-data-map-edit-b2b.png "Primary key and attribute type B2B")</span></span>

## <a name="next-step"></a><span data-ttu-id="e19b0-162">Nākamā darbība</span><span class="sxs-lookup"><span data-stu-id="e19b0-162">Next step</span></span>

<span data-ttu-id="e19b0-163">Datu apvienošanas procesa ietvaros pārejiet uz lapu **Atbilstība**.</span><span class="sxs-lookup"><span data-stu-id="e19b0-163">As part of the data unification process, go to the **Match** page.</span></span> <span data-ttu-id="e19b0-164">Apmeklējiet rakstu [**Atbilstība**](match-entities.md), lai uzzinātu par šo posmu.</span><span class="sxs-lookup"><span data-stu-id="e19b0-164">Visit [**Match**](match-entities.md) to learn about this phase.</span></span>

> [!TIP]
> <span data-ttu-id="e19b0-165">Noskatieties šo videoklipu: [Darba sākšana: vienota klienta profila izveide](https://youtu.be/oBfGEhucAxs).</span><span class="sxs-lookup"><span data-stu-id="e19b0-165">Check out the following video: [Getting Started: Creating a Unified Customer Profile](https://youtu.be/oBfGEhucAxs).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]