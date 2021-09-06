---
title: Izmantojiet datu avotus datu uzņemšanai
description: Uzziniet, kā importēt datus no dažādiem avotiem.
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 75d597158233f75f0eb5f94389f9dba199d81719f2bbe4e5cc58d2a3afc7dcf8
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032859"
---
# <a name="data-sources-overview"></a>Datu avotu pārskats

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Auditorijas ieskatus Dynamics 365 Customer Insights var savienot ar datiem no plašas avotu kopas. Pieslēgšanos datu avotam bieži vien dēvē par *datu uzņemšanas* procesu. Pēc datu uzņemšanas varat tos [apvienot](data-unification.md) un veikt ar tiem darbības.

## <a name="add-a-data-source"></a>Pievienot datu avotu

Skatiet detalizētus rakstus, kā pievienot datu avotu atkarībā no izvēlētās opcijas.

Datu avotu varat pievienot trīs galvenajos veidos:

- [Izmantojot daudzos Power Query savienotājus](connect-power-query.md)
- [No Common Data Model mapes](connect-common-data-model.md)
- [No sava Microsoft Dataverse ezera](connect-dataverse-managed-lake.md)

## <a name="add-data-from-on-premises-data-sources"></a>Datu pievienošana no lokālajiem datu avotiem

Datu pievienošana no lokālajiem datu avotiem auditorijas ieskatos tiek atbalstīta, balstoties uz Microsoft Power Platform datu plūsmām. Datu plūsmas var iespējot risinājumā Customer Insights, [nodrošinot Microsoft Dataverse vides URL](get-started-paid.md), kad tiek iestatīta vide.

Datu avoti, kuri tiek izveidoti pēc saistīšanas ar Dataverse vidi ar Customer Insights, pēc noklusējuma izmantos [Power Platform datu plūsmas](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365). Datu plūsmas atbalsta lokālo savienojamību, izmantojot datu vārtejas. Noņemiet un no jauna izveidojiet datu avotus, kuri pastāvēja, pirms Dataverse vide tika saistīta, lai [lietotu lokālās datu vārtejas](/data-integration/gateway/service-gateway-app).

Datu vārtejas no esošās Power BI vai Power Apps vides būs redzama, un to varat atkārtoti izmantot risinājumā Customer Insights. Datu avotu lapā ir redzamas saites, kas ļauj pāriet uz Microsoft Power Platform vidi, kurā varat skatīt un konfigurēt lokālās datu vārtejas.

## <a name="review-ingested-data"></a>Uzņemto datu pārskatīšana

Jūs redzēsit katra uzņemtā datu avota nosaukumu, tā statusu un pēdējo reizi, kad dati tika atsvaidzināti no šī avota. Datu avotu sarakstu var kārtot pēc katras kolonnas.

> [!div class="mx-imgBorder"]
> ![Pievienotie datu avoti.](media/configure-data-datasource-added.png "Pievienotie datu avoti")

|Statuss  |Apraksts  |
|---------|---------|
|Sekmīgs   |Datu avots tika veiksmīgi paņemts, ja ir minēts laiks kolonnā **Atsvaidzināts**.
|Nav sākts   |Datu avots nesatur datus, kas ir uzņemti vai vēl ir melnraksta režīmā.         |
|Notiek atsvaidzināšana    |Notiek datu uzņemšana. Šo darbību varat atcelt, kolonnā **Darbības** atlasot **Apturēt atsvaidzināšanu**. Apturot datu avota atsvaidzināšanu, tas atkal kļūs tāds pats kā pēdējās atsvaidzināšanas brīdī.       |
|Neizdevās     |Veicot datu uzņemšanu, radās kļūdas.         |

Atlasiet vērtību jebkura datu avoti kolonnā **Statuss**, lai pārskatītu papildinformāciju. Rūtī **Detalizēta informācija** izvērsiet **Datu avoti**. Atlasiet **Skatīt detalizētu informāciju** papildu informācijai par atsvaidzināšanas statusu, ieskaitot kļūdas detaļas un pakārtotā procesa atjauninājumus.

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
