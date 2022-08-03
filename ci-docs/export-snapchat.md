---
title: Segmentu sarakstu eksportēšana uz Snapchat (priekšskatījums)
description: Uzziniet, kā konfigurēt savienojumu un eksportēt uz Snapchat.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 85443dcb54ebd58182997fbb56a738901f2a051f
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195391"
---
# <a name="export-segments-to-snapchat-preview"></a>Segmentu sarakstu eksportēšana uz Snapchat (priekšskatījums)

Eksportējiet vienoto klientu profilu segmentus uz Snapchat un izmantojiet tos reklāmā.

## <a name="prerequisites"></a>Priekšnoteikumi

- Snapchat [biznesa konts](https://business.snapchat.com/), [Snapchat Ads konts](https://ads.snapchat.com/) un atbilstošie administratora akreditācijas dati. Jums ir jābūt vismaz organizācijas konta dalībniekam un konkrēta reklāmas konta datu pārvaldniekam.
- Vismaz viena auditorija Snapchat auditorijas menedžerī, kas ir SAM tipa (Snap Audience Match).
- Snapchat segments [/ auditorijas ID](https://businesshelp.snapchat.com/s/article/custom-audiences). Auditorijas ID var atrast vietrādī URL pēc auditorijas atlasīšanas Snapchat Audience Manager.
- [Konfigurētie segmenti](segments.md) programmā Customer Insights.
- Eksportētajos segmentos vienotajiem klientu profiliem ir lauks, kas norāda e-pasta adresi.

## <a name="known-limitations"></a>Zināmie ierobežojumi

- Līdz 1 miljonam klientu profilu, kuru pabeigšana var aizņemt līdz 15 minūtēm.
- Tikai segmenti.

## <a name="set-up-connection-to-snapchat"></a>Savienojuma ar Snapchat iestatīšana

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Dodieties uz **Administrators** > **Savienojumi**.

1. Atlasiet **Pievienot savienojumu** un izvēlieties **Snapchat**.

1. Laukā **Parādāmais nosaukums** piešķiriet savienojumam atpazīstamu nosaukumu. Parādāmais nosaukums un nosaukuma veids raksturo šo savienojumu. Ir ieteicams izvēlēties nosaukumu, kas paskaidro savienojuma nolūku.

1. Izvēlieties, kurš var izmantot šo savienojumu. Pēc noklusējuma tie ir tikai administratori. Papildinformāciju skatiet rakstā [Atļaut līdzstrādniekiem izmantot savienojumu eksportam](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Pārskatiet datu privātumu [un atbilstību](connections.md#data-privacy-and-compliance) un atlasiet **Es piekrītu**.

1. Atlasiet **Izveidot savienojumu**, lai inicializētu savienojumu.

1. Atlasiet **Autentificēt ar Snapchat** un norādiet savus Snapchat administratora akreditācijas datus.

1. Atlasiet opciju **Pievienot sevi kā eksporta lietotāju** un sniedziet savus Customer Insights akreditācijas datus.

1. Lai pabeigtu savienošanu, atlasiet **Saglabāt**.

## <a name="configure-an-export"></a>Eksporta konfigurēšana

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Pārejiet uz **Dati** > **Eksportēšana**.

1. Atlasiet **Pievienot eksportēšanu**.

1. Laukā **Savienošana eksportam** atlasiet savienojumu no sadaļas Snapchat. Ja nav pieejamu savienojumu, sazinieties ar administratoru.

1. Ievadiet eksportēšanas nosaukumu.

1. Ievadiet Snapchat segmenta **/ auditorijas ID**.

1. **Datu atbilstības noteikšanas** sadaļas laukā **E-pasts** atlasiet lauku, kas norāda klienta e-pasta adresi.

1. Atlasiet segmentus, kurus vēlaties eksportēt.

1. Atlasiet **Saglabāt**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
