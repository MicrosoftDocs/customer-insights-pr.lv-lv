---
title: Izmantojiet datu avotus datu uzņemšanai
description: Uzziniet, kā importēt datus no dažādiem avotiem.
ms.date: 12/06/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 6846c73cb156aaa049e2656c8e327bcba1f73abc
ms.sourcegitcommit: 11b343f6622665251ab84ae39ebcd91fa1c928ca
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 12/08/2021
ms.locfileid: "7900388"
---
# <a name="data-sources-overview"></a>Datu avotu pārskats

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Auditorijas ieskatus Dynamics 365 Customer Insights var savienot ar datiem no plašas avotu kopas. Pieslēgšanos datu avotam bieži vien dēvē par *datu uzņemšanas* procesu. Pēc datu uzņemšanas varat tos [apvienot](data-unification.md) un veikt ar tiem darbības.

## <a name="add-a-data-source"></a>Pievienot datu avotu

Skatiet detalizētus rakstus, kā pievienot datu avots atkarībā no izvēlētās opcijas.

Varat pievienot šādus datu avotus:

- [Power Query savienotāji](connect-power-query.md)
- [Common Data Model](connect-common-data-model.md)
- [Microsoft Dataverse ezers](connect-dataverse-managed-lake.md)

> [!NOTE]
> Ja izmantojat izmēģinājuma versiju, importēšanas metožu sadaļā ir iekļauta **Customer Insights datu bibliotēkas** opcija. Izvēlieties šo opciju, lai atlasītu datu kopas paraugu, kas pieejams dažādām nozarēm. Papildinformāciju skatiet [Dynamics 365 Customer Insights izmēģinājumversijā](../trial-signup.md).

## <a name="add-data-from-on-premises-data-sources"></a>Datu pievienošana no lokālajiem datu avotiem

Datu pievienošana no lokālajiem datu avotiem auditorijas ieskatos tiek atbalstīta, balstoties uz Microsoft Power Platform datu plūsmām. Datu plūsmas programmā Customer Insights var [iespējot, Microsoft Dataverse iestatot vidi, norādot vides](create-environment.md) URL.

Datu avoti, kas izveidoti pēc vides saistīšanas Dataverse ar Customer Insights, pēc noklusējuma izmanto [Power Platform datu](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) plūsmas. Datu plūsmas atbalsta lokālo savienojamību, izmantojot datu vārtejas. Varat noņemt un atkārtoti izveidot datu avotus, kas pastāvēja pirms Dataverse vides saisti, [izmantojot lokāls datu vārtejas](/data-integration/gateway/service-gateway-app).

Datu vārtejas no esošās Power BI vai Power Apps vides būs redzama, un to varat atkārtoti izmantot risinājumā Customer Insights. Datu avotu lapā ir redzamas saites, kas ļauj pāriet uz Microsoft Power Platform vidi, kurā varat skatīt un konfigurēt lokālās datu vārtejas.

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
