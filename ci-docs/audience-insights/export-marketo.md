---
title: Customer Insights datu eksportēšana uz Marketo
description: Uzziniet, kā konfigurēt savienojumu ar Marketo.
ms.date: 11/12/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 74d19a0448123904210c26f7b8760d00296c9cfd
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597980"
---
# <a name="connector-for-marketo-preview"></a>Savienotājs ar Marketo (priekšskatījums)

Izmantojiet pakalpojumā Customer Insights izveidotos segmentus kampaņu veidošanai, e-pasta mārketinga sniegšanai un specifisku klientu grupu atlases iespējas pakalpojumā Marketo.

## <a name="prerequisites"></a>Priekšnosacījumi

-   Jums ir [Marketo konts](https://login.marketo.com/) un atbilstošie administratora akreditācijas dati.
-   Marketo ir esošas auditorijas un attiecīgie ID. Lai iegūtu papildinformāciju, skatiet [Marketo sarakstus](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).
-   Jums ir [konfigurēti segmenti](segments.md).
-   Eksportētajos segmentos vienotajiem klientu profiliem ir lauks, kas norāda e-pasta adresi.

## <a name="connect-to-marketo"></a>Izveidot savienojumu ar Marketo

1. Dodieties uz sadaļu **Administrators** > **Eksportēšanas galamērķi**.

1. Sadaļā **Marketo** atlasiet vienumu **Iestatīt**.

1. Piešķiriet eksportēšanas galamērķim atpazīstamu nosaukumu laukā **Parādāmais nosaukums**.

1. Ievadiet savu **[Marketo klienta ID, klienta slepeno vārdu un REST galapunktu resursdatorā](https://developers.marketo.com/rest-api/authentication/)**.

1. Ievadiet savu **[Marketo saraksta ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)** 

1. Atlasiet **Es piekrītu**, lai apstiprinātu **Datu konfidencialitāti un atbilstību**, un atlasiet opciju **Izveidot savienojumu**, lai inicializētu savienojumu ar Marketo.

1. Atlasiet opciju **Pievienot sevi kā eksporta lietotāju** un sniedziet savus Customer Insights akreditācijas datus.

   :::image type="content" source="media/export-connect-marketo.png" alt-text="Eksportēt ekrānuzņēmumu Marketo savienojumā":::

1. Lai konfigurētu eksportēšanu, atlasiet **Tālāk**.

## <a name="configure-the-connector"></a>Savienotāja konfigurēšana

1. Sadaļas **Datu atbilstības** laukā **E-pasts** atlasiet lauku, kas iekļauts vienotajā klientu profilā, kas pārstāv klienta e-pasta adresi. 

1. Ja vēlaties, varat eksportēt **Vārds**, **Uzvārds**, **Pilsēta**, **Štats** un **Valsts/Reģions**  kā papildu laukus, lai izveidotu vairāk personalizētu e-pasta ziņojumu. Atlasiet **Pievienot atribūtu**, lai kartētu šos laukus.

1. Atlasiet segmentus, kurus vēlaties eksportēt. Kopsummā var eksportēt līdz 1 000 000 klientu profilu uz Marketo.

   :::image type="content" source="media/export-segment-marketo.png" alt-text="Atlasīt laukus un segmentus eksportēšanai uz Marketo":::

1. Atlasiet vienumu **Saglabāt**.

## <a name="export-the-data"></a>Datu eksportēšana

Datus var [eksportēt pēc pieprasījuma](export-destinations.md). Eksportēšana arī tiks palaista ar katru [plānoto atsvaidzināšanu](system.md#schedule-tab). Marketo tagad varat atrast jūsu segmentus sadaļā [Marketo saraksti](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).

## <a name="known-limitations"></a>Zināmie ierobežojumi

- Līdz 1 000 000 profilu, eksportējot uz Marketo.
- Eksportēšana uz Marketo ir ierobežota līdz segmentiem.
- Eksportējot segmentus kopā ar 1 000 000 profiliem, var būt nepieciešamas 3 stundas. 
- To profilu skaits, ko var eksportēt uz Marketo, ir atkarīgs, un tas ir ierobežots jūsu līgumā ar Marketo.

## <a name="data-privacy-and-compliance"></a>Datu konfidencialitāte un atbilstība

Ja iespējojat Dynamics 365 Customer Insights datu pārsūtīšanu uz Marketo, jūs atļaujat datu pārsūtīšanu ārpus atbilstības robežām Dynamics 365 Customer Insights, ieskaitot iespējami sensitīvus datus, piemēram, personas datus. Microsoft šos datus pārsūtīs pēc jūsu norādēm, bet jūs esat atbildīgs par to, lai nodrošinātu Marketo atbilstību konfidencialitātes vai drošības saistībām, kas jums varētu rasties. Papildinformāciju skatiet rakstā [Microsoft Privātuma paziņojums](https://go.microsoft.com/fwlink/?linkid=396732).
Jūsu Dynamics 365 Customer Insights administrators var noņemt šo eksportēšanas galamērķi jebkurā laikā, lai pārtrauktu izmantot šo funkcionalitāti.


[!INCLUDE[footer-include](../includes/footer-banner.md)]