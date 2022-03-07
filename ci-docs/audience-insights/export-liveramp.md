---
title: LiveRamp savienotājs
description: Uzziniet, kā konfigurēt savienojumu un eksportēt uz LiveRamp.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 4c0f58083e8486d2042d8efcc8b3690020efb1c3
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 02/16/2022
ms.locfileid: "8226361"
---
# <a name="export-segments-to-liverampreg-preview"></a>Segmentu eksportēšana uz LiveRamp&reg; (priekšskatījums)

Aktivizējiet savus datus LiveRamp, lai savienotos ar vairāk nekā 500 digitālajām, sociālajām un TV platformām. Strādājiet ar saviem datiem risinājumā LiveRamp, lai mērķētu, izlaistu un personalizētu reklāmas kampaņas.

## <a name="prerequisites-for-a-connection"></a>Savienojuma priekšnosacījumi

- Lai izmantotu šo savienotāju, ir nepieciešams LiveRamp abonements.
- Lai iegūtu abonementu, [sazinieties tieši ar LiveRamp](https://liveramp.com/contact/). [Uzzināt vairāk par LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).

## <a name="set-up-connection-to-liveramp"></a>Savienojuma ar LiveRamp iestatīšana

1. Dodieties uz **Administrators** > **Savienojumi**.

1. Atlasiet vienumu **Pievienot savienojumu** un atlasiet **LiveRamp**, lai konfigurētu savienojumu.

1. Laukā **Parādāmais nosaukums** piešķiriet savienojumam atpazīstamu nosaukumu. Parādāmais nosaukums un nosaukuma veids raksturo šo savienojumu. Ir ieteicams izvēlēties nosaukumu, kas paskaidro savienojuma nolūku.

1. Izvēlieties, kurš var izmantot šo savienojumu. Ja nesāksit nekādas darbības, noklusējums būs Administratori. Papildinformāciju skatiet rakstā [Atļaut līdzstrādniekiem izmantot savienojumu eksportam](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Norādiet **Lietotājvārds** un **Parole** savam LiveRamp Drošajam FTP (SFTP) kontam.
Šie akreditācijas dati var atšķirties no jūsu LiveRamp Onboarding akreditācijas datiem.

1. Atlasiet **Pārbaudīt**, lai pārbaudītu savienojumu ar LiveRamp.

1. Pēc sekmīgas verifikācijas sniedziet savu piekrišanu **Datu konfidencialitātei un atbilstībai**, atzīmējot izvēles rūtiņu **Piekrītu**.

1. Lai pabeigtu savienošanu, atlasiet **Saglabāt**.

## <a name="configure-an-export"></a>Eksporta konfigurēšana

Šo eksportu varat konfigurēt, ja jums ir piekļuve šā veida pieslēgumam. Papildinformāciju skatiet rakstā [Atļaujas, kas nepieciešamas eksporta konfigurēšanai](export-destinations.md#set-up-a-new-export).

1. Pārejiet uz **Dati** > **Eksportēšana**.

1. Lai izveidotu jaunu eksportu, atlasiet **Pievienot galamērķi**.

1. Laukā **Savienošana eksportam** atlasiet savienojumu no sadaļas LiveRamp. Ja šis sadaļas nosaukums nav redzams, šāda veida savienojumi jums nav pieejami.

1. Laukā **Izvēlēties galveno identifikatoru** atlasiet **E-pasts**, **Vārds un adrese** vai **Tālrunis**, kas tiks nosūtīts uz LiveRamp identitātes atrisināšanai.
   > [!div class="mx-imgBorder"]
   > ![LiveRamp savienotājs ar atribūtu kartējumu.](media/export-liveramp-segments.png "LiveRamp savienotājs ar atribūtu kartējumu")

1. Kartējiet atlasītajam atslēgas identifikatoram atbilstošos atribūtus no entītijas *Klients*.

1. Atlasiet **Pievienot atribūtu**, lai kartētu vairāk atribūtu, ko nosūtīt uz LiveRamp.

   > [!TIP]
   > Vairāku galveno identifikatora atribūtu nosūtīšana uz LiveRamp, visticamāk, iegūs lielāku atbilstību.

1. Atlasiet segmentus, kurus vēlaties eksportēt uz LiveRamp.

1. Atlasiet vienumu **Saglabāt**.

Eksporta saglabāšana automātiski nepalaiž eksportu.

Eksports tiek palaists ar katru [plānoto atsvaidzināšanu](system.md#schedule-tab). Varat arī [eksportēt datus pēc pieprasījuma](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Datu konfidencialitāte un atbilstība

Ja iespējojat Dynamics 365 Customer Insights datu pārsūtīšanu uz Liveramp, jūs atļaujat datu pārsūtīšanu ārpus atbilstības robežām Dynamics 365 Customer Insights, ieskaitot iespējami sensitīvus datus, piemēram, personas datus. Microsoft šos datus pārsūtīs pēc jūsu norādēm, bet jūs esat atbildīgs par to, lai nodrošinātu Liveramp atbilstību konfidencialitātes vai drošības saistībām, kas jums varētu rasties. Papildinformāciju skatiet rakstā [Microsoft Privātuma paziņojums](https://go.microsoft.com/fwlink/?linkid=396732).
Jūsu Dynamics 365 Customer Insights administrators var noņemt šo eksportēšanas galamērķi jebkurā laikā, lai pārtrauktu izmantot šo funkcionalitāti.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
