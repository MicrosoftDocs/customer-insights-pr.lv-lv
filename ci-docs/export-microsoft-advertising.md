---
title: Segmentu eksportēšana uz Microsoft Advertising (priekšskatījums)
description: Uzziniet, kā konfigurēt savienojumu un eksportēt uz Microsoft Advertising.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 44217e7823ffbe14d232b3e33de1b4ea6ed69dcf
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196541"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a>Segmentu eksportēšana uz Microsoft Advertising (priekšskatījums)

Eksportēt Customer Insights segmentus uz Microsoft Advertising, lai izveidotu Customer Match auditorijas. Izmantojiet šīs mērķauditorijas savām reklāmu kampaņām.

## <a name="prerequisites"></a>Priekšnoteikumi

- [Microsoft Advertising konts](https://ads.microsoft.com/) un atbilstošie administratora akreditācijas dati.
- Microsoft reklamēšanas klienta ID un konta ID. Atrodiet klienta ID (`cid`) un konta ID (`aid`) vietrāža URL parametros, kad esat pieteicies programmā Microsoft Advertising.
- Customer Match lietošanas noteikumi tiek pieņemti.
- [Konfigurētie segmenti](segments.md) programmā Customer Insights.
- Eksportētajos segmentos vienotajiem klientu profiliem ir lauks, kas norāda e-pasta adresi.

## <a name="known-limitations"></a>Zināmie ierobežojumi

- Līdz 500 000 klientu profilu eksportēšanai uz Microsoft Advertising, kas var aizņemt līdz pat 10 minūtēm.
- Tikai segmenti.

## <a name="set-up-connection-to-microsoft-advertising"></a>Savienojuma ar Microsoft Advertising iestatīšana

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Dodieties uz **Administrators** > **Savienojumi**.

1. Atlasiet **Pievienot savienojumu** un izvēlieties **Microsoft Advertising**.

1. Laukā **Parādāmais nosaukums** piešķiriet savienojumam atpazīstamu nosaukumu. Parādāmais nosaukums un nosaukuma veids raksturo šo savienojumu. Ir ieteicams izvēlēties nosaukumu, kas paskaidro savienojuma nolūku.

1. Izvēlieties, kurš var izmantot šo savienojumu. Noklusējums ir administratori. Papildinformāciju skatiet rakstā [Atļaut līdzstrādniekiem izmantot savienojumu eksportam](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Ievadiet Microsoft reklamēšanas **klienta ID**.

1. Pārskatiet datu privātumu [un atbilstību](connections.md#data-privacy-and-compliance) un atlasiet **Es piekrītu**.

1. Atlasiet **Izveidot savienojumu**, lai inicializētu savienojumu.

1. Atlasiet **Autentificēties ar Microsoft Advertising** un norādiet savus Microsoft Advertising administratora akreditācijas datus.

1. Atlasiet opciju **Pievienot sevi kā eksporta lietotāju** un sniedziet savus Customer Insights akreditācijas datus.

1. Lai pabeigtu savienošanu, atlasiet **Saglabāt**.

## <a name="configure-an-export"></a>Eksporta konfigurēšana

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Pārejiet uz **Dati** > **Eksportēšana**.

1. Atlasiet **Pievienot eksportēšanu**.

1. Laukā **Savienošana eksportam** atlasiet savienojumu no sadaļas Microsoft Advertising. Ja nav pieejamu savienojumu, sazinieties ar administratoru.

1. Ievadiet eksportēšanas nosaukumu.

1. Atlasiet eksportējamos segmentus. Klientu atbilstības auditorijas programmā Microsoft Advertising tiek automātiski izveidotas ar eksportēšanai atlasīto segmentu nosaukumu. Katrs segments radīs atsevišķu Customer Match auditoriju.

1. Ievadiet savu **Microsoft Advertising klienta ID un konta ID**.

1. **Datu atbilstības noteikšanas** sadaļas laukā **E-pasts** atlasiet lauku, kas norāda klienta e-pasta adresi.

1. Atlasiet **Saglabāt**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
