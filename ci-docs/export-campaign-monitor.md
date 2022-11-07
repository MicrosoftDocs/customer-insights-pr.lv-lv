---
title: Segmentu eksportēšana uz Campaign Monitor (priekšskatījums)
description: Uzziniet, kā konfigurēt savienojumu un eksportēt uz Campaign Monitor.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 82303c7bcb269ee68419c9639ee743e13451f273
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724693"
---
# <a name="export-segments-to-campaign-monitor-preview"></a>Segmentu eksportēšana uz Campaign Monitor (priekšskatījums)

Eksportējiet vienoto klientu profilu segmentus uz Campaign Monitor un izmantojiet tos mārketinga darbībās.

## <a name="prerequisites"></a>Priekšnoteikumi

- Kampaņu pārraudzības [konts](https://www.campaignmonitor.com/) un atbilstošie administratora akreditācijas dati.
- Kampaņas pārraudzības [saraksta ID](https://www.campaignmonitor.com/api/getting-started/#your-list-id).
- Ģenerēta [API atslēga](https://www.campaignmonitor.com/api/getting-started/) no **kampaņas pārraudzības konta iestatījumiem**, lai iegūtu API saraksta ID.
- [Konfigurēti segmenti](segments.md) programmā Customer Insights.
- Eksportētajos segmentos vienotajiem klientu profiliem ir lauks, kas norāda e-pasta adresi.

## <a name="known-limitations"></a>Zināmie ierobežojumi

- Privātā saite kombinācijā ar krātuvi Bring your own storage (BYOS) netiek atbalstīta.
- Līdz 1 miljonam klientu profilu vienam eksportam uz kampaņu pārraudzību, kas var aizņemt līdz 20 minūtēm. Klientu profilu skaits, ko varat eksportēt kampaņu pārraugā, ir atkarīgs no jūsu līguma ar Campaign Monitor.
- Tikai segmenti.

## <a name="set-up-connection-to-campaign-monitor"></a>Savienojuma ar Campaign Monitor iestatīšana

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Dodieties uz **Administrators** > **Savienojumi**.

1. Atlasiet **Pievienot savienojumu** un izvēlieties **Kampaņas pārraudzība**.

1. Laukā **Parādāmais nosaukums** piešķiriet savienojumam atpazīstamu nosaukumu. Parādāmais nosaukums un nosaukuma veids raksturo šo savienojumu. Ir ieteicams izvēlēties nosaukumu, kas paskaidro savienojuma nolūku.

1. Izvēlieties, kurš var izmantot šo savienojumu. Pēc noklusējuma tie ir tikai administratori. Papildinformāciju skatiet rakstā [Atļaut līdzstrādniekiem izmantot savienojumu eksportam](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Pārskatiet datu konfidencialitāti [un atbilstību](connections.md#data-privacy-and-compliance) un atlasiet **Es piekrītu**.

1. Lai uzsāktu savienojumu ar Campaign Monitor, atlasiet **Savienot**.

1. Atlasiet **Autentificēt ar Campaign Monitor** un norādiet savus Campaign Monitor administratora akreditācijas datus.

1. Atlasiet opciju **Pievienot sevi kā eksporta lietotāju** un sniedziet savus Customer Insights akreditācijas datus.

1. Lai pabeigtu savienošanu, atlasiet **Saglabāt**.

## <a name="configure-an-export"></a>Eksporta konfigurēšana

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Pārejiet uz **Dati** > **Eksportēšana**.

1. Lai izveidotu jaunu eksportu, atlasiet **Pievienot eksportu**.

1. Laukā **Savienošana eksportam** atlasiet savienojumu no sadaļas Campaign Monitor. Ja nav pieejamu savienojumu, sazinieties ar administratoru.

1. Ievadiet eksportēšanas nosaukumu.

1. Ievadiet kampaņas **pārraudzības saraksta ID.**

1. **Datu atbilstības noteikšanas** sadaļas laukā **E-pasts** atlasiet lauku, kas norāda klienta e-pasta adresi. Segmenti ir obligāti jāeksportē uz Campaign Monitor.

1. Atlasiet segmentus, kurus vēlaties eksportēt.

1. Atlasiet **Saglabāt**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
