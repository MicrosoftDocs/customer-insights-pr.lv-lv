---
title: Customer Insights datu eksportēšana uz AdRoll
description: Uzziniet, kā konfigurēt savienojumu ar AdRoll.
ms.date: 02/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6fedd549c2e7de362f36e3fb23d363200bb92a04
ms.sourcegitcommit: d24e52150fe5a4fab45128e12d6a03637771d9b9
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 03/19/2021
ms.locfileid: "5697083"
---
# <a name="connector-for-adroll-preview"></a>Savienotājs ar AdRoll (priekšskatījums)

Eksportējiet vienoto klientu profilu segmentus uz AdRoll un izmantojiet tos reklāmai. 

## <a name="prerequisites"></a>Priekšnosacījumi

-   Jums ir [AdRoll konts](https://www.adroll.com/) un atbilstošie administratora akreditācijas dati.
-   Jums ir [konfigurēti segmenti](segments.md) auditorijas ieskatos.
-   Eksportētajos segmentos vienotajiem klientu profiliem ir lauks, kas norāda e-pasta adresi.

## <a name="connect-to-adroll"></a>Izveidot savienojumu ar AdRoll

1. Dodieties uz sadaļu **Administrators** > **Eksportēšanas galamērķi**.

1. Sadaļā **AdRoll** atlasiet vienumu **Iestatīt**.

1. Piešķiriet eksportēšanas galamērķim atpazīstamu nosaukumu laukā **Parādāmais nosaukums**.

   :::image type="content" source="media/AdRoll_config.PNG" alt-text="Konfigurēšanas rūts AdRoll savienojumam.":::

1. Atlasiet **Piekrītu**, lai apstiprinātu **Datu konfidencialitāti un atbilstību**.

1. Atlasiet **Izveidot savienojumu**, lai inicializētu savienojumu ar AdRoll.

1. Atlasiet **Autentificēties ar AdRoll** un sniedziet savus administratora akreditācijas datus AdRoll. 

1. Atlasiet opciju **Pievienot sevi kā eksporta lietotāju** un sniedziet savus Customer Insights akreditācijas datus.

1. Ievadiet savu **AdRoll reklamētāja ID**[AdRoll reklamējams](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles).

1. Lai konfigurētu eksportēšanu, atlasiet **Tālāk**.

## <a name="configure-the-connector"></a>Savienotāja konfigurēšana

1. Sadaļas **Datu atbilstības** laukā **E-pasts** atlasiet lauku, kas iekļauts vienotajā klientu profilā, kas pārstāv klienta e-pasta adresi. Segmenti ir jāeksportē uz AdRoll.

1. Atlasiet segmentus, kurus vēlaties eksportēt. Atlasiet segmentu, kurā ir vismaz 100 dalībnieku. Nevar eksportēt mazākus segmentus. Turklāt eksportējamā segmenta maksimālais lielums ir 250 000 dalībnieku vienam eksportam. 

1. Atlasiet vienumu **Saglabāt**.

## <a name="export-the-data"></a>Datu eksportēšana

Datus var [eksportēt pēc pieprasījuma](export-destinations.md). Eksportēšana arī tiks palaista ar katru [plānoto atsvaidzināšanu](system.md#schedule-tab).

## <a name="known-limitations"></a>Zināmie ierobežojumi

- Vienam eksportam var eksportēt līdz 250 000 profilu uz AdRoll.
- Jūs nevarat eksportēt segmentus, kuros ir mazāk par 100 profiliem, uz AdRoll. 
- Eksportēšana uz AdRoll ir ierobežota līdz segmentiem.
- Līdz 250 000 profilu eksportēšanai uz AdRoll var paiet 10 minūtes. 
- To profilu skaits, ko var eksportēt uz AdRoll, ir atkarīgs, un tas ir ierobežots jūsu līgumā ar AdRoll.

## <a name="data-privacy-and-compliance"></a>Datu konfidencialitāte un atbilstība

Ja iespējojat Dynamics 365 Customer Insights datu pārsūtīšanu uz AdRoll, jūs atļaujat datu pārsūtīšanu ārpus atbilstības robežām Dynamics 365 Customer Insights, ieskaitot iespējami sensitīvus datus, piemēram, personas datus. Microsoft šos datus pārsūtīs pēc jūsu norādēm, bet jūs esat atbildīgs par to, lai nodrošinātu AdRoll atbilstību konfidencialitātes vai drošības saistībām, kas jums varētu rasties. Papildinformāciju skatiet rakstā [Microsoft Privātuma paziņojums](https://go.microsoft.com/fwlink/?linkid=396732).

Jūsu Dynamics 365 Customer Insights administrators var noņemt šo eksportēšanas galamērķi jebkurā laikā, lai pārtrauktu izmantot šo funkcionalitāti.
