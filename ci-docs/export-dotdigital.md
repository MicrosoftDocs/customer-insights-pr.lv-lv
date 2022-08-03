---
title: Segmentu eksportēšana uz DotDigital (priekšskatījums)
description: Uzziniet, kā konfigurēt savienojumu un eksportēt uz DotDigital.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: cabaea84e31f8fe97bc558a8dca8d93bc40f43b7
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196081"
---
# <a name="export-segments-to-dotdigital-preview"></a>Segmentu eksportēšana uz DotDigital (priekšskatījums)

Eksportējiet vienoto klientu profilu segmentus uz DotDigital adrešu grāmatām un izmantojiet tās kampaņām, e-pasta mārketingā un klientu segmentu izveidei ar DotDigital.

## <a name="prerequisites"></a>Priekšnoteikumi

- [DotDigital konts](https://dotdigital.com/) un [API lietotājs](https://support.dotdigital.com/hc/articles/115001718730-How-do-I-create-an-API-user).
- DotDigital ID no jaunas [vai esošas](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book) adrešu grāmatas DotDigital. ID var atrast URL, kad atlasāt un atverat adrešu grāmatu.
- [Konfigurētie segmenti](segments.md) programmā Customer Insights.
- Eksportētajos segmentos vienotajiem klientu profiliem ir lauks, kas norāda e-pasta adresi.

## <a name="known-limitations"></a>Zināmie ierobežojumi

- Līdz 1 miljonam klientu profilu vienam eksportam uz DotDigital, kura pabeigšana var ilgt līdz trim stundām, jo pakalpojumu sniedzēja pusē ir ierobežojumi. Klientu profilu skaits, ko varat eksportēt uz DotDigital, ir atkarīgs no jūsu līguma ar DotDigital.
- Tikai segmenti.

## <a name="set-up-connection-to-dotdigital"></a>Savienojuma ar DotDigital iestatīšana

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Dodieties uz **Administrators** > **Savienojumi**.

1. Atlasiet **Pievienot savienojumu** un izvēlieties **DotDigital**.

1. Laukā **Parādāmais nosaukums** piešķiriet savienojumam atpazīstamu nosaukumu. Parādāmais nosaukums un nosaukuma veids raksturo šo savienojumu. Ir ieteicams izvēlēties nosaukumu, kas paskaidro savienojuma nolūku.

1. Izvēlieties, kurš var izmantot šo savienojumu. Pēc noklusējuma tie ir tikai administratori. Papildinformāciju skatiet rakstā [Atļaut līdzstrādniekiem izmantot savienojumu eksportam](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Ievadiet savu **DotDigital API lietotājvārdu un paroli**.

1. Ievadiet savu **DotDigital adrešu grāmatas ID**.

1. Pārskatiet datu privātumu [un atbilstību](connections.md#data-privacy-and-compliance) un atlasiet **Es piekrītu**.

1. Atlasiet **Izveidot savienojumu**, lai inicializētu savienojumu.

1. Atlasiet opciju **Pievienot sevi kā eksporta lietotāju** un sniedziet savus Customer Insights akreditācijas datus.

1. Lai pabeigtu savienošanu, atlasiet **Saglabāt**.

## <a name="configure-an-export"></a>Eksporta konfigurēšana

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Pārejiet uz **Dati** > **Eksportēšana**.

1. Atlasiet **Pievienot eksportēšanu**.

1. Laukā **Savienošana eksportam** atlasiet savienojumu no sadaļas DotDigital. Ja nav pieejamu savienojumu, sazinieties ar administratoru.

1. Ievadiet eksportēšanas nosaukumu.

1. **Datu atbilstības noteikšanas** sadaļas laukā **E-pasts** atlasiet lauku, kas norāda klienta e-pasta adresi.

1. Pēc izvēles eksportējiet **vārds**, **uzvārds**, **pilnu vārdu**, **dzimumu** un **pasta indeksu**.

1. Atlasiet segmentus, kurus vēlaties eksportēt.

1. Atlasiet **Saglabāt**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

DotDigital atrodiet savus segmentus [DotDigital adrešu grāmatās](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).

[!INCLUDE [footer-include](includes/footer-banner.md)]
