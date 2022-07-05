---
title: Segmentu eksportēšana uz Criteo (priekšskatījums)
description: Uzziniet, kā konfigurēt savienojumu un eksportēt uz Criteo.
ms.date: 05/27/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ace9056d200a3179e442132004324a01f0d247b6
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082788"
---
# <a name="export-segments-to-criteo-preview"></a>Segmentu eksportēšana uz Criteo (priekšskatījums)

Eksportējiet vienotu klientu profilu segmentus, lai ģenerētu kampaņas, nodrošinātu e-pasta mārketingu un izmantotu noteiktas klientu grupas ar Criteo.

## <a name="prerequisites-for-connection"></a>Savienojuma priekšnosacījumi

-   Jums ir [Criteo Dynamics atkārtotas mērķauditorijas atlases konts](https://www.criteo.com/login/) un atbilstošie administratora akreditācijas dati.
-   Jums ir [konfigurēti segmenti](segments.md).
-   Eksportētajos segmentos vienotajiem klientu profiliem ir lauks, kas norāda e-pasta adresi.

## <a name="known-limitations"></a>Zināmie ierobežojumi

- Līdz 1 miljonam klientu profilu vienam eksportam uz Criteo.
- Eksports uz Criteo attiecas tikai uz segmentiem.
- 1 miljona klientu profilu segmentu eksports var ilgt līdz 30 minūtēm. 
- Klientu profilu skaits, ko varat eksportēt uz Criteo, ir atkarīgs un ierobežots no jūsu līguma ar Criteo.

## <a name="set-up-connection-to-criteo"></a>Savienojuma ar Criteo iestatīšana

1. Dodieties uz **Administrators** > **Savienojumi**.

1. Atlasiet **Pievienot savienojumu** un izvēlieties **Criteo**, lai konfigurētu savienojumu.

1. Laukā **Parādāmais nosaukums** piešķiriet savienojumam atpazīstamu nosaukumu. Parādāmais nosaukums un nosaukuma veids raksturo šo savienojumu. Ir ieteicams izvēlēties nosaukumu, kas paskaidro savienojuma nolūku.

1. Izvēlieties, kurš var izmantot šo savienojumu. Ja nesāksit nekādas darbības, noklusējums būs Administratori. Papildinformāciju skatiet rakstā [Atļaut līdzstrādniekiem izmantot savienojumu eksportam](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Atlasiet **Es piekrītu**, lai apstiprinātu **datu konfidencialitāti un atbilstību**, un atlasiet **Izveidot savienojumu**, lai inicializētu savienojumu ar Criteo.

1. Atlasiet **Autentificēties ar Criteo** un norādiet savu administratora lietotājvārdu un akreditācijas datus Criteo. 

1. Atlasiet opciju **Pievienot sevi kā eksporta lietotāju** un sniedziet savus Customer Insights akreditācijas datus.

1. Lai pabeigtu savienošanu, atlasiet **Saglabāt**.

## <a name="configure-an-export"></a>Eksporta konfigurēšana

Šo eksportu varat konfigurēt, ja jums ir piekļuve šā veida pieslēgumam. Papildinformāciju skatiet rakstā [Atļaujas, kas nepieciešamas eksporta konfigurēšanai](export-destinations.md#set-up-a-new-export).

1. Pārejiet uz **Dati** > **Eksportēšana**.

1. Lai izveidotu jaunu eksportu, atlasiet **Pievienot galamērķi**.

1. **Laukā Savienojums eksportēšanai** izvēlieties savienojumu no sadaļas Criteo. Ja šis sadaļas nosaukums nav redzams, šāda veida savienojumi jums nav pieejami. 

1. **Datu atbilstības noteikšanas** sadaļas laukā **E-pasts** atlasiet lauku, kas norāda klienta e-pasta adresi. 

1. Pēc izvēles varat eksportēt **reklāmdevēja ID** un vārdu un **uzvārdu**

1. Atlasiet segmentus, kurus vēlaties eksportēt. 

1. Atlasiet **Saglabāt**.

Eksporta saglabāšana automātiski nepalaiž eksportu.

Eksports tiek palaists ar katru [plānoto atsvaidzināšanu](system.md#schedule-tab). Varat arī [eksportēt datus pēc pieprasījuma](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Datu konfidencialitāte un atbilstība

Kad jūs iespējojat Dynamics 365 Customer Insights datu pārsūtīšanu uz Criteo, jūs atļaujat pārsūtīt datus ārpus atbilstības robežas, tostarp potenciāli sensitīvus Dynamics 365 Customer Insights datus, piemēram, Personas datus. Microsoft pārsūtīs šādus datus pēc jūsu norādījumiem, taču jūs esat atbildīgs par to, lai Criteo izpildītu visas jūsu iespējamās konfidencialitātes vai drošības saistības. Papildinformāciju skatiet rakstā [Microsoft Privātuma paziņojums](https://go.microsoft.com/fwlink/?linkid=396732).
Jūsu Dynamics 365 Customer Insights administrators var noņemt šo eksportēšanas galamērķi jebkurā laikā, lai pārtrauktu izmantot šo funkcionalitāti.


[!INCLUDE[footer-include](includes/footer-banner.md)]
