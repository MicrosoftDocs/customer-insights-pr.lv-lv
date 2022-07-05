---
title: Savienojuma izveide ar Power Query datu avots (satur video)
description: Datu uzņemšana, izmantojot savienotāju Power Query (satur video).
ms.date: 06/13/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: matgos
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: 6736b253e3a7e652f92f61bc44bfb31ca69be31a
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082179"
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

1. Atlasiet **Pārveidot datus**. Šajā darbībā jūs pievienosiet entītijas savam datu avotam. Entitījas ir datu kopas. Ja jums ir datu bāze, kurā ir ietvertas vairākas datu kopas, katra datu kopa ir entītija.

1. Dialoglodziņš **Power Query - vaicājumu** rediģēšana ļauj pārskatīt un precizēt datus. Entītijas, kuras sistēma identificēja jūsu atlasītajā datu avotā, tiek rādītas kreisajā rūtī.

   :::image type="content" source="media/data-manager-configure-edit-queries.png" alt-text="Vaicājumu rediģēšanas dialoglodziņš":::

1. Varat arī transformēt savus datus. Atlasiet entītiju, ko vēlaties rediģēt vai transformēt. Izmantojiet logā esošās opcijas, Power Query lai lietotu transformācijas. Katra transformācija ir norādīta sadaļā **Lietotās darbības**. Power Query nodrošina daudzas iepriekš izveidotas transformācijas iespējas. Papildinformāciju skatiet sadaļā [Power Query Transformācijas](/power-query/power-query-what-is-power-query#transformations).

   Mēs iesakām izmantot šādas transformācijas:

   - Ja uzņemat datus no CSV faila, pirmajā rindā bieži vien ir galvenes. Dodieties uz **Transformācija** un atlasiet **Izmantot pirmo rindu kā galvenes**.
   - Pārliecinieties, ka datu veids ir iestatīts atbilstoši. Piemēram, datuma laukiem atlasiet datuma tipu.

1. Lai pievienotu papildu entītijas savai datu avots dialoglodziņā Vaicājumu **rediģēšana, dodieties uz** Sākums **un atlasiet** Iegūt datus **.** Atkārtojiet 6.–10. darbību, līdz esat pievienojis visas šīs datu avots entītijas.

1. Atlasiet **Saglabāt**. Tiek **atvērta lapa Datu avoti**, kurā redzams jaunais datu avots sadaļā **Atsvaidzināšanas** statuss.

### <a name="available-power-query-data-sources"></a>Pieejamie Power Query datu avoti

Skatiet savienotāja [Power Query atsauci](/power-query/connectors/), lai skatītu to savienotāju sarakstu, kurus varat izmantot, lai importētu datus programmā Customer Insights.

Savienotāji ar atzīmi **kolonnā Customer Insights (Dataflows)** ir pieejami, lai izveidotu jaunus datu avotus, kuru pamatā Power Query ir. Pārskatiet konkrēta savienotāja dokumentāciju, lai uzzinātu vairāk par tā priekšnosacījumiem, [vaicājumu ierobežojumiem](/power-query/power-query-online-limits) un citu informāciju.

## <a name="add-data-from-on-premises-data-sources"></a>Datu pievienošana no lokālajiem datu avotiem

Datu uzņemšana no lokāls datu avotiem tiek atbalstīta, pamatojoties uz Microsoft Power Platform datu plūsmām (PPDF). Varat iespējot datu plūsmas programmā Customer Insights, [vides iestatīšanas Microsoft Dataverse laikā norādot vides URL](create-environment.md).

Datu avoti, kas tiek izveidoti pēc vides saistīšanas Dataverse ar Customer Insights, pēc noklusējuma izmanto [Power Platform datu plūsmas](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365). Datu plūsmas atbalsta lokālo savienojamību, izmantojot datu vārtejas. Varat noņemt un atkārtoti izveidot datu avotus, kas pastāvēja pirms Dataverse vides saistīšanas, [izmantojot lokāls datu vārtejas](/data-integration/gateway/service-gateway-app).

Datu vārtejas no esošās Power BI vai Power Apps vides būs redzama, un to varat atkārtoti izmantot risinājumā Customer Insights. Datu avotu lapā ir redzamas saites, kas ļauj pāriet uz Microsoft Power Platform vidi, kurā varat skatīt un konfigurēt lokālās datu vārtejas.

> [!IMPORTANT]
> Pārliecinieties, vai vārtejas ir atjauninātas uz jaunāko versiju. Varat instalēt atjauninājumu un pārkonfigurēt vārteju no uzvednes, kas parādīta vārtejas ekrānā tieši, vai [lejupielādēt jaunāko versiju](https://powerapps.microsoft.com/downloads/). Ja neizmantojat jaunāko vārtejas versiju, datu plūsmas atsvaidzināšana neizdodas ar tādiem kļūdu ziņojumiem kā **Atslēgvārds netiek atbalstīts: konfigurācijas rekvizīti. Parametra nosaukums: atslēgvārds**.

## <a name="edit-power-query-data-sources"></a>Datu avotu rediģēšana Power Query

> [!NOTE]
> Iespējams, nevarēs veikt izmaiņas datu avotos, kuri pašlaik tiek izmantoti kādā no programmas procesiem (piemēram, *segmentēšana*, *atbilstības noteikšana* vai *sapludināšana*).
>
> **Lapā Iestatījumi** varat izsekot katra aktīvā procesa norisei. Kad process ir pabeigts, varat atgriezties lapā **Datu avoti** un veikt vajadzīgās izmaiņas.

1. Dodieties uz **Dati** > **Datu avoti**.

1. Blakus datu avots, kuru vēlaties atjaunināt, atlasiet **Rediģēt**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

1. Lietojiet izmaiņas un transformācijas **Power Query dialoglodziņā Vaicājumu** rediģēšana, [kā aprakstīts sadaļā Jauna datu avots](#create-a-new-data-source) izveide.

1. Pēc labojumu pabeigšanas atlasiet **Saglabāt**, Power Query lai saglabātu izmaiņas.
