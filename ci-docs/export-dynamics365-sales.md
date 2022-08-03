---
title: Segmentu eksportēšana uz Dynamics 365 Sales (priekšskatījums)
description: Uzziniet, kā konfigurēt savienojumu un eksportēt uz Dynamics 365 Sales.
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
ms.openlocfilehash: c3497f4625cada49ae33c6987e58994a15536f9b
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195990"
---
# <a name="export-segments-to-dynamics-365-sales-preview"></a>Segmentu eksportēšana uz Dynamics 365 Sales (priekšskatījums)

Izmantojiet klientu datus, lai izveidotu mārketinga adresātu sarakstus, tālāko darbību plūsmas un nosūtītu reklāmas ar Dynamics 365 Sales.

## <a name="prerequisites"></a>Priekšnoteikumi

Lai varētu eksportēt segmentu no programmas Customer Insights uz programmu Sales, programmā Dynamics 365 Sales ir jābūt kontaktpersonu ierakstiem. Uzziniet vairāk par to, kā uzņemt kontaktpersonas no [Dynamics 365 Sales, izmantojot Microsoft Dataverse](connect-dataverse-managed-lake.md).

   > [!NOTE]
   > Eksportējot segmentus no Customer Insights uz Sales, pārdošanas instancēs netiks izveidoti jauni kontaktpersonu ieraksti. Sales kontaktpersonu ieraksti ir jāuzņem programmā Customer Insights un jāizmanto kā datu avots. Tie ir jāiekļauj arī vienotā Klienta entītijā, lai kartētu klientu ID uz kontaktu ID pirms segmentu eksportēšanas.

## <a name="known-limitations"></a>Zināmie ierobežojumi

Eksportēšana uz Dynamics 365 Sales ir ierobežota līdz 100 000 vienam segmentam, un tā pabeigšana var ilgt līdz 3 stundām.

## <a name="set-up-connection-to-sales"></a>Savienojuma ar pārdošanu iestatīšana

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Dodieties uz **Administrators** > **Savienojumi**.

1. Atlasiet **Pievienot savienojumu** un izvēlieties **Dynamics 365 Sales**.

1. Laukā **Parādāmais nosaukums** piešķiriet savienojumam atpazīstamu nosaukumu. Parādāmais nosaukums un nosaukuma veids raksturo šo savienojumu. Ir ieteicams izvēlēties nosaukumu, kas paskaidro savienojuma nolūku.

1. Izvēlieties, kurš var izmantot šo savienojumu. Pēc noklusējuma tie ir tikai administratori. Papildinformāciju skatiet rakstā [Atļaut līdzstrādniekiem izmantot savienojumu eksportam](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Ievadiet jūsu organizācijas Sales URL laukā **Servera adrese**.

1. Sadaļā **Servera administratora konts** atlasiet **Pieteikties** un izvēlieties Dynamics 365 Sales kontu.

1. Kartēt klienta ID lauku uz Dynamics 365 kontaktpersonas ID.

1. Pārskatiet datu privātumu [un atbilstību](connections.md#data-privacy-and-compliance) un atlasiet **Es piekrītu**.

1. Lai pabeigtu savienošanu, atlasiet **Saglabāt**.

## <a name="configure-an-export"></a>Eksporta konfigurēšana

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Pārejiet uz **Dati** > **Eksportēšana**.

1. Atlasiet **Pievienot eksportēšanu**.

1. Laukā **Savienošana eksportam** atlasiet savienojumu no sadaļas Dynamics 365 Sales. Ja nav pieejamu savienojumu, sazinieties ar administratoru.

1. Ievadiet eksportēšanas nosaukumu.

1. Entītijā Klients atlasiet lauku Kontaktpersona ID, kas atbilst Dynamics 365 kontaktpersonas ID.

1. Atlasiet segmentus, kurus vēlaties eksportēt.

1. Atlasiet vienumu **Saglabāt**

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
