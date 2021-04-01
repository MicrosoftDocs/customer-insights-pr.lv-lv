---
title: Customer Insights datu eksportēšana uz Autopilot
description: Uzziniet, kā konfigurēt savienojumu ar Autopilot.
ms.date: 12/08/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6d039c4afd84eaad942d214d4e6fb8ef7b1ec72a
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596140"
---
# <a name="connector-for-autopilot-preview"></a>Savienotājs ar Autopilot (priekšskatījums)

Eksportējiet vienoto klientu profilu segmentus uz Autopilot un izmantojiet tos e-pasta mārketingam lietojumprogrammā Autopilot. 

## <a name="prerequisites"></a>Priekšnosacījumi

-   Jums ir [Autopilot konts](https://www.autopilothq.com/) un atbilstošie administratora akreditācijas dati.
-   Jums ir [konfigurēti segmenti](segments.md) auditorijas ieskatos.
-   Eksportētajos segmentos vienotajiem klientu profiliem ir lauks, kas norāda e-pasta adresi.

## <a name="connect-to-autopilot"></a>Izveidot savienojumu ar Autopilot

1. Dodieties uz sadaļu **Administrators** > **Eksportēšanas galamērķi**.

1. Sadaļā **Autopilot** atlasiet vienumu **Iestatīt**.

1. Piešķiriet eksportēšanas galamērķim atpazīstamu nosaukumu laukā **Parādāmais nosaukums**.

   :::image type="content" source="media/export-autopilot.PNG" alt-text="Konfigurēšanas rūts Autopilot savienojumam.":::

1. Ievadiet savu **Autopilot API atslēgu** [Autopilot API atslēga](https://autopilot.docs.apiary.io/#).

1. Atlasiet **Piekrītu**, lai apstiprinātu **Datu konfidencialitāti un atbilstību**.

1. Atlasiet **Izveidot savienojumu**, lai inicializētu savienojumu ar Autopilot.

1. Atlasiet opciju **Pievienot sevi kā eksporta lietotāju** un sniedziet savus Customer Insights akreditācijas datus.

1. Lai konfigurētu eksportēšanu, atlasiet **Tālāk**.

## <a name="configure-the-connector"></a>Savienotāja konfigurēšana

1. Sadaļas **Datu atbilstības** laukā **E-pasts** atlasiet lauku, kas iekļauts vienotajā klientu profilā, kas pārstāv klienta e-pasta adresi. Veiciet tās pašas darbības ar citiem neobligātajiem laukiem, piemēram, **Vārds**, **Uzvārds**.

1. Atlasiet segmentus, kurus vēlaties eksportēt. Mēs **stingri iesakām eksportēt kopumā ne vairāk kā 100 000 klientu profilu** programmā Autopilot. 

1. Atlasiet vienumu **Saglabāt**.

## <a name="export-the-data"></a>Datu eksportēšana

Datus var [eksportēt pēc pieprasījuma](export-destinations.md). Eksportēšana arī tiks palaista ar katru [plānoto atsvaidzināšanu](system.md#schedule-tab).

## <a name="known-limitations"></a>Zināmie ierobežojumi

- Kopsummā var eksportēt līdz 100 000 profilu uz Autopilot.
- Eksportēšana uz Autopilot ir ierobežota līdz segmentiem.
- 100 000 profilu eksportēšana uz Autopilot var aizņemt dažas stundas. 
- To profilu skaits, ko var eksportēt uz Autopilot, ir atkarīgs, un tas ir ierobežots jūsu līgumā ar Autopilot.

## <a name="data-privacy-and-compliance"></a>Datu konfidencialitāte un atbilstība

Ja iespējojat Dynamics 365 Customer Insights datu pārsūtīšanu uz Autopilot, jūs atļaujat datu pārsūtīšanu ārpus atbilstības robežām Dynamics 365 Customer Insights, ieskaitot iespējami sensitīvus datus, piemēram, personas datus. Microsoft šos datus pārsūtīs pēc jūsu norādēm, bet jūs esat atbildīgs par to, lai nodrošinātu Autopilot atbilstību konfidencialitātes vai drošības saistībām, kas jums varētu rasties. Papildinformāciju skatiet rakstā [Microsoft Privātuma paziņojums](https://go.microsoft.com/fwlink/?linkid=396732).
Jūsu Dynamics 365 Customer Insights administrators var noņemt šo eksportēšanas galamērķi jebkurā laikā, lai pārtrauktu izmantot šo funkcionalitāti.


[!INCLUDE[footer-include](../includes/footer-banner.md)]