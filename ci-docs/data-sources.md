---
title: Datu avotu pārskats
description: Uzziniet, kā importēt vai uzņemt datus no dažādiem avotiem.
ms.date: 05/18/2022
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
ms.openlocfilehash: fbe44f655bdbc20ef7f0956022395e2dcb570adf
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 06/29/2022
ms.locfileid: "9051462"
---
# <a name="data-sources-overview"></a>Datu avotu pārskats

Dynamics 365 Customer Insights nodrošina savienojumus, lai iegūtu datus no plaša avotu kopuma. Pieslēgšanos datu avotam bieži vien dēvē par *datu uzņemšanas* procesu. Pēc datu uzņemšanas varat [apvienot](data-unification.md), ģenerēt ieskatus un aktivizēt datus personalizētas pieredzes veidošanai.

## <a name="add-data-sources"></a>Pievienot datu avotus

Varat pievienot vai importēt datu avotus programmā Customer Insights. Tālāk norādītajās saitēs ir sniegti norādījumi par datu avotu pievienošanu.

**Pievienojiet datu avots**

Ja jums ir dati, kas sagatavoti kādā no Microsoft Azure datu pakalpojumiem, Customer Insights var viegli izveidot savienojumu ar datu avots bez nepieciešamības atkārtoti ievadīt datus. Atlasiet kādu no šīm opcijām:
- [Azure Data Lake Storage(csv vai parketa faili mapē Common Data Model)](connect-common-data-model.md)
- [Azure Synapse Analytics(Ezeru datubāzes)](connect-synapse.md)
- [Microsoft Dataverse datu ezers](connect-dataverse-managed-lake.md)

**Importēšana un transformācija**

Ja izmantojat lokālos datu avotus, Microsoft vai trešo pušu datus, importējiet un pārveidojiet datus, izmantojot Power Query savienotājus.
- [Power Query Savienotāji](connect-power-query.md)

## <a name="review-data-sources"></a>Datu avotu pārskatīšana

Ja jūsu vide tika konfigurēta tā, lai izmantotu Customer Insights krātuvi, un jūs izmantojat lokālos datu avotus, jūs izmantojat Power Platform datu plūsmas. Izmantojot Power Platform datu plūsmas, varat skatīt koplietojamus datu avotus un datu avotus, ko pārvalda citi. Lapā **Datu avoti** datu avoti ir uzskaitīti trīs sadaļās:
- **Kopīgots**: datu avoti, kurus var pārvaldīt visi Customer Insights administratori. Power Platform datu plūsmas, savs krātuves konts un pievienošana pārvaldītam datu ezeram Dataverse ir koplietojamu datu avotu piemēri.
- **Pārvalda es**: Power Platform datu plūsmas, ko izveidojis un pārvaldāt tikai jūs. Citi Customer Insights administratori var tikai skatīt šīs datu plūsmas, bet ne rediģēt, atsvaidzināt vai dzēst.
- **Pārvalda citi**: Power Platform datu plūsmas, ko izveidojuši citi administratori. Tos var apskatīt tikai. Tajā ir norādīts datu plūsmas īpašnieks, ar kuru sazināties, lai saņemtu palīdzību.
> [!NOTE]
> Visas entītijas var skatīt un izmantot citi lietotāji. Lai gan datu avoti pieder lietotājam, kurš tos ir izveidojis, iegūtās entītijas no datu norīšanas var izmantot ikviens Customer Insights lietotājs.

Ja jūsu vide neizmanto Power Platform datu plūsmas, **lapā Datu avoti** ir tikai visu datu avotu saraksts. Sadaļas netiek rādītas.

Dodieties uz **Datu** > **datu avoti**, lai skatītu katras uzņemtās datu avots nosaukumu, tā statusu un pēdējo reizi, kad dati tika atsvaidzināti šim avotam. Datu avotu sarakstu var kārtot pēc katras kolonnas.

:::image type="content" source="media/configure-data-datasource-added.png" alt-text="Pievienotie datu avoti.":::

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Datu ielāde var aizņemt laiku. Pēc veiksmīgas atsvaidzināšanas uzņemtos datus var pārskatīt no lapas **Entītijas**. Papildinformāciju skatiet rakstā [Entītijas](entities.md).

## <a name="refresh-data-sources"></a>Atsvaidzināt datu avotus

Datu avotus var atsvaidzināt pēc automātiska grafika vai atsvaidzināt manuāli pēc pieprasījuma. [Lokālie datu avoti](connect-power-query.md#add-data-from-on-premises-data-sources) atsvaidzina savus grafikus, kas tiek iestatīti datu uzņemšanas laikā. Attiecībā uz pievienotajiem datu avotiem datu uzņemšana patērē jaunākos datus, kas pieejami no šīs datu avots.

Dodieties uz **administrēšanas** > **sistēmas** > [**grafiku**](system.md#schedule-tab), lai konfigurētu sistēmas ieplānotos uzņemto datu avotu atsvaidzinājumus.

Lai atsvaidzinātu datu avotu pēc pieprasījuma, veiciet šīs darbības:

1. Dodieties uz **Dati** > **Datu avoti**.

1. Atlasiet vertikālo daudzpunkti (&vellip;) blakus datu avots, kuru vēlaties atsvaidzināt, un nolaižamajā sarakstā atlasiet **Atsvaidzināt**. Datu avots tagad tiek iespējots manuālai atsvaidzināšanai. Datu avota atsvaidzināšana atjauninās gan entitījas shēmu, gan datus visām entitījām, kuras ir norādītas datu avotā.

1. Atlasiet **Pārtraukt atsvaidzināšanu**, ja vēlaties atcelt esošu atsvaidzināšanu, un datu avots atgriezīsies pēdējās atsvaidzināšanas statusā.

## <a name="delete-a-data-source"></a>Datu avota dzēšana

Datu avots var dzēst tikai tad, ja dati netiek izmantoti nekādā apstrādē, piemēram, unifikācijā, ieskatos, aktivizēšanā vai eksportēšanā.

1. Dodieties uz **Dati** > **Datu avoti**.

2. Atlasiet vertikālo daudzpunkti (&vellip;) blakus datu avots, kuru vēlaties noņemt, un nolaižamajā izvēlnē atlasiet **Dzēst**.

3. Apstipriniet dzēšanu.


[!INCLUDE [footer-include](includes/footer-banner.md)]
