---
title: Datu avotu pārskats
description: Uzziniet, kā importēt vai uzņemt datus no dažādiem avotiem.
ms.date: 09/29/2022
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
ms.openlocfilehash: f89da3cf5b56e367bd673740f80cd82ec0907b28
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610061"
---
# <a name="data-sources-overview"></a>Datu avotu pārskats

Dynamics 365 Customer Insights nodrošina savienojumus, lai iegūtu datus no plaša avotu kopuma. Pieslēgšanos datu avotam bieži vien dēvē par *datu uzņemšanas* procesu. Pēc datu uzņemšanas varat [apvienot](data-unification.md), ģenerēt ieskatus un aktivizēt datus personalizētas pieredzes veidošanai.

## <a name="add-or-edit-data-sources"></a>Datu avotu pievienošana vai rediģēšana

Varat pievienot vai importēt datu avotus programmā Customer Insights. Tālāk norādītajās saitēs ir sniegti norādījumi par datu avotu pievienošanu un rediģēšanu.

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

## <a name="manage-existing-data-sources"></a>Esošo datu avotu pārvaldība

Dodieties uz **Datu** > **datu avoti**, lai skatītu katras uzņemtās datu avots nosaukumu, tā statusu un pēdējo reizi, kad dati tika atsvaidzināti šim avotam. Datu avotu sarakstu var kārtot pēc jebkuras kolonnas vai izmantot meklēšanas lodziņu, lai atrastu datu avots, kuru vēlaties pārvaldīt.

Atlasiet datu avots, lai skatītu pieejamās darbības.

:::image type="content" source="media/data_sources_showmore.png" alt-text="Pievienotie datu avoti.":::

- [**Rediģējiet**](#add-or-edit-data-sources) datu avots, lai mainītu tās rekvizītus.
- [**Atsvaidziniet**](#refresh-data-sources) datu avots, lai iekļautu jaunākos datus.
- [**Bagātiniet**](data-sources-enrichment.md) datu avots pirms apvienošanās.
- **Dzēsiet** datu avots. Datu avots var dzēst tikai tad, ja dati netiek izmantoti nekādā apstrādē, piemēram, unifikācijā, ieskatos, aktivizēšanā vai eksportēšanā.

## <a name="refresh-data-sources"></a>Atsvaidzināt datu avotus

Datu avotus var atsvaidzināt pēc automātiska grafika vai atsvaidzināt manuāli pēc pieprasījuma. [Lokālie datu avoti](connect-power-query.md#add-data-from-on-premises-data-sources) atsvaidzina savus grafikus, kas tiek iestatīti datu uzņemšanas laikā. Padomus par problēmu novēršanu skatiet rakstā [Uz PPDF Power Query balstītas datu avots atsvaidzināšanas problēmu novēršana](connect-power-query.md#troubleshoot-ppdf-power-query-based-data-source-refresh-issues).

Attiecībā uz pievienotajiem datu avotiem datu uzņemšana patērē jaunākos datus, kas pieejami no šīs datu avots.

Dodieties uz **administrēšanas** > **sistēmas** > [**grafiku**](schedule-refresh.md), lai konfigurētu sistēmas ieplānotos uzņemto datu avotu atsvaidzinājumus.

Lai atsvaidzinātu datu avots pēc pieprasījuma:

1. Dodieties uz **Dati** > **Datu avoti**.

1. Atlasiet datu avots, kuru vēlaties atsvaidzināt, un atlasiet **Atsvaidzināt**. Datu avots tagad tiek iespējots manuālai atsvaidzināšanai. Datu avota atsvaidzināšana atjauninās gan entitījas shēmu, gan datus visām entitījām, kuras ir norādītas datu avotā.

1. Atlasiet statusu, lai atvērtu progresa detalizētās **informācijas** rūti un skatītu norisi. Lai atceltu darbu, rūts apakšdaļā atlasiet **Atcelt darbu**.

## <a name="corrupt-data-sources"></a>Bojāti datu avoti

Norijot datus, var būt bojāti ieraksti, kas var izraisīt datu norīšanas procesa pabeigšanu ar kļūdām vai brīdinājumiem.

> [!NOTE]
> Ja datu norīšana tiek pabeigta ar kļūdām, turpmākā apstrāde (piemēram, apvienošana vai darbību izveide), kas izmanto šo datu avots, tiks izlaista. Ja norīšana ir pabeigta ar brīdinājumiem, turpmāka apstrāde turpinās, bet daži ieraksti var netikt iekļauti.

Šīs kļūdas var redzēt uzdevuma detaļās.

:::image type="content" source="media/corrupt-task-error.png" alt-text="Detalizēta informācija par uzdevumu, kurā redzama kļūda bojāti dati.":::

Bojāti ieraksti tiek rādīti sistēmas izveidotās entītijās.

### <a name="fix-corrupt-data"></a>Bojātu datu labošana

1. Lai skatītu bojātos datus, dodieties uz **Datu entītijas** > **un sadaļā Sistēma** meklējiet bojātās **entītijas**. Korumpētu vienību nosaukšanas shēma: "DataSourceName_EntityName_corrupt".

1. Atlasiet bojātu entītiju un pēc tam cilni **Dati**.

1. Identificējiet bojātos laukus ierakstā un iemeslu.

   :::image type="content" source="media/corruption-reason.png" alt-text="Korupcijas iemesls." lightbox="media/corruption-reason.png":::

   > [!NOTE]
   > **Datu** > **entītijas** rāda tikai daļu no bojātajiem ierakstiem. Lai skatītu visus bojātos ierakstus, eksportējiet failus uz krātuves konta konteineru, [izmantojot Customer Insights eksportēšanas procesu](export-destinations.md). Ja izmantojāt savu krātuves kontu, varat arī apskatīt sava krātuves konta mapi Customer Insights.

1. Labojiet bojātos datus. Piemēram, Azure Data Lake datu avotiem [labojiet datus datu ezera krātuvē vai atjauniniet datu tipus manifest/model.json failā](connect-common-data-model.md#common-reasons-for-ingestion-errors-or-corrupt-data). Datu Power Query avotiem izlabojiet datus avota failā un [izlabojiet datu tipa transformācijas darbību](connect-power-query.md#data-type-does-not-match-data)**Power Query lapā - Rediģēt vaicājumus**.

Pēc nākamās datu avotu atsvaidzināšanas labotie ieraksti tiek lietoti programmā Customer Insights un nodoti lejupstraumes procesiem.

Piemēram, kolonnas 'dzimšanas diena' datu tips ir iestatīts kā 'datums'. Klienta ieraksta dzimšanas diena ir ievadīta kā '01/01/19777'. Sistēma šo ierakstu atzīmē kā bojātu. Mainiet dzimšanas dienu avota sistēmā uz "1977". Pēc datu avotu automātiskās atsvaidzināšanas laukam tagad ir derīgs formāts, un ieraksts tiek noņemts no bojātās entītijas.

[!INCLUDE [footer-include](includes/footer-banner.md)]
