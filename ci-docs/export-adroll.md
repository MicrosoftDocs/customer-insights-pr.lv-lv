---
title: Segmentu eksportēšana uz AdRoll (priekšskatījums)
description: Uzziniet, kā konfigurēt savienojumu un eksportēt uz AdRoll.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 81adad4caf2d4c6f792bf920b29fc7c67eef42b0
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724721"
---
# <a name="export-segments-to-adroll-preview"></a>Segmentu eksportēšana uz AdRoll (priekšskatījums)

Eksportējiet vienoto klientu profilu segmentus uz AdRoll un izmantojiet tos reklāmai.

## <a name="prerequisites"></a>Priekšnoteikumi

- AdRoll [konts](https://www.adroll.com/) un atbilstošie administratora akreditācijas dati.
- AdRoll [reklāmdevēja ID](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).
- [Konfigurēti segmenti](segments.md) programmā Customer Insights.
- Eksportētajos segmentos vienotajiem klientu profiliem ir lauks, kas norāda e-pasta adresi.

## <a name="known-limitations"></a>Zināmie ierobežojumi

- Privātā saite kombinācijā ar krātuvi Bring your own storage (BYOS) netiek atbalstīta.
- Līdz 250 000 klientu profilu eksportēšanai uz AdRoll, kuru pabeigšana var aizņemt līdz 10 minūtēm. Klientu profilu skaits, ko varat eksportēt pakalpojumā AdRoll, ir atkarīgs no jūsu līguma ar AdRoll.
- Tikai segmenti. Segmentā jābūt vismaz 100 klientu profiliem.

## <a name="set-up-connection-to-adroll"></a>Savienojuma ar AdRoll iestatīšana

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Dodieties uz **Administrators** > **Savienojumi**.

1. Atlasiet **Pievienot savienojumu** un izvēlieties **AdRoll**.

1. Laukā **Parādāmais nosaukums** piešķiriet savienojumam atpazīstamu nosaukumu. Parādāmais nosaukums un nosaukuma veids raksturo šo savienojumu. Ir ieteicams izvēlēties nosaukumu, kas paskaidro savienojuma nolūku.

1. Izvēlieties, kurš var izmantot šo savienojumu. Pēc noklusējuma tie ir tikai administratori. Papildinformāciju skatiet rakstā [Atļaut līdzstrādniekiem izmantot savienojumu eksportam](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Pārskatiet datu konfidencialitāti [un atbilstību](connections.md#data-privacy-and-compliance) un atlasiet **Es piekrītu**.

1. Atlasiet **Izveidot savienojumu, lai inicializētu savienojumu**.

1. Atlasiet **Autentificēties ar AdRoll** un sniedziet savus administratora akreditācijas datus AdRoll.

1. Atlasiet opciju **Pievienot sevi kā eksporta lietotāju** un sniedziet savus Customer Insights akreditācijas datus.

1. Lai pabeigtu savienošanu, atlasiet **Saglabāt**.

## <a name="configure-an-export"></a>Eksporta konfigurēšana

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Pārejiet uz **Dati** > **Eksportēšana**.

1. Atlasiet **Pievienot eksportu**.

1. Laukā **Savienošana eksportam** atlasiet savienojumu no sadaļas AdRoll. Ja nav pieejamu savienojumu, sazinieties ar administratoru.

1. Ievadiet eksportēšanas nosaukumu.

1. Ievadiet savu **AdRoll reklamētāja ID**.

1. **Datu atbilstības noteikšanas** sadaļas laukā **E-pasts** atlasiet lauku, kas norāda klienta e-pasta adresi.

1. Atlasiet segmentus, kurus vēlaties eksportēt.

1. Atlasiet **Saglabāt**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
