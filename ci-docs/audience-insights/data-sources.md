---
title: Izmantojiet datu avotus datu uzņemšanai
description: Uzziniet, kā importēt datus no dažādiem avotiem.
ms.date: 03/18/2022
ms.subservice: audience-insights
ms.topic: overview
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: 9cf97c3e30d7501ba1f188a0e25a1a103299aa7f
ms.sourcegitcommit: a8e99cf8b23ccc00d76c1dee22afd808a160a5c8
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 03/22/2022
ms.locfileid: "8464083"
---
# <a name="data-sources-overview"></a>Datu avotu pārskats



Auditorijas ieskatus Dynamics 365 Customer Insights var savienot ar datiem no plašas avotu kopas. Pieslēgšanos datu avotam bieži vien dēvē par *datu uzņemšanas* procesu. Pēc datu uzņemšanas varat tos [apvienot](data-unification.md) un veikt ar tiem darbības.

## <a name="add-a-data-source"></a>Pievienot datu avotu

Skatiet detalizētus rakstus, lai uzzinātu, kā pievienot datu avots atkarībā no izvēlētās opcijas.

Varat pievienot šādus datu avotus:

- [Caur desmitiem savienotāju Power Query](connect-power-query.md)
- [No Common Data Model mapes](connect-common-data-model.md)
- [No sava Microsoft Dataverse ezera](connect-dataverse-managed-lake.md)
- [Azure Synapse Analytics No datu bāzes](connect-synapse.md)

> [!NOTE]
> Ja izmantojat izmēģinājuma versiju, importēšanas metožu sadaļā ir **iekļauta opcija Customer Insights datu bibliotēkas** opcija. Izvēlieties šo opciju, lai atlasītu dažādām nozarēm pieejamo datu kopas paraugu. Papildinformāciju skatiet sadaļā [Dynamics 365 Customer Insights Izmēģinājumversija](../trial-signup.md).

## <a name="add-data-from-on-premises-data-sources"></a>Datu pievienošana no lokālajiem datu avotiem

Datu pievienošana no lokālajiem datu avotiem auditorijas ieskatos tiek atbalstīta, balstoties uz Microsoft Power Platform datu plūsmām. Datu plūsmas programmā Customer Insights var iespējot, iestatot vidi, [norādot Microsoft Dataverse vides URL](create-environment.md).

Datu avoti, kas izveidoti pēc vides saistīšanas Dataverse ar Customer Insights, pēc noklusējuma izmanto [Power Platform datu plūsmas](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365). Datu plūsmas atbalsta lokālo savienojamību, izmantojot datu vārtejas. Varat noņemt un atkārtoti izveidot datu avotus, kas pastāvēja pirms vides saistīšanas Dataverse, [izmantojot lokāls datu vārtejas](/data-integration/gateway/service-gateway-app).

Datu vārtejas no esošās Power BI vai Power Apps vides būs redzama, un to varat atkārtoti izmantot risinājumā Customer Insights. Datu avotu lapā ir redzamas saites, kas ļauj pāriet uz Microsoft Power Platform vidi, kurā varat skatīt un konfigurēt lokālās datu vārtejas.

> [!IMPORTANT]
> Pārliecinieties, vai vārtejas ir atjauninātas uz jaunāko versiju. Varat instalēt atjauninājumu un pārkonfigurēt vārteju no uzvednes, kas tiek parādīta vārtejas ekrānā tieši, vai [lejupielādēt jaunāko versiju](https://powerapps.microsoft.com/downloads/). Ja neizmantojat jaunāko vārtejas versiju, datu plūsmas atsvaidzināšana neizdodas ar kļūdu ziņojumiem, piemēram **, Atslēgvārds netiek atbalstīts: konfigurācijas rekvizīti. Parametra nosaukums: atslēgvārds**.

## <a name="review-ingested-data"></a>Uzņemto datu pārskatīšana
Ja jūsu vidē ir Power Platform datu plūsmas, **lapā Datu avoti** ir uzskaitītas trīs sadaļas: 
- **Koplietots**: datu avoti, kurus var pārvaldīt visi Customer Insights administratori. Power BI datu plūsmas, savs krātuves konts un pievienošana pārvaldītam datu ezeram Dataverse ir koplietojamu datu avotu piemēri.
- **Pārvalda es**: Power Platform datu plūsmas, kas izveidotas, un tās var pārvaldīt tikai jūs. Citi Customer Insights administratori var skatīt tikai šīs datu plūsmas, bet ne rediģēt, atsvaidzināt vai dzēst tās.
- **Pārvalda citi**: Power Platform datu plūsmas, ko izveidojuši citi administratori. Tos var apskatīt tikai. Tajā ir norādīts datu plūsmas īpašnieks, ar kuru sazināties, lai saņemtu jebkādu palīdzību.
> [!NOTE]
> Visas entītijas var skatīt un izmantot citi lietotāji. Lietotāja kontekstualitāte attiecas tikai uz datu avotiem, nevis uz entītijām, kas rodas šo datu plūsmu rezultātā.

Power Platform Ja netiek izmantotas datu plūsmas, neredzēsiet nevienu grupu vai sadaļu. Lapā **Datu avoti** ir tikai visu datu avotu saraksts.

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
