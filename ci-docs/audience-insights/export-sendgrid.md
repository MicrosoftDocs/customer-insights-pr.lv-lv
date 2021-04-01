---
title: Customer Insights datu eksportēšana uz SendGrid
description: Uzziniet, kā konfigurēt savienojumu ar SendGrid.
ms.date: 12/08/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 1a1f679fa42d47d524ebfdd6e931ae2822565f77
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597290"
---
# <a name="connector-for-sendgrid-preview"></a>Savienotājs ar SendGrid (priekšskatījums)

Eksportējiet vienoto klientu profilu segmentus uz SendGrid kontaktpersonu sarakstiem un izmantojiet tos kampaņām un e-pasta mārketingam lietojumprogrammā SendGrid. 

## <a name="prerequisites"></a>Priekšnosacījumi

-   Jums ir [SendGrid konts](https://sendgrid.com/) un atbilstošie administratora akreditācijas dati.
-   SendGrid ir esoši kontaktpersonu saraksti un attiecīgie ID. Papildinformāciju skatiet rakstā [SendGrid - Pārvaldīt kontaktus](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).
-   Jums ir [konfigurēti segmenti](segments.md) auditorijas ieskatos.
-   Eksportētajos segmentos vienotajiem klientu profiliem ir lauks, kas norāda e-pasta adresi.

## <a name="connect-to-sendgrid"></a>Izveidot savienojumu ar SendGrid

1. Dodieties uz sadaļu **Administrators** > **Eksportēšanas galamērķi**.

1. Sadaļā **SendGrid** atlasiet vienumu **Iestatīt**.

1. Piešķiriet eksportēšanas galamērķim atpazīstamu nosaukumu laukā **Parādāmais nosaukums**.

   :::image type="content" source="media/export-sendgrid.PNG" alt-text="SendGrid eksportēšanas konfigurācijas rūts.":::

1. Ievadiet savu **SendGrid API atslēgu** [SendGrid API atslēga](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).

1. Ievadiet savu **[SendGrid saraksta ID](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.

1. Atlasiet **Piekrītu**, lai apstiprinātu **Datu konfidencialitāti un atbilstību**.

1. Atlasiet **Izveidot savienojumu**, lai inicializētu savienojumu ar SendGrid.

1. Atlasiet opciju **Pievienot sevi kā eksporta lietotāju** un sniedziet savus Customer Insights akreditācijas datus.

1. Lai konfigurētu eksportēšanu, atlasiet **Tālāk**.

## <a name="configure-the-connector"></a>Savienotāja konfigurēšana

1. Sadaļas **Datu atbilstības** laukā **E-pasts** atlasiet lauku, kas iekļauts vienotajā klientu profilā, kas pārstāv klienta e-pasta adresi. Veiciet tās pašas darbības ar citiem neobligātajiem laukiem, piemēram, **Vārds**, **Uzvārds**, **Valsts/Reģions**, **Štats**, **Pilsēta**, and **Pasta indekss**.

1. Atlasiet segmentus, kurus vēlaties eksportēt. Mēs **stingri iesakām eksportēt kopumā ne vairāk kā 100 000 klientu profilu** programmā SendGrid. 

1. Atlasiet vienumu **Saglabāt**.

## <a name="export-the-data"></a>Datu eksportēšana

Datus var [eksportēt pēc pieprasījuma](export-destinations.md). Eksportēšana arī tiks palaista ar katru [plānoto atsvaidzināšanu](system.md#schedule-tab).

## <a name="known-limitations"></a>Zināmie ierobežojumi

- Kopumā līdz 100 000 profiliem uz SendGrid.
- Eksportēšana uz SendGrid ir ierobežota līdz segmentiem.
- 100 000 profilu eksportēšana uz SendGrid var aizņemt dažas stundas. 
- To profilu skaits, ko var eksportēt uz SendGrid, ir atkarīgs, un tas ir ierobežots jūsu līgumā ar SendGrid.

## <a name="data-privacy-and-compliance"></a>Datu konfidencialitāte un atbilstība

Ja iespējojat Dynamics 365 Customer Insights datu pārsūtīšanu uz SendGrid, jūs atļaujat datu pārsūtīšanu ārpus atbilstības robežām Dynamics 365 Customer Insights, ieskaitot iespējami sensitīvus datus, piemēram, personas datus. Microsoft šos datus pārsūtīs pēc jūsu norādēm, bet jūs esat atbildīgs par to, lai nodrošinātu SendGrid atbilstību konfidencialitātes vai drošības saistībām, kas jums varētu rasties. Papildinformāciju skatiet rakstā [Microsoft Privātuma paziņojums](https://go.microsoft.com/fwlink/?linkid=396732).
Jūsu Dynamics 365 Customer Insights administrators var noņemt šo eksportēšanas galamērķi jebkurā laikā, lai pārtrauktu izmantot šo funkcionalitāti.


[!INCLUDE[footer-include](../includes/footer-banner.md)]