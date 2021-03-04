---
title: Klientu profilu bagātināšana ar programmu Microsoft Graph
description: Izmantojiet īpašnieka datus no Microsoft Graph, lai bagātinātu klientu datus ar zīmolu un interešu radniecību.
ms.date: 12/10/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 2c95369c778f592bc1460799aca0fa8cff813d68
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269339"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a>Bagātiniet klientu profilus ar zīmola un interešu radniecību (priekšskatījums)

Izmantojiet īpašnieka datus no Microsoft Graph, lai bagātinātu klientu datus ar zīmolu un interešu radniecību. Šie apstākļi tiek noteikti, vadoties pēc datiem, kas iegūti no cilvēkiem ar līdzīgiem demogrāfiskajiem datiem līdz jūsu klientiem. Šī informācija palīdz labāk izprast un segmentēt jūsu klientus, ņemot vērā viņu saistību ar noteiktiem zīmoliem un interesēm.

Rīkā Auditorijas ieskati ejiet uz **Dati** > **Bagātināšana**, lai [konfigurētu un skatītu bagātināšanu](enrichment-hub.md).

Lai konfigurētu zīmola saistību bagātināšanu, dodieties uz cilni **Atklāt** un atlasiet **Bagātināt manus datus** elementā **Zīmoli**.

Lai konfigurētu interešu saistību bagātināšanu, dodieties uz cilni **Atklāt** un atlasiet **Bagātināt manus datus** elementā **Intereses**.

   > [!div class="mx-imgBorder"]
   > ![Zīmolu un interešu rūtis](media/BrandsInterest-tile-Hub.png "Zīmolu un interešu rūtis")

## <a name="about-microsoft-graph"></a>Par Microsoft Graph

Mēs izmantojam tiešsaistes meklēšanas datus no Microsoft Graph, lai atrastu zīmolu un interešu radniecību dažādos demogrāfiskajos segmentos (kurus nosaka pēc vecuma, dzimuma vai atrašanās vietas). Zīmola vai intereses tiešsaistes meklēšanas apjoms nosaka, cik daudz radniecības demogrāfiskajam segmentam ir ar šo zīmolu vai interesi, salīdzinot ar citiem segmentiem.

[Uzziniet vairāk par Microsoft Graph](https://docs.microsoft.com/graph/overview).

## <a name="affinity-level-and-score"></a>Saistību līmenis un rezultāts

Katrā bagātinātā klienta profilā mēs nodrošinām divas saistītās vērtības — saistību līmeni un saistību rezultātu. Šīs vērtības palīdz noteikt, cik spēcīgas ir saistības šī profila demogrāfiskajam segmentam attiecībā uz zīmolu vai interesi salīdzinājumā ar citiem demogrāfiskajiem segmentiem.

*Saistību līmenis* sastāv no četriem līmeņiem, un *saistību rādītājs* tiek aprēķināts pēc 100 punktu skalas, kura tiek kartēta uz saistību līmeņiem.


|Saistību līmenis |Saistības rādītājs  |
|---------|---------|
|Ļoti augsts     | 85-100       |
|Augsts     | 70-84        |
|Vidēja     | 35-69        |
|Zems     | 1-34        |

Atkarībā no tā, cik detalizēti vēlaties mērīt saistības, varat izmantot vai nu saistību līmeni, vai rezultātu. Saistību rādītājs sniedz precīzāku vadīklu.

## <a name="supported-countriesregions"></a>Atbalstītās valstis/reģioni

Pašlaik tiek atbalstītas šādas valsts/reģiona opcijas: Austrālija, Kanāda (angļu valoda), Francija, Vācija, Apvienotā Karaliste vai Amerikas Savienotās Valstis (angļu valoda).

Lai atlasītu valsti, atveriet **Zīmolu papildināšanu** vai **Intereses papildināšanu** un atlasiet opciju **Mainīt** blakus **Valsts/Reģions**. Rūtī **Valsts/Reģiona iestatījumi** izvēlieties opciju un atlasiet **Piemērot**.

### <a name="implications-related-to-country-selection"></a>Ar valsts atlasi saistītās sekas

- [Izvēloties savus zīmolus](#define-your-brands-or-interests), sistēma sniedz ieteikumus, kas balstīti uz atlasīto valsti vai reģionu.

- [Izvēloties nozari](#define-your-brands-or-interests), jūs iegūsiet svarīgākos zīmolus vai intereses, pamatojoties uz atlasīto valsti vai reģionu.

- [Bagātinot profilus](#refresh-enrichment), mēs bagātināsim visus klientu profilus, attiecībā uz kuriem mēs iegūstam datus par atlasītajiem zīmoliem un interesēm. Ieskaitot profilus, kas nav atlasītajā valstī vai reģionā. Piemēram, ja atlasījāt Vāciju, mēs bagātināsim profilus, kas atrodas Amerikas Savienotajās Valstīs, ja ir pieejami Microsoft Graph dati par atlasītajiem zīmoliem un interesēm Amerikas Savienotajās Valstīs (ASV).

## <a name="configure-enrichment"></a>Konfigurēt bagātināšanu

### <a name="define-your-brands-or-interests"></a>Definēt zīmolus vai intereses

Atlasiet kādu no šīm opcijām:

- **Nozare**: Sistēma identificē galvenos zīmolus vai intereses, kas attiecas uz jūsu nozari, un bagātina jūsu klientu datus ar tiem.
- **Izvēlieties paši**: Atlasiet līdz pieciem vienumiem no zīmolu vai interešu saraksta, kuri jūsu organizācijai ir vissaistošākie.

Lai pievienotu zīmolu vai interesi, ievadiet to ievades apgabalā, lai saņemtu ieteikumus, pamatojoties uz atbilstības nosacījumiem. Ja mēs neuzskaitām zīmolu vai interesi, kuru meklējat, nosūtiet mums atsauksmi, izmantojot saiti **Ieteikt**.

### <a name="review-enrichment-preferences"></a>Bagātināšanas preferenču pārskatīšana

Pārskatiet noklusējuma bagātināšanas preferences un atjauniniet tās, kad tas ir nepieciešams.

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Bagātinātā preferenču loga ekrānuzņēmums.":::

### <a name="select-entity-to-enrich"></a>Atlasiet bagātināmo entītiju

Atlasiet **Bagātinātā entītija** un izvēlieties datu kopu, ko vēlaties bagātināt ar uzņēmuma datiem no programmas Microsoft Graph. Varat atlasīt entītiju Klients, lai bagātinātu visus klientu profilus, vai atlasīt segmenta entītiju, lai bagātinātu tikai šajā segmentā iekļautos klientu profilus.

### <a name="map-your-fields"></a>Lauku kartēšana

Kartējiet laukus no savas vienotās klienta entītijas, lai definētu demogrāfisko segmentu, kuru sistēma vēlas, lai izmantojat jūsu klientu datu bagātināšanai. Kartējiet valsti/reģionu un vismaz Dzimšanas datu vai Dzimuma atribūtus. Turklāt ir jākartē vismaz viens no atribūtiem — Pilsēta (un novads/rajons) vai pasta indekss. Atlasiet **Rediģēt**, lai definētu lauku kartēšanu, un atlasiet **Piemērot**, kad esat to izdarījis. Atlasiet **Saglabāt**, lai pabeigtu lauka kartēšanu.

Tiek atbalstīti šādi(-as) formāti un vērtības; vērtības nav reģistrjutīgas:

- **Dzimšanas datums** : Iesakām, lai datu uzņemšanas laikā dzimšanas datums tiek pārvērsts par DateTime tipu. Vai arī tā var būt virkne [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) “gggg-MM-dd” vai “gggg-MM-ddTHH:mm:ssZ” formātā.
- **Dzimums**: Vīrietis, sieviete, nezināms
- **Pasta indekss**: Piecciparu pasta indeksi ASV, standarta pasta indekss citur
- **Pilsēta** : Pilsētas nosaukums angļu valodā
- **Štats/Province**: Divu burtu saīsinājums Amerikas Savienotajās Valstīs (ASV) un Kanādā. Divu vai trīs burtu saīsinājums Austrālijā. Nav piemērojams Francijai, Vācijai vai Apvienotajai Karalistei.
- **Valsts/Reģions**:

  - US: Amerikas Savienotās Valstis, ASV, US, Amerika
  - CA: Kanāda, CA
  - GB: Apvienotā Karaliste, AK, Lielbritānija, GB, Lielbritānijas un Ziemeļīrijas Apvienotā Karaliste, Lielbritānijas Apvienotā Karaliste
  - AU: Austrālija, AU, Austrālijas Savienība
  - FR: Francija, FR, Francijas Republika
  - DE: Vācija, vācu valoda, Deutschland, Allemagne, DE, Vācijas Federatīvā Republika, Vācijas Republika

## <a name="refresh-enrichment"></a>Atsvaidzināt bagātināšanu

Pēc zīmolu, interešu un demogrāfijas lauku kartēšanas palaidiet bagātināšanu. Lai sāktu procesu, atlasiet **Palaist** zīmola vai interešu konfigurācijas lapā. Turklāt varat ļaut sistēmai automātiski palaist bagātināšanu kā plānotas atsvaidzināšanas daļu.
Atkarībā no jūsu klientu datu apjoma bagātināšanas izpilde var aizņemt vairākas minūtes.

> [!TIP]
> Uzdevumiem/procesiem ir [seši statusu tipi](system.md#status-types). Turklāt vairums procesu [ir atkarīgi no citiem pakārtotiem procesiem](system.md#refresh-policies). Varat atlasīt procesa statusu, lai skatītu detalizētu informāciju par visa uzdevuma norisi. Pēc tam, kad vienam no darba uzdevumiem esat atlasījis **Skatīt detalizētu informāciju**, jūs redzēsit papildinformāciju: apstrādes laiku, pēdējās apstrādes datumu un visas ar uzdevumu saistītas kļūdas un brīdinājumus.

## <a name="enrichment-results"></a>Bagātināšanas rezultāti

Pēc bagātināšanas procesa palaišanas dodieties uz **Manas bagātināšanas**, lai pārskatītu kopējo bagātināto klientu skaitu un zīmolu vai interešu sadalījumu bagātināto klientu profilos.

:::image type="content" source="media/my-enrichments.png" alt-text="Rezultātu priekšskatījums pēc bagātināšanas procesa izpildes":::

Pārskatiet bagātinātos datus, diagrammā atlasot **Skatīt bagātinātos datus**. Zīmolu bagātinātie dati dodas uz entītiju **BrandAffinityFromMicrosoft**. Interešu dati atrodas entītijā **InterestAffinityFromMicrosoft**. Šīs entītijas ir uzskaitītas arī grupā **Bagātināšana** sadaļā **Dati** > **Entītijas**.

## <a name="see-enrichment-data-on-the-customer-card"></a>Skatiet informāciju par produkta bagātināšanu klienta kartītē

Zīmola un intereses radniecību var apskatīt arī atsevišķās klientu kartītēs. Atveriet sadaļu **Klienti** un atlasiet klienta profilu. Klienta kartē ir atrodamas to zīmolu vai interešu diagrammas, kuras ir saistītas ar šī klienta demogrāfiskā profila lietotājiem.

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Klienta kartīte ar bagātinātiem datiem":::

## <a name="next-steps"></a>Nākamās darbības

Būvējiet virs saviem bagātinātajiem klientu datiem. Veidojiet [segmentus](segments.md), [mērus](measures.md)un pat [eksportējiet datus](export-destinations.md), lai klientiem sniegtu personalizētas iespējas.


[!INCLUDE[footer-include](../includes/footer-banner.md)]