---
title: Customer Insights datu eksportēšana uz Mailchimp
description: Uzziniet, kā konfigurēt savienojumu ar Mailchimp.
ms.date: 10/26/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: edff494f6edf26a8b641cb1d788a715389ddb346
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406326"
---
# <a name="connector-for-mailchimp-preview"></a>Savienotājs ar Mailchimp (priekšskatījums)

Eksportējiet vienotu klientu profilu segmentus uz Mailchimp, lai izveidotu informatīvas vēstules un e-pasta kampaņas.

## <a name="prerequisites"></a>Priekšnosacījumi

-   Jums ir [Mailchimp konts](https://mailchimp.com/) un atbilstošie administratora akreditācijas dati.
-   Mailchimp ir esošas auditorijas un attiecīgie ID. Papildinformāciju skatiet rakstā [Mailchimp auditorijas](https://mailchimp.com/help/create-audience/).
-   Jums ir [konfigurēti segmenti](segments.md)
-   Eksportētajos segmentos vienotajiem klientu profiliem ir lauks, kas norāda e-pasta adresi.

## <a name="connect-to-mailchimp"></a>Izveidot savienojumu ar Mailchimp

1. Dodieties uz sadaļu **Administrators** > **Eksportēšanas galamērķi**.

1. Sadaļā **Mailchimp** atlasiet vienumu **Iestatīt**.

1. Piešķiriet eksportēšanas galamērķim atpazīstamu nosaukumu laukā **Parādāmais nosaukums**.

1. Atlasiet **Piekrītu**, lai apstiprinātu **Datu privātumu un atbilstību**.

1. Ievadiet savas **[Mailchimp auditorijas ID](https://mailchimp.com/help/find-audience-id/)** un atlasiet opciju **Izveidot savienojumu**, lai inicializētu savienojumu ar Mailchimp.

1. Atlasiet **Autentificēties ar Mailchimp** un sniedziet savus Mailchimp akreditācijas datus.

1. Atlasiet opciju **Pievienot sevi kā eksporta lietotāju** un sniedziet savus Customer Insights akreditācijas datus.

   :::image type="content" source="media/export-connect-mailchimp.png" alt-text="Eksportēt ekrānuzņēmumu Mailchimp savienojumā":::

1. Lai konfigurētu eksportēšanu, atlasiet **Tālāk**.

## <a name="configure-the-connector"></a>Savienotāja konfigurēšana

1. Sadaļas **Datu atbilstības** laukā **E-pasts** atlasiet lauku, kas iekļauts vienotajā klientu profilā, kas pārstāv klienta e-pasta adresi. 

1. Ja vēlaties, varat eksportēt **Vārds** un **Uzvārds** kā papildu laukus, lai izveidotu vairāk personalizētu e-pasta ziņojumu. Atlasiet **Pievienot atribūtu**, lai kartētu šos laukus.

1. Atlasiet segmentus, kurus vēlaties eksportēt. Kopsummā var eksportēt līdz 1 000 000 klientu profilu uz Mailchimp.

   :::image type="content" source="media/export-segments-mailchimp.png" alt-text="Atlasīt laukus un segmentus eksportēšanai uz Mailchimp":::

1. Atlasiet vienumu **Saglabāt**.

## <a name="export-the-data"></a>Datu eksportēšana

Datus var [eksportēt pēc pieprasījuma](export-destinations.md). Eksportēšana arī tiks palaista ar katru [plānoto atsvaidzināšanu](system.md#schedule-tab). Mailchimp tagad varat atrast jūsu segmentus sadaļā [Mailchimp auditorija](https://mailchimp.com/help/create-audience/).

## <a name="known-limitations"></a>Zināmie ierobežojumi

- Līdz 1 000 000 profilu, eksportējot uz Mailchimp.
- Eksportēšana uz Mailchimp ir ierobežota līdz segmentiem.
- Segmentu eksportēšanai kopā ar 1 000 000 profilu var būt nepieciešamas 3 stundas, jo pastāv ierobežojumi no pakalpojuma sniedzēja puses. 
- To profilu skaits, ko var eksportēt uz Mailchimp, ir atkarīgs, un tas ir ierobežots jūsu līgumā ar Mailchimp.

## <a name="data-privacy-and-compliance"></a>Datu konfidencialitāte un atbilstība

Ja iespējojat Dynamics 365 Customer Insights datu pārsūtīšanu uz Mailchimp, jūs atļaujat datu pārsūtīšanu ārpus atbilstības robežām Dynamics 365 Customer Insights, ieskaitot iespējami sensitīvus datus, piemēram, personas datus. Microsoft šos datus pārsūtīs pēc jūsu norādēm, bet jūs esat atbildīgs par to, lai nodrošinātu Mailchimp atbilstību konfidencialitātes vai drošības saistībām, kas jums varētu rasties. Papildinformāciju skatiet rakstā [Microsoft Privātuma paziņojums](https://go.microsoft.com/fwlink/?linkid=396732).
Jūsu Dynamics 365 Customer Insights administrators var noņemt šo eksportēšanas galamērķi jebkurā laikā, lai pārtrauktu izmantot šo funkcionalitāti.
