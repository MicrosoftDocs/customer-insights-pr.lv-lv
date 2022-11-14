---
title: Datu avots pievienošana Azure Synapse (priekšskatījums)
description: Izmantojiet datu bāzi Azure Synapse kā datu avots programmā Dynamics 365 Customer Insights.
ms.date: 07/26/2022
ms.reviewer: v-wendysmith
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 675fd03c44a7a7a492b111895d79c2e77f93a5b5
ms.sourcegitcommit: 4ba74816ebfa46412c64c40a61e1f31c4ccc40f2
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 11/03/2022
ms.locfileid: "9738165"
---
# <a name="connect-an-azure-synapse-analytics-data-source-preview"></a>Datu avots pievienošana Azure Synapse Analytics (priekšskatījums)

Azure Synapse Analytics ir uzņēmuma analīzes pakalpojums, kas paātrina laiku līdz ieskatiem datu noliktavās un lielo datu sistēmās. Azure Synapse Analytics apvieno labākās SQL tehnoloģijas, ko izmanto uzņēmuma datu noliktavā, Spark tehnoloģijas, ko izmanto lielajiem datiem, datu pārlūku žurnālu un laikrindu analīzei, konveijerus datu integrācijai un ETL/ELT, kā arī dziļo integrāciju ar citiem Azure pakalpojumiem, piemēram Power BI, Cosmos DB un AzureML.

Papildinformāciju skatiet sadaļā [Azure Synapse Pārskats](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Priekšnoteikumi

> [!NOTE]
> Synapse Workspaces, kurās ir [iespējots](/azure/synapse-analytics/security/synapse-workspace-ip-firewall) ugunsmūris, pašlaik netiek atbalstītas.
> [!IMPORTANT]
> Noteikti iestatiet visas **lomu piešķires**, kā aprakstīts.  

**Programmā Customer Insights**:

* Jums ir administratora **loma** programmā Customer Insights. Papildinformāciju par [lietotāju atļaujām skatiet rakstā Customer Insights](permissions.md#add-users).

**Pakalpojumā Azure**:

- Aktīvs Azure abonements.

- Ja izmantojat jaunu Azure Data Lake Storage Gen2 kontu, *Customer Insights* pakalpojuma vadītājam "Dynamics 365 AI for Customer Insights" ir nepieciešamas **krātuves Blob datu līdzstrādnieka** atļaujas. Uzziniet vairāk par [saziņu ar Azure Data Lake Storage pakalpojumu vadītāju, lai iegūtu Customer Insights](connect-service-principal.md). Data Lake Storage Gen2 **jābūt** iespējotai [hierarhiskajai nosaukumvietai](/azure/storage/blobs/data-lake-storage-namespace).

- Resursu grupā, kurā Azure Synapse atrodas darbvieta, *pakalpojuma vadītājam* "Dynamics 365 AI for Customer Insights" un *Customer Insights* lietotājam ir jāpiešķir vismaz **Reader** atļaujas. Papildinformāciju skatiet sadaļā [Azure lomu piešķiršana, izmantojot Azure portālu](/azure/role-based-access-control/role-assignments-portal).

- *Lietotājam* ir nepieciešamas **Blob datu līdzdalībā glabātavas** atļaujas Azure Data Lake Storage Gen2 kontā, kur šie dati atrodas un ir saistīti ar šo Azure Synapse darbvietu. Uzziniet vairāk par [Azure portāla izmantošanas iespēju, lai piešķirtu Azure lomu piekļuvei BLOB un rindas datiem](/azure/storage/common/storage-auth-aad-rbac-portal) un [Krātuves Blob datu līdzdalības atļaujām](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- *[Azure Synapse darbvietas pārvaldītajai identitātei](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* ir nepieciešamas **Storage Blob datu līdzdalības** atļaujas Azure Data Lake Storage Gen2 kontā, kur atrodas dati un ir saistīti ar Azure Synapse darbvietu. Uzziniet vairāk par [Azure portāla izmantošanas iespēju, lai piešķirtu Azure lomu piekļuvei BLOB un rindas datiem](/azure/storage/common/storage-auth-aad-rbac-portal) un [Krātuves Blob datu līdzdalības atļaujām](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Darbvietā Azure Synapse *Customer Insights* pakalpojuma vadītājam "Dynamics 365 AI for Customer Insights" ir jāpiešķir **Synapse administratora** loma. Lietotājam **ir** nepieciešama vismaz **Synapse līdzstrādnieka** loma, kas piešķirta darbvietai. Papildinformāciju skatiet rakstā [Kā iestatīt piekļuves vadīklu jūsu Synapse darbvietai](/azure/synapse-analytics/security/how-to-set-up-access-control).

- Ja jūsu Customer Insights vide saglabā datus jūsu [vidē Azure Data Lake Storage](own-data-lake-storage.md), lietotājam, kurš iestata savienojumu Azure Synapse Analytics, ir nepieciešama vismaz iebūvētā **lasītāja** loma Data Lake krātuves kontā. Papildinformāciju skatiet sadaļā [Azure lomu piešķiršana, izmantojot Azure portālu](/azure/role-based-access-control/role-assignments-portal).

## <a name="connect-to-the-data-lake-database-in-azure-synapse-analytics"></a>Izveidojiet savienojumu ar datu ezera datu bāzi Azure Synapse Analytics

1. Dodieties uz **Dati** > **Datu avoti**.

1. Atlasiet **Pievienot datu avotu**.

1. Izvēlieties **Azure Synapse Analytics (priekšskatījuma)** metodi.

   :::image type="content" source="media/data_sources_synapse.png" alt-text="Dialoglodziņš, lai izveidotu savienojumu ar Synapse Analytics datiem":::
  
1. Ievadiet **datu avots nosaukumu** un neobligātu **aprakstu**.

1. Izvēlieties [pieejamo savienojumu](connections.md)Azure Synapse Analytics vai [izveidojiet jaunu](export-azure-synapse-analytics.md#set-up-connection-to-azure-synapse).

1. Izvēlieties **Datu bāzi no darbvietas, kas savienota atlasītajā** savienojumā, un atlasiet Azure Synapse Analytics Tālāk **·**. Pašlaik mēs atbalstām tikai datu bāzes tipa *ezera datu bāzi*.

1. Atlasiet entītijas, kuras vēlaties uzņemt no pievienotās datu bāzes, un atlasiet **Tālāk**.

1. Ja vēlaties, izvēlieties datu elementus, kuros atļaut datu profilēšanu.

1. Atlasiet **Saglabāt**, lai lietotu atlasi un sāktu datu uzņemšanu no jaunizveidotās datu avots, kas saistīta ar Lake datu bāzes tabulām sadaļā Azure Synapse Analytics. Tiek **atvērta lapa Datu avoti**, kurā jaunā datu avots tiek rādīta statusā **Atsvaidzināt.**

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Datu ielāde var aizņemt laiku. Pēc veiksmīgas atsvaidzināšanas uzņemtos datus var pārskatīt [**no lapas Entītijas**](entities.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
