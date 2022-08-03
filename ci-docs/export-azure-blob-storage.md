---
title: Datu eksportēšana uz Azure Blob krātuvi (priekšskatījums)
description: Uzziniet, kā konfigurēt savienojumu un eksportēt uz Blob krātuvi.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 22593ed05f403a40fe494e30f807b57658594f01
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195713"
---
# <a name="export-data-to-an-azure-blob-storage-preview"></a>Datu eksportēšana uz Azure Blob krātuvi (priekšskatījums)

Glabājiet Customer Insights datus Blob krātuvē vai izmantojiet pakalpojumu, lai pārsūtītu datus uz citām programmām.

## <a name="prerequisites"></a>Priekšnoteikumi

- [Azure Blob krātuves konta](/azure/storage/blobs/create-data-lake-storage-account) nosaukums un konta atslēga. Lai atrastu nosaukumu un atslēgu, skatiet rakstu [Krātuves konta iestatījumu pārvaldība Azure portālā](/azure/storage/common/storage-account-manage).
- Azure [Blob krātuves konteiners](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

## <a name="known-limitations"></a>Zināmie ierobežojumi

- Azure Blob krātuvei izvēlieties starp standarta veiktspēju [un Premium veiktspējas līmeni](/azure/storage/blobs/storage-blob-performance-tiers). Ja izvēlaties Premium veiktspējas līmeni, atlasiet [premium bloka BLOB kā uzņēmuma tipu](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-connection-to-blob-storage"></a>Savienojuma ar Blob krātuvi iestatīšana

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Dodieties uz **Administrators** > **Savienojumi**.

1. Atlasiet **Pievienot savienojumu** un izvēlieties **Azure Blob krātuve**.

1. Laukā **Parādāmais nosaukums** piešķiriet savienojumam atpazīstamu nosaukumu. Parādāmais nosaukums un nosaukuma veids raksturo šo savienojumu. Ir ieteicams izvēlēties nosaukumu, kas paskaidro savienojuma nolūku.

1. Izvēlieties, kurš var izmantot šo savienojumu. Pēc noklusējuma tie ir tikai administratori. Papildinformāciju skatiet rakstā [Atļaut līdzstrādniekiem izmantot savienojumu eksportam](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Ievadiet sava Blob Storage konta **Konta nosaukumu**, **Konta atslēgu** un **Konteineru**.

1. Pārskatiet datu privātumu [un atbilstību](connections.md#data-privacy-and-compliance) un atlasiet **Es piekrītu**.

1. Lai pabeigtu savienošanu, atlasiet **Saglabāt**.

## <a name="configure-an-export"></a>Eksporta konfigurēšana

Lai konfigurētu šo eksportēšanu, šim savienojuma tipam ir [jābūt atļaujai](export-destinations.md#set-up-a-new-export).

> [!IMPORTANT]
> Ja Azure Blob krātuves kontam ieslēdzāt [mīkstās dzēšanas iestatījumu](/azure/storage/blobs/soft-delete-blob-enable), eksportēšana neizdosies. Izslēdziet nevajadzīgo dzēšanu, lai eksportētu datus uz BLOB.

1. Pārejiet uz **Dati** > **Eksportēšana**.

1. Atlasiet **Pievienot eksportēšanu**.

1. Laukā **Savienošana eksportam** atlasiet savienojumu no sadaļas Azure Blob Storage. Ja nav pieejamu savienojumu, sazinieties ar administratoru.

1. Ievadiet eksportēšanas nosaukumu.

1. Ievadiet mapes nosaukumu Blob krātuvei.

1. Atzīmējiet lodziņu blakus visām entītijām, ko vēlaties eksportēt šajā galamērķī.

1. Atlasiet **Saglabāt**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Eksportētie dati tiek glabāti jūsu konfigurētajā Blob Storage konteinerā. Konteinerā automātiski tiek izveidoti šādi mapju ceļi:

- Avota entītijām un sistēmas ģenerētajām entītijām:  
  *%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*  

  Piemērs: Dynamics365CustomerInsights/CustomerInsights_ abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv
  
  > [!TIP]
  > Eksportējot entītijas, kurās ir liels datu apjoms, katrā eksportā var rasties vairāki CSV faili vienā mapē. Eksportēšanas sadalīšana notiek veiktspējas apsvērumu dēļ, lai samazinātu laiku, kas nepieciešams eksportēšanas pabeigšanai.

- Eksportēto entītiju modelis.json atrodas līmenī *%ExportDestinationName%*.  
  
  Piemērs: Dynamics365CustomerInsights/CustomerInsights_ abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json

[!INCLUDE [footer-include](includes/footer-banner.md)]
