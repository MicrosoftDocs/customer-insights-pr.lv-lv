---
title: Customer Insights datu eksportēšana uz Campaign Monitor
description: Uzziniet, kā konfigurēt savienojumu un eksportēt uz Campaign Monitor.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 063de14c4ffd51b3afd89786606d7b37626695dc
ms.sourcegitcommit: 23c8973a726b15050e368cc6e0aab78b266a89f6
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 10/08/2021
ms.locfileid: "7618990"
---
# <a name="export-segments-to-campaign-monitor-preview"></a>Segmentu eksportēšana uz Campaign Monitor (priekšskatījums)

Eksportējiet vienoto klientu profilu segmentus uz Campaign Monitor un izmantojiet tos mārketinga darbībās.

## <a name="prerequisites"></a>Priekšnosacījumi

-   Jums ir [Campaign Monitor konts](https://www.campaignmonitor.com/) un atbilstošie administratora akreditācijas dati.
-   Jums ir [konfigurēti segmenti](segments.md) auditorijas ieskatos.
-   Eksportētajos segmentos vienotajiem klientu profiliem ir lauks, kas norāda e-pasta adresi.

## <a name="known-limitations"></a>Zināmie ierobežojumi

- Vienā eksportā uz Kampaņas pārraudzīšanu var eksportēt līdz pat 1 miljoniem klientu profilu.
- Eksportēšana uz Campaign Monitor attiecas tikai uz segmentiem.
- Līdz pat 1 miljoniem klientu profilu eksportēšanai uz Kampaņas pārraudzīšanu var paiet līdz 20 minūtēm. 
- To klientu profilu skaits, kurus varat eksportēt uz Kampaņas pārraudzīšanu, ir atkarīgs un ierobežots atkarībā no jūsu līguma ar Kampaņas pārraudzīšanu.

## <a name="set-up-connection-to-campaign-monitor"></a>Savienojuma ar Campaign Monitor iestatīšana

1. Dodieties uz **Administrators** > **Savienojumi**.

1. Atlasiet vienumu **Pievienot savienojumu** un atlasiet **Campaign Monitor**, lai konfigurētu savienojumu.

1. Laukā **Parādāmais nosaukums** piešķiriet savienojumam atpazīstamu nosaukumu. Parādāmais nosaukums un nosaukuma veids raksturo šo savienojumu. Ir ieteicams izvēlēties nosaukumu, kas paskaidro savienojuma nolūku.

1. Izvēlieties, kurš var izmantot šo savienojumu. Ja nesāksit nekādas darbības, noklusējums būs Administratori. Papildinformāciju skatiet rakstā [Atļaut līdzstrādniekiem izmantot savienojumu eksportam](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Atlasiet **Piekrītu**, lai apstiprinātu **Datu konfidencialitāti un atbilstību**.

1. Lai uzsāktu savienojumu ar Campaign Monitor, atlasiet **Savienot**.

1. Atlasiet **Autentificēt ar Campaign Monitor** un norādiet savus Campaign Monitor administratora akreditācijas datus.

1. Atlasiet opciju **Pievienot sevi kā eksporta lietotāju** un sniedziet savus Customer Insights akreditācijas datus.

1. Lai pabeigtu savienošanu, atlasiet **Saglabāt**.

## <a name="configure-an-export"></a>Eksporta konfigurēšana

Šo eksportu varat konfigurēt, ja jums ir piekļuve šā veida pieslēgumam. Papildinformāciju skatiet rakstā [Atļaujas, kas nepieciešamas eksporta konfigurēšanai](export-destinations.md#set-up-a-new-export).

1. Pārejiet uz **Dati** > **Eksportēšana**.

1. Lai izveidotu jaunu eksportu, atlasiet **Pievienot galamērķi**.

1. Laukā **Savienošana eksportam** atlasiet savienojumu no sadaļas Campaign Monitor. Ja šis sadaļas nosaukums nav redzams, šāda veida savienojumi jums nav pieejami.

1. Ievadiet savu [**Campaign Monitor saraksta ID**](https://www.campaignmonitor.com/api/getting-started/#your-list-id).    
   Vispirms [Ģenerējiet API atslēgu](https://www.campaignmonitor.com/api/getting-started/) no Campaign Monitor **Konta iestatījumiem**, lai skatītu API saraksta ID.  

1. **Datu atbilstības noteikšanas** sadaļas laukā **E-pasts** atlasiet lauku, kas norāda klienta e-pasta adresi. Segmenti ir obligāti jāeksportē uz Campaign Monitor.

1. Atlasiet vienumu **Saglabāt**.

Eksporta saglabāšana automātiski nepalaiž eksportu.

Eksports tiek palaists ar katru [plānoto atsvaidzināšanu](system.md#schedule-tab). Varat arī [eksportēt datus pēc pieprasījuma](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Datu konfidencialitāte un atbilstība

Iespējojot Dynamics 365 Customer Insights datu pārnesi uz Campaign Monitor, jūs ļaujat datus pārnest ārpus Dynamics 365 Customer Insights atbilstības robežām, ieskaitot potenciāli sensitīvus datus, tostarp, personas datus. Microsoft šos datus pārvirzīs atbilstoši jūsu norādījumiem, taču jūs atbildat par to, ka Campaign Monitor atbilst jebkādiem jūsu privātuma vai drošības nosacījumiem. Papildinformāciju skatiet rakstā [Microsoft Privātuma paziņojums](https://go.microsoft.com/fwlink/?linkid=396732).

Jūsu Dynamics 365 Customer Insights administrators var noņemt šo eksportēšanas galamērķi jebkurā laikā, lai pārtrauktu izmantot šo funkcionalitāti.
