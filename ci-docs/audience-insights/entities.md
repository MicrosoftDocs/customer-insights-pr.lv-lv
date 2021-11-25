---
title: Entītijas un datu kopas.
description: Datu skatīšana Entītiju lapā.
ms.date: 11/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 2a207a3dcad4bf192efb6ee1554195f10b19670b
ms.sourcegitcommit: 834651b933b1e50e7557d44f926a3fb757c1f83a
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 11/02/2021
ms.locfileid: "7732089"
---
# <a name="entities-in-audience-insights"></a>Entītijas auditorijas ieskatiem

Pēc [datu avotu konfigurēšanas](data-sources.md) pārejiet uz lapu [Entītijas](data-sources.md), lai novērtētu uzņemto datu kvalitāti. Entītijas tiek uzskatītas par datu kopām. Ap šīm entītijām ir veidotas vairākas Dynamics 365 Customer Insights iespējas. Rūpīga to pārskatīšana var palīdzēt pārbaudīt šo iespēju rezultātus.

Lapā **Entītijas** tiek norādītas entītijas, un tajā ir vairākas kolonnas.

- **Nosaukums**: Datu entītijas nosaukums. Ja blakus entītijas nosaukumam tiek rādīts brīdinājuma simbols, tas nozīmē, ka šīs entītijas dati netika veiksmīgi ielādēti.
- **Avots**: Tas datu avota veids, kas uzņēma entītiju
- **Izveidoja**: Tās personas vārds, kura izveidoja šo entītiju
- **Izveidots**: Entītijas izveides datums un laiks
- **Atjaunināts** : tās personas vārds, kura atjaunināja entītiju
- **Statuss** : detalizēta informācija par entītijas pēdējo atjauninājumu

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="explore-a-specific-entitys-data"></a>Noteiktu entītijas datu izpēte

Atlasiet entītiju, lai izpētītu tajā ietvertos dažādos laukus un ierakstus.

> [!div class="mx-imgBorder"]
> ![Atlasīt entītiju.](media/data-manager-entities-data.png "Entītijas atlase")

- Cilnē **Dati** ir redzama tabulas detalizēta informācija par atsevišķiem entītijas ierakstiem.

> [!div class="mx-imgBorder"]
> ![Tabula Lauki.](media/data-manager-entities-fields.PNG "Tabula Lauki")

- Pēc noklusējuma ir atlasīta cilne **Atribūti**, un tajā ir redzama tabula, lai pārskatītu atlasītās entītijas detalizēto informāciju, piemēram, lauku nosaukumus, datu tipus un tipus. Kolonnā **Tips** ir redzami kopējā datu modeļa saistītie tipi, ko ir automātiski identificējusi sistēma vai [manuāli kartējuši](map-entities.md) lietotāji. Šie tipi ir semantiskie tipi, kas var atšķirties no atribūtu datu tipiem. Piemēram, tālāk redzamajam laukam *E-pasts* ir datu tips *Teksts*, bet tā (semantiskais) Common Data Model tips var būt *E-pasts* vai *E-pasta adrese*.

> [!NOTE]
> Abās tabulās ir redzams tikai entītijas datu paraugs. Lai skatītu pilnu datu kopu, atveriet lapu **Datu avoti**, atlasiet entītiju, atlasiet **Rediģēt** un pēc tam skatiet šīs entītijas datus, izmantojot Power Query redaktoru, kā paskaidrots tēmā [Datu avoti](data-sources.md).

Lai uzzinātu vairāk par entītijā pieņemtajiem datiem, kolonnā **Kopsavilkums** ir norādītas svarīgas datu īpašības, piemēram, vērtības Null, trūkstošās vērtības, unikālās vērtības, skaits un izplatīšanas reižu skaits attiecībā uz jūsu datiem.

Atlasiet diagrammas ikonu, lai skatītu datu kopsavilkumu.

> [!div class="mx-imgBorder"]
> ![Kopsavilkuma simbols.](media/data-manager-entities-summary.png "Tabula Datu kopsavilkums")

## <a name="entity-specific-information"></a>Noteiktas entītijas informācija

Nākamajā sadaļā ir sniegta informācija par dažām sistēmas izveidotām entītijām.

### <a name="corrupted-data-sources"></a>Bojāti datu avoti

Uzņemtu datu avotu lauki var saturēt bojātus datus. Ieraksti ar bojātiem laukiem tiek rādīti sistēmas izveidotās entītijās. Pārzināšana par bojātiem ierakstiem palīdz noteikt, kurus datus pārskatīt un atjaunināt avota sistēmā. Pēc nākamās datu avotu atsvaidzināšanas labotie ieraksti tiek lietoti programmā Customer Insights un nodoti lejupstraumes procesiem. 

Piemēram, kolonnas 'dzimšanas diena' datu tips ir iestatīts kā 'datums'. Klienta ieraksta dzimšanas diena ir ievadīta kā '01/01/19777'. Sistēma atzīmēs, ka šis ieraksts ir bojāts. Kāds tagad avota sistēmā var mainīt dzimšanas dienu uz '1977'. Pēc automātiskas datu avotu atsvaidzināšanas šim laukam tagad ir derīgs formāts, un ieraksts tiks noņemts no bojātās entītijas. 

Pārejiet uz **Dati** > **Entītijas** un sadaļā **Sistēma** meklējiet bojātās entītijas. Bojātās entītijas nosaukumu shēma: "DataSourceName_EntityName_corrupt".

Customer Insights joprojām apstrādā bojātos ierakstus. Tomēr, strādājot ar vienotajiem datiem, tie var radīt problēmas.

Šādi ievadītie dati pārbauda, vai tiek rādīti bojāti ieraksti: 

- Lauka vērtība neatbilst tā kolonnas datu tipam.
- Laukos ir rakstzīmes, kas liek kolonnai neatbilst gaidītajai shēmai. Piemēram: nepareizi formatēti piedāvājumi, nebeidzami piedāvājumi vai jaunas rindas rakstzīmes.
- Ja ir datuma un laika/datuma/datuma/datuma_laika_kopas kolonnas, to formāts ir jānorāda modelī, ja tas neatbilst standarta ISO formātam.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
