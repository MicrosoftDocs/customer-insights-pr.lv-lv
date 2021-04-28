---
title: Customer Insights datu eksportēšana uz Dynamics 365 Marketing
description: Uzziniet, kā konfigurēt savienojumu un eksportēt uz Dynamics 365 Marketing.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: a13f6f81f5e2570d3302d88c02755f1d86321a01
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759646"
---
# <a name="use-segments-in-dynamics-365-marketing-preview"></a><span data-ttu-id="f412f-103">Segmentu lietošana Dynamics 365 Marketing (priekšskatījums)</span><span class="sxs-lookup"><span data-stu-id="f412f-103">Use segments in Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="f412f-104">Izmantojiet [segmentus](segments.md) kampaņu veidošanai un saziņai ar specifisku klientu grupu pakalpojumā Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="f412f-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="f412f-105">Papildinformāciju skatiet tēmā [Segmentu izmantošana no Dynamics 365 Customer Insights ar Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="f412f-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite-for-a-connection"></a><span data-ttu-id="f412f-106">Savienojuma priekšnosacījums</span><span class="sxs-lookup"><span data-stu-id="f412f-106">Prerequisite for a connection</span></span>

- <span data-ttu-id="f412f-107">Lai varētu eksportēt segmentu no programmas Customer Insights uz programmu Marketing, programmā Dynamics 365 Marketing ir jābūt kontaktpersonu ierakstiem.</span><span class="sxs-lookup"><span data-stu-id="f412f-107">Contact records must be present in Dynamics 365 Marketing before you can export a segment from Customer Insights to Marketing.</span></span> <span data-ttu-id="f412f-108">Papildinformācija par kontaktpersonu uzņemšanu programmā [Dynamics 365 Marketing, izmantojot Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="f412f-108">Read more on how to ingest contacts in [Dynamics 365 Marketing using Common Data Services](connect-power-query.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="f412f-109">Eksportējot segmentus no auditorijas ieskatiem uz programmu Marketing, netiek veidoti jauni kontaktpersonu ieraksti.</span><span class="sxs-lookup"><span data-stu-id="f412f-109">Exporting segments from audience insights to Marketing will not create new contact records in the Marketing instances.</span></span> <span data-ttu-id="f412f-110">Kontaktpersonu ieraksti no programmas Marketing jābūt uzņemtiem auditorijas ieskatos un izmantotiem kā datu avotam.</span><span class="sxs-lookup"><span data-stu-id="f412f-110">The contact records from Marketing must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="f412f-111">Tie ir jāiekļauj arī vienotā Klienta entītijā, lai kartētu klientu ID uz kontaktu ID pirms segmentu eksportēšanas.</span><span class="sxs-lookup"><span data-stu-id="f412f-111">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="set-up-connection-to-marketing"></a><span data-ttu-id="f412f-112">Savienojuma ar Marketing iestatīšana</span><span class="sxs-lookup"><span data-stu-id="f412f-112">Set up connection to Marketing</span></span>

1. <span data-ttu-id="f412f-113">Dodieties uz **Administrators** > **Savienojumi**.</span><span class="sxs-lookup"><span data-stu-id="f412f-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="f412f-114">Atlasiet vienumu **Pievienot savienojumu** un atlasiet **Dynamics 365 Marketing**, lai konfigurētu savienojumu.</span><span class="sxs-lookup"><span data-stu-id="f412f-114">Select **Add connection** and choose **Dynamics 365 Marketing** to configure the connection.</span></span>

1. <span data-ttu-id="f412f-115">Laukā **Parādāmais nosaukums** piešķiriet savienojumam atpazīstamu nosaukumu.</span><span class="sxs-lookup"><span data-stu-id="f412f-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="f412f-116">Parādāmais nosaukums un nosaukuma veids raksturo šo savienojumu.</span><span class="sxs-lookup"><span data-stu-id="f412f-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="f412f-117">Ir ieteicams izvēlēties nosaukumu, kas paskaidro savienojuma nolūku.</span><span class="sxs-lookup"><span data-stu-id="f412f-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="f412f-118">Izvēlieties, kurš var izmantot šo savienojumu.</span><span class="sxs-lookup"><span data-stu-id="f412f-118">Choose who can use this connection.</span></span> <span data-ttu-id="f412f-119">Ja nesāksit nekādas darbības, noklusējums būs Administratori.</span><span class="sxs-lookup"><span data-stu-id="f412f-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="f412f-120">Papildinformāciju skatiet rakstā [Atļaut līdzstrādniekiem izmantot savienojumu eksportam](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="f412f-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="f412f-121">Ievadiet jūsu organizācijas Marketing URL laukā **Servera adrese**.</span><span class="sxs-lookup"><span data-stu-id="f412f-121">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="f412f-122">Sadaļā **Servera administratora konts** atlasiet **Pieteikties** un izvēlieties Dynamics 365 Marketing kontu.</span><span class="sxs-lookup"><span data-stu-id="f412f-122">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="f412f-123">Kartēt klienta ID lauku uz Dynamics 365 kontaktpersonas ID.</span><span class="sxs-lookup"><span data-stu-id="f412f-123">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="f412f-124">Lai pabeigtu savienošanu, atlasiet **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="f412f-124">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="f412f-125">Eksporta konfigurēšana</span><span class="sxs-lookup"><span data-stu-id="f412f-125">Configure an export</span></span>

<span data-ttu-id="f412f-126">Šo eksportu varat konfigurēt, ja jums ir piekļuve šā veida pieslēgumam.</span><span class="sxs-lookup"><span data-stu-id="f412f-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="f412f-127">Papildinformāciju skatiet rakstā [Atļaujas, kas nepieciešamas eksporta konfigurēšanai](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="f412f-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="f412f-128">Pārejiet uz **Dati** > **Eksportēšana**.</span><span class="sxs-lookup"><span data-stu-id="f412f-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="f412f-129">Lai izveidotu jaunu eksportu, atlasiet **Pievienot galamērķi**.</span><span class="sxs-lookup"><span data-stu-id="f412f-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="f412f-130">Laukā **Savienošana eksportam** atlasiet savienojumu no sadaļas Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="f412f-130">In the **Connection for export** field, choose a connection from the Dynamics 365 Marketing section.</span></span> <span data-ttu-id="f412f-131">Ja šis sadaļas nosaukums nav redzams, šāda veida savienojumi jums nav pieejami.</span><span class="sxs-lookup"><span data-stu-id="f412f-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="f412f-132">Izvēlieties vienu vai vairākus segmentus.</span><span class="sxs-lookup"><span data-stu-id="f412f-132">Choose one or more segments.</span></span>

1. <span data-ttu-id="f412f-133">Atlasiet vienumu **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="f412f-133">Select **Save**.</span></span>

<span data-ttu-id="f412f-134">Eksporta saglabāšana automātiski nepalaiž eksportu.</span><span class="sxs-lookup"><span data-stu-id="f412f-134">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="f412f-135">Eksports tiek palaists ar katru [plānoto atsvaidzināšanu](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="f412f-135">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="f412f-136">Varat arī [eksportēt datus pēc pieprasījuma](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="f412f-136">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
