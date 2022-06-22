---
title: Customer Insights datu eksportēšana Azure Blob krātuvē
description: Uzziniet, kā konfigurēt savienojumu un eksportēt uz Blob krātuvi.
ms.date: 06/09/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 623926bf520b19ee4156b7a05e953241cd819e9e
ms.sourcegitcommit: 8e9f0a9693fd8d91ad0227735ff03688fef5406f
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 06/10/2022
ms.locfileid: "8947147"
---
# <a name="export-segment-list-and-other-data-to-azure-blob-storage-preview"></a>Segmentu saraksta un citu datu eksportēšana uz Azure Blob krātuvi (priekšskatījums)

Glabājiet Customer Insights datus Blob krātuvē vai izmantojiet pakalpojumu, lai pārsūtītu datus uz citām programmām.

## <a name="known-limitations"></a>Zināmie ierobežojumi

1. Azure Blob krātuvē varat izvēlēties starp [Standarta veiktspējas un Premium veiktspējas līmeni](/azure/storage/blobs/storage-blob-performance-tiers). Ja izvēlaties Premium veiktspējas līmeni, atlasiet [premium bloka BLOB kā uzņēmuma tipu](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-the-connection-to-blob-storage"></a>Savienojuma ar Blob Storage iestatīšana

1. Dodieties uz **Administrators** > **Savienojumi**.

1. Atlasiet vienumu **Pievienot savienojumu** un atlasiet **Azure Blob krātuve**, lai konfigurētu savienojumu.

1. Laukā **Parādāmais nosaukums** piešķiriet savienojumam atpazīstamu nosaukumu. Parādāmais nosaukums un nosaukuma veids raksturo šo savienojumu. Ir ieteicams izvēlēties nosaukumu, kas paskaidro savienojuma nolūku.

1. Izvēlieties, kurš var izmantot šo savienojumu. Ja nesāksit nekādas darbības, noklusējums būs Administratori. Papildinformāciju skatiet rakstā [Atļaut līdzstrādniekiem izmantot savienojumu eksportam](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Ievadiet sava Blob Storage konta **Konta nosaukumu**, **Konta atslēgu** un **Konteineru**.
    - Papildinformāciju par Blob krātuves konta nosaukuma un konta atslēgas meklēšanu skatiet sadaļā [Krātuves konta iestatījumu pārvaldība Azure portālā](/azure/storage/common/storage-account-manage).
    - Lai uzzinātu, kā izveidot konteineru, skatiet sadaļu [Konteinera izveide](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Lai pabeigtu savienošanu, atlasiet **Saglabāt**. 

## <a name="configure-an-export"></a>Eksporta konfigurēšana

Šo eksportu varat konfigurēt, ja jums ir piekļuve šā veida pieslēgumam. Papildinformāciju skatiet rakstā [Atļaujas, kas nepieciešamas eksporta konfigurēšanai](export-destinations.md#set-up-a-new-export).

> [!IMPORTANT]
> Ja ieslēgsit nevajadzīgās dzēšanas iestatījumu Azure Blob Storage kontam, eksportēšana neizdosies. Izslēdziet nevajadzīgo dzēšanu, lai eksportētu datus uz BLOB. Papildinformāciju skatiet sadaļā [Iespējot Blob nevajadzīgo dzēšanu](/azure/storage/blobs/soft-delete-blob-enable)

1. Pārejiet uz **Dati** > **Eksportēšana**.

1. Lai izveidotu jaunu eksportu, atlasiet **Pievienot galamērķi**.

1. Laukā **Savienošana eksportam** atlasiet savienojumu no sadaļas Azure Blob Storage. Ja neredzat šo sadaļas nosaukumu, tad jums nav pieejami šī tipa savienojumi.

1. Atzīmējiet lodziņu blakus visām entītijām, ko vēlaties eksportēt šajā galamērķī.

1. Atlasiet vienumu **Saglabāt**.

Eksporta saglabāšana automātiski nepalaiž eksportu.

Eksports tiek palaists ar katru [plānoto atsvaidzināšanu](system.md#schedule-tab).

Varat arī [eksportēt datus pēc pieprasījuma](export-destinations.md#run-exports-on-demand).

Eksportētie dati tiek glabāti jūsu konfigurētajā Blob Storage konteinerā. Konteinerā automātiski tiek izveidoti šādi mapju ceļi:

- Avota entītijām un sistēmas ģenerētajām entītijām:  
  `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`  
  - Piemērs: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`
  
  > [!TIP]
  > Eksportējot entītijas, kurās ir liels datu apjoms, katram eksportam vienā mapē var rasties vairāki CSV faili. Eksporta sadalīšana notiek veiktspējas apsvērumu dēļ, lai samazinātu laiku, kas nepieciešams eksporta pabeigšanai.

- Eksportēto entītiju model.json būs %ExportDestinationName% līmenī.  
  - Piemērs: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`

[!INCLUDE [footer-include](includes/footer-banner.md)]
