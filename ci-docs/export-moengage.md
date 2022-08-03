---
title: Eksportējiet segmentus uz MoEngage
description: Uzziniet, kā konfigurēt savienojumu un eksportēt uz MoEngage.
ms.date: 07/26/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ffc591c01a5a9434cde41f2da25fa930a515b8c1
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 07/27/2022
ms.locfileid: "9199217"
---
# <a name="export-segments-to-moengage-preview"></a>Eksportējiet segmentus uz MoEngage (priekšskatījums)

Eksportējiet vienotu klientu profilu segmentus uz MoEngage un izmantojiet tos e-pasta mārketingam MoEngage.

## <a name="prerequisites-for-a-connection"></a>Savienojuma priekšnosacījumi

- [MoEngage konts](https://www.moengage.com/) un atbilstošie administratora akreditācijas dati.
- MoEngage API atslēga no iestatījumiem > API MoEngage.
- [Konfigurētie segmenti](segments.md) programmā Customer Insights.

## <a name="known-limitations"></a>Zināmie ierobežojumi

- Līdz 100'000 klientu profiliem eksportēšanai uz MoEngage, kas var aizņemt līdz pat 15 minūtēm. Klientu profilu skaits, ko varat eksportēt uz MoEngage, ir atkarīgs no jūsu līguma ar MoEngage.
- Tikai segmenti.

## <a name="set-up-connection-to-moengage"></a>Savienojuma ar MoEngage iestatīšana

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Dodieties uz **Administrators** > **Savienojumi**.

1. Atlasiet **Pievienot savienojumu** un izvēlieties **MoEngage**, lai konfigurētu savienojumu.

1. Laukā **Parādāmais nosaukums** piešķiriet savienojumam atpazīstamu nosaukumu. Parādāmais nosaukums un nosaukuma veids raksturo šo savienojumu. Ir ieteicams izvēlēties nosaukumu, kas paskaidro savienojuma nolūku.

1. Izvēlieties, kurš var izmantot šo savienojumu. Ja nesāksit nekādas darbības, noklusējums būs Administratori. Papildinformāciju skatiet rakstā [Atļaut līdzstrādniekiem izmantot savienojumu eksportam](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Ievadiet savu [MoEngage Data API ID un API atslēgu](https://developers.moengage.com/hc/articles/4404674776724-Overview#:~:text=Navigate%20to%20Settings%20%3E%20APIs%20%3E%20DATA,ID%20Password%20%2D%20DATA%20API%20KEY).

1. Pārskatiet datu privātumu [un atbilstību](connections.md#data-privacy-and-compliance) un atlasiet **Es piekrītu**.

1. Atlasiet **Izveidot savienojumu**, lai inicializētu savienojumu ar MoEngage.

1. Atlasiet opciju **Pievienot sevi kā eksporta lietotāju** un sniedziet savus Customer Insights akreditācijas datus.

1. Lai pabeigtu savienošanu, atlasiet **Saglabāt**.

## <a name="configure-an-export"></a>Eksporta konfigurēšana

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Pārejiet uz **Dati** > **Eksportēšana**.

1. Lai izveidotu jaunu eksportu, atlasiet **Pievienot eksportu**.

1. **Laukā Savienojums eksportēšanai** izvēlieties savienojumu no sadaļas MoEngage. Ja šis sadaļas nosaukums nav redzams, šāda veida savienojumi jums nav pieejami.

1. **Datu atbilstības noteikšanas** sadaļas laukā **E-pasts** atlasiet lauku, kas norāda klienta e-pasta adresi. Atkārtojiet tās pašas darbības citiem neobligātajiem laukiem.

1. Atlasiet segmentus, kurus vēlaties eksportēt. Mēs izveidosim vienu vai vairākus segmentus ar tādu pašu nosaukumu kā atlasītajiem segmentiem MoEngage sadaļā **Segmenti** > **Pielāgotie segmenti**.

1. Atlasiet **Saglabāt**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
