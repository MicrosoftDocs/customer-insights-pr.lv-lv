---
title: Galamērķu eksportēšana
description: Eksportēt datus un pārvaldīt eksportēšanas galamērķus.
ms.date: 07/21/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 5557442983f8c48cd46387009e0060beb6e764bb
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596094"
---
# <a name="export-destinations-preview-overview"></a>Galamērķu pārskata eksportēšana (priekšskatījums)

Lapā **Eksportēšanas galamērķi** tiek parādītas visas jūsu iestatītās datu eksportēšanas vietas. Eksportēšanai var pievienot arī jaunus adresātus. Turklāt tajā ir redzama pašlaik pieejamo opciju eksportēšana. Saņemiet īsu pārskatu, aprakstu un uzziniet, ko varat darīt ar katru paplašināmības opciju. Eksportējiet vienotos profilus, mērvienības un segmentus uz atbalstītajām programmām, kas ir saistošas jūsu uzņēmumam.

Dodieties uz **Administrators** > **Eksportēšanas galamērķi**, lai atrastu šādas paplašināšanas opcijas:

- [Adobe Campaign Standard](export-adobe-campaign-standard.md)
- [Adobe Experience Platform](export-adobe-experience-platform.md)
- [AdRoll](export-adroll.md)
- [Autopilot](export-autopilot.md)
- [Azure Blob krātuve](export-azure-blob-storage.md)
- [Azure Data Lake Storage Gen2](export-azure-data-lake-storage-gen2.md)
- [Bots pakalpojumam Microsoft Teams](export-teams-bot.md)
- [Customer Insights API](apis.md)
- [DotDigital](export-dotdigital.md)
- [Dynamics 365 Customer Service (klienta kartes pievienojumprogramma)](customer-card-add-in.md)
- [Dynamics 365 Marketing](export-dynamics365-marketing.md)
- [Dynamics 365 Sales](export-dynamics365-sales.md)
- [Dynamics 365 Sales centrs (klienta kartes pievienojumprogramma)](customer-card-add-in.md)
- [Facebook Ads Manager](export-facebook.md)
- [Google Ads ikona](export-google-ads.md)
- [LiveRamp&reg;](export-liveramp.md)
- [MailChimp](export-mailchimp.md)
- [Marketo](export-marketo.md)
- [Power Automate](export-power-automate.md)
- [Power Apps](export-power-apps.md)
- [Power BI](export-power-bi.md)
- [SendGrid](export-sendgrid.md)
- [SFTP](export-sftp.md)

## <a name="add-a-new-export-destination"></a>Jaunu eksportēšanas galamērķu pievienošana

Lai pievienotu eksportēšanas galamērķus, jums ir [administratora atļaujas](permissions.md). Ja eksportējat uz Microsoft pakalpojumiem, mēs pieņemam, ka abi pakalpojumi atrodas vienā un tajā pašā organizācijā.

1. Dodieties uz sadaļu **Administrators** > **Eksportēšanas galamērķi**.

1. Pārslēdzieties uz cilni **Mani eksportēšanas galamērķi**.

1. Atlasiet **Pievienot galamērķi**, lai izveidotu jaunu eksportēšanas galamērķi.

1. Rūts **Pievienot galamērķi** nolaižamajā sarakstā atlasiet eksportēšanas galamērķa **Tipu**.

1. Norādiet nepieciešamo informāciju un atlasiet **Tālāk**, lai izveidotu eksportēšanas galamērķi.

Cilnes elementā **Iestatīt** var atlasīt arī **Atklāt**.

## <a name="view-export-destinations"></a>Skatīt eksportēšanas galamērķus

Pēc eksportēšanas galamērķu izveides tie ir atrodami tabulā **Mani eksportēšanas galamērķi**. Šajā tabulā ir trīs kolonnas:

- **Parādāmais nosaukums**: Nosaukums, ko ievadījāt, veidojot galamērķi.
- **Tips**: Eksportēšanas galamērķa tips, ko iestatījāt, izveidojot galamērķi.
- **Izveidots**: Datums, kad izveidojāt galamērķi.

## <a name="edit-an-export-destination"></a>Eksportēšanas galamērķa rediģēšana

1. Atlasiet eksportēšanas galamērķa vertikālo elipsi, ko vēlaties rediģēt.

   > [!div class="mx-imgBorder"]
   > ![Vertikālā elipse](media/export-destinations-page-ellipsis.png "Vertikālā elipse")

1. Nolaižamajā izvēlnē atlasiet **Rediģēt**.

1. Mainiet vērtības, kurām nepieciešama atjaunināšana, un atlasiet **Saglabāt**.

## <a name="export-data-on-demand"></a>Datu eksportēšana pēc pieprasījuma

Pēc eksportēšanas galamērķa savienotāja konfigurēšanas eksportēšanas darbības notiks ar katru [plānoto atsvaidzināšanu](system.md#schedule-tab).

Lai eksportētu datus, negaidot plānoto atsvaidzināšanu, cilnē **Mani eksportēšanas galamērķi** atlasiet **Administrators** > **Eksportēšanas galamērķi**.

> [!div class="mx-imgBorder"]
> ![Vertikālā elipse](media/export-destinations-page-ellipsis.png "Vertikālā elipse")

- Atlasiet opciju **Eksportēt** virs saraksta, lai vienlaikus izpildītu eksportēšanu uz visiem eksportēšanas galamērķiem.
- Pēc saraksta elementa atlasiet daudzpunkti (...) un pēc tam izvēlieties opciju **Eksportēt**, lai izpildītu eksportēšanu atsevišķam eksportēšanas galamērķim.

## <a name="remove-an-export-destination"></a>Eksportēšanas galamērķa noņemšana

Lai noņemtu eksportēšanas galamērķi, sāciet no galvenās **eksportēšanas galamērķu** lapas.

1. Atlasiet eksportēšanas galamērķa vertikālo elipsi, ko vēlaties noņemt.

   > [!div class="mx-imgBorder"]
   > ![Vertikālā elipse](media/export-destinations-page-ellipsis.png "Vertikālā elipse")

2. Atlasiet **Noņemt** nolaižamajā izvēlnē.

3. Apstipriniet noņemšanu, apstiprinājuma ekrānā atlasot pogu **Noņemt**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]