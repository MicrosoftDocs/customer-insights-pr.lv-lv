---
title: Eksportējiet datus uz Salesforce Marketing Cloud (priekšskatījums)
description: Uzziniet, kā konfigurēt savienojumu un eksportēt uz Salesforce Marketing Cloud.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 58e76e51c18c25177f9b4551b70b25b41248b142
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 07/27/2022
ms.locfileid: "9197047"
---
# <a name="export-data-to-salesforce-marketing-cloud-preview"></a>Eksportējiet datus uz Salesforce Marketing Cloud (priekšskatījums)

Izmantojiet klientu datus programmā Salesforce Marketing Cloud, eksportējot tos, izmantojot drošu failu pārsūtīšanas protokola (SFTP) atrašanās vietu.

## <a name="prerequisites"></a>Priekšnoteikumi

- [SFTP resursdators Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) un atbilstošie administratora akreditācijas dati.

## <a name="set-up-connection-to-salesforce-marketing-cloud"></a>Savienojuma ar Salesforce Marketing Cloud iestatīšana

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Dodieties uz **Administrators** > **Savienojumi**.

1. Atlasiet **Pievienot savienojumu** un izvēlieties **Salesforce Marketing Cloud**.

1. Laukā **Parādāmais nosaukums** piešķiriet savienojumam atpazīstamu nosaukumu. Parādāmais nosaukums un nosaukuma veids raksturo šo savienojumu. Ir ieteicams izvēlēties nosaukumu, kas paskaidro savienojuma nolūku.

1. Izvēlieties, kurš var izmantot šo savienojumu. Pēc noklusējuma tie ir tikai administratori. Papildinformāciju skatiet rakstā [Atļaut līdzstrādniekiem izmantot savienojumu eksportam](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Norādiet **Lietotājvārdu**, **Paroli**, **Resursdatora nosaukumu** un **Eksporta mapi** savam SFTP kontam.

1. Atlasiet **Pārbaudīt**, lai testētu savienojumu.

1. Pārskatiet datu privātumu [un atbilstību](connections.md#data-privacy-and-compliance) un atlasiet **Es piekrītu**.

1. Lai pabeigtu savienošanu, atlasiet **Saglabāt**.

## <a name="configure-an-export"></a>Eksporta konfigurēšana

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Pārejiet uz **Dati** > **Eksportēšana**.

1. Atlasiet **Pievienot eksportēšanu**.

1. Laukā **Savienošana eksportam** atlasiet savienojumu no sadaļas SFTP. Ja nav pieejamu savienojumu, sazinieties ar administratoru.

1. Ievadiet eksportēšanas nosaukumu.

1. Izvēlieties, vai vēlaties eksportēt datus kā **Gzipped** vai **Unzipped**, un eksportēto failu **lauku norobežotāju**.

1. Atlasiet entītijas, piemēram, segmentus, kurus vēlaties eksportēt.

   > [!NOTE]
   > Eksportējot katru atlasīto entītiju, tā tiks sadalīta ne vairāk kā piecos izvades failos.

1. Atlasiet **Saglabāt**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a>Customer Insights datu importēšana no SFTP atrašanās vietas uz Salesforce Marketing Cloud

1. Izveidojiet [datu paplašinājumus programmai Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5), lai importētu Customer Insights datu failu no SFTP atrašanās vietas.

2. [Importējiet datus no SFTP atrašanās vietas](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) uz Salesforce Marketing Cloud datu paplašinājumu.

3. Iestatiet automatizāciju, lai datus importētu datu paplašinājumos. Papildinformācija par [failu nomešanas automatizāciju un ieplānotajām automatizācijujām](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).

   Definējiet [failu nomešanas automatizāciju](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) vai [ieplānotas automatizācijas](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5)

Tālāk parādīts piemērs [automatizācijai ar SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).

[!INCLUDE [footer-include](includes/footer-banner.md)]
