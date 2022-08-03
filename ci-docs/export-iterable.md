---
title: Segmentu eksportēšana uz iterable (priekšskatījums)
description: Uzziniet, kā konfigurēt savienojumu un eksportēt uz iterable.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ccf10b6e3a28a75f9d1bd3d8da3bf870ebc2b1b2
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195438"
---
# <a name="export-segments-to-iterable-preview"></a>Segmentu eksportēšana uz iterable (priekšskatījums)

Eksportējiet vienotu klientu profilu segmentus uz Iterable un izmantojiet tos mārketinga aktivitātēm.

## <a name="prerequisites"></a>Priekšnoteikumi

- Iterable [konts](https://iterable.com/) un atbilstošie administratora akreditācijas dati.
- Iterable [API atslēga](https://support.iterable.com/hc/en-us/articles/360043464871)
- [Konfigurētie segmenti](segments.md) programmā Customer Insights.
- Eksportētajos segmentos vienotajiem klientu profiliem ir lauks, kas norāda e-pasta adresi.

## <a name="known-limitations"></a>Zināmie ierobežojumi

- Iterable līdz 1 miljonam klientu profilu, kuru pabeigšana var aizņemt līdz 30 minūtēm. Klientu profilu skaits, ko varat eksportēt uz Iterable, ir atkarīgs no jūsu līguma ar Iterable.
- Tikai segmenti.

## <a name="set-up-connection-to-iterable"></a>Savienojuma ar iterable iestatīšana

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Dodieties uz **Administrators** > **Savienojumi**.

1. Atlasiet **Pievienot savienojumu** un izvēlieties **Iterable ( Iterable )**.

1. Laukā **Parādāmais nosaukums** piešķiriet savienojumam atpazīstamu nosaukumu. Parādāmais nosaukums un nosaukuma veids raksturo šo savienojumu. Ir ieteicams izvēlēties nosaukumu, kas paskaidro savienojuma nolūku.

1. Izvēlieties, kurš var izmantot šo savienojumu. Pēc noklusējuma tie ir tikai administratori. Papildinformāciju skatiet rakstā [Atļaut līdzstrādniekiem izmantot savienojumu eksportam](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Norādiet savu iterable API atslēgu, lai turpinātu pieteikties.

1. Pārskatiet datu privātumu [un atbilstību](connections.md#data-privacy-and-compliance) un atlasiet **Es piekrītu**.

1. Atlasiet **Izveidot savienojumu**, lai inicializētu savienojumu.

1. Atlasiet opciju **Pievienot sevi kā eksporta lietotāju** un sniedziet savus Customer Insights akreditācijas datus.

1. Lai pabeigtu savienošanu, atlasiet **Saglabāt**.

## <a name="configure-an-export"></a>Eksporta konfigurēšana

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Pārejiet uz **Dati** > **Eksportēšana**.

1. Atlasiet **Pievienot eksportēšanu**.

1. **Laukā Savienojums eksportēšanai** izvēlieties savienojumu no sadaļas Iterable. Ja nav pieejamu savienojumu, sazinieties ar administratoru.

1. Ievadiet eksportēšanas nosaukumu.

1. **Datu atbilstības noteikšanas** sadaļas laukā **E-pasts** atlasiet lauku, kas norāda klienta e-pasta adresi. Iterable izveidotais saraksts saņems tieši tādu pašu nosaukumu kā jūsu segmenta Dynamics 365 Customer Insights nosaukums.

1. Atlasiet segmentus, kurus vēlaties eksportēt.

1. Atlasiet **Saglabāt**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
