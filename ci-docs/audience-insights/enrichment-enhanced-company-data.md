---
title: Uzņēmuma datu uzlabošana
description: Bagātiniet un normalizējiet uzņēmuma datus, izmantojot Microsoft modeļus.
ms.date: 01/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: e9cf93f28ba6918c72039670e42d26c8aaa7f922
ms.sourcegitcommit: 50d32a4cab01421a5c3689af789e20857ab009c4
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 03/03/2022
ms.locfileid: "8376360"
---
# <a name="enrichment-of-company-profiles-with-enhanced-company-data"></a>Uzņēmuma profilu bagātināšana ar uzlabotiem uzņēmuma datiem

Izmantojiet Microsoft modeļus un kompilētos uzņēmuma datus, lai labotu, papildinātu un standartizētu uzņēmuma profilus. Lai nodrošinātu labāku precizitāti un ieskatus, [mēs izmantosim common data model formātu](/common-data-model/schema/core/applicationcommon/account).

Varat arī [uzlabot uzņēmuma datus par datu avotiem](data-sources-enrichment.md), lai uzlabotu atbilstības precizitāti datu apvienošanas procesā. 

## <a name="how-we-enhance-company-data"></a>Kā mēs uzlabojam uzņēmuma datus

Mūsu modelis iziet divpakāpju procesu, lai uzlabotu uzņēmuma profilu. Pirmkārt, tas normalizē uzņēmuma nosaukumu. Piemēram, *Microsoft Corp* tiks labots un standartizēts uz *Microsoft Corporation*. Tā mēģina atrast atbilstību Microsoft apkopotajos uzņēmuma datos. Ja tiek atrasta atbilstība, mēs bagātinām uzņēmuma profilu ar informāciju no mūsu apkopotajiem uzņēmuma datiem, ieskaitot uzņēmuma nosaukumu.


### <a name="example"></a>Piemērs

Iespējams, ka jūsu uzņēmuma informācija neatbilst standartizētam formātam un satur pareizrakstības kļūdas. Modelis mēģina novērst šīs problēmas un izveidot konsekventu informāciju.

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

Uzlabotajiem datiem ir daži ierobežojumi. Modelis neatbalsta zemāk esošā saraksta elementus.

1.  Apstipriniet uzņēmuma identitāti. Mēs nepārbaudām, vai ievade ir esoša organizācija vai vai uzņēmums izmanto izvadi kā standarta nosaukumu.
2.  Visaptveroši aptver uzņēmumus visā pasaulē. Microsoft apkopotajiem uzņēmuma datiem ir globāls pārklājums, bet tie piedāvā lielāko daļu pārklājuma Austrālijā, Kanādā, Apvienotajā Karalistē un Amerikas Savienotajās Valstīs.
3.  Standartizēt uzņēmumu adreses visā pasaulē. Pašlaik mēs atbalstām adrešu standartizāciju šajās valstīs vai reģionos: Austrālijā, Kanādā, Francijā, Vācijā, Itālijā, Japānā, Apvienotajā Karalistē un Amerikas Savienotajās Valstīs.
4.  Garantējiet datu precizitāti vai svaigumu. Tā kā biznesa informācija bieži mainās, mēs nevaram garantēt, ka sniegtie uzlabotie uzņēmuma dati vienmēr ir precīzi vai atjaunināti.

## <a name="configure-the-enrichment"></a>Bagātināto datu konfigurēšana

1. Dodieties uz **Dati** > **Bagātināšana**.

1. Uzlabotajā uzņēmuma datu elementā atlasiet **Bagātināt manus** datus **·**.

   :::image type="content" source="media/enhanced-company-data-tile.png" alt-text="Bagātināšanas flīzes bagātināšanas mezglā uzņēmuma datiem.":::

1. Atlasiet **Klientu datu kopu** un izvēlieties entītiju, kurā ir ietvertas bagātināmās adreses. Varat atlasīt entītiju *Klients*, lai bagātinātu adreses visos klientu profilos, vai atlasīt segmenta entītiju, lai bagātinātu adreses tikai šajā segmentā iekļautajos klientu profilos.

1. Atlasiet, kāda tipa lauki no jūsu uzņēmuma profiliem ir jāizmanto saskaņošanai ar Microsoft apkopotajiem uzņēmuma datiem. Šāda atlase ietekmēs kartēšanas laukus, kuriem jums būs piekļuve nākamajā darbībā.

1.  Kartējiet uzņēmuma laukus no vienotās klienta entītijas. Jo vairāk galveno identifikatoru un lauku kartējat, jo lielāka ir lielāka atbilstības līmeņa iespējamība.

    :::image type="content" source="media/enhanced-company-data-mapping.png" alt-text="Datu kartēšanas solis, konfigurējot uzņēmuma bagātināšanu.":::

1. Lai pabeigtu lauka kartēšanu, atlasiet **Tālāk**.

1. Norādiet bagātināto datu nosaukumu un izvades entitījas nosaukumu.

1. Pēc izvēļu pārskatīšanas atlasiet **Saglabāt vidi**.

## <a name="enrichment-results"></a>Bagātināšanas rezultāti

Lai sāktu bagātināšanas procesu, komandjoslā atlasiet **Palaist**. Varat arī ļaut sistēmai palaist bagātināšanu automātiski kā daļu no [plānotās atsvaidzināšanas](system.md#schedule-tab). Apstrādes laiks ir atkarīgs no klientu datu lieluma.

Pēc bagātināšanas procesa noslēgšanas varat pārskatīt tikko bagātinātos klientu profilu datus, dodoties uz sadaļu **Mana bagātināšana**. Turklāt jūs redzēsit pēdējā atjauninājuma laiku un bagātināto profilu skaitu.

Bagātināto klientu priekšskatījuma elementā var redzēt bagātināto klientu priekšskatījuma **paraugu**. Atlasiet **Skatīt vairāk** un atlasiet **cilni Dati**, lai piekļūtu detalizētam katra bagātinātā profila skatam.

### <a name="overview-card"></a>Pārskata karte

Pārskata kartē ir norādīta detalizēta informācija par bagātināšanas aptvērumu. 

* **Apstrādātie un mainītie** uzņēmumi: veiksmīgi bagātināto klientu uzņēmumu profilu skaits.

* **Apstrādātie un nemainītie** uzņēmumi: atzīto, bet nemainīto klientu uzņēmumu profilu skaits. Tas parasti notiek, ja ievades dati ir derīgi un bagātināšanas dēļ tos nevar uzlabot.

* **Uzņēmumi, kas nav apstrādāti un nav mainīti**: neatpazītu klientu uzņēmumu profilu skaits. Tas parasti notiek ievades datiem, kas nav derīgi vai ko neatbalsta bagātināšana.

## <a name="next-steps"></a>Nākamās darbības

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

[!INCLUDE[footer-include](../includes/footer-banner.md)]
