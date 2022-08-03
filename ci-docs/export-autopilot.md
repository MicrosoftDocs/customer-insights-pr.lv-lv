---
title: Segmentu eksportēšana uz Autopilot (priekšskatījums)
description: Uzziniet, kā konfigurēt savienojumu un eksportēt uz Autopilot.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 449d2c5e32697e4a5d2c9dff4a5a1cbdb26aeb4d
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195069"
---
# <a name="export-segments-to-autopilot-preview"></a>Segmentu eksportēšana uz Autopilot (priekšskatījums)

Eksportējiet vienoto klientu profilu segmentus uz Autopilot un izmantojiet tos e-pasta mārketingam lietojumprogrammā Autopilot.

## <a name="prerequisites-for-a-connection"></a>Savienojuma priekšnosacījumi

- Autopilot [konts](https://www.autopilothq.com/) un atbilstošie administratora akreditācijas dati.
- [Autopilot API atslēga](https://autopilot.docs.apiary.io/#)
- [Konfigurētie segmenti](segments.md) programmā Customer Insights.
- Eksportētajos segmentos vienotajiem klientu profiliem ir lauks, kas norāda e-pasta adresi.

## <a name="known-limitations"></a>Zināmie ierobežojumi

- Līdz pat 100 000 klientu profilu eksportēšanai uz Autopilot, kas var aizņemt līdz pat dažām stundām. Klientu profilu skaits, ko varat eksportēt uz Autopilot, ir atkarīgs no jūsu līguma ar Autopilot.
- Tikai segmenti.

## <a name="set-up-connection-to-autopilot"></a>Savienojuma ar Autopilot iestatīšana

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Dodieties uz **Administrators** > **Savienojumi**.

1. Atlasiet **Pievienot savienojumu** un izvēlieties **Autopilot**.

1. Laukā **Parādāmais nosaukums** piešķiriet savienojumam atpazīstamu nosaukumu. Parādāmais nosaukums un nosaukuma veids raksturo šo savienojumu. Ir ieteicams izvēlēties nosaukumu, kas paskaidro savienojuma nolūku.

1. Izvēlieties, kurš var izmantot šo savienojumu. Pēc noklusējuma tie ir tikai administratori. Papildinformāciju skatiet rakstā [Atļaut līdzstrādniekiem izmantot savienojumu eksportam](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Ievadiet savu Autopilot API atslēgu.

1. Pārskatiet datu privātumu [un atbilstību](connections.md#data-privacy-and-compliance) un atlasiet **Es piekrītu**.

1. Atlasiet **Izveidot savienojumu**, lai inicializētu savienojumu.

1. Atlasiet opciju **Pievienot sevi kā eksporta lietotāju** un sniedziet savus Customer Insights akreditācijas datus.

1. Lai pabeigtu savienošanu, atlasiet **Saglabāt**.

## <a name="configure-an-export"></a>Eksporta konfigurēšana

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Pārejiet uz **Dati** > **Eksportēšana**.

1. Atlasiet **Pievienot eksportēšanu**.

1. Laukā **Savienošana eksportam** atlasiet savienojumu no sadaļas Autopilot. Ja nav pieejamu savienojumu, sazinieties ar administratoru.

1. Ievadiet eksportēšanas nosaukumu.

1. **Datu atbilstības noteikšanas** sadaļas laukā **E-pasts** atlasiet lauku, kas norāda klienta e-pasta adresi.

1. Pēc izvēles eksportējiet citus laukus, piemēram **, vārds** un **uzvārds**.

1. Atlasiet segmentus, kurus vēlaties eksportēt, ievērojot zināmos ierobežojumus.

1. Atlasiet **Saglabāt**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
