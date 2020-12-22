---
title: Sākumlapa rīkā auditorijas ieskati
description: Sāciet lietotnes izpēti sākumlapā.
ms.date: 09/30/2020
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: bd16966eabb126d9c9945ededc53273df02c3369
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406350"
---
# <a name="create-a-new-environment"></a>Izveidot jaunu vidi

## <a name="create-a-trial-environment"></a>Izveidojiet izmēģinājuma vidi

Izmēģinājumam varat pierakstīties [izmēģinājuma pierakstīšanās lapā](https://dynamics.microsoft.com/get-started/free-trial/?appname=customerinsights). 

> [!NOTE]
> Izmēģinājumu termiņš beidzas pēc 30 dienām.

1. Izvēlieties opciju **Pieteikties bezmaksas izmēģinājumam** un atlasiet **Pieteikties tūlīt**.

1. Norādiet darba vai mācību e-pasta adresi, pastāstiet vairāk par sevi un atlasiet **Tālāk**.

1. Norādiet savas jaunās vides **nosaukumu**. 

1. Atlasiet izmēģinājuma veidu.

1. Atlasiet vides **Reģionu**.

1. Dynamics 365 organizācijas administratoriem, neobligāti: Atlasiet **Papildu iestatījumi** un sniedziet savas organizācijas URL, lai izmantotu prognozēšanas līdzekļus, piemēram, klientu zudumu.

1. Atlasiet **Izveidot**. 

Pēc vides izveides jūs redzēsit **Demonstrācijas** vidi, kura ļaus izpētīt programmu, izmantojot izdomātus datus. Varat mainīt parauga datus tā, lai tie atbilstu jūsu nozarei. Galvenē atlasiet ikonu **Iestatījumi** un atlasiet **Demonstrācijas iestatījumi**. Turklāt jūs varat arī mainīt vizuālo dizainu. 

Lai strādātu ar saviem datiem, jūs [pārslēdzaties uz vidi](#change-between-environments), kuru izveidojāt pieteikšanās procesa laikā.

## <a name="create-a-new-production-or-sandbox-environment"></a>Izveidojiet jaunu ražošanas vai smilškastes vidi

Vides galvenē atlasiet **Iestatījumu** ikonu un atlasiet **Jauna vide**.

[Izmēģinājuma vides izveides laikā](#create-a-trial-environment) izpildies darbības. Atlasot **Papildu iestatījumus** jums piešķirs papildu opciju uzglabāt savus datus pašiem sazā Azure Data Lake. Lai nodibinātu savienojumu ar Azure Data Lake, norādiet uzņēmuma nosaukumu un uzņēmuma atslēgu. Dati pēc noklusējuma tiek glabāti Customer Insights pārvaldītā datu ezerā.

> [!IMPORTANT]
> Saglabājot datus Azure Data Lake Storage, jūs piekrītat, ka dati tiks pārsūtīti un glabāti attiecīgajam Azure krātuves kontam atbilstošajā ģeogrāfiskās atrašanās vietā, kas var atšķirties no vietas, kurā tiek glabāti Dynamics 365 Customer Insights. [Uzziniet vairāk Microsoft Trust Center.](https://www.microsoft.com/trust-center)

## <a name="explore-the-home-page"></a>Sākumlapas izpēte

[Savai Customer Insights videi](https://home.ci.ai.dynamics.com/) varat piekļūt, izmantojot šādu vietrādi URL: [https://home.ci.ai.dynamics.com/](https://home.ci.ai.dynamics.com/).
**Sākuma** lapā ir sniegts pārskats par jūsu klientu bāzi un galvenajām metrikām, lai izsekotu sava biznesa statusu.

> [!div class="mx-imgBorder"] 
> ![Ieskati sākumlapā](media/home-page-insights.png "Ieskati sākumlapā")

Sadaļā **Nesen izmantotie segmenti** tiek rādītas klientu grupas, pamatojoties uz jūsu definētajiem demogrāfiskajiem, uzvedības vai transakciju atribūtiem. [Segmentu izveide](segments.md) palīdz uzlabot uzņēmuma darbības mērķi.

**Nesen izmantotie mēri** rāda elementus ar [mēriem](measures.md). Šie mēri ir jūsu definētie izpildes pamatrādītāji (KPI). Piemēram, vidējā iespējamība zaudēt klientu vai klienta vidējais tiešsaistē pavadītais laiks.

Sadaļā **Nesen izmantotie bagātinājumi** uzskaitīti nesen pabeigtās bagātinājumu izpildes rezultāti. Bagātinājumi pievieno informāciju jūsu klientu bāzei. Piemēram, izprotot intereses un zīmolus, kas viņiem simpatizē. Šo informāciju var atbloķēt, izmantojot [bagātināšanās](enrichment-microsoft-graph.md) iespējas pēc tādu fāžu pabeigšanas kā [kartēšana](map-entities.md)[atbilstība](match-entities.md) un [sapludināšana](merge-entities.md).

## <a name="change-between-environments"></a>Maiņa starp vidēm

Kad ir iestatīti un konfigurēti [datu avoti](data-sources.md), jūs vēlēsieties pārslēgties no demonstrācijas vides uz dzīvo vidi. Izmantojot ražošanas vidi, varat strādāt ar savu klientu datiem. Lai mainītu vides, lapas augšējā labajā stūrī atlasiet vadīklu **Vide**.

> [!div class="mx-imgBorder"] 
> ![Mainīt vidi](media/home-page-environment-switcher.png "Mainīt vidi")

Administratori var izveidot un pārvaldīt [vairākas vides](manage-environments.md). Vairāk nekā viena vide var būt noderīga, ja, piemēram, jūsu organizācija darbojas starptautiski un jums ir nepieciešams nodalīt datus un ieskatus dažādos veidos.

## <a name="next-step"></a>Nākamā darbība

Lai skatītu savus ieskatus sākumlapā, vispirms ir [jāpievieno datu avoti](data-sources.md) un [jāapvieno](data-unification.md) jūsu dati, lai izveidotu klientu profilus.
