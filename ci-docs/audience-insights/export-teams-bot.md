---
title: Bots pakalpojumam Microsoft Teams
description: Ar bota palīdzību uzmeklējiet vienotos klientu profilus pakalpojumā Microsoft Teams.
ms.date: 04/21/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 03299610fd41a7e142e3c9723fad56ce7f90e083
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267961"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a><span data-ttu-id="b104c-103">Teams bots Dynamics 365 Customer Insights (priekšskatījums)</span><span class="sxs-lookup"><span data-stu-id="b104c-103">Teams bot for Dynamics 365 Customer Insights (preview)</span></span>

<span data-ttu-id="b104c-104">Pievienojieties Microsoft Teams, lai ļautu botam uzmeklēt vienotos klientu profilus Teams kanālos.</span><span class="sxs-lookup"><span data-stu-id="b104c-104">Connect with Microsoft Teams to let a bot look up unified customer profiles in Teams channels.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="b104c-105">![Programmas Teams bots, kas rāda klienta ierakstu](media/teams-bot.png "Programmas Teams bots rāda klienta ierakstu")</span><span class="sxs-lookup"><span data-stu-id="b104c-105">![Teams bot showing a customer record](media/teams-bot.png "Teams bot showing a customer record")</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b104c-106">Priekšnosacījumi</span><span class="sxs-lookup"><span data-stu-id="b104c-106">Prerequisites</span></span>

<span data-ttu-id="b104c-107">Lai iestatītu un konfigurētu botu, ir jāizpilda tālāk aprakstītie priekšnosacījumi:</span><span class="sxs-lookup"><span data-stu-id="b104c-107">To set up and configure the bot, the following prerequisites must be met:</span></span>

- <span data-ttu-id="b104c-108">Ir vismaz viens [pievienotais datu avots](data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="b104c-108">There's at least one [data source added](data-sources.md).</span></span>
- <span data-ttu-id="b104c-109">Ir pabeigts [apvienošanas process](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="b104c-109">The [unification process](data-unification.md) is complete.</span></span>
- <span data-ttu-id="b104c-110">Lauki tiek pievienoti [meklēšanas un filtru indeksam](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="b104c-110">Fields are added to the [search and filter index](search-filter-index.md).</span></span>
- <span data-ttu-id="b104c-111">Customer Insights un Teams ir vienā un tajā pašā organizācijā.</span><span class="sxs-lookup"><span data-stu-id="b104c-111">Customer Insights and Teams are in the same organization.</span></span>

## <a name="configure-the-bot"></a><span data-ttu-id="b104c-112">Bota konfigurēšana</span><span class="sxs-lookup"><span data-stu-id="b104c-112">Configure the bot</span></span>

1. <span data-ttu-id="b104c-113">Sadaļā Auditorijas ieskati ejiet uz **Administrators** > **Eksportēšanas galamērķi**.</span><span class="sxs-lookup"><span data-stu-id="b104c-113">In audience insights, go to **Admin** > **Export Destinations**.</span></span>
1. <span data-ttu-id="b104c-114">Elementā Microsoft Teams atlasiet **Iestatīt**.</span><span class="sxs-lookup"><span data-stu-id="b104c-114">On the Microsoft Teams tile, select **Set up**.</span></span>
1. <span data-ttu-id="b104c-115">Jūs tiksit pārvirzīts uz sadaļu **Programmas** programmā Teams.</span><span class="sxs-lookup"><span data-stu-id="b104c-115">You're redirected to the **Apps** area in Teams.</span></span> <span data-ttu-id="b104c-116">Varat arī atvērt Teams un atlasīt **Programmas** apakšējā kreisajā stūrī vai [iegūt to tieši no programmas AppSource](https://go.microsoft.com/fwlink/?linkid=2124104).</span><span class="sxs-lookup"><span data-stu-id="b104c-116">You can also open Teams and select **Apps** in the bottom-left corner or [get it from AppSource](https://go.microsoft.com/fwlink/?linkid=2124104) directly.</span></span>
1. <span data-ttu-id="b104c-117">Meklējiet **Customer Insights** un atlasiet programmu.</span><span class="sxs-lookup"><span data-stu-id="b104c-117">Search for **Customer Insights** and select the app.</span></span>
1. <span data-ttu-id="b104c-118">Atlasīt **Pievienot**.</span><span class="sxs-lookup"><span data-stu-id="b104c-118">Select **Add**.</span></span>
1. <span data-ttu-id="b104c-119">Pēc pieteikšanās Customer Insights programmā Teams tiks parādīts sveiciena ziņojums, un jūs varat sākt darbu.</span><span class="sxs-lookup"><span data-stu-id="b104c-119">After signing in to Customer Insights in Teams, you'll see a welcome message and can get started.</span></span>

## <a name="things-you-can-do-with-the-bot"></a><span data-ttu-id="b104c-120">Ko varat paveikt ar botu</span><span class="sxs-lookup"><span data-stu-id="b104c-120">Things you can do with the bot</span></span>

<span data-ttu-id="b104c-121">Bots nodrošina uzmeklēšanas iespējas vienotiem klientu profiliem.</span><span class="sxs-lookup"><span data-stu-id="b104c-121">The bot provides lookup capabilities for unified customer profiles.</span></span>

- <span data-ttu-id="b104c-122">Ievadiet **meklēt**, kam seko vārds, e-pasta adrese vai jebkurš cits vienotā klienta profila lauks, kurš tiek pievienots meklēšanas un filtra indeksam.</span><span class="sxs-lookup"><span data-stu-id="b104c-122">Enter **search** followed by a name, email address, or any other field on the unified customer profile that is added to the search and filter index.</span></span>

  <span data-ttu-id="b104c-123">Jūs saņemsit kartīti ar līdz pat 15 laukiem no iegūtā klienta profila.</span><span class="sxs-lookup"><span data-stu-id="b104c-123">You'll get a card with up to 15 fields from the resulting customer profile.</span></span> <span data-ttu-id="b104c-124">Vairākas atbilstības atgriež rezultātu sarakstu, kurā varat atlasīt profilu.</span><span class="sxs-lookup"><span data-stu-id="b104c-124">Multiple matches return a list of results where you can select a profile.</span></span> <span data-ttu-id="b104c-125">Lai uzmeklētu precīzu atbilstību, meklēšanas vaicājumu var pievienot pēdiņās.</span><span class="sxs-lookup"><span data-stu-id="b104c-125">You can add the search term in double quotes to look up an exact match.</span></span>

- <span data-ttu-id="b104c-126">Ja jūsu organizācija uztur vairākas Customer Insights vides tajā pašā organizācijā, varat ievadīt **switchinstance**, lai izvēlētos, ar kuru vidi vēlaties savienot botu.</span><span class="sxs-lookup"><span data-stu-id="b104c-126">If your organization maintains multiple Customer Insights environments in the same organization, you can enter **switchinstance** to choose which environment you want to connect the bot to.</span></span>

- <span data-ttu-id="b104c-127">Ievadiet **palīdzība**, lai skatītu botam pieejamo komandu sarakstu.</span><span class="sxs-lookup"><span data-stu-id="b104c-127">Enter **help** to see a list of available commands for the bot.</span></span>  


[!INCLUDE[footer-include](../includes/footer-banner.md)]