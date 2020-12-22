---
title: Klientu profilu bagātināšana ar programmu Microsoft Graph
description: Izmantojiet īpašnieka datus no Microsoft Graph, lai bagātinātu klientu datus ar zīmolu un interešu radniecību.
ms.date: 09/28/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 4f93a2337815f76b98185ecb3755e08443031748
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406332"
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

## <a name="affinity-score-and-confidence"></a>Radniecības rezultāts un uzticība

**Radniecības rezultāts** tiek aprēķināts, izmantojot 100 punktu skalu, ar 100 apzīmē segmentu, kam ir visaugstākā radniecība attiecībā pret zīmolu vai interesi.

**Radniecības ticamība** arī tiek aprēķināta 100 punktu skalā. Tā norāda uz sistēmas ticamības līmeni tam, ka segmentam ir radniecība ar zīmolu vai interesi. Ticamības līmenis ir atkarīgs no segmenta lieluma un segmenta detalizācijas. Segmenta lielumu nosaka jūsu norādītā segmenta datu daudzums. Segmenta detalizāciju nosaka, cik daudzi atribūti (vecums, dzimums, atrašanās vieta) ir pieejami profilā.

Mēs nenormalizējam jūsu datu kopas rezultātus. Līdz ar to var nebūt redzamas visas datu kopas iespējamās radniecības rezultātu vērtības. Piemēram, jūsu datos varētu nebūt neviena bagātināta klienta profila ar radniecības novērtējumu 100. Tas ir iespējams gadījumā, ja demogrāfiskajā segmentā, kas noteiktajam zīmolam vai interesei ir novērtēts ar 100, nav neviena klienta.

> [!TIP]
> Ja [veidojat segmentus](segments.md), izmantojot radniecības rezultātus, pārskatiet savas datu kopas radniecības rezultātus, pirms pieņemat lēmumu par atbilstošajiem rezultātu sliekšņiem. Piemēram, radniecības rezultātu 10 var uzskatīt par nozīmīgu rezultātu datu kopai ar visaugstāko rezultātu, kas ir tikai 25 attiecībā uz doto zīmolu vai interesi.

## <a name="supported-countriesregions"></a>Atbalstītās valstis/reģioni

Pašlaik tiek atbalstītas šādas valsts/reģiona opcijas: Austrālija, Kanāda (angļu valoda), Francija, Vācija, Apvienotā Karaliste vai Amerikas Savienotās Valstis (angļu valoda).

Lai atlasītu valsti, atveriet **Zīmolu papildināšanu** vai **Intereses papildināšanu** un atlasiet opciju **Mainīt** blakus **Valsts/Reģions**. Rūtī **Valsts/Reģiona iestatījumi** izvēlieties opciju un atlasiet **Piemērot**.

### <a name="implications-related-to-country-selection"></a>Ar valsts atlasi saistītās sekas

- Izvēloties [savus zīmolus](#define-your-brands-or-interests), tiks sniegti ieteikumi, balstoties uz atlasīto valsti/reģionu.

- [Izvēloties nozari](#define-your-brands-or-interests), mēs noteiksim visatbilstošākos zīmolus vai intereses, pamatojoties uz atlasīto valsti/reģionu.

- [Kartējot savus laukus](#map-your-fields), ja lauks Valsts/Reģions nav kartēts, mēs izmantosim Microsoft Graph datus no atlasītā(s) valsts/reģiona, lai bagātinātu klientu profilus. Mēs arī izmantosim šo atlasi, lai bagātinātu klientu profilus, kuriem nav pieejami valsts/reģiona dati.

- [Papildinot profilus](#refresh-enrichment), mēs bagātināsim visus klientu profilus, kuriem ir pieejami Microsoft Graph dati par atlasītajiem zīmoliem un interesēm, ieskaitot profilus, kas nav atlasītajā valstī/reģionā. Piemēram, ja atlasījāt Vāciju, mēs bagātināsim profilus, kas atrodas Amerikas Savienotajās Valstīs, ja ir pieejami Microsoft Graph dati par atlasītajiem zīmoliem un interesēm Amerikas Savienotajās Valstīs (ASV).

## <a name="configure-enrichment"></a>Konfigurēt bagātināšanu

Konfigurējot zīmolus vai intereses, bagātināšana sastāv no divām darbībām:

### <a name="define-your-brands-or-interests"></a>Definēt zīmolus vai intereses

Atlasiet kādu no šīm opcijām:

- **Nozare**: Sistēma identificē galvenos zīmolus vai intereses, kas attiecas uz jūsu nozari, un bagātina jūsu klientu datus ar tiem.
- **Izvēlieties paši**: Atlasiet līdz pieciem vienumiem no zīmolu vai interešu saraksta, kuri jūsu organizācijai ir vissaistošākie.

Lai pievienotu zīmolu vai interesi, ievadiet to ievades apgabalā, lai saņemtu ieteikumus, pamatojoties uz atbilstības nosacījumiem. Ja mēs neuzskaitām zīmolu vai interesi, kuru meklējat, nosūtiet mums atsauksmi, izmantojot saiti **Ieteikt**.

### <a name="map-your-fields"></a>Lauku kartēšana

Kartējiet laukus no savas vienotās klienta entītijas uz vismaz diviem atribūtiem, lai definētu demogrāfisko segmentu, kuru vēlaties, lai izmantojam jūsu klientu datu bagātināšanai. Atlasiet **Rediģēt**, lai definētu lauku kartēšanu, un atlasiet **Piemērot**, kad esat to izdarījis. Atlasiet **Saglabāt**, lai pabeigtu lauka kartēšanu.

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
