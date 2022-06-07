---
title: Customer Insights datu eksportēšana uz Azure Synapse Analytics
description: Uzziniet, kā konfigurēt savienojumu ar Azure Synapse Analytics.
ms.date: 04/11/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 772fe0978362ccd829077a8133e2a3e74043f3f8
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741512"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a>Eksportēt datus uz Azure Synapse Analytics (Priekšskatījums)

Azure Synapse ir analīzes pakalpojums, kas paātrina laiku, lai gūtu ieskatu datu noliktavās un lielās datu sistēmās. Jūs varat uzņemt un izmantot Customer Insights datus programmā [Azure Synapse](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Priekšnosacījumi

Lai konfigurētu savienojumu no Customer Insights uz Azure Synapse, ir jāizpilda tālāk sniegtie priekšnosacījumi.

> [!NOTE]
> Noteikti iestatiet visas **lomu piešķires**, kā aprakstīts.  

## <a name="prerequisites-in-customer-insights"></a>Customer Insights priekšnosacījumi

* Jūsu Azure Active Directory (AD) lietotāja kontam **ir administratora** loma customer insights. Uzziniet vairāk par [lietotāju atļauju iestatīšanu](permissions.md#assign-roles-and-permissions).

Azure: 

- Aktīvs Azure abonements.

- Ja izmantojat jaunu Azure Data Lake Storage Gen2 kontu, *Customer Insights pakalpojumu vadītājam ir nepieciešamas* Krātuves **BLOB datu līdzstrādnieka** atļaujas. Uzziniet vairāk par [savienojumu ar Azure Data Lake Storage Gen2 kontu, izmantojot Azure pakalpojumu vadītāju customer insights](connect-service-principal.md). Data Lake Storage Gen2 **jābūt** iespējotai [hierarhiskajai nosaukumvietai](/azure/storage/blobs/data-lake-storage-namespace).

- Resursu grupā, kurā Azure Synapse atrodas darbvieta, *pakalpojuma vadītājam* un *Azure AD lietotājam ar administratora atļaujām customer insights* ir jāpiešķir vismaz **Reader** atļaujas. Papildinformāciju skatiet sadaļā [Azure lomu piešķiršana, izmantojot Azure portālu](/azure/role-based-access-control/role-assignments-portal).

- Lietotājam *Azure AD ar administratora atļaujām customer insights ir nepieciešamas* Krātuves **BLOB** datu līdzstrādnieka Azure Data Lake Storage atļaujas Gen2 kontā, kurā dati atrodas un ir saistīti ar darbvietu Azure Synapse. Uzziniet vairāk par [Azure portāla izmantošanas iespēju, lai piešķirtu Azure lomu piekļuvei BLOB un rindas datiem](/azure/storage/common/storage-auth-aad-rbac-portal) un [Krātuves Blob datu līdzdalības atļaujām](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- *[Azure Synapse darbvietas pārvaldītajai identitātei](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* ir nepieciešamas **Storage Blob datu līdzdalības** atļaujas Azure Data Lake Storage Gen2 kontā, kur atrodas dati un ir saistīti ar Azure Synapse darbvietu. Uzziniet vairāk par [Azure portāla izmantošanas iespēju, lai piešķirtu Azure lomu piekļuvei BLOB un rindas datiem](/azure/storage/common/storage-auth-aad-rbac-portal) un [Krātuves Blob datu līdzdalības atļaujām](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Darbvietā Azure Synapse *Customer Insights* pakalpojumu vadītājam ir **jāpiešķir Synapse administratora** loma. Papildinformāciju skatiet rakstā [Kā iestatīt piekļuves vadīklu jūsu Synapse darbvietai](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="set-up-the-connection-and-export-to-azure-synapse"></a>Savienojuma izveide un eksportēšana Azure Synapse

### <a name="configure-a-connection"></a>Savienojuma konfigurēšana

Lai izveidotu savienojumu, pakalpojumu vadītājam un lietotāja kontam Customer Insights ir nepieciešamas **Reader** atļaujas *resursu grupā*, kurā atrodas Synapse Analytics darbvieta. Turklāt pakalpojuma vadītājam un lietotājam Synapse Analytics darbvietā ir nepieciešamas **Synapse administratora** atļaujas. 

1. Dodieties uz **Administrators** > **Savienojumi**.

1. Atlasiet **Pievienot savienojumu** un izvēlieties **Azure Synapse Analytics** vai atlasiet **elementa iestatījumu** Iestatīt, **Azure Synapse Analytics** lai konfigurētu savienojumu.

1. Laukā Parādāmais nosaukums piešķiriet savienojumam atpazīstamu nosaukumu. Parādāmais nosaukums un nosaukuma veids raksturo šo savienojumu. Ir ieteicams izvēlēties nosaukumu, kas paskaidro savienojuma nolūku.

1. Izvēlieties, kurš var izmantot šo savienojumu. Ja nesāksit nekādas darbības, noklusējums būs Administratori. Papildinformāciju skatiet rakstā [Atļaut līdzstrādniekiem izmantot savienojumu eksportam](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Atlasiet vai meklējiet abonementu, kurā vēlaties izmantot Customer Insights datus. Līdzko ir atlasīts abonements, varat arī atlasīt **Darbvieta**, **Krātuves konts** un **Konteiners**.

1. Lai saglabātu savienojumu, atlasiet **Saglabāt**.

### <a name="configure-an-export"></a>Eksporta konfigurēšana

Šo eksportu varat konfigurēt, ja jums ir piekļuve šā veida pieslēgumam. Lai konfigurētu eksportēšanu ar koplietojamu savienojumu, programmā Customer Insights ir nepieciešamas vismaz **līdzstrādnieka** atļaujas. Papildinformāciju skatiet rakstā [atļaujas, kas nepieciešamas eksporta konfigurēšanai](export-destinations.md#set-up-a-new-export).

1. Pārejiet uz **Dati** > **Eksportēšana**.

1. Lai izveidotu jaunu eksportu, atlasiet **Pievienot eksportu**.

1. Laukā **Savienojums eksportam** izvēlieties savienojumu no **Azure Synapse Analytics** sadaļas. Ja šis sadaļas nosaukums nav redzams, šāda veida [savienojumi](connections.md) jums nav pieejami.

1. Norādiet atpazīstamu eksportēšanas **Parādāmo nosaukumu** un **Datu bāzes nosaukumu**.

1. Atlasiet, uz kurām entītijām vēlaties eksportēt Azure Synapse Analytics.
   > [!NOTE]
   > Datu avoti, kuru pamatā ir [Common Data Model](connect-common-data-model.md) mape, netiek atbalstīti.

2. Atlasiet vienumu **Saglabāt**.

Eksporta saglabāšana automātiski nepalaiž eksportu.

Eksports tiek palaists ar katru [plānoto atsvaidzināšanu](system.md#schedule-tab). Varat arī [eksportēt datus pēc pieprasījuma](export-destinations.md#run-exports-on-demand).

Lai veiktu vaicājumu datus, kas tika eksportēti uz Synapse Analytics, jums ir nepieciešama **krātuves BLOB datu lasītāja** piekļuve mērķa krātuvei eksporta darbvietā. 

### <a name="update-an-export"></a>Eksportēšanas atjaunināšana

1. Pārejiet uz **Dati** > **Eksportēšana**.

1. Atlasīt **Rediģēt** atjaunināmajam eksporta vienumam.

   - **Pievienot** vai **Noņemt** entītijas no atlases. Ja entītijas tiek noņemtas no atlases, tās netiek dzēstas no Synapse Analytics datu bāzes. Tomēr turpmākas datu atsvaidzināšanas gadījumā šajā datu bāzē noņemtās entītijas netiks atjauninātas.

   - **Mainot datu bāzes nosaukumu**, tiek izveidota jauna Synapse Analytics datu bāze. Datu bāze ar nosaukumu, kas tika konfigurētsa iepriekš, vairs nesaņems atjauninājumus tālākajos laidienos.