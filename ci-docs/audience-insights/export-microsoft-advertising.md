---
title: Customer Insights datu eksportēšana Microsoft Advertising
description: Uzziniet, kā konfigurēt savienojumu un eksportēt uz Microsoft Advertising.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 12fd221acb7c0eed443c9b860aca42dcb2b3788c
ms.sourcegitcommit: 23c8973a726b15050e368cc6e0aab78b266a89f6
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 10/08/2021
ms.locfileid: "7618070"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a>Segmentu eksportēšana uz Microsoft Advertising (priekšskatījums)

Eksportēt Customer Insights segmentus uz Microsoft Advertising, lai izveidotu Customer Match auditorijas. Izmantojiet šīs mērķauditorijas savām reklāmu kampaņām.

## <a name="prerequisites"></a>Priekšnosacījumi

-   [Microsoft Advertising konts](https://ads.microsoft.com/) un atbilstošie administratora akreditācijas dati.
-   Jūs esat piekritis Customer Match lietošanas noteikumiem. 
-   [Konfigurēti segmenti](segments.md) Audience Insights.
-   Eksportētajos segmentos vienoto klientu profilos ir lauks ar e-pasta adresi.

## <a name="known-limitations"></a>Zināmie ierobežojumi

- Programmā Microsoft Advertising viena eksporta laikā var eksportēt līdz pat 500000 klientu profilu.
- Eksportēšana uz Microsoft Advertising attiecas tikai uz segmentiem.
- Līdz pat 250000 klientu profilu eksportēšana uz Microsoft Advertising var paiet līdz 10 minūtēm. 


## <a name="set-up-the-connection-to-microsoft-advertising"></a>Iestatiet savienojumu ar Microsoft Advertising

1. Dodieties uz **Administrators** > **Savienojumi**.

1. Atlasiet vienumu **Pievienot savienojumu** un atlasiet **Microsoft Advertising**, lai konfigurētu savienojumu.

1. Laukā **Parādāmais nosaukums** piešķiriet savienojumam atpazīstamu nosaukumu. Parādāmais nosaukums un nosaukuma veids raksturo šo savienojumu. Ir ieteicams izvēlēties nosaukumu, kas paskaidro savienojuma nolūku.

1. Izvēlieties, kurš var izmantot šo savienojumu. Noklusējums ir administratori. Papildinformāciju skatiet rakstā [Atļaut līdzstrādniekiem izmantot savienojumu eksportam](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Atlasiet **Piekrītu**, lai apstiprinātu **Datu konfidencialitāti un atbilstību**.

1. Lai uzsāktu savienojumu ar Microsoft Advertising, atlasiet **Savienot**.

1. Atlasiet **Autentificēties ar Microsoft Advertising** un norādiet savus Microsoft Advertising administratora akreditācijas datus.

1. Atlasiet opciju **Pievienot sevi kā eksporta lietotāju** un sniedziet savus Customer Insights akreditācijas datus.

1. Lai pabeigtu savienošanu, atlasiet **Saglabāt**.

## <a name="configure-an-export"></a>Eksporta konfigurēšana

Šo eksportu varat konfigurēt, ja jums ir piekļuve šā veida pieslēgumam. Papildinformāciju skatiet rakstā [Atļaujas, kas nepieciešamas eksporta konfigurēšanai](export-destinations.md#set-up-a-new-export).

1. Pārejiet uz **Dati** > **Eksportēšana**.

1. Lai izveidotu jaunu eksportu, atlasiet **Pievienot galamērķi**.

1. Laukā **Savienošana eksportam** atlasiet savienojumu no sadaļas Microsoft Advertising. Ja šis sadaļas nosaukums nav redzams, šāda veida savienojumi jums nav pieejami.

1. Atlasiet eksportējamos segmentus. Klientu atbilstības auditorijas programmā Microsoft Advertising tiek automātiski izveidotas ar eksportēšanai atlasīto segmentu nosaukumu. Katrs segments radīs atsevišķu Customer Match auditoriju. 

1. Ievadiet savu **Microsoft Advertising klienta ID un konta ID**. Vietrāža URL parametros varat atrast klienta ID (`cid`) un konta ID (`aid`), kad esat pieteicies Microsoft Advertising.

1. **Datu atbilstības noteikšanas** sadaļas laukā **E-pasts** atlasiet lauku, kas norāda klienta e-pasta adresi. Segmenti ir obligāti jāeksportē uz Microsoft Advertising.

1. Atlasiet vienumu **Saglabāt**.

Eksporta saglabāšana automātiski nepalaiž eksportu.

Eksports tiek palaists ar katru [plānoto atsvaidzināšanu](system.md#schedule-tab). Varat arī [eksportēt datus pēc pieprasījuma](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Datu konfidencialitāte un atbilstība

Iespējojot Dynamics 365 Customer Insights datu pārnesi uz Microsoft Advertising, jūs ļaujat datus pārnest ārpus Dynamics 365 Customer Insights atbilstības robežām, ieskaitot potenciāli sensitīvus datus, tostarp, personas datus. Microsoft šos datus pārvirzīs atbilstoši jūsu norādījumiem, taču jūs atbildat par to, ka Microsoft Advertising atbilst jebkādiem jūsu privātuma vai drošības nosacījumiem. Papildinformāciju skatiet rakstā [Microsoft Privātuma paziņojums](https://go.microsoft.com/fwlink/?linkid=396732).

Lai pārtrauktu izmantot šo funkcionalitāti, jūsu Dynamics 365 Customer Insights administrators var noņemt šo eksportēšanas galamērķi jebkurā laikā.
