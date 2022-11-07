---
title: Segmentu eksportēšana uz RollWorks (priekšskatījums)
description: Uzziniet, kā konfigurēt savienojumu un eksportēt uz RollWorks.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d857bf5d11de86521c4a9d4fc665c020496d89d2
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725134"
---
# <a name="export-segments-to-rollworks-preview"></a>Segmentu eksportēšana uz RollWorks (priekšskatījums)

Eksportējiet vienoto klientu profilu segmentus uz RollWorks un izmantojiet tos reklāmā.

## <a name="prerequisites"></a>Priekšnoteikumi

- RollWorks [konts](https://www.rollworks.com/) un atbilstošie administratora akreditācijas dati.
- [RollWorks reklāmdevēja ID](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).
- [Konfigurēti segmenti](segments.md) programmā Customer Insights.
- Eksportētajos segmentos vienotajiem klientu profiliem ir lauks, kas norāda e-pasta adresi.

## <a name="known-limitations"></a>Zināmie ierobežojumi

- Privātā saite kombinācijā ar krātuvi Bring your own storage (BYOS) netiek atbalstīta.
- Līdz 250 000 klientu profilu eksportēšanai uz RollWorks, kuru pabeigšana var aizņemt līdz 10 minūtēm. Klientu profilu skaits, ko varat eksportēt pakalpojumā RollWorks, ir atkarīgs no jūsu līguma ar RollWorks.
- Tikai segmenti.

## <a name="set-up-connection-to-rollworks"></a>Savienojuma ar RollWorks iestatīšana

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Dodieties uz **Administrators** > **Savienojumi**.

1. Atlasiet **Pievienot savienojumu** un izvēlieties **RollWorks**.

1. Laukā **Parādāmais nosaukums** piešķiriet savienojumam atpazīstamu nosaukumu. Parādāmais nosaukums un nosaukuma veids raksturo šo savienojumu. Ir ieteicams izvēlēties nosaukumu, kas paskaidro savienojuma nolūku.

1. Izvēlieties, kurš var izmantot šo savienojumu.  Pēc noklusējuma tie ir tikai administratori. Papildinformāciju skatiet rakstā [Atļaut līdzstrādniekiem izmantot savienojumu eksportam](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Pārskatiet datu konfidencialitāti [un atbilstību](connections.md#data-privacy-and-compliance) un atlasiet **Es piekrītu**.

1. Atlasiet **Izveidot savienojumu, lai inicializētu savienojumu**.

1. Atlasiet **Autentificēt ar RollWorks** un norādiet savus RollWorks administratora akreditācijas datus.

1. Atlasiet opciju **Pievienot sevi kā eksporta lietotāju** un sniedziet savus Customer Insights akreditācijas datus.

1. Lai pabeigtu savienošanu, atlasiet **Saglabāt**.

## <a name="configure-an-export"></a>Eksporta konfigurēšana

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Pārejiet uz **Dati** > **Eksportēšana**.

1. Atlasiet **Pievienot eksportu**.

1. Laukā **Savienošana eksportam** atlasiet savienojumu no sadaļas RollWorks. Ja nav pieejamu savienojumu, sazinieties ar administratoru.

1. Ievadiet eksportēšanas nosaukumu.

1. Ievadiet savu **RollWorks reklāmdevēja ID.**

1. **Datu atbilstības noteikšanas** sadaļas laukā **E-pasts** atlasiet lauku, kas norāda klienta e-pasta adresi.

1. Atlasiet segmentus, kurus vēlaties eksportēt.

1. Atlasiet **Saglabāt**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
