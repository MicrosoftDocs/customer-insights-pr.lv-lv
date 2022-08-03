---
title: Eksportējiet Customer Insights datus uz InMobi
description: Uzziniet, kā konfigurēt savienojumu un eksportēt uz InMobi.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ef486ad6786ef01be977f3d6bda69ce8a2b081c7
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195897"
---
# <a name="export-customer-insights-data-to-inmobi-preview"></a>Customer Insights datu eksportēšana uz InMobi (priekšskatījums)

Eksportējiet segmentu sarakstus vai citus datus no savas Customer Insights instances uz [InMobi](https://www.inmobi.com/).

## <a name="prerequisites"></a>Priekšnoteikumi

- [InMobi konts](https://www.inmobi.com/) un administratora akreditācijas dati.
- [Azure Blob krātuves konta](/azure/storage/blobs/create-data-lake-storage-account) nosaukums un konta atslēga. Lai atrastu nosaukumu un atslēgu, skatiet rakstu [Krātuves konta iestatījumu pārvaldība Azure portālā](/azure/storage/common/storage-account-manage).
- Azure Blob krātuves [konteiners](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container) InMobi datu eksportēšanai uz.
- InMobi izveidos tiešu savienojumu ar jūsu Blob krātuvi un konfigurēs automātisku jūsu datu importēšanu inMobi. Sazinieties ar savu InMobi pārstāvi, lai uzsāktu procesu.

## <a name="known-limitations"></a>Zināmie ierobežojumi

- Azure Blob krātuvei izvēlieties starp standarta veiktspēju [un Premium veiktspējas līmeni](/azure/storage/blobs/storage-blob-performance-tiers). Ja izvēlaties Premium veiktspējas līmeni, atlasiet [premium bloka BLOB kā uzņēmuma tipu](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-connection-to-azure-blob-storage"></a>Savienojuma ar Azure Blob krātuvi iestatīšana

[Iestatiet savienojumu ar Azure Blob krātuvi](export-azure-blob-storage.md).

## <a name="configure-an-export"></a>Eksporta konfigurēšana

[Konfigurējiet eksportēšanu](export-azure-blob-storage.md#configure-an-export).

[!INCLUDE [footer-include](includes/footer-banner.md)]
