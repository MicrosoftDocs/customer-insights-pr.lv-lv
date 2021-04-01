---
title: Customer Insights datu eksportēšana uz Dynamics 365 Sales
description: Uzziniet, kā konfigurēt savienojumu ar Dynamics 365 Sales.
ms.date: 02/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 39ecdf528c6be4d8fb420a52a6ed998317e43bcd
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598118"
---
# <a name="connector-for-dynamics-365-sales-preview"></a><span data-ttu-id="f6c4f-103">Savienotājs ar Dynamics 365 Sales (priekšskatījums)</span><span class="sxs-lookup"><span data-stu-id="f6c4f-103">Connector for Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="f6c4f-104">Izmantojiet Dynamics 365 Sales klientu datus, lai izveidotu mārketinga adresātu sarakstus, tālāko darbību plūsmas un nosūtītu reklāmas.</span><span class="sxs-lookup"><span data-stu-id="f6c4f-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite"></a><span data-ttu-id="f6c4f-105">Priekšnosacījums</span><span class="sxs-lookup"><span data-stu-id="f6c4f-105">Prerequisite</span></span>

1. <span data-ttu-id="f6c4f-106">Lai varētu eksportēt segmentu no programmas Customer Insights uz programmu Sales, programmā Dynamics 365 Sales ir jābūt kontaktpersonu ierakstiem.</span><span class="sxs-lookup"><span data-stu-id="f6c4f-106">Contact records must be present in Dynamics 365 Sales before you can export a segment from Customer Insights to Sales.</span></span> <span data-ttu-id="f6c4f-107">Papildinformācija par kontaktpersonu uzņemšanu programmā [Dynamics 365 Sales, izmantojot Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="f6c4f-107">Read more on how to ingest contacts in [Dynamics 365 Sales using Common Data Services](connect-power-query.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="f6c4f-108">Eksportējot segmentus no auditorijas ieskatiem uz programmu Sales, netiek veidoti jauni kontaktpersonu ieraksti.</span><span class="sxs-lookup"><span data-stu-id="f6c4f-108">Exporting segments from audience insights to Sales will not create new contact records in the Sales instances.</span></span> <span data-ttu-id="f6c4f-109">Kontaktpersonu ieraksti no programmas Sales jābūt uzņemtiem auditorijas ieskatos un izmantotiem kā datu avotam.</span><span class="sxs-lookup"><span data-stu-id="f6c4f-109">The contact records from Sales must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="f6c4f-110">Tie ir jāiekļauj arī vienotā Klienta entītijā, lai kartētu klientu ID uz kontaktu ID pirms segmentu eksportēšanas.</span><span class="sxs-lookup"><span data-stu-id="f6c4f-110">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="configure-the-connector-for-sales"></a><span data-ttu-id="f6c4f-111">Savienotāja konfigurēšana pakalpojumam Sales</span><span class="sxs-lookup"><span data-stu-id="f6c4f-111">Configure the connector for Sales</span></span>

1. <span data-ttu-id="f6c4f-112">Sadaļā Auditorijas ieskati ejiet uz **Administrators** > **Eksportēšanas galamērķi**.</span><span class="sxs-lookup"><span data-stu-id="f6c4f-112">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="f6c4f-113">Sadaļā **Dynamics 365 Sales** atlasiet **Iestatīt**.</span><span class="sxs-lookup"><span data-stu-id="f6c4f-113">Under **Dynamics 365 Sales**, select **Set up**.</span></span>

1. <span data-ttu-id="f6c4f-114">Piešķiriet eksportēšanas galamērķim atpazīstamu nosaukumu laukā **Parādāmais nosaukums**.</span><span class="sxs-lookup"><span data-stu-id="f6c4f-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="f6c4f-115">Ievadiet jūsu organizācijas Sales URL laukā **Servera adrese**.</span><span class="sxs-lookup"><span data-stu-id="f6c4f-115">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="f6c4f-116">Sadaļā **Servera administratora konts** atlasiet **Pieteikties** un izvēlieties Dynamics 365 Sales kontu.</span><span class="sxs-lookup"><span data-stu-id="f6c4f-116">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="f6c4f-117">Kartēt klienta ID lauku uz Dynamics 365 kontaktpersonas ID.</span><span class="sxs-lookup"><span data-stu-id="f6c4f-117">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="f6c4f-118">Atlasiet **Tālāk**.</span><span class="sxs-lookup"><span data-stu-id="f6c4f-118">Select **Next**.</span></span>

1. <span data-ttu-id="f6c4f-119">Izvēlieties vienu vai vairākus segmentus.</span><span class="sxs-lookup"><span data-stu-id="f6c4f-119">Choose one or more segments.</span></span>

1. <span data-ttu-id="f6c4f-120">Atlasiet vienumu **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="f6c4f-120">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="f6c4f-121">Datu eksportēšana</span><span class="sxs-lookup"><span data-stu-id="f6c4f-121">Export the data</span></span>

<span data-ttu-id="f6c4f-122">Datus var [eksportēt pēc pieprasījuma](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="f6c4f-122">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="f6c4f-123">Eksportēšana arī tiks palaista ar katru [plānoto atsvaidzināšanu](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="f6c4f-123">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]