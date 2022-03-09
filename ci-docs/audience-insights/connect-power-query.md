---
title: Datu uzdošana, izmantojot savienotāju Power Query (satur video)
description: Savienotāji datu avotiem, pamatojoties uz Power Query.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: 4c12933a0684094702843be309525dd6d5d9b6f4
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 02/25/2022
ms.locfileid: "8355530"
---
# <a name="connect-to-a-power-query-data-source"></a>Savienojuma izveide ar Power Query datu avots

Power Query piedāvā plašu savienotāju komplektu, lai uzņemtu datus. Vairumu no šiem savienotājiem atbalsta Dynamics 365 Customer Insights. 

Pievienojot datu avotus, kuru pamatā Power Query ir savienotāji, parasti tiek ievērotas šajā sadaļā izklāstītās darbības. Taču atkarībā no savienotāja, kuru izmantojat, var būt nepieciešama atšķirīga informācija. Papildinformāciju skatiet savienotāja [Power Query atsaucē redzamajā dokumentācijā par atsevišķiem savienotājiem](/power-query/connectors/).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6EK]

## <a name="create-a-new-data-source"></a>Jauna datu avota izveide

1. Sadaļā Auditorijas ieskati skatiet **Dati** > **Datu avoti**.

1. Atlasiet **Pievienot datu avotu**.

1. Atlasiet **Microsoft Power Query**.

1. Sniedziet datu avota **Nosaukmu** un atlasiet **Tālāk**, lai izveidotu datu avotu.

1. Izvēlieties vienu no [pieejamiem savienotājiem](#available-power-query-data-sources). Šajā piemērā mēs izvēlamies **teksta/CSV** savienotāju.

1. Ievadiet nepieciešamo informāciju sadaļā **Savienojuma iestatījumi** attiecībā uz atlasīto savienotāju un atlasiet **Tālāk**, lai skatītu datu priekšskatījumu.

1. Atlasiet **Pārveidot datus**. Šajā darbībā jūs pievienosiet entītijas savam datu avotam. Entitījas ir datu kopas. Ja jums ir datu bāze, kurā ir ietvertas vairākas datu kopas, katra datu kopa ir entītija.

1. Dialoglodziņš **Power Query - Vaicājumu** rediģēšana ļauj pārskatīt un precizēt datus. Entītijas, kuras sistēma identificēja jūsu atlasītajā datu avotā, tiek rādītas kreisajā rūtī.

   > [!div class="mx-imgBorder"]
   > ![Vaicājumu rediģēšanas dialoglodziņš.](media/data-manager-configure-edit-queries.png "Vaicājumu rediģēšanas dialoglodziņš")

1. Varat arī transformēt savus datus. Atlasiet entītiju, ko vēlaties rediģēt vai transformēt. Izmantojiet loga opcijas, Power Query lai lietotu transformācijas. Visas izmaiņas ir uzskaitītas sadaļā **Lietotās darbības**. Power Query nodrošina daudzas iepriekš izveidotas transformācijas iespējas. Plašāku informāciju skatiet [Power Query Transformations](/power-query/power-query-what-is-power-query#transformations).

   Ieteicams izmantot šādas transformācijas:

   - Ja uzņemat datus no CSV faila, pirmajā rindā bieži vien ir galvenes. Dodieties uz **Transformācija** un atlasiet **Izmantot pirmo rindu kā galvenes**.
   - Pārliecinieties, ka datu veids ir iestatīts atbilstoši. Piemēram, datuma laukiem atlasiet datuma tipu.

1. Lai datu avots pievienotu papildu entītijas dialoglodziņā Vaicājumu rediģēšana, dodieties uz **Sākums** un atlasiet **Iegūt datus**.**·**

1. Lai saglabātu transformācijas, **loga apakšdaļā atlasiet** Saglabāt Power Query. Pēc saglabāšanas jūsu datu avots atradīsies sadaļā **Dati** > **Datu avoti**.

1. Lapā **Datu avoti** redzēsit, ka jaunā datu avota statuss ir **Atsvaidzina**.

## <a name="available-power-query-data-sources"></a>Pieejamie Power Query datu avoti

Savienotāja [Power Query atsauci](/power-query/connectors/) skatiet to savienotāju sarakstā, kurus var izmantot, lai importētu datus customer insights. 

Savienotāji ar atzīmi **kolonnā Customer Insights (Dataflows)** ir pieejami, lai izveidotu jaunus datu avotus, pamatojoties uz Power Query. Pārskatiet konkrētā savienotāja dokumentāciju, lai uzzinātu vairāk par tā priekšnosacījumiem, ierobežojumiem un citu informāciju.

## <a name="edit-power-query-data-sources"></a>Rediģēt Power Query datu avotus

> [!NOTE]
> Iespējams, nevarēs veikt izmaiņas datu avotos, kuri pašlaik tiek izmantoti kādā no programmas procesiem (piemēram, *segmentēšana*, *atbilstības noteikšana* vai *sapludināšana*). 
>
> **Lapā Iestatījumi** varat izsekot katra aktīvā procesa norisei. Kad process ir pabeigts, varat atgriezties lapā **Datu avoti** un veikt vajadzīgās izmaiņas.

1. Sadaļā Auditorijas ieskati skatiet **Dati** > **Datu avoti**.

2. Nolaižamajā izvēlnē atlasiet vertikālās līknes blakus datu avotam, kuru vēlaties mainīt un atlasiet **Rediģēt**.

   > [!div class="mx-imgBorder"]
   > ![Rediģēšanas opcija.](media/edit-option-data-sources.png "Rediģēšanas opcija")

   [!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]
   
3. Lietojiet izmaiņas un transformācijas dialoglodziņā **Power Query Vaicājumu rediģēšana**, [kā aprakstīts sadaļā Jauna datu avots](#create-a-new-data-source) izveide.

4. Pēc labojumu pabeigšanas atlasiet **Saglabāt** Power Query, lai saglabātu izmaiņas.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
