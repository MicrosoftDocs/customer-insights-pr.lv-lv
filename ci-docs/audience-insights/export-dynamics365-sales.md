---
title: Customer Insights datu eksportēšana uz Dynamics 365 Sales
description: Uzziniet, kā konfigurēt savienojumu ar Dynamics 365 Sales.
ms.date: 02/01/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0013c4e6a96401d6cdbea55ed38f85f5e10dcc56
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269017"
---
# <a name="connector-for-dynamics-365-sales-preview"></a>Savienotājs ar Dynamics 365 Sales (priekšskatījums)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Izmantojiet Dynamics 365 Sales klientu datus, lai izveidotu mārketinga adresātu sarakstus, tālāko darbību plūsmas un nosūtītu reklāmas.

## <a name="prerequisite"></a>Priekšnosacījums

1. Lai varētu eksportēt segmentu no programmas Customer Insights uz programmu Sales, programmā Dynamics 365 Sales ir jābūt kontaktpersonu ierakstiem. Papildinformācija par kontaktpersonu uzņemšanu programmā [Dynamics 365 Sales, izmantojot Common Data Services](connect-power-query.md).

   > [!NOTE]
   > Eksportējot segmentus no auditorijas ieskatiem uz programmu Sales, netiek veidoti jauni kontaktpersonu ieraksti. Kontaktpersonu ieraksti no programmas Sales jābūt uzņemtiem auditorijas ieskatos un izmantotiem kā datu avotam. Tie ir jāiekļauj arī vienotā Klienta entītijā, lai kartētu klientu ID uz kontaktu ID pirms segmentu eksportēšanas.

## <a name="configure-the-connector-for-sales"></a>Savienotāja konfigurēšana pakalpojumam Sales

1. Sadaļā Auditorijas ieskati ejiet uz **Administrators** > **Eksportēšanas galamērķi**.

1. Sadaļā **Dynamics 365 Sales** atlasiet **Iestatīt**.

1. Piešķiriet eksportēšanas galamērķim atpazīstamu nosaukumu laukā **Parādāmais nosaukums**.

1. Ievadiet jūsu organizācijas Sales URL laukā **Servera adrese**.

1. Sadaļā **Servera administratora konts** atlasiet **Pieteikties** un izvēlieties Dynamics 365 Sales kontu.

1. Kartēt klienta ID lauku uz Dynamics 365 kontaktpersonas ID.

1. Atlasiet **Tālāk**.

1. Izvēlieties vienu vai vairākus segmentus.

1. Atlasiet vienumu **Saglabāt**.

## <a name="export-the-data"></a>Datu eksportēšana

Datus var [eksportēt pēc pieprasījuma](export-destinations.md). Eksportēšana arī tiks palaista ar katru [plānoto atsvaidzināšanu](system.md#schedule-tab).


[!INCLUDE[footer-include](../includes/footer-banner.md)]