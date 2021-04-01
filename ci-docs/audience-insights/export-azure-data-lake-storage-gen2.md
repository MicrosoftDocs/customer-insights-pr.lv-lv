---
title: Customer Insights datu eksportēšana uz Azure Data Lake Storage Gen2
description: Uzziniet, kā konfigurēt savienojumu ar Azure Data Lake Storage Gen2.
ms.date: 02/04/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 7c0eef575f745efa6312d7141a6dd96607f9797e
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596647"
---
# <a name="connector-for-azure-data-lake-storage-gen2-preview"></a>Savienotājs ar Azure Data Lake Storage Gen2 (priekšskatījums)

Glabājiet Customer Insights datus pakalpojumā Azure Data Lake Storage Gen2 vai izmantojiet pakalpojumu, lai pārsūtītu datus uz citām programmām.

## <a name="configure-the-connector-for-azure-data-lake-storage-gen2"></a>Savienotāja konfigurēšana Azure Data Lake Storage Gen2

1. Sadaļā Auditorijas ieskati ejiet uz **Administrators** > **Eksportēšanas galamērķi**.

1. Sadaļā **Azure Data Lake Storage Gen2** atlasiet vienumu **Iestatīt**.

1. Laukā **Parādāmais nosaukums** piešķiriet galamērķim atpazīstamu nosaukumu.

1. Ievadiet **Uzņēmuma nosaukumu**, **Uzņēmuma atslēgu** un **Konteineru** jūsu Azure Data Lake Storage Gen2.
    - Informāciju par to, kā izveidot krātuves kontu, ko izmantot ar Azure Data Lake Storage Gen2, skatiet [Krātuves konta izveide](/azure/storage/blobs/create-data-lake-storage-account). 
    - Papildinformāciju, kā atrast Azure Data Lake Gen2 krātuves konta nosaukumu un konta atslēgu, skatiet sadaļā [Krātuves konta iestatījumu pārvaldība Azure portālā](/azure/storage/common/storage-account-manage).

1. Atlasiet **Tālāk**.

1. Atzīmējiet lodziņu blakus visām entītijām, ko vēlaties eksportēt šajā galamērķī.

1. Atlasiet vienumu **Saglabāt**.

## <a name="export-the-data"></a>Datu eksportēšana

Datus var [eksportēt pēc pieprasījuma](export-destinations.md#export-data-on-demand). Eksportēšana arī tiks palaista ar katru [plānoto atsvaidzināšanu](system.md#schedule-tab).