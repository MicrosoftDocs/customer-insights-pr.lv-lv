---
title: Segmentu eksportēšana uz Dynamics 365 Marketing (priekšskatījums)
description: Uzziniet, kā konfigurēt savienojumu un eksportēt uz Dynamics 365 Marketing.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- customerInsights
ms.openlocfilehash: 123b565421a7d096e7341a8f600f91e59aefe8d0
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196633"
---
# <a name="export-segments-to-dynamics-365-marketing-preview"></a>Segmentu eksportēšana uz Dynamics 365 Marketing (priekšskatījums)

Izmantojiet [segmentus](segments.md), lai ģenerētu kampaņas un sazinātos ar noteiktām klientu grupām, izmantojot [Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments).

Ja izmantojat jaunās iespējas Dynamics 365 Marketing reāllaika automatizētas kampaņas orķestrācijai Dataverse org, nav nepieciešams izveidot standarta eksportēšanu uz Dynamics 365 Marketing. Kontaktpersonas un segmenti no Customer Insights ir pieejami tieši programmā Dynamics 365 Marketing pēc tam, kad ir izveidots savienojums ar Marketing un Customer Insights. Pirms esošo eksportēšanas dzēšanas pārskatiet dokumentāciju par [to, kā savienot Customer Insights un Dynamics 365 Marketing automatizēta kampaņa orķestrāciju](/dynamics365/marketing/real-time-marketing-ci-profile).

## <a name="prerequisite"></a>Priekšnosacījums

Lai varētu eksportēt segmentu no programmas Customer Insights uz programmu Marketing, programmā Dynamics 365 Marketing ir jābūt kontaktpersonu ierakstiem. Papildinformācija par kontaktpersonu uzņemšanu programmā [Dynamics 365 Marketing, izmantojot Microsoft Dataverse](connect-dataverse-managed-lake.md).

> [!NOTE]
> Eksportējot segmentus no Customer Insights uz Marketing, mārketinga instancēs netiks izveidoti jauni kontaktpersonu ieraksti. Mārketinga kontaktpersonu ieraksti ir jāuzņem programmā Customer Insights un jāizmanto kā datu avots. Tie ir jāiekļauj arī vienotā Klienta entītijā, lai kartētu klientu ID uz kontaktu ID pirms segmentu eksportēšanas.

## <a name="set-up-connection-to-marketing"></a>Savienojuma ar Marketing iestatīšana

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Dodieties uz **Administrators** > **Savienojumi**.

1. Atlasiet **Pievienot savienojumu** un izvēlieties **Dynamics 365 Marketing**.

1. Laukā **Parādāmais nosaukums** piešķiriet savienojumam atpazīstamu nosaukumu. Parādāmais nosaukums un nosaukuma veids raksturo šo savienojumu. Ir ieteicams izvēlēties nosaukumu, kas paskaidro savienojuma nolūku.

1. Izvēlieties, kurš var izmantot šo savienojumu. Pēc noklusējuma tie ir tikai administratori. Papildinformāciju skatiet rakstā [Atļaut līdzstrādniekiem izmantot savienojumu eksportam](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Ievadiet jūsu organizācijas Marketing URL laukā **Servera adrese**.

1. Sadaļā **Servera administratora konts** atlasiet **Pieteikties** un izvēlieties Dynamics 365 Marketing kontu.

1. Kartējiet entītijas Klienta ID lauku Kontaktpersona ID uz Dynamics 365 kontaktpersonas ID.

1. Pārskatiet datu privātumu [un atbilstību](connections.md#data-privacy-and-compliance) un atlasiet **Es piekrītu**.

1. Lai pabeigtu savienošanu, atlasiet **Saglabāt**.

## <a name="configure-an-export"></a>Eksporta konfigurēšana

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Pārejiet uz **Dati** > **Eksportēšana**.

1. Atlasiet **Pievienot eksportēšanu**.

1. Laukā **Savienošana eksportam** atlasiet savienojumu no sadaļas Dynamics 365 Marketing. Ja nav pieejamu savienojumu, sazinieties ar administratoru.

1. Ievadiet eksportēšanas nosaukumu.

1. Entītijā Klients atlasiet lauku Kontaktpersona ID, kas atbilst Dynamics 365 kontaktpersonas ID.

1. Atlasiet segmentus, kurus vēlaties eksportēt.

1. Atlasiet **Saglabāt**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
