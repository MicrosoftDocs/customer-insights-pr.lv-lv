---
title: Attiecību izveide starp entītijām un entītiju ceļiem
description: Vairāku datu avotu entītiju relāciju izveide un pārvaldība.
ms.date: 04/14/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: c25bfcb8e2a8223498dd1a5e8cfb3712a40ab85e
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595221"
---
# <a name="relationships-between-entities"></a><span data-ttu-id="c8464-103">Relācijas starp entītijām</span><span class="sxs-lookup"><span data-stu-id="c8464-103">Relationships between entities</span></span>

<span data-ttu-id="c8464-104">Relācijas palīdz entītijām izveidot savienojumu un ģenerēt datu grafiku, ja entītijām ir kopējs identifikators (ārējā atslēga), uz kuru var atsaukties no vienas entītijas uz citu.</span><span class="sxs-lookup"><span data-stu-id="c8464-104">Relationships help you connect entities and generate a graph of your data when entities share a common identifier (foreign key) that can be referenced from one entity to another.</span></span> <span data-ttu-id="c8464-105">Savienotās entītijas ļauj definēt segmentus un pasākumus, par pamatu izmantojot vairākus datu avotus.</span><span class="sxs-lookup"><span data-stu-id="c8464-105">Connected entities enable you to define segments and measures based on multiple data sources.</span></span>

<span data-ttu-id="c8464-106">Ir divu tipu relācijas:</span><span class="sxs-lookup"><span data-stu-id="c8464-106">There are two types of relationships.</span></span> <span data-ttu-id="c8464-107">Nerediģējamas sistēmas relācijas, kas tiek izveidotas automātiski, un pielāgotas relācijas, kuras veido un iestata lietotāji.</span><span class="sxs-lookup"><span data-stu-id="c8464-107">Non-editable system relationships, which are created automatically, and custom relationships created and configured by users.</span></span>

<span data-ttu-id="c8464-108">Atbilstības un sapludināšanas procesu laikā sistēmas relācijas tiek izveidotas, pamatojoties uz inteliģentu atbilstību.</span><span class="sxs-lookup"><span data-stu-id="c8464-108">During the match and merge processes, system relationships are created behind the scenes based on intelligent matching.</span></span> <span data-ttu-id="c8464-109">Šīs relācijas palīdz saistīt klientu profila ierakstus ar citu atbilstošo entītiju ierakstiem.</span><span class="sxs-lookup"><span data-stu-id="c8464-109">These relationships help relate the Customer Profile records with other corresponding entities' records.</span></span> <span data-ttu-id="c8464-110">Šajā shēmā ir parādīta trīs sistēmu relāciju izveide, kad klienta entītija tiek saskaņota ar papildu entītijām, lai izveidotu galīgo klienta profila entītiju.</span><span class="sxs-lookup"><span data-stu-id="c8464-110">The following diagram illustrates the creation of three system relationships when the customer entity is matched with additional entities to produce the final Customer Profile entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c8464-111">![Relāciju izveide](media/relationships-entities-merge.png "Relāciju izveide")</span><span class="sxs-lookup"><span data-stu-id="c8464-111">![Relationship creation](media/relationships-entities-merge.png "Relationship creation")</span></span>

- <span data-ttu-id="c8464-112">Starp Klienta entītiju un Kontaktpersonas entītiju ir izveidota ***CustomerToContact* relācija**.</span><span class="sxs-lookup"><span data-stu-id="c8464-112">***CustomerToContact* relationship** was created between the Customer entity and the Contact entity.</span></span> <span data-ttu-id="c8464-113">Klienta entītija iegūst atslēgas lauku **Contact_contactId**, lai to saistītu ar kontaktpersonas entītijas atslēgas lauku **contactId**.</span><span class="sxs-lookup"><span data-stu-id="c8464-113">The Customer entity gets the key field **Contact_contactId** to relate to the Contact entity key field **contactId**.</span></span>
- <span data-ttu-id="c8464-114">Starp Klienta entītiju un Uzņēmuma entītiju ir izveidota ***CustomerToAccount* relācija**.</span><span class="sxs-lookup"><span data-stu-id="c8464-114">***CustomerToAccount* relationship** was created between the Customer entity and the Account entity.</span></span> <span data-ttu-id="c8464-115">Klienta entītija iegūst atslēgas lauku **Account_contactId**, lai to saistītu ar Uzņēmuma entītijas atslēgas lauku **accountId**.</span><span class="sxs-lookup"><span data-stu-id="c8464-115">The Customer entity gets the key field **Account_accountId** to relate to the Account entity key field **accountId**.</span></span>
- <span data-ttu-id="c8464-116">Starp Klienta entītiju un WebAccount entītiju ir izveidota ***CustomerToWebAccount* relācija**.</span><span class="sxs-lookup"><span data-stu-id="c8464-116">***CustomerToWebAccount* relationship** was created between the Customer entity and the WebAccount entity.</span></span> <span data-ttu-id="c8464-117">Klienta entītija iegūst atslēgas lauku **WebAccount_webaccountId**, lai to saistītu ar WebAccount entītijas atslēgas lauku **webaccountId**.</span><span class="sxs-lookup"><span data-stu-id="c8464-117">The Customer entity gets the key field **WebAccount_webaccountId** to relate to the WebAccount entity key field **webaccountId**.</span></span>

## <a name="create-a-relationship"></a><span data-ttu-id="c8464-118">Relācijas izveide</span><span class="sxs-lookup"><span data-stu-id="c8464-118">Create a relationship</span></span>

<span data-ttu-id="c8464-119">Lapā **Relācijas** definējiet pielāgotas relācijas.</span><span class="sxs-lookup"><span data-stu-id="c8464-119">Define custom relationships on the **Relationships** page.</span></span> <span data-ttu-id="c8464-120">Katra relācija sastāv no avota entītijas (entītijas, kas glabā ārējo atslēgu) un mērķa entītijas (entītija, uz kuru norāda avota entītijas ārējā atslēga).</span><span class="sxs-lookup"><span data-stu-id="c8464-120">Each relationship consists of a Source entity (the entity that holds the foreign key) and a Target entity (the entity that the source entity's foreign key points to).</span></span>

1. <span data-ttu-id="c8464-121">Sadaļā Auditorijas ieskati ejiet uz **Dati** > **Relācijas**.</span><span class="sxs-lookup"><span data-stu-id="c8464-121">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="c8464-122">Atlasiet **Jauna relācija**.</span><span class="sxs-lookup"><span data-stu-id="c8464-122">Select **New relationship**.</span></span>

3. <span data-ttu-id="c8464-123">Rūtī **Jauna relācija** norādiet šādu informāciju:</span><span class="sxs-lookup"><span data-stu-id="c8464-123">In the **Add relationship** pane, provide the following information:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c8464-124">![Ievadiet relācijas informāciju](media/relationships-add.png "Ievadiet relācijas informāciju")</span><span class="sxs-lookup"><span data-stu-id="c8464-124">![Enter relationship details](media/relationships-add.png "Enter relationship details")</span></span>

   - <span data-ttu-id="c8464-125">**Relācijas nosaukums**: nosaukums, kas atspoguļo relāciju mērķi (piemēram, **AccountWebLogs**).</span><span class="sxs-lookup"><span data-stu-id="c8464-125">**Relationship name**: Name that reflects the purpose of the relationship (for example, **AccountWebLogs**).</span></span>
   - <span data-ttu-id="c8464-126">**Apraksts**: Relācijas apraksts.</span><span class="sxs-lookup"><span data-stu-id="c8464-126">**Description**: Description of the relationship.</span></span>
   - <span data-ttu-id="c8464-127">**Avota entītija**: Atlasiet entītiju, kas tiek izmantota kā relāciju avots (piemēram, WebLog).</span><span class="sxs-lookup"><span data-stu-id="c8464-127">**Source entity**: Select the entity that is used as a source in the relationship (for example, WebLog).</span></span>
   - <span data-ttu-id="c8464-128">**Kardinalitāte**: Atlasiet avota entītijas ierakstu kardinalitāti.</span><span class="sxs-lookup"><span data-stu-id="c8464-128">**Cardinality**: Select the cardinality of the source entity records.</span></span> <span data-ttu-id="c8464-129">Piemēram, "daudzi" nozīmē, ka vairāki Weblog ieraksti ir saistīti ar vienu WebAccount.</span><span class="sxs-lookup"><span data-stu-id="c8464-129">For example, "many" means that multiple Weblog records are related to one WebAccount.</span></span>
   - <span data-ttu-id="c8464-130">**Avota atslēgas lauks**: Tas norāda uz avota entītijas ārējās atslēgas lauku.</span><span class="sxs-lookup"><span data-stu-id="c8464-130">**Source key field**: This represents the foreign key field in the source entity.</span></span> <span data-ttu-id="c8464-131">Piemēram, WebLog ir **accountId** ārējās atslēgas lauks.</span><span class="sxs-lookup"><span data-stu-id="c8464-131">For example, WebLog has the **accountId** foreign key field.</span></span>
   - <span data-ttu-id="c8464-132">**Mērķa entītija**: Atlasiet entītiju, kas tiek izmantota kā relāciju mērķis (piemēram, WebAccount).</span><span class="sxs-lookup"><span data-stu-id="c8464-132">**Target entity**: Select the entity that is used as a target in the relationship (for example, WebAccount).</span></span>
   - <span data-ttu-id="c8464-133">**Mērķa kardinalitāte**: Atlasiet mērķa entītijas ierakstu kardinalitāti.</span><span class="sxs-lookup"><span data-stu-id="c8464-133">**Target cardinality**: Select the cardinality of the target entity records.</span></span> <span data-ttu-id="c8464-134">Piemēram, "viens" nozīmē, ka vairāki Weblog ieraksti ir saistīti ar vienu WebAccount.</span><span class="sxs-lookup"><span data-stu-id="c8464-134">For example, "one" means that multiple Weblog records are related to one WebAccount.</span></span>
   - <span data-ttu-id="c8464-135">**Mērķa atslēgas lauks**: Šis lauks norāda mērķa entītijas atslēgas lauku.</span><span class="sxs-lookup"><span data-stu-id="c8464-135">**Target key field**: This field represents the key field of target entity.</span></span> <span data-ttu-id="c8464-136">Piemēram, WebAccount ir **accountId** ārējās atslēgas lauks.</span><span class="sxs-lookup"><span data-stu-id="c8464-136">For example, WebAccount has the **accountId** key field.</span></span>

> [!NOTE]
> <span data-ttu-id="c8464-137">Tiek atbalstītas tikai “daudzas pret vienu” un “viena pret vienu” relācijas.</span><span class="sxs-lookup"><span data-stu-id="c8464-137">Only many-to-one and one-to-one relationships are supported.</span></span> <span data-ttu-id="c8464-138">Relācijas “daudzas pret daudzām” var izveidot, izmantojot divas “daudzas pret vienu” relācijas un saišu entītiju (entītiju, kas tiek izmantota, lai savienotu avota entītiju un mērķa entītiju).</span><span class="sxs-lookup"><span data-stu-id="c8464-138">Many-to-many relationships can be created using two many-to-one relationships and a link entity (an entity that is used to connect the source entity and the target entity).</span></span>

## <a name="delete-a-relationship"></a><span data-ttu-id="c8464-139">Dzēst relāciju</span><span class="sxs-lookup"><span data-stu-id="c8464-139">Delete a relationship</span></span>

1. <span data-ttu-id="c8464-140">Sadaļā Auditorijas ieskati ejiet uz **Dati** > **Relācijas**.</span><span class="sxs-lookup"><span data-stu-id="c8464-140">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="c8464-141">Atzīmējiet rūtiņas tām relācijām, kuras vēlaties dzēst.</span><span class="sxs-lookup"><span data-stu-id="c8464-141">Select check boxes for the relationships you want to delete.</span></span>

3. <span data-ttu-id="c8464-142">Atlasiet **Dzēst** tabulas **Relācijas** augšpusē.</span><span class="sxs-lookup"><span data-stu-id="c8464-142">Select **Delete** at the top of the **Relationships** table.</span></span>

4. <span data-ttu-id="c8464-143">Apstipriniet dzēšanu.</span><span class="sxs-lookup"><span data-stu-id="c8464-143">Confirm your deletion.</span></span>

## <a name="next-step"></a><span data-ttu-id="c8464-144">Nākamā darbība</span><span class="sxs-lookup"><span data-stu-id="c8464-144">Next step</span></span>

<span data-ttu-id="c8464-145">Sistēmas un pielāgotas relācijas tiek izmantotas, lai izveidotu segmentus, pamatojoties uz vairākiem datu avotiem, kas vairs nav sadrumstaloti.</span><span class="sxs-lookup"><span data-stu-id="c8464-145">System and custom relationships are used to create segments based on multiple data sources that are no longer siloed.</span></span> <span data-ttu-id="c8464-146">Papildinformāciju skatiet rakstā [Segmenti](segments.md).</span><span class="sxs-lookup"><span data-stu-id="c8464-146">For more information, see [Segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]