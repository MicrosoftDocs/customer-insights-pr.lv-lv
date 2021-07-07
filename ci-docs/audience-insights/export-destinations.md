---
title: Datu eksportēšana no Customer Insights
description: Pārvaldiet eksportēšanu, lai kopīgotu datus.
ms.date: 06/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 28563e3a76535cb0c92bfcda4ef5037430d00cfa
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305487"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="ce4b5-103">Eksportēšanas (priekšskatījuma) pārskats</span><span class="sxs-lookup"><span data-stu-id="ce4b5-103">Exports (preview) overview</span></span>

<span data-ttu-id="ce4b5-104">Lapā **Eksportēšana** tiek rādītas visas konfigurētās eksportēšanas.</span><span class="sxs-lookup"><span data-stu-id="ce4b5-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="ce4b5-105">Eksportēšana kopīgo konkrētus datus ar dažādām lietojumprogrammām.</span><span class="sxs-lookup"><span data-stu-id="ce4b5-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="ce4b5-106">Tie var ietvert klientu profilus vai entitījas, shēmas un kartēšanas informāciju.</span><span class="sxs-lookup"><span data-stu-id="ce4b5-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="ce4b5-107">Katrai eksportēšanai ir nepieciešams [administratora iestatīts savienojums, lai pārvaldītu autentifikāciju un piekļuvi](connections.md).</span><span class="sxs-lookup"><span data-stu-id="ce4b5-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

<span data-ttu-id="ce4b5-108">Dodieties uz lapu **Dati** > **Eksportēšana**, lai skatītu eksportēšanas lapu.</span><span class="sxs-lookup"><span data-stu-id="ce4b5-108">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="ce4b5-109">Visas lietotāju lomas var skatīt konfigurētās eksportēšanas.</span><span class="sxs-lookup"><span data-stu-id="ce4b5-109">All user roles can view configured exports.</span></span> <span data-ttu-id="ce4b5-110">Izmantojiet komandjoslā esošo meklēšanas lauku, lai atrastu eksportēšanas pēc to nosaukuma, savienojuma nosaukuma vai savienojuma tipa.</span><span class="sxs-lookup"><span data-stu-id="ce4b5-110">Use the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="ce4b5-111">Jauna eksporta iestatīšana</span><span class="sxs-lookup"><span data-stu-id="ce4b5-111">Set up a new export</span></span>

<span data-ttu-id="ce4b5-112">Lai iestatītu vai rediģētu eksportu, ir jābūt pieejamiem savienojumiem.</span><span class="sxs-lookup"><span data-stu-id="ce4b5-112">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="ce4b5-113">Savienojumi ir atkarīgi no jūsu [lietotāja lomas](permissions.md):</span><span class="sxs-lookup"><span data-stu-id="ce4b5-113">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="ce4b5-114">Administratoriem ir piekļuve visiem savienojumiem.</span><span class="sxs-lookup"><span data-stu-id="ce4b5-114">Administrators have access to all connections.</span></span> <span data-ttu-id="ce4b5-115">Viņi var arī eksportēšanas iestatīšanas laikā izveidot jaunus savienojumus.</span><span class="sxs-lookup"><span data-stu-id="ce4b5-115">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="ce4b5-116">Līdzstrādniekiem nav piekļuves konkrētiem savienojumiem.</span><span class="sxs-lookup"><span data-stu-id="ce4b5-116">Contributors can have access to specific connections.</span></span> <span data-ttu-id="ce4b5-117">Viņi ir atkarīgi no administratoriem, kuri konfigurē un kopīgo savienojumus.</span><span class="sxs-lookup"><span data-stu-id="ce4b5-117">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="ce4b5-118">Eksportēšanas sarakstā tiek rādīti dalībnieki, vai viņi var rediģēt vai tikai skatīt eksportēšanu kolonnā **Jūsu atļaujas**.</span><span class="sxs-lookup"><span data-stu-id="ce4b5-118">The exports list shows contributors whether they can edit or only view an export in the **Your permissions** column.</span></span> <span data-ttu-id="ce4b5-119">Papildinformāciju skatiet rakstā [Atļaut līdzstrādniekiem izmantot savienojumu eksportam](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="ce4b5-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="ce4b5-120">Skatītāji var tikai skatīt esošos eksportus, bet nevar tos izveidot.</span><span class="sxs-lookup"><span data-stu-id="ce4b5-120">Viewers can only view existing exports but not create them.</span></span>

### <a name="define-a-new-export"></a><span data-ttu-id="ce4b5-121">Jauna eksporta iestatīšana</span><span class="sxs-lookup"><span data-stu-id="ce4b5-121">Define a new export</span></span>

1. <span data-ttu-id="ce4b5-122">Pārejiet uz **Dati** > **Eksportēšana**.</span><span class="sxs-lookup"><span data-stu-id="ce4b5-122">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="ce4b5-123">Lai izveidotu jaunu eksportu, atlasiet **Pievienot eksportu**.</span><span class="sxs-lookup"><span data-stu-id="ce4b5-123">Select **Add export** to create a new export.</span></span>

1. <span data-ttu-id="ce4b5-124">Rūtī **Iestatīt eksportu** atlasiet, kuru savienojumu izmantot.</span><span class="sxs-lookup"><span data-stu-id="ce4b5-124">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="ce4b5-125">[Savienojumus](connections.md) pārvalda administratori.</span><span class="sxs-lookup"><span data-stu-id="ce4b5-125">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="ce4b5-126">Norādiet prasīto informāciju un atlasiet **Saglabāt**, lai izveidotu ziņojumu.</span><span class="sxs-lookup"><span data-stu-id="ce4b5-126">Provide the required details and select **Save** to create the export.</span></span>

### <a name="define-a-new-export-based-on-an-existing-export"></a><span data-ttu-id="ce4b5-127">Definējiet jaunu eksportēšanu, pamatojoties uz esošu eksportēšanu</span><span class="sxs-lookup"><span data-stu-id="ce4b5-127">Define a new export based on an existing export</span></span>

1. <span data-ttu-id="ce4b5-128">Pārejiet uz **Dati** > **Eksportēšana**.</span><span class="sxs-lookup"><span data-stu-id="ce4b5-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="ce4b5-129">Atskaišu sarakstā atlasiet dublicējamo atskaiti.</span><span class="sxs-lookup"><span data-stu-id="ce4b5-129">In the list of exports, select the export you want to duplicate.</span></span>

1. <span data-ttu-id="ce4b5-130">Atlasiet komandjoslā **Izveidot dublikātu**, lai atvērtu **Eksporta iestatīšanas** rūti ar detalizētu informāciju par atlasīto eksportēšanu.</span><span class="sxs-lookup"><span data-stu-id="ce4b5-130">Select **Create duplicate** in the command bar to open the **Set up export** pane with the details of the selected export.</span></span>

1. <span data-ttu-id="ce4b5-131">Pārskatiet un pielāgojiet eksportēšanu un atlasiet **Saglabāt**, lai izveidotu jaunu eksportēšanu.</span><span class="sxs-lookup"><span data-stu-id="ce4b5-131">Review and adapt the export and select **Save** to create a new export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="ce4b5-132">Eksporta rediģēšana</span><span class="sxs-lookup"><span data-stu-id="ce4b5-132">Edit an export</span></span>

1. <span data-ttu-id="ce4b5-133">Pārejiet uz **Dati** > **Eksportēšana**.</span><span class="sxs-lookup"><span data-stu-id="ce4b5-133">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="ce4b5-134">Atskaišu sarakstā atlasiet rediģējamo atskaiti.</span><span class="sxs-lookup"><span data-stu-id="ce4b5-134">In the list of exports, select the export you want to edit.</span></span>

1. <span data-ttu-id="ce4b5-135">Komandjoslā atlasiet **Rediģēt**.</span><span class="sxs-lookup"><span data-stu-id="ce4b5-135">Select **Edit** in the command bar.</span></span>

1. <span data-ttu-id="ce4b5-136">Mainiet vērtības, kuras vēlaties atjaunināt, un atlasiet **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="ce4b5-136">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="ce4b5-137">Skatīt eksportu un eksportēšanas informāciju</span><span class="sxs-lookup"><span data-stu-id="ce4b5-137">View exports and export details</span></span>

<span data-ttu-id="ce4b5-138">Pēc eksporta galamērķu izveides tos uzskaita lapā **Dati** > **Eksporti**.</span><span class="sxs-lookup"><span data-stu-id="ce4b5-138">After creating export destinations, they're listed on **Data** > **Exports**.</span></span> <span data-ttu-id="ce4b5-139">Visi lietotāji var redzēt, kuri dati tiek kopīgoti, kā arī to jaunāko statusu.</span><span class="sxs-lookup"><span data-stu-id="ce4b5-139">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="ce4b5-140">Pārejiet uz **Dati** > **Eksportēšana**.</span><span class="sxs-lookup"><span data-stu-id="ce4b5-140">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="ce4b5-141">Ja esat lietotājs bez rediģēšanas atļaujām, atlasiet **Skatīt** nevis **Rediģēt**, lai skatītu eksportēšanas informāciju.</span><span class="sxs-lookup"><span data-stu-id="ce4b5-141">Users without edit permissions select **View** instead of **Edit** to see the export details.</span></span>

1. <span data-ttu-id="ce4b5-142">Sānu rūtī ir redzama eksportēšanas konfigurācija.</span><span class="sxs-lookup"><span data-stu-id="ce4b5-142">The side pane shows the configuration of an export.</span></span> <span data-ttu-id="ce4b5-143">Bez rediģēšanas atļaujas vērtības nav iespējams mainīt.</span><span class="sxs-lookup"><span data-stu-id="ce4b5-143">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="ce4b5-144">Atlasiet **Aizvērt**, lai atgrieztos eksportēšanas lapā.</span><span class="sxs-lookup"><span data-stu-id="ce4b5-144">Select **Close** to return to the exports page.</span></span>

## <a name="schedule-and-run-exports"></a><span data-ttu-id="ce4b5-145">Eksportēšanas darbību ieplānošana un palaišana</span><span class="sxs-lookup"><span data-stu-id="ce4b5-145">Schedule and run exports</span></span>

<span data-ttu-id="ce4b5-146">Katrai konfigurētai eksportēšanai ir atsvaidzināšanas grafiks.</span><span class="sxs-lookup"><span data-stu-id="ce4b5-146">Each export you configure has a refresh schedule.</span></span> <span data-ttu-id="ce4b5-147">Atsvaidzināšanas laikā sistēma meklē jaunus vai atjauninātus datus, ko iekļaut eksportā.</span><span class="sxs-lookup"><span data-stu-id="ce4b5-147">During a refresh, the system looks for new or updated data to include in an export.</span></span> <span data-ttu-id="ce4b5-148">Pēc noklusējuma eksportēšana tiek izpildīta kā daļa no katras [plānotās sistēmas atsvaidzināšanas](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="ce4b5-148">By default, exports are run as part of every [scheduled system refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="ce4b5-149">Varat pielāgot atsvaidzināšanas grafiku vai izslēgt to, lai palaistu eksportu manuāli.</span><span class="sxs-lookup"><span data-stu-id="ce4b5-149">You can customize the refresh schedule or turn it off to run exports manually.</span></span>

<span data-ttu-id="ce4b5-150">Eksportēšanas grafiki ir atkarīgi no vides stāvokļa.</span><span class="sxs-lookup"><span data-stu-id="ce4b5-150">Export schedules depend on the state of your environment.</span></span> <span data-ttu-id="ce4b5-151">Ja laikā, kad būtu jāsāk plānotā atjaunināšana, notiek [atkarību](system.md#refresh-policies) atjaunināšana, sistēma vispirms pabeigs atjaunināšanu un pēc tam veiks eksportēšanu.</span><span class="sxs-lookup"><span data-stu-id="ce4b5-151">If there are updates in progress on [dependencies](system.md#refresh-policies) when a scheduled export should start, the system will first complete the updates and then run the export.</span></span> <span data-ttu-id="ce4b5-152">Kolonnā **Atsvaidzināts** varat redzēt, kad eksportēšana tika pēdējo reizi atsvaidzināta.</span><span class="sxs-lookup"><span data-stu-id="ce4b5-152">You can see when an export was last refreshed in column **Refreshed**.</span></span>

### <a name="schedule-exports"></a><span data-ttu-id="ce4b5-153">Eksportēšanas grafiks</span><span class="sxs-lookup"><span data-stu-id="ce4b5-153">Schedule exports</span></span>

<span data-ttu-id="ce4b5-154">Pielāgotus atsvaidzināšanas grafikus var definēt atsevišķam eksportēšanai vai vairāku veidu eksportēšanai vienlaikus.</span><span class="sxs-lookup"><span data-stu-id="ce4b5-154">You can define custom refresh schedules for individual exports or several exports at once.</span></span> <span data-ttu-id="ce4b5-155">Pašlaik definētais grafiks ir norādīts eksportēšanas saraksta kolonnā **Grafiks**.</span><span class="sxs-lookup"><span data-stu-id="ce4b5-155">The currently defined schedule is listed in the **Schedule** column of the export list.</span></span> <span data-ttu-id="ce4b5-156">Atļauja mainīt grafiku ir tāda pati kā [eksportēšanas rediģēšanai un definēšanai](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="ce4b5-156">The permission to change the schedule is the same as for [editing and defining exports](export-destinations.md#set-up-a-new-export).</span></span> 

1. <span data-ttu-id="ce4b5-157">Pārejiet uz **Dati** > **Eksportēšana**.</span><span class="sxs-lookup"><span data-stu-id="ce4b5-157">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="ce4b5-158">Atlasiet eksportēšanas darbību, ko vēlaties ieplānot.</span><span class="sxs-lookup"><span data-stu-id="ce4b5-158">Select the export you want to schedule.</span></span>

1. <span data-ttu-id="ce4b5-159">Komandjoslā atlasiet **Ieplānot**.</span><span class="sxs-lookup"><span data-stu-id="ce4b5-159">Select **Schedule** in the command bar.</span></span>

1. <span data-ttu-id="ce4b5-160">**Plānošanas eksportēšanas** rūtī iestatiet **Ieplānot palaišanu** uz **Ieslēgts**, lai automātiski palaistu eksportēšanu.</span><span class="sxs-lookup"><span data-stu-id="ce4b5-160">In the **Schedule export** pane, set the **Schedule run** to **On** to run the export automatically.</span></span> <span data-ttu-id="ce4b5-161">Iestatiet opciju **Izslēgt**, lai atsvaidzinātu manuāli.</span><span class="sxs-lookup"><span data-stu-id="ce4b5-161">Set it to **Off** to refresh it manually.</span></span>

1. <span data-ttu-id="ce4b5-162">Lai automātiski atsvaidzinātu eksportē, izvēlieties **Periodiskuma** vērtību un norādiet detalizētu informāciju par to.</span><span class="sxs-lookup"><span data-stu-id="ce4b5-162">For automatically refreshed exports, choose a **Recurrence** value and specify the details for it.</span></span> <span data-ttu-id="ce4b5-163">Definētais laiks attiecas uz visām atkārtošanās instancēm.</span><span class="sxs-lookup"><span data-stu-id="ce4b5-163">The time defined applies to all instances of a recurrence.</span></span> <span data-ttu-id="ce4b5-164">Tas ir laiks, kad eksportēšanai ir jāsāk atsvaidzināšana.</span><span class="sxs-lookup"><span data-stu-id="ce4b5-164">It's the time when an export should start refreshing.</span></span>

1. <span data-ttu-id="ce4b5-165">Izmaiņu lietot un aktivizēt, atlasot vienumu **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="ce4b5-165">Apply and activate your changes by selecting **Save**.</span></span>

<span data-ttu-id="ce4b5-166">Rediģējot vairāku eksportēšanas darbību grafiku, jums jāatlasa sadaļa **Atstāt vai ignorēt plānus**:</span><span class="sxs-lookup"><span data-stu-id="ce4b5-166">When editing the schedule for several exports, you need to make a selection under **Keep or override schedules**:</span></span>
- <span data-ttu-id="ce4b5-167">**Atstāt atsevišķus grafikus**: nemainiet iepriekš definēto atlasītā eksportēšanas grafika darbību un tikai atspējojiet vai iespējojiet tos.</span><span class="sxs-lookup"><span data-stu-id="ce4b5-167">**Keep individual schedules**: Persist the previously defined schedule for the selected exports and only disable or enable them.</span></span>
- <span data-ttu-id="ce4b5-168">**Definēt jaunu grafiku visām atlasītajām eksportēšanas darbībām**: ignorējiet atlasīto eksportēšanas darbību esošos plānus.</span><span class="sxs-lookup"><span data-stu-id="ce4b5-168">**Define new schedule for all selected exports**: Override the existing schedules of the selected exports.</span></span>

### <a name="run-exports-on-demand"></a><span data-ttu-id="ce4b5-169">Eksportēšanas palaišana pēc pieprasījuma</span><span class="sxs-lookup"><span data-stu-id="ce4b5-169">Run exports on demand</span></span>

<span data-ttu-id="ce4b5-170">Lai datus eksportētu, negaidot uz plānoto atsvaidzināšanu, dodieties uz **Dati** > **Eksportēšana**.</span><span class="sxs-lookup"><span data-stu-id="ce4b5-170">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span>

- <span data-ttu-id="ce4b5-171">Lai palaistu visus eksportus, komandjoslā atlasiet **Palaist visus**.</span><span class="sxs-lookup"><span data-stu-id="ce4b5-171">To run all exports, select **Run all** in the command bar.</span></span> <span data-ttu-id="ce4b5-172">Šī darbība tiks palaista tikai eksportam ar aktīvu grafiku.</span><span class="sxs-lookup"><span data-stu-id="ce4b5-172">This action will only run exports that have an active schedule.</span></span>
- <span data-ttu-id="ce4b5-173">Lai izpildītu vienu eksportēšanas darbību, atlasiet to sarakstā un komandjoslā atlasiet **Izpildīt**.</span><span class="sxs-lookup"><span data-stu-id="ce4b5-173">To run a single export, select it in the list and select **Run** in the command bar.</span></span> <span data-ttu-id="ce4b5-174">Tā tiek eksportēta bez aktīva grafika.</span><span class="sxs-lookup"><span data-stu-id="ce4b5-174">That's how you run exports with no active schedule.</span></span> 

## <a name="remove-an-export"></a><span data-ttu-id="ce4b5-175">Eksporta noņemšana</span><span class="sxs-lookup"><span data-stu-id="ce4b5-175">Remove an Export</span></span>

1. <span data-ttu-id="ce4b5-176">Pārejiet uz **Dati** > **Eksportēšana**.</span><span class="sxs-lookup"><span data-stu-id="ce4b5-176">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="ce4b5-177">Atlasiet eksportēšanas darbību, kuru vēlaties noņemt.</span><span class="sxs-lookup"><span data-stu-id="ce4b5-177">Select the export you want to remove.</span></span>

1. <span data-ttu-id="ce4b5-178">Komandjoslā atlasiet vienumu **Noņemt**.</span><span class="sxs-lookup"><span data-stu-id="ce4b5-178">Select **Remove** in the command bar.</span></span>

1. <span data-ttu-id="ce4b5-179">Apstipriniet noņemšanu, apstiprinājuma ekrānā atlasot pogu **Noņemt**.</span><span class="sxs-lookup"><span data-stu-id="ce4b5-179">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
