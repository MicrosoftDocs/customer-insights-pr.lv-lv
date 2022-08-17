---
title: Azure Synapse datu avots pievienošana (priekšskatījums)
description: Izmantojiet datu bāzi Azure Synapse kā datu avots iekšā Dynamics 365 Customer Insights.
ms.date: 07/26/2022
ms.reviewer: v-wendysmith
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 7bc0c3614e6dd39fbd65ae098ed679d95d09de9d
ms.sourcegitcommit: 086f75136132d561cd78a4c2cb1e1933e2301f32
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 08/11/2022
ms.locfileid: "9259807"
---
# <a name="connect-an-azure-synapse-analytics-data-source-preview"></a>Azure Synapse Analytics datu avots pievienošana (priekšskatījums)

Azure Synapse Analytics ir uzņēmuma analīzes pakalpojums, kas paātrina laiku līdz ieskatiem datu noliktavās un lielo datu sistēmās. Azure Synapse Analytics apvieno labākās SQL tehnoloģijas, ko izmanto uzņēmuma datu bāzē, Spark tehnoloģijas, ko izmanto lielajiem datiem, Data Explorer žurnālu un laikrindu analīzei, Konveijerus datu integrācijai un ETL/ELT, kā arī dziļu integrāciju ar citiem Azure pakalpojumiem, piemēram Power BI,, Cosmos DB, un AzureML.

Papildinformāciju skatiet pārskatā [Azure Synapse](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Priekšnoteikumi

> [!NOTE]
> Synapse Darbvietas, kurām ir [iespējots](/azure/synapse-analytics/security/synapse-workspace-ip-firewall) ugunsmūris, pašlaik netiek atbalstītas.
> [!IMPORTANT]
> Noteikti iestatiet visas **lomu piešķires**, kā aprakstīts.  

**Programmā Customer Insights**:

* Jums ir **administratora** loma programmā Customer Insights. Papildinformāciju par [lietotāju atļaujām skatiet sadaļā Customer Insights](permissions.md#add-users).

**In Azure**:

- Aktīvs Azure abonements.

- Ja izmantojat jaunu Azure Data Lake Storage Gen2 kontu, Customer Insights *pakalpojuma vadītājam,* kas ir "Dynamics 365 AI for Customer Insights", ir nepieciešamas **krātuves Blob datu līdzstrādnieka** atļaujas. Uzziniet vairāk par [savienojuma izveidi Azure Data Lake Storage ar pakalpojumu sniedzēju programmā Customer Insights](connect-service-principal.md). Data Lake Storage Gen2 **jābūt** iespējotai [hierarhiskajai nosaukumvietai](/azure/storage/blobs/data-lake-storage-namespace).

- Resursu grupā, kurā Azure Synapse atrodas darbvieta, *ir jāpiešķir vismaz* Lasītāja *atļaujas, kas* ir "Dynamics 365 AI for Customer Insights", un **Customer Insights** lietotājam. Papildinformāciju skatiet sadaļā [Azure lomu piešķiršana, izmantojot Azure portālu](/azure/role-based-access-control/role-assignments-portal).

- *Lietotājam* ir nepieciešamas **Blob datu līdzdalībā glabātavas** atļaujas Azure Data Lake Storage Gen2 kontā, kur šie dati atrodas un ir saistīti ar šo Azure Synapse darbvietu. Uzziniet vairāk par [Azure portāla izmantošanas iespēju, lai piešķirtu Azure lomu piekļuvei BLOB un rindas datiem](/azure/storage/common/storage-auth-aad-rbac-portal) un [Krātuves Blob datu līdzdalības atļaujām](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- *[Azure Synapse darbvietas pārvaldītajai identitātei](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* ir nepieciešamas **Storage Blob datu līdzdalības** atļaujas Azure Data Lake Storage Gen2 kontā, kur atrodas dati un ir saistīti ar Azure Synapse darbvietu. Uzziniet vairāk par [Azure portāla izmantošanas iespēju, lai piešķirtu Azure lomu piekļuvei BLOB un rindas datiem](/azure/storage/common/storage-auth-aad-rbac-portal) un [Krātuves Blob datu līdzdalības atļaujām](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Darbvietā Azure Synapse customer insights *pakalpojuma vadītājam,* kas ir "Dynamics 365 AI for Customer Insights", ir jāpiešķir **Synapse administratora** loma. Papildinformāciju skatiet rakstā [Kā iestatīt piekļuves vadīklu jūsu Synapse darbvietai](/azure/synapse-analytics/security/how-to-set-up-access-control).

- Ja jūsu Customer Insights vidē dati [tiek glabāti atsevišķi Azure Data Lake Storage](own-data-lake-storage.md), lietotājam, kurš iestata savienojumu, Azure Synapse Analytics ir nepieciešama vismaz iebūvētā **lasītāja** loma Data Lake Krātuves kontā. Papildinformāciju skatiet sadaļā [Azure lomu piešķiršana, izmantojot Azure portālu](/azure/role-based-access-control/role-assignments-portal).

## <a name="connect-to-the-data-lake-database-in-azure-synapse-analytics"></a>Savienojuma izveide ar datu ezeru datu bāzi Azure Synapse Analytics

1. Dodieties uz **Dati** > **Datu avoti**.

1. Atlasiet **Pievienot datu avotu**.

1. **Azure Synapse Analytics Izvēlieties (priekšskatījuma)** metodi.

   :::image type="content" source="media/data_sources_synapse.png" alt-text="Dialoglodziņš savienojuma izveidei ar Synapse Analytics datiem":::
  
1. **Ievadiet datu avots nosaukumu** un neobligātu **aprakstu**.

1. [Izvēlieties pieejamo savienojumu ar jaunu savienojumu](connections.md)Azure Synapse Analytics vai [izveidojiet to](export-azure-synapse-analytics.md#set-up-connection-to-azure-synapse).

1. **Izvēlieties datu bāzi** no darbvietas, kas savienota ar atlasīto Azure Synapse Analytics savienojumu, un atlasiet **Tālāk**. Pašlaik mēs atbalstām tikai datu bāzes tipa *ezera datu bāzi*.

1. Atlasiet entītijas, kuras jāuzņem no pievienotās datu bāzes, un atlasiet **Tālāk**.

1. Pēc izvēles izvēlieties datu elementus, kuros atļaut datu profilēšanu.

1. Atlasiet **Saglabāt**, lai lietotu atlasi, un sāciet datu uzņemšanu no jaunizveidotās datu avots, kas saistītas ar ezera datu bāzes tabulām.Azure Synapse Analytics Tiek **atvērta lapa Datu avoti**, kurā redzams jaunais datu avots sadaļā **Atsvaidzināšanas** statuss.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Datu ielāde var aizņemt laiku. Pēc veiksmīgas atsvaidzināšanas pieņemtos datus var pārskatīt lapā [**Entītijas**](entities.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
