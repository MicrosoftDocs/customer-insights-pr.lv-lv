---
title: Datu paņemšana, izmantojot Power Query savienotāju
description: Savienotāji datu avotiem, pamatojoties uz Power Query.
ms.date: 09/29/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.openlocfilehash: 3be417845a41c8f25c71bfc0823f42571157759b224e46d5e114037ee3df8329
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 08/10/2021
ms.locfileid: "7033273"
---
# <a name="connect-to-a-power-query-data-source"></a>Savienojuma izveide ar Power Query datu avotu

Power Query piedāvā plašu savienotāju kopu datu uzņemšanai. Vairumu no šiem savienotājiem atbalsta Dynamics 365 Customer Insights. Datu avotu pievienošanā, pamatojoties uz Power Query savienotājiem, kopumā tiek izpildītas nākamajā sadaļā izklāstītās darbības. Taču atkarībā no savienotāja, kuru izmantojat, var būt nepieciešama atšķirīga informācija. Lai iegūtu papildinformāciju, skatiet dokumentus par atsevišķiem savienotājiem [Power Query savienotāja atsaucē](/power-query/connectors/).

## <a name="create-a-new-data-source"></a>Jauna datu avota izveide

1. Sadaļā Auditorijas ieskati skatiet **Dati** > **Datu avoti**.

1. Atlasiet **Pievienot datu avotu**.

1. Atlasiet **Datu importēšanas** metodi, pēc tam atlasiet **Tālāk**.

1. Sniedziet datu avota **Nosaukmu** un atlasiet **Tālāk**, lai izveidotu datu avotu. Nosaukuma vadlīnijas: 
   - Sāciet ar burtu.
   - Izmantojiet tikai burtus un ciparus. Speciālās rakstzīmes un atstarpes nav atļautas.
   - Izmantojiet no 3 līdz 64 rakstzīmēm.

1. Izvēlieties vienu no [pieejamiem savienotājiem](#available-power-query-data-sources). Šajā piemērā esam atlasījuši savienotāju **Text/CSV**.

1. Ievadiet nepieciešamo informāciju sadaļā **Savienojuma iestatījumi** attiecībā uz atlasīto savienotāju un atlasiet **Tālāk**, lai skatītu datu priekšskatījumu.

1. Atlasiet **Pārveidot datus**. Šajā darbībā jūs pievienosiet entītijas savam datu avotam. Entitījas ir datu kopas. Ja jums ir datu bāze, kurā ir ietvertas vairākas datu kopas, katra datu kopa ir entītija.

1. Dialoglodziņā **Power Query — rediģēt vaicājumus** ļauj pārskatīt un precizēt datus. Entītijas, kuras sistēma identificēja jūsu atlasītajā datu avotā, tiek rādītas kreisajā rūtī.

   > [!div class="mx-imgBorder"]
   > ![Vaicājumu rediģēšanas dialoglodziņš.](media/data-manager-configure-edit-queries.png "Vaicājumu rediģēšanas dialoglodziņš")

1. Varat arī transformēt savus datus. Atlasiet entītiju, ko vēlaties rediģēt vai transformēt. Izmantojiet Power Query loga opcijas, lai lietotu izmaiņas. Visas izmaiņas ir uzskaitītas sadaļā **Lietotās darbības**. Power Query nodrošina daudzas iepriekš izveidotas izmaiņu opcijas. Papildinformāciju skatiet sadaļā [Power Query izmaiņas](/power-query/power-query-what-is-power-query#transformations).

1. Saviem datu avotiem varat pievienotu papildu entītijas, dialoglodziņā **Vaicājumu rediģēšana** atlasot **Iegūt datus**.

   Ir ieteicams veikt tālāk norādītās transformācijas:

   - Ja uzņemat datus no CSV faila, pirmajā rindā bieži vien ir galvenes. Dodieties uz **Mainīt tabulu** un atlasiet **Izmantot galvenes kā pirmo rindu**.
   - Pārliecinieties, ka datu veids ir iestatīts atbilstoši.

1. Power Query loga apakšējā labajā stūrī atlasiet **Saglabāt**, lai saglabātu izmaiņas. Pēc saglabāšanas jūsu datu avots atradīsies sadaļā **Dati** > **Datu avoti**.

1. Lapā **Datu avoti** redzēsit, ka jaunā datu avota statuss ir **Atsvaidzina**.

## <a name="available-power-query-data-sources"></a>Pieejamie Power Query datu avoti

Informāciju par jaunākajiem savienotājiem, kurus varat atlasīt datu importēšanai uz Customer Insights skatiet [Power Query savienotāja atsaucē](/power-query/connectors/). 

Savienotāji ar atzīmi kolonnā **Customer Insights (Dataflows)** ir pieejami, lai izveidotu jaunus datu avotus, pamatojoties uz Power Query. Pārskatiet konkrētā savienotāja dokumentāciju, lai uzzinātu vairāk par tā priekšnosacījumiem, ierobežojumiem un citu informāciju.

## <a name="edit-power-query-data-sources"></a>Power Query datu avotu rediģēšana

> [!NOTE]
> Iespējams, nevarēs veikt izmaiņas datu avotos, kuri pašlaik tiek izmantoti kādā no programmas procesiem (piemēram, *segmentēšana*, *atbilstības noteikšana* vai *sapludināšana*). 
>
> Izmantojot lapu **Iestatījumi**, varat izsekot katra aktīvā procesa norisei. Kad process ir pabeigts, varat atgriezties lapā **Datu avoti** un veikt vajadzīgās izmaiņas.

1. Sadaļā Auditorijas ieskati skatiet **Dati** > **Datu avoti**.

2. Nolaižamajā izvēlnē atlasiet vertikālās līknes blakus datu avotam, kuru vēlaties mainīt un atlasiet **Rediģēt**.

   > [!div class="mx-imgBorder"]
   > ![Rediģēšanas opcija.](media/edit-option-data-sources.png "Rediģēšanas opcija")

3. Piemērojiet veiktās izmaiņas un transformācijas dialoglodziņā **Power Query — izmaiņu rediģēšana**, kā aprakstīts sadaļā [Jauna datu avota izveide](#create-a-new-data-source).

4. Lai saglabātu izmaiņas, pēc rediģēšanas pabeigšanas Power Query atlasiet **Saglabāt**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]