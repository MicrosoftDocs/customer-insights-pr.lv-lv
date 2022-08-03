---
title: Segmentu eksportēšana uz ActiveCampaign
description: Uzziniet, kā konfigurēt savienojumu un eksportēt uz ActiveCampaign.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 178d2df8edf1abcec72664e19d73a88f2b97f12d
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195575"
---
# <a name="export-segments-to-activecampaign-preview"></a>Segmentu eksportēšana uz ActiveCampaign (priekšskatījums)

Eksportējiet vienoto klientu profilu segmentus uz ActiveCampaign un izmantojiet tos mārketinga darbībām.

## <a name="prerequisites"></a>Priekšnoteikumi

- [ActiveCampaign konts](https://www.activecampaign.com/) un atbilstošie administratora akreditācijas dati.
- [ActiveCampaign saraksta ID](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).
- [ActiveCampaign API atslēga](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key) un REST galapunkta resursdatora nosaukums.
- [Konfigurētie segmenti](segments.md) programmā Customer Insights.
- Eksportētajos segmentos vienotajiem klientu profiliem ir lauks, kas norāda e-pasta adresi.

## <a name="known-limitations"></a>Zināmie ierobežojumi

- Līdz 1 miljonam klientu profilu eksportēšanai uz ActiveCampaign, kura pabeigšana var ilgt līdz 90 minūtēm. To klientu profilu skaits, ko var eksportēt uz ActiveCampaign, ir atkarīgs no jūsu līguma ar ActiveCampaign.
- Tikai segmenti.

## <a name="set-up-connection-to-activecampaign"></a>Savienojuma izveide ar ActiveCampaign

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Dodieties uz **Administrators** > **Savienojumi**.

1. Atlasiet **Pievienot savienojumu** un izvēlieties **ActiveCampaign**.

1. Laukā **Parādāmais nosaukums** piešķiriet savienojumam atpazīstamu nosaukumu. Parādāmais nosaukums un nosaukuma veids raksturo šo savienojumu. Ir ieteicams izvēlēties nosaukumu, kas paskaidro savienojuma nolūku.

1. Izvēlieties, kurš var izmantot šo savienojumu. Pēc noklusējuma tie ir tikai administratori. Papildinformāciju skatiet rakstā [Atļaut līdzstrādniekiem izmantot savienojumu eksportam](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Ievadiet savu ActiveCampaign API atslēgu un REST galapunkta resursdatora nosaukumu. REST galapunkta resursdatora nosaukums ir tikai viesošanas nosaukums bez https://.

1. Pārskatiet datu privātumu [un atbilstību](connections.md#data-privacy-and-compliance) un atlasiet **Es piekrītu**.

1. Atlasiet **Izveidot savienojumu**, lai inicializētu savienojumu.

1. Atlasiet opciju **Pievienot sevi kā eksporta lietotāju** un sniedziet savus Customer Insights akreditācijas datus.

1. Lai pabeigtu savienošanu, atlasiet **Saglabāt**.

## <a name="configure-an-export"></a>Eksporta konfigurēšana

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Pārejiet uz **Dati** > **Eksportēšana**.

1. Atlasiet **Pievienot eksportēšanu**.

1. Laukam **Savienojums eksportēšanai** izvēlieties savienojumu no ActiveCampaign sadaļas. Ja nav pieejamu savienojumu, sazinieties ar administratoru.

1. Ievadiet eksportēšanas nosaukumu.

1. Ievadiet savu **ActiveCampaign saraksta ID**.

1. **Datu atbilstības noteikšanas** sadaļas laukā **E-pasts** atlasiet lauku, kas norāda klienta e-pasta adresi.

1. Pēc izvēles eksportējiet **vārds**, **uzvārds** un **tālruni**, lai izveidotu personalizētākus e-pasta ziņojumus. Atlasiet **Pievienot atribūtu**, lai kartētu šos laukus.

1. Atlasiet segmentus, kurus vēlaties eksportēt.

1. Atlasiet **Saglabāt**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
