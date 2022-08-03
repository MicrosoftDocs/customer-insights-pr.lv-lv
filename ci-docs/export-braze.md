---
title: Segmentu eksportēšana uz Braze (priekšskatījums)
description: Uzziniet, kā konfigurēt savienojumu un eksportēt uz Braze.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 84dc7f13f30e0334d431fe5b5866c7f87e82ab27
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195116"
---
# <a name="export-segments-to-braze-preview"></a>Segmentu eksportēšana uz Braze (priekšskatījums)

Eksportējiet vienotu klientu profilu segmentus uz Braze un izmantojiet tos mārketinga aktivitātēm.

## <a name="prerequisites"></a>Priekšnoteikumi

- [Braze konts](https://www.braze.com/) un atbilstošie administratora akreditācijas dati.
- [Braze API atslēga](https://www.braze.com/docs/api/basics/)
- [Konfigurētie segmenti](segments.md) programmā Customer Insights.
- Vienoti klientu profili eksportētajos segmentos satur lauku, kas attēlo e-pasta adresi un Braze klienta ID.

## <a name="known-limitations"></a>Zināmie ierobežojumi

- Braze līdz 1 miljonam klientu profilu, kuru pabeigšana var aizņemt līdz pat 40 minūtēm. Klientu profilu skaits, ko varat eksportēt uz Braze, ir atkarīgs no jūsu līguma ar Braze.
- Tikai segmenti.

## <a name="set-up-connection-to-braze"></a>Savienojuma ar Braze iestatīšana

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Dodieties uz **Administrators** > **Savienojumi**.

1. Atlasiet **Pievienot savienojumu** un izvēlieties **Braze**.

1. Laukā **Parādāmais nosaukums** piešķiriet savienojumam atpazīstamu nosaukumu. Parādāmais nosaukums un nosaukuma veids raksturo šo savienojumu. Ir ieteicams izvēlēties nosaukumu, kas paskaidro savienojuma nolūku.

1. Izvēlieties, kurš var izmantot šo savienojumu. Pēc noklusējuma tie ir tikai administratori. Papildinformāciju skatiet rakstā [Atļaut līdzstrādniekiem izmantot savienojumu eksportam](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Norādiet savu Braze API atslēgu, lai turpinātu pieteikties.

1. Pārskatiet datu privātumu [un atbilstību](connections.md#data-privacy-and-compliance) un atlasiet **Es piekrītu**.

1. Atlasiet **Izveidot savienojumu**, lai inicializētu savienojumu.

1. Atlasiet opciju **Pievienot sevi kā eksporta lietotāju** un sniedziet savus Customer Insights akreditācijas datus.

1. Lai pabeigtu savienošanu, atlasiet **Saglabāt**.

## <a name="configure-an-export"></a>Eksporta konfigurēšana

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Pārejiet uz **Dati** > **Eksportēšana**.

1. Atlasiet **Pievienot eksportēšanu**.

1. **Laukā Savienojums eksportēšanai** izvēlieties savienojumu no sadaļas Braze. Ja nav pieejamu savienojumu, sazinieties ar administratoru.

1. Ievadiet eksportēšanas nosaukumu.

1. **Datu atbilstības noteikšanas** sadaļas laukā **E-pasts** atlasiet lauku, kas norāda klienta e-pasta adresi. Laukā **Klienta ID** atlasiet lauku, kas apzīmē klienta Braze ID. Braze segmenti tiks izveidoti ar tādu pašu segmenta nosaukumu kā .Dynamics 365 Customer Insights Varat izvēlēties vairāk neobligātus laukus datu saskaņošanai.

1. Atlasiet entītijas vai segmentus, kurus vēlaties eksportēt.

1. Atlasiet **Saglabāt**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
