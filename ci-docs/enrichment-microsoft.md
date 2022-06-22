---
title: Bagātiniet klientu profilus ar zīmolu un interešu datiem no Microsoft
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
ms.openlocfilehash: 61262980cafdcd130430e200e466ce7da6cc4d07
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 06/13/2022
ms.locfileid: "8953774"
---
# <a name="enrich-customer-profiles-with-affinities-and-share-of-voice-preview"></a>Bagātiniet klientu profilus ar radniecību un balss daļu (priekšskatījums)

Izmantojiet Microsoft patentētos datus, lai bagātinātu klientu datus ar zīmola radniecību, interešu radniecību un balss daļu (SoV). Šīs radniecības un SoV pamatā ir dati no cilvēkiem ar demogrāfisko situāciju, kas ir līdzīga jūsu klientiem. Šī informācija palīdz jums labāk izprast un segmentēt savus klientus, pamatojoties uz viņu radniecību vai SoV, konkrētiem zīmoliem un interesēm.

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

## <a name="configure-the-enrichment"></a>Bagātināto datu konfigurēšana

1. Dodieties uz **Dati** > **Bagātināšana** un atlasiet cilni **Atklāt**.

   - Lai konfigurētu zīmola radniecību un SoV bagātināšanu, elementu Zīmoli atlasiet **Bagātināt manus** datus **·**.

   - Lai konfigurētu interešu radniecības un SoV bagātināšanu, atlasiet **Bagātināt manus datus** elementā **Intereses**.

   > [!div class="mx-imgBorder"]
   > ![Zīmolu un interešu elementi.](media/BrandsInterest-tile-Hub.png "Zīmolu un interešu elementi")

1. Pārskatiet pārskatu un pēc tam atlasiet **Tālāk**.

1. Lai mainītu savu valsti vai reģionu, atlasiet **Mainīt** blakus valstij/reģionam **·**. **Rūtī Valsts/reģiona iestatījumi** izvēlieties [atbalstītu valsti/reģionu](#supported-countriesregions) un atlasiet **Lietot**.

   > [!NOTE]
   > Izvēloties savus zīmolus, sistēma sniedz ieteikumus, kas balstīti uz atlasīto valsti vai reģionu. Izvēloties nozari, jūs iegūsiet svarīgākos zīmolus vai intereses, pamatojoties uz atlasīto valsti vai reģionu.

1. Izmantojot vienu vai abas iespējas, izvēlieties līdz pieciem zīmoliem vai interesēm:

   - **Nozare**: nolaižamajā sarakstā atlasiet savu nozari un pēc tam izvēlieties kādu no šīs nozares populārākajiem zīmoliem vai interesēm.
   - **Izvēlieties savu**: ievadiet ar organizāciju atbilstošu zīmolu vai ieinteresētību un pēc tam izvēlieties kādu no atbilstības noteikšanas ieteikumiem. Ja mēs neuzskaitām zīmolu vai interesi, kuru meklējat, nosūtiet mums atsauksmi, izmantojot saiti **Ieteikt**.

1. Atlasiet **Tālāk** un pārskatiet noklusējuma bagātināšanas preferences un atjauniniet tās pēc vajadzības.

   :::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Bagātinātā preferenču loga ekrānuzņēmums.":::

1. Atlasiet **Tālāk**.

1. **Atlasiet klienta datu kopu** un izvēlieties profilu vai segmentu, kuru vēlaties bagātināt ar Microsoft datiem. Klientu *uzņēmums* bagātina visus jūsu klientu profilus, savukārt segments bagātina tikai šajā segmentā esošos klientu profilus.

1. Atlasiet **Tālāk**.

1. Kartējiet savus vienotās klienta entītijas laukus uz Microsoft datiem.

   > [!NOTE]
   > Nepieciešami vismaz atribūti Dzimšanas datums vai dzimums. Nepieciešama valsts/reģions un vismaz pilsēta (un valsts/province) vai pasta indekss. Ieteicams datu uzņemšanas laikā dzimšanas datumu pārvērst par DateTime tipu. Vai arī tā var būt virkne [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) formātā “yyyy-MM-dd” vai “yyyy-MM-ddTHH:mm:ss”.

1. Lai pabeigtu lauka kartēšanu, atlasiet **Tālāk**.

1. Norādiet bagātināto datu nosaukumu. Izvades **entītijas nosaukums** tiek atlasīts automātiski.

   :::image type="content" source="media/enrichment-interests-summary.png" alt-text="Interešu pārskatīšanas un dēvēšanas lapa.":::

1. Pēc izvēļu pārskatīšanas atlasiet **Saglabāt bagātināšanu**.

1. Atlasiet **Palaist**, lai sāktu bagātināšanas procesu, vai tuvu, lai **atgrieztos lapā Bagātinājumi**.

   Ja bagātināsiet profilus, mēs bagātināsim visus klientu profilus, no kuriem mēs iegūstam datus par atlasītajiem zīmoliem un interesēm, tostarp profilus, kuri neietilps atlasītajā valstī vai reģionā. Piemēram, ja atlasāt Vāciju, mēs bagātināsim profilus, kuri atrodas ASV, ja mums būs pieejami dati par atlasītajiem zīmoliem un interesēm ASV.

## <a name="enrichment-results"></a>Bagātināšanas rezultāti

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

:::image type="content" source="media/my-enrichments.png" alt-text="Rezultātu priekšskatījums pēc bagātināšanas procesa izpildes.":::

Rezultāti ietver **radniecības līmeni** vai **balss** diagrammu koplietošanu.

No bagātinājumiem izveidotās entītijas ir uzskaitītas datu **entītiju** **grupā** > **Bagātināšana**. Bagātinātie dati zīmoliem tiek novirzīti **BrandAffinityFromMicrosoft** un **BrandShareOfVoiceFromMicrosoft** entītijām. Dati par interesēm ir **InterestAffinityFromMicrosoft** un **InterestShareOfVoiceFromMicrosoft** entītijās.

## <a name="see-enrichment-data-on-the-customer-card"></a>Skatiet informāciju par produkta bagātināšanu klienta kartītē

Zīmols un interese SoV var apskatīt arī individuālās klientu kartēs. Atveriet sadaļu **Klienti** un atlasiet klienta profilu. Klienta kartē atradīsit diagrammas zīmolam vai interesei SoV, pamatojoties uz šī klienta demogrāfiskā profila lietotājiem.

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Klienta kartīte ar bagātinātiem datiem.":::

## <a name="next-steps"></a>Nākamās darbības

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]


[!INCLUDE [footer-include](includes/footer-banner.md)]
