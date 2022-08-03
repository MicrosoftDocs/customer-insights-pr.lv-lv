---
title: Segmentu eksportēšana uz Criteo (priekšskatījums)
description: Uzziniet, kā konfigurēt savienojumu un eksportēt uz Criteo.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d7c8d6f0121fe18a6c886ba3776109a1a592ef33
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195345"
---
# <a name="export-segments-to-criteo-preview"></a>Segmentu eksportēšana uz Criteo (priekšskatījums)

Eksportējiet vienotu klientu profilu segmentus, lai ģenerētu kampaņas, nodrošinātu e-pasta mārketingu un izmantotu noteiktas klientu grupas ar Criteo.

## <a name="prerequisites"></a>Priekšnoteikumi

- [Criteo Dynamics atkārtotas mērķauditorijas atlases konts](https://www.criteo.com/login/) un atbilstošie administratora akreditācijas dati.
- [Konfigurētie segmenti](segments.md).
- Eksportētajos segmentos vienotajiem klientu profiliem ir lauks, kas norāda e-pasta adresi.

## <a name="known-limitations"></a>Zināmie ierobežojumi

- Līdz 1 miljonam klientu profilu vienam eksportam uz Criteo, kas var aizņemt līdz 30 minūtēm. Klientu profilu skaits, ko varat eksportēt uz Criteo, ir atkarīgs no jūsu līguma ar Criteo.
- Tikai segmenti.

## <a name="set-up-connection-to-criteo"></a>Savienojuma ar Criteo iestatīšana

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Dodieties uz **Administrators** > **Savienojumi**.

1. Atlasiet **Pievienot savienojumu** un izvēlieties **Criteo**.

1. Laukā **Parādāmais nosaukums** piešķiriet savienojumam atpazīstamu nosaukumu. Parādāmais nosaukums un nosaukuma veids raksturo šo savienojumu. Ir ieteicams izvēlēties nosaukumu, kas paskaidro savienojuma nolūku.

1. Izvēlieties, kurš var izmantot šo savienojumu. Pēc noklusējuma tie ir tikai administratori. Papildinformāciju skatiet rakstā [Atļaut līdzstrādniekiem izmantot savienojumu eksportam](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Pārskatiet datu privātumu [un atbilstību](connections.md#data-privacy-and-compliance) un atlasiet **Es piekrītu**.

1. Atlasiet **Izveidot savienojumu**, lai inicializētu savienojumu.

1. Atlasiet **Autentificēties ar Criteo** un norādiet savu administratora lietotājvārdu un akreditācijas datus Criteo.

1. Atlasiet opciju **Pievienot sevi kā eksporta lietotāju** un sniedziet savus Customer Insights akreditācijas datus.

1. Lai pabeigtu savienošanu, atlasiet **Saglabāt**.

## <a name="configure-an-export"></a>Eksporta konfigurēšana

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Pārejiet uz **Dati** > **Eksportēšana**.

1. Atlasiet **Pievienot eksportēšanu**.

1. **Laukā Savienojums eksportēšanai** izvēlieties savienojumu no sadaļas Criteo. Ja nav pieejamu savienojumu, sazinieties ar administratoru.

1. Ievadiet eksportēšanas nosaukumu.

1. **Datu atbilstības noteikšanas** sadaļas laukā **E-pasts** atlasiet lauku, kas norāda klienta e-pasta adresi.

1. Pēc izvēles eksportējiet **reklāmdevēja ID** un **nosaukumu**.

1. Atlasiet segmentus, kurus vēlaties eksportēt.

1. Atlasiet **Saglabāt**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
