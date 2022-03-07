---
title: Customer Insights datu eksportēšana uz Salesforce Marketing Cloud
description: Uzziniet, kā konfigurēt savienojumu un eksportēt uz Salesforce Marketing Cloud.
ms.date: 07/23/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 17a608a64433cdc395e0b503a42b6290db5c39ec
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 02/16/2022
ms.locfileid: "8230213"
---
# <a name="export-segments-and-other-data-to-salesforce-marketing-cloud-preview"></a>Segmentu un citu datu eksportēšana uz Salesforce Marketing Cloud (priekšskatījums)

Izmantojiet klientu datus programmā Salesforce Marketing Cloud, eksportējot tos, izmantojot drošu failu pārsūtīšanas protokola (SFTP) atrašanās vietu.

## <a name="prerequisites-for-connection"></a>Savienojuma priekšnosacījumi

- SFTP viesošanas pakalpojuma pieejamība un attiecīgie administratora akreditācijas dati. [Kā iestatīt SFTP atrašanās vietas programmai Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) 

## <a name="set-up-the-connection-to-salesforce-marketing-cloud"></a>Savienojuma iestatīšana ar Salesforce Marketing Cloud

1. Dodieties uz **Administrators** > **Savienojumi**.

1. Atlasiet vienumu **Pievienot savienojumu** un izvēlieties **Salesforce Marketing Cloud**, lai konfigurētu savienojumu.

1. Laukā **Parādāmais nosaukums** piešķiriet savienojumam atpazīstamu nosaukumu. Parādāmais nosaukums un nosaukuma veids raksturo šo savienojumu. Ir ieteicams izvēlēties nosaukumu, kas paskaidro savienojuma nolūku.

1. Izvēlieties, kurš var izmantot šo savienojumu. Ja nesāksit nekādas darbības, noklusējums būs Administratori. Papildinformāciju skatiet rakstā [Atļaut līdzstrādniekiem izmantot savienojumu eksportam](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Norādiet **Lietotājvārdu**, **Paroli**, **Resursdatora nosaukumu** un **Eksporta mapi** savam SFTP kontam.

1. Atlasiet **Pārbaudīt**, lai testētu savienojumu.

1. Atlasiet **Piekrītu**, lai apstiprinātu **Datu konfidencialitāti un atbilstību**.

1. Lai pabeigtu savienošanu, atlasiet **Saglabāt**.

## <a name="configure-an-export"></a>Eksporta konfigurēšana

Šo eksportu varat konfigurēt, ja jums ir piekļuve šā veida pieslēgumam. Papildinformāciju skatiet rakstā [Atļaujas, kas nepieciešamas eksporta konfigurēšanai](export-destinations.md#set-up-a-new-export).

1. Pārejiet uz **Dati** > **Eksportēšana**.

1. Lai izveidotu jaunu eksportu, atlasiet **Pievienot galamērķi**.

1. Laukā **Savienošana eksportam** atlasiet savienojumu no sadaļas SFTP. Ja šis sadaļas nosaukums nav redzams, šāda veida savienojumi jums nav pieejami.

1. Izvēlieties, vai vēlaties eksportēt datus kā **Gzipped** vai **Unzipped**, un eksportēto failu **lauku norobežotāju**.

1. Atlasiet entītijas, piemēram, segmentus, kurus vēlaties eksportēt.

   > [!NOTE]
   > Eksportēšanas laikā katra atlasītā entitīja tiks iedalīta maksimums piecos izvades failos. 

1. Atlasiet vienumu **Saglabāt**.

Eksporta saglabāšana automātiski nepalaiž eksportu.

Eksports tiek palaists ar katru [plānoto atsvaidzināšanu](system.md#schedule-tab). Varat arī [eksportēt datus pēc pieprasījuma](export-destinations.md#run-exports-on-demand). 

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a>Customer Insights datu importēšana no SFTP atrašanās vietas uz Salesforce Marketing Cloud

1. Izveidojiet [datu paplašinājumus programmai Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5), lai importētu Customer Insights datu failu no SFTP atrašanās vietas.

2. [Importējiet datus no SFTP atrašanās vietas](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) uz Salesforce Marketing Cloud datu paplašinājumu. 

3. Iestatiet automatizāciju, lai datus importētu datu paplašinājumos. Papildinformācija par [failu nomešanas automatizāciju un ieplānotajām automatizācijujām](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).

   Definējiet [failu nomešanas automatizāciju](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) vai [ieplānotas automatizācijas](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5) 

Tālāk parādīts piemērs [automatizācijai ar SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).

## <a name="data-privacy-and-compliance"></a>Datu konfidencialitāte un atbilstība

Ja iespējojat Dynamics 365 Customer Insights datu pārsūtīšanu caur SFTP, jūs atļaujat datu pārsūtīšanu ārpus atbilstības robežām Dynamics 365 Customer Insights, ieskaitot iespējami sensitīvus datus, piemēram, personas datus. Microsoft šos datus pārsūtīs pēc jūsu norādēm, bet jūs esat atbildīgs par to, lai nodrošinātu eksporta galamērķa atbilstību konfidencialitātes vai drošības saistībām, kas jums varētu rasties. Papildinformāciju skatiet rakstā [Microsoft Privātuma paziņojums](https://go.microsoft.com/fwlink/?linkid=396732).
Jūsu Dynamics 365 Customer Insights administrators var noņemt šo eksportēšanas galamērķi jebkurā laikā, lai pārtrauktu izmantot šo funkcionalitāti.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
