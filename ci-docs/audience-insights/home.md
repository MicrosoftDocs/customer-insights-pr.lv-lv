---
title: Sākumlapa rīkā auditorijas ieskati
description: Sāciet lietotnes izpēti sākumlapā.
ms.date: 01/07/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: bf9080c564850bca0c239b7317eed2fc0f77d9f3
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597244"
---
# <a name="create-a-new-environment"></a>Izveidot jaunu vidi

## <a name="create-a-trial-environment"></a>Izveidojiet izmēģinājuma vidi

Izmēģinājumam varat pierakstīties [izmēģinājuma pierakstīšanās lapā](https://dynamics.microsoft.com/get-started/free-trial/?appname=customerinsights). 

> [!NOTE]
> Izmēģinājumu termiņš beidzas pēc 30 dienām.

1. Izvēlieties opciju **Pieteikties bezmaksas izmēģinājumam** un atlasiet **Pieteikties tūlīt**.

1. Norādiet darba vai mācību e-pasta adresi, pastāstiet vairāk par sevi un atlasiet **Tālāk**.

   :::image type="content" source="media/trial-signup-dialog.png" alt-text="Dialogs, lai reģistrētos izmēģinājuma instancē":::

1. Norādiet savas jaunās vides **nosaukumu**. 

1. Atlasiet izmēģinājuma veidu.

1. Atlasiet vides **Reģionu**.

1. Dynamics 365 organizācijas administratoriem, neobligāti: Atlasiet **Papildu iestatījumi** un sniedziet savas organizācijas URL, lai izmantotu prognozēšanas līdzekļus, piemēram, klientu zudumu.

1. Atlasiet **Izveidot**. 

Pēc vides izveides jūs redzēsit **Demonstrācijas** vidi, kura ļaus izpētīt programmu, izmantojot izdomātus datus. Varat mainīt parauga datus tā, lai tie atbilstu jūsu nozarei. Galvenē atlasiet ikonu **Iestatījumi** un atlasiet **Demonstrācijas iestatījumi**. Turklāt jūs varat arī mainīt vizuālo dizainu. 

Lai strādātu ar saviem datiem, jūs [pārslēdzaties uz vidi](#switch-environments), kuru izveidojāt pieteikšanās procesa laikā.

## <a name="create-a-new-production-or-sandbox-environment"></a>Izveidojiet jaunu ražošanas vai smilškastes vidi

Savā vidē atlasiet **Vides** atlasītāju programmas galvene un atlasiet opciju **Jauns**.

[Izmēģinājuma vides izveides laikā](#create-a-trial-environment) izpildies darbības. Dati pēc noklusējuma tiek glabāti Customer Insights pārvaldītā datu ezerā. Atlasot **Papildu iestatījumus** jums piešķirs papildu opciju uzglabāt savus datus pašiem sazā Azure Data Lake. Lai nodibinātu savienojumu ar Azure Data Lake, norādiet uzņēmuma nosaukumu un uzņēmuma atslēgu. 

> [!IMPORTANT]
> Saglabājot datus Azure Data Lake Storage, jūs piekrītat, ka dati tiks pārsūtīti un glabāti attiecīgajam Azure krātuves kontam atbilstošajā ģeogrāfiskās atrašanās vietā, kas var atšķirties no vietas, kurā tiek glabāti Dynamics 365 Customer Insights. [Uzziniet vairāk Microsoft Trust Center.](https://www.microsoft.com/trust-center)

## <a name="explore-the-home-page"></a>Sākumlapas izpēte

Jūs varat [piekļūt auditorijas ieskatiem no programmas Dynamics 365 Customer Insights](https://home.ci.ai.dynamics.com/) sekojošajā URL: [https://home.ci.ai.dynamics.com/](https://home.ci.ai.dynamics.com/).
**Sākumlapa** parāda pārskatu par segmentiem, pasākumiem un bagātināšanas datiem (ja konfigurēts) pēc [kartēšanas](map-entities.md), [saskaņošanas](match-entities.md) un [apvienošanas](merge-entities.md) fāžu pabeigšanas.

> [!div class="mx-imgBorder"] 
> ![Ieskati sākumlapā](media/home-page-insights.png "Ieskati sākumlapā")

Sadaļā **Nesen izmantotie segmenti** tiek rādītas klientu grupas, pamatojoties uz jūsu definētajiem demogrāfiskajiem, uzvedības vai transakciju atribūtiem. [Izveidojot segmentus](segments.md), varat grupēt klientu bāzi un labāk izvēlēties uzņēmējdarbības mērķauditoriju.

**Pēdējie pasākumi** parāda elementus ar jūsu definētajiem [izpildes pamatrādītājiem (KPI)](measures.md). Piemēram, klienta vidējā iespējamība vai vidējie tiešsaistes izdevumi vienam klientam.

Sadaļā **Nesen izmantotie bagātinājumi** uzskaitīti nesen pabeigtās bagātinājumu izpildes rezultāti. [Bagātinājumi](enrichment-hub.md) pievieno informāciju jūsu klientu bāzei. Piemēram, izprotot intereses un zīmolus, kas viņiem simpatizē.

## <a name="switch-environments"></a>Pārslēgt vides

Lai mainītu vides, lapas augšējā labajā stūrī atlasiet vadīklu **Vide**.

> [!div class="mx-imgBorder"] 
> ![Mainīt vidi](media/home-page-environment-switcher.png "Mainīt vidi")

Administratori var izveidot un pārvaldīt [vairākas vides](manage-environments.md). Vairāk nekā viena vide var būt noderīga, ja, piemēram, jūsu organizācija darbojas starptautiski un jums ir nepieciešams nodalīt datus un ieskatus dažādos veidos.

## <a name="next-step"></a>Nākamā darbība

Lai skatītu savus ieskatus sākumlapā, vispirms ir [jāpievieno datu avoti](data-sources.md) un [jāapvieno](data-unification.md) jūsu dati, lai izveidotu klientu profilus.


[!INCLUDE[footer-include](../includes/footer-banner.md)]