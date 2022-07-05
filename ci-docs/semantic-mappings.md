---
title: Semantiskie kartējumi (priekšskatījums)
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
ms.openlocfilehash: b3a0643ab71c98ce212f4e4581a584d8382c67eb
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 06/29/2022
ms.locfileid: "9083145"
---
# <a name="semantic-mappings-preview"></a>Semantiskie kartējumi (priekšskatījums)

Semantiskie kartējumi ļauj kartēt datus, kas nav darbības dati, uz iepriekšdefinētām shēmām. Šīs shēmas palīdz programmai Customer Insights labāk izprast jūsu datu atribūtus. Semantiskā kartēšana un sniegtie dati ļauj gūt jaunus ieskatus un līdzekļus programmā Customer Insights. Lai darbības datus kartētu uz shēmām, pārskatiet [darbību ](activities.md) dokumentāciju.

**Semantiski kartējumi pašlaik ir iespējoti vidēm, kuru pamatā ir biznesa uzņēmumi**. *ContactProfile* ir vienīgais semantiskās kartēšanas veids, kas pašlaik ir pieejams programmā Customer Insights.

## <a name="define-a-contactprofile-semantic-entity-mapping"></a>ContactProfile semantiskās entītijas kartējuma definēšana

1. Dodieties uz **Datu** > **semantiskie kartējumi (priekšskatījums)**.

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

## <a name="use-a-contactprofile-semantic-entity-mapping-to-create-contact-level-activities"></a>ContactProfile semantiskās entītijas kartēšanas izmantošana, lai izveidotu kontaktpersonas līmeņa darbības

Pēc ContactProfile *semantiskās entītijas kartēšanas izveides* varat tvert kontaktpersonu darbības. Tas ļauj jums redzēt konta darbību laika grafikā, kura kontaktpersona bija atbildīga par katru darbību. Lielākā daļa darbību tiek veiktas pēc tipiskās darbību kartēšanas konfigurācijas.

   > [!NOTE]
   > Lai kontaktpersonas līmeņa darbības darbotos, katram ierakstam jūsu darbības datos ir jābūt gan **accountID**, gan **contactid** atribūtiem.

1. [*Definējiet ContactProfile* semantisko entītiju kartēšanu.](#define-a-contactprofile-semantic-entity-mapping) Un palaist semantisko kartēšanu.

1. Dodieties uz **datu** > **aktivitātes**.

1. Atlasiet **Pievienot darbību**, lai izveidotu jaunu darbību.

1. Piešķiriet darbībai nosaukumu, atlasiet avota darbības entītiju un atlasiet darbības entītijas primāro atslēgu.

1. **Darbībā Relācijas** izveidojiet netiešu relāciju starp saviem darbības avota datiem un kontiem, izmantojot savus kontaktdatus kā starpniekuzņēmumu. Papildinformāciju skatiet tiešo [un netiešo attiecību ceļos](relationships.md#relationship-paths).
   - Relācijas piemērs darbībai ar nosaukumu *Pirkumi*:
      - **Iegādājas avota darbības datu** > **kontaktinformāciju** atribūtā **ContactID**
      - **·** > **Kontaktinformācijas konta dati** atribūtā **AccountID**

   :::image type="content" source="media/Contact_Activities1.png" alt-text="Relāciju iestatīšanas piemērs.":::

1. Pēc relāciju iestatīšanas atlasiet **Tālāk** un pabeidziet darbību kartēšanas konfigurēšanu. Detalizētus soļus par darbību izveidi skatiet sadaļā [Darbības](activities.md) definēšana.

1. Palaidiet savu darbību kartēšanu.

1. Jūsu kontaktpersonas līmeņa darbības tagad būs redzamas jūsu klientu laika skalā.

   :::image type="content" source="media/Contact_Activities2.png" alt-text="Galīgais rezultāts pēc kontakta darbību konfigurēšanas":::

### <a name="contact-level-activity-timeline-filtering"></a>Kontaktpersonu līmeņa darbību laika grafika filtrēšana

Pēc kontaktpersonas līmeņa darbību kartēšanas konfigurēšanas un tās palaišanas jūsu klientu darbību laika grafiks tiks atjaunināts. Tas ietver viņu ID vai vārdus, atkarībā no jūsu *ContactProfile* konfigurācijas, darbībām, ar kurām viņi rīkojās. Laika skalā varat filtrēt kontaktpersonu darbības, lai skatītu konkrētas jūs interesējošas kontaktpersonas. Turklāt visas darbības, kas nav piešķirtas konkrētai kontaktpersonai, varat skatīt, atlasot **Darbības, kas nav kartētas uz kontaktpersonu**.

   :::image type="content" source="media/Contact_Activities3.png" alt-text="Filtrēšanas opcijas, kas pieejamas kontaktpersonu līmeņa darbībām.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
