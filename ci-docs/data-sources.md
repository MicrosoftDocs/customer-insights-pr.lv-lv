---
title: Izmantojiet datu avotus datu uzņemšanai
description: Uzziniet, kā importēt datus no dažādiem avotiem.
ms.date: 05/31/2022
ms.subservice: audience-insights
ms.topic: overview
author: mukeshpo
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: e22977107565a0b28b74f41576a1c7ccc74f6dc1
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 06/14/2022
ms.locfileid: "9011758"
---
# <a name="data-sources-overview"></a>Datu avotu pārskats

Dynamics 365 Customer Insights nodrošina savienojumus, lai iegūtu datus no plaša avotu kopuma. Pieslēgšanos datu avotam bieži vien dēvē par *datu uzņemšanas* procesu. Pēc datu uzņemšanas varat [apvienoties](data-unification.md), ģenerēt ieskatus un aktivizēt datus personalizētas pieredzes veidošanai.

## <a name="add-data-sources"></a>Pievienot datu avotus

Programmā Customer Insights varat pievienot vai importēt datu avotus. Tālāk norādītajās saitēs ir sniegti norādījumi par datu avotu pievienošanu.

**datu avots pievienošana**

Ja dati ir sagatavoti kādā no Microsoft Azure datu pakalpojumiem, Customer Insights var viegli izveidot savienojumu ar datu avots, atkārtoti neuzņemot datus. Atlasiet kādu no šīm opcijām:
- [Azure Data Lake Storage(csv vai parketa faili mapē Kopējais datu modelis)](connect-common-data-model.md)
- [Azure Synapse Analytics(Ezeru datubāzes)](connect-synapse.md)
- [Microsoft Dataverse datu ezers](connect-dataverse-managed-lake.md)

**Importēt un pārveidot**

Ja izmantojat lokālus datu avotus, Microsoft vai trešo pušu datus, importējiet un pārveidojiet datus, izmantojot Power Query savienotājus.
- [Power Query Savienotāji](connect-power-query.md)

## <a name="review-data-sources"></a>Pārskatīt datu avotus

Ja vide ir konfigurēta Customer Insights krātuves izmantošanai un tiek izmantoti lokāli datu avoti, tiek izmantotas Power Platform datu plūsmas. Izmantojot Power Platform datu plūsmas, varat skatīt koplietojamus datu avotus un datu avotus, ko pārvalda citi. Lapā **Datu avoti** datu avoti ir uzskaitīti trīs sadaļās:
- **Koplietots**: datu avoti, kurus var pārvaldīt visi Customer Insights administratori. Power Platform datu plūsmas, savs krātuves konts un pievienošana pārvaldītam datu ezeram ir koplietojamu Dataverse datu avotu piemēri.
- **Manis pārvaldīts**: Power Platform datu plūsmas, ko izveidoja un pārvalda tikai jūs. Citi Customer Insights administratori var skatīt tikai šīs datu plūsmas, bet ne rediģēt, atsvaidzināt vai dzēst tās.
- **Pārvalda citi**: Power Platform citu administratoru izveidotas datu plūsmas. Tos var apskatīt tikai. Tajā ir norādīts datu plūsmas īpašnieks, ar kuru sazināties, lai saņemtu jebkādu palīdzību.
> [!NOTE]
> Visas entītijas var skatīt un izmantot citi lietotāji. Lai gan datu avoti pieder lietotājam, kurš tos izveidoja, datu norīšanas rezultātā iegūtās entītijas var izmantot ikviens Customer Insights lietotājs.

Ja vide neizmanto Power Platform datu plūsmas, **lapā Datu avoti** ir tikai visu datu avotu saraksts. Sadaļas netiek rādītas.

Dodieties uz **Datu** > **datu avoti**, lai skatītu katra uzņemtā datu avots nosaukumu, tā statusu un pēdējo reizi, kad dati tika atsvaidzināti šim avotam. Datu avotu sarakstu var kārtot pēc katras kolonnas.

:::image type="content" source="media/configure-data-datasource-added.png" alt-text="Pievienotie datu avoti.":::

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Datu ielāde var aizņemt laiku. Pēc veiksmīgas atsvaidzināšanas uzņemtos datus var pārskatīt no lapas **Entītijas**. Papildinformāciju skatiet rakstā [Entītijas](entities.md).

## <a name="refresh-data-sources"></a>Atsvaidzināt datu avotus

Datu avotus var atsvaidzināt pēc automātiska grafika vai atsvaidzināt manuāli pēc pieprasījuma. [Lokāli datu avoti](connect-power-query.md#add-data-from-on-premises-data-sources) tiek atsvaidzināti pēc saviem grafikiem, kas iestatīti datu uzņemšanas laikā. Attiecībā uz pievienotajiem datu avotiem datu uzņemšana patērē jaunākos datus, kas pieejami no šīs datu avots.

Dodieties uz **Administrēšanas** > **sistēmas** > [**grafiku**](system.md#schedule-tab), lai konfigurētu sistēmā ieplānotās uzņemto datu avotu atsvaidzināšanas.

Lai atsvaidzinātu datu avotu pēc pieprasījuma, veiciet šīs darbības:

1. Dodieties uz **Dati** > **Datu avoti**.

1. Atlasiet vertikālo daudzpunkti (&vellip;) blakus datu avots, kuru vēlaties atsvaidzināt, un nolaižamajā sarakstā atlasiet **Atsvaidzināt**. Datu avots tagad tiek iespējots manuālai atsvaidzināšanai. Datu avota atsvaidzināšana atjauninās gan entitījas shēmu, gan datus visām entitījām, kuras ir norādītas datu avotā.

1. Atlasiet **Pārtraukt atsvaidzināšanu**, ja vēlaties atcelt esošu atsvaidzināšanu, un datu avots atgriezīsies pēdējās atsvaidzināšanas statusā.

## <a name="delete-a-data-source"></a>Datu avota dzēšana

Datu avots var dzēst tikai tad, ja dati netiek izmantoti nekādā apstrādē, piemēram, apvienošanā, ieskatos, aktivizēšanā vai eksportā.

1. Dodieties uz **Dati** > **Datu avoti**.

2. Atlasiet vertikālo daudzpunkti (&vellip;) blakus datu avots, kuru vēlaties noņemt, un nolaižamajā izvēlnē atlasiet **Dzēst**.

3. Apstipriniet dzēšanu.


[!INCLUDE [footer-include](includes/footer-banner.md)]
