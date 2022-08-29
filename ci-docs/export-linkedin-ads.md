---
title: Segmentu eksportēšana uz LinkedIn Ads (priekšskatījums)
description: Uzziniet, kā konfigurēt savienojumu un eksportēt uz LinkedIn Ads.
ms.date: 08/12/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 4c3928e05db0ebda262b4ad3e928ce85f70035b9
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304712"
---
# <a name="export-segments-to-linkedin-ads-preview"></a>Segmentu eksportēšana uz LinkedIn Ads (priekšskatījums)

Eksportēt vienoto klientu profilu segmentus uz LinkedIn Ads, lai izveidotu Matched Audiences. Izmantojiet Matched Audiences, lai mērķētu uz uzņēmumu un sazinātos ar mērķauditorijas atlasi.

## <a name="prerequisites"></a>Priekšnoteikumi

- Konts [LinkedIn Campaign Manager](https://business.linkedin.com/marketing-solutions/ads) un atbilstošie administratora akreditācijas dati.
- [LinkedIn Campaign Manager Konta ID](https://www.linkedin.com/help/lms/answer/a424270).
- [Konfigurētie segmenti](segments.md) programmā Customer Insights.
- Eksportētajiem segmentiem ir nepieciešams vismaz viens konkrēts lauks atkarībā no tā, vai izvēlaties [mērķauditorijas atlasi pēc](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) saziņas vai [uzņēmuma mērķauditorijas atlases](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) pakalpojumā LinkedIn. Iespējamie lauki ir uzskaitīti **darbībā Datu saskaņošana,** konfigurējot [eksportēšanu](#configure-an-export).

## <a name="known-limitations"></a>Zināmie ierobežojumi

- Līdz pat 100 000 klientu profilu eksportēšanai uz LinkedIn Reklāmām, un tā pabeigšana var aizņemt līdz pat 10 minūtēm.
- Tikai segmenti. Segmentā jābūt vismaz 300 unikāliem profiliem.

## <a name="set-up-connection-to-linkedin-ads"></a>Savienojuma ar LinkedIn reklāmām iestatīšana

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Dodieties uz **Administrators** > **Savienojumi**.

1. Atlasiet **Pievienot savienojumu** un izvēlieties **LinkedIn reklāmas**.

1. Laukā **Parādāmais nosaukums** piešķiriet savienojumam atpazīstamu nosaukumu. Parādāmais nosaukums un nosaukuma veids raksturo šo savienojumu. Ir ieteicams izvēlēties nosaukumu, kas paskaidro savienojuma nolūku.

1. Izvēlieties, kurš var izmantot šo savienojumu. Pēc noklusējuma tie ir tikai administratori. Papildinformāciju skatiet rakstā [Atļaut līdzstrādniekiem izmantot savienojumu eksportam](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Norādiet sava LinkedIn Campaign Manager konta ID.

1. Pārskatiet datu privātumu [un atbilstību](connections.md#data-privacy-and-compliance) un atlasiet **Es piekrītu**.

1. Atlasiet **Izveidot savienojumu**, lai inicializētu savienojumu.

1. Atlasiet **Autentificēties ar LinkedIn** un norādiet savus LinkedIn Campaign Manager administratora akreditācijas datus.

1. Atlasiet opciju **Pievienot sevi kā eksporta lietotāju** un sniedziet savus Customer Insights akreditācijas datus.

1. Lai pabeigtu savienošanu, atlasiet **Saglabāt**.

## <a name="configure-an-export"></a>Eksporta konfigurēšana

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Pārejiet uz **Dati** > **Eksportēšana**.

1. Atlasiet **Pievienot eksportēšanu**.

1. Laukā **Savienošana eksportam** atlasiet savienojumu no sadaļas LinkedIn Ads. Ja nav pieejamu savienojumu, sazinieties ar administratoru.

1. Ievadiet eksportēšanas nosaukumu.

1. Izvēlieties, vai vēlaties eksportēt datus, lai sazinātos [ar mērķauditorijas atlasi](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting), [vai uzņēmuma mērķauditorijas atlasi](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) LinkedIn.

1. Sadaļā **Datu atbilstība**, lai atlasītu kontaktpersonu, atlasiet vismaz vienu lauku, kurā ir norādīta klienta e-pasta adrese, Apple Ad ID, Google Ad ID, Google User ID vai vārds un uzvārds. Ja izvēlaties uzņēmuma mērķauditorijas atlasi, atlasiet vismaz vienu lauku, kas apzīmē uzņēmuma nosaukumu, e-pasta domēnu, LinkedIn lapas vietrādi URL, krājumu simbolu vai vietni.

1. Pēc izvēles pievienojiet laukus, lai sīkāk definētu eksportēšanu. Atlasiet **Pievienot atribūtu**, lai kartētu šos laukus.

1. Atlasiet segmentus, kurus vēlaties eksportēt. Matched Audiences programmā LinkedIn Campaign Manager tiks automātiski izveidotas ar eksportējamo segmentu nosaukumu. Katrs segments radīs atsevišķu Matched Audience.

1. Atlasiet **Saglabāt**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
