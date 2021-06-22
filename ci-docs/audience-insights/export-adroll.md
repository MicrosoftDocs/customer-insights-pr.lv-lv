---
title: Customer Insights datu eksportēšana uz AdRoll
description: Uzziniet, kā konfigurēt savienojumu un eksportēt uz AdRoll.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: dbebc3ee3978ca6ee9d1ad1c15c226479876709f
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124374"
---
# <a name="export-segments-to-adroll-preview"></a>Segmentu eksportēšana uz AdRoll (priekšskatījums)

Eksportējiet vienoto klientu profilu segmentus uz AdRoll un izmantojiet tos reklāmai. 

## <a name="prerequisites-for-a-connection"></a>Savienojuma priekšnosacījumi

-   Jums ir [AdRoll konts](https://www.adroll.com/) un atbilstošie administratora akreditācijas dati.
-   Jums ir [konfigurēti segmenti](segments.md) auditorijas ieskatos.
-   Eksportētajos segmentos vienotajiem klientu profiliem ir lauks, kas norāda e-pasta adresi.

## <a name="known-limitations"></a>Zināmie ierobežojumi

- Vienam eksportam var eksportēt līdz 250 000 profilu uz AdRoll.
- Jūs nevarat eksportēt segmentus, kuros ir mazāk par 100 profiliem, uz AdRoll. 
- Eksportēšana uz AdRoll ir ierobežota līdz segmentiem.
- Līdz 250 000 profilu eksportēšanai uz AdRoll var paiet 10 minūtes. 
- To profilu skaits, ko var eksportēt uz AdRoll, ir atkarīgs, un tas ir ierobežots jūsu līgumā ar AdRoll.

## <a name="set-up-connection-to-adroll"></a>Savienojuma ar AdRoll iestatīšana

1. Dodieties uz **Administrators** > **Savienojumi**.

1. Atlasiet vienumu **Pievienot savienojumu** un atlasiet **AdRoll**, lai konfigurētu savienojumu.

1. Laukā **Parādāmais nosaukums** piešķiriet savienojumam atpazīstamu nosaukumu. Parādāmais nosaukums un nosaukuma veids raksturo šo savienojumu. Ir ieteicams izvēlēties nosaukumu, kas paskaidro savienojuma nolūku.

1. Izvēlieties, kurš var izmantot šo savienojumu. Ja nesāksit nekādas darbības, noklusējums būs Administratori. Papildinformāciju skatiet rakstā [Atļaut līdzstrādniekiem izmantot savienojumu eksportam](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Atlasiet **Piekrītu**, lai apstiprinātu **Datu konfidencialitāti un atbilstību**.

1. Atlasiet **Izveidot savienojumu**, lai inicializētu savienojumu ar AdRoll.

1. Atlasiet **Autentificēties ar AdRoll** un sniedziet savus administratora akreditācijas datus AdRoll. 

1. Atlasiet opciju **Pievienot sevi kā eksporta lietotāju** un sniedziet savus Customer Insights akreditācijas datus.

1. Lai pabeigtu savienošanu, atlasiet **Saglabāt**.

## <a name="configure-an-export"></a>Eksporta konfigurēšana

Šo eksportu varat konfigurēt, ja jums ir piekļuve šā veida pieslēgumam. Papildinformāciju skatiet rakstā [Atļaujas, kas nepieciešamas eksporta konfigurēšanai](export-destinations.md#set-up-a-new-export).

1. Pārejiet uz **Dati** > **Eksportēšana**.

1. Lai izveidotu jaunu eksportu, atlasiet **Pievienot galamērķi**.

1. Laukā **Savienošana eksportam** atlasiet savienojumu no sadaļas AdRoll. Ja šis sadaļas nosaukums nav redzams, šāda veida savienojumi jums nav pieejami.

1. Ievadiet savu **AdRoll Advertiser ID** Papildu informāciju skatiet rakstā [AdRoll Advertiser profili](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).

3. Sadaļas **Datu atbilstības** laukā **E-pasts** atlasiet lauku, kas iekļauts vienotajā klientu profilā, kas pārstāv klienta e-pasta adresi. Segmenti ir jāeksportē uz AdRoll.

1. Atlasiet segmentus, kurus vēlaties eksportēt. Atlasiet segmentu, kurā ir vismaz 100 dalībnieku. Nevar eksportēt mazākus segmentus. Turklāt eksportējamā segmenta maksimālais lielums ir 250 000 dalībnieku vienam eksportam. 

1. Atlasiet vienumu **Saglabāt**.

Eksporta saglabāšana automātiski nepalaiž eksportu.

Eksports tiek palaists ar katru [plānoto atsvaidzināšanu](system.md#schedule-tab). Varat arī [eksportēt datus pēc pieprasījuma](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Datu konfidencialitāte un atbilstība

Ja iespējojat Dynamics 365 Customer Insights datu pārsūtīšanu uz AdRoll, jūs atļaujat datu pārsūtīšanu ārpus atbilstības robežām Dynamics 365 Customer Insights, ieskaitot iespējami sensitīvus datus, piemēram, personas datus. Microsoft šos datus pārsūtīs pēc jūsu norādēm, bet jūs esat atbildīgs par to, lai nodrošinātu AdRoll atbilstību konfidencialitātes vai drošības saistībām, kas jums varētu rasties. Papildinformāciju skatiet rakstā [Microsoft Privātuma paziņojums](https://go.microsoft.com/fwlink/?linkid=396732).

Jūsu Dynamics 365 Customer Insights administrators var noņemt šo eksportēšanas galamērķi jebkurā laikā, lai pārtrauktu izmantot šo funkcionalitāti.
