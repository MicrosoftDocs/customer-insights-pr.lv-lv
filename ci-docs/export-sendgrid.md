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
ms.openlocfilehash: 855e77055eeb24a2c6cff0d45cd23edf93cc0581
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724857"
---
# <a name="export-segments-to-sendgrid-preview"></a>Segmentu eksportēšana uz SendGrid (priekšskatījums)

Eksportējiet vienoto klientu profilu segmentus uz SendGrid kontaktpersonu sarakstiem un izmantojiet tos kampaņām un e-pasta mārketingam lietojumprogrammā SendGrid.

## <a name="prerequisites"></a>Priekšnoteikumi

- SendGrid [konts](https://sendgrid.com/) un atbilstošie administratora akreditācijas dati.
- [Esošie kontaktpersonu saraksti SendGrid](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts) un atbilstošie ID.
- SendGrid [API atslēga](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).
- [Konfigurēti segmenti](segments.md) programmā Customer Insights.
- Eksportētajos segmentos vienotajiem klientu profiliem ir lauks, kas norāda e-pasta adresi.

## <a name="known-limitations"></a>Zināmie ierobežojumi

- Privātā saite kombinācijā ar krātuvi Bring your own storage (BYOS) netiek atbalstīta.
- SendGrid kopā līdz 100 000 klientu profilu, kuru pabeigšana var aizņemt līdz pat dažām stundām. Klientu profilu skaits, ko varat eksportēt uz SendGrid, ir atkarīgs no jūsu līguma ar SendGrid.
- Tikai segmenti.

## <a name="set-up-connection-to-sendgrid"></a>Savienojuma ar SendGrid iestatīšana

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Dodieties uz **Administrators** > **Savienojumi**.

1. Atlasiet **Pievienot savienojumu** un izvēlieties **SendGrid**.

1. Laukā **Parādāmais nosaukums** piešķiriet savienojumam atpazīstamu nosaukumu. Parādāmais nosaukums un nosaukuma veids raksturo šo savienojumu. Ir ieteicams izvēlēties nosaukumu, kas paskaidro savienojuma nolūku.

1. Izvēlieties, kurš var izmantot šo savienojumu. Pēc noklusējuma tie ir tikai administratori. Papildinformāciju skatiet rakstā [Atļaut līdzstrādniekiem izmantot savienojumu eksportam](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Ievadiet savu **SendGrid API atslēgu**.

1. Pārskatiet datu konfidencialitāti [un atbilstību](connections.md#data-privacy-and-compliance) un atlasiet **Es piekrītu**.

1. Atlasiet **Izveidot savienojumu, lai inicializētu savienojumu**.

1. Atlasiet opciju **Pievienot sevi kā eksporta lietotāju** un sniedziet savus Customer Insights akreditācijas datus.

1. Lai pabeigtu savienošanu, atlasiet **Saglabāt**.

## <a name="configure-an-export"></a>Eksporta konfigurēšana

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Pārejiet uz **Dati** > **Eksportēšana**.

1. Atlasiet **Pievienot eksportu**.

1. Laukā **Savienošana eksportam** atlasiet savienojumu no sadaļas SendGrid. Ja nav pieejamu savienojumu, sazinieties ar administratoru.

1. Ievadiet eksportēšanas nosaukumu.

1. Ievadiet savu **SendGrid saraksta ID.**

1. **Datu atbilstības noteikšanas** sadaļas laukā **E-pasts** atlasiet lauku, kas norāda klienta e-pasta adresi.

1. Ja vēlaties, atlasiet laukus, piemēram **, vārds**, uzvārds **, Valsts/reģions**, **Štats** **,** **Pilsēta** un **Pasta indekss**.

1. Atlasiet segmentus, kurus vēlaties eksportēt, ievērojot zināmos ierobežojumus.

1. Atlasiet **Saglabāt**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
