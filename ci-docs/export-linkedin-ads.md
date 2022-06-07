---
title: Customer Insights datu eksportēšana uz LinkedIn Ads
description: Uzziniet, kā konfigurēt savienojumu un eksportēt uz LinkedIn Ads.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: bf1d12ffbd7a4cfd7d268fea8a1f90cc37589e00
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643929"
---
# <a name="export-segments-to-linkedin-ads-preview"></a>Segmentu eksportēšana uz LinkedIn Ads (priekšskatījums)

Eksportēt vienoto klientu profilu segmentus uz LinkedIn Ads, lai izveidotu Matched Audiences. Izmantojiet Matched Audiences, lai mērķētu uz uzņēmumu un sazinātos ar mērķauditorijas atlasi.

## <a name="prerequisites"></a>Priekšnosacījumi

-   Jums ir [LinkedIn Campaign Manager konts](https://business.linkedin.com/marketing-solutions/ads) un atbilstošie administratora akreditācijas dati.
-   Programmā Customer Insights ir [konfigurēti](segments.md) segmenti.
-   Eksportēto segmentu klientu profilos ir lauks ar e-pasta adresi.

## <a name="known-limitations"></a>Zināmie ierobežojumi

- Jūsu segmentā Customer Insights ir jābūt vismaz 300 unikāliem profiliem. 
- Programmā LinkedIn Ads viena eksporta laikā var eksportēt līdz pat 100000 klientu profilu.
- Eksportēšana uz LinkedIn Ads attiecas tikai uz segmentiem.
- Līdz pat 100000 klientu profilu eksportēšana uz LinkedIn Ads var aizņemt līdz 10 minūtēm. 

## <a name="set-up-the-connection-to-linkedin-ads"></a>Savienojuma ar LinkedIn Ads krātuvi iestatīšana

1. Dodieties uz **Administrators** > **Savienojumi**.

1. Atlasiet vienumu **Pievienot savienojumu** un atlasiet **LinkedIn Ads**, lai konfigurētu savienojumu.

1. Laukā **Parādāmais nosaukums** piešķiriet savienojumam atpazīstamu nosaukumu. Parādāmais nosaukums un nosaukuma veids raksturo šo savienojumu. Ir ieteicams izvēlēties nosaukumu, kas paskaidro savienojuma nolūku.

1. Izvēlieties, kurš var izmantot šo savienojumu. Ja nesāksit nekādas darbības, noklusējums būs administratori. Papildinformāciju skatiet rakstā [Atļaut līdzstrādniekiem izmantot savienojumu eksportam](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Norādiet sava [LinkedIn Campaign Manager konta ID](https://www.linkedin.com/help/lms/answer/a424270).

1. Atlasiet **Piekrītu**, lai apstiprinātu **Datu konfidencialitāti un atbilstību**.

1. Lai uzsāktu savienojumu ar Campaign Monitor, atlasiet **Savienot**.

1. Atlasiet **Autentificēties ar LinkedIn** un norādiet savus LinkedIn Campaign Manager administratora akreditācijas datus.

1. Atlasiet opciju **Pievienot sevi kā eksporta lietotāju** un sniedziet savus Customer Insights akreditācijas datus.

1. Lai pabeigtu savienošanu, atlasiet **Saglabāt**.

## <a name="configure-an-export"></a>Eksporta konfigurēšana

Šo eksportu varat konfigurēt, ja jums ir piekļuve šā veida pieslēgumam. Papildinformāciju skatiet rakstā [Atļaujas, kas nepieciešamas eksporta konfigurēšanai](export-destinations.md#set-up-a-new-export).

1. Pārejiet uz **Dati** > **Eksportēšana**.

1. Lai izveidotu jaunu eksportu, atlasiet **Pievienot galamērķi**.

1. Laukā **Savienošana eksportam** atlasiet savienojumu no sadaļas LinkedIn Ads. Ja šis sadaļas nosaukums nav redzams, šāda veida savienojumi jums nav pieejami.

1. Izvēlieties, vai vēlaties eksportēt datus, lai sazinātos [ar mērķauditorijas atlasi](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting), [vai uzņēmuma mērķauditorijas atlasi](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) LinkedIn. 

1. Sadaļā **Datu atbilstība**, lai atlasītu kontaktpersonu, atlasiet vismaz vienu lauku, kurā ir norādīta klienta e-pasta adrese, Apple Ad ID, Google Ad ID, Google User ID vai vārds un uzvārds. Ja izvēlaties uzņēmuma mērķauditorijas atlasi, atlasiet vismaz vienu lauku, kas apzīmē uzņēmuma nosaukumu, e-pasta domēnu, LinkedIn lapas vietrādi URL, krājumu simbolu vai vietni. Papildu laukus var atlasīt, lai tālāk definētu eksportēšanu. 

1. Atlasiet segmentus, kurus vēlaties eksportēt. Matched Audiences programmā LinkedIn Campaign Manager tiks automātiski izveidotas ar eksportējamo segmentu nosaukumu. Katrs segments radīs atsevišķu Matched Audience. 

1. Atlasiet vienumu **Saglabāt**.

Eksporta saglabāšana automātiski nepalaiž eksportu.

Eksports tiek palaists ar katru [plānoto atsvaidzināšanu](system.md#schedule-tab). Varat arī [eksportēt datus pēc pieprasījuma](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Datu konfidencialitāte un atbilstība

Iespējojot Dynamics 365 Customer Insights datu pārnesi uz LinkedIn Ads, jūs ļaujat datus pārnest ārpus Dynamics 365 Customer Insights atbilstības robežām, ieskaitot potenciāli sensitīvus datus, tostarp, personas datus. Microsoft šos datus pārvirzīs atbilstoši jūsu norādījumiem, taču jūs atbildat par to, ka LinkedIn Ads atbilst jebkādiem jūsu privātuma vai drošības nosacījumiem. Papildinformāciju skatiet rakstā [Microsoft Privātuma paziņojums](https://go.microsoft.com/fwlink/?linkid=396732).

Lai pārtrauktu izmantot šo funkcionalitāti, jūsu Dynamics 365 Customer Insights administrators var noņemt šo eksportēšanas galamērķi jebkurā laikā.