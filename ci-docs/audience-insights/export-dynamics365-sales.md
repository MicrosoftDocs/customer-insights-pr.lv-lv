---
title: Customer Insights datu eksportēšana uz Dynamics 365 Sales
description: Uzziniet, kā konfigurēt savienojumu ar Dynamics 365 Sales.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: af0824e69dfdf620a0ac756e32a9bd3dd85e5151
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643827"
---
# <a name="connector-for-dynamics-365-sales-preview"></a>Savienotājs ar Dynamics 365 Sales (priekšskatījums)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Izmantojiet klientu datus, lai izveidotu mārketinga adresātu sarakstus, tālāko darbību plūsmas un nosūtītu reklāmas ar Dynamics 365 Sales.

## <a name="prerequisite"></a>Priekšnosacījums

Kontaktpersonu ieraksti [no Dynamics 365 Sales, kas uzņemti Common Data Service](connect-power-query.md).

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
