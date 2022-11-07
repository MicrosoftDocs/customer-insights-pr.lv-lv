---
title: Segmentu eksportēšana uz MoEngage
description: Uzziniet, kā konfigurēt savienojumu un eksportēt uz MoEngage.
ms.date: 07/26/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: df38e9e88a9c116252fba26983b5f3711b46f051
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725275"
---
# <a name="export-segments-to-moengage-preview"></a>Segmentu eksportēšana uz MoEngage (priekšskatījums)

Eksportējiet vienoto klientu profilu segmentus uz MoEngage un izmantojiet tos e-pasta mārketingam pakalpojumā MoEngage.

## <a name="prerequisites-for-a-connection"></a>Savienojuma priekšnosacījumi

- [MoEngage konts](https://www.moengage.com/) un atbilstošie administratora akreditācijas dati.
- MoEngage API atslēga no MoEngage iestatījumiem > API.
- [Konfigurēti segmenti](segments.md) programmā Customer Insights.

## <a name="known-limitations"></a>Zināmie ierobežojumi

- Privātā saite kombinācijā ar krātuvi Bring your own storage (BYOS) netiek atbalstīta.
- Līdz 100'000 klientu profiliem vienā eksporta reizē uz MoEngage, kas var aizņemt līdz 15 minūtēm. Klientu profilu skaits, ko varat eksportēt uz MoEngage, ir atkarīgs no jūsu līguma ar MoEngage.
- Tikai segmenti.

## <a name="set-up-connection-to-moengage"></a>Savienojuma iestatīšana ar MoEngage

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Dodieties uz **Administrators** > **Savienojumi**.

1. Atlasiet **Pievienot savienojumu un izvēlieties** MoEngal **, lai konfigurētu savienojumu**.

1. Laukā **Parādāmais nosaukums** piešķiriet savienojumam atpazīstamu nosaukumu. Parādāmais nosaukums un nosaukuma veids raksturo šo savienojumu. Ir ieteicams izvēlēties nosaukumu, kas paskaidro savienojuma nolūku.

1. Izvēlieties, kurš var izmantot šo savienojumu. Ja nesāksit nekādas darbības, noklusējums būs Administratori. Papildinformāciju skatiet rakstā [Atļaut līdzstrādniekiem izmantot savienojumu eksportam](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Ievadiet savu [MoEngage Data API ID un API atslēgu](https://developers.moengage.com/hc/articles/4404674776724-Overview#:~:text=Navigate%20to%20Settings%20%3E%20APIs%20%3E%20DATA,ID%20Password%20%2D%20DATA%20API%20KEY).

1. Pārskatiet datu konfidencialitāti [un atbilstību](connections.md#data-privacy-and-compliance) un atlasiet **Es piekrītu**.

1. Atlasiet **Izveidot savienojumu, lai inicializētu savienojumu** ar MoEngage.

1. Atlasiet opciju **Pievienot sevi kā eksporta lietotāju** un sniedziet savus Customer Insights akreditācijas datus.

1. Lai pabeigtu savienošanu, atlasiet **Saglabāt**.

## <a name="configure-an-export"></a>Eksporta konfigurēšana

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Pārejiet uz **Dati** > **Eksportēšana**.

1. Lai izveidotu jaunu eksportu, atlasiet **Pievienot eksportu**.

1. **Laukā Savienojums eksportēšanai** izvēlieties savienojumu no MoEngage sadaļas. Ja šis sadaļas nosaukums nav redzams, šāda veida savienojumi jums nav pieejami.

1. **Datu atbilstības noteikšanas** sadaļas laukā **E-pasts** atlasiet lauku, kas norāda klienta e-pasta adresi. Atkārtojiet tās pašas darbības citiem neobligātajiem laukiem.

1. Atlasiet segmentus, kurus vēlaties eksportēt. Mēs izveidosim vienu vai vairākus segmentus ar tādu pašu nosaukumu kā atlasītajiem segmentiem moengage sadaļā Segmenti pielāgotie **segmenti** > **·**.

1. Atlasiet **Saglabāt**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
