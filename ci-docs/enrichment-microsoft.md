---
title: Klientu profilu bagātināšana ar Microsoft zīmoliem un interešu datiem (priekšskatījums)
description: Izmantojiet Microsoft patentētos datus, lai bagātinātu savus klientu datus ar radniecību un balss kopīgošanu.
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
ms.openlocfilehash: e1827adca10a3b193c02a20c4abccacf73194a77
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082704"
---
# <a name="enrich-customer-profiles-with-brands-and-interests-data-from-microsoft-preview"></a>Klientu profilu bagātināšana ar Microsoft zīmoliem un interešu datiem (priekšskatījums)

Izmantojiet Microsoft patentētos datus, lai bagātinātu savus klientu datus ar zīmola piederību, interešu piederību un balss kopīgošanu (SoV). Šīs radniecības un SoV ir balstītas uz datiem no cilvēkiem, kuru demogrāfiskie dati ir līdzīgi jūsu klientiem. Šī informācija palīdz jums labāk izprast un segmentēt savus klientus, pamatojoties uz viņu piederību vai SoV konkrētiem zīmoliem un interesēm.

## <a name="how-we-determine-affinities-and-sov"></a>Kā mēs nosakām radniecību un SoV

Mēs izmantojam Microsoft tiešsaistes meklēšanas datus, lai atrastu radniecību un SoV zīmoliem un interesēm dažādos demogrāfiskajos segmentos (definēti pēc vecuma, dzimuma vai atrašanās vietas). Zīmola vai interešu tiešsaistes meklēšanas apjoms veido pamatu radniecības vai SoV noteikšanai. Tomēr katrs no tiem sniedz atšķirīgu skatījumu, lai izprastu savus klientus.

- Affinity ir salīdzinājums starp demogrāfiskajiem segmentiem. Šo informāciju varat izmantot, lai identificētu demogrāfiskos segmentus, kuriem ir vislielākā afinitāte pret konkrētu zīmolu vai interesēm salīdzinājumā ar citiem segmentiem.

- Balss daļa ir salīdzināma starp jūsu izvēlētajiem zīmoliem vai interesēm. Varat izmantot šo informāciju, lai noteiktu, kuram zīmolam vai interesēm ir vislielākā balss daļa attiecīgajā demogrāfiskajā segmentā salīdzinājumā ar citiem jūsu atlasītajiem zīmoliem vai interesēm.

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

Mēs aprēķinām SoV 100 punktu skalā. Kopējais SoV visos zīmolos vai interesēs katram bagātinātajam klienta profilam ir līdz 100. Atšķirībā no afinitātēm, SoV ir relatīvs attiecībā pret jūsu izvēlētajiem zīmoliem un interesēm. Piemēram, "Microsoft" SoV vērtības var atšķirties, ja atlasītie zīmoli ir ("Microsoft", "GitHub") salīdzinājumā ar ("Microsoft", "LinkedIn").

## <a name="supported-countriesregions"></a>Atbalstītās valstis/reģioni

Pašlaik tiek atbalstītas šādas valsts/reģiona opcijas: Austrālija, Kanāda (angļu valoda), Francija, Vācija, Apvienotā Karaliste vai Amerikas Savienotās Valstis (angļu valoda).

## <a name="configure-the-enrichment"></a>Bagātināto datu konfigurēšana

1. Dodieties uz **Dati** > **Bagātināšana** un atlasiet cilni **Atklāt**.

   - Lai konfigurētu zīmola radniecību un SoV bagātināšanu, atlasiet **Bagātināt manus datus** elementā **Zīmoli**.

   - Lai konfigurētu interešu intereses un SoV bagātināšanu, atlasiet **Bagātināt manus datus** elementā **Intereses**.

   > [!div class="mx-imgBorder"]
   > ![Zīmolu un interešu elementi.](media/BrandsInterest-tile-Hub.png "Zīmolu un interešu elementi")

1. Pārskatiet pārskatu un pēc tam atlasiet **Tālāk**.

1. Lai mainītu valsti vai reģionu, atlasiet **Mainīt blakus Vienumam** Valsts/reģions **·**. **Rūtī Valsts/reģiona iestatījumi** izvēlieties atbalstīto [valsti/reģionu](#supported-countriesregions) un atlasiet **Lietot**.

   > [!NOTE]
   > Izvēloties savus zīmolus, sistēma sniedz ieteikumus, kas balstīti uz atlasīto valsti vai reģionu. Izvēloties nozari, jūs iegūsiet svarīgākos zīmolus vai intereses, pamatojoties uz atlasīto valsti vai reģionu.

1. Izmantojot vienu vai abas iespējas, izvēlieties līdz pieciem zīmoliem vai interesēm:

   - **Nozare**: nolaižamajā sarakstā atlasiet savu nozari un pēc tam izvēlieties kādu no šīs nozares populārākajiem zīmoliem vai interesēm.
   - **Izvēlieties savu**: ievadiet ar organizāciju atbilstošu zīmolu vai ieinteresētību un pēc tam izvēlieties kādu no atbilstības noteikšanas ieteikumiem. Ja mēs neuzskaitām zīmolu vai interesi, kuru meklējat, nosūtiet mums atsauksmi, izmantojot saiti **Ieteikt**.

1. Atlasiet **Tālāk** un pārskatiet noklusējuma bagātināšanas preferences un pēc vajadzības atjauniniet tās.

   :::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Bagātinātā preferenču loga ekrānuzņēmums.":::

1. Atlasiet **Tālāk**.

1. **Atlasiet klienta datu kopu** un izvēlieties profilu vai segmentu, kuru vēlaties bagātināt ar Microsoft datiem. Klienta *entītija* bagātina visus jūsu klientu profilus, savukārt segments bagātina tikai šajā segmentā ietvertos klientu profilus.

1. Atlasiet **Tālāk**.

1. Kartējiet laukus no vienotās klienta entītijas uz Microsoft datiem.

   > [!NOTE]
   > Ir nepieciešami vismaz dzimšanas datuma vai dzimuma atribūti. Ir nepieciešama valsts/reģions un vismaz pilsēta (un štats/province) vai pasta indekss. Ieteicams, lai datu norīšanas laikā dzimšanas datums tiktu pārveidots par datetime tipu. Vai arī tā var būt virkne [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) formātā “yyyy-MM-dd” vai “yyyy-MM-ddTHH:mm:ss”.

1. Lai pabeigtu lauka kartēšanu, atlasiet **Tālāk**.

1. Norādiet bagātināto datu nosaukumu. Automātiski tiek atlasīts izvades **entītijas nosaukums**.

   :::image type="content" source="media/enrichment-interests-summary.png" alt-text="Interešu pārskatīšanas un dēvēšanas lapa.":::

1. Pēc izvēļu pārskatīšanas atlasiet **Saglabāt bagātināšanu**.

1. Atlasiet **Palaist**, lai sāktu bagātināšanas procesu, vai aizveriet, lai **atgrieztos bagātināšanas** lapā.

   Ja bagātināsiet profilus, mēs bagātināsim visus klientu profilus, no kuriem mēs iegūstam datus par atlasītajiem zīmoliem un interesēm, tostarp profilus, kuri neietilps atlasītajā valstī vai reģionā. Piemēram, ja atlasāt Vāciju, mēs bagātināsim profilus, kuri atrodas ASV, ja mums būs pieejami dati par atlasītajiem zīmoliem un interesēm ASV.

## <a name="view-enrichment-results"></a>Bagātināšanas rezultātu skatīšana

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

:::image type="content" source="media/my-enrichments.png" alt-text="Rezultātu priekšskatījums pēc bagātināšanas procesa izpildes.":::

Rezultāti ietver **Affinity Level** vai **Share of Voice** diagrammas.

Entītijas, kas izveidotas no bagātināšanas, ir uzskaitītas **datu vienību** grupā **·** > **Enrichment**. Bagātināti dati par zīmoliem nonāk **BrandAffinityFromMicrosoft** un **BrandShareOfVoiceFromMicrosoft** entītijās. Interešu dati ir **InterestAffinityFromMicrosoft** un **InterestShareOfVoiceFromMicrosoft** entities.

## <a name="see-enrichment-data-on-the-customer-card"></a>Skatiet informāciju par produkta bagātināšanu klienta kartītē

Zīmolu un intereses SoV var apskatīt arī uz atsevišķām klientu kartēm. Atveriet sadaļu **Klienti** un atlasiet klienta profilu. Klienta kartē atradīsit zīmola vai interešu SoV diagrammas, pamatojoties uz cilvēkiem šī klienta demogrāfiskajā profilā.

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Klienta kartīte ar bagātinātiem datiem.":::

## <a name="next-steps"></a>Nākamās darbības

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]


[!INCLUDE [footer-include](includes/footer-banner.md)]
