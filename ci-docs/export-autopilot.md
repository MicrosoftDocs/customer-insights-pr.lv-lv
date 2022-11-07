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
ms.openlocfilehash: b4b14ba9de2c7e20175fac664a705f2212a411fd
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724766"
---
# <a name="export-segments-to-autopilot-preview"></a>Segmentu eksportēšana uz Autopilot (priekšskatījums)

Eksportējiet vienoto klientu profilu segmentus uz Autopilot un izmantojiet tos e-pasta mārketingam lietojumprogrammā Autopilot.

## <a name="prerequisites-for-a-connection"></a>Savienojuma priekšnosacījumi

- Autopilota konts [un atbilstošie administratora](https://www.autopilothq.com/) akreditācijas dati.
- Autopilota [API atslēga](https://autopilot.docs.apiary.io/#)
- [Konfigurēti segmenti](segments.md) programmā Customer Insights.
- Eksportētajos segmentos vienotajiem klientu profiliem ir lauks, kas norāda e-pasta adresi.

## <a name="known-limitations"></a>Zināmie ierobežojumi

- Privātā saite kombinācijā ar krātuvi Bring your own storage (BYOS) netiek atbalstīta.
- Līdz 100 000 klientu profilu vienā eksportā uz Autopilot, kas var aizņemt līdz pat dažām stundām. Klientu profilu skaits, ko varat eksportēt uz Autopilot, ir atkarīgs no jūsu līguma ar Autopilot.
- Tikai segmenti.

## <a name="set-up-connection-to-autopilot"></a>Savienojuma ar Autopilot iestatīšana

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Dodieties uz **Administrators** > **Savienojumi**.

1. Atlasiet **Pievienot savienojumu** un izvēlieties **Autopilots**.

1. Laukā **Parādāmais nosaukums** piešķiriet savienojumam atpazīstamu nosaukumu. Parādāmais nosaukums un nosaukuma veids raksturo šo savienojumu. Ir ieteicams izvēlēties nosaukumu, kas paskaidro savienojuma nolūku.

1. Izvēlieties, kurš var izmantot šo savienojumu. Pēc noklusējuma tie ir tikai administratori. Papildinformāciju skatiet rakstā [Atļaut līdzstrādniekiem izmantot savienojumu eksportam](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Ievadiet savu Autopilot API atslēgu.

1. Pārskatiet datu konfidencialitāti [un atbilstību](connections.md#data-privacy-and-compliance) un atlasiet **Es piekrītu**.

1. Atlasiet **Izveidot savienojumu, lai inicializētu savienojumu**.

1. Atlasiet opciju **Pievienot sevi kā eksporta lietotāju** un sniedziet savus Customer Insights akreditācijas datus.

1. Lai pabeigtu savienošanu, atlasiet **Saglabāt**.

## <a name="configure-an-export"></a>Eksporta konfigurēšana

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Pārejiet uz **Dati** > **Eksportēšana**.

1. Atlasiet **Pievienot eksportu**.

1. Laukā **Savienošana eksportam** atlasiet savienojumu no sadaļas Autopilot. Ja nav pieejamu savienojumu, sazinieties ar administratoru.

1. Ievadiet eksportēšanas nosaukumu.

1. **Datu atbilstības noteikšanas** sadaļas laukā **E-pasts** atlasiet lauku, kas norāda klienta e-pasta adresi.

1. Pēc izvēles eksportējiet citus laukus, piemēram **, vārds** un **uzvārds**.

1. Atlasiet eksportējamos segmentus, ievērojot zināmos ierobežojumus.

1. Atlasiet **Saglabāt**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
