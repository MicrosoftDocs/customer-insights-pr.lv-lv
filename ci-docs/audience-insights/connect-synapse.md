---
title: Uzņemt datus no Azure Synapse Analytics
description: Datu bāzes izmantošana programmā Azure Synapse datu avots programmā Dynamics 365 Customer Insights.
ms.date: 02/24/2022
ms.reviewer: v-wendysmith
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 163bef897880f0497bf00e90fd095621a2d14378
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 02/25/2022
ms.locfileid: "8356049"
---
# <a name="connect-an-azure-synapse-data-source-preview"></a>Azure Synapse datu avots savienošana (priekšskatījums)

Azure Synapse Analytics ir uzņēmuma analītikas pakalpojums, kas paātrina laiku līdz ieskatiem datu noliktavās un lielo datu sistēmās. Azure Synapse Analytics apvieno labākās SQL tehnoloģijas, ko izmanto uzņēmuma datu apkopošanā, Spark tehnoloģijas, ko izmanto lielajiem datiem, Datu pārlūku žurnālu un laik sēriju analīzei, Konveijerus datu integrācijai un ETL/ELT, kā arī dziļu integrāciju ar citiem Azure pakalpojumiem, piemēram Power BI,, Cosmos DB un AzureML.

Plašāku informāciju skatiet [Azure Synapse pārskatā](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Priekšnoteikumi

Lai konfigurētu savienojumu no Customer Insights uz Azure Synapse, ir jāizpilda tālāk sniegtie priekšnosacījumi.

> [!IMPORTANT]
> Noteikti iestatiet visas **lomu piešķires**, kā aprakstīts.  

## <a name="prerequisites-in-customer-insights"></a>Customer Insights priekšnosacījumi

* Jums ir **administratora** loma programmā Customer Insights. Papildinformācija par [lietotāju atļaujām auditorijas ieskatos](permissions.md#assign-roles-and-permissions).

Azure: 

- Aktīvs Azure abonements.

- Ja izmantojat jaunu Azure Data Lake Storage Gen2 kontu, *pakalpojuma vadītājam auditorijas ieskatiem* ir nepieciešamas **Krātuves BLOB datu līdzdalībnieku** atļaujas. Uzziniet vairāk par [savienojumu Azure Data Lake Storage ar pakalpojuma vadītāju auditorijas ieskatiem](connect-service-principal.md). Data Lake Storage Gen2 **jābūt** iespējotai [hierarhiskajai nosaukumvietai](/azure/storage/blobs/data-lake-storage-namespace).

- Resursu grupā, kas atrodas Azure Synapse darbvietā, *servisa vadītājam* un *auditorijas ieskatu lietotājam* ir jāpiešķir vismaz **Lasītāja** atļaujas. Papildinformāciju skatiet sadaļā [Azure lomu piešķiršana, izmantojot Azure portālu](/azure/role-based-access-control/role-assignments-portal).

- *Lietotājam* ir nepieciešamas **Blob datu līdzdalībā glabātavas** atļaujas Azure Data Lake Storage Gen2 kontā, kur šie dati atrodas un ir saistīti ar šo Azure Synapse darbvietu. Uzziniet vairāk par [Azure portāla izmantošanas iespēju, lai piešķirtu Azure lomu piekļuvei BLOB un rindas datiem](/azure/storage/common/storage-auth-aad-rbac-portal) un [Krātuves Blob datu līdzdalības atļaujām](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- *[Azure Synapse darbvietas pārvaldītajai identitātei](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* ir nepieciešamas **Storage Blob datu līdzdalības** atļaujas Azure Data Lake Storage Gen2 kontā, kur atrodas dati un ir saistīti ar Azure Synapse darbvietu. Uzziniet vairāk par [Azure portāla izmantošanas iespēju, lai piešķirtu Azure lomu piekļuvei BLOB un rindas datiem](/azure/storage/common/storage-auth-aad-rbac-portal) un [Krātuves Blob datu līdzdalības atļaujām](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Darbvietā Azure Synapse *servisa vadītājam auditorijas ieskatiem* ir jāpiešķir **Synapse administratora** loma. Papildinformāciju skatiet rakstā [Kā iestatīt piekļuves vadīklu jūsu Synapse darbvietai](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="connect-to-data-lake-databases-in-azure-synapse-analytics"></a>Savienojuma izveide ar datu ezeru datu bāzēm Azure Synapse Analytics

1. Dodieties uz **Dati** > **Datu avoti**.

1. Atlasiet **Pievienot datu avotu**.

1. Izvēlieties **Azure Synapse Analytics (Priekšskatījuma)** metodi.

1. Sniedziet datu avota **Nosaukmu** un atlasiet **Tālāk**, lai izveidotu datu avotu. 

1. [Izvēlieties pieejamo savienojumu ar vai](connections.md)Azure Synapse Analytics izveidojiet jaunu savienojumu.

1. **Atlasītajā** savienojumā pievienotajā darbvietā izvēlieties ezera datu bāzi Azure Synapse Analytics un atlasiet **Tālāk**.

1. Atlasiet entītijas, kas jāmer no pievienotās datu bāzes. 

1. Pēc izvēles izvēlieties datu entītijas, kurās atļaut datu profilēšanu. 

1. Atlasiet **Saglabāt**, lai lietotu atlasi un sāktu datu uzņemšanu no jaunizveidotās datu avots saistītas ar ezera datu bāzes tabulām programmā Azure Synapse Analytics.
