---
title: Uzņemt datus no Azure Synapse Analytics
description: Izmantojiet datu bāzi Azure Synapse programmā kā datu avots programmā Dynamics 365 Customer Insights.
ms.date: 02/24/2022
ms.reviewer: v-wendysmith
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 7c758dccf7ea34dd7b8f80d05eff1ed12030526f
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643346"
---
# <a name="connect-an-azure-synapse-data-source-preview"></a>Azure Synapse datu avots savienošana (priekšskatījums)

Azure Synapse Analytics ir uzņēmuma analītikas pakalpojums, kas paātrina laiku, lai gūtu ieskatu datu noliktavās un lielo datu sistēmās. Azure Synapse Analytics apvieno labākās SQL tehnoloģijas, ko izmanto uzņēmuma datu uzglabāšanā, Spark tehnoloģijas, ko izmanto lielajiem datiem, Data Explorer žurnāla un laikrindu analīzei, Konveijerus datu integrācijai un ETL/ELT, kā arī dziļu integrāciju ar citiem Azure pakalpojumiem, piemēram Power BI, un Cosmos DB AzureML.

Plašāku informāciju skatiet [Azure Synapse overview](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Priekšnoteikumi

Lai konfigurētu savienojumu no Dynamics 365 Customer Insights uz Azure Synapse.

> [!IMPORTANT]
> Noteikti iestatiet visas **lomu piešķires**, kā aprakstīts.  

## <a name="prerequisites-in-customer-insights"></a>Customer Insights priekšnosacījumi

* Programmā Customer Insights **ir administratora** loma. Uzziniet vairāk par [lietotāju atļaujām customer insights](permissions.md#assign-roles-and-permissions).

Azure: 

- Aktīvs Azure abonements.

- Ja izmantojat jaunu Azure Data Lake Storage Gen2 kontu, *Customer Insights pakalpojumu vadītājam ir nepieciešamas* Krātuves **BLOB datu līdzstrādnieka** atļaujas. Uzziniet vairāk par [savienojuma izveidi Azure Data Lake Storage ar klientu ieskatu](connect-service-principal.md) pakalpojumu vadītāju. Data Lake Storage Gen2 **jābūt** iespējotai [hierarhiskajai nosaukumvietai](/azure/storage/blobs/data-lake-storage-namespace).

- Resursu grupā Azure Synapse atrodas darbvieta, *pakalpojuma principālam* un *Customer Insights* lietotājam ir jāpiešķir vismaz **Reader** atļaujas. Papildinformāciju skatiet sadaļā [Azure lomu piešķiršana, izmantojot Azure portālu](/azure/role-based-access-control/role-assignments-portal).

- *Lietotājam* ir nepieciešamas **Blob datu līdzdalībā glabātavas** atļaujas Azure Data Lake Storage Gen2 kontā, kur šie dati atrodas un ir saistīti ar šo Azure Synapse darbvietu. Uzziniet vairāk par [Azure portāla izmantošanas iespēju, lai piešķirtu Azure lomu piekļuvei BLOB un rindas datiem](/azure/storage/common/storage-auth-aad-rbac-portal) un [Krātuves Blob datu līdzdalības atļaujām](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- *[Azure Synapse darbvietas pārvaldītajai identitātei](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* ir nepieciešamas **Storage Blob datu līdzdalības** atļaujas Azure Data Lake Storage Gen2 kontā, kur atrodas dati un ir saistīti ar Azure Synapse darbvietu. Uzziniet vairāk par [Azure portāla izmantošanas iespēju, lai piešķirtu Azure lomu piekļuvei BLOB un rindas datiem](/azure/storage/common/storage-auth-aad-rbac-portal) un [Krātuves Blob datu līdzdalības atļaujām](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Darbvietā Azure Synapse *Customer Insights* pakalpojumu vadītājam ir **jāpiešķir Synapse administratora** loma. Papildinformāciju skatiet rakstā [Kā iestatīt piekļuves vadīklu jūsu Synapse darbvietai](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="connect-to-data-lake-databases-in-azure-synapse-analytics"></a>Savienojuma izveide ar datu ezeru datu bāzēm Azure Synapse Analytics

1. Dodieties uz **Dati** > **Datu avoti**.

1. Atlasiet **Pievienot datu avotu**.

1. Izvēlieties **Azure Synapse Analytics (Priekšskatījums)** metodi.

1. Sniedziet datu avota **Nosaukmu** un atlasiet **Tālāk**, lai izveidotu datu avotu. 

1. [Izvēlieties pieejamo savienojumu ar](connections.md)Azure Synapse Analytics vai izveidojiet jaunu savienojumu.

1. **Atlasītajā** savienojumā pievienotajā darbvietā izvēlieties ezera datu bāzi Azure Synapse Analytics un atlasiet **Tālāk**.

1. Atlasiet entītijas, ko uzņemt no pievienotās datu bāzes. 

1. Pēc izvēles izvēlieties datu entītijas, kurās atļaut datu profilēšanu. 

1. Atlasiet **Saglabāt**, lai lietotu atlasi, un sāciet datu uzņemšanu no jaunizveidotās datu avots, kas saistītas ar ezera datu bāzes tabulām programmā Azure Synapse Analytics.
