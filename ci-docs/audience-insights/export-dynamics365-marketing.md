---
title: Customer Insights datu eksportēšana uz Dynamics 365 Marketing
description: Uzziniet, kā konfigurēt savienojumu ar Dynamics 365 Marketing.
ms.date: 02/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 892aff643872f11307a2c43e5670edab657d7848
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597612"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a><span data-ttu-id="39c88-103">Savienotājs ar Dynamics 365 Marketing (priekšskatījums)</span><span class="sxs-lookup"><span data-stu-id="39c88-103">Connector for Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="39c88-104">Izmantojiet [segmentus](segments.md) kampaņu veidošanai un saziņai ar specifisku klientu grupu pakalpojumā Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="39c88-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="39c88-105">Papildinformāciju skatiet tēmā [Segmentu izmantošana no Dynamics 365 Customer Insights ar Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="39c88-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite"></a><span data-ttu-id="39c88-106">Priekšnosacījums</span><span class="sxs-lookup"><span data-stu-id="39c88-106">Prerequisite</span></span>

- <span data-ttu-id="39c88-107">Lai varētu eksportēt segmentu no programmas Customer Insights uz programmu Marketing, programmā Dynamics 365 Marketing ir jābūt kontaktpersonu ierakstiem.</span><span class="sxs-lookup"><span data-stu-id="39c88-107">Contact records must be present in Dynamics 365 Marketing before you can export a segment from Customer Insights to Marketing.</span></span> <span data-ttu-id="39c88-108">Papildinformācija par kontaktpersonu uzņemšanu programmā [Dynamics 365 Marketing, izmantojot Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="39c88-108">Read more on how to ingest contacts in [Dynamics 365 Marketing using Common Data Services](connect-power-query.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="39c88-109">Eksportējot segmentus no auditorijas ieskatiem uz programmu Marketing, netiek veidoti jauni kontaktpersonu ieraksti.</span><span class="sxs-lookup"><span data-stu-id="39c88-109">Exporting segments from audience insights to Marketing will not create new contact records in the Marketing instances.</span></span> <span data-ttu-id="39c88-110">Kontaktpersonu ieraksti no programmas Marketing jābūt uzņemtiem auditorijas ieskatos un izmantotiem kā datu avotam.</span><span class="sxs-lookup"><span data-stu-id="39c88-110">The contact records from Marketing must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="39c88-111">Tie ir jāiekļauj arī vienotā Klienta entītijā, lai kartētu klientu ID uz kontaktu ID pirms segmentu eksportēšanas.</span><span class="sxs-lookup"><span data-stu-id="39c88-111">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="configure-the-connector-for-marketing"></a><span data-ttu-id="39c88-112">Savienotāja konfigurēšana pakalpojumam Marketing</span><span class="sxs-lookup"><span data-stu-id="39c88-112">Configure the connector for Marketing</span></span>

1. <span data-ttu-id="39c88-113">Sadaļā Auditorijas ieskati ejiet uz **Administrators** > **Eksportēšanas galamērķi**.</span><span class="sxs-lookup"><span data-stu-id="39c88-113">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="39c88-114">Sadaļā **Dynamics 365 Marketing** atlasiet **Iestatīt**.</span><span class="sxs-lookup"><span data-stu-id="39c88-114">Under **Dynamics 365 Marketing**, select **Set up**.</span></span>

1. <span data-ttu-id="39c88-115">Piešķiriet eksportēšanas galamērķim atpazīstamu nosaukumu laukā **Parādāmais nosaukums**.</span><span class="sxs-lookup"><span data-stu-id="39c88-115">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="39c88-116">Ievadiet jūsu organizācijas Marketing URL laukā **Servera adrese**.</span><span class="sxs-lookup"><span data-stu-id="39c88-116">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="39c88-117">Sadaļā **Servera administratora konts** atlasiet **Pieteikties** un izvēlieties Dynamics 365 Marketing kontu.</span><span class="sxs-lookup"><span data-stu-id="39c88-117">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="39c88-118">Kartēt klienta ID lauku uz Dynamics 365 kontaktpersonas ID.</span><span class="sxs-lookup"><span data-stu-id="39c88-118">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="39c88-119">Atlasiet **Tālāk**.</span><span class="sxs-lookup"><span data-stu-id="39c88-119">Select **Next**.</span></span>

1. <span data-ttu-id="39c88-120">Izvēlieties vienu vai vairākus segmentus.</span><span class="sxs-lookup"><span data-stu-id="39c88-120">Choose one or more segments.</span></span>

1. <span data-ttu-id="39c88-121">Atlasiet vienumu **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="39c88-121">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="39c88-122">Datu eksportēšana</span><span class="sxs-lookup"><span data-stu-id="39c88-122">Export the data</span></span>

<span data-ttu-id="39c88-123">Datus var [eksportēt pēc pieprasījuma](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="39c88-123">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="39c88-124">Eksportēšana arī tiks palaista ar katru [plānoto atsvaidzināšanu](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="39c88-124">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]