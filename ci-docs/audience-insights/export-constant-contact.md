---
title: Customer Insights datu eksportēšana uz Constant Contact
description: Uzziniet, kā konfigurēt savienojumu un eksportēt uz Constant Contact.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3a9372cc4ffa4fb112a96b1286aee9dc35059a50
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760581"
---
# <a name="export-segment-lists-to-constant-contact-preview"></a>Segmentu sarakstu eksportēšana uz Constant Contact (priekšskatījums)

Eksportējiet vienoto klientu profilu segmentus uz Constant Contact un izmantojiet tos mārketinga darbībās. 

## <a name="prerequisites-for-a-connection"></a>Savienojuma priekšnosacījumi

-   Jums ir [Constant Contact konts](https://www.constantcontact.com/account-home) un atbilstošie administratora akreditācijas dati.
-   Jums ir [konfigurēti segmenti](segments.md) auditorijas ieskatos.
-   Eksportētajos segmentos vienotajiem klientu profiliem ir lauks, kas norāda e-pasta adresi.

## <a name="known-limitations"></a>Zināmie ierobežojumi

- Jūs varat eksportēt līdz 1 miljonam profilu uz katru eksportu uz Constant Contact.
- Eksportēšana uz Constant Contact attiecas tikai uz segmentiem.
- Līdz 1 miljona profilu eksportēšana uz Constant Contact var aizņemt līdz 1 stundai. 
- Profilu, kurus varat eksportēt uz Constant Contact, skaits ir atkarīgs no jūsu līguma ar Constant Contract un attiecas vienīgi uz tā tvērumu.

## <a name="set-up-connection-to-constant-contact"></a>Savienojuma ar Constant Contact izveide

1. Dodieties uz **Administrators** > **Savienojumi**.

1. Atlasiet vienumu **Pievienot savienojumu** un atlasiet **Constant Contact**, lai konfigurētu savienojumu.

1. Laukā **Parādāmais nosaukums** piešķiriet savienojumam atpazīstamu nosaukumu. Parādāmais nosaukums un nosaukuma veids raksturo šo savienojumu. Ir ieteicams izvēlēties nosaukumu, kas paskaidro savienojuma nolūku.

1. Izvēlieties, kurš var izmantot šo savienojumu. Ja nesāksit nekādas darbības, noklusējums būs Administratori. Papildinformāciju skatiet rakstā [Atļaut līdzstrādniekiem izmantot savienojumu eksportam](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Atlasiet **Piekrītu**, lai apstiprinātu **Datu konfidencialitāti un atbilstību**.

1. Lai uzsāktu savienojumu ar Constant Contact, atlasiet **Savienot**.

1. Atlasiet **Autentificēt ar AdRoll** un norādiet savus Constant Contact administratora akreditācijas datus. 

1. Atlasiet opciju **Pievienot sevi kā eksporta lietotāju** un sniedziet savus Customer Insights akreditācijas datus.

1. Lai pabeigtu savienošanu, atlasiet **Saglabāt**.

## <a name="configure-an-export"></a>Eksporta konfigurēšana

Šo eksportu varat konfigurēt, ja jums ir piekļuve šā veida pieslēgumam. Papildinformāciju skatiet rakstā [Atļaujas, kas nepieciešamas eksporta konfigurēšanai](export-destinations.md#set-up-a-new-export).

1. Pārejiet uz **Dati** > **Eksportēšana**.

1. Lai izveidotu jaunu eksportu, atlasiet **Pievienot galamērķi**.

1. Laukā **Savienošana eksportam** atlasiet savienojumu no sadaļas Constant Contact. Ja šis sadaļas nosaukums nav redzams, šāda veida savienojumi jums nav pieejami.

1. Ievadiet savu [**Constant Contact saraksta ID**](https://app.constantcontact.com/pages/contacts/ui#lists). Constant Contact atveriet sarakstu, lai URL vietrādī atrastu saraksta ID.

1. Sadaļas **Datu atbilstības** laukā **E-pasts** atlasiet lauku, kas iekļauts vienotajā klientu profilā, kas pārstāv klienta e-pasta adresi. Segmenti ir obligāti jāeksportē uz Constant Contact.

1. Ja vēlaties, varat eksportēt Vārds un Uzvārds kā papildu laukus, lai izveidotu vairāk personalizētu e-pasta ziņojumu. Atlasiet **Pievienot atribūtu**, lai kartētu šos laukus.

1. Atlasiet segmentus, kurus vēlaties eksportēt.

1. Atlasiet vienumu **Saglabāt**.

Eksporta saglabāšana automātiski nepalaiž eksportu.

Eksports tiek palaists ar katru [plānoto atsvaidzināšanu](system.md#schedule-tab). Varat arī [eksportēt datus pēc pieprasījuma](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Datu konfidencialitāte un atbilstība

Iespējojot Dynamics 365 Customer Insights datu pārnesi uz Constant Contact, jūs ļaujat datus pārnest ārpus Dynamics 365 Customer Insights atbilstības robežām, ieskaitot potenciāli sensitīvus datus, tostarp, personas datus. Microsoft šos datus pārvirzīs atbilstoši jūsu norādījumiem, taču jūs atbildat par to, ka Constant Contact atbilst jebkādiem jūsu privātuma vai drošības nosacījumiem. Papildinformāciju skatiet rakstā [Microsoft Privātuma paziņojums](https://go.microsoft.com/fwlink/?linkid=396732).

Jūsu Dynamics 365 Customer Insights administrators var noņemt šo eksportēšanas galamērķi jebkurā laikā, lai pārtrauktu izmantot šo funkcionalitāti.