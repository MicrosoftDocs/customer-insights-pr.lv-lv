---
title: Export Customer Insights datus sftp resursdatoriem (Video)
description: Uzziniet, kā konfigurēt savienojumu un eksportēt uz SFTP atrašanās vietu.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 568e5826175417175bd09435d697031f0ab64223
ms.sourcegitcommit: e141a6a34a985cca68f03082a700ed27f2f3c0c1
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 12/17/2021
ms.locfileid: "7927612"
---
# <a name="export-segments-and-other-data-to-sftp-preview"></a>Eksportējiet segmentus un citus datus uz SFTP (priekšskatījums)

Izmantojiet klientu datus trešo pušu lietojumprogrammās, eksportējot tos uz drošu failu pārsūtīšanas protokola (SFTP) atrašanās vietu.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO94X]

## <a name="prerequisites-for-connection"></a>Savienojuma priekšnosacījumi

- SFTP resursdatora pieejamība un atbilstošie akreditācijas dati.

## <a name="known-limitations"></a>Zināmie ierobežojumi

- SFTP galamērķi aiz ugunsmūriem pašlaik netiek atbalstīti. 
- Eksportēšanas izpildlaiks ir atkarīgs no sistēmas veiktspējas. Kā minimālu servera konfigurēšanu ieteicams izmantot divus procesora kodolus un 1 Gb atmiņu. 
- Līdz pat 100 miljoniem klientu profilu entītiju eksportēšana var aizņemt 90 minūtes, ja tiek izmantota ieteicama minimālā divu procesoru kodolu konfigurācija un 1 Gb atmiņa. 

## <a name="set-up-connection-to-sftp"></a>Savienojuma ar SFTP iestatīšana

1. Dodieties uz **Administrators** > **Savienojumi**.

1. Atlasiet vienumu **Pievienot savienojumu** un atlasiet **SFTP**, lai konfigurētu savienojumu.

1. Laukā **Parādāmais nosaukums** piešķiriet savienojumam atpazīstamu nosaukumu. Parādāmais nosaukums un nosaukuma veids raksturo šo savienojumu. Ir ieteicams izvēlēties nosaukumu, kas paskaidro savienojuma nolūku.

1. Izvēlieties, kurš var izmantot šo savienojumu. Ja nesāksit nekādas darbības, noklusējums būs Administratori. Papildinformāciju skatiet rakstā [Atļaut līdzstrādniekiem izmantot savienojumu eksportam](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Norādiet **Lietotājvārdu**, **Paroli**, **Resursdatora nosaukumu** un **Eksporta mapi** savam SFTP kontam.

1. Atlasiet **Pārbaudīt**, lai testētu savienojumu.

1. Izvēlieties, vai vēlaties eksportēt datus kā **Gzipped** vai **Unzipped**, un eksportēto failu **lauku norobežotāju**.

1. Atlasiet **Piekrītu**, lai apstiprinātu **Datu konfidencialitāti un atbilstību**.

1. Lai pabeigtu savienošanu, atlasiet **Saglabāt**.

## <a name="configure-an-export"></a>Eksporta konfigurēšana

Šo eksportu varat konfigurēt, ja jums ir piekļuve šā veida pieslēgumam. Papildinformāciju skatiet rakstā [Atļaujas, kas nepieciešamas eksporta konfigurēšanai](export-destinations.md#set-up-a-new-export).

1. Pārejiet uz **Dati** > **Eksportēšana**.

1. Lai izveidotu jaunu eksportu, atlasiet **Pievienot galamērķi**.

1. Laukā **Savienošana eksportam** atlasiet savienojumu no sadaļas SFTP. Ja šis sadaļas nosaukums nav redzams, šāda veida savienojumi jums nav pieejami.

1. Atlasiet entītijas, piemēram, segmentus, kurus vēlaties eksportēt.

   > [!NOTE]
   > Eksportēšanas laikā katra atlasītā entitīja tiks iedalīta maksimums piecos izvades failos. 

1. Atlasiet vienumu **Saglabāt**.

Eksporta saglabāšana automātiski nepalaiž eksportu.

Eksports tiek palaists ar katru [plānoto atsvaidzināšanu](system.md#schedule-tab). Varat arī [eksportēt datus pēc pieprasījuma](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Datu konfidencialitāte un atbilstība

Ja iespējojat Dynamics 365 Customer Insights datu pārsūtīšanu caur SFTP, jūs atļaujat datu pārsūtīšanu ārpus atbilstības robežām Dynamics 365 Customer Insights, ieskaitot iespējami sensitīvus datus, piemēram, personas datus. Microsoft šos datus pārsūtīs pēc jūsu norādēm, bet jūs esat atbildīgs par to, lai nodrošinātu eksporta galamērķa atbilstību konfidencialitātes vai drošības saistībām, kas jums varētu rasties. Papildinformāciju skatiet rakstā [Microsoft Privātuma paziņojums](https://go.microsoft.com/fwlink/?linkid=396732).
Jūsu Dynamics 365 Customer Insights administrators var noņemt šo eksportēšanas galamērķi jebkurā laikā, lai pārtrauktu izmantot šo funkcionalitāti.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
