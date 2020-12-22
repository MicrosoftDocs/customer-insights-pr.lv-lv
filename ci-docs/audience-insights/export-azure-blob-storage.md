---
title: Customer Insights datu eksportēšana Azure Blob krātuvē
description: Uzzinieto, kā konfigurēt savienojumu ar Azure Blob krātuvi.
ms.date: 09/18/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 925b53260e7c633e17d7f172d2dd2d581e982e10
ms.sourcegitcommit: 334633cbd58f5659d20b4f87252c1a10cc7130db
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 12/03/2020
ms.locfileid: "4667148"
---
# <a name="connector-for-azure-blob-storage-preview"></a>Savienotājs Azure Blob krātuvei (priekšskatījums)

Uzglabājiet Customer Insights datus Azure Blob krātuvē vai izmantojiet tos datu pārsūtīšanai uz citām programmām.

## <a name="configure-the-connector-for-azure-blob-storage"></a>Konfigurējiet savienotāju Azure Blob krātuvei

1. Sadaļā Auditorijas ieskati ejiet uz **Administrators** > **Eksportēšanas galamērķi**.

1. Sadaļā **Azure Blob krātuve** atlasiet **Iestatīt**.

1. Ievadiet **Konta nosaukums**, **Konta atslēga** un **Konteiners** savam Azure Blob krātuves kontam.
    - Papildinformāciju, kā atrast Azure Blob krātuves konta nosaukumu un konta atslēgu, skatiet sadaļā [Krātuves konta iestatījumu pārvaldība Azure portālā](https://docs.microsoft.com/azure/storage/common/storage-account-manage).
    - Lai uzzinātu, kā izveidot konteineru, skatiet sadaļu [Konteinera izveide](https://docs.microsoft.com/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Laukā **Parādāmais nosaukums** piešķiriet galamērķim atpazīstamu nosaukumu.

1. Atlasiet **Tālāk**.

1. Atzīmējiet lodziņu blakus visām entītijām, ko vēlaties eksportēt šajā galamērķī.

1. Atlasiet **Saglabāt**.

Eksportētie dati tiek glabāti jūsu konfigurētajā Azure Blob krātuves konteinerā. Konteinerā automātiski tiek izveidoti šādi mapju ceļi:

- Avota entītijām un sistēmas ģenerētajām entītijām: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`
  - Piemērs: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`
- Eksportēto entītiju model.json fails atradīsies %ExportDestinationName% līmenī
  - Piemērs: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`

## <a name="export-the-data"></a>Datu eksportēšana

Datus var [eksportēt pēc pieprasījuma](/export-destinations.md#export-data-on-demand). Eksportēšana arī tiks palaista ar katru [plānoto atsvaidzināšanu](system.md#schedule-tab).
