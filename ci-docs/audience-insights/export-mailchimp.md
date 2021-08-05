---
title: Customer Insights datu eksportēšana uz Mailchimp
description: Uzziniet, kā konfigurēt savienojumu un eksportēt uz Mailchimp.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ac6642c0ce02f1a92458a16250fd3b4cdef5fd1c
ms.sourcegitcommit: adb9c43ddaba25e511535d78a4bcf8815f154a7b
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 07/06/2021
ms.locfileid: "6362518"
---
# <a name="export-segments-to-mailchimp-preview"></a>Segmentu eksportēšana uz Mailchimp (priekšskatījums)

Eksportējiet vienotu klientu profilu segmentus uz Mailchimp, lai izveidotu informatīvas vēstules un e-pasta kampaņas.

## <a name="prerequisites-for-connection"></a>Savienojuma priekšnosacījumi

-   Jums ir [Mailchimp konts](https://mailchimp.com/) un atbilstošie administratora akreditācijas dati.
-   Mailchimp ir esošas auditorijas un attiecīgie ID. Papildinformāciju skatiet rakstā [Mailchimp auditorijas](https://mailchimp.com/help/create-audience/).
-   Jums ir [konfigurēti segmenti](segments.md)
-   Eksportētajos segmentos vienotajiem klientu profiliem ir lauks, kas norāda e-pasta adresi.

## <a name="known-limitations"></a>Zināmie ierobežojumi

- Līdz 1 000 000 profilu, eksportējot uz Mailchimp.
- Eksportēšana uz Mailchimp ir ierobežota līdz segmentiem.
- Segmentu ar 1 miljonu profilu eksportēšana var aizņemt līdz trim stundām. 
- To profilu skaits, ko var eksportēt uz Mailchimp, ir atkarīgs, un tas ir ierobežots jūsu līgumā ar Mailchimp.

## <a name="set-up-connection-to-mailchimp"></a>Savienojuma ar Mailchimp iestatīšana

1. Dodieties uz **Administrators** > **Savienojumi**.

1. Atlasiet vienumu **Pievienot savienojumu** un izvēlieties **Mailchimp**, lai konfigurētu savienojumu.

1. Laukā **Parādāmais nosaukums** piešķiriet savienojumam atpazīstamu nosaukumu. Parādāmais nosaukums un nosaukuma veids raksturo šo savienojumu. Ir ieteicams izvēlēties nosaukumu, kas paskaidro savienojuma nolūku.

1. Izvēlieties, kurš var izmantot šo savienojumu. Ja nesāksit nekādas darbības, noklusējums būs Administratori. Papildinformāciju skatiet rakstā [Atļaut līdzstrādniekiem izmantot savienojumu eksportam](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Atlasiet **Piekrītu**, lai apstiprinātu **Datu konfidencialitāti un atbilstību**.

1. Lai uzsāktu savienojumu ar Mailchimp, atlasiet **Savienot**.

1. Atlasiet **Autentificēties ar Mailchimp** un sniedziet savus Mailchimp akreditācijas datus.

1. Atlasiet opciju **Pievienot sevi kā eksporta lietotāju** un sniedziet savus Customer Insights akreditācijas datus.

1. Lai pabeigtu savienošanu, atlasiet **Saglabāt**. 

## <a name="configure-the-connector"></a>Savienotāja konfigurēšana

Šo eksportu varat konfigurēt, ja jums ir piekļuve šā veida pieslēgumam. Papildinformāciju skatiet rakstā [Atļaujas, kas nepieciešamas eksporta konfigurēšanai](export-destinations.md#set-up-a-new-export).

1. Pārejiet uz **Dati**> **Eksportēšana**.

1. Lai izveidotu jaunu eksportu, atlasiet **Pievienot galamērķi**.

1. Laukā **Savienošana eksportam** atlasiet savienojumu no sadaļas Mailchimp. Ja šis sadaļas nosaukums nav redzams, šāda veida savienojumi jums nav pieejami.

1. Ievadiet **[Mailchimp auditorijas ID](https://mailchimp.com/help/find-audience-id/)**

3. Sadaļas **Datu atbilstības** laukā **E-pasts** atlasiet lauku, kas iekļauts vienotajā klientu profilā, kas pārstāv klienta e-pasta adresi. 

1. Ja vēlaties, varat eksportēt **Vārdu** un **Uzvārdu**, lai izveidotu personalizētākus e-pastus. Atlasiet **Pievienot atribūtu**, lai kartētu šos laukus.

1. Atlasiet segmentus, kurus vēlaties eksportēt. Kopsummā var eksportēt līdz 1 000 000 klientu profilu uz Mailchimp.

1. Atlasiet vienumu **Saglabāt**.

Eksporta saglabāšana automātiski nepalaiž eksportu.

Eksports tiek palaists ar katru [plānoto atsvaidzināšanu](system.md#schedule-tab). Varat arī [eksportēt datus pēc pieprasījuma](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Datu konfidencialitāte un atbilstība

Ja iespējojat Dynamics 365 Customer Insights datu pārsūtīšanu uz Mailchimp, jūs atļaujat datu pārsūtīšanu ārpus atbilstības robežām Dynamics 365 Customer Insights, ieskaitot iespējami sensitīvus datus, piemēram, personas datus. Microsoft šos datus pārsūtīs pēc jūsu norādēm, bet jūs esat atbildīgs par to, lai nodrošinātu Mailchimp atbilstību konfidencialitātes vai drošības saistībām, kas jums varētu rasties. Papildinformāciju skatiet rakstā [Microsoft Privātuma paziņojums](https://go.microsoft.com/fwlink/?linkid=396732).
Jūsu Dynamics 365 Customer Insights administrators var noņemt šo eksportēšanas galamērķi jebkurā laikā, lai pārtrauktu izmantot šo funkcionalitāti.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
