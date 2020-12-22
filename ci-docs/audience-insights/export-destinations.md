---
title: Galamērķu eksportēšana
description: Eksportēt datus un pārvaldīt eksportēšanas galamērķus.
ms.date: 07/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 9032d99357db86e66588eda544211a5f8eb2f23b
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643872"
---
# <a name="export-destinations-preview"></a>Galamērķu eksportēšana (priekšskatījums)

Lapā **Eksportēšanas galamērķi** tiek parādītas visas jūsu iestatītās datu eksportēšanas vietas. Eksportēšanai var pievienot arī jaunus adresātus. Turklāt tajā ir redzama pašlaik pieejamo opciju eksportēšana. Saņemiet īsu pārskatu, aprakstu un uzziniet, ko varat darīt ar katru paplašināmības opciju. Eksportējiet vienotos profilus, mērvienības un segmentus uz atbalstītajām programmām, kas ir saistošas jūsu uzņēmumam.

Dodieties uz **Administrators** > **Eksportēšanas galamērķi**, lai atrastu šādas paplašināšanas opcijas:

- [Dynamics 365 klienta kartes pievienojumprogramma](customer-card-add-in.md)
- [Facebook Reklāmu pārvaldnieka savienotājs](export-facebook.md)
- [Power Automate savienotājs](export-power-automate.md)
- [Power Apps savienotājs](export-power-apps.md)
- [Power BI savienotājs](export-power-bi.md)
- [DotDigital](export-dotdigital.md)
- [Dynamics 365 Sales](export-dynamics365-sales.md)
- [Dynamics 365 Marketing](export-dynamics365-marketing.md)
- [Azure Blob krātuve](export-azure-blob-storage.md)
- [LiveRamp&reg; savienotājs](export-liveramp.md)
- [Bots pakalpojumam Microsoft Teams](export-teams-bot.md)
- [MailChimp](export-mailchimp.md)
- [Customer Insights API](apis.md)

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
