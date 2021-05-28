---
title: Customer Insights datu eksportēšana uz Dynamics 365 Sales
description: Uzziniet, kā konfigurēt savienojumu un eksportēt uz Dynamics 365 Sales.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 328bb2f26ebcea234fb645e5225930ab12f82a8b
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976235"
---
# <a name="use-segments-in-dynamics-365-sales-preview"></a><span data-ttu-id="2f799-103">Segmentu lietošana Dynamics 365 Sales (priekšskatījums)</span><span class="sxs-lookup"><span data-stu-id="2f799-103">Use segments in Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="2f799-104">Izmantojiet Dynamics 365 Sales klientu datus, lai izveidotu mārketinga adresātu sarakstus, tālāko darbību plūsmas un nosūtītu reklāmas.</span><span class="sxs-lookup"><span data-stu-id="2f799-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite-for-connection"></a><span data-ttu-id="2f799-105">Savienojuma priekšnosacījums</span><span class="sxs-lookup"><span data-stu-id="2f799-105">Prerequisite for connection</span></span>

1. <span data-ttu-id="2f799-106">Lai varētu eksportēt segmentu no programmas Customer Insights uz programmu Sales, programmā Dynamics 365 Sales ir jābūt kontaktpersonu ierakstiem.</span><span class="sxs-lookup"><span data-stu-id="2f799-106">Contact records must be present in Dynamics 365 Sales before you can export a segment from Customer Insights to Sales.</span></span> <span data-ttu-id="2f799-107">Papildinformācija par kontaktpersonu uzņemšanu programmā [Dynamics 365 Sales, izmantojot Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="2f799-107">Read more on how to ingest contacts in [Dynamics 365 Sales using Common Data Services](connect-power-query.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="2f799-108">Eksportējot segmentus no auditorijas ieskatiem uz programmu Sales, netiek veidoti jauni kontaktpersonu ieraksti.</span><span class="sxs-lookup"><span data-stu-id="2f799-108">Exporting segments from audience insights to Sales will not create new contact records in the Sales instances.</span></span> <span data-ttu-id="2f799-109">Kontaktpersonu ieraksti no programmas Sales jābūt uzņemtiem auditorijas ieskatos un izmantotiem kā datu avotam.</span><span class="sxs-lookup"><span data-stu-id="2f799-109">The contact records from Sales must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="2f799-110">Tie ir jāiekļauj arī vienotā Klienta entītijā, lai kartētu klientu ID uz kontaktu ID pirms segmentu eksportēšanas.</span><span class="sxs-lookup"><span data-stu-id="2f799-110">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="set-up-the-connection-to-sales"></a><span data-ttu-id="2f799-111">Savienojuma ar Sales iestatīšana</span><span class="sxs-lookup"><span data-stu-id="2f799-111">Set up the connection to Sales</span></span>

1. <span data-ttu-id="2f799-112">Dodieties uz **Administrators** > **Savienojumi**.</span><span class="sxs-lookup"><span data-stu-id="2f799-112">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="2f799-113">Atlasiet vienumu **Pievienot savienojumu** un atlasiet **Dynamics 365 Sales**, lai konfigurētu savienojumu.</span><span class="sxs-lookup"><span data-stu-id="2f799-113">Select **Add connection** and choose **Dynamics 365 Sales** to configure the connection.</span></span>

1. <span data-ttu-id="2f799-114">Laukā **Parādāmais nosaukums** piešķiriet savienojumam atpazīstamu nosaukumu.</span><span class="sxs-lookup"><span data-stu-id="2f799-114">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="2f799-115">Parādāmais nosaukums un nosaukuma veids raksturo šo savienojumu.</span><span class="sxs-lookup"><span data-stu-id="2f799-115">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="2f799-116">Ir ieteicams izvēlēties nosaukumu, kas paskaidro savienojuma nolūku.</span><span class="sxs-lookup"><span data-stu-id="2f799-116">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="2f799-117">Izvēlieties, kurš var izmantot šo savienojumu.</span><span class="sxs-lookup"><span data-stu-id="2f799-117">Choose who can use this connection.</span></span> <span data-ttu-id="2f799-118">Ja nesāksit nekādas darbības, noklusējums būs Administratori.</span><span class="sxs-lookup"><span data-stu-id="2f799-118">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="2f799-119">Papildinformāciju skatiet rakstā [Atļaut līdzstrādniekiem izmantot savienojumu eksportam](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="2f799-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="2f799-120">Ievadiet jūsu organizācijas Sales URL laukā **Servera adrese**.</span><span class="sxs-lookup"><span data-stu-id="2f799-120">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="2f799-121">Sadaļā **Servera administratora konts** atlasiet **Pieteikties** un izvēlieties Dynamics 365 Sales kontu.</span><span class="sxs-lookup"><span data-stu-id="2f799-121">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="2f799-122">Kartēt klienta ID lauku uz Dynamics 365 kontaktpersonas ID.</span><span class="sxs-lookup"><span data-stu-id="2f799-122">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="2f799-123">Lai pabeigtu savienošanu, atlasiet **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="2f799-123">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="2f799-124">Eksporta konfigurēšana</span><span class="sxs-lookup"><span data-stu-id="2f799-124">Configure an export</span></span>

<span data-ttu-id="2f799-125">Šo eksportu varat konfigurēt, ja jums ir piekļuve šā veida pieslēgumam.</span><span class="sxs-lookup"><span data-stu-id="2f799-125">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="2f799-126">Papildinformāciju skatiet rakstā [Atļaujas, kas nepieciešamas eksporta konfigurēšanai](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="2f799-126">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="2f799-127">Pārejiet uz **Dati** > **Eksportēšana**.</span><span class="sxs-lookup"><span data-stu-id="2f799-127">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="2f799-128">Lai izveidotu jaunu eksportu, atlasiet **Pievienot galamērķi**.</span><span class="sxs-lookup"><span data-stu-id="2f799-128">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="2f799-129">Laukā **Savienošana eksportam** atlasiet savienojumu no sadaļas Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="2f799-129">In the **Connection for export** field, choose a connection from the Dynamics 365 Sales section.</span></span> <span data-ttu-id="2f799-130">Ja šis sadaļas nosaukums nav redzams, šāda veida savienojumi jums nav pieejami.</span><span class="sxs-lookup"><span data-stu-id="2f799-130">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="2f799-131">Izvēlieties vienu vai vairākus segmentus.</span><span class="sxs-lookup"><span data-stu-id="2f799-131">Choose one or more segments.</span></span>

1. <span data-ttu-id="2f799-132">Atlasiet vienumu **Saglabāt**</span><span class="sxs-lookup"><span data-stu-id="2f799-132">Select **Save**</span></span>

<span data-ttu-id="2f799-133">Eksporta saglabāšana automātiski nepalaiž eksportu.</span><span class="sxs-lookup"><span data-stu-id="2f799-133">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="2f799-134">Eksports tiek palaists ar katru [plānoto atsvaidzināšanu](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="2f799-134">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="2f799-135">Varat arī [eksportēt datus pēc pieprasījuma](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="2f799-135">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
