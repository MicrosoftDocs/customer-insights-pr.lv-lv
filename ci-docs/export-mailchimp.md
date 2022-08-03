---
title: Segmentu eksportēšana uz Mailchimp (priekšskatījums)
description: Uzziniet, kā konfigurēt savienojumu un eksportēt uz Mailchimp.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 54aec10e24b6356e2e4317cf33e740a1a086a2dd
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196863"
---
# <a name="export-segments-to-mailchimp-preview"></a>Segmentu eksportēšana uz Mailchimp (priekšskatījums)

Eksportējiet vienotu klientu profilu segmentus uz Mailchimp, lai izveidotu informatīvas vēstules un e-pasta kampaņas.

## <a name="prerequisites"></a>Priekšnoteikumi

- [Mailchimp konts](https://mailchimp.com/) un atbilstošie administratora akreditācijas dati.
- [Esošās auditorijas Mailchimp](https://mailchimp.com/help/create-audience/) un atbilstošos [auditorijas ID](https://mailchimp.com/help/find-audience-id/).
- [Konfigurētie segmenti](segments.md).
- Eksportētajos segmentos vienotajiem klientu profiliem ir lauks, kas norāda e-pasta adresi.

## <a name="known-limitations"></a>Zināmie ierobežojumi

- Līdz 1 miljonam klientu profilu vienā eksportā uz Mailchimp, kas var aizņemt līdz trim stundām. Klientu profilu skaits, ko varat eksportēt uz Mailchimp, ir atkarīgs no jūsu līguma ar Mailchimp.
- Tikai segmenti.

## <a name="set-up-connection-to-mailchimp"></a>Savienojuma ar Mailchimp iestatīšana

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Dodieties uz **Administrators** > **Savienojumi**.

1. Atlasiet **Pievienot savienojumu** un izvēlieties **Mailchimp**.

1. Laukā **Parādāmais nosaukums** piešķiriet savienojumam atpazīstamu nosaukumu. Parādāmais nosaukums un nosaukuma veids raksturo šo savienojumu. Ir ieteicams izvēlēties nosaukumu, kas paskaidro savienojuma nolūku.

1. Izvēlieties, kurš var izmantot šo savienojumu. Pēc noklusējuma tie ir tikai administratori. Papildinformāciju skatiet rakstā [Atļaut līdzstrādniekiem izmantot savienojumu eksportam](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Pārskatiet datu privātumu [un atbilstību](connections.md#data-privacy-and-compliance) un atlasiet **Es piekrītu**.

1. Atlasiet **Izveidot savienojumu**, lai inicializētu savienojumu.

1. Atlasiet **Autentificēties ar Mailchimp** un sniedziet savus Mailchimp akreditācijas datus.

1. Atlasiet opciju **Pievienot sevi kā eksporta lietotāju** un sniedziet savus Customer Insights akreditācijas datus.

1. Lai pabeigtu savienošanu, atlasiet **Saglabāt**.

## <a name="configure-an-export"></a>Eksporta konfigurēšana

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Pārejiet uz **Dati** > **Eksportēšana**.

1. Atlasiet **Pievienot eksportēšanu**.

1. Laukā **Savienošana eksportam** atlasiet savienojumu no sadaļas Mailchimp. Ja nav pieejamu savienojumu, sazinieties ar administratoru.

1. Ievadiet eksportēšanas nosaukumu.

1. Ievadiet savu **Mailchimp auditorijas ID**.

1. **Datu atbilstības noteikšanas** sadaļas laukā **E-pasts** atlasiet lauku, kas norāda klienta e-pasta adresi.

1. Pēc izvēles eksportējiet **vārds** un **uzvārds**, lai izveidotu personalizētākus e-pasta ziņojumus. Atlasiet **Pievienot atribūtu**, lai kartētu šos laukus.

1. Atlasiet segmentus, kurus vēlaties eksportēt.

1. Atlasiet **Saglabāt**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
