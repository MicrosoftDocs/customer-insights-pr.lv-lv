---
title: Customer Insights datu eksportēšana uz LinkedIn Ads
description: Uzziniet, kā konfigurēt savienojumu un eksportēt uz LinkedIn Ads.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 867a6541734746f75a35faaa8d3861e0479d6114
ms.sourcegitcommit: 9558ff772ee6c944fcb8db4bfc8cda13b38a1bff
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 11/29/2021
ms.locfileid: "7866897"
---
# <a name="export-segments-to-linkedin-ads-preview"></a>Segmentu eksportēšana uz LinkedIn Ads (priekšskatījums)

Eksportēt vienoto klientu profilu segmentus uz LinkedIn Ads, lai izveidotu Matched Audiences. Izmantojiet Matched Audiences, lai mērķētu uz uzņēmumu un sazinātos ar mērķauditorijas atlasi.

## <a name="prerequisites"></a>Priekšnoteikumi

-   Jums ir [LinkedIn Campaign Manager konts](https://business.linkedin.com/marketing-solutions/ads) un atbilstoši administratora akreditācijas dati.
-   Jums ir [konfigurēti segmenti](segments.md) auditorijas ieskatos.
-   Eksportēto segmentu klientu profilos ir lauks ar e-pasta adresi.

## <a name="known-limitations"></a>Zināmie ierobežojumi

- Customer Insights segmentā ir jābūt vismaz 300 unikāliem profiliem. 
- Programmā LinkedIn Ads viena eksporta laikā var eksportēt līdz pat 100000 klientu profilu.
- Eksportēšana uz LinkedIn Ads attiecas tikai uz segmentiem.
- Līdz pat 100000 klientu profilu eksportēšana uz LinkedIn Ads var aizņemt līdz 10 minūtēm. 

## <a name="set-up-the-connection-to-linkedin-ads"></a>Savienojuma ar LinkedIn Ads krātuvi iestatīšana

1. Auditorijas ieskatos dodieties uz **Administrators** > **Savienojumi**.

1. Atlasiet vienumu **Pievienot savienojumu** un atlasiet **LinkedIn Ads**, lai konfigurētu savienojumu.

1. Laukā **Parādāmais nosaukums** piešķiriet savienojumam atpazīstamu nosaukumu. Parādāmais nosaukums un nosaukuma veids raksturo šo savienojumu. Ir ieteicams izvēlēties nosaukumu, kas paskaidro savienojuma nolūku.

1. Izvēlieties, kurš var izmantot šo savienojumu. Ja nesāksit nekādas darbības, noklusējums būs administratori. Papildinformāciju skatiet rakstā [Atļaut līdzstrādniekiem izmantot savienojumu eksportam](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Norādiet [savu LinkedIn Campaign Manager konta ID](https://www.linkedin.com/help/lms/answer/a424270).

1. Atlasiet **Piekrītu**, lai apstiprinātu **Datu konfidencialitāti un atbilstību**.

1. Lai uzsāktu savienojumu ar Campaign Monitor, atlasiet **Savienot**.

1. Atlasiet **Autentificēties ar LinkedIn** un norādiet administratora akreditācijas datus LinkedIn Campaign Manager.

1. Atlasiet opciju **Pievienot sevi kā eksporta lietotāju** un sniedziet savus Customer Insights akreditācijas datus.

1. Lai pabeigtu savienošanu, atlasiet **Saglabāt**.

## <a name="configure-an-export"></a>Eksporta konfigurēšana

Šo eksportu varat konfigurēt, ja jums ir piekļuve šā veida pieslēgumam. Papildinformāciju skatiet rakstā [Atļaujas, kas nepieciešamas eksporta konfigurēšanai](export-destinations.md#set-up-a-new-export).

1. Pārejiet uz **Dati** > **Eksportēšana**.

1. Lai izveidotu jaunu eksportu, atlasiet **Pievienot galamērķi**.

1. Laukā **Savienošana eksportam** atlasiet savienojumu no sadaļas LinkedIn Ads. Ja šis sadaļas nosaukums nav redzams, šāda veida savienojumi jums nav pieejami.

1. Izvēlieties, vai vēlaties eksportēt datus, lai sazinātos [ar mērķauditorijas atlasi](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting), [vai uzņēmuma mērķauditorijas atlasi](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) LinkedIn. 

1. Sadaļā **Datu atbilstība**, lai atlasītu kontaktpersonu, atlasiet vismaz vienu lauku, kurā ir norādīta klienta e-pasta adrese, Apple Ad ID, Google Ad ID, Google User ID vai vārds un uzvārds. Ja izvēlaties uzņēmuma mērķauditorijas atlasi, atlasiet vismaz vienu lauku, kas apzīmē uzņēmuma nosaukumu, e-pasta domēnu, LinkedIn lapas vietrādi URL, krājumu simbolu vai vietni. Papildu laukus var atlasīt, lai tālāk definētu eksportēšanu. 

1. Atlasiet segmentus, kurus vēlaties eksportēt. Saskaņotās auditorijas LinkedIn Campaign Manager tiks automātiski izveidotas ar eksportējamo segmentu nosaukumu. Katrs segments radīs atsevišķu Matched Audience. 

1. Atlasiet vienumu **Saglabāt**.

Eksporta saglabāšana automātiski nepalaiž eksportu.

Eksports tiek palaists ar katru [plānoto atsvaidzināšanu](system.md#schedule-tab). Varat arī [eksportēt datus pēc pieprasījuma](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Datu konfidencialitāte un atbilstība

Kad iespējojat Dynamics 365 Customer Insights pārraidīt datus LinkedIn Reklāmām, jūs atļaujat pārsūtīt datus ārpus atbilstības robežas Dynamics 365 Customer Insights, tostarp potenciāli sensitīvus datus, piemēram, Personas datus. Microsoft šos datus pārvirzīs atbilstoši jūsu norādījumiem, taču jūs atbildat par to, ka LinkedIn Ads atbilst jebkādiem jūsu privātuma vai drošības nosacījumiem. Papildinformāciju skatiet rakstā [Microsoft Privātuma paziņojums](https://go.microsoft.com/fwlink/?linkid=396732).

Jūsu Dynamics 365 Customer Insights administrators jebkurā laikā var noņemt šo eksportēšanas galamērķi, lai pārtrauktu šīs funkcionalitātes izmantošanu.
