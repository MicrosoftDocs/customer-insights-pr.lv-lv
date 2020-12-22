---
title: Customer Insights datu eksportēšana uz Dynamics 365 Marketing
description: Uzziniet, kā konfigurēt savienojumu ar Dynamics 365 Marketing.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 163387779b64bd78ef08e2d96a5f1c9615062f28
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643782"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a>Savienotājs ar Dynamics 365 Marketing (priekšskatījums)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Izmantojiet [segmentus](segments.md) kampaņu veidošanai un saziņai ar specifisku klientu grupu pakalpojumā Dynamics 365 Marketing. Papildinformāciju skatiet tēmā [Segmentu izmantošana no Dynamics 365 Customer Insights ar Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)

## <a name="prerequisite"></a>Priekšnosacījums

Kontaktpersonu ieraksti [no Dynamics 365 Marketing, kas uzņemti Common Data Service](connect-power-query.md).

## <a name="configure-the-connector-for-marketing"></a>Savienotāja konfigurēšana pakalpojumam Marketing

1. Sadaļā Auditorijas ieskati ejiet uz **Administrators** > **Eksportēšanas galamērķi**.

1. Sadaļā **Dynamics 365 Marketing** atlasiet **Iestatīt**.

1. Piešķiriet eksportēšanas galamērķim atpazīstamu nosaukumu laukā **Parādāmais nosaukums**.

1. Ievadiet jūsu organizācijas Marketing URL laukā **Servera adrese**.

1. Sadaļā **Servera administratora konts** atlasiet **Pieteikties** un izvēlieties Dynamics 365 Marketing kontu.

1. Kartēt klienta ID lauku uz Dynamics 365 kontaktpersonas ID.

1. Atlasiet **Tālāk**.

1. Izvēlieties vienu vai vairākus segmentus.

1. Atlasiet vienumu **Saglabāt**.

## <a name="export-the-data"></a>Datu eksportēšana

Datus var [eksportēt pēc pieprasījuma](export-destinations.md). Eksportēšana arī tiks palaista ar katru [plānoto atsvaidzināšanu](system.md#schedule-tab).
