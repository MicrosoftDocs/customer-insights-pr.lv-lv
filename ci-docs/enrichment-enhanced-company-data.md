---
title: Uzņēmuma datu uzlabošana
description: Bagātiniet un normalizējiet uzņēmuma datus, izmantojot Microsoft modeļus.
ms.date: 04/22/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 6aa38afa7f92b512d19b4967fc1652b5e43ad094
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642995"
---
# <a name="enrichment-of-company-profiles-with-enhanced-company-data"></a>Uzņēmuma profilu bagātināšana ar uzlabotiem uzņēmuma datiem

Izmantojiet Microsoft modeļus un apkopotos uzņēmuma datus, lai labotu, papildinātu un standartizētu uzņēmuma profilus. Lai uzlabotu precizitāti un ieskatus, [mēs izmantosim kopējo datu modeļa formātu](/common-data-model/schema/core/applicationcommon/account).

Varat arī [uzlabot uzņēmuma datus par datu avotiem](data-sources-enrichment.md), lai uzlabotu atbilstības precizitāti datu apvienošanas procesā. 

Amerikas Savienoto Valstu valsts uzņēmumiem ir pieejama tāda informācija kā ieņēmumi, akciju rādītājs, rūpniecība un daudz kas cits.  

## <a name="how-we-enhance-company-data"></a>Kā mēs uzlabojam uzņēmuma datus

Mūsu modelis iziet divpakāpju procesu, lai uzlabotu uzņēmuma profilu. Pirmkārt, tas normalizē uzņēmuma nosaukumu. Piemēram, *Microsoft Corp* tiks labots un standartizēts korporācijai *Microsoft Corporation*. Tas mēģina atrast atbilstību Microsoft apkopotajos uzņēmuma datos. Ja tiek atrasta atbilstība, mēs bagātinām uzņēmuma profilu ar informāciju no mūsu apkopotajiem uzņēmuma datiem, tostarp uzņēmuma nosaukumu.


### <a name="example"></a>Piemērs

Jūsu uzņēmuma informācija, iespējams, neatbilst standartizētam formātam un satur pareizrakstības kļūdas. Modelis mēģina novērst šīs problēmas un izveidot konsekventu informāciju.

```Input
Microsft
```

```Output
- AccountName: Microsoft Corporation
- MainPhoneNumber: 8006427676
- Website: https://www.microsoft.com/
- Street1: One Microsoft Way
- City: Redmond
- StateOrProvince: Washington
- County: King
- ZipOrPostalCode: 98052
- CountryOrRegion: United States
```

## <a name="limitations"></a>Ierobežojumi

Uzlabotajiem datiem ir daži ierobežojumi. Modelis neatbalsta tālāk redzamā saraksta vienumus.

1.  Apstipriniet uzņēmuma identitāti. Mēs nepārbaudām, vai ievade ir esoša organizācija vai uzņēmums izmanto izvadi kā standarta nosaukumu.
2.  Visaptveroši aptver uzņēmumus visā pasaulē. Microsoft apkopotajiem uzņēmuma datiem ir globāls pārklājums, taču tie piedāvā vislielāko pārklājumu Austrālijā, Kanādā, Apvienotajā Karalistē un Amerikas Savienotajās Valstīs.
3.  Standartizēt uzņēmuma adreses visā pasaulē. Pašlaik mēs atbalstām adrešu standartizāciju šajās valstīs vai reģionos: Austrālijā, Kanādā, Francijā, Vācijā, Itālijā, Japānā, Apvienotajā Karalistē un Amerikas Savienotajās Valstīs.
4.  Garantējiet datu precizitāti vai svaigumu. Tā kā biznesa informācija bieži mainās, mēs nevaram garantēt, ka sniegtie uzlabotie uzņēmuma dati vienmēr ir precīzi vai atjaunināti.

## <a name="configure-the-enrichment"></a>Bagātināto datu konfigurēšana

1. Dodieties uz **Dati** > **Bagātināšana**.

1. Uzlabotā uzņēmuma datu elementā atlasiet **Bagātināt manus** datus **·**.

   :::image type="content" source="media/enhanced-company-data-tile.png" alt-text="Bagātināšanas elements bagātināšanas centrmezglā uzņēmuma datiem.":::

1. Atlasiet **Klientu datu kopu** un izvēlieties entītiju, kurā ir ietvertas bagātināmās adreses. Varat atlasīt entītiju *Klients*, lai bagātinātu adreses visos klientu profilos, vai atlasīt segmenta entītiju, lai bagātinātu adreses tikai šajā segmentā iekļautajos klientu profilos.

1. Atlasiet, kāda tipa lauki no jūsu uzņēmuma profiliem jāizmanto, lai saskaņotu ar Microsoft apkopotajiem uzņēmuma datiem. Šāda atlase ietekmēs kartēšanas laukus, kuriem jums būs piekļuve nākamajā darbībā.

1.  Kartējiet uzņēmuma laukus no vienotās klienta entītijas. Jo vairāk atslēgu identifikatoru un lauku kartējat, jo lielāka ir lielāka atbilstības līmeņa iespējamība.

    :::image type="content" source="media/enhanced-company-data-mapping.png" alt-text="Datu kartēšanas solis, konfigurējot uzņēmuma bagātināšanu.":::

1. Lai pabeigtu lauka kartēšanu, atlasiet **Tālāk**.

1. Norādiet bagātināto datu nosaukumu un izvades entitījas nosaukumu.

1. Pēc izvēļu pārskatīšanas atlasiet **Saglabāt vidi**.

## <a name="enrichment-results"></a>Bagātināšanas rezultāti

Lai sāktu bagātināšanas procesu, komandjoslā atlasiet **Palaist**. Varat arī ļaut sistēmai palaist bagātināšanu automātiski kā daļu no [plānotās atsvaidzināšanas](system.md#schedule-tab). Apstrādes laiks ir atkarīgs no klientu datu lieluma.

Pēc bagātināšanas procesa noslēgšanas varat pārskatīt tikko bagātinātos klientu profilu datus, dodoties uz sadaļu **Mana bagātināšana**. Turklāt jūs redzēsit pēdējā atjauninājuma laiku un bagātināto profilu skaitu.

Bagātināto klientu priekšskatījuma elementā **varat redzēt bagātināto klientu priekšskatījuma** paraugu. Atlasiet **Skatīt vairāk** un atlasiet **cilni Dati**, lai piekļūtu detalizētam katra bagātinātā profila skatam.

### <a name="overview-card"></a>Pārskata karte

Pārskata kartē ir parādīta detalizēta informācija par bagātināšanas segumu. 

* **Uzņēmumi apstrādāti un mainīti**: veiksmīgi bagātināto klientu uzņēmumu profilu skaits.

* **Uzņēmumi apstrādāti un nav mainīti**: klientu uzņēmuma profilu skaits, kas tika atzīti, bet netika mainīti. Tas parasti notiek, ja ievades dati ir derīgi un tos nevar uzlabot ar bagātināšanu.

* **Uzņēmumi nav apstrādāti un nav mainīti**: neatzīto klientu uzņēmumu profilu skaits. Tas parasti notiek ievades datiem, kas nav derīgi vai ko bagātināšana neatbalsta.

## <a name="next-steps"></a>Nākamās darbības

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
