---
title: Customer Insights datu eksportēšana uz HubSpot
description: Uzziniet, kā konfigurēt savienojumu un eksportēt uz HubSpot.
ms.date: 09/23/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b34f1d54fa499f6c6b80fa547a8aaf61af3b35a1
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725363"
---
# <a name="export-segments-to-hubspot-preview"></a>Segmentu eksportēšana uz HubSpot (priekšskatījums)

Eksportējiet vienoto klientu profilu segmentus uz HubSpot un izmantojiet tos e-pasta mārketingam.

## <a name="prerequisites-for-a-connection"></a>Savienojuma priekšnosacījumi

- HubSpot [konts](https://www.hubspot.com/) un atbilstošie administratora akreditācijas dati.
- [API atslēga](https://knowledge.hubspot.com/Integrations/How-do-I-get-my-HubSpot-API-key) no HubSpot.
- [Konfigurēti segmenti](segments.md) programmā Customer Insights.

## <a name="known-limitations"></a>Zināmie ierobežojumi

- Privātā saite kombinācijā ar krātuvi Bring your own storage (BYOS) netiek atbalstīta.
- Līdz 100'000 klientu profiliem vienā eksportā uz HubSpot, kas var aizņemt līdz pat 15 minūtēm. Klientu profilu skaits, ko varat eksportēt uz HubSpot, ir atkarīgs un ierobežots no jūsu līguma ar HubSpot.
- Tikai segmenti.

## <a name="set-up-connection-to-hubspot"></a>Savienojuma ar HubSpot iestatīšana

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Dodieties uz **Administrators** > **Savienojumi**.

1. Atlasiet **Pievienot savienojumu un izvēlieties** HubSpot **, lai konfigurētu savienojumu**.

1. Laukā **Parādāmais nosaukums** piešķiriet savienojumam atpazīstamu nosaukumu. Parādāmais nosaukums un nosaukuma veids raksturo šo savienojumu. Ir ieteicams izvēlēties nosaukumu, kas paskaidro savienojuma nolūku.

1. Izvēlieties, kurš var izmantot šo savienojumu. Ja nesāksit nekādas darbības, noklusējums būs Administratori. Papildinformāciju skatiet rakstā [Atļaut līdzstrādniekiem izmantot savienojumu eksportam](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Kad tiek prasīts, ievadiet savus HubSpot akreditācijas datus.

1. Pārskatiet datu konfidencialitāti [un atbilstību](connections.md#data-privacy-and-compliance) un atlasiet **Es piekrītu**.

1. Atlasiet **Izveidot savienojumu, lai inicializētu savienojumu** ar HubSpot.

1. Atlasiet opciju **Pievienot sevi kā eksporta lietotāju** un sniedziet savus Customer Insights akreditācijas datus.

1. Lai pabeigtu savienošanu, atlasiet **Saglabāt**.

## <a name="configure-an-export"></a>Eksporta konfigurēšana

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Pārejiet uz **Dati** > **Eksportēšana**.

1. Lai izveidotu jaunu eksportu, atlasiet **Pievienot eksportu**.

1. **Laukā Savienojums eksportēšanai** izvēlieties savienojumu no sadaļas HubSpot. Ja šis sadaļas nosaukums nav redzams, šāda veida savienojumi jums nav pieejami.

1. **Datu atbilstības noteikšanas** sadaļas laukā **E-pasts** atlasiet lauku, kas norāda klienta e-pasta adresi. Atkārtojiet tās pašas darbības citiem neobligātajiem laukiem.

1. Atlasiet segmentus, kurus vēlaties eksportēt.

1. Atlasiet **Saglabāt**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
