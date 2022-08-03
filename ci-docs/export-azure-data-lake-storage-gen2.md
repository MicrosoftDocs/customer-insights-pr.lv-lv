---
title: Datu eksportēšana uz Azure Data Lake Storage Gen2 (priekšskatījums)
description: Uzziniet, kā konfigurēt savienojumu ar Azure Data Lake Storage Gen2.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 55a61e4d9166df7809a64aeb1168a730402aaed6
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196449"
---
# <a name="export-data-to-azure-data-lake-storage-gen2-preview"></a>Datu eksportēšana uz Azure Data Lake Storage Gen2 (priekšskatījums)

Glabājiet Customer Insights datus pakalpojuma Azure Data Lake Storage Gen2 kontā vai izmantojiet to, lai pārsūtītu datus uz citām programmām.

## <a name="prerequisites"></a>Priekšnoteikumi

- Krātuves [konts, ko izmantot kopā ar Azure Data Lake Gen2](/azure/storage/blobs/create-data-lake-storage-account). Lai atrastu krātuves konta nosaukumu un atslēgu, skatiet rakstu [Krātuves konta iestatījumu pārvaldība Azure portālā](/azure/storage/common/storage-account-manage).
- Azure [Blob krātuves konteiners](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

## <a name="known-limitations"></a>Zināmie ierobežojumi

- Azure Data Lake Storage Gen2 gadījumā izvēlieties starp [standarta veiktspēju un Premium veiktspējas līmeni](/azure/storage/blobs/create-data-lake-storage-account). Ja izvēlaties Premium veiktspējas līmeni, atlasiet [premium bloka BLOB kā uzņēmuma tipu](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-connection-to-azure-data-lake-storage-gen2"></a>Savienojuma Azure Data Lake Storage ar Gen2 iestatīšana

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Dodieties uz **Administrators** > **Savienojumi**.

1. Atlasiet **Pievienot savienojumu** un izvēlieties **Azure Data Lake Gen 2**.

1. Laukā **Parādāmais nosaukums** piešķiriet savienojumam atpazīstamu nosaukumu. Parādāmais nosaukums un nosaukuma veids raksturo šo savienojumu. Ir ieteicams izvēlēties nosaukumu, kas paskaidro savienojuma nolūku.

1. Izvēlieties, kurš var izmantot šo savienojumu. Pēc noklusējuma tie ir tikai administratori. Papildinformāciju skatiet rakstā [Atļaut līdzstrādniekiem izmantot savienojumu eksportam](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Ievadiet **Uzņēmuma nosaukumu**, **Uzņēmuma atslēgu** un **Konteineru** jūsu Azure Data Lake Storage Gen2.

1. Pārskatiet datu privātumu [un atbilstību](connections.md#data-privacy-and-compliance) un atlasiet **Es piekrītu**.

1. Lai pabeigtu savienošanu, atlasiet **Saglabāt**.

## <a name="configure-an-export"></a>Eksporta konfigurēšana

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Pārejiet uz **Dati** > **Eksportēšana**.

1. Atlasiet **Pievienot eksportēšanu**.

1. **Laukā Savienojums eksportēšanai** izvēlieties savienojumu no sadaļas Azure datu ezers. Ja nav pieejamu savienojumu, sazinieties ar administratoru.

1. Ievadiet eksportēšanas nosaukumu.

1. Ievadiet Gen2 krātuves mapes Azure Data Lake Storage nosaukumu.

1. Atzīmējiet lodziņu blakus visām entītijām, ko vēlaties eksportēt šajā galamērķī.

1. Atlasiet **Saglabāt**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Eksportētie dati tiek glabāti jūsu konfigurētajā Azure Data Lake Gen 2 krātuves konteinerā.

> [!TIP]
> Eksportējot entītijas, kurās ir liels datu apjoms, katrā eksportā var rasties vairāki CSV faili vienā mapē. Eksportēšanas sadalīšana notiek veiktspējas apsvērumu dēļ, lai samazinātu laiku, kas nepieciešams eksportēšanas pabeigšanai.

[!INCLUDE [footer-include](includes/footer-banner.md)]
