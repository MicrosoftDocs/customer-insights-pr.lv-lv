---
title: Segmentu eksportēšana uz Marketo (priekšskatījums)
description: Uzziniet, kā konfigurēt savienojumu un eksportēt uz Marketo.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f57cdfbb24df8a8ffa1670b426d50dbba2c5f40f
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195253"
---
# <a name="export-segments-to-marketo-preview"></a>Segmentu eksportēšana uz Marketo (priekšskatījums)

Izmantojiet pakalpojumā Customer Insights izveidotos segmentus kampaņu veidošanai, e-pasta mārketinga sniegšanai un specifisku klientu grupu atlases iespējas pakalpojumā Marketo.

## <a name="prerequisites"></a>Priekšnoteikumi

- [Marketo konts](https://login.marketo.com/) un atbilstošie administratora akreditācijas dati.
- [Marketo klienta ID, klienta noslēpums un REST galapunkta resursdatora nosaukums](https://developers.marketo.com/rest-api/authentication/).
- [Esošie saraksti Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists) un atbilstošie ID.
- [Konfigurētie segmenti](segments.md).
- Eksportētajos segmentos vienotajiem klientu profiliem ir lauks, kas norāda e-pasta adresi.

## <a name="known-limitations"></a>Zināmie ierobežojumi

- Līdz 1 miljonam klientu profilu vienam eksportam uz Marketo, kas var aizņemt līdz 3 stundām. Klientu profilu skaits, ko varat eksportēt uz Marketo, ir atkarīgs no jūsu līguma ar Marketo.
- Tikai segmenti.

## <a name="set-up-connection-to-marketo"></a>Savienojuma ar Marketo iestatīšana

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Dodieties uz **Administrators** > **Savienojumi**.

1. Atlasiet **Pievienot savienojumu** un izvēlieties **Marketo**.

1. Laukā **Parādāmais nosaukums** piešķiriet savienojumam atpazīstamu nosaukumu. Parādāmais nosaukums un nosaukuma veids raksturo šo savienojumu. Ir ieteicams izvēlēties nosaukumu, kas paskaidro savienojuma nolūku.

1. Izvēlieties, kurš var izmantot šo savienojumu. Pēc noklusējuma tie ir tikai administratori. Papildinformāciju skatiet rakstā [Atļaut līdzstrādniekiem izmantot savienojumu eksportam](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Ievadiet savu **Marketo klienta ID, klienta noslēpumu un REST galapunkta resursdatora nosaukumu**. REST galapunkta resursdatora nosaukums ir tikai viesošanas nosaukums bez https://. Piemērs: xyz-abc-123.mktorest.com.

1. Pārskatiet datu privātumu [un atbilstību](connections.md#data-privacy-and-compliance) un atlasiet **Es piekrītu**.

1. Atlasiet **Izveidot savienojumu**, lai inicializētu savienojumu.

1. Atlasiet opciju **Pievienot sevi kā eksporta lietotāju** un sniedziet savus Customer Insights akreditācijas datus.

1. Lai pabeigtu savienošanu, atlasiet **Saglabāt**.

## <a name="configure-an-export"></a>Eksporta konfigurēšana

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Pārejiet uz **Dati** > **Eksportēšana**.

1. Atlasiet **Pievienot eksportēšanu**.

1. Laukā **Savienošana eksportam** atlasiet savienojumu no sadaļas Marketo. Ja nav pieejamu savienojumu, sazinieties ar administratoru.

1. Ievadiet eksportēšanas nosaukumu.

1. Ievadiet savu **Marketo saraksta ID**. Saraksta ID ir tikai skaitliska vērtība. Piemēram, ja jūsu Marketo saraksta ID ir ST12345A7, noņemiet rakstzīmi pirms un pēc cipariem un ievadiet *12345*.

1. **Sadaļā Datu saskaņošana** atlasiet vismaz vienu lauku, kas apzīmē klienta e-pasta adresi vai klienta Marketo ID.

1. Pēc izvēles eksportējiet **vārds**, **uzvārds**, **pilsētu,** štatu **un** **valsti/reģionu**, lai izveidotu personalizētākus e-pasta ziņojumus. Atlasiet **Pievienot atribūtu**, lai kartētu šos laukus.

1. Atlasiet segmentus, kurus vēlaties eksportēt.

1. Atlasiet **Saglabāt**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Marketo atrodiet savus segmentus zem [Marketo sarakstiem](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).

[!INCLUDE [footer-include](includes/footer-banner.md)]
