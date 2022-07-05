---
title: Segmentu eksportēšana uz AdRoll (priekšskatījums)
description: Uzziniet, kā konfigurēt savienojumu un eksportēt uz AdRoll.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 13c7dd3b8556ad807fba6c537525b463480e860b
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082830"
---
# <a name="export-segments-to-adroll-preview"></a>Segmentu eksportēšana uz AdRoll (priekšskatījums)

Eksportējiet vienoto klientu profilu segmentus uz AdRoll un izmantojiet tos reklāmai. 

## <a name="prerequisites-for-a-connection"></a>Savienojuma priekšnosacījumi

- Jums ir [AdRoll konts](https://www.adroll.com/) un atbilstošie administratora akreditācijas dati.
- Jūs esat [konfigurējis segmentus](segments.md) programmā Customer Insights.
- Eksportētajos segmentos vienotajiem klientu profiliem ir lauks, kas norāda e-pasta adresi.

## <a name="known-limitations"></a>Zināmie ierobežojumi

- Jūs varat vienlaikus eksportēt uz AdRoll līdz pat 250 000 klientu profilu.
- Jūs nevarat eksportēt segmentus, kuros ir mazāk par 100 klientu profiliem, uz AdRoll. 
- Eksportēšana uz AdRoll ir ierobežota līdz segmentiem.
- Līdz pat 250000 klientu profilu eksportēšana uz AdRoll var paiet līdz 10 minūtēm. 
- To klientu profilu skaits, ko var eksportēt uz AdRoll, ir atkarīgs no jūsu līguma ar AdRoll.

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

1. Laukā **Savienošana eksportam** atlasiet savienojumu no sadaļas AdRoll. Ja neredzat šo sadaļas nosaukumu, tad jums nav pieejami šī tipa savienojumi.

1. Ievadiet savu **AdRoll reklamētāja ID**. Papildinformāciju skatiet sadaļā [AdRoll reklamētāju profili](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).

1. **Datu atbilstības noteikšanas** sadaļas laukā **E-pasts** atlasiet lauku, kas norāda klienta e-pasta adresi. Segmenti ir jāeksportē uz AdRoll.

1. Atlasiet segmentus, kurus vēlaties eksportēt. Atlasiet segmentu, kurā ir vismaz 100 dalībnieku. Nevar eksportēt mazākus segmentus. Turklāt eksportējamā segmenta maksimālais lielums ir 250 000 dalībnieku vienam eksportam. 

1. Atlasiet vienumu **Saglabāt**.

Eksporta saglabāšana automātiski nepalaiž eksportu.

Eksports tiek palaists ar katru [plānoto atsvaidzināšanu](system.md#schedule-tab). 

Varat arī [eksportēt datus pēc pieprasījuma](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Datu konfidencialitāte un atbilstība

Ja iespējojat Dynamics 365 Customer Insights datu pārsūtīšanu uz AdRoll, jūs atļaujat datu pārsūtīšanu ārpus atbilstības robežām Dynamics 365 Customer Insights, ieskaitot iespējami sensitīvus datus, piemēram, personas datus. Microsoft šos datus pārsūtīs pēc jūsu norādēm, bet jūs esat atbildīgs par to, lai nodrošinātu AdRoll atbilstību konfidencialitātes vai drošības saistībām, kas jums varētu rasties. Papildinformāciju skatiet rakstā [Microsoft Privātuma paziņojums](https://go.microsoft.com/fwlink/?linkid=396732).

Jūsu Dynamics 365 Customer Insights administrators var noņemt šo eksportēšanas galamērķi jebkurā laikā, lai pārtrauktu izmantot šo funkcionalitāti.
