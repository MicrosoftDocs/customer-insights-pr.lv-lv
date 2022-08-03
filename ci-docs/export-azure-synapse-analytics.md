---
title: Datu eksportēšana uz Azure Synapse Analytics (priekšskatījums)
description: Uzziniet, kā konfigurēt savienojumu ar Azure Synapse Analytics.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: f9c9ee55f2874ae1dcaf82f2ff17ed0fbbb7804d
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196403"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a>Datu eksportēšana uz Azure Synapse Analytics (priekšskatījums)

Azure Synapse ir analīzes pakalpojums, kas paātrina laiku, lai gūtu ieskatu datu noliktavās un lielās datu sistēmās. Jūs varat uzņemt un izmantot Customer Insights datus programmā [Azure Synapse](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Priekšnoteikumi

> [!NOTE]
> Noteikti iestatiet visas **lomu piešķires**, kā aprakstīts.

- Programmā Customer Insights jūsu Azure Active Directory (AD) lietotāja kontam ir jābūt administratora [lomai](permissions.md#assign-roles-and-permissions).

Azure:

- Aktīvs Azure abonements.

- Ja izmantojat jaunu Azure Data Lake Storage Gen2 kontu, [Customer Insights servisa vadītājam ir](connect-service-principal.md) krātuves **Blob datu līdzstrādnieka** atļaujas. Data Lake Storage Gen2 **jābūt** iespējotai [hierarhiskajai nosaukumvietai](/azure/storage/blobs/data-lake-storage-namespace).

- Resursu grupā, kurā Azure Synapse atrodas darbvieta, *pakalpojuma vadītājam* un *Azure AD lietotājam ar administratora atļaujām programmā Customer Insights* ir jāpiešķir vismaz **Reader**[atļaujas](/azure/role-based-access-control/role-assignments-portal).

- Lietotājam *Azure AD ar administratora atļaujām programmā Customer Insights* ir **krātuves Blob datu līdzstrādnieka** Azure Data Lake Storage atļaujas Gen2 kontā, kur dati atrodas un ir saistīti ar darbvietu Azure Synapse. Uzziniet vairāk par [Azure portāla izmantošanas iespēju, lai piešķirtu Azure lomu piekļuvei BLOB un rindas datiem](/azure/storage/common/storage-auth-aad-rbac-portal) un [Krātuves Blob datu līdzdalības atļaujām](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Darbvietas pārvaldītajai identitātei *[Azure Synapse ir](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* krātuves Blob datu līdzstrādnieka **atļaujas** Gen2 kontā, kur dati atrodas un ir saistīti ar darbvietu Azure Data Lake Storage Azure Synapse. Uzziniet vairāk par [Azure portāla izmantošanas iespēju, lai piešķirtu Azure lomu piekļuvei BLOB un rindas datiem](/azure/storage/common/storage-auth-aad-rbac-portal) un [Krātuves Blob datu līdzdalības atļaujām](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Darbvietā Azure Synapse *Customer Insights* pakalpojumu vadītājam ir **piešķirta** Synapse administratora [loma](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="set-up-connection-to-azure-synapse"></a>Savienojuma iestatīšana uz Azure Synapse

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Dodieties uz **Administrators** > **Savienojumi**.

1. Atlasiet **Pievienot savienojumu** un izvēlieties **Azure Synapse Analytics**.

1. Laukā **Parādāmais nosaukums** piešķiriet savienojumam atpazīstamu nosaukumu. Parādāmais nosaukums un nosaukuma veids raksturo šo savienojumu. Ir ieteicams izvēlēties nosaukumu, kas paskaidro savienojuma nolūku.

1. Izvēlieties, kurš var izmantot šo savienojumu. Pēc noklusējuma tie ir tikai administratori. Papildinformāciju skatiet rakstā [Atļaut līdzstrādniekiem izmantot savienojumu eksportam](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Atlasiet vai meklējiet abonementu, kurā vēlaties izmantot Customer Insights datus. Līdzko ir atlasīts abonements, varat arī atlasīt **Darbvieta**, **Krātuves konts** un **Konteiners**.

1. Pārskatiet datu privātumu [un atbilstību](connections.md#data-privacy-and-compliance) un atlasiet **Es piekrītu**.

1. Lai pabeigtu savienošanu, atlasiet **Saglabāt**.

## <a name="configure-an-export"></a>Eksporta konfigurēšana

[!INCLUDE [export-permission-include](includes/export-permission.md)] Lai konfigurētu eksportēšanu, izmantojot koplietojamu savienojumu, programmā Customer Insights ir nepieciešamas vismaz **līdzstrādnieka** atļaujas.

1. Pārejiet uz **Dati** > **Eksportēšana**.

1. Atlasiet **Pievienot eksportēšanu**.

1. Laukā **Savienojums eksportēšanai** izvēlieties savienojumu no Azure Synapse Analytics sadaļas. Ja nav pieejamu savienojumu, sazinieties ar administratoru.

1. Norādiet atpazīstamu eksportēšanas **Parādāmo nosaukumu** un **Datu bāzes nosaukumu**. Eksportēšana izveidos jaunu [Azure Synapse ezeru datu bāzi](/azure/synapse-analytics/database-designer/concepts-lake-database) savienojumā definētajā darbvietā.

1. Atlasiet, uz Azure Synapse Analytics kurām entītijām vēlaties eksportēt.
   > [!NOTE]
   > Datu avoti, kuru pamatā ir [Common Data Model](connect-common-data-model.md) mape, netiek atbalstīti.

1. Atlasiet **Saglabāt**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Lai vaicātu datus, kas eksportēti uz Synapse Analytics, ir nepieciešama **krātuves Blob datu lasītāja** piekļuve mērķa krātuvei eksportēšanas darbvietā.

## <a name="update-an-export"></a>Eksportēšanas atjaunināšana

1. Pārejiet uz **Dati** > **Eksportēšana**.

1. Atlasīt **Rediģēt** atjaunināmajam eksporta vienumam.

   - **Pievienot** vai **Noņemt** entītijas no atlases. Ja entītijas tiek noņemtas no atlases, tās netiek dzēstas no Synapse Analytics datu bāzes. Tomēr turpmākas datu atsvaidzināšanas gadījumā šajā datu bāzē noņemtās entītijas netiks atjauninātas.

   - **Mainot datu bāzes nosaukumu**, tiek izveidota jauna Synapse Analytics datu bāze. Datu bāze ar nosaukumu, kas tika konfigurētsa iepriekš, vairs nesaņems atjauninājumus tālākajos laidienos.

[!INCLUDE [footer-include](includes/footer-banner.md)]
