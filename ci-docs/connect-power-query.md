---
title: Savienojuma izveide ar Power Query datu avots (satur video)
description: Datu uzņemšana, izmantojot savienotāju Power Query (satur video).
ms.date: 07/26/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: 6a25e332bafab414c9def4e1e6b461139dd24ea6
ms.sourcegitcommit: dfba60e17ae6dc1e2e3830e6365e2c1f87230afd
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 09/09/2022
ms.locfileid: "9463274"
---
# <a name="connect-to-a-power-query-data-source"></a>Savienojuma izveide ar Power Query datu avots

Power Query piedāvā plašu savienotāju komplektu, lai uzņemtu datus. Vairumu no šiem savienotājiem atbalsta Dynamics 365 Customer Insights.

Pievienojot datu avotus, kuru pamatā Power Query ir savienotāji, parasti tiek veiktas šajā sadaļā aprakstītās darbības. Taču atkarībā no savienotāja, kuru izmantojat, var būt nepieciešama atšķirīga informācija. Lai uzzinātu vairāk, skatiet dokumentāciju par atsevišķiem savienotājiem savienotāja [Power Query atsaucē](/power-query/connectors/).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6EK]

## <a name="create-a-new-data-source"></a>Jauna datu avota izveide

1. Dodieties uz **Dati** > **Datu avoti**.

1. Atlasiet **Pievienot datu avotu**.

1. Atlasiet **Microsoft Power Query**.

1. **Norādiet datu avots nosaukumu** un neobligātu **aprakstu** un atlasiet **Tālāk**.

1. Izvēlieties vienu no [pieejamiem savienotājiem](#available-power-query-data-sources). Šajā piemērā mēs atlasām **teksta/CSV savienotāju**.

1. Ievadiet nepieciešamo informāciju sadaļā **Savienojuma iestatījumi** attiecībā uz atlasīto savienotāju un atlasiet **Tālāk**, lai skatītu datu priekšskatījumu.

1. Atlasiet **Pārveidot datus**.

1. Dialoglodziņš **Power Query - vaicājumu** rediģēšana ļauj pārskatīt un precizēt datus. Entītijas, kuras sistēma identificēja jūsu atlasītajā datu avotā, tiek rādītas kreisajā rūtī.

   :::image type="content" source="media/data-manager-configure-edit-queries.png" alt-text="Vaicājumu rediģēšanas dialoglodziņš":::

1. Varat arī transformēt savus datus. Atlasiet entītiju, ko vēlaties rediģēt vai transformēt. Izmantojiet logā esošās opcijas, Power Query lai lietotu transformācijas. Katra transformācija ir norādīta sadaļā **Lietotās darbības**. Power Query nodrošina daudzas [iepriekš izveidotas transformācijas](/power-query/power-query-what-is-power-query#transformations) iespējas.

   Mēs iesakām izmantot šādas transformācijas:

   - Ja uzņemat datus no CSV faila, pirmajā rindā bieži vien ir galvenes. Dodieties uz **Transformācija** un atlasiet **Izmantot pirmo rindu kā galvenes**.
   - Pārliecinieties, ka datu veids ir iestatīts atbilstoši. Piemēram, datuma laukiem atlasiet datuma tipu.

1. Lai pievienotu papildu entītijas savai datu avots dialoglodziņā Vaicājumu **rediģēšana, dodieties uz** Sākums **un atlasiet** Iegūt datus **.** Atkārtojiet 5.–10. darbību, līdz esat pievienojis visas šīs datu avots entītijas. Ja jums ir datu bāze, kurā ir ietvertas vairākas datu kopas, katra datu kopa ir entītija.

1. Atlasiet **Saglabāt**. Tiek **atvērta lapa Datu avoti**, kurā redzams jaunais datu avots sadaļā **Atsvaidzināšanas** statuss.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Datu ielāde var aizņemt laiku. Pēc veiksmīgas atsvaidzināšanas pieņemtos datus var pārskatīt lapā [**Entītijas**](entities.md).

> [!CAUTION]
>
> - Datu avots, kura pamatā Power Query ir datu plūsma, izveido [datu plūsmu .Dataverse](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) Nemainiet datu plūsmas nosaukumu administrēšanas centrā, Power Platform kas tiek izmantots programmā Customer Insights. Datu plūsmas pārdēvēšana rada problēmas ar atsaucēm starp Customer Insights datu avots un Dataverse datu plūsmu.
> - Vienlaicīgai Power Query datu avotu novērtēšanai programmā Customer Insights ir tādi paši [atsvaidzināšanas ierobežojumi kā Dataflows PowerBI.com](/power-query/power-query-online-limits#refresh-limits). Ja datu atsvaidzināšana neizdodas, jo tā ir sasniegusi novērtēšanas ierobežojumu, ieteicams pielāgot atsvaidzināšanas grafiku katrai datu plūsmai, lai nodrošinātu, ka datu avoti netiek apstrādāti vienlaikus.

### <a name="available-power-query-data-sources"></a>Pieejamie Power Query datu avoti

Skatiet savienotāja [Power Query atsauci](/power-query/connectors/), lai skatītu to savienotāju sarakstu, kurus varat izmantot, lai importētu datus programmā Customer Insights.

Savienotāji ar atzīmi **kolonnā Customer Insights (Dataflows)** ir pieejami, lai izveidotu jaunus datu avotus, kuru pamatā Power Query ir. Pārskatiet konkrēta savienotāja dokumentāciju, lai uzzinātu vairāk par tā priekšnosacījumiem, [vaicājumu ierobežojumiem](/power-query/power-query-online-limits) un citu informāciju.

## <a name="add-data-from-on-premises-data-sources"></a>Datu pievienošana no lokālajiem datu avotiem

Datu uzņemšana no lokāls datu avotiem tiek atbalstīta, pamatojoties uz Microsoft Power Platform datu plūsmām (PPDF). Varat iespējot datu plūsmas programmā Customer Insights, [vides iestatīšanas Microsoft Dataverse laikā norādot vides URL](create-environment.md).

Datu avoti, kas tiek izveidoti pēc vides saistīšanas Dataverse ar Customer Insights, pēc noklusējuma izmanto [Power Platform datu plūsmas](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365). Datu plūsmas atbalsta lokālo savienojamību, izmantojot datu vārtejas. Varat noņemt un atkārtoti izveidot datu avotus, kas pastāvēja pirms Dataverse vides saistīšanas, [izmantojot lokāls datu vārtejas](/data-integration/gateway/service-gateway-app).

Datu vārtejas no esošas Power BI vai Power Apps vides būs redzamas, un tās varēsit atkārtoti izmantot programmā Customer Insights, ja datu vārteja un Customer Insights vide atrodas vienā Azure reģionā. Datu avotu lapā ir redzamas saites, kas ļauj pāriet uz Microsoft Power Platform vidi, kurā varat skatīt un konfigurēt lokālās datu vārtejas.

> [!IMPORTANT]
> Pārliecinieties, vai vārtejas ir atjauninātas uz jaunāko versiju. Varat instalēt atjauninājumu un pārkonfigurēt vārteju no uzvednes, kas parādīta vārtejas ekrānā tieši, vai [lejupielādēt jaunāko versiju](https://powerapps.microsoft.com/downloads/). Ja neizmantojat jaunāko vārtejas versiju, datu plūsmas atsvaidzināšana neizdodas ar tādiem kļūdu ziņojumiem kā **Atslēgvārds netiek atbalstīts: konfigurācijas rekvizīti. Parametra nosaukums: atslēgvārds**.
>
> Kļūdas, kas saistītas ar lokāls datu vārtejām programmā Customer Insights, bieži izraisa konfigurācijas problēmas. Papildinformāciju par datu vārteju problēmu novēršanu skatiet sadaļā [Lokāls datu vārtejas](/data-integration/gateway/service-gateway-tshoot) problēmu novēršana.

## <a name="edit-power-query-data-sources"></a>Datu avotu rediģēšana Power Query

> [!NOTE]
> Iespējams, nav iespējams veikt izmaiņas datu avotos, kas pašlaik tiek izmantoti kādā no lietotnes procesiem (piemēram, segmentācija vai datu apvienošana).
>
> **Lapā Iestatījumi** varat izsekot katra aktīvā procesa norisei. Kad process ir pabeigts, varat atgriezties lapā **Datu avoti** un veikt vajadzīgās izmaiņas.

1. Dodieties uz **Dati** > **Datu avoti**.

1. Blakus datu avots, kuru vēlaties atjaunināt, atlasiet **Rediģēt**.

1. Lietojiet izmaiņas un transformācijas **Power Query dialoglodziņā Vaicājumu** rediģēšana, [kā aprakstīts sadaļā Jauna datu avots](#create-a-new-data-source) izveide.

1. Atlasiet **Saglabāt**, lai lietotu izmaiņas un atgrieztos **lapā Datu avoti**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
