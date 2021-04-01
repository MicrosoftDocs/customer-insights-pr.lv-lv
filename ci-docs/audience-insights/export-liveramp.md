---
title: LiveRamp savienotājs
description: Uzziniet, kā eksportēt datus LiveRamp.
ms.date: 12/02/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 6ef4388b0e8ba8bc5866807765d8a872d41c9c14
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597566"
---
# <a name="liverampreg-connector-preview"></a>LiveRamp&reg; savienotājs (priekšskatījums)

Aktivizējiet datus risinājumā LiveRamp, lai izveidotu savienojumu ar vairāk nekā 500 platformām digitālajās, sociālajās un TV ekosistēmās. Strādājiet ar saviem datiem risinājumā LiveRamp, lai mērķētu, izlaistu un personalizētu reklāmas kampaņas.

## <a name="prerequisites"></a>Priekšnosacījumi

- Lai izmantotu šo savienotāju, ir nepieciešams LiveRamp abonements.
- Lai iegūtu abonementu, [sazinieties tieši ar LiveRamp](https://liveramp.com/contact/). [Uzzināt vairāk par LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).

## <a name="connect-to-liveramp"></a>Savienojums ar LiveRamp

1. Sadaļā Auditorijas ieskati ejiet uz **Administrators** > **Eksportēšanas galamērķi**.

1. **LiveRamp** elementā atlasiet **Iestatīt**.

1. Laukā **Parādāmais nosaukums** piešķiriet galamērķim atpazīstamu nosaukumu.

1. Norādiet **Lietotājvārds** un **Parole** savam LiveRamp Drošajam FTP (SFTP) kontam.
Šie akreditācijas dati var atšķirties no jūsu LiveRamp Onboarding akreditācijas datiem.

1. Atlasiet **Pārbaudīt**, lai pārbaudītu savienojumu ar LiveRamp.

1. Pēc sekmīgas verifikācijas sniedziet savu piekrišanu **Datu konfidencialitātei un atbilstībai**, atzīmējot izvēles rūtiņu **Piekrītu**.

1. Atlasiet **Tālāk**, lai iestatītu LiveRamp savienotāju.

## <a name="configure-the-connector"></a>Savienotāja konfigurēšana

1. Laukā **Izvēlēties galveno identifikatoru** atlasiet **E-pasts**, **Vārds un adrese** vai **Tālrunis**, kas tiks nosūtīts uz LiveRamp identitātes atrisināšanai.

1. Kartējiet atbilstošos atribūtus no savas vienotās klienta entītijas atlasītajam galvenajam identifikatoram.

1. Atlasiet **Pievienot atribūtu**, lai kartētu papildu atribūtus nosūtīšanai uz LiveRamp.

   > [!TIP]
   > Vairāku galveno identifikatora atribūtu nosūtīšana uz LiveRamp, visticamāk, iegūs lielāku atbilstību.

1. Atlasiet segmentus, kurus vēlaties eksportēt uz LiveRamp.

1. Atlasiet vienumu **Saglabāt**.

> [!div class="mx-imgBorder"]
> ![LiveRamp savienotājs ar atribūtu kartējumu](media/export-liveramp-segments.png "LiveRamp savienotājs ar atribūtu kartējumu")

## <a name="export-the-data"></a>Datu eksportēšana

Eksportēšana drīzumā tiks sākta, ja būs pabeigti visi eksportēšanas priekšnosacījumi. Eksportēšana arī tiks palaista ar katru [plānoto atsvaidzināšanu](system.md#schedule-tab).
Kad eksportēšana ir sekmīgi pabeigta, varat pieteikties programmā LiveRamp Onboarding, lai aktivizētu un izplatītu savus datus.

## <a name="data-privacy-and-compliance"></a>Datu konfidencialitāte un atbilstība

Ja iespējojat Dynamics 365 Customer Insights datu pārsūtīšanu uz Liveramp, jūs atļaujat datu pārsūtīšanu ārpus atbilstības robežām Dynamics 365 Customer Insights, ieskaitot iespējami sensitīvus datus, piemēram, personas datus. Microsoft šos datus pārsūtīs pēc jūsu norādēm, bet jūs esat atbildīgs par to, lai nodrošinātu Liveramp atbilstību konfidencialitātes vai drošības saistībām, kas jums varētu rasties. Papildinformāciju skatiet rakstā [Microsoft Privātuma paziņojums](https://go.microsoft.com/fwlink/?linkid=396732).
Jūsu Dynamics 365 Customer Insights administrators var noņemt šo eksportēšanas galamērķi jebkurā laikā, lai pārtrauktu izmantot šo funkcionalitāti.

[!INCLUDE[footer-include](../includes/footer-banner.md)]