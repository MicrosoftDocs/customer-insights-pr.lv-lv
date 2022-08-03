---
title: Entitījas risinājumā Customer Insights.
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
ms.openlocfilehash: 0beaa46d47545ac195ced876b509dfc57821bfaf
ms.sourcegitcommit: ad74ace653db9a25fce4343adef7db1c9b0d8904
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 07/21/2022
ms.locfileid: "9183574"
---
# <a name="entities-in-customer-insights"></a>Entitījas risinājumā Customer Insights.

Pēc [datu avotu konfigurēšanas](data-sources.md) pārejiet uz lapu **Entītijas**, lai novērtētu uzņemto datu kvalitāti. Entītijas tiek uzskatītas par datu kopām. Dynamics 365 Customer Insights daudzās iespējas ir veidotas ap šīm entītijām. Rūpīga to pārskatīšana var palīdzēt pārbaudīt šo iespēju rezultātus.

Strādājot programmā Customer Insights, bagātinot datus vai veidojot segmentus, mērus un darbības, entītijas, kas izveidotas no šīm darbībām, tiek rādītas **lapā Entītijas**.

## <a name="view-a-list-of-entities"></a>Entītiju saraksta skatīšana

Dodieties uz **Datu** > **entītijas**, lai skatītu entītiju sarakstu. Tālāk sniegtā informācija tiek parādīta par katru entītiju.

- **Nosaukums**: datu elementa nosaukums. Ja blakus entītijas nosaukumam tiek rādīts brīdinājuma simbols, tas nozīmē, ka šīs entītijas dati netika veiksmīgi ielādēti.
- **Avots**: datu avots veids, kas pārņēma entītiju.
- **Atjaunināts**: laiks, kad entītija pēdējo reizi tika atjaunināta.
- **Statuss**: detalizēta informācija par entītijas pēdējo atjauninājumu.

## <a name="explore-a-specific-entitys-data"></a>Noteiktu entītijas datu izpēte

1. Dodieties uz **datu** > **entītijas**.
1. Atlasiet entītiju, lai atvērtu detalizētas informācijas lapu.  
1. Izpētiet dažādos šai entītijai iekļautos laukus un ierakstus.

- Cilne **Atribūti ir atlasīta** pēc noklusējuma, un tajā tiek rādīta detalizēta informācija par atlasīto entītiju, piemēram, lauku nosaukumi, datu tipi un tipi. Kolonnā **Tips** ir redzami kopējā datu modeļa saistītie tipi, ko ir automātiski identificējusi sistēma vai [manuāli kartējuši](map-entities.md) lietotāji. Šie tipi ir semantiskie tipi, kas var atšķirties no atribūtu datu tipiem. Piemēram, tālāk esošajā laukā *E-pasts* ir datu tips *Virkne*, bet tā (semantiskais) Common Data Model tips var būt *E-pasts*, *EmailAddress* vai *Identity.Service.Email*.

   :::image type="content" source="media/data-manager-entities-fields.png" alt-text="Tabula Lauki.":::

   > [!NOTE]
   > Šajā lapā tiek rādīts tikai jūsu entītijas datu paraugs. Lai skatītu pilnu datu kopu, dodieties uz **lapu Datu avoti**, atlasiet entītiju, atlasiet **Rediģēt** un pēc tam skatiet šīs entītijas datus ar Power Query redaktoru, kā paskaidrots sadaļā [Datu avoti](data-sources.md).

   Lai uzzinātu vairāk par entītijā uzņemtajiem datiem, **kolonnā Kopsavilkums** ir norādīti daži svarīgi datu raksturlielumi, piemēram, nulles, trūkstošās vērtības, unikālās vērtības, skaits un sadalījumi neatkarīgi no tā, kas ir piemērojams jūsu datiem. Atlasiet diagrammas ikonu, lai skatītu datu kopsavilkumu.

   :::image type="content" source="media/data-manager-entities-summary.png" alt-text="Datu kopsavilkuma tabula.":::

- Cilnē **Dati** tiek rādīta detalizēta informācija par atsevišķiem entītijas ierakstiem. Norādītā detalizētā informācija ir atkarīga no entītijas datu tipa.

   :::image type="content" source="media/data-manager-entities-data.png" alt-text="Atlasīt entītiju.":::

- Cilnē **Atskaites** (pieejama dažām entītijām) varat vizualizēt datus, izveidojot atskaiti, kurā iekļautas tālāk norādītās kolonnas.

  - **Atskaites nosaukums**: atskaites nosaukums.
  - **Izveidoja**: tās personas vārds, kura izveidoja entītiju.
  - **Izveidots**: entītijas izveides datums un laiks.
  - **Rediģēja**: tās personas vārds, kura modificēja entītiju.
  - **Rediģēts**: entītijas modificēšanas datums un laiks.

## <a name="entity-specific-information"></a>Noteiktas entītijas informācija

Nākamajā sadaļā ir sniegta informācija par dažām sistēmas izveidotām entītijām.

### <a name="corrupted-data-sources"></a>Bojāti datu avoti

Uzņemtu datu avotu lauki var saturēt bojātus datus. Ieraksti ar bojātiem laukiem tiek rādīti sistēmas izveidotās entītijās. Pārzināšana par bojātiem ierakstiem palīdz noteikt, kurus datus pārskatīt un atjaunināt avota sistēmā. Pēc nākamās datu avotu atsvaidzināšanas labotie ieraksti tiek lietoti programmā Customer Insights un nodoti lejupstraumes procesiem. 

Piemēram, kolonnas 'dzimšanas diena' datu tips ir iestatīts kā 'datums'. Klienta ieraksta dzimšanas diena ir ievadīta kā '01/01/19777'. Sistēma atzīmēs, ka šis ieraksts ir bojāts. Kāds tagad avota sistēmā var mainīt dzimšanas dienu uz '1977'. Pēc automātiskas datu avotu atsvaidzināšanas šim laukam tagad ir derīgs formāts, un ieraksts tiks noņemts no bojātās entītijas.

Pārejiet uz **Dati** > **Entītijas** un sadaļā **Sistēma** meklējiet bojātās entītijas. Bojātās entītijas nosaukumu shēma: "DataSourceName_EntityName_corrupt". Atlasiet bojātu entītiju, lai identificētu bojātos laukus un iemeslu atsevišķa ieraksta līmenī.

   :::image type="content" source="media/corruption-reason.png" alt-text="Korupcijas iemesls.":::

Customer Insights joprojām apstrādā bojātos ierakstus. Tomēr, strādājot ar vienotajiem datiem, tie var radīt problēmas.

Šādi ievadītie dati pārbauda, vai tiek rādīti bojāti ieraksti:

- Lauka vērtība neatbilst tā kolonnas datu tipam.
- Laukos ir rakstzīmes, kas liek kolonnai neatbilst gaidītajai shēmai. Piemēram: nepareizi formatēti piedāvājumi, nebeidzami piedāvājumi vai jaunas rindas rakstzīmes.
- Ja ir kolonnas datetime/datetime/datetimeoffset, to formāts ir jānorāda modelī, ja tas neatbilst standarta ISO formātam.

[!INCLUDE [footer-include](includes/footer-banner.md)]
