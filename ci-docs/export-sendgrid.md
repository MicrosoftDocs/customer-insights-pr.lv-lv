---
title: Segmentu eksportēšana uz SendGrid (priekšskatījums)
description: Uzziniet, kā konfigurēt savienojumu un eksportēt uz SendGrid.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f2990ad410dda0cbf952f82f3fc30b3a53a7bcd4
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 07/27/2022
ms.locfileid: "9197001"
---
# <a name="export-segments-to-sendgrid-preview"></a>Segmentu eksportēšana uz SendGrid (priekšskatījums)

Eksportējiet vienoto klientu profilu segmentus uz SendGrid kontaktpersonu sarakstiem un izmantojiet tos kampaņām un e-pasta mārketingam lietojumprogrammā SendGrid.

## <a name="prerequisites"></a>Priekšnoteikumi

- [SendGrid konts](https://sendgrid.com/) un atbilstošie administratora akreditācijas dati.
- [SendGrid](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts) esošie kontaktpersonu saraksti un atbilstošie ID.
- [SendGrid API atslēga](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).
- [Konfigurētie segmenti](segments.md) programmā Customer Insights.
- Eksportētajos segmentos vienotajiem klientu profiliem ir lauks, kas norāda e-pasta adresi.

## <a name="known-limitations"></a>Zināmie ierobežojumi

- Līdz pat 100 000 klientu profilu kopumā līdz SendGrid, kura pabeigšana var aizņemt līdz pat dažām stundām. Klientu profilu skaits, ko varat eksportēt uz SendGrid, ir atkarīgs no jūsu līguma ar SendGrid.
- Tikai segmenti.

## <a name="set-up-connection-to-sendgrid"></a>Savienojuma ar SendGrid iestatīšana

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Dodieties uz **Administrators** > **Savienojumi**.

1. Atlasiet **Pievienot savienojumu** un izvēlieties **SendGrid**.

1. Laukā **Parādāmais nosaukums** piešķiriet savienojumam atpazīstamu nosaukumu. Parādāmais nosaukums un nosaukuma veids raksturo šo savienojumu. Ir ieteicams izvēlēties nosaukumu, kas paskaidro savienojuma nolūku.

1. Izvēlieties, kurš var izmantot šo savienojumu. Pēc noklusējuma tie ir tikai administratori. Papildinformāciju skatiet rakstā [Atļaut līdzstrādniekiem izmantot savienojumu eksportam](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Ievadiet savu **SendGrid API atslēgu**.

1. Pārskatiet datu privātumu [un atbilstību](connections.md#data-privacy-and-compliance) un atlasiet **Es piekrītu**.

1. Atlasiet **Izveidot savienojumu**, lai inicializētu savienojumu.

1. Atlasiet opciju **Pievienot sevi kā eksporta lietotāju** un sniedziet savus Customer Insights akreditācijas datus.

1. Lai pabeigtu savienošanu, atlasiet **Saglabāt**.

## <a name="configure-an-export"></a>Eksporta konfigurēšana

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Pārejiet uz **Dati** > **Eksportēšana**.

1. Atlasiet **Pievienot eksportēšanu**.

1. Laukā **Savienošana eksportam** atlasiet savienojumu no sadaļas SendGrid. Ja nav pieejamu savienojumu, sazinieties ar administratoru.

1. Ievadiet eksportēšanas nosaukumu.

1. Ievadiet savu **SendGrid saraksta ID**.

1. **Datu atbilstības noteikšanas** sadaļas laukā **E-pasts** atlasiet lauku, kas norāda klienta e-pasta adresi.

1. Pēc izvēles atlasiet laukus, piemēram **, vārds**, **uzvārds**, **valsts/reģions**, **štats**, **pilsēta** un **pasta indekss**.

1. Atlasiet segmentus, kurus vēlaties eksportēt, ievērojot zināmos ierobežojumus.

1. Atlasiet **Saglabāt**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
