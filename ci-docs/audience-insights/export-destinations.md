---
title: Datu eksportēšana no Customer Insights
description: Pārvaldiet eksportēšanu, lai kopīgotu datus.
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c1078ed0ba259a6e9cde3c7ede3570890ae48e67
ms.sourcegitcommit: 33a8e21b3bf6521bdb8346f81f79fce88091ddfd
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 05/10/2021
ms.locfileid: "6016623"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="52f6e-103">Eksportēšanas (priekšskatījuma) pārskats</span><span class="sxs-lookup"><span data-stu-id="52f6e-103">Exports (preview) overview</span></span>

<span data-ttu-id="52f6e-104">Lapā **Eksportēšana** tiek rādītas visas konfigurētās eksportēšanas.</span><span class="sxs-lookup"><span data-stu-id="52f6e-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="52f6e-105">Eksportēšana kopīgo konkrētus datus ar dažādām lietojumprogrammām.</span><span class="sxs-lookup"><span data-stu-id="52f6e-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="52f6e-106">Tie var ietvert klientu profilus vai entitījas, shēmas un kartēšanas informāciju.</span><span class="sxs-lookup"><span data-stu-id="52f6e-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="52f6e-107">Katrai eksportēšanai ir nepieciešams [administratora iestatīts savienojums, lai pārvaldītu autentifikāciju un piekļuvi](connections.md).</span><span class="sxs-lookup"><span data-stu-id="52f6e-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

<span data-ttu-id="52f6e-108">Dodieties uz lapu **Dati** > **Eksportēšana**, lai skatītu eksportēšanas lapu.</span><span class="sxs-lookup"><span data-stu-id="52f6e-108">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="52f6e-109">Visām lietotāju lomām ir piekļuve konfigurētajai eksportēšanai.</span><span class="sxs-lookup"><span data-stu-id="52f6e-109">All user roles have access to view configured exports.</span></span> <span data-ttu-id="52f6e-110">Izmantojiet komandjoslas meklēšanas lauku, lai meklētu eksportus pēc nosaukuma, savienojuma nosaukuma vai savienojuma veida.</span><span class="sxs-lookup"><span data-stu-id="52f6e-110">Use of the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="52f6e-111">Jauna eksporta iestatīšana</span><span class="sxs-lookup"><span data-stu-id="52f6e-111">Set up a new export</span></span>

<span data-ttu-id="52f6e-112">Lai iestatītu vai rediģētu eksportu, ir jābūt pieejamiem savienojumiem.</span><span class="sxs-lookup"><span data-stu-id="52f6e-112">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="52f6e-113">Savienojumi ir atkarīgi no jūsu [lietotāja lomas](permissions.md):</span><span class="sxs-lookup"><span data-stu-id="52f6e-113">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="52f6e-114">Administratoriem ir piekļuve visiem savienojumiem.</span><span class="sxs-lookup"><span data-stu-id="52f6e-114">Administrators have access to all connections.</span></span> <span data-ttu-id="52f6e-115">Viņi var arī eksportēšanas iestatīšanas laikā izveidot jaunus savienojumus.</span><span class="sxs-lookup"><span data-stu-id="52f6e-115">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="52f6e-116">Līdzstrādniekiem nav piekļuves konkrētiem savienojumiem.</span><span class="sxs-lookup"><span data-stu-id="52f6e-116">Contributors can have access to specific connections.</span></span> <span data-ttu-id="52f6e-117">Viņi ir atkarīgi no administratoriem, kuri konfigurē un kopīgo savienojumus.</span><span class="sxs-lookup"><span data-stu-id="52f6e-117">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="52f6e-118">Papildinformāciju skatiet rakstā [Atļaut līdzstrādniekiem izmantot savienojumu eksportam](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="52f6e-118">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="52f6e-119">Skatītāji var tikai skatīt esošos eksportus, bet nevar tos izveidot.</span><span class="sxs-lookup"><span data-stu-id="52f6e-119">Viewers can only view existing exports but not create them.</span></span>

1. <span data-ttu-id="52f6e-120">Pārejiet uz **Dati** > **Eksportēšana**.</span><span class="sxs-lookup"><span data-stu-id="52f6e-120">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="52f6e-121">Lai izveidotu jaunu eksporta galamērķi, atlasiet **Pievienot eksportu**.</span><span class="sxs-lookup"><span data-stu-id="52f6e-121">Select **Add export** to create a new export destination.</span></span>

1. <span data-ttu-id="52f6e-122">Rūtī **Iestatīt eksportu** atlasiet, kuru savienojumu izmantot.</span><span class="sxs-lookup"><span data-stu-id="52f6e-122">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="52f6e-123">[Savienojumus](connections.md) pārvalda administratori.</span><span class="sxs-lookup"><span data-stu-id="52f6e-123">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="52f6e-124">Norādiet prasīto informāciju un atlasiet **Saglabāt**, lai izveidotu ziņojumu.</span><span class="sxs-lookup"><span data-stu-id="52f6e-124">Provide the required details and select **Save** to create the export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="52f6e-125">Eksporta rediģēšana</span><span class="sxs-lookup"><span data-stu-id="52f6e-125">Edit an export</span></span>

1. <span data-ttu-id="52f6e-126">Atlasiet eksportēšanas galamērķa vertikālo elipsi, ko vēlaties rediģēt.</span><span class="sxs-lookup"><span data-stu-id="52f6e-126">Select the vertical ellipsis for the export destination you want to edit.</span></span>

1. <span data-ttu-id="52f6e-127">Nolaižamajā izvēlnē atlasiet **Rediģēt**.</span><span class="sxs-lookup"><span data-stu-id="52f6e-127">Select **Edit** from the drop-down menu.</span></span>

1. <span data-ttu-id="52f6e-128">Mainiet vērtības, kuras vēlaties atjaunināt, un atlasiet **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="52f6e-128">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="52f6e-129">Skatīt eksportus un eksportēšanas informāciju</span><span class="sxs-lookup"><span data-stu-id="52f6e-129">View Exports and export details</span></span>

<span data-ttu-id="52f6e-130">Pēc eksporta galamērķu izveides tās tiek uzskaitītas lapā **Dati** > **Eksporti**.</span><span class="sxs-lookup"><span data-stu-id="52f6e-130">After creating export destinations, they are listed on **Data** > **Exports**.</span></span> <span data-ttu-id="52f6e-131">Visi lietotāji var redzēt, kuri dati tiek kopīgoti, kā arī to jaunāko statusu.</span><span class="sxs-lookup"><span data-stu-id="52f6e-131">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="52f6e-132">Pārejiet uz **Dati** > **Eksportēšana**.</span><span class="sxs-lookup"><span data-stu-id="52f6e-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="52f6e-133">Lietotājiem bez rediģēšanas atļaujas ir **Rediģēt** vietā jāizvēlas **Skatīt**, lai redzētu eksportēšanas informāciju.</span><span class="sxs-lookup"><span data-stu-id="52f6e-133">Users without edit permissions select **View** instead of **Edit** see the export details.</span></span>

1. <span data-ttu-id="52f6e-134">Sānu rūti redzami eksporta iestatījumi.</span><span class="sxs-lookup"><span data-stu-id="52f6e-134">This side pane shows the set up of this export.</span></span> <span data-ttu-id="52f6e-135">Bez rediģēšanas atļaujas vērtības nav iespējams mainīt.</span><span class="sxs-lookup"><span data-stu-id="52f6e-135">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="52f6e-136">Atlasiet **Aizvērt**, lai atgrieztos eksportēšanas lapā.</span><span class="sxs-lookup"><span data-stu-id="52f6e-136">Select **Close** to return to the exports page.</span></span>

## <a name="run-exports-on-demand"></a><span data-ttu-id="52f6e-137">Eksportēšanas palaišana pēc pieprasījuma</span><span class="sxs-lookup"><span data-stu-id="52f6e-137">Run exports on demand</span></span>

<span data-ttu-id="52f6e-138">Pēc eksporta konfigurēšanas tas tiks palaists ar katru [plānoto atsvaidzināšanu](system.md#schedule-tab), kamēr vien ir funkcionējošs savienojums.</span><span class="sxs-lookup"><span data-stu-id="52f6e-138">After configuring an export, it will run with every [scheduled refresh](system.md#schedule-tab) as long as it has a working connection.</span></span>

<span data-ttu-id="52f6e-139">Lai datus eksportētu, negaidot uz plānoto atsvaidzināšanu, dodieties uz **Dati** > **Eksportēšana**.</span><span class="sxs-lookup"><span data-stu-id="52f6e-139">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span> <span data-ttu-id="52f6e-140">Ir divas iespējas:</span><span class="sxs-lookup"><span data-stu-id="52f6e-140">You have two options:</span></span>

- <span data-ttu-id="52f6e-141">Lai palaistu visus eksportus, komandjoslā atlasiet **Palaist visus**.</span><span class="sxs-lookup"><span data-stu-id="52f6e-141">To run all exports, select **Run all** in the command bar.</span></span> 
- <span data-ttu-id="52f6e-142">Lai palaistu vienreizējo eksportēšanu, sarakstu elementā atlasiet daudzpunkti (...) un atlasiet **Palaist**.</span><span class="sxs-lookup"><span data-stu-id="52f6e-142">To run a single export, select the ellipsis (...) on a list item and then choose **Run**.</span></span>

## <a name="remove-an-export"></a><span data-ttu-id="52f6e-143">Eksporta noņemšana</span><span class="sxs-lookup"><span data-stu-id="52f6e-143">Remove an Export</span></span>

1. <span data-ttu-id="52f6e-144">Pārejiet uz **Dati** > **Eksportēšana**.</span><span class="sxs-lookup"><span data-stu-id="52f6e-144">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="52f6e-145">Atlasiet vertikālo daudzpunkti eksportam, kuru vēlaties noņemt.</span><span class="sxs-lookup"><span data-stu-id="52f6e-145">Select the vertical ellipsis for the Export you want to remove.</span></span>

1. <span data-ttu-id="52f6e-146">Atlasiet **Noņemt** nolaižamajā izvēlnē.</span><span class="sxs-lookup"><span data-stu-id="52f6e-146">Select **Remove** from the dropdown menu.</span></span>

1. <span data-ttu-id="52f6e-147">Apstipriniet noņemšanu, apstiprinājuma ekrānā atlasot pogu **Noņemt**.</span><span class="sxs-lookup"><span data-stu-id="52f6e-147">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
