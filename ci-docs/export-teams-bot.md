---
title: Bots pakalpojumam Microsoft Teams
description: Ar bota palīdzību uzmeklējiet vienotos klientu profilus pakalpojumā Microsoft Teams.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 89a293d5b6f9f5452b2ccba495d2475002806019
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643909"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a>Teams bots Dynamics 365 Customer Insights (priekšskatījums)

Pievienojieties Microsoft Teams, lai ļautu botam uzmeklēt vienotos klientu profilus Teams kanālos.

> [!div class="mx-imgBorder"]
> ![Programmas Teams bots, kas rāda klienta ierakstu.](media/teams-bot.png "Programmas Teams bots rāda klienta ierakstu")

## <a name="prerequisites"></a>Priekšnosacījumi

Lai iestatītu un konfigurētu botu, ir jāizpilda tālāk aprakstītie priekšnosacījumi:

- Ir vismaz viens [pievienotais datu avots](data-sources.md).
- Ir pabeigts [apvienošanas process](data-unification.md).
- Lauki tiek pievienoti [meklēšanas un filtru indeksam](search-filter-index.md).
- Customer Insights un Teams ir vienā un tajā pašā organizācijā.
- Jūsu vides primārā mērķauditorija ir iestatīta atsevišķiem klientiem. Biznesa konti netiek atbalstīti.


> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWRElj]

## <a name="configure-the-bot"></a>Bota konfigurēšana

1. Dodieties uz **AdminExport** > **destinations**.
1. Elementā Microsoft Teams atlasiet **Iestatīt**.
1. Jūs tiksit pārvirzīts uz sadaļu **Programmas** programmā Teams. Varat arī atvērt Teams un atlasīt **Programmas** apakšējā kreisajā stūrī vai [iegūt to tieši no programmas AppSource](https://go.microsoft.com/fwlink/?linkid=2124104).
1. Meklējiet **Customer Insights** un atlasiet programmu.
1. Atlasīt **Pievienot**.
1. Pēc pieteikšanās Customer Insights programmā Teams tiks parādīts sveiciena ziņojums, un jūs varat sākt darbu.

## <a name="things-you-can-do-with-the-bot"></a>Ko varat paveikt ar botu

Bots nodrošina uzmeklēšanas iespējas vienotiem klientu profiliem.

- Ievadiet **meklēt**, kam seko vārds, e-pasta adrese vai jebkurš cits vienotā klienta profila lauks, kurš tiek pievienots meklēšanas un filtra indeksam.

  Jūs saņemsit kartīti ar līdz pat 15 laukiem no iegūtā klienta profila. Vairākas atbilstības atgriež rezultātu sarakstu, kurā varat atlasīt profilu. Lai uzmeklētu precīzu atbilstību, meklēšanas vaicājumu var pievienot pēdiņās.

- Ja jūsu organizācija uztur vairākas Customer Insights vides tajā pašā organizācijā, varat ievadīt **switchinstance**, lai izvēlētos, ar kuru vidi vēlaties savienot botu.

- Ievadiet **palīdzība**, lai skatītu botam pieejamo komandu sarakstu.  


[!INCLUDE [footer-include](includes/footer-banner.md)]