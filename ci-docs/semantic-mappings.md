---
title: Semantiskie kartējumi (priekšskatījums)
description: Pārskats par semantiskajiem kartējumiem un to lietošanu.
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.reviewer: v-wendysmith
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
searchScope:
- ci-semantic-mapping
- customerInsights
ms.openlocfilehash: 8780c11c8b091717349f0fd75a36b99c3a63ab49
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 08/16/2022
ms.locfileid: "9303885"
---
# <a name="semantic-mappings-preview"></a>Semantiskie kartējumi (priekšskatījums)

> [!NOTE]
> Semantiskās **kartēšanas** lapa ir pieejama tikai biznesa vidēm (no B līdz B), kur kontaktu profili jau ir izveidoti, izmantojot šo lapu. Varat turpināt veidot un pārvaldīt atsevišķus kontaktpersonu profilus, **izmantojot lapu Semantiskie kartējumi**. Vai arī apvienojiet savus kontaktpersonu datus [,](data-unification-contacts.md) lai noņemtu dublikātus, identificētu atbilstības dažādās entītijās un izveidotu vienu vienotu kontaktpersonas profilu. Pēc tam varat izmantot vienoto kontaktpersonas profilu, lai izveidotu kontaktpersonas līmeņa darbības.

Semantiskie kartējumi ļauj kartēt datus, kas nav darbības dati, uz iepriekšdefinētām shēmām. Šīs shēmas palīdz programmai Customer Insights labāk izprast jūsu datu atribūtus. Semantiskā kartēšana un sniegtie dati ļauj gūt jaunus ieskatus un līdzekļus programmā Customer Insights. Lai darbības datus kartētu uz shēmām, pārskatiet [darbību ](activities.md) dokumentāciju.

## <a name="define-a-contactprofile-semantic-entity-mapping"></a>ContactProfile semantiskās entītijas kartējuma definēšana

1. Dodieties uz **Datu** > **semantiskie kartējumi (priekšskatījums)**.

1. Atlasiet **Pievienot semantisko kartējumu**, lai sāktu vadīto pieredzi.

1. **Entītijas datu** solī iestatiet šo lauku vērtības:

   - **Semantiskās entītijas kartēšanas nosaukums**: jūsu semantiskās entītijas kartēšanas nosaukums.
   - **Avota entītija**: entītija, kas ietver kontaktinformāciju.
   - **Primārā atslēga**: lauks, kas unikāli identificē kontaktpersonas ierakstu. Tajā nedrīkst ietvert dublētas vērtības, tukšas vērtības vai trūkstošas vērtības.

   :::image type="content" source="media/Semantic_Mapping_Wizard1.png" alt-text="Iestatiet semantiskās entītijas kartējumu ar nosaukumu, avota entītiju un primāro atslēgu.":::

1. Atlasiet **Tālāk**.

1. Solī **Attiecības** konfigurējiet detalizētu informāciju, lai kontaktpersonu datus savienotu ar atbilstošā konta datiem. Šajā darbībā tiek vizualizēts entītiju savienojums.  

   Ir divu tipu attiecību ceļi, ko var ieviest: **Tiešās attiecības** un **Netiešās attiecības**. Lai iegūtu papildinformāciju, atveriet [tiešo un netiešo attiecību ceļus](relationships.md#relationship-paths).

   1. Atlasiet **Pievienot relāciju**, lai konfigurētu relāciju.
   1. Izvēlieties atribūtu no avota entītijas, kas veido kontaktpersonas entītijas savienojumu ar citu entītiju.
   1. Izvēlieties entītiju, ar kuru veidot kontaktpersonas entītijas savienojumu. Izvēlieties entītiju no **konta entītijām** vai sadaļas Starpnieks **entītija**. Ja atlasāt starpnieks entītiju, definējiet otru relāciju, lai izveidotu savienojumu ar mērķa konta entītiju.

      :::image type="content" source="media/Semantic_Mapping_Wizard2.png" alt-text="Atlasiet uzņēmuma entītiju vai Sekundāru entītiju.":::

   1. Norādiet **Attiecību nosaukumu**. Ja attiecības starp entītijām jau pastāv, attiecību nosaukums ir tikai lasāms. Ja attiecību nav, tiks izveidotas jaunas attiecības ar jūsu norādīto nosaukumu.
   1. Atlasiet **Lietot**, lai pabeigtu attiecību konfigurāciju.

   > [!NOTE]
   > Varat konfigurēt vairāk attiecību starp kontaktpersonas entītiju un citām uzņēmuma entītijām, izmantojot sekundārās entītijas.
   
     :::image type="content" source="media/Semantic_Mapping_Wizard4.png" alt-text="Dažādu attiecību vizualizācija savieno kontaktpersonu entītijas ar uzņēmuma entītijām.":::

1. Atlasiet **Tālāk**.

1. Solī **Iestatīt semantisko tipu** izvēlieties **Semantisko tipu**. Pašlaik pastāv viens **Semantiskais tips** ar nosaukumu *ContactProfile*.

1. Kartējiet savu kontaktpersonas ID uz *ContactProfile* semantiskā tipa **kontakta ID**. Pēc izvēles kartējiet citus laukus, piemēram, vārds, uzvārds, dzimumu vai e-pastu.

   :::image type="content" source="media/Semantic_Mapping_Wizard5.png" alt-text="Kartējiet kontaktpersonu datu atribūtus uz nodrošinātajiem obligātajiem un neobligātajiem laukiem.":::

1. Atlasiet **Tālāk**.

1. Pārskatīšanas **solī** pārskatiet semantiskās kartēšanas konfigurāciju. Lai veiktu izmaiņas, atbilstošajai sadaļai atlasiet **Rediģēt**.

1. Atlasiet **Saglabāt**.

1. Lai apstrādātu semantisko kartēšanu, atlasiet **Palaist**. Vai arī atlasiet **Aizvērt**, lai saglabātu semantisko kartējumu, to neapstrādājot. Lai to palaistu vēlāk, atlasiet semantisko kartēšanu un atlasiet **Atsvaidzināt**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="manage-existing-semantic-mappings"></a>Pārvaldīt esošos semantiskos kartējumus

Dodieties uz **Datu** > **semantiskie kartējumi (priekšskatījums),** lai skatītu saglabātos semantiskos kartējumus, to avota entītiju, semantisko tipu, kartēšanas veidu un statusu.

:::image type="content" source="media/semantic-mapping-options.png" alt-text="Semantisko kartējumu pārvaldīšanas opcijas.":::

Atlasiet semantisko kartēšanu, lai skatītu pieejamās darbības.
- **Rediģējiet** pašreizējo konfigurāciju. Lai apstrādātu izmaiņas, atlasiet **Saglabāt** un **Palaist**.
- **Atsvaidziniet** semantisko kartēšanu, lai iekļautu jaunākos datus. Atsvaidzinot jebkuru doto semantisko kartējumu, tiks atsvaidzināti visi viena semantiskā tipa kartējumi.
- **Pārdēvējiet** semantisko kartēšanu. Atlasiet **Saglabāt**.
- **Dzēsiet** semantisko kartēšanu. Lai vienlaikus izdzēstu vairāk nekā vienu semantisko kartējumu, atlasiet semantiskos kartējumus un dzēšanas ikonu. Lai apstiprinātu dzēšanu, atlasiet **Dzēst**.

[!INCLUDE [footer-include](includes/footer-banner.md)]
