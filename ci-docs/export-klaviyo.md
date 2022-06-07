---
title: Customer Insights datu eksportēšana uz Klaviyo
description: Uzziniet, kā konfigurēt savienojumu un eksportēt uz Klaviyo.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: aa6d43884e5e57af4627b7d5a857d3043abcd026
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643772"
---
# <a name="export-segment-lists-to-klaviyo-preview"></a>Eksportēt segmentu sarakstus uz Klaviyo (priekšskatījums)

Eksportējiet vienoto klientu profilu segmentus uz Klaviyo un izmantojiet tos mārketinga darbībām.

## <a name="prerequisites"></a>Priekšnosacījumi

-   Jums ir [Klaviyo konts](https://www.klaviyo.com/) un atbilstošie administratora akreditācijas dati.
-   Programmā Customer Insights ir [konfigurēti](segments.md) segmenti.
-   Eksportētajos segmentos vienotajiem klientu profiliem ir lauks, kas norāda e-pasta adresi.

## <a name="known-limitations"></a>Zināmie ierobežojumi

- Programmā Klaviyo viena eksporta laikā var eksportēt līdz pat 100000 klientu profilu.
- Eksportēšana uz Klaviyo attiecas tikai uz segmentiem.
- Līdz pat 1 miljonam klientu profilu eksportēšana uz Klaviyo var aizņemt līdz 20 minūtēm. 
- To klientu profilu skaits, kurus varat eksportēt uz Klaviyo, ir atkarīgs un ierobežots atkarībā no jūsu līguma ar Klaviyo.

## <a name="set-up-connection-to-klaviyo"></a>Savienojuma ar Klaviyo iestatīšana

1. Dodieties uz **Administrators** > **Savienojumi**.

1. Atlasiet vienumu **Pievienot savienojumu** un izvēlieties **Klaviyo**, lai konfigurētu savienojumu.

1. Laukā **Parādāmais nosaukums** piešķiriet savienojumam atpazīstamu nosaukumu. Parādāmais nosaukums un nosaukuma veids raksturo šo savienojumu. Ir ieteicams izvēlēties nosaukumu, kas paskaidro savienojuma nolūku.

1. Izvēlieties, kurš var izmantot šo savienojumu. Ja nesāksit nekādas darbības, noklusējums būs Administratori. Papildinformāciju skatiet rakstā [Atļaut līdzstrādniekiem izmantot savienojumu eksportam](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Norādiet savu [Galveno API atslēgu](https://help.klaviyo.com/hc/articles/115005062267-How-to-Manage-Your-Account-s-API-Keys), lai turpinātu pieteikties. 

1. Atlasiet **Piekrītu**, lai apstiprinātu **Datu konfidencialitāti un atbilstību**.

1. Atlasiet **Savienot**, lai uzsāktu savienojuma izveidi ar Klaviyo.

1. Atlasiet vienumu **Autentificēties ar Klaviyo** un norādiet savus Klaviyo administratora akreditācijas datus.

1. Atlasiet opciju **Pievienot sevi kā eksporta lietotāju** un sniedziet savus Customer Insights akreditācijas datus.

1. Lai pabeigtu savienošanu, atlasiet **Saglabāt**.

## <a name="configure-an-export"></a>Eksporta konfigurēšana

Šo eksportu varat konfigurēt, ja jums ir piekļuve šā veida pieslēgumam. Papildinformāciju skatiet rakstā [Atļaujas, kas nepieciešamas eksporta konfigurēšanai](export-destinations.md#set-up-a-new-export).

1. Pārejiet uz **Dati** > **Eksportēšana**.

1. Lai izveidotu jaunu eksportu, atlasiet **Pievienot galamērķi**.

1. Laukam **Savienojums eksportēšanai** izvēlieties savienojumu no Klaviyo sadaļas. Ja šis sadaļas nosaukums nav redzams, šāda veida savienojumi jums nav pieejami.

1. Ievadiet savu [**Klaviyo saraksta ID**](https://help.klaviyo.com/hc/articles/115005078647-How-to-Find-a-List-ID).     

3. **Datu atbilstības noteikšanas** sadaļas laukā **E-pasts** atlasiet lauku, kas norāda klienta e-pasta adresi. Tas ir nepieciešams, lai eksportētu segmentus uz Klaviyo.

1. Atlasiet vienumu **Saglabāt**.

Eksporta saglabāšana automātiski nepalaiž eksportu.

Eksports tiek palaists ar katru [plānoto atsvaidzināšanu](system.md#schedule-tab). Varat arī [eksportēt datus pēc pieprasījuma](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Datu konfidencialitāte un atbilstība

Iespējojot Dynamics 365 Customer Insights datu pārsūtīšanai uz Klaviyo, jūs atļaujat datu pārsūtīšanu ārpus atbilstības robežas, kas paredzēta Dynamics 365 Customer Insights, ieskaitot potenciāli sensitīvus datus, piemēram, personas datus. Microsoft šos datus pārsūtīs pēc jūsu norādījuma, bet jūs esat atbildīgs par to, lai Klaviyo atbilstu visām jūsu konfidencialitātes vai drošības saistībām. Papildinformāciju skatiet rakstā [Microsoft Privātuma paziņojums](https://go.microsoft.com/fwlink/?linkid=396732).

Jūsu Dynamics 365 Customer Insights administrators var noņemt šo eksportēšanas galamērķi jebkurā laikā, lai pārtrauktu izmantot šo funkcionalitāti.