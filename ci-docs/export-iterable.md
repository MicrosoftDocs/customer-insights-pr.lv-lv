---
title: Segmentu eksportēšana uz Iterable (priekšskatījums)
description: Uzziniet, kā konfigurēt savienojumu un eksportēt uz Iterable.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 69e2bd207c98fc2530620018bf95dd869d1798f6
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724555"
---
# <a name="export-segments-to-iterable-preview"></a>Segmentu eksportēšana uz Iterable (priekšskatījums)

Eksportējiet vienoto klientu profilu segmentus uz Iterable un izmantojiet tos mārketinga aktivitātēm.

## <a name="prerequisites"></a>Priekšnoteikumi

- Iterable [konts](https://iterable.com/) un atbilstošie administratora akreditācijas dati.
- Iterable [API atslēga](https://support.iterable.com/hc/en-us/articles/360043464871)
- [Konfigurēti segmenti](segments.md) programmā Customer Insights.
- Eksportētajos segmentos vienotajiem klientu profiliem ir lauks, kas norāda e-pasta adresi.

## <a name="known-limitations"></a>Zināmie ierobežojumi

- Privātā saite kombinācijā ar krātuvi Bring your own storage (BYOS) netiek atbalstīta.
- Iterable līdz 1 miljonam klientu profilu, kuru pabeigšana var aizņemt līdz 30 minūtēm. Klientu profilu skaits, ko varat eksportēt uz Iterable, ir atkarīgs no jūsu līguma ar Iterable.
- Tikai segmenti.

## <a name="set-up-connection-to-iterable"></a>Savienojuma iestatīšana ar Iterable

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Dodieties uz **Administrators** > **Savienojumi**.

1. Atlasiet **Pievienot savienojumu** un izvēlieties **Iterable**.

1. Laukā **Parādāmais nosaukums** piešķiriet savienojumam atpazīstamu nosaukumu. Parādāmais nosaukums un nosaukuma veids raksturo šo savienojumu. Ir ieteicams izvēlēties nosaukumu, kas paskaidro savienojuma nolūku.

1. Izvēlieties, kurš var izmantot šo savienojumu. Pēc noklusējuma tie ir tikai administratori. Papildinformāciju skatiet rakstā [Atļaut līdzstrādniekiem izmantot savienojumu eksportam](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Norādiet savu Iterable API atslēgu, lai turpinātu pieteikties.

1. Pārskatiet datu konfidencialitāti [un atbilstību](connections.md#data-privacy-and-compliance) un atlasiet **Es piekrītu**.

1. Atlasiet **Izveidot savienojumu, lai inicializētu savienojumu**.

1. Atlasiet opciju **Pievienot sevi kā eksporta lietotāju** un sniedziet savus Customer Insights akreditācijas datus.

1. Lai pabeigtu savienošanu, atlasiet **Saglabāt**.

## <a name="configure-an-export"></a>Eksporta konfigurēšana

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Pārejiet uz **Dati** > **Eksportēšana**.

1. Atlasiet **Pievienot eksportu**.

1. **Laukā Savienojums eksportēšanai** izvēlieties savienojumu no sadaļas Iterable. Ja nav pieejamu savienojumu, sazinieties ar administratoru.

1. Ievadiet eksportēšanas nosaukumu.

1. **Datu atbilstības noteikšanas** sadaļas laukā **E-pasts** atlasiet lauku, kas norāda klienta e-pasta adresi. Iterable izveidotais saraksts saņems tieši tādu pašu nosaukumu kā jūsu segmenta nosaukums .Dynamics 365 Customer Insights

1. Atlasiet segmentus, kurus vēlaties eksportēt.

1. Atlasiet **Saglabāt**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
