---
title: Customer Insights datu eksportēšana uz Dynamics 365 Sales
description: Uzziniet, kā konfigurēt savienojumu ar Dynamics 365 Sales.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: af0824e69dfdf620a0ac756e32a9bd3dd85e5151
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643827"
---
# <a name="connector-for-dynamics-365-sales-preview"></a><span data-ttu-id="2019f-103">Savienotājs ar Dynamics 365 Sales (priekšskatījums)</span><span class="sxs-lookup"><span data-stu-id="2019f-103">Connector for Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="2019f-104">Izmantojiet klientu datus, lai izveidotu mārketinga adresātu sarakstus, tālāko darbību plūsmas un nosūtītu reklāmas ar Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="2019f-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite"></a><span data-ttu-id="2019f-105">Priekšnosacījums</span><span class="sxs-lookup"><span data-stu-id="2019f-105">Prerequisite</span></span>

<span data-ttu-id="2019f-106">Kontaktpersonu ieraksti [no Dynamics 365 Sales, kas uzņemti Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="2019f-106">Contact records [from Dynamics 365 Sales ingested using Common Data Service](connect-power-query.md).</span></span>

## <a name="configure-the-connector-for-sales"></a><span data-ttu-id="2019f-107">Savienotāja konfigurēšana pakalpojumam Sales</span><span class="sxs-lookup"><span data-stu-id="2019f-107">Configure the connector for Sales</span></span>

1. <span data-ttu-id="2019f-108">Sadaļā Auditorijas ieskati ejiet uz **Administrators** > **Eksportēšanas galamērķi**.</span><span class="sxs-lookup"><span data-stu-id="2019f-108">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="2019f-109">Sadaļā **Dynamics 365 Sales** atlasiet **Iestatīt**.</span><span class="sxs-lookup"><span data-stu-id="2019f-109">Under **Dynamics 365 Sales**, select **Set up**.</span></span>

1. <span data-ttu-id="2019f-110">Piešķiriet eksportēšanas galamērķim atpazīstamu nosaukumu laukā **Parādāmais nosaukums**.</span><span class="sxs-lookup"><span data-stu-id="2019f-110">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="2019f-111">Ievadiet jūsu organizācijas Sales URL laukā **Servera adrese**.</span><span class="sxs-lookup"><span data-stu-id="2019f-111">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="2019f-112">Sadaļā **Servera administratora konts** atlasiet **Pieteikties** un izvēlieties Dynamics 365 Sales kontu.</span><span class="sxs-lookup"><span data-stu-id="2019f-112">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="2019f-113">Kartēt klienta ID lauku uz Dynamics 365 kontaktpersonas ID.</span><span class="sxs-lookup"><span data-stu-id="2019f-113">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="2019f-114">Atlasiet **Tālāk**.</span><span class="sxs-lookup"><span data-stu-id="2019f-114">Select **Next**.</span></span>

1. <span data-ttu-id="2019f-115">Izvēlieties vienu vai vairākus segmentus.</span><span class="sxs-lookup"><span data-stu-id="2019f-115">Choose one or more segments.</span></span>

1. <span data-ttu-id="2019f-116">Atlasiet vienumu **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="2019f-116">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="2019f-117">Datu eksportēšana</span><span class="sxs-lookup"><span data-stu-id="2019f-117">Export the data</span></span>

<span data-ttu-id="2019f-118">Datus var [eksportēt pēc pieprasījuma](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="2019f-118">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="2019f-119">Eksportēšana arī tiks palaista ar katru [plānoto atsvaidzināšanu](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="2019f-119">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
