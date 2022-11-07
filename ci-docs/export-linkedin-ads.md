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
ms.openlocfilehash: 06eb915e352ad545f95e96e6108be0f81f43a451
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725317"
---
# <a name="export-segments-to-linkedin-ads-preview"></a>Segmentu eksportēšana uz LinkedIn Ads (priekšskatījums)

Eksportēt vienoto klientu profilu segmentus uz LinkedIn Ads, lai izveidotu Matched Audiences. Izmantojiet Matched Audiences, lai mērķētu uz uzņēmumu un sazinātos ar mērķauditorijas atlasi.

## <a name="prerequisites"></a>Priekšnoteikumi

- Konts [LinkedIn Campaign Manager un atbilstošie administratora](https://business.linkedin.com/marketing-solutions/ads) akreditācijas dati.
- Konta [LinkedIn Campaign Manager ID](https://www.linkedin.com/help/lms/answer/a424270).
- [Konfigurēti segmenti](segments.md) programmā Customer Insights.
- Eksportētajiem segmentiem ir nepieciešams vismaz viens konkrēts lauks atkarībā no tā, vai izvēlaties [mērķauditorijas atlasi pēc kontaktiem vai](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) uzņēmuma mērķauditorijas atlasi [pakalpojumā](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) LinkedIn. Iespējamie lauki tiek uzskaitīti **darbībā Datu atbilstība**, konfigurējot [eksportēšanu](#configure-an-export).

## <a name="known-limitations"></a>Zināmie ierobežojumi

- Privātā saite kombinācijā ar krātuvi Bring your own storage (BYOS) netiek atbalstīta.
- Līdz 100 000 klientu profilu eksportēšanai uz LinkedIn Ads, kas var aizņemt līdz 10 minūtēm.
- Tikai segmenti. Segmentā jābūt vismaz 300 unikāliem profiliem.

## <a name="set-up-connection-to-linkedin-ads"></a>Savienojuma ar LinkedIn Ads iestatīšana

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Dodieties uz **Administrators** > **Savienojumi**.

1. Atlasiet **Pievienot savienojumu** un izvēlieties **LinkedIn reklāmas**.

1. Laukā **Parādāmais nosaukums** piešķiriet savienojumam atpazīstamu nosaukumu. Parādāmais nosaukums un nosaukuma veids raksturo šo savienojumu. Ir ieteicams izvēlēties nosaukumu, kas paskaidro savienojuma nolūku.

1. Izvēlieties, kurš var izmantot šo savienojumu. Pēc noklusējuma tie ir tikai administratori. Papildinformāciju skatiet rakstā [Atļaut līdzstrādniekiem izmantot savienojumu eksportam](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Norādiet sava LinkedIn Campaign Manager konta ID.

1. Pārskatiet datu konfidencialitāti [un atbilstību](connections.md#data-privacy-and-compliance) un atlasiet **Es piekrītu**.

1. Atlasiet **Izveidot savienojumu, lai inicializētu savienojumu**.

1. Atlasiet **Autentificēties ar LinkedIn** un norādiet savus LinkedIn Campaign Manager administratora akreditācijas datus.

1. Atlasiet opciju **Pievienot sevi kā eksporta lietotāju** un sniedziet savus Customer Insights akreditācijas datus.

1. Lai pabeigtu savienošanu, atlasiet **Saglabāt**.

## <a name="configure-an-export"></a>Eksporta konfigurēšana

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Pārejiet uz **Dati** > **Eksportēšana**.

1. Atlasiet **Pievienot eksportu**.

1. Laukā **Savienošana eksportam** atlasiet savienojumu no sadaļas LinkedIn Ads. Ja nav pieejamu savienojumu, sazinieties ar administratoru.

1. Ievadiet eksportēšanas nosaukumu.

1. Izvēlieties, vai vēlaties eksportēt datus, lai sazinātos [ar mērķauditorijas atlasi](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting), [vai uzņēmuma mērķauditorijas atlasi](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) LinkedIn.

1. Sadaļā **Datu atbilstība**, lai atlasītu kontaktpersonu, atlasiet vismaz vienu lauku, kurā ir norādīta klienta e-pasta adrese, Apple Ad ID, Google Ad ID, Google User ID vai vārds un uzvārds. Ja izvēlaties uzņēmuma mērķauditorijas atlasi, atlasiet vismaz vienu lauku, kas apzīmē uzņēmuma nosaukumu, e-pasta domēnu, LinkedIn lapas vietrādi URL, krājumu simbolu vai vietni.

1. Ja vēlaties, pievienojiet laukus, lai vēl vairāk definētu eksportu. Atlasiet **Pievienot atribūtu**, lai kartētu šos laukus.

1. Atlasiet segmentus, kurus vēlaties eksportēt. Matched Audiences programmā LinkedIn Campaign Manager tiks automātiski izveidotas ar eksportējamo segmentu nosaukumu. Katrs segments radīs atsevišķu Matched Audience.

1. Atlasiet **Saglabāt**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
