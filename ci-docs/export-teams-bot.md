---
title: Teams bots Dynamics 365 Customer Insights (priekšskatījums)
description: Ar bota palīdzību uzmeklējiet vienotos klientu profilus pakalpojumā Microsoft Teams.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: d140ae72578b48091a41005c4acafe03bac540da
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195851"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a>Teams bots Dynamics 365 Customer Insights (priekšskatījums)

Pievienojieties Microsoft Teams, lai ļautu botam uzmeklēt vienotos klientu profilus Teams kanālos.

:::image type="content" source="media/teams-bot.png" alt-text="Programmas Teams bots, kas rāda klienta ierakstu":::

## <a name="prerequisites"></a>Priekšnoteikumi

- Vismaz viens [datu avots pievienots](data-sources.md).
- Ir pabeigts [apvienošanas process](data-unification.md).
- Lauki tiek pievienoti [meklēšanas un filtrēšanas indeksam](search-filter-index.md).
- Customer Insights un Teams ir vienā un tajā pašā organizācijā.
- Jūsu vides primārā mērķauditorija ir iestatīta atsevišķiem klientiem. Biznesa konti netiek atbalstīti.


> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWRElj]

## <a name="configure-the-bot"></a>Bota konfigurēšana

1. Dodieties uz **Administrators** > **Savienojumi**.
1. Elementā Microsoft Teams atlasiet **Iestatīt**.
1. Jūs tiksit pārvirzīts uz sadaļu **Programmas** programmā Teams. Varat arī atvērt Teams un atlasīt **Programmas** apakšējā kreisajā stūrī vai [iegūt to tieši no programmas AppSource](https://go.microsoft.com/fwlink/?linkid=2124104).
1. Meklējiet **Customer Insights** un atlasiet programmu.
1. Atlasīt **Pievienot**.
1. Piesakieties programmā Customer Insights programmā Teams. Tiek parādīta sveiciena ziņa.

## <a name="things-you-can-do-with-the-bot"></a>Ko varat paveikt ar botu

Bots nodrošina uzmeklēšanas iespējas vienotiem klientu profiliem.

- Ievadiet **meklēšanu**, kam seko vārds, e-pasta adrese vai jebkurš cits lauks vienotajā klienta profilā, kas tiek pievienots meklēšanas un filtrēšanas indeksam.

  Jūs saņemsit kartīti ar līdz pat 15 laukiem no iegūtā klienta profila. Vairākas atbilstības atgriež rezultātu sarakstu, kurā varat atlasīt profilu. Lai uzmeklētu precīzu atbilstību, pievienojiet meklējamo terminu dubultajās pēdiņās.

- Ja jūsu organizācija uztur vairākas Customer Insights vides vienā organizācijā, ievadiet **switchinstance**, lai izvēlētos, kurā vidē vēlaties savienot robotprogrammatūru.

- Ievadiet **palīdzība**, lai skatītu botam pieejamo komandu sarakstu.  

[!INCLUDE [footer-include](includes/footer-banner.md)]