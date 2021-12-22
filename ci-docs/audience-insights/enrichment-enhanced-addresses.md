---
title: Adreses uzlabošanas bagātināšana (video)
description: Bagātināt un normalizēt klientu profilu adrešu informāciju, izmantojot Microsoft modeļus.
ms.date: 12/16/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: d2c174b7882382faf4c363198982317ee21fdd4b
ms.sourcegitcommit: e141a6a34a985cca68f03082a700ed27f2f3c0c1
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 12/17/2021
ms.locfileid: "7927520"
---
# <a name="enrichment-of-customer-profiles-with-enhanced-addresses"></a>Klientu profilu bagātināšana ar uzlabotām adresēm

Datu adreses var būt nestrukturētas, nepilnīgas vai nepareizas. Izmantojiet Microsoft modeļus, lai normalizētu un bagātinātu adreses [Common Data Model formātā](/common-data-model/schema/core/applicationcommon/address), lai iegūtu labāku precizitāti un ieskatus.

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

Paplašinātās adreses darbojas tikai ar vērtībām, kas jau ir jūsu nosūtāmos adrešu datos. Modelis: 

1. nepārbauda, vai adrese ir derīga.
2. nepārbauda, vai ir derīga kāda no vērtībām, piemēram, pasta indeksi vai pasta indeksu nosaukumi.
3. nemaina neatpazītās vērtības.

Modelis izmanto algoritmiskās mācīšanās metodes, lai uzlabotu adreses. Lai gan mēs piemērojam augstu ticamības slieksni, kad modelis maina ievades vērtību, tāpat kā jebkuram uz algoritmisko mācīšanos balstītam modelim, 100 procentu precizitāte netiek garantēta.

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

Adresēs jābūt norādītai valsts/reģiona vērtībai. Netiek apstrādātas adreses tām valstīm vai reģioniem, kas netiek atbalstīti, un adresēm, kurām nav nodrošināta neviena valsts vai reģions.

## <a name="configure-the-enrichment"></a>Bagātināto datu konfigurēšana

1. Dodieties uz **Dati** > **Bagātināšana**.

1. Elementā **Paplašinātās adreses** atlasiet **Bagātināt savus datus**.

   :::image type="content" source="media/enhanced-addresses-tile.png" alt-text="Elementa Paplašinātās adreses ekrānuzņēmums.":::

1. Atlasiet **Klientu datu kopu** un izvēlieties entītiju, kurā ir ietvertas bagātināmās adreses. Varat atlasīt entītiju *Klients*, lai bagātinātu adreses visos klientu profilos, vai atlasīt segmenta entītiju, lai bagātinātu adreses tikai šajā segmentā iekļautajos klientu profilos.

1. Atlasiet adrešu formatēšanas veidu datu kopā. Izvēlieties **Viena atribūta adresi**, ja datu adresēs tiek izmantots viens lauks. Izvēlieties **Vairāku atribūta adresi**, ja datu adresēs tiek izmantots vairāk nekā viens datu lauks.

   > [!NOTE]
   > Valsts/reģions ir obligāts gan viena atribūta, gan vairāku atribūtu adresēs. Adreses, kurās nav derīgu vai atbalstītu valsts/reģiona vērtību, netiks bagātinātas.

1.  Kartējiet adreses laukus no savas vienotās klienta entītijas.

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="Paplašināta adrešu lauku kartējuma lapa.":::

1. Lai pabeigtu lauka kartēšanu, atlasiet **Tālāk**.

1. Norādiet bagātināto datu nosaukumu un izvades entitījas nosaukumu.

1. Pēc izvēļu pārskatīšanas atlasiet **Saglabāt vidi**.

## <a name="enrichment-results"></a>Bagātināšanas rezultāti

Lai sāktu bagātināšanas procesu, komandjoslā atlasiet **Palaist**. Varat arī ļaut sistēmai palaist bagātināšanu automātiski kā daļu no [plānotās atsvaidzināšanas](system.md#schedule-tab). Apstrādes laiks ir atkarīgs no klientu datu lieluma.

Pēc bagātināšanas procesa noslēgšanas varat pārskatīt tikko bagātinātos klientu profilu datus, dodoties uz sadaļu **Mana bagātināšana**. Turklāt jūs redzēsit pēdējā atjauninājuma laiku un bagātināto profilu skaitu.

Jūs varat piekļūt detalizētam katra bagātināta profila skatam, atlasot opciju **Skatīt bagātinātos datus**.

### <a name="overview-card"></a>Pārskata karte

Pārskata kartē ir parādīta detalizēta informācija par bagātināšanas aptvērumu. 

* **Klienti apstrādāja un mainīja** : veiksmīgi bagātināto klientu profilu skaits.

* **Klienti apstrādāti un nav** mainīti : atpazīto, bet nemainīto klientu profilu skaits. Tas parasti notiek, ja ievades dati ir derīgi un bagātināšana tos nevar uzlabot.

* **Klienti nav apstrādāti un nav** mainīti : neatpazītu profilu skaits. Parasti ievades datiem, kas nav derīgi vai ko neatbalsta bagātināšana.

## <a name="next-steps"></a>Nākamās darbības

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

[!INCLUDE[footer-include](../includes/footer-banner.md)]
