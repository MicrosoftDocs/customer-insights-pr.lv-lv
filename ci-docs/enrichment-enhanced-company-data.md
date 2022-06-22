---
title: Uzņēmuma datu uzlabošana
description: Bagātiniet un normalizējiet uzņēmuma datus, izmantojot Microsoft modeļus.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 4247d59806468907d93fc7848231ec5a2985580e
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 06/13/2022
ms.locfileid: "8953958"
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

Modelis:

- Apstipriniet uzņēmuma identitāti. Mēs nepārbaudām, vai ievade ir esoša organizācija vai uzņēmums izmanto izvadi kā standarta nosaukumu.
- Visaptveroši aptver uzņēmumus visā pasaulē. Microsoft apkopotajiem uzņēmuma datiem ir globāls pārklājums, taču tie piedāvā vislielāko pārklājumu Austrālijā, Kanādā, Apvienotajā Karalistē un Amerikas Savienotajās Valstīs.
- Standartizēt uzņēmuma adreses visā pasaulē. Pašlaik mēs atbalstām adrešu standartizāciju šajās valstīs vai reģionos: Austrālijā, Kanādā, Francijā, Vācijā, Itālijā, Japānā, Apvienotajā Karalistē un Amerikas Savienotajās Valstīs.
- Garantējiet datu precizitāti vai svaigumu. Tā kā biznesa informācija bieži mainās, mēs nevaram garantēt, ka sniegtie uzlabotie uzņēmuma dati vienmēr ir precīzi vai atjaunināti.

## <a name="configure-the-enrichment"></a>Bagātināto datu konfigurēšana

1. Dodieties uz **Dati** > **Bagātināšana** un atlasiet cilni **Atklāt**.

1. Uzlabotā uzņēmuma datu elementā atlasiet **Bagātināt manus** datus **·**.

   :::image type="content" source="media/enhanced-company-data-tile.png" alt-text="Bagātināšanas elements bagātināšanas centrmezglā uzņēmuma datiem.":::

1. Pārskatiet pārskatu un pēc tam atlasiet **Tālāk**.

1. Atlasiet klienta datu kopu **un** izvēlieties profilu vai segmentu, kuru vēlaties bagātināt. Klientu *uzņēmums* bagātina visus jūsu klientu profilus, savukārt segments bagātina tikai šajā segmentā esošos klientu profilus.

1. Atlasiet, kāda veida laukus no uzņēmuma profiliem izmantot saskaņošanai ar Microsoft apkopotajiem uzņēmuma datiem. Šāda atlase ietekmēs kartēšanas laukus, kuriem jums būs piekļuve nākamajā darbībā.

1. Atlasiet **Tālāk**.

1. Kartējiet uzņēmuma laukus uz uzņēmuma datiem no Microsoft. Lai nodrošinātu augstāku atbilstības precizitāti, pievienojiet papildu laukus.

    :::image type="content" source="media/enhanced-company-data-mapping.png" alt-text="Datu kartēšanas solis, konfigurējot uzņēmuma bagātināšanu.":::

1. Lai pabeigtu lauka kartēšanu, atlasiet **Tālāk**.

1. Norādiet **bagātināšanas un entītijas** Izvades **nosaukumu**.

1. Pēc izvēļu pārskatīšanas atlasiet **Saglabāt bagātināšanu**.

1. Atlasiet **Palaist**, lai sāktu bagātināšanas procesu, vai tuvu, lai **atgrieztos lapā Bagātinājumi**.

## <a name="enrichment-results"></a>Bagātināšanas rezultāti

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

### <a name="overview-card"></a>Pārskata karte

Klientu **izmaiņu pārskata** elements parāda detalizētu informāciju par bagātināšanas segumu

- **Uzņēmumi apstrādāti un mainīti**: veiksmīgi bagātināto klientu uzņēmumu profilu skaits.
- **Uzņēmumi apstrādāti un nav mainīti**: klientu uzņēmuma profilu skaits, kas tika atzīti, bet netika mainīti. Tas parasti notiek, ja ievades dati ir derīgi un tos nevar uzlabot ar bagātināšanu.
- **Uzņēmumi nav apstrādāti un nav mainīti**: neatpazītu klientu uzņēmuma profilu skaits. Tas parasti notiek ievades datiem, kas nav derīgi vai ko bagātināšana neatbalsta.

## <a name="next-steps"></a>Nākamās darbības

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
