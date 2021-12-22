---
title: Datu uzdošana, izmantojot Power Query savienotāju (video)
description: Savienotāji datu avotiem, pamatojoties uz Power Query.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.openlocfilehash: 38c447d80a25feca087ca9f110278b8401423018
ms.sourcegitcommit: 12910882ca990ec0e890ed4deaf3dac7e01621e5
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 12/10/2021
ms.locfileid: "7903849"
---
# <a name="connect-to-a-power-query-data-source"></a>Savienojuma izveide ar Power Query datu avotu

Power Query piedāvā plašu savienotāju kopu datu uzņemšanai. Vairumu no šiem savienotājiem atbalsta Dynamics 365 Customer Insights. 

Pievienojot datu avotus, kuru pamatā ir Power Query savienotāji, parasti tiek ievērotas šajā sadaļā izklāstītās darbības. Taču atkarībā no savienotāja, kuru izmantojat, var būt nepieciešama atšķirīga informācija. Papildinformāciju skatiet Power Query [savienotāja atsaucē](/power-query/connectors/).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6EK]

## <a name="create-a-new-data-source"></a>Jauna datu avota izveide

1. Sadaļā Auditorijas ieskati skatiet **Dati** > **Datu avoti**.

1. Atlasiet **Pievienot datu avotu**.

1. Atlasiet **Microsoft Power Query, pēc tam** atlasiet **Tālāk**.

1. Sniedziet datu avota **Nosaukmu** un atlasiet **Tālāk**, lai izveidotu datu avotu.

1. Izvēlieties vienu no [pieejamiem savienotājiem](#available-power-query-data-sources). Šajā piemērā mēs izvēlamies **teksta/CSV** savienotāju.

1. Ievadiet nepieciešamo informāciju sadaļā **Savienojuma iestatījumi** attiecībā uz atlasīto savienotāju un atlasiet **Tālāk**, lai skatītu datu priekšskatījumu.

1. Atlasiet **Pārveidot datus**. Šajā darbībā jūs pievienosiet entītijas savam datu avotam. Entitījas ir datu kopas. Ja jums ir datu bāze, kurā ir ietvertas vairākas datu kopas, katra datu kopa ir entītija.

1. Dialoglodziņā **Power Query — rediģēt vaicājumus** ļauj pārskatīt un precizēt datus. Entītijas, kuras sistēma identificēja jūsu atlasītajā datu avotā, tiek rādītas kreisajā rūtī.

   > [!div class="mx-imgBorder"]
   > ![Vaicājumu rediģēšanas dialoglodziņš.](media/data-manager-configure-edit-queries.png "Vaicājumu rediģēšanas dialoglodziņš")

1. Varat arī transformēt savus datus. Atlasiet entītiju, ko vēlaties rediģēt vai transformēt. Izmantojiet Power Query loga opcijas, lai lietotu izmaiņas. Visas izmaiņas ir uzskaitītas sadaļā **Lietotās darbības**. Power Query nodrošina daudzas iepriekš izveidotas izmaiņu opcijas. Papildinformāciju skatiet sadaļā [Power Query izmaiņas](/power-query/power-query-what-is-power-query#transformations).

1. Saviem datu avotiem varat pievienotu papildu entītijas, dialoglodziņā **Vaicājumu rediģēšana** atlasot **Iegūt datus**.

   Ieteicams izmantot šādas transformācijas:

   - Ja uzņemat datus no CSV faila, pirmajā rindā bieži vien ir galvenes. Dodieties uz **Mainīt tabulu** un atlasiet **Izmantot galvenes kā pirmo rindu**.
   - Pārliecinieties, ka datu veids ir iestatīts atbilstoši.

1. Power Query loga apakšējā labajā stūrī atlasiet **Saglabāt**, lai saglabātu izmaiņas. Pēc saglabāšanas jūsu datu avots atradīsies sadaļā **Dati** > **Datu avoti**.

1. Lapā **Datu avoti** redzēsit, ka jaunā datu avota statuss ir **Atsvaidzina**.

## <a name="available-power-query-data-sources"></a>Pieejamie Power Query datu avoti

[Savienotāju](/power-query/connectors/) sarakstu, ko var izmantot datu importēšanai customer insights, skatiet Power Query savienotāja atsauci. 

Savienotāji ar atzīmi kolonnā **Customer Insights (Dataflows)** ir pieejami, lai izveidotu jaunus datu avotus, pamatojoties uz Power Query. Pārskatiet konkrētā savienotāja dokumentāciju, lai uzzinātu vairāk par tā priekšnosacījumiem, ierobežojumiem un citu informāciju.

## <a name="edit-power-query-data-sources"></a>Power Query datu avotu rediģēšana

> [!NOTE]
> Iespējams, nevarēs veikt izmaiņas datu avotos, kuri pašlaik tiek izmantoti kādā no programmas procesiem (piemēram, *segmentēšana*, *atbilstības noteikšana* vai *sapludināšana*). 
>
> Lapā **Iestatījumi** varat izsekot katra aktīvā procesa norisei. Kad process ir pabeigts, varat atgriezties lapā **Datu avoti** un veikt vajadzīgās izmaiņas.

1. Sadaļā Auditorijas ieskati skatiet **Dati** > **Datu avoti**.

2. Nolaižamajā izvēlnē atlasiet vertikālās līknes blakus datu avotam, kuru vēlaties mainīt un atlasiet **Rediģēt**.

   > [!div class="mx-imgBorder"]
   > ![Rediģēšanas opcija.](media/edit-option-data-sources.png "Rediģēšanas opcija")

   [!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]
   
3. Piemērojiet veiktās izmaiņas un transformācijas dialoglodziņā **Power Query — izmaiņu rediģēšana**, kā aprakstīts sadaļā [Jauna datu avota izveide](#create-a-new-data-source).

4. Lai saglabātu izmaiņas, pēc rediģēšanas pabeigšanas Power Query atlasiet **Saglabāt**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
