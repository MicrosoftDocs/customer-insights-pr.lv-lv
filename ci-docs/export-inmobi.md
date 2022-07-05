---
title: Eksportējiet Customer Insights datus uz InMobi
description: Uzziniet, kā konfigurēt savienojumu un eksportēt uz InMobi.
ms.date: 06/27/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8261c8adfe231792e70fc85432237cf73d5cd5a7
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 06/29/2022
ms.locfileid: "9059613"
---
# <a name="export-segment-list-and-other-data-to-inmobi-preview"></a>Segmentu saraksta un citu datu eksportēšana uz InMobi (priekšskatījums)

Eksportējiet segmentu sarakstus vai citus datus no savas Customer Insights instances uz [InMobi](https://www.inmobi.com/).

## <a name="prerequisites"></a>Priekšnoteikumi

1. Jums ir [InMobi konts](https://www.inmobi.com/) un administratora akreditācijas dati.
1. Jums ir Azure Blob krātuves konta nosaukums un atbilstošā konta atslēga. Papildinformāciju skatiet sadaļā [Krātuves konta iestatījumu pārvaldība Azure portālā](/azure/storage/common/storage-account-manage). Krātuves kontā ir konteiners, uz kuru eksportēt inMobi datus. Papildinformāciju skatiet sadaļā [Konteinera izveide](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).
1. InMobi izveidos tiešu savienojumu ar jūsu Blob krātuvi un konfigurēs automātisku jūsu datu importēšanu inMobi. Sazinieties ar savu InMobi pārstāvi, lai uzsāktu procesu.

## <a name="known-limitations"></a>Zināmie ierobežojumi

1. Azure Blob krātuvei varat izvēlēties starp [standarta veiktspēju un Premium veiktspējas līmeni](/azure/storage/blobs/storage-blob-performance-tiers). Ja izvēlaties Premium veiktspējas līmeni, atlasiet [premium bloka BLOB kā uzņēmuma tipu](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-the-connection-to-azure-blob-storage-and-configure-an-export"></a>Savienojuma iestatīšana ar Azure Blob krātuvi un eksportēšanas konfigurēšana

1. Izpildiet norādījumus, lai [iestatītu savienojumu ar Azure Blob krātuvi](export-azure-blob-storage.md).
2. Izpildiet norādījumus, lai [konfigurētu eksportēšanu](export-azure-blob-storage.md#configure-an-export).

[!INCLUDE [footer-include](includes/footer-banner.md)]
