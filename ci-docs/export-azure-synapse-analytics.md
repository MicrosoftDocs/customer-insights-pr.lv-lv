---
title: Datu eksportēšana uz Azure Synapse Analytics (priekšskatījums)
description: Uzziniet, kā konfigurēt savienojumu ar Azure Synapse Analytics.
ms.date: 06/29/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 60bacb313e0426564310f3c1339bf3b732e17489
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082872"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a>Datu eksportēšana uz Azure Synapse Analytics (priekšskatījums)

Azure Synapse ir analīzes pakalpojums, kas paātrina laiku, lai gūtu ieskatu datu noliktavās un lielās datu sistēmās. Jūs varat uzņemt un izmantot Customer Insights datus programmā [Azure Synapse](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Priekšnosacījumi

Lai konfigurētu savienojumu no Customer Insights uz Azure Synapse, ir jāizpilda tālāk sniegtie priekšnosacījumi.

> [!NOTE]
> Noteikti iestatiet visas **lomu piešķires**, kā aprakstīts.  

## <a name="prerequisites-in-customer-insights"></a>Customer Insights priekšnosacījumi

* Jūsu Azure Active Directory (AD) lietotāja kontam ir **administratora** loma programmā Customer Insights. Uzziniet vairāk par [lietotāju atļauju iestatīšanu](permissions.md#assign-roles-and-permissions).

Azure: 

- Aktīvs Azure abonements.

- Ja izmantojat jaunu Azure Data Lake Storage Gen2 kontu, *Customer Insights servisa vadītājam ir nepieciešamas* krātuves **Blob datu līdzstrādnieka** atļaujas. Uzziniet vairāk par [savienojuma izveidi Azure Data Lake Storage ar Gen2 kontu, izmantojot Azure pakalpojumu principālu programmai Customer Insights](connect-service-principal.md). Data Lake Storage Gen2 **jābūt** iespējotai [hierarhiskajai nosaukumvietai](/azure/storage/blobs/data-lake-storage-namespace).

- Resursu grupā, kurā Azure Synapse atrodas darbvieta, *pakalpojuma vadītājam* un *Azure AD lietotājam ar administratora atļaujām programmā Customer Insights* ir jāpiešķir vismaz **Reader** atļaujas. Papildinformāciju skatiet sadaļā [Azure lomu piešķiršana, izmantojot Azure portālu](/azure/role-based-access-control/role-assignments-portal).

- Lietotājam *Azure AD ar administratora atļaujām programmā Customer Insights ir nepieciešamas* krātuves **Blob datu līdzstrādnieka** Azure Data Lake Storage atļaujas Gen2 kontā, kurā dati atrodas un ir saistīti ar darbvietu Azure Synapse. Uzziniet vairāk par [Azure portāla izmantošanas iespēju, lai piešķirtu Azure lomu piekļuvei BLOB un rindas datiem](/azure/storage/common/storage-auth-aad-rbac-portal) un [Krātuves Blob datu līdzdalības atļaujām](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- *[Azure Synapse darbvietas pārvaldītajai identitātei](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* ir nepieciešamas **Storage Blob datu līdzdalības** atļaujas Azure Data Lake Storage Gen2 kontā, kur atrodas dati un ir saistīti ar Azure Synapse darbvietu. Uzziniet vairāk par [Azure portāla izmantošanas iespēju, lai piešķirtu Azure lomu piekļuvei BLOB un rindas datiem](/azure/storage/common/storage-auth-aad-rbac-portal) un [Krātuves Blob datu līdzdalības atļaujām](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Darbvietā Azure Synapse *customer insights* pakalpojumu direktoram ir nepieciešama **synapse administratora** loma. Papildinformāciju skatiet rakstā [Kā iestatīt piekļuves vadīklu jūsu Synapse darbvietai](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="set-up-the-connection-and-export-to-azure-synapse"></a>Savienojuma izveide un eksportēšana Azure Synapse

### <a name="configure-a-connection"></a>Savienojuma konfigurēšana

Lai izveidotu savienojumu, pakalpojuma vadītājam un lietotāja kontam programmā Customer Insights ir nepieciešamas **lasītāja** atļaujas resursu grupā *,* kurā atrodas Synapse Analytics darbvieta. Turklāt pakalpojuma vadītājam un synapse Analytics darbvietas lietotājam ir nepieciešamas **Synapse administratora** atļaujas. 

1. Dodieties uz **Administrators** > **Savienojumi**.

1. Atlasiet **Pievienot savienojumu** un **Azure Synapse Analytics** izvēlieties vai atlasiet **elementu Iestatīt**, **Azure Synapse Analytics** lai konfigurētu savienojumu.

1. Laukā Parādāmais nosaukums piešķiriet savienojumam atpazīstamu nosaukumu. Parādāmais nosaukums un nosaukuma veids raksturo šo savienojumu. Ir ieteicams izvēlēties nosaukumu, kas paskaidro savienojuma nolūku.

1. Izvēlieties, kurš var izmantot šo savienojumu. Ja nesāksit nekādas darbības, noklusējums būs Administratori. Papildinformāciju skatiet rakstā [Atļaut līdzstrādniekiem izmantot savienojumu eksportam](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Atlasiet vai meklējiet abonementu, kurā vēlaties izmantot Customer Insights datus. Līdzko ir atlasīts abonements, varat arī atlasīt **Darbvieta**, **Krātuves konts** un **Konteiners**.

1. Lai saglabātu savienojumu, atlasiet **Saglabāt**.

### <a name="configure-an-export"></a>Eksporta konfigurēšana

Šo eksportu varat konfigurēt, ja jums ir piekļuve šā veida pieslēgumam. Lai konfigurētu eksportēšanu, izmantojot koplietojamu savienojumu, programmā Customer Insights ir nepieciešamas vismaz **līdzstrādnieka** atļaujas. Papildinformāciju skatiet rakstā [atļaujas, kas nepieciešamas eksporta konfigurēšanai](export-destinations.md#set-up-a-new-export).

1. Pārejiet uz **Dati** > **Eksportēšana**.

1. Lai izveidotu jaunu eksportu, atlasiet **Pievienot eksportu**.

1. Laukā **Savienojums eksportēšanai** izvēlieties savienojumu no **Azure Synapse Analytics** sadaļas. Ja šis sadaļas nosaukums nav redzams, šāda veida [savienojumi](connections.md) jums nav pieejami.

1. Norādiet atpazīstamu eksportēšanas **Parādāmo nosaukumu** un **Datu bāzes nosaukumu**. Eksportēšana izveidos jaunu [Azure Synapse ezera datu bāzi](/azure/synapse-analytics/database-designer/concepts-lake-database) darbvietā, kas definēta savienojumā.

1. Atlasiet, uz Azure Synapse Analytics kurām entītijām vēlaties eksportēt.
   > [!NOTE]
   > Datu avoti, kuru pamatā ir [Common Data Model](connect-common-data-model.md) mape, netiek atbalstīti.

1. Atlasiet vienumu **Saglabāt**.

Eksporta saglabāšana automātiski nepalaiž eksportu.

Eksports tiek palaists ar katru [plānoto atsvaidzināšanu](system.md#schedule-tab). Varat arī [eksportēt datus pēc pieprasījuma](export-destinations.md#run-exports-on-demand).

Lai vaicātu datus, kas eksportēti uz Synapse Analytics, ir nepieciešama **krātuves Blob datu lasītāja** piekļuve mērķa krātuvei eksportēšanas darbvietā. 

### <a name="update-an-export"></a>Eksportēšanas atjaunināšana

1. Pārejiet uz **Dati** > **Eksportēšana**.

1. Atlasīt **Rediģēt** atjaunināmajam eksporta vienumam.

   - **Pievienot** vai **Noņemt** entītijas no atlases. Ja entītijas tiek noņemtas no atlases, tās netiek dzēstas no Synapse Analytics datu bāzes. Tomēr turpmākas datu atsvaidzināšanas gadījumā šajā datu bāzē noņemtās entītijas netiks atjauninātas.

   - **Mainot datu bāzes nosaukumu**, tiek izveidota jauna Synapse Analytics datu bāze. Datu bāze ar nosaukumu, kas tika konfigurētsa iepriekš, vairs nesaņems atjauninājumus tālākajos laidienos.
