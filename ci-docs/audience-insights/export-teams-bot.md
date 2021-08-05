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
ms.openlocfilehash: e563619f40be859f3f02638adbd60b80423182b3
ms.sourcegitcommit: dab2cbf818fafc9436e685376df94c5e44e4b144
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 07/13/2021
ms.locfileid: "6554396"
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

## <a name="configure-the-bot"></a>Bota konfigurēšana

1. Sadaļā Auditorijas ieskati ejiet uz **Administrators** > **Eksportēšanas galamērķi**.
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


[!INCLUDE[footer-include](../includes/footer-banner.md)]