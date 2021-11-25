---
title: Izmantojiet datu avotus datu uzņemšanai
description: Uzziniet, kā importēt datus no dažādiem avotiem.
ms.date: 11/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 27cbd0346b1219c7812f4b90327dd27b645c2b8e
ms.sourcegitcommit: 834651b933b1e50e7557d44f926a3fb757c1f83a
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 11/02/2021
ms.locfileid: "7732164"
---
# <a name="data-sources-overview"></a>Datu avotu pārskats

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Auditorijas ieskatu iespējas Dynamics 365 Customer Insights ir savienotas ar datiem no plašas avotu kopas. Pieslēgšanos datu avotam bieži vien dēvē par *datu uzņemšanas* procesu. Pēc datu uzņemšanas varat tos [apvienot](data-unification.md) un veikt ar tiem darbības.

## <a name="add-a-data-source"></a>Pievienot datu avotu

Skatiet detalizētus rakstus, kā pievienot datu avotu atkarībā no izvēlētās opcijas.

Datu avotu varat pievienot trīs galvenajos veidos:

- [Izmantojot daudzos Power Query savienotājus](connect-power-query.md)
- [No Common Data Model mapes](connect-common-data-model.md)
- [No sava Microsoft Dataverse ezera](connect-dataverse-managed-lake.md)

## <a name="add-data-from-on-premises-data-sources"></a>Datu pievienošana no lokālajiem datu avotiem

Datu uzzīšana no lokāls datu avotiem auditorijas ieskatos tiek atbalstīta, pamatojoties uz Microsoft Power Platform datu plūsmām. Datu plūsmas var iespējot customer insights, [iestatot vidi, norādot Microsoft Dataverse vides](create-environment.md) URL.

Datu avoti, kas izveidoti pēc Dataverse vides saistīšanas ar Customer Insights, [pēc noklusējuma izmantos Power Platform datu plūsmas.](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) Datu plūsmas atbalsta lokālo savienojamību, izmantojot datu vārtejas. Noņemiet un atkārtoti izveidojiet datu avotus, kas pastāvēja pirms Dataverse vides saisti ar [lokāls datu vārteju izmantošanu](/data-integration/gateway/service-gateway-app).

Būs redzamas datu vārtejas no esošas Power BI vai Power Apps vides, un jūs varat atkārtoti izmantot programmā Customer Insights. Datu avotu lapā ir redzamas saites, lai dotos uz Microsoft Power Platform vidi, kurā var skatīt un konfigurēt lokāls datu vārtejas.

## <a name="review-ingested-data"></a>Uzņemto datu pārskatīšana

Jūs redzēsit katra uzņemtā datu avota nosaukumu, tā statusu un pēdējo reizi, kad dati tika atsvaidzināti no šī avota. Datu avotu sarakstu var kārtot pēc katras kolonnas.

> [!div class="mx-imgBorder"]
> ![Pievienotie datu avoti.](media/configure-data-datasource-added.png "Pievienotie datu avoti")

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

Datu ielāde var aizņemt laiku. Pēc veiksmīgas atsvaidzināšanas uzņemtos datus var pārskatīt no lapas **Entītijas**. Papildinformāciju skatiet rakstā [Entītijas](entities.md).

## <a name="refresh-a-data-source"></a>Atsvaidzināt datu avotu

Datu avotus var atsvaidzināt pēc automātiska grafika vai atsvaidzināt manuāli pēc pieprasījuma. 

Apmeklējiet **Administrators** > **Sistēma** > [**Grafiks**](system.md#schedule-tab), lai konfigurētu visu jūsu uzņemto datu avotu plānoto atsvaidzināšanu.

Lai atsvaidzinātu datu avotu pēc pieprasījuma, veiciet šīs darbības:

1. Sadaļā Auditorijas ieskati skatiet **Dati** > **Datu avoti**.

2. Nolaižamajā izvēlnes sarakstā atlasiet vertikālās līknes blakus datu avotam, kuru vēlaties atsvaidzināt un atlasiet **Atsvaidzināt**.

3. Datu avots tagad tiek iespējots manuālai atsvaidzināšanai. Datu avota atsvaidzināšana atjauninās gan entitījas shēmu, gan datus visām entitījām, kuras ir norādītas datu avotā.

4. Atlasiet **Pārtraukt atsvaidzināšanu**, ja vēlaties atcelt esošu atsvaidzināšanu, un datu avots atgriezīsies pēdējās atsvaidzināšanas statusā.

## <a name="delete-a-data-source"></a>Datu avota dzēšana

1. Sadaļā Auditorijas ieskati skatiet **Dati** > **Datu avoti**.

2. Nolaižamajā izvēlnē atlasiet vertikālās līknes blakus datu avotam, kuru vēlaties noņemt un atlasiet **Dzēst**.

3. Apstipriniet dzēšanu.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
