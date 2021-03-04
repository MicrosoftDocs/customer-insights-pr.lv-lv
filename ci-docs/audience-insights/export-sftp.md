---
title: Customer Insights datu eksportēšana uz SFTP resursdatoriem
description: Uzziniet, kā konfigurēt savienojumu ar SFTP resursdatoru.
ms.date: 01/27/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ddba55b3ca159c0095371e46385dcf1d3ed4a63d
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268007"
---
# <a name="connector-for-sftp-preview"></a>SFTP savienotājs (priekšskatījums)

Izmantojiet klienta datus trešo pušu lietojumprogrammās, eksportējot tos caur mūsu Drošo failu pārsūtīšanas protokola (SFTP) resursdatoru.

## <a name="prerequisites"></a>Priekšnosacījumi

- SFTP resursdatora pieejamība un atbilstošie akreditācijas dati.

## <a name="connect-to-sftp"></a>Savienojuma izveide ar SFTP

1. Dodieties uz sadaļu **Administrators** > **Eksportēšanas galamērķi**.

1. Sadaļā **SFTP** atlasiet **Iestatīt**.

1. Laukā **Parādāmais nosaukums** piešķiriet galamērķim atpazīstamu nosaukumu.

1. Norādiet **Lietotājvārdu**, **Paroli**, **Resursdatora nosaukumu** un **Eksporta mapi** savam SFTP kontam.

1. Atlasiet **Pārbaudīt**, lai testētu savienojumu.

1. Pēc sekmīgas pārbaudes izvēlieties, vai vēlaties eksportēt datus **Saspiestus** vai **Atspiestus**, un atlasiet eksportēto failu **Lauku norobežotāju**.

1. Atlasiet **Piekrītu**, lai apstiprinātu **Datu konfidencialitāti un atbilstību**.

1. Lai sāktu eksporta konfigurēšanu, atlasiet **Tālāk**.

## <a name="configure-the-export"></a>Eksporta konfigurēšana

1. Atlasiet entītijas, piemēram, segmentus, kurus vēlaties eksportēt.

   > [!NOTE]
   > Katra atlasītajā entītija pēc eksportēšanas būs līdz pieciem izvades failiem. 

1. Atlasiet vienumu **Saglabāt**.

## <a name="export-the-data"></a>Datu eksportēšana

Datus var [eksportēt pēc pieprasījuma](export-destinations.md). Eksportēšana arī tiks palaista ar katru [plānoto atsvaidzināšanu](system.md#schedule-tab).

## <a name="known-limitations"></a>Zināmie ierobežojumi

- Eksportēšanas izpildlaiks ir atkarīgs no sistēmas veiktspējas. Kā minimālu servera konfigurēšanu ieteicams izmantot divus procesora kodolus un 1 Gb atmiņu. 
- Līdz pat 100 miljoniem klientu profilu entītiju eksportēšana var aizņemt 90 minūtes, ja tiek izmantota ieteicama minimālā divu procesoru kodolu konfigurācija un 1 Gb atmiņa. 

## <a name="data-privacy-and-compliance"></a>Datu konfidencialitāte un atbilstība

Ja iespējojat Dynamics 365 Customer Insights datu pārsūtīšanu caur SFTP, jūs atļaujat datu pārsūtīšanu ārpus atbilstības robežām Dynamics 365 Customer Insights, ieskaitot iespējami sensitīvus datus, piemēram, personas datus. Microsoft šos datus pārsūtīs pēc jūsu norādēm, bet jūs esat atbildīgs par to, lai nodrošinātu eksporta galamērķa atbilstību konfidencialitātes vai drošības saistībām, kas jums varētu rasties. Papildinformāciju skatiet rakstā [Microsoft Privātuma paziņojums](https://go.microsoft.com/fwlink/?linkid=396732).
Jūsu Dynamics 365 Customer Insights administrators var noņemt šo eksportēšanas galamērķi jebkurā laikā, lai pārtrauktu izmantot šo funkcionalitāti.


[!INCLUDE[footer-include](../includes/footer-banner.md)]