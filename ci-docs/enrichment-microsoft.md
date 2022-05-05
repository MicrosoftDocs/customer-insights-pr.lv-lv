---
title: Klientu profilu bagātināšana ar Microsoft datiem
description: Izmantojiet Microsoft īpašumtiesību datus, lai bagātinātu klientu datus ar radniecību un balss daļu.
ms.date: 03/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
searchScope:
- ci-enrichments
- ci-enrichment-wizard
- customerInsights
ms.openlocfilehash: 5c016a394fdf485057a190d03bfed9ce5481f435
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643292"
---
# <a name="enrich-customer-profiles-with-affinities-and-share-of-voice-preview"></a>Bagātiniet klientu profilus ar radniecību un balss daļu (priekšskatījums)

Izmantojiet Microsoft patentētos datus, lai bagātinātu klientu datus ar zīmola radniecību, interešu radniecību un balss daļu (SoV). Šīs radniecības un SoV pamatā ir dati no cilvēkiem ar demogrāfisko situāciju, kas ir līdzīga jūsu klientiem. Šī informācija palīdz jums labāk izprast un segmentēt savus klientus, pamatojoties uz viņu radniecību vai SoV, konkrētiem zīmoliem un interesēm.

Dodieties uz **DataEnrichment** > **·**, lai konfigurētu [un skatītu jauninājumus](enrichment-hub.md).

Lai konfigurētu zīmola radniecību un SoV bagātināšanu, dodieties uz **cilni Atklāšana** un atlasiet **Bagātināt manus datus** elementu **Zīmoli**.

Lai konfigurētu interešu radniecības un SoV bagātināšanu, dodieties uz **cilni Atklāšana** un atlasiet **Bagātināt manus** datus **elementā Intereses**.

   > [!div class="mx-imgBorder"]
   > ![Zīmolu un interešu elementi.](media/BrandsInterest-tile-Hub.png "Zīmolu un interešu elementi")

## <a name="how-we-determine-affinities-and-sov"></a>Kā mēs nosakām radniecību un SoV

Mēs izmantojam Microsoft tiešsaistes meklēšanas datus, lai atrastu radniecību un SoV zīmoliem un interesēm dažādos demogrāfiskajos segmentos (ko nosaka vecums, dzimums vai atrašanās vieta). Zīmola vai intereses tiešsaistes meklēšanas apjoms veido pamatu radniecības vai SoV noteikšanai. Tomēr katrs no tiem sniedz atšķirīgu perspektīvu, lai izprastu savus klientus.

- Radniecība ir salīdzināma starp demogrāfiskajiem segmentiem. Šo informāciju var izmantot, lai identificētu demogrāfiskos segmentus, kuriem ir visaugstākā radniecība ar konkrētu zīmolu vai interesi, salīdzinot ar citiem segmentiem.

- Balss daļa ir salīdzināma starp jūsu izvēlētajiem zīmoliem vai interesēm. Šo informāciju var izmantot, lai noteiktu, kuram zīmolam vai interesei ir vislielākā balss daļa konkrētā demogrāfiskajā segmentā, salīdzinot ar citiem izvēlētajiem zīmoliem vai interesēm.

## <a name="affinity-level-and-score"></a>Saistību līmenis un rezultāts

Katrā bagātinātā klienta profilā mēs nodrošinām divas saistītās vērtības: saistību līmeni un saistību rezultātu. Šīs vērtības palīdz noteikt, cik spēcīgas ir saistības šī profila demogrāfiskajam segmentam attiecībā uz zīmolu vai interesi salīdzinājumā ar citiem demogrāfiskajiem segmentiem.

*Saistību līmenis* sastāv no četriem līmeņiem, un *saistību rādītājs* tiek aprēķināts pēc 100 punktu skalas, kura tiek kartēta uz saistību līmeņiem.


|Saistību līmenis |Saistības rādītājs  |
|---------|---------|
|Ļoti augsts     | 85-100       |
|Augsts     | 70-84        |
|Vidēja     | 35-69        |
|Zems     | 1-34        |

Atkarībā no tā, cik detalizēti vēlaties mērīt saistības, varat izmantot vai nu saistību līmeni, vai rezultātu. Saistību rādītājs sniedz precīzāku vadīklu.

## <a name="share-of-voice-sov"></a>Balss daļa (SoV)

Mēs aprēķinām SoV 100 punktu skalā. Kopējais SoV visos zīmolos vai interesēs katram bagātinātam klienta profilam ir līdz 100. Atšķirībā no radniecības SoV ir saistīts ar izvēlētajiem zīmoliem un interesēm. Piemēram, "Microsoft" SoV vērtības var atšķirties, ja atlasītie zīmoli ir ("Microsoft", "GitHub") salīdzinājumā ar ("Microsoft", "LinkedIn").

## <a name="supported-countriesregions"></a>Atbalstītās valstis/reģioni

Pašlaik tiek atbalstītas šādas valsts/reģiona opcijas: Austrālija, Kanāda (angļu valoda), Francija, Vācija, Apvienotā Karaliste vai Amerikas Savienotās Valstis (angļu valoda).

Lai atlasītu valsti vai reģionu, atveriet sadaļu **Zīmolu bagātināšana** vai **Interešu bagātināšana** un atlasiet **Mainīt** opciju pie **Valsts/Reģiona**. Rūtī **Valsts/Reģiona iestatījumi** izvēlieties opciju un atlasiet **Piemērot**.

### <a name="implications-related-to-country-selection"></a>Ar valsts atlasi saistītās sekas

- [Izvēloties savus zīmolus](#define-your-brands-or-interests), sistēma sniedz ieteikumus, kas balstīti uz atlasīto valsti vai reģionu.

- [Izvēloties nozari](#define-your-brands-or-interests), jūs iegūsiet svarīgākos zīmolus vai intereses, pamatojoties uz atlasīto valsti vai reģionu.

- Ja [bagātināsiet profilus](#refresh-enrichment), mēs bagātināsim visus klientu profilus, no kuriem mēs iegūstam datus par atlasītajiem zīmoliem un interesēm, tostarp profilus, kuri neietilps atlasītajā valstī vai reģionā. Piemēram, ja atlasāt Vāciju, mēs bagātināsim profilus, kuri atrodas ASV, ja mums būs pieejami dati par atlasītajiem zīmoliem un interesēm ASV.

## <a name="configure-enrichment"></a>Bagātināšanas konfigurēšana

Vadītā pieredze palīdz bagātinājumu konfigurēšanas laikā. 

### <a name="define-your-brands-or-interests"></a>Definēt zīmolus vai intereses

Izmantojot vienu vai abas iespējas, izvēlieties līdz pieciem zīmoliem vai interesēm:

- **Nozare**: nolaižamajā sarakstā atlasiet savu nozari un pēc tam izvēlieties kādu no šīs nozares populārākajiem zīmoliem vai interesēm.
- **Izvēlieties savu**: ievadiet ar organizāciju atbilstošu zīmolu vai ieinteresētību un pēc tam izvēlieties kādu no atbilstības noteikšanas ieteikumiem. Ja mēs neuzskaitām zīmolu vai interesi, kuru meklējat, nosūtiet mums atsauksmi, izmantojot saiti **Ieteikt**.

### <a name="review-enrichment-preferences"></a>Bagātināšanas preferenču pārskatīšana

Pārskatiet noklusējuma bagātināšanas preferences un atjauniniet tās, kad tas ir nepieciešams.

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Bagātinātā preferenču loga ekrānuzņēmums.":::

### <a name="select-entity-to-enrich"></a>Atlasiet bagātināmo entītiju

Atlasiet **Bagātināts entītija** un izvēlieties datu kopu, kuru vēlaties bagātināt ar Microsoft datiem. Varat atlasīt entītiju Klients, lai bagātinātu visus klientu profilus, vai atlasīt segmenta entītiju, lai bagātinātu tikai šajā segmentā iekļautos klientu profilus.

### <a name="map-your-fields"></a>Lauku kartēšana

Kartējiet laukus no savas vienotās klienta entītijas, lai definētu demogrāfisko segmentu, kuru sistēma vēlas, lai izmantojat jūsu klientu datu bagātināšanai. Kartējiet valsti/reģionu un vismaz Dzimšanas datu vai Dzimuma atribūtus. Turklāt ir jākartē vismaz viens no atribūtiem — Pilsēta (un novads/rajons) vai pasta indekss. Atlasiet **Rediģēt**, lai definētu lauku kartēšanu, un atlasiet **Piemērot**, kad esat to izdarījis. Atlasiet **Saglabāt**, lai pabeigtu lauka kartēšanu.

Tiek atbalstīti šādi(-as) formāti un vērtības (vērtības nav reģistrjutīgas):

- **Dzimšanas datums** : Iesakām, lai datu pievienošanas laikā dzimšanas datums tiek pārvērsts par DateTime tipu. Vai arī tā var būt virkne [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) formātā “yyyy-MM-dd” vai “yyyy-MM-ddTHH:mm:ss”.
- **Dzimums**: Vīrietis, sieviete, nezināms.
- **Pasta indekss**: Piecciparu pasta indeksi Amerikas Savienotajās Valstīs, standarta pasta indekss, ko izmanto citur.
- **Pilsēta**: Pilsētas nosaukums angļu valodā.
- **Štats/Province**: Divu burtu saīsinājums Amerikas Savienotajās Valstīs (ASV) un Kanādā. Divu vai trīs burtu saīsinājums Austrālijā. Nav piemērojams Francijai, Vācijai vai Apvienotajai Karalistei.
- **Valsts/Reģions**:

  - US: Amerikas Savienotās Valstis, ASV, US, Amerika
  - CA: Kanāda, CA
  - GB: Apvienotā Karaliste, AK, Lielbritānija, GB, Lielbritānijas un Ziemeļīrijas Apvienotā Karaliste, Lielbritānijas Apvienotā Karaliste
  - AU: Austrālijā, AU, Austrālijas Savienība
  - FR: Francija, FR, Francijas Republika
  - DE: Vācija, vācu valoda, Deutschland, Allemagne, DE, Vācijas Federatīvā Republika, Vācijas Republika

## <a name="review-and-name-the-enrichment"></a>Bagātinājuma pārskatīšana un dēvēšana

Visbeidzot, varat pārskatīt informāciju un nodrošināt bagātinājuma nosaukumu.

:::image type="content" source="media/enrichment-interests-summary.png" alt-text="Interešu pārskatīšanas un dēvēšanas lapa.":::

## <a name="refresh-enrichment"></a>Atsvaidzināt bagātināšanu

Pēc zīmolu, interešu un demogrāfijas lauku kartēšanas palaidiet bagātināšanu. Lai sāktu procesu, atlasiet **Palaist** zīmola vai interešu konfigurācijas lapā. Turklāt varat ļaut sistēmai automātiski palaist bagātināšanu kā plānotas atsvaidzināšanas daļu.

Atkarībā no jūsu klientu datu apjoma bagātināšanas izpilde var aizņemt vairākas minūtes.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="enrichment-results"></a>Bagātināšanas rezultāti

Pēc bagātināšanas procesa palaišanas dodieties uz **Manas bagātināšanas**, lai pārskatītu kopējo bagātināto klientu skaitu un zīmolu vai interešu sadalījumu bagātināto klientu profilos.

:::image type="content" source="media/my-enrichments.png" alt-text="Rezultātu priekšskatījums pēc bagātināšanas procesa izpildes.":::

Jūs atradīsit diagrammu ar bagātināto klientu profilu skaitu laika gaitā un bagātināto entītiju priekšskatījumiem. Pārskatiet bagātinātos datus, atlasot **Skatīt vairāk** **afinitātes līmenī** vai **Balss** diagrammu koplietošanā. Bagātinātie dati zīmoliem tiek novirzīti **BrandAffinityFromMicrosoft** un **BrandShareOfVoiceFromMicrosoft** entītijām. Dati par interesēm ir **InterestAffinityFromMicrosoft** un **InterestShareOfVoiceFromMicrosoft** entītijās. Šīs entītijas ir uzskaitītas arī grupā **Bagātināšana** sadaļā **Dati** > **Entītijas**.

## <a name="see-enrichment-data-on-the-customer-card"></a>Skatiet informāciju par produkta bagātināšanu klienta kartītē

Zīmols un interese SoV var apskatīt arī individuālās klientu kartēs. Atveriet sadaļu **Klienti** un atlasiet klienta profilu. Klienta kartē atradīsit diagrammas zīmolam vai interesei SoV, pamatojoties uz šī klienta demogrāfiskā profila lietotājiem.

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Klienta kartīte ar bagātinātiem datiem.":::

## <a name="next-steps"></a>Nākamās darbības

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]


[!INCLUDE [footer-include](includes/footer-banner.md)]
