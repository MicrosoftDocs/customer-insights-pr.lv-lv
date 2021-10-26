---
title: Semantiskie kartējumi (Priekšskatījums)
description: Pārskats par semantiskajiem kartējumiem un to lietošanu.
ms.date: 09/28/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
ms.openlocfilehash: b0884b8b6a2c5abe4b3967d1b57d11a3a6d65c5b
ms.sourcegitcommit: 5d82e5b808517e0e99fdfdd7e4a4422a5b8ebd5c
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 10/11/2021
ms.locfileid: "7622944"
---
# <a name="semantic-mappings"></a>Semantiskie kartējumi

Semantiskie kartējumi ļauj kartēt datus, kas nav darbības dati, uz iepriekšdefinētām shēmām. Šīs shēmas palīdz auditorijas ieskatiem labāk izprast datu atribūtus. Semantiskā kartēšana un nodrošinātie dati ļauj gūt jaunus ieskatus un līdzekļus auditorijas ieskatos. Lai darbības datus kartētu uz shēmām, pārskatiet [darbību ](activities.md) dokumentāciju.

**Semantiski kartējumi pašlaik ir iespējoti vidēm, kuru pamatā ir biznesa uzņēmumi**. *ContactProfile* ir vienīgais semantisko kartējumu veids, kas pašlaik ir pieejams auditorijas ieskatos.

## <a name="define-a-contactprofile-semantic-entity-mapping"></a>ContactProfile semantiskās entītijas kartējuma definēšana

1. Auditorijas ieskatos dodieties uz **Dati** > **Semantiskie kartējumi (priekšskatījums)**.

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

> [!TIP]
> Uzdevumiem/procesiem ir [seši statusu tipi](system.md#status-types). Turklāt vairums procesu [ir atkarīgi no citiem pakārtotiem procesiem](system.md#refresh-policies). Varat atlasīt procesa statusu, lai skatītu detalizētu informāciju par visa uzdevuma norisi. Pēc tam, kad vienam no darba uzdevumiem esat atlasījis **Skatīt detalizētu informāciju**, jūs redzēsit papildinformāciju: apstrādes laiku, pēdējās apstrādes datumu un visas ar uzdevumu saistītas kļūdas un brīdinājumus.

## <a name="manage-existing-semantic-mappings"></a>Pārvaldīt esošos semantiskos kartējumus

Sadaļā **Dati** > **Semantiskie kartējumi (priekšskatījums)** varat skatīt un pārvaldīt visus saglabātos semantiskos kartējumus. Katrs semantiskais kartējums tiek attēlots ar atsevišķu rindu. Detalizēta informācija par avota entītiju, semantisko tipu, kartēšanas tipu un tās statusu.

:::image type="content" source="media/semantic-mapping-options.png" alt-text="Semantisko kartējumu pārvaldīšanas opcijas.":::

- **Rediģēt**: pārskatīšanas solī tiek atvērta semantiskā kartējuma iestatījumu konfigurācija. Varat mainīt pašreizējo konfigurāciju. Lai apstrādātu izmaiņas, atlasiet **Saglabāt** un **Palaist**.

- **Atsvaidzināt**: atsvaidzina atlasīto s savietošanas kartējumu ar visjaunākajiem datiem no entītijām, kas ir daļa no konfigurācijas. Atsvaidzinot jebkuru doto semantisko kartējumu, tiks atsvaidzināti visi viena semantiskā tipa kartējumi.

- **Pārdēvēt**: atver dialogu, kurā var ievadīt citu atlasītā semantiskā kartējuma nosaukumu. Lai veiktās izmaiņas stātos spēkā, atlasiet **Saglabāt**.

- **Dzēst**: atver dialogu, lai apstiprinātu atlasītā semantiskā kartējuma dzēšanu. Atlasot semantiskos kartējumus un dzēšanas ikonu, vienlaicīgi var izdzēst arī vairākus semantiskos kartējumus. Lai apstiprinātu dzēšanu, atlasiet **Dzēst**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
