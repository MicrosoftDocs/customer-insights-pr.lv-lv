---
title: Segmentu sarakstu eksportēšana uz Snapchat (priekšskatījums)
description: Uzziniet, kā konfigurēt savienojumu un eksportēt uz Snapchat.
ms.date: 06/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: abe04cd1464c3f7df969da3c769329382d603d7e
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 06/29/2022
ms.locfileid: "9051922"
---
# <a name="export-segments-to-snapchat-preview"></a>Segmentu sarakstu eksportēšana uz Snapchat (priekšskatījums)

Eksportējiet vienoto klientu profilu segmentus uz Snapchat un izmantojiet tos reklāmā. 

## <a name="prerequisites-for-a-connection"></a>Savienojuma priekšnosacījumi

-   Jums ir [Snapchat Business konts](https://business.snapchat.com/), [Snapchat Ads konts](https://ads.snapchat.com/) un atbilstošie administratora akreditācijas dati. YOu ir jābūt vismaz organizācijas konta dalībniekam un konkrēta reklāmas konta datu pārvaldniekam. 
-   Jums ir vismaz viena auditorija Snapchat auditorijas pārvaldniekā, kas ir SAM tipa (Snap Audience Match). 
-   Jūs esat [konfigurējis segmentus](segments.md) programmā Customer Insights.
-   Eksportētajos segmentos vienotajiem klientu profiliem ir lauks, kas norāda e-pasta adresi.

## <a name="known-limitations"></a>Zināmie ierobežojumi

- Eksportēšana uz Snapchat attiecas tikai uz segmentiem.
- Līdz pat 1 miljonam klientu profilu eksportēšana uz Snapchat var aizņemt līdz 15 minūtēm. 

## <a name="set-up-connection-to-snapchat"></a>Savienojuma ar Snapchat iestatīšana

1. Dodieties uz **Administrators** > **Savienojumi**.

1. Atlasiet vienumu **Pievienot savienojumu** un atlasiet **Snapchat**, lai konfigurētu savienojumu.

1. Laukā **Parādāmais nosaukums** piešķiriet savienojumam atpazīstamu nosaukumu. Parādāmais nosaukums un nosaukuma veids raksturo šo savienojumu. Ir ieteicams izvēlēties nosaukumu, kas paskaidro savienojuma nolūku.

1. Izvēlieties, kurš var izmantot šo savienojumu. Ja nesāksit nekādas darbības, noklusējums būs Administratori. Papildinformāciju skatiet rakstā [Atļaut līdzstrādniekiem izmantot savienojumu eksportam](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Atlasiet **Piekrītu**, lai apstiprinātu **Datu konfidencialitāti un atbilstību**.

1. Lai uzsāktu savienojumu ar Snapchat, atlasiet **Savienot**.

1. Atlasiet **Autentificēt ar Snapchat** un norādiet savus Snapchat administratora akreditācijas datus. 

1. Atlasiet opciju **Pievienot sevi kā eksporta lietotāju** un sniedziet savus Customer Insights akreditācijas datus.

1. Lai pabeigtu savienošanu, atlasiet **Saglabāt**.

## <a name="configure-an-export"></a>Eksporta konfigurēšana

Šo eksportu varat konfigurēt, ja jums ir piekļuve šā veida pieslēgumam. Papildinformāciju skatiet rakstā [Atļaujas, kas nepieciešamas eksporta konfigurēšanai](export-destinations.md#set-up-a-new-export).

1. Pārejiet uz **Dati** > **Eksportēšana**.

1. Lai izveidotu jaunu eksportu, atlasiet **Pievienot galamērķi**.

1. Laukā **Savienošana eksportam** atlasiet savienojumu no sadaļas Snapchat. Ja šis sadaļas nosaukums nav redzams, šāda veida savienojumi jums nav pieejami.

1. Ievadiet Snapchat segmenta [**/ auditorijas ID**](https://businesshelp.snapchat.com/s/article/custom-audiences). Auditorijas ID var atrast vietrādī URL pēc auditorijas atlasīšanas Snapchat Audience Manager. 

1. **Datu atbilstības noteikšanas** sadaļas laukā **E-pasts** atlasiet lauku, kas norāda klienta e-pasta adresi. Segmenti ir obligāti jāeksportē uz Snapchat.

1. Atlasiet segmentus, kurus vēlaties eksportēt. 

1. Atlasiet vienumu **Saglabāt**.

Eksporta saglabāšana automātiski nepalaiž eksportu.

Eksports tiek palaists ar katru [plānoto atsvaidzināšanu](system.md#schedule-tab). Varat arī [eksportēt datus pēc pieprasījuma](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Datu konfidencialitāte un atbilstība

Iespējojiet Dynamics 365 Customer Insights datu pārnesi uz Snapchat, jūs ļaujat datus pārnest ārpus Dynamics 365 Customer Insights atbilstības robežām, ieskaitot potenciāli sensitīvus datus, tostarp, personas datus. Microsoft šos datus pārvirzīs atbilstoši jūsu norādījumiem, taču jūs atbildat par to, ka Snapchat atbilst jebkādiem jūsu privātuma vai drošības nosacījumiem. Papildinformāciju skatiet rakstā [Microsoft Privātuma paziņojums](https://go.microsoft.com/fwlink/?linkid=396732).

Jūsu Dynamics 365 Customer Insights administrators var noņemt šo eksportēšanas galamērķi jebkurā laikā, lai pārtrauktu izmantot šo funkcionalitāti.
