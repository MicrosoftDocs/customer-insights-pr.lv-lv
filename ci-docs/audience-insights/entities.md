---
title: Entītijas un datu kopas.
description: Datu skatīšana Entītiju lapā.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-entities
- customerInsight
ms.openlocfilehash: 1e1abdf49a3c1fe6f9fdd2cf5353a7723454f47b
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 02/25/2022
ms.locfileid: "8355307"
---
# <a name="entities-in-audience-insights"></a>Entītijas auditorijas ieskatiem

Pēc [datu avotu konfigurēšanas](data-sources.md) pārejiet uz lapu **Entītijas**, lai novērtētu uzņemto datu kvalitāti. Entītijas tiek uzskatītas par datu kopām. Dynamics 365 Customer Insights daudzās iespējas ir veidotas ap šīm entītijām. Rūpīga to pārskatīšana var palīdzēt pārbaudīt šo iespēju rezultātus.

Lapā Entītijas **ir** uzskaitītas entītijas un iekļautas šīs kolonnas:

- **Nosaukums**: datu entītijas nosaukums. Ja blakus entītijas nosaukumam tiek rādīts brīdinājuma simbols, tas nozīmē, ka šīs entītijas dati netika veiksmīgi ielādēti.
- **Avots**: datu avots tips, kas uztrīja entītiju.
- **Atjaunināts**: entītijas pēdējās atjaunināšanas laiks.
- **Statuss**: detalizēta informācija par entītijas pēdējo atjauninājumu.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="explore-a-specific-entitys-data"></a>Noteiktu entītijas datu izpēte

1. Sadaļā Auditorijas ieskati skatiet **Dati** > **Entītijas**.
1. **Lapā Entītijas** atlasiet entītiju, lai atvērtu detalizētas informācijas lapu.  
1. Izpētiet dažādus šai entītijai iekļautos laukus un ierakstus.

- Pēc noklusējuma ir atlasīta cilne **Atribūti**, un tajā ir redzama tabula, lai pārskatītu atlasītās entītijas detalizēto informāciju, piemēram, lauku nosaukumus, datu tipus un tipus. Kolonnā **Tips** ir redzami kopējā datu modeļa saistītie tipi, ko ir automātiski identificējusi sistēma vai [manuāli kartējuši](map-entities.md) lietotāji. Šie tipi ir semantiskie tipi, kas var atšķirties no atribūtu datu tipiem. Piemēram, tālāk redzamajam laukam *E-pasts* ir datu tips *Teksts*, bet tā (semantiskais) Common Data Model tips var būt *E-pasts* vai *E-pasta adrese*.

> [!div class="mx-imgBorder"]
> ![Tabula Lauki.](media/data-manager-entities-fields.PNG "Tabula Lauki")

> [!NOTE]
> Šajā lapā tiek rādīts tikai jūsu entītijas datu paraugs. Lai skatītu pilnu datu kopu, dodieties uz **lapu Datu avoti**, atlasiet entītiju, atlasiet **Rediģēt** un pēc tam skatiet šīs entītijas datus ar Power Query redaktoru, kā paskaidrots datu [avotos](data-sources.md).

Lai uzzinātu vairāk par entītijā pieņemtajiem datiem, kolonnā **Kopsavilkums** ir norādītas svarīgas datu īpašības, piemēram, vērtības Null, trūkstošās vērtības, unikālās vērtības, skaits un izplatīšanas reižu skaits attiecībā uz jūsu datiem. Atlasiet diagrammas ikonu, lai skatītu datu kopsavilkumu.

> [!div class="mx-imgBorder"]
> ![Kopsavilkuma simbols.](media/data-manager-entities-summary.png "Tabula Datu kopsavilkums")

- Cilnē **Dati** ir redzama tabulas detalizēta informācija par atsevišķiem entītijas ierakstiem. Norādītā informācija ir atkarīga no entītijas datu tipa.

> [!div class="mx-imgBorder"]
> ![Atlasīt entītiju.](media/data-manager-entities-data.png "Entītijas atlase")

- Cilne **Atskaites** (pieejama dažām entītijām) ļauj vizualizēt datus, izveidojot atskaiti, un ietver šīs kolonnas:

  - **Atskaites nosaukums**: Atskaites nosaukums.
  - **Izveidoja**: tās personas vārds, kura izveidoja entītiju.
  - **Izveidots**: entītijas izveides datums un laiks.
  - **Rediģējis**: tās personas vārds, kura modificēja entītiju.
  - **Rediģēts**: entītijas modificēšanas datums un laiks. 

## <a name="entity-specific-information"></a>Noteiktas entītijas informācija

Nākamajā sadaļā ir sniegta informācija par dažām sistēmas izveidotām entītijām.

### <a name="corrupted-data-sources"></a>Bojāti datu avoti

Uzņemtu datu avotu lauki var saturēt bojātus datus. Ieraksti ar bojātiem laukiem tiek rādīti sistēmas izveidotās entītijās. Pārzināšana par bojātiem ierakstiem palīdz noteikt, kurus datus pārskatīt un atjaunināt avota sistēmā. Pēc nākamās datu avotu atsvaidzināšanas labotie ieraksti tiek lietoti programmā Customer Insights un nodoti lejupstraumes procesiem. 

Piemēram, kolonnas 'dzimšanas diena' datu tips ir iestatīts kā 'datums'. Klienta ieraksta dzimšanas diena ir ievadīta kā '01/01/19777'. Sistēma atzīmēs, ka šis ieraksts ir bojāts. Kāds tagad avota sistēmā var mainīt dzimšanas dienu uz '1977'. Pēc automātiskas datu avotu atsvaidzināšanas šim laukam tagad ir derīgs formāts, un ieraksts tiks noņemts no bojātās entītijas. 

Pārejiet uz **Dati** > **Entītijas** un sadaļā **Sistēma** meklējiet bojātās entītijas. Bojātās entītijas nosaukumu shēma: "DataSourceName_EntityName_corrupt". Atlasiet bojātu entītiju, lai identificētu visus bojātos laukus un iemeslu individuālā ieraksta līmenī.
> [!div class="mx-imgBorder"]
> ![Korupcijas iemesls.](media/corruption-reason.png "Korupcijas iemesls")

Customer Insights joprojām apstrādā bojātos ierakstus. Tomēr, strādājot ar vienotajiem datiem, tie var radīt problēmas.

Šādi ievadītie dati pārbauda, vai tiek rādīti bojāti ieraksti: 

- Lauka vērtība neatbilst tā kolonnas datu tipam.
- Laukos ir rakstzīmes, kas liek kolonnai neatbilst gaidītajai shēmai. Piemēram: nepareizi formatēti piedāvājumi, nebeidzami piedāvājumi vai jaunas rindas rakstzīmes.
- Ja ir datuma/datuma/datuma un datuma izslēgšanas kolonnas, to formāts ir jānorāda modelī, ja tas neatbilst standarta ISO formātam.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
