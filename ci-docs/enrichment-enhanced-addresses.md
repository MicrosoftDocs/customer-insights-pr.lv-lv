---
title: Adreses uzlabošanas bagātināšana (satur video)
description: Bagātināt un normalizēt klientu profilu adrešu informāciju, izmantojot Microsoft modeļus.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
searchScope:
- ci-data-sources-enrichment
- ci-data-sources-enrichment-details
- ci-enrichments
- ci-enrichment-wizard
- customerInsights
ms.openlocfilehash: f6279b9bb721d99d66f73e8dc839a92f1ad90140
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 06/13/2022
ms.locfileid: "8953820"
---
# <a name="enrichment-of-customer-profiles-with-enhanced-addresses"></a>Klientu profilu bagātināšana ar uzlabotām adresēm

Datu adreses var būt nestrukturētas, nepilnīgas vai nepareizas. Izmantojiet Microsoft modeļus, lai normalizētu un bagātinātu adreses [Common Data Model formātā](/common-data-model/schema/core/applicationcommon/address), lai iegūtu labāku precizitāti un ieskatus.

Varat arī [bagātināt adreses datu avotos](data-sources-enrichment.md), lai uzlabotu datu apvienošanas procesa atbilstības precizitāti. 

## <a name="how-we-enhance-addresses"></a>Adrešu uzlabošana

Mūsu modelis iet cauri divsoļu procesam, lai uzlabotu adresi. Vispirms tiek parsēta adrese, lai identificētu tās komponentus, un tie tiek ievietoti strukturētā formātā. Pēc tam izmantojam AI, lai labotu, pabeigtu un standartizētu adreses vērtības.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWNewo]

### <a name="example"></a>Piemērs

Adreses informācija var būt nestandarta formātā un var saturēt pareizrakstības kļūdas. Modelis var novērst šīs problēmas un izveidot konsekventas adreses vienotā klientu profilos.

```Input
4567 w main stret californa missouri 54321 us
```

```Output
- Street1: 4567 W Main St
- City: California
- StateOrProvince: MO
- ZipOrPostalCode: 54321
- CountryOrRegion: United States of America

- Address: 4567 W Main St, California, MO, 54321, United States of America
```

### <a name="limitations"></a>Ierobežojumi

Uzlabotās adreses darbojas tikai ar vērtībām, kas jau pastāv jūsu uzņemtajos adreses datos. Modelis:

1. nepārbauda, vai adrese ir derīga.
2. nepārbauda, vai ir derīga kāda no vērtībām, piemēram, pasta indeksi vai pasta indeksu nosaukumi.
3. nemaina neatpazītās vērtības.

Modelis izmanto algoritmiskās mācīšanās metodes, lai uzlabotu adreses. Tāpat kā jebkuram mašīnmācīšanās modelim, simtprocentīga precizitāte netiek garantēta.

## <a name="supported-countries-or-regions"></a>Atbalstītās valstis vai reģioni

Pašlaik mēs atbalstītu adrešu bagātināšanu šajās valstīs vai reģionos:

- Austrālija
- Kanāda
- Francija
- Vācija
- Itālija
- Japāna
- Lielbritānija
- Amerikas Savienotās Valstis

## <a name="configure-the-enrichment"></a>Bagātināto datu konfigurēšana

1. Dodieties uz **Dati** > **Bagātināšana** un atlasiet cilni **Atklāt**.

1. Elementā **Paplašinātās adreses** atlasiet **Bagātināt savus datus**.

   :::image type="content" source="media/enhanced-addresses-tile.png" alt-text="Elementa Paplašinātās adreses ekrānuzņēmums.":::

1. Pārskatiet pārskatu un pēc tam atlasiet **Tālāk**.

1. Atlasiet klienta datu kopu **un** izvēlieties profilu vai segmentu, kuru vēlaties bagātināt. Klientu *uzņēmums* bagātina visus jūsu klientu profilus, savukārt segments bagātina tikai šajā segmentā esošos klientu profilus.

1. Atlasiet adrešu formatēšanas veidu datu kopā. Izvēlieties **Viena atribūta adresi**, ja datu adresēs tiek izmantots viens lauks. Izvēlieties **Vairāku atribūta adresi**, ja datu adresēs tiek izmantots vairāk nekā viens datu lauks.

1. Atlasiet **Tālāk** un kartējiet adreses laukus no vienotās klienta entītijas.

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="Paplašināta adrešu lauku kartējuma lapa.":::

   > [!NOTE]
   > Valsts/reģions ir obligāts gan viena atribūta, gan vairāku atribūtu adresēs. Adreses, kurās nav derīgu vai atbalstītu valsts/reģiona vērtību, netiks bagātinātas.

1. Lai pabeigtu lauka kartēšanu, atlasiet **Tālāk**.

1. Norādiet **bagātināšanas un entītijas** Izvades **nosaukumu**.

1. Pēc izvēļu pārskatīšanas atlasiet **Saglabāt bagātināšanu**.

## <a name="enrichment-results"></a>Bagātināšanas rezultāti

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

Klientu **skaits, kas bagātināts ar lauku**, nodrošina katra bagātinātā lauka aptvērumu.

### <a name="overview-card"></a>Pārskata karte

Klienti **maina pārskata** karti, kurā redzama detalizēta informācija par bagātināšanas segumu:

- **Apstrādātās un mainītās** adreses: klientu profilu skaits ar veiksmīgi bagātinātām adresēm.
- **Adreses, kas apstrādātas un nav mainītas**: klientu profilu skaits ar adresēm, kas tika atpazītas, bet netika mainītas. Tas parasti notiek, kad ievades dati ir derīgi un tos nevar uzlabot ar bagātināšanu.
- **Adreses nav apstrādātas un nav mainītas**: profilu skaits ar neatpazītām adresēm. Parasti ievades datiem, kas nav derīgi vai ko neatbalsta bagātināšana.

## <a name="next-steps"></a>Nākamās darbības

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
