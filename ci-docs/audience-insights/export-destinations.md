---
title: Datu eksportēšana no Customer Insights
description: Pārvaldiet eksportēšanu, lai kopīgotu datus.
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 354ce9ef30fe918975d06290430996c84f8bd3f7
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896152"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="6e502-103">Eksportēšanas (priekšskatījuma) pārskats</span><span class="sxs-lookup"><span data-stu-id="6e502-103">Exports (preview) overview</span></span>

<span data-ttu-id="6e502-104">Lapā **Eksportēšana** tiek rādītas visas konfigurētās eksportēšanas.</span><span class="sxs-lookup"><span data-stu-id="6e502-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="6e502-105">Eksportēšana kopīgo konkrētus datus ar dažādām lietojumprogrammām.</span><span class="sxs-lookup"><span data-stu-id="6e502-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="6e502-106">Tie var ietvert klientu profilus vai entitījas, shēmas un kartēšanas informāciju.</span><span class="sxs-lookup"><span data-stu-id="6e502-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="6e502-107">Katrai eksportēšanai ir nepieciešams [administratora iestatīts savienojums, lai pārvaldītu autentifikāciju un piekļuvi](connections.md).</span><span class="sxs-lookup"><span data-stu-id="6e502-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

> [!NOTE]
> <span data-ttu-id="6e502-108">Līdz 2021. gada martam eksportēšana automātiski veidoja savienojumu ar atbilstošo pakalpojumu.</span><span class="sxs-lookup"><span data-stu-id="6e502-108">Until March 2021, exports created a connection to the corresponding service automatically.</span></span> <span data-ttu-id="6e502-109">Tagad eksportēšanai ir nepieciešams [administratora izveidots un kopīgots savienojums](connections.md), pirms varat to izveidot.</span><span class="sxs-lookup"><span data-stu-id="6e502-109">Exports now require a [connection, created and shared by an administrator](connections.md) before you can create them.</span></span>

<span data-ttu-id="6e502-110">Dodieties uz lapu **Dati** > **Eksportēšana**, lai skatītu eksportēšanas lapu.</span><span class="sxs-lookup"><span data-stu-id="6e502-110">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="6e502-111">Visām lietotāju lomām ir piekļuve konfigurētajai eksportēšanai.</span><span class="sxs-lookup"><span data-stu-id="6e502-111">All user roles have access to view configured exports.</span></span> <span data-ttu-id="6e502-112">Izmantojiet komandjoslas meklēšanas lauku, lai meklētu eksportus pēc nosaukuma, savienojuma nosaukuma vai savienojuma veida.</span><span class="sxs-lookup"><span data-stu-id="6e502-112">Use of the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="6e502-113">Jauna eksporta iestatīšana</span><span class="sxs-lookup"><span data-stu-id="6e502-113">Set up a new export</span></span>

<span data-ttu-id="6e502-114">Lai iestatītu vai rediģētu eksportu, ir jābūt pieejamiem savienojumiem.</span><span class="sxs-lookup"><span data-stu-id="6e502-114">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="6e502-115">Savienojumi ir atkarīgi no jūsu [lietotāja lomas](permissions.md):</span><span class="sxs-lookup"><span data-stu-id="6e502-115">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="6e502-116">Administratoriem ir piekļuve visiem savienojumiem.</span><span class="sxs-lookup"><span data-stu-id="6e502-116">Administrators have access to all connections.</span></span> <span data-ttu-id="6e502-117">Viņi var arī eksportēšanas iestatīšanas laikā izveidot jaunus savienojumus.</span><span class="sxs-lookup"><span data-stu-id="6e502-117">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="6e502-118">Līdzstrādniekiem nav piekļuves konkrētiem savienojumiem.</span><span class="sxs-lookup"><span data-stu-id="6e502-118">Contributors can have access to specific connections.</span></span> <span data-ttu-id="6e502-119">Viņi ir atkarīgi no administratoriem, kuri konfigurē un kopīgo savienojumus.</span><span class="sxs-lookup"><span data-stu-id="6e502-119">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="6e502-120">Papildinformāciju skatiet rakstā [Atļaut līdzstrādniekiem izmantot savienojumu eksportam](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="6e502-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="6e502-121">Skatītāji var tikai skatīt esošos eksportus, bet nevar tos izveidot.</span><span class="sxs-lookup"><span data-stu-id="6e502-121">Viewers can only view existing exports but not create them.</span></span>

1. <span data-ttu-id="6e502-122">Pārejiet uz **Dati** > **Eksportēšana**.</span><span class="sxs-lookup"><span data-stu-id="6e502-122">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="6e502-123">Lai izveidotu jaunu eksporta galamērķi, atlasiet **Pievienot eksportu**.</span><span class="sxs-lookup"><span data-stu-id="6e502-123">Select **Add export** to create a new export destination.</span></span>

1. <span data-ttu-id="6e502-124">Rūtī **Iestatīt eksportu** atlasiet, kuru savienojumu izmantot.</span><span class="sxs-lookup"><span data-stu-id="6e502-124">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="6e502-125">[Savienojumus](connections.md) pārvalda administratori.</span><span class="sxs-lookup"><span data-stu-id="6e502-125">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="6e502-126">Norādiet prasīto informāciju un atlasiet **Saglabāt**, lai izveidotu ziņojumu.</span><span class="sxs-lookup"><span data-stu-id="6e502-126">Provide the required details and select **Save** to create the export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="6e502-127">Eksporta rediģēšana</span><span class="sxs-lookup"><span data-stu-id="6e502-127">Edit an export</span></span>

1. <span data-ttu-id="6e502-128">Atlasiet eksportēšanas galamērķa vertikālo elipsi, ko vēlaties rediģēt.</span><span class="sxs-lookup"><span data-stu-id="6e502-128">Select the vertical ellipsis for the export destination you want to edit.</span></span>

1. <span data-ttu-id="6e502-129">Nolaižamajā izvēlnē atlasiet **Rediģēt**.</span><span class="sxs-lookup"><span data-stu-id="6e502-129">Select **Edit** from the drop-down menu.</span></span>

1. <span data-ttu-id="6e502-130">Mainiet vērtības, kuras vēlaties atjaunināt, un atlasiet **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="6e502-130">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="6e502-131">Skatīt eksportus un eksportēšanas informāciju</span><span class="sxs-lookup"><span data-stu-id="6e502-131">View Exports and export details</span></span>

<span data-ttu-id="6e502-132">Pēc eksporta galamērķu izveides tās tiek uzskaitītas lapā **Dati** > **Eksporti**.</span><span class="sxs-lookup"><span data-stu-id="6e502-132">After creating export destinations, they are listed on **Data** > **Exports**.</span></span> <span data-ttu-id="6e502-133">Visi lietotāji var redzēt, kuri dati tiek kopīgoti, kā arī to jaunāko statusu.</span><span class="sxs-lookup"><span data-stu-id="6e502-133">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="6e502-134">Pārejiet uz **Dati** > **Eksportēšana**.</span><span class="sxs-lookup"><span data-stu-id="6e502-134">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="6e502-135">Lietotājiem bez rediģēšanas atļaujas ir **Rediģēt** vietā jāizvēlas **Skatīt**, lai redzētu eksportēšanas informāciju.</span><span class="sxs-lookup"><span data-stu-id="6e502-135">Users without edit permissions select **View** instead of **Edit** see the export details.</span></span>

1. <span data-ttu-id="6e502-136">Sānu rūti redzami eksporta iestatījumi.</span><span class="sxs-lookup"><span data-stu-id="6e502-136">This side pane shows the set up of this export.</span></span> <span data-ttu-id="6e502-137">Bez rediģēšanas atļaujas vērtības nav iespējams mainīt.</span><span class="sxs-lookup"><span data-stu-id="6e502-137">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="6e502-138">Atlasiet **Aizvērt**, lai atgrieztos eksportēšanas lapā.</span><span class="sxs-lookup"><span data-stu-id="6e502-138">Select **Close** to return to the exports page.</span></span>

## <a name="run-exports-on-demand"></a><span data-ttu-id="6e502-139">Eksportēšanas palaišana pēc pieprasījuma</span><span class="sxs-lookup"><span data-stu-id="6e502-139">Run exports on demand</span></span>

<span data-ttu-id="6e502-140">Pēc eksporta konfigurēšanas tas tiks palaists ar katru [plānoto atsvaidzināšanu](system.md#schedule-tab), kamēr vien ir funkcionējošs savienojums.</span><span class="sxs-lookup"><span data-stu-id="6e502-140">After configuring an export, it will run with every [scheduled refresh](system.md#schedule-tab) as long as it has a working connection.</span></span>

<span data-ttu-id="6e502-141">Lai datus eksportētu, negaidot uz plānoto atsvaidzināšanu, dodieties uz **Dati** > **Eksportēšana**.</span><span class="sxs-lookup"><span data-stu-id="6e502-141">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span> <span data-ttu-id="6e502-142">Ir divas iespējas:</span><span class="sxs-lookup"><span data-stu-id="6e502-142">You have two options:</span></span>

- <span data-ttu-id="6e502-143">Lai palaistu visus eksportus, komandjoslā atlasiet **Palaist visus**.</span><span class="sxs-lookup"><span data-stu-id="6e502-143">To run all exports, select **Run all** in the command bar.</span></span> 
- <span data-ttu-id="6e502-144">Lai palaistu vienreizējo eksportēšanu, sarakstu elementā atlasiet daudzpunkti (...) un atlasiet **Palaist**.</span><span class="sxs-lookup"><span data-stu-id="6e502-144">To run a single export, select the ellipsis (...) on a list item and then choose **Run**.</span></span>

## <a name="remove-an-export"></a><span data-ttu-id="6e502-145">Eksporta noņemšana</span><span class="sxs-lookup"><span data-stu-id="6e502-145">Remove an Export</span></span>

1. <span data-ttu-id="6e502-146">Pārejiet uz **Dati** > **Eksportēšana**.</span><span class="sxs-lookup"><span data-stu-id="6e502-146">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="6e502-147">Atlasiet vertikālo daudzpunkti eksportam, kuru vēlaties noņemt.</span><span class="sxs-lookup"><span data-stu-id="6e502-147">Select the vertical ellipsis for the Export you want to remove.</span></span>

1. <span data-ttu-id="6e502-148">Atlasiet **Noņemt** nolaižamajā izvēlnē.</span><span class="sxs-lookup"><span data-stu-id="6e502-148">Select **Remove** from the dropdown menu.</span></span>

1. <span data-ttu-id="6e502-149">Apstipriniet noņemšanu, apstiprinājuma ekrānā atlasot pogu **Noņemt**.</span><span class="sxs-lookup"><span data-stu-id="6e502-149">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
