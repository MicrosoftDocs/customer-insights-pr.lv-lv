---
title: Savienojumi ar citiem pakalpojumiem no Customer Insights.
description: Kopīgojiet datus ar citiem pakalpojumiem.
ms.date: 04/09/2021
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 106dbc26f95b309821d738e1484b1eaa79dd225b
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896106"
---
# <a name="connections-preview-overview"></a><span data-ttu-id="73af3-103">Savienojumu (priekšskatījums) pārskats</span><span class="sxs-lookup"><span data-stu-id="73af3-103">Connections (preview) overview</span></span>

<span data-ttu-id="73af3-104">Savienojumi ir atslēga tam, lai jūs iespējotu datu kopīgošanu ar un no Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="73af3-104">Connections are the key to enable data sharing to and from Customer Insights.</span></span> <span data-ttu-id="73af3-105">Katrs savienojums kopīgo datus ar konkrēto servisu.</span><span class="sxs-lookup"><span data-stu-id="73af3-105">Each connection establishes data sharing with a specific service.</span></span> <span data-ttu-id="73af3-106">Savienojumi ir pamatā [trešās puses bagātinājumu konfigurēšanai](enrichment-hub.md) un [eksportēšanas konfigurēšanai](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="73af3-106">Connections are the foundation to [configure third-party enrichments](enrichment-hub.md) and [configure exports](export-destinations.md).</span></span> <span data-ttu-id="73af3-107">Vienu un to pašu savienojumu var izmantot vairākkārt.</span><span class="sxs-lookup"><span data-stu-id="73af3-107">The same connection can be used multiple times.</span></span> <span data-ttu-id="73af3-108">Piemēram, viens savienojums ar Dynamics 365 Marketing darbojas vairākiem eksportiem, un vienu Leadspace savienojumu var izmantot vairākiem bagātinājumiem.</span><span class="sxs-lookup"><span data-stu-id="73af3-108">For example, one connection to Dynamics 365 Marketing works for multiple exports and one Leadspace connection can be used for several enrichments.</span></span>

<span data-ttu-id="73af3-109">Lai izveidotu un skatītu savienojumus, dodieties uz **Administrators** > **Savienojumi**.</span><span class="sxs-lookup"><span data-stu-id="73af3-109">Go to **Admin** > **Connections** to create and view connections.</span></span>

<span data-ttu-id="73af3-110">Cilnē **Savienojumi** ir redzami visi aktīvie savienojumi.</span><span class="sxs-lookup"><span data-stu-id="73af3-110">The **Connections** tab shows you all active connections.</span></span> <span data-ttu-id="73af3-111">Sarakstā redzama katra savienojuma rinda.</span><span class="sxs-lookup"><span data-stu-id="73af3-111">The list shows a row for each connection.</span></span> 

<span data-ttu-id="73af3-112">Cilnē **Atklāt** plūkojiet īsu pārskatu un aprakstu un uzziniet, ko varat darīt ar katru paplašināšanas opciju.</span><span class="sxs-lookup"><span data-stu-id="73af3-112">Get a quick overview, description, and find out what you can do with each extensibility option on the **Discover** tab.</span></span>

### <a name="exports"></a><span data-ttu-id="73af3-113">Eksports</span><span class="sxs-lookup"><span data-stu-id="73af3-113">Exports</span></span>

<span data-ttu-id="73af3-114">Tikai administratori var konfigurēt jaunos savienojumus, taču viņi var piešķirt piekļuvi līdzstrādniekiem, lai viņi lietotu esošos savienojumus.</span><span class="sxs-lookup"><span data-stu-id="73af3-114">Only administrators can configure new connections but they can grant access to contributors to use existing connections.</span></span> <span data-ttu-id="73af3-115">Administratori nosaka, kur dati var doties, līdzstrādnieki atbilstoši savām vajadzībām definē lietderīgo slodzi un biežumu.</span><span class="sxs-lookup"><span data-stu-id="73af3-115">Administrators control where data can go, contributors define the payload and frequency fitting their needs.</span></span> <span data-ttu-id="73af3-116">Papildinformāciju skatiet rakstā [Atļaut līdzstrādniekiem izmantot savienojumu eksportam](#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="73af3-116">For more information, see [Allow contributors to use a connection for exports](#allow-contributors-to-use-a-connection-for-exports).</span></span>

### <a name="enrichments"></a><span data-ttu-id="73af3-117">Bagātinājumi</span><span class="sxs-lookup"><span data-stu-id="73af3-117">Enrichments</span></span>

<span data-ttu-id="73af3-118">Jaunus savienojumu drīkst konfigurēt tikai administratori, taču izveidotie savienojumi vienmēr ir pieejami gan administratoriem, gan līdzstrādniekiem.</span><span class="sxs-lookup"><span data-stu-id="73af3-118">Only administrators can configure new connections but the created connections are always available to both administrators and contributors.</span></span> <span data-ttu-id="73af3-119">Administratori pārvalda akreditācijas un sniedz piekrišanu datu pārsūtīšanai.</span><span class="sxs-lookup"><span data-stu-id="73af3-119">Administrators manage credentials and give consent to data transfers.</span></span> <span data-ttu-id="73af3-120">Pēc tam savienojumus bagātināšanai var izmantot kā administratori, tā arī līdzstrādnieki.</span><span class="sxs-lookup"><span data-stu-id="73af3-120">The connections can then be used for enrichments by both administrators and contributors.</span></span>

## <a name="add-a-new-connection"></a><span data-ttu-id="73af3-121">Jauna savienojuma pievienošana</span><span class="sxs-lookup"><span data-stu-id="73af3-121">Add a new connection</span></span>

<span data-ttu-id="73af3-122">Lai pievienotu savienojumu, ir jābūt [administratora atļaujām](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="73af3-122">To add connections, you need to have [administrator permissions](permissions.md).</span></span> <span data-ttu-id="73af3-123">Ja savienojaties ar citiem Microsoft pakalpojumiem, mēs pieņemam, ka abi pakalpojumi atrodas vienā organizācijā.</span><span class="sxs-lookup"><span data-stu-id="73af3-123">If you connect to other Microsoft services, we assume both services are in the same organization.</span></span>

1. <span data-ttu-id="73af3-124">Dodieties uz **Administrators** > **Savienojumi (priekšskatījums)**.</span><span class="sxs-lookup"><span data-stu-id="73af3-124">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="73af3-125">Doties uz cilni **Savienojumi**.</span><span class="sxs-lookup"><span data-stu-id="73af3-125">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="73af3-126">Lai izveidotu jaunu savienojumu, atlasiet **Pievienot savienojumu**.</span><span class="sxs-lookup"><span data-stu-id="73af3-126">Select **Add connection** to create a new connection.</span></span> <span data-ttu-id="73af3-127">Nolaižamajā izvēlnē atlasiet, kāda veida savienojumu vēlaties izveidot.</span><span class="sxs-lookup"><span data-stu-id="73af3-127">Choose from the drop-down menu what type of connection you want to create.</span></span>

1. <span data-ttu-id="73af3-128">Rūtī **Iestatīt savienojumu** norādiet nepieciešamo informāciju.</span><span class="sxs-lookup"><span data-stu-id="73af3-128">In the **Set up connection** pane, provide the required details.</span></span> 
   1. <span data-ttu-id="73af3-129">**Parādāmais nosaukums** un nosaukuma veids raksturo savienojumu.</span><span class="sxs-lookup"><span data-stu-id="73af3-129">The **Display name** and the type of the connection describe a connection.</span></span> <span data-ttu-id="73af3-130">Ir ieteicams izvēlēties nosaukumu, kas paskaidro savienojuma nolūku.</span><span class="sxs-lookup"><span data-stu-id="73af3-130">We recommend choosing a name that explains the purpose and target of this connection.</span></span>
   1. <span data-ttu-id="73af3-131">Precīzie lauki ir atkarīgi no tā, kādam pakalpojuma pieslēdzaties.</span><span class="sxs-lookup"><span data-stu-id="73af3-131">The exact fields depend on what service you are connecting to.</span></span> <span data-ttu-id="73af3-132">Varat sīkāk uzzināt par konkrēto savienojuma veidu rakstā par mērķa pakalpojumu.</span><span class="sxs-lookup"><span data-stu-id="73af3-132">You can learn about details of a specific connection type in the article about the target service.</span></span>

1. <span data-ttu-id="73af3-133">Lai izveidotu savienojumu, atlasiet **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="73af3-133">To create the connection, select **Save**.</span></span>

<span data-ttu-id="73af3-134">Cilnes elementā **Iestatīt** var atlasīt arī **Atklāt**.</span><span class="sxs-lookup"><span data-stu-id="73af3-134">You can also select **Set up** on a tile on the **Discover** tab.</span></span>

### <a name="allow-contributors-to-use-a-connection-for-exports"></a><span data-ttu-id="73af3-135">Ļaut līdzstrādniekiem izmantot savienojumu eksportēšanai</span><span class="sxs-lookup"><span data-stu-id="73af3-135">Allow contributors to use a connection for exports</span></span>

<span data-ttu-id="73af3-136">Iestatot vai rediģējot eksportēšanas savienojumu, jūs izvēlaties, kuriem lietotājiem ir atļauts izmantot konkrēto savienojumu, lai definētu [eksportēšanu](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="73af3-136">When setting up or editing an export connection, you choose which users are allowed to use this specific connection to define [exports](export-destinations.md).</span></span> <span data-ttu-id="73af3-137">Savienojums pēc noklusējuma ir pieejams lietotājiem ar administratora lomu.</span><span class="sxs-lookup"><span data-stu-id="73af3-137">By default a connection is available to users with an administrator role.</span></span> <span data-ttu-id="73af3-138">Šo iestatījumu varat mainīt sadaļān **Izvēlieties, kas var lietot šo savienojumu** un ļaut šo savienojumu izmantot lietotājiem ar līdzstrādnieka lomu.</span><span class="sxs-lookup"><span data-stu-id="73af3-138">You can change this setting under **Choose who can use this connection** and allow users with contributor role to use this connection.</span></span>

- <span data-ttu-id="73af3-139">Līdzstrādnieki nevarēs savienojumu skatīt vai rediģēt.</span><span class="sxs-lookup"><span data-stu-id="73af3-139">Contributors won't be able to view or edit the connection.</span></span> <span data-ttu-id="73af3-140">Viņi eksporta izveides laikā redzēs vienīgi parādāmo nosaukumu un veidu.</span><span class="sxs-lookup"><span data-stu-id="73af3-140">They will only see the display name and its type when creating an export.</span></span>
- <span data-ttu-id="73af3-141">Kopīgojot savienojumu, jūs ļaujat savienojumu izmantot līdzstrādniekiem.</span><span class="sxs-lookup"><span data-stu-id="73af3-141">By sharing a connection, you allow contributors to use a connection.</span></span> <span data-ttu-id="73af3-142">Līdzstrādnieki eksportēšanas iestatīšanas laikā redzēs kopīgotos savienojumus.</span><span class="sxs-lookup"><span data-stu-id="73af3-142">Contributors will see shared connections when they set up exports.</span></span> <span data-ttu-id="73af3-143">Viņi var pārvaldīt visus eksportus, kuri izmanto konkrēto savienojumu.</span><span class="sxs-lookup"><span data-stu-id="73af3-143">They can manage every export that uses this specific connection.</span></span>
- <span data-ttu-id="73af3-144">Šo iestatījumu varat mainīt, vienlaikus paturot līdzstrādnieku jau definētos eksportus.</span><span class="sxs-lookup"><span data-stu-id="73af3-144">You can change this setting while keeping the exports that have already been defined by contributors.</span></span>

## <a name="edit-a-connection"></a><span data-ttu-id="73af3-145">Savienojuma rediģēšana</span><span class="sxs-lookup"><span data-stu-id="73af3-145">Edit a connection</span></span>

1. <span data-ttu-id="73af3-146">Dodieties uz **Administrators** > **Savienojumi (priekšskatījums)**.</span><span class="sxs-lookup"><span data-stu-id="73af3-146">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="73af3-147">Doties uz cilni **Savienojumi**.</span><span class="sxs-lookup"><span data-stu-id="73af3-147">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="73af3-148">Atlasiet vertikālo daudzpunkti savienojumam, kuru vēlaties rediģēt.</span><span class="sxs-lookup"><span data-stu-id="73af3-148">Select the vertical ellipsis for the connection you want to edit.</span></span>

1. <span data-ttu-id="73af3-149">Atlasiet **Rediģēt**.</span><span class="sxs-lookup"><span data-stu-id="73af3-149">Select **Edit**.</span></span>

1. <span data-ttu-id="73af3-150">Mainiet vērtības, kuras vēlaties atjaunināt, un atlasiet **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="73af3-150">Change the values you want to update and select **Save**.</span></span>

## <a name="remove-a-connection"></a><span data-ttu-id="73af3-151">Savienojuma noņemšana</span><span class="sxs-lookup"><span data-stu-id="73af3-151">Remove a connection</span></span>

<span data-ttu-id="73af3-152">Ja savienojumu, kuru noņemat, izmanto bagātināšanā vai eksportēšanā, tās vispirms ir jāatvieno vai jāņoņem.</span><span class="sxs-lookup"><span data-stu-id="73af3-152">If the connection you are removing is used by enrichments or exports, you first need to detach or remove them.</span></span> <span data-ttu-id="73af3-153">Noņemšanas dialoglodziņš jūs aizvirzīs uz atbilstīgo bagātināšanu vai eksportēšanu.</span><span class="sxs-lookup"><span data-stu-id="73af3-153">The remove dialog will guide you to the relevant enrichments or exports.</span></span> <span data-ttu-id="73af3-154">Atvienota bagātināšana un eksportēšana kļūst neaktīva.</span><span class="sxs-lookup"><span data-stu-id="73af3-154">Detached enrichments and exports become inactive.</span></span> <span data-ttu-id="73af3-155">Jūs varat tās aktivizēt no jauna, pievienojot tām citu savienojumu lapā [Bagātināšana](enrichment-hub.md) vai [Eksportēšana](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="73af3-155">You reactivate them by adding another connection to them on the [Enrichments](enrichment-hub.md) or [Exports](export-destinations.md) page.</span></span>

1. <span data-ttu-id="73af3-156">Dodieties uz **Administrators** > **Savienojumi (priekšskatījums)**.</span><span class="sxs-lookup"><span data-stu-id="73af3-156">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="73af3-157">Doties uz cilni **Savienojumi**.</span><span class="sxs-lookup"><span data-stu-id="73af3-157">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="73af3-158">Atlasiet vertikālo daudzpunkti savienojumam, kuru vēlaties noņemt.</span><span class="sxs-lookup"><span data-stu-id="73af3-158">Select the vertical ellipsis for the connection you want to remove.</span></span>

1. <span data-ttu-id="73af3-159">Atlasiet **Noņemt** nolaižamajā izvēlnē.</span><span class="sxs-lookup"><span data-stu-id="73af3-159">Select **Remove** from the dropdown menu.</span></span> <span data-ttu-id="73af3-160">Tiek atvērts apstiprinājuma dialoglodziņš.</span><span class="sxs-lookup"><span data-stu-id="73af3-160">A confirmation dialog appears.</span></span>

   1. <span data-ttu-id="73af3-161">Ja šo savienojumu izmanto bagātināšana vai eksportēšana, atlasiet pogu, lai redzētu, kas izmanto savienojumu.</span><span class="sxs-lookup"><span data-stu-id="73af3-161">If there are enrichments or exports using this connection, select the button to see what's using the connection.</span></span>
      - <span data-ttu-id="73af3-162">**Eksportēšana:** Varat izvēlēties vai nu noņemt vai atvienot eksportēšanu, lai varētu noņemt savienojumu.</span><span class="sxs-lookup"><span data-stu-id="73af3-162">**Exports:** You can choose to either remove or disconnect the exports to be able to remove the connection.</span></span> <span data-ttu-id="73af3-163">Lai atvienotu eksportēšanu, administratori var izmantot darbību **Atvienot**.</span><span class="sxs-lookup"><span data-stu-id="73af3-163">To disconnect an export, administrators can use the **Disconnect** action.</span></span> <span data-ttu-id="73af3-164">Šī darbība ir pieejama atsevišķām un vairākām eksportēšanām.</span><span class="sxs-lookup"><span data-stu-id="73af3-164">This action is available for individual and multiple selected exports.</span></span> <span data-ttu-id="73af3-165">Veicot atvienošanu, tiek saglabāta eksportēšanas konfigurācija, taču tā netiks palaista, iekams nebūs pievienots cits savienojums.</span><span class="sxs-lookup"><span data-stu-id="73af3-165">By disconnecting you keep the export config, but it won't be run until another connection is added to it.</span></span>
      - <span data-ttu-id="73af3-166">**Bagātināšana:** Varat izvēlēties vai nu noņemt vai deaktivizēt bagātināšanu, lai varētu noņemt savienojumu.</span><span class="sxs-lookup"><span data-stu-id="73af3-166">**Enrichments:** You can choose to either remove or deactivate the enrichments to be able to remove the connection.</span></span> 
   1. <span data-ttu-id="73af3-167">Kolīdz savienojumam vairs nav atkarīgo elementu, atgriezieties lapā **Administrators** > **Savienojumi** un vēlreiz mēģiniet noņemt savienojumu.</span><span class="sxs-lookup"><span data-stu-id="73af3-167">Once the connection has no more dependencies, go back to **Admin** > **Connections** and try removing the connection again.</span></span>

1. <span data-ttu-id="73af3-168">Lai apstiprinātu dzēšanu, atlasiet **Noņemt**.</span><span class="sxs-lookup"><span data-stu-id="73af3-168">To confirm the deletion select **Remove**.</span></span>

