---
title: Attiecību izveide starp entītijām un entītiju ceļiem
description: Vairāku datu avotu entītiju relāciju izveide un pārvaldība.
ms.date: 06/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: d5b9566ec88096fec31d8e164a51598159ec26d4
ms.sourcegitcommit: ece48f80a7b470fb33cd36e3096b4f1e9190433a
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 06/03/2021
ms.locfileid: "6171173"
---
# <a name="relationships-between-entities"></a><span data-ttu-id="1a224-103">Relācijas starp entītijām</span><span class="sxs-lookup"><span data-stu-id="1a224-103">Relationships between entities</span></span>

<span data-ttu-id="1a224-104">Attiecības savieno entītijas un definē datu grafiku, kad entītijas koplieto kopēju identifikatoru — ārēju atslēgu.</span><span class="sxs-lookup"><span data-stu-id="1a224-104">Relationships connect entities and define a graph of your data when entities share a common identifier, a foreign key.</span></span> <span data-ttu-id="1a224-105">Šī ārējā atslēga var tikt atsaukties no vienas entītijas uz citu.</span><span class="sxs-lookup"><span data-stu-id="1a224-105">This foreign key can be referenced from one entity to another.</span></span> <span data-ttu-id="1a224-106">Savienotās entītijas ļauj definēt segmentus un pasākumus, par pamatu izmantojot vairākus datu avotus.</span><span class="sxs-lookup"><span data-stu-id="1a224-106">Connected entities enable the definition of segments and measures based on multiple data sources.</span></span>

<span data-ttu-id="1a224-107">Ir trīs attiecību tipi:</span><span class="sxs-lookup"><span data-stu-id="1a224-107">There are three types of relationships:</span></span> 
- <span data-ttu-id="1a224-108">Nerediģējamas sistēmas attiecības, ko sistēma izveidoja kā daļu no datu apvienošanas procesa</span><span class="sxs-lookup"><span data-stu-id="1a224-108">Non-editable system relationships, created by the system as part of the data unification process</span></span>
- <span data-ttu-id="1a224-109">Nerediģējamas mantotas attiecības, kas tiek automātiski izveidotas, ietverot datu avotus</span><span class="sxs-lookup"><span data-stu-id="1a224-109">Non-editable inherited relationships, which are created automatically from ingesting data sources</span></span> 
- <span data-ttu-id="1a224-110">Rediģējamas pielāgotas attiecības, ko izveido un konfigurē lietotāji</span><span class="sxs-lookup"><span data-stu-id="1a224-110">Editable custom relationships, created and configured by users</span></span>

## <a name="non-editable-system-relationships"></a><span data-ttu-id="1a224-111">Nerediģējamas sistēmu attiecības</span><span class="sxs-lookup"><span data-stu-id="1a224-111">Non-editable system relationships</span></span>

<span data-ttu-id="1a224-112">Datu apvienošanas laikā sistēmas attiecības tiek izveidotas automātiski, pamatojoties uz informācijas atbilstību.</span><span class="sxs-lookup"><span data-stu-id="1a224-112">During data unification, system relationships are created automatically based on intelligent matching.</span></span> <span data-ttu-id="1a224-113">Šīs relācijas palīdz saistīt klientu profila ierakstus ar citu atbilstošo entītiju ierakstiem.</span><span class="sxs-lookup"><span data-stu-id="1a224-113">These relationships help relate the customer profile records with corresponding records.</span></span> <span data-ttu-id="1a224-114">Šajā shēmā parādīta trīs sistēmas attiecību izveide.</span><span class="sxs-lookup"><span data-stu-id="1a224-114">The following diagram illustrates the creation of three system-based relationships.</span></span> <span data-ttu-id="1a224-115">Lai izveidotu vienoto *Klienta* entītiju, klienta entītija tiek saskaņoti ar citām entītijām.</span><span class="sxs-lookup"><span data-stu-id="1a224-115">The customer entity is matched with other entities to produce the unified *Customer* entity.</span></span>

:::image type="content" source="media/relationships-entities-merge.png" alt-text="Shēma ar klienta entītijas attiecību ceļiem ar trim 1-n attiecībām.":::

- <span data-ttu-id="1a224-117">Starp *Klienta* entītiju un *Kontaktpersonas* entītiju ir izveidota ***CustomerToContact* relācija**.</span><span class="sxs-lookup"><span data-stu-id="1a224-117">***CustomerToContact* relationship** was created between the *Customer* entity and the *Contact* entity.</span></span> <span data-ttu-id="1a224-118">*Klienta* entītija iegūst atslēgas lauku **Contact_contactID**, lai to saistītu ar *Kontaktpersonas* entītijas atslēgas lauku **contactID**.</span><span class="sxs-lookup"><span data-stu-id="1a224-118">The *Customer* entity gets the key field **Contact_contactID** to relate to the *Contact* entity key field **contactID**.</span></span>
- <span data-ttu-id="1a224-119">Starp *Klienta* entītiju un *Kontaktpersonas* entītiju ir izveidota ***CustomerToContact* relācija**.</span><span class="sxs-lookup"><span data-stu-id="1a224-119">***CustomerToAccount* relationship** was created between the *Customer* entity and the *Account* entity.</span></span> <span data-ttu-id="1a224-120">*Klienta* entītija iegūst atslēgas lauku **Account_accountID**, lai to saistītu ar *Uzņēmuma* entītijas atslēgas lauku **accountID**.</span><span class="sxs-lookup"><span data-stu-id="1a224-120">The *Customer* entity gets the key field **Account_accountID** to relate to the *Account* entity key field **accountID**.</span></span>
- <span data-ttu-id="1a224-121">Starp *Klienta* entītiju un *WebAccount* entītiju ir izveidota ***CustomerToWebAccount* relācija**.</span><span class="sxs-lookup"><span data-stu-id="1a224-121">***CustomerToWebAccount* relationship** was created between the *Customer* entity and the *WebAccount* entity.</span></span> <span data-ttu-id="1a224-122">*Klienta* entītija iegūst atslēgas lauku **WebAccount_webaccountID**, lai to saistītu ar *WebAccount* entītijas atslēgas lauku **webaccountID**.</span><span class="sxs-lookup"><span data-stu-id="1a224-122">The *Customer* entity gets the key field **WebAccount_webaccountID** to relate to the *WebAccount* entity key field **webaccountID**.</span></span>

## <a name="non-editable-inherited-relationships"></a><span data-ttu-id="1a224-123">Nerediģējamas mantojamas attiecības</span><span class="sxs-lookup"><span data-stu-id="1a224-123">Non-editable inherited relationships</span></span>

<span data-ttu-id="1a224-124">Datu ietveršanas procesa laikā sistēma pārbauda datu avotus esošām attiecībām.</span><span class="sxs-lookup"><span data-stu-id="1a224-124">During the data ingestion process, the system checks data sources for existing relationships.</span></span> <span data-ttu-id="1a224-125">Ja attiecību nav, sistēma tās izveido automātiski.</span><span class="sxs-lookup"><span data-stu-id="1a224-125">If no relationship exists, the system automatically creates them.</span></span> <span data-ttu-id="1a224-126">Šīs attiecības tiek lietotas arī lejupstraumes procesos.</span><span class="sxs-lookup"><span data-stu-id="1a224-126">These relationships are also used in downstream processes.</span></span>

## <a name="create-a-custom-relationship"></a><span data-ttu-id="1a224-127">Izveidot pielāgotu relāciju</span><span class="sxs-lookup"><span data-stu-id="1a224-127">Create a custom relationship</span></span>

<span data-ttu-id="1a224-128">Attiecības sastāv no *avota entītijas*, kurā ir iekļaujošā atslēga un *mērķa entītija*, uz ko norāda avota entītijas nosakošā atslēga.</span><span class="sxs-lookup"><span data-stu-id="1a224-128">Relationship consists of a *source entity* containing the foreign key and a *target entity* that the source entity's foreign key points to.</span></span> 

1. <span data-ttu-id="1a224-129">Sadaļā Auditorijas ieskati ejiet uz **Dati** > **Relācijas**.</span><span class="sxs-lookup"><span data-stu-id="1a224-129">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="1a224-130">Atlasiet **Jauna relācija**.</span><span class="sxs-lookup"><span data-stu-id="1a224-130">Select **New relationship**.</span></span>

3. <span data-ttu-id="1a224-131">Rūtī **Jauna relācija** norādiet šādu informāciju:</span><span class="sxs-lookup"><span data-stu-id="1a224-131">In the **New relationship** pane, provide the following information:</span></span>

   :::image type="content" source="media/relationship-add.png" alt-text="Jauna attiecību sānu rūts ar tukšiem ievades laukiem.":::

   - <span data-ttu-id="1a224-133">**Relāciju nosaukums**: nosaukums, kas atspoguļo attiecību mērķi.</span><span class="sxs-lookup"><span data-stu-id="1a224-133">**Relationship name**: Name that reflects the purpose of the relationship.</span></span> <span data-ttu-id="1a224-134">Piemērs: CustomerToSupportCase.</span><span class="sxs-lookup"><span data-stu-id="1a224-134">Example: CustomerToSupportCase.</span></span>
   - <span data-ttu-id="1a224-135">**Apraksts**: Relācijas apraksts.</span><span class="sxs-lookup"><span data-stu-id="1a224-135">**Description**: Description of the relationship.</span></span>
   - <span data-ttu-id="1a224-136">**Avota entītija**: entītija, kas attiecībās tiek izmantota kā relāciju avots.</span><span class="sxs-lookup"><span data-stu-id="1a224-136">**Source entity**: Entity that is used as a source in the relationship.</span></span> <span data-ttu-id="1a224-137">Piemērs: SupportCase.</span><span class="sxs-lookup"><span data-stu-id="1a224-137">Example: SupportCase.</span></span>
   - <span data-ttu-id="1a224-138">**Mērķa entītija**: entītija, kas attiecībās tiek izmantota kā relāciju mērķis.</span><span class="sxs-lookup"><span data-stu-id="1a224-138">**Target entity**: Entity that is used as a target in the relationship.</span></span> <span data-ttu-id="1a224-139">Piemērs: klients.</span><span class="sxs-lookup"><span data-stu-id="1a224-139">Example: Customer.</span></span>
   - <span data-ttu-id="1a224-140">**Avota kardinalitāte**: norādiet avota entītijas kardinalitāti.</span><span class="sxs-lookup"><span data-stu-id="1a224-140">**Source cardinality**: Specify the cardinality of the source entity.</span></span> <span data-ttu-id="1a224-141">Kardinalitāte apraksta iespējamo elementu skaitu kopā.</span><span class="sxs-lookup"><span data-stu-id="1a224-141">Cardinality describes the number of possible elements in a set.</span></span> <span data-ttu-id="1a224-142">Tā vienmēr ir saistīta ar mērķa kardinalitāti.</span><span class="sxs-lookup"><span data-stu-id="1a224-142">It always relates to the target cardinality.</span></span> <span data-ttu-id="1a224-143">Var izvēlēties starp **vienu** un **vairākiem**.</span><span class="sxs-lookup"><span data-stu-id="1a224-143">You can choose between **One** and **Many**.</span></span> <span data-ttu-id="1a224-144">Tiek atbalstītas tikai “daudzas pret vienu” un “viena pret vienu” relācijas.</span><span class="sxs-lookup"><span data-stu-id="1a224-144">Only many-to-one and one-to-one relationships are supported.</span></span>  
     - <span data-ttu-id="1a224-145">Daudzi pret vienu: vairāki avota ieraksti var būt saistīti ar vienu mērķa ierakstu.</span><span class="sxs-lookup"><span data-stu-id="1a224-145">Many-to-one: Multiple source records can relate to one target record.</span></span> <span data-ttu-id="1a224-146">Piemērs: vairāki atbalsta pieteikumi no viena klienta.</span><span class="sxs-lookup"><span data-stu-id="1a224-146">Example: Multiple support cases from a single customer.</span></span>
     - <span data-ttu-id="1a224-147">Viens pret vienu: viens avota ieraksts ir saistīts ar vienu mērķa ierakstu.</span><span class="sxs-lookup"><span data-stu-id="1a224-147">One-to-one: A single source record relates to a one target record.</span></span> <span data-ttu-id="1a224-148">Piemērs: viens atsevišķa klienta gaidīšanas ID.</span><span class="sxs-lookup"><span data-stu-id="1a224-148">Example: One loyalty ID for a single customer.</span></span>

     > [!NOTE]
     > <span data-ttu-id="1a224-149">Attiecības daudzi pret daudziem var izveidot, izmantojot divas attiecības daudzi pret vienu, un saistot entītiju, kas savieno avota entītiju un mērķa entītiju.</span><span class="sxs-lookup"><span data-stu-id="1a224-149">Many-to-many relationships can be created using two many-to-one relationships and a linking entity, which connects the source entity and the target entity.</span></span>

   - <span data-ttu-id="1a224-150">**Mērķa kardinalitāte**: Atlasiet mērķa entītijas ierakstu kardinalitāti.</span><span class="sxs-lookup"><span data-stu-id="1a224-150">**Target cardinality**: Select the cardinality of the target entity records.</span></span> 
   - <span data-ttu-id="1a224-151">**Avota atslēgas lauks**: avota entītijas avota atslēgas lauks.</span><span class="sxs-lookup"><span data-stu-id="1a224-151">**Source key field**: The foreign key field in the source entity.</span></span> <span data-ttu-id="1a224-152">Piemērs: SupportCase kā noslogotu galveno lauku var izmantot CaseID.</span><span class="sxs-lookup"><span data-stu-id="1a224-152">Example: SupportCase could use CaseID as a foreign key field.</span></span>
   - <span data-ttu-id="1a224-153">**Mērķa atslēgas lauks**: Šis lauks norāda mērķa entītijas atslēgas lauku.</span><span class="sxs-lookup"><span data-stu-id="1a224-153">**Target key field**: The key field of the target entity.</span></span> <span data-ttu-id="1a224-154">Piemēram, klients var izmantot atslēgas lauku **CustomerID**.</span><span class="sxs-lookup"><span data-stu-id="1a224-154">Example Customer could use the **CustomerID** key field.</span></span>

4. <span data-ttu-id="1a224-155">Lai izveidotu pielāgotu relāciju, atlasiet **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="1a224-155">Select **Save** to create the custom relationship.</span></span>

## <a name="view-relationships"></a><span data-ttu-id="1a224-156">Skatīt relācijas</span><span class="sxs-lookup"><span data-stu-id="1a224-156">View relationships</span></span>

<span data-ttu-id="1a224-157">Lapā Attiecības ir uzskaitītas visas izveidotās relācijas.</span><span class="sxs-lookup"><span data-stu-id="1a224-157">The Relationships page lists all the relationships that have been created.</span></span> <span data-ttu-id="1a224-158">Katra rinda ir attiecības, kurās ir iekļauta arī detalizēta informācija par avota entītiju, mērķa entītiju un jucību.</span><span class="sxs-lookup"><span data-stu-id="1a224-158">Each row represents a relationship, which also includes details about the source entity, the target entity, and the cardinality.</span></span> 

:::image type="content" source="media/relationships-list.png" alt-text="Attiecību un opciju saraksts attiecību lapas darbību joslā.":::

<span data-ttu-id="1a224-160">Šajā lapā ir opciju kopa esošām un jaunām attiecībām:</span><span class="sxs-lookup"><span data-stu-id="1a224-160">This page offers a set of options for existing and new relationships:</span></span> 
- <span data-ttu-id="1a224-161">**Jaunas attiecības**: [Izveidot pielāgotas attiecības](#create-a-custom-relationship).</span><span class="sxs-lookup"><span data-stu-id="1a224-161">**New Relationship**: [Create a custom relationship](#create-a-custom-relationship).</span></span>
- <span data-ttu-id="1a224-162">**Visualizētājs**: [izpētiet relāciju vizualizētāju](#explore-the-relationship-visualizer), lai redzētu esošo attiecību tīkla diagrammu un to kardinalitāti.</span><span class="sxs-lookup"><span data-stu-id="1a224-162">**Visualizer**: [Explore the relationship visualizer](#explore-the-relationship-visualizer) to see a network diagram of the existing relationships and their cardinality.</span></span>
- <span data-ttu-id="1a224-163">**Filtrēt pēc**: izvēlieties sarakstā rādīto attiecību tipu.</span><span class="sxs-lookup"><span data-stu-id="1a224-163">**Filter by**: Choose the type of relationships to show in the list.</span></span>
- <span data-ttu-id="1a224-164">**Meklēšanas attiecības**: izmantojiet teksta meklēšanu, kas balstīta uz attiecību rekvizītiem.</span><span class="sxs-lookup"><span data-stu-id="1a224-164">**Search relationships**: Use a text-based search on properties of the relationships.</span></span>

### <a name="explore-the-relationship-visualizer"></a><span data-ttu-id="1a224-165">Izpētīt relāciju visualatoru</span><span class="sxs-lookup"><span data-stu-id="1a224-165">Explore the relationship visualizer</span></span>

<span data-ttu-id="1a224-166">Relāciju vizualizētājs parāda esošo attiecību tīkla diagrammu starp savienotajām entītijām un to kardinalitāti.</span><span class="sxs-lookup"><span data-stu-id="1a224-166">The relationship visualizer shows a network diagram of the existing relationships between connected entities and their cardinality.</span></span>

<span data-ttu-id="1a224-167">Lai pielāgotu skatu, lodziņu atrašanās vietu var mainīt, velkot tos uz pamatnes.</span><span class="sxs-lookup"><span data-stu-id="1a224-167">To customize the view, you can change the position of the boxes by dragging them on the canvas.</span></span>

:::image type="content" source="media/relationship-visualizer.png" alt-text="Relāciju visualizēšanas tīkla shēmas ekrānuzņēmumu ar savienojumiem starp saistītajām entītijām.":::

<span data-ttu-id="1a224-169">Pieejamās opcijas:</span><span class="sxs-lookup"><span data-stu-id="1a224-169">Available options:</span></span> 
- <span data-ttu-id="1a224-170">**Eksportēt kā attēlu**: saglabāt pašreizējo skatu kā attēla failu.</span><span class="sxs-lookup"><span data-stu-id="1a224-170">**Export as image**: Save the current view as an image file.</span></span>
- <span data-ttu-id="1a224-171">**Mainīt uz horizontālo/vertikālo izkārtojumu**: mainiet entītiju un attiecību līdzinājumu.</span><span class="sxs-lookup"><span data-stu-id="1a224-171">**Change to horizontal/vertical layout**: Change the alignment of the entities and relationships.</span></span>
- <span data-ttu-id="1a224-172">**Rediģēšana**: atjauniniet pielāgotu attiecību rekvizītus rediģēšanas rūtī un saglabājiet izmaiņas.</span><span class="sxs-lookup"><span data-stu-id="1a224-172">**Edit**: Update properties of custom relationships in the edit pane and save changes.</span></span>

## <a name="manage-existing-relationships"></a><span data-ttu-id="1a224-173">Pārvaldīt esošās relācijas</span><span class="sxs-lookup"><span data-stu-id="1a224-173">Manage existing relationships</span></span> 

<span data-ttu-id="1a224-174">Lapā Attiecības katra attiecība ir apzīmēta ar rindu.</span><span class="sxs-lookup"><span data-stu-id="1a224-174">On the Relationships page, each relationship is represented by a row.</span></span> 

<span data-ttu-id="1a224-175">Atlasiet relāciju un izvēlieties vienu no šīm opcijām:</span><span class="sxs-lookup"><span data-stu-id="1a224-175">Select a relationship and choose one of the following options:</span></span> 
 
- <span data-ttu-id="1a224-176">**Rediģēšana**: atjauniniet pielāgotu attiecību rekvizītus rediģēšanas rūtī un saglabājiet izmaiņas.</span><span class="sxs-lookup"><span data-stu-id="1a224-176">**Edit**: Update properties of custom relationships in the edit pane and save changes.</span></span>
- <span data-ttu-id="1a224-177">**Dzēšana**: dzēsiet pielāgotas attiecības.</span><span class="sxs-lookup"><span data-stu-id="1a224-177">**Delete**: Delete custom relationships.</span></span>
- <span data-ttu-id="1a224-178">**Skatīt**: skatiet sistēmas izveidotās un mantotās attiecības.</span><span class="sxs-lookup"><span data-stu-id="1a224-178">**View**: View system-created and inherited relationships.</span></span> 

## <a name="next-step"></a><span data-ttu-id="1a224-179">Nākamā darbība</span><span class="sxs-lookup"><span data-stu-id="1a224-179">Next step</span></span>

<span data-ttu-id="1a224-180">Sistēmas un pielāgotas relācijas tiek izmantotas, lai [izveidotu segmentus](segments.md), pamatojoties uz vairākiem datu avotiem, kas vairs nav sadrumstaloti.</span><span class="sxs-lookup"><span data-stu-id="1a224-180">System and custom relationships are used to [create segments](segments.md) based on multiple data sources that are no longer siloed.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
