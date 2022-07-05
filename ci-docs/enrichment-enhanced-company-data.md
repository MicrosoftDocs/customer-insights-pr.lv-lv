---
title: Bagātiniet uzņēmuma profilus, izmantojot uzlabotus uzņēmuma datus
description: Bagātiniet un normalizējiet uzņēmuma datus, izmantojot Microsoft modeļus.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 131ef3d1e123628779609ddec368cfef8f4d607e
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 06/29/2022
ms.locfileid: "9054257"
---
# <a name="enrich-company-profiles-with-enhanced-company-data"></a>Bagātiniet uzņēmuma profilus, izmantojot uzlabotus uzņēmuma datus

Izmantojiet Microsoft modeļus un kompilētos uzņēmuma datus, lai labotu, papildinātu un standartizētu savus uzņēmuma profilus. Mēs izmantosim [formātu](/common-data-model/schema/core/applicationcommon/account) Common Data Model, lai nodrošinātu labāku precizitāti un ieskatus.

Varat arī [uzlabot uzņēmuma datus par datu avotiem](data-sources-enrichment.md), lai uzlabotu atbilstības precizitāti datu apvienošanas procesā.

Valsts uzņēmumiem Amerikas Savienotajās Valstīs ir pieejama tāda informācija kā ieņēmumi, akciju atzīmēšana, rūpniecība un daudz kas cits.  

## <a name="how-we-enhance-company-data"></a>Kā mēs uzlabojam uzņēmuma datus

Mūsu modelis iziet divpakāpju procesu, lai uzlabotu uzņēmuma profilu. Pirmkārt, tas normalizē uzņēmuma nosaukumu. Piemēram, *Microsoft Corp* tiks labots un standartizēts Microsoft *corporation*. Tas mēģina atrast atbilstību Microsoft kompilētajos uzņēmuma datos. Ja tiek atrasta atbilstība, mēs bagātinām uzņēmuma profilu ar informāciju no mūsu apkopotajiem uzņēmuma datiem, tostarp uzņēmuma nosaukuma.

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

- Apstipriniet uzņēmuma identitāti. Mēs nepārbaudām, vai ievade ir esoša organizācija vai ka uzņēmums izmanto izvadi kā standarta nosaukumu.
- Visaptveroši aptver uzņēmumus visā pasaulē. Microsoft apkopotajiem uzņēmuma datiem ir globāls pārklājums, taču tie piedāvā lielāko daļu pārklājuma Austrālijā, Kanādā, Apvienotajā Karalistē un Amerikas Savienotajās Valstīs.
- Standartizējiet uzņēmuma adreses visā pasaulē. Pašlaik mēs atbalstām adrešu standartizēšanu šajās valstīs vai reģionos: Austrālijā, Kanādā, Francijā, Vācijā, Itālijā, Japānā, Apvienotajā Karalistē un Amerikas Savienotajās Valstīs.
- Garantēt datu precizitāti vai svaigumu. Tā kā uzņēmējdarbības informācija bieži mainās, mēs nevaram garantēt, ka sniegtie uzlabotie uzņēmuma dati vienmēr ir precīzi vai atjaunināti.

## <a name="configure-the-enrichment"></a>Bagātināto datu konfigurēšana

1. Dodieties uz **Dati** > **Bagātināšana** un atlasiet cilni **Atklāt**.

1. Atlasiet **Bagātināt manus datus** elementā **Uzlabotie uzņēmuma dati**.

   :::image type="content" source="media/enhanced-company-data-tile.png" alt-text="Bagātināšanas flīzes bagātināšanas centrā uzņēmuma datiem.":::

1. Pārskatiet pārskatu un pēc tam atlasiet **Tālāk**.

1. **Atlasiet klienta datu kopu** un izvēlieties profilu vai segmentu, kuru vēlaties bagātināt. Klienta *entītija* bagātina visus jūsu klientu profilus, savukārt segments bagātina tikai šajā segmentā ietvertos klientu profilus.

1. Atlasiet, kāda veida laukus no sava uzņēmuma profiliem izmantot, lai nodrošinātu atbilstību Microsoft apkopotajiem uzņēmuma datiem. Šāda atlase ietekmēs kartēšanas laukus, kuriem jums būs piekļuve nākamajā darbībā.

1. Atlasiet **Tālāk**.

1. Kartējiet sava uzņēmuma laukus uz uzņēmuma datiem no Microsoft. Lai nodrošinātu lielāku atbilstības precizitāti, pievienojiet papildu laukus.

    :::image type="content" source="media/enhanced-company-data-mapping.png" alt-text="Datu kartēšanas solis, konfigurējot uzņēmuma bagātināšanu.":::

1. Lai pabeigtu lauka kartēšanu, atlasiet **Tālāk**.

1. **Norādiet bagātināšanas un izvades entītijas** **nosaukumu**.

1. Pēc izvēļu pārskatīšanas atlasiet **Saglabāt bagātināšanu**.

1. Atlasiet **Palaist**, lai sāktu bagātināšanas procesu, vai aizveriet, lai **atgrieztos bagātināšanas** lapā.

## <a name="view-enrichment-results"></a>Bagātināšanas rezultātu skatīšana

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

### <a name="overview-card"></a>Pārskata kartīte

Atskaites **elements Klientu izmaiņas** rāda detalizētu informāciju par bagātināšanas pārklājumu

- **Uzņēmumi apstrādāti un mainīti**: Klientu uzņēmumu profilu skaits, kas tika veiksmīgi bagātināti.
- **Uzņēmumi, kas apstrādāti un nav mainīti**: klientu uzņēmumu profilu skaits, kas tika atzīti, bet netika mainīti. Tas parasti notiek, ja ievades dati ir derīgi un bagātināšana tos nevar uzlabot.
- **Uzņēmumi nav apstrādāti un nav mainīti**: klientu uzņēmumu profilu skaits, kas netika atpazīti. Tas parasti notiek ievades datiem, kas ir nederīgi vai ko bagātināšana neatbalsta.

## <a name="next-steps"></a>Nākamās darbības

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
