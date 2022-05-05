---
title: Semantiskie kartējumi (Priekšskatījums)
description: Pārskats par semantiskajiem kartējumiem un to lietošanu.
ms.date: 12/01/2021
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
searchScope:
- ci-semantic-mapping
- customerInsights
ms.openlocfilehash: a60855f6d5616ca9b958752836d1071ae3433db0
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643532"
---
# <a name="semantic-mappings-preview"></a>Semantiskie kartējumi (Priekšskatījums)

Semantiskie kartējumi ļauj kartēt datus, kas nav darbības dati, uz iepriekšdefinētām shēmām. Šīs shēmas palīdz Customer Insights labāk izprast jūsu datu atribūtus. Semantiskā kartēšana un sniegtie dati ļauj gūt jaunus ieskatus un līdzekļus customer insights. Lai darbības datus kartētu uz shēmām, pārskatiet [darbību ](activities.md) dokumentāciju.

**Semantiski kartējumi pašlaik ir iespējoti vidēm, kuru pamatā ir biznesa uzņēmumi**. *ContactProfile* ir vienīgais semantiskās kartēšanas veids, kas pašlaik ir pieejams customer insights.

## <a name="define-a-contactprofile-semantic-entity-mapping"></a>ContactProfile semantiskās entītijas kartējuma definēšana

1. Dodieties uz **DataSemantic** > **kartējumiem (priekšskatījums)**.

1. Atlasiet **Pievienot semantisko kartējumu**, lai sāktu vadīto pieredzi.

1. **Entītijas datu** solī iestatiet šo lauku vērtības:

   - **Semantiskās entītijas kartējuma nosaukums**: norādiet semantiskās entītijas kartējuma nosaukumu.
   - **Avota entītija**: atlasiet entītiju, kurā ir ietverti kontaktpersonu dati.
   - **Primārā atslēga**: Atlasiet lauku, kas unikāli identificē klienta ierakstu. Tajā nedrīkst ietvert dublētas vērtības, tukšas vērtības vai trūkstošas vērtības.

   :::image type="content" source="media/Semantic_Mapping_Wizard1.png" alt-text="Iestatiet semantiskās entītijas kartējumu ar nosaukumu, avota entītiju un primāro atslēgu.":::

1. Atlasiet **Tālāk**, lai turpinātu.

1. Solī **Attiecības** konfigurējiet detalizētu informāciju, lai kontaktpersonu datus savienotu ar atbilstošā konta datiem. Šajā darbībā tiek vizualizēts entītiju savienojums.  

   Ir divu tipu attiecību ceļi, ko var ieviest: **Tiešās attiecības** un **Netiešās attiecības**. Lai iegūtu papildinformāciju, atveriet [tiešo un netiešo attiecību ceļus](relationships.md#relationship-paths).

   1. Atlasiet **Pievienot attiecības**, lai konfigurētu attiecības.
   1. Izvēlieties atribūtu no avota entītijas, kas veido kontaktpersonas entītijas savienojumu ar citu entītiju.
   1. Izvēlieties entītiju, ar kuru veidot kontaktpersonas entītijas savienojumu. Entītiju var izvēlēties no sadaļas **Uzņēmuma entītijas** vai **Sekundāra entītija**. Ja atlasīsit sekundāru entītiju, ir jādefinē otra attiecība, lai izveidotu savienojumu ar mērķa uzņēmuma entītiju.

      :::image type="content" source="media/Semantic_Mapping_Wizard2.png" alt-text="Atlasiet uzņēmuma entītiju vai Sekundāru entītiju.":::

   1. Norādiet **Attiecību nosaukumu**. Ja attiecības starp entītijām jau pastāv, attiecību nosaukums ir tikai lasāms. Ja attiecību nav, tiks izveidotas jaunas attiecības ar jūsu norādīto nosaukumu.
   1. Atlasiet **Lietot**, lai pabeigtu attiecību konfigurāciju.

   > [!NOTE]
   > Varat konfigurēt vairāk attiecību starp kontaktpersonas entītiju un citām uzņēmuma entītijām, izmantojot sekundārās entītijas.
   >  :::image type="content" source="media/Semantic_Mapping_Wizard4.png" alt-text="Dažādu attiecību vizualizācija savieno kontaktpersonu entītijas ar uzņēmuma entītijām.":::

1. Kad esat beidzis ar attiecību konfigurāciju, atlasiet **Tālāk**.

1. Solī **Iestatīt semantisko tipu** izvēlieties **Semantisko tipu**. Pašlaik pastāv viens **Semantiskais tips** ar nosaukumu *ContactProfile*.

1. Kartējiet datus uz *ContactProfile* **Semantisko tipu** šādiem laukiem.
   - Obligātais lauks: Kontaktpersonas ID
   - Neobligātie lauki: vārds, uzvārds, dzimšanas datums, dzimums, galvenais e-pasts un galvenais telefona numurs

   :::image type="content" source="media/Semantic_Mapping_Wizard5.png" alt-text="Kartējiet kontaktpersonu datu atribūtus uz nodrošinātajiem obligātajiem un neobligātajiem laukiem.":::

1. Atlasiet **Tālāk**, lai turpinātu.

1. Solī **Pārskatīt** apskatiet semantiskās kartēšanas konfigurāciju. Lai veiktu izmaiņas, atbilstošajai sadaļai atlasiet **Rediģēt**.

1. Atlasiet **Saglabāt**, lai saglabātu jauno **Semantisko kartējumu**.

1. Pēc saglabāšanas varat atlasīt opciju **Palaist** semantiskā kartējuma procesu, vai arī varat atlasīt **Aizvērt**, lai saglabātu semantisko kartējumu, neapstrādājot to.

1. Lai palaistu semantisko kartējumu vēlāk, atlasiet semantisko kartējumu opciju un atlasiet **Atsvaidzināt**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="manage-existing-semantic-mappings"></a>Pārvaldīt esošos semantiskos kartējumus

Sadaļā **Dati** > **Semantiskie kartējumi (priekšskatījums)** varat skatīt un pārvaldīt visus saglabātos semantiskos kartējumus. Katrs semantiskais kartējums tiek attēlots ar atsevišķu rindu. Detalizēta informācija par avota entītiju, semantisko tipu, kartēšanas tipu un tās statusu.

:::image type="content" source="media/semantic-mapping-options.png" alt-text="Semantisko kartējumu pārvaldīšanas opcijas.":::

- **Rediģēt**: pārskatīšanas solī tiek atvērta semantiskā kartējuma iestatījumu konfigurācija. Varat mainīt pašreizējo konfigurāciju. Lai apstrādātu izmaiņas, atlasiet **Saglabāt** un **Palaist**.

- **Atsvaidzināt**: atsvaidzina atlasīto s savietošanas kartējumu ar visjaunākajiem datiem no entītijām, kas ir daļa no konfigurācijas. Atsvaidzinot jebkuru doto semantisko kartējumu, tiks atsvaidzināti visi viena semantiskā tipa kartējumi.

- **Pārdēvēt**: atver dialogu, kurā var ievadīt citu atlasītā semantiskā kartējuma nosaukumu. Lai veiktās izmaiņas stātos spēkā, atlasiet **Saglabāt**.

- **Dzēst**: atver dialogu, lai apstiprinātu atlasītā semantiskā kartējuma dzēšanu. Atlasot semantiskos kartējumus un dzēšanas ikonu, vienlaicīgi var izdzēst arī vairākus semantiskos kartējumus. Lai apstiprinātu dzēšanu, atlasiet **Dzēst**.

## <a name="use-a-contactprofile-semantic-entity-mapping-to-create-contact-level-activities"></a>ContactProfile semantiskās entītijas kartējuma izmantošana, lai izveidotu kontaktu līmeņa aktivitātes

Pēc ContactProfile *semantiskās entītijas kartējuma izveides* varat tvert kontaktpersonu darbības. Tas ļauj darbību laika grafikā redzēt uzņēmumam, kura kontaktpersona bija atbildīga par katru darbību. Lielākā daļa darbību atbilst tipiskajai aktivitāšu kartēšanas konfigurācijai.

   > [!NOTE]
   > Lai kontaktpersonas līmeņa darbības darbotos, katram ierakstam darbību datos ir jābūt atribūtiem **Gan AccountID**, gan **ContactID**.

1. [Definējiet *ContactProfile* semantisko entītiju kartējumu.](#define-a-contactprofile-semantic-entity-mapping) Un palaidiet semantisko kartēšanu.

1. Dodieties uz **DataActivities** > **·**.

1. Atlasiet **Pievienot darbību**, lai izveidotu jaunu darbību.

1. Piešķiriet aktivitātei nosaukumu, atlasiet avota aktivitātes entītiju un atlasiet aktivitātes entītijas primāro atslēgu.

1. Solī Relācijas **izveidojiet** netiešas attiecības starp darbības avota datiem ar uzņēmumiem, izmantojot savus kontaktpersonas datus kā starpniekstruktūru. Plašāku informāciju skatiet [tiešās un netiešās attiecību trajektorijās](relationships.md#relationship-paths).
   - Darbības ar nosaukumu *Iepirkumi* attiecību piemērs:
      - **Iepirkumi Avota darbības datiKontakti** > **Dati** par atribūtu **ContactID**
      - **Kontaktpersonas datiKonta** > **dati** par atribūtu **AccountID**

   :::image type="content" source="media/Contact_Activities1.png" alt-text="Attiecību iestatīšanas piemērs.":::

1. Pēc relāciju iestatīšanas atlasiet **Tālāk** un pabeidziet darbību kartēšanas konfigurāciju. Detalizētus darbības par aktivitātes izveidi skatiet rakstā [Aktivitātes](activities.md) definēšana.

1. Palaidiet savu darbību kartējumus.

1. Kontaktpersonas līmeņa darbības tagad būs redzamas jūsu klientu laika skalā.

   :::image type="content" source="media/Contact_Activities2.png" alt-text="Gala rezultāts pēc kontaktpersonu darbību konfigurēšanas":::

### <a name="contact-level-activity-timeline-filtering"></a>Kontaktpersonas līmeņa aktivitāšu laika grafika filtrēšana

Pēc kontaktpersonas līmeņa aktivitāšu kartējuma konfigurēšanas un palaišanas klientiem tiks atjaunināts darbību laika grafiks. Atkarībā no *ContactProfile* konfigurācijas tas ietver viņu ID vai nosaukumus darbībām, ar kurām viņi rīkojās. Varat filtrēt darbības pēc kontaktpersonām laika skalā, lai skatītu konkrētas interesējošas kontaktpersonas. Turklāt visas darbības, kas nav piešķirtas konkrētai kontaktpersonai, var redzēt, atlasot **Darbības, kas nav kartētas uz kontaktpersonu**.

   :::image type="content" source="media/Contact_Activities3.png" alt-text="Filtrēšanas opcijas, kas pieejamas kontaktu līmeņa aktivitātēm.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
