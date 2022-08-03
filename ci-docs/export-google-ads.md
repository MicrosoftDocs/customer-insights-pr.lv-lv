---
title: Segmentu eksportēšana uz Google Ads (priekšskatījums)
description: Uzziniet, kā konfigurēt savienojumu un eksportēt uz Google Ads.
ms.date: 07/25/2022
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: fd7498ecf17ef8a3a8f22dcc49ae204bef88b47f
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196587"
---
# <a name="export-segments-to-google-ads-preview"></a>Segmentu eksportēšana uz Google Ads (priekšskatījums)

Eksportējiet vienoto klientu profilu segmentus uz Google Ads auditoriju sarakstu un izmantojiet tos, lai reklāma tiktu rādīta Google meklēšanā, Gmail, YouTube un Google Display Network.

## <a name="prerequisites"></a>Priekšnoteikumi

- [Google Ads konts](https://ads.google.com/) un atbilstošie administratora akreditācijas dati.
- [Google Ads klienta ID](https://support.google.com/google-ads/answer/1704344).
- Klientu atbilstības politikas [prasības](https://support.google.com/adspolicy/answer/6299717) ir izpildītas.
- Atkārtotā [mārketinga sarakstu izmēru](https://support.google.com/google-ads/answer/7558048) prasības ir izpildītas.
- [Konfigurētie segmenti](segments.md).
- Vienoti klientu profili eksportētajos segmentos satur laukus, kuros norādīta e-pasta adrese, tālrunis, mobilā reklāmdevēja ID, trešās puses lietotāja ID vai adrese.

## <a name="known-limitations"></a>Zināmie ierobežojumi

- Eksportējiet uz Google Ads līdz pat 1 miljonam klientu profilu vienā eksportā, kura pabeigšana var ilgt līdz pat 30 minūtēm, jo pakalpojumu sniedzēja pusē ir ierobežojumi.
- Tikai segmenti.
- Atbilstība programmā Google Ads var ilgt līdz pat 48 stundām.

## <a name="set-up-connection-to-google-ads"></a>Savienojuma ar Google Ads iestatīšana

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Dodieties uz **Administrators** > **Savienojumi**.

1. Atlasiet **Pievienot savienojumu** un izvēlieties **Google Ads**.

1. Laukā **Parādāmais nosaukums** piešķiriet savienojumam atpazīstamu nosaukumu. Parādāmais nosaukums un nosaukuma veids raksturo šo savienojumu. Ir ieteicams izvēlēties nosaukumu, kas paskaidro savienojuma nolūku.

1. Izvēlieties, kurš var izmantot šo savienojumu. Pēc noklusējuma tie ir tikai administratori. Papildinformāciju skatiet rakstā [Atļaut līdzstrādniekiem izmantot savienojumu eksportam](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Ievadiet savu Google Ads klienta ID.

1. Pārskatiet datu privātumu [un atbilstību](connections.md#data-privacy-and-compliance) un atlasiet **Es piekrītu**.

1. Atlasiet **Autentificēties ar Google Ads** un sniedziet savus Google Ads akreditācijas datus.

1. Atlasiet opciju **Pievienot sevi kā eksporta lietotāju** un sniedziet savus Customer Insights akreditācijas datus.

1. Lai pabeigtu savienošanu, atlasiet **Saglabāt**.

## <a name="configure-an-export"></a>Eksporta konfigurēšana

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Pārejiet uz **Dati** > **Eksportēšana**.

1. Atlasiet **Pievienot eksportēšanu**.

1. Laukā **Savienošana eksportam** atlasiet savienojumu no sadaļas Google Ads. Ja nav pieejamu savienojumu, sazinieties ar administratoru.

1. Ievadiet eksportēšanas nosaukumu.

1. Izvēlieties, vai izmantot esošu vai izveidot jaunu auditoriju:
   - Lai atjauninātu esošu Google Ads mērķauditoriju, ievadiet savu [Google Ads mērķauditorijas ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns).
   - Lai izveidotu jaunu auditoriju, atstājiet lauku Google mērķauditorijas ID tukšu. Customer Insights automātiski izveidos jaunu mērķauditoriju jūsu Google Ads kontā un izmantos eksportētā segmenta nosaukumu.

1. **Sadaļā Datu saskaņošana atlasiet vienu vai vairākus eksportējamos** datu laukus un atlasiet lauku, kas programmā Customer Insights attēlo atbilstošos datu laukus.

1. Atlasiet segmentus, kurus vēlaties eksportēt.

1. Atlasiet **Saglabāt**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
