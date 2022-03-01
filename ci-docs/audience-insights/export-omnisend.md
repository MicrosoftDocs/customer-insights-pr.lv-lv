---
title: Customer Insights datu eksportēšana uz Omnisend
description: Uzziniet, kā konfigurēt savienojumu un eksportēt uz Omnisend.
ms.date: 05/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8bd692819fa8451ded5e74191ee717f81f87425d
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124520"
---
# <a name="export-segments-to-omnisend-preview"></a>Segmentu eksportēšana uz Omnisend (priekšskatījums)

Eksportējiet vienoto klientu profilu segmentus uz Omnisend un izmantojiet tos mārketinga darbībās.

## <a name="prerequisites"></a>Priekšnosacījumi

-   Jums ir [Omnisend konts](https://www.omnisend.com/) un atbilstošie administratora akreditācijas dati.
-   Jums ir [konfigurēti segmenti](segments.md) auditorijas ieskatos.
-   Eksportētajos segmentos vienotajiem klientu profiliem ir lauks, kas norāda e-pasta adresi.

## <a name="known-limitations"></a>Zināmie ierobežojumi

- Uz Omnisend var eksportēt līdz pat 1 miljonam profilu, un tas var ilgt līdz 4 stundām.
- Eksportēšana uz Omnisend attiecas tikai uz segmentiem.
- Uz Omnisend var eksportēt profilus, kas ir atkarīgi no jūsu līguma ar Omnisend.

## <a name="set-up-connection-to-omnisend"></a>Savienojuma ar Omnisend iestatīšana

1. Dodieties uz **Administrators** > **Savienojumi**.

1. Atlasiet vienumu **Pievienot savienojumu** un atlasiet **Omnisend**, lai konfigurētu savienojumu.

1. Laukā **Parādāmais nosaukums** piešķiriet savienojumam atpazīstamu nosaukumu. Parādāmais nosaukums un nosaukuma veids raksturo šo savienojumu. Ir ieteicams izvēlēties nosaukumu, kas paskaidro savienojuma nolūku.

1. Izvēlieties, kurš var izmantot šo savienojumu. Pēc noklusējuma ir tikai administratori. Papildinformāciju skatiet rakstā [Atļaut līdzstrādniekiem izmantot savienojumu eksportam](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Ievadiet savu [Omnisend API atslēgu](https://support.omnisend.com/en/articles/1061890-generating-api-key).

1. Atlasiet **Piekrītu**, lai apstiprinātu **Datu konfidencialitāti un atbilstību**.

1. Lai uzsāktu savienojumu ar Omnisend, atlasiet **Savienot**.

1. Atlasiet opciju **Pievienot sevi kā eksporta lietotāju** un sniedziet savus Customer Insights akreditācijas datus.

1. Lai pabeigtu savienošanu, atlasiet **Saglabāt**.

## <a name="configure-an-export"></a>Eksporta konfigurēšana

Šo eksportu varat konfigurēt, ja jums ir piekļuve šā veida pieslēgumam. Papildinformāciju skatiet rakstā [Atļaujas, kas nepieciešamas eksporta konfigurēšanai](export-destinations.md#set-up-a-new-export).

1. Pārejiet uz **Dati** > **Eksportēšana**.

1. Lai izveidotu jaunu eksportu, atlasiet **Pievienot galamērķi**.

1. Laukā **Savienošana eksportam** atlasiet savienojumu no sadaļas Omnisend. Ja šis sadaļas nosaukums nav redzams, šāda veida savienojumi jums nav pieejami.

1. Sadaļas **Datu atbilstības** laukā **E-pasts** atlasiet lauku, kas iekļauts vienotajā klientu profilā, kas pārstāv klienta e-pasta adresi. Segmenti ir obligāti jāeksportē uz Omnisend. Ja vēlaties, varat eksportēt Vārdu, Uzvārdu, Pilsētu, Pavalsti un Valsti/reģionu, lai izveidotu personalizētākus e-pastus. Atlasiet **Pievienot atribūtu**, lai kartētu šos laukus.

1. Atlasiet vienumu **Saglabāt**.

Eksporta saglabāšana automātiski nepalaiž eksportu.

Eksports tiek palaists ar katru [plānoto atsvaidzināšanu](system.md#schedule-tab). Varat arī [eksportēt datus pēc pieprasījuma](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Datu konfidencialitāte un atbilstība

Iespējojoet Dynamics 365 Customer Insights datu pārnesi uz Omnisend, jūs ļaujat datus pārnest ārpus Dynamics 365 Customer Insights atbilstības robežām, ieskaitot potenciāli sensitīvus datus, tostarp, personas datus. Microsoft šos datus pārvirzīs atbilstoši jūsu norādījumiem, taču jūs atbildat par to, ka Omnisend atbilst jebkādiem jūsu privātuma vai drošības nosacījumiem. Papildinformāciju skatiet rakstā [Microsoft Privātuma paziņojums](https://go.microsoft.com/fwlink/?linkid=396732).

Jūsu Dynamics 365 Customer Insights administrators var noņemt šo eksportēšanas galamērķi jebkurā laikā, lai pārtrauktu izmantot šo funkcionalitāti.
