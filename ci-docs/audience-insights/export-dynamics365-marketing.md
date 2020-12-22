---
title: Customer Insights datu eksportēšana uz Dynamics 365 Marketing
description: Uzziniet, kā konfigurēt savienojumu ar Dynamics 365 Marketing.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 163387779b64bd78ef08e2d96a5f1c9615062f28
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643782"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a><span data-ttu-id="7066e-103">Savienotājs ar Dynamics 365 Marketing (priekšskatījums)</span><span class="sxs-lookup"><span data-stu-id="7066e-103">Connector for Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="7066e-104">Izmantojiet [segmentus](segments.md) kampaņu veidošanai un saziņai ar specifisku klientu grupu pakalpojumā Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="7066e-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="7066e-105">Papildinformāciju skatiet tēmā [Segmentu izmantošana no Dynamics 365 Customer Insights ar Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="7066e-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite"></a><span data-ttu-id="7066e-106">Priekšnosacījums</span><span class="sxs-lookup"><span data-stu-id="7066e-106">Prerequisite</span></span>

<span data-ttu-id="7066e-107">Kontaktpersonu ieraksti [no Dynamics 365 Marketing, kas uzņemti Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="7066e-107">Contact records [from Dynamics 365 Marketing ingested Common Data Service](connect-power-query.md).</span></span>

## <a name="configure-the-connector-for-marketing"></a><span data-ttu-id="7066e-108">Savienotāja konfigurēšana pakalpojumam Marketing</span><span class="sxs-lookup"><span data-stu-id="7066e-108">Configure the connector for Marketing</span></span>

1. <span data-ttu-id="7066e-109">Sadaļā Auditorijas ieskati ejiet uz **Administrators** > **Eksportēšanas galamērķi**.</span><span class="sxs-lookup"><span data-stu-id="7066e-109">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="7066e-110">Sadaļā **Dynamics 365 Marketing** atlasiet **Iestatīt**.</span><span class="sxs-lookup"><span data-stu-id="7066e-110">Under **Dynamics 365 Marketing**, select **Set up**.</span></span>

1. <span data-ttu-id="7066e-111">Piešķiriet eksportēšanas galamērķim atpazīstamu nosaukumu laukā **Parādāmais nosaukums**.</span><span class="sxs-lookup"><span data-stu-id="7066e-111">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="7066e-112">Ievadiet jūsu organizācijas Marketing URL laukā **Servera adrese**.</span><span class="sxs-lookup"><span data-stu-id="7066e-112">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="7066e-113">Sadaļā **Servera administratora konts** atlasiet **Pieteikties** un izvēlieties Dynamics 365 Marketing kontu.</span><span class="sxs-lookup"><span data-stu-id="7066e-113">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="7066e-114">Kartēt klienta ID lauku uz Dynamics 365 kontaktpersonas ID.</span><span class="sxs-lookup"><span data-stu-id="7066e-114">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="7066e-115">Atlasiet **Tālāk**.</span><span class="sxs-lookup"><span data-stu-id="7066e-115">Select **Next**.</span></span>

1. <span data-ttu-id="7066e-116">Izvēlieties vienu vai vairākus segmentus.</span><span class="sxs-lookup"><span data-stu-id="7066e-116">Choose one or more segments.</span></span>

1. <span data-ttu-id="7066e-117">Atlasiet vienumu **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="7066e-117">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="7066e-118">Datu eksportēšana</span><span class="sxs-lookup"><span data-stu-id="7066e-118">Export the data</span></span>

<span data-ttu-id="7066e-119">Datus var [eksportēt pēc pieprasījuma](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="7066e-119">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="7066e-120">Eksportēšana arī tiks palaista ar katru [plānoto atsvaidzināšanu](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="7066e-120">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
