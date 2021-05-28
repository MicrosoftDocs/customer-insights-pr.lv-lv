---
title: Adreses uzlabošanas bagātināšana
description: Bagātināt un normalizēt klientu profilu adrešu informāciju, izmantojot Microsoft modeļus.
ms.date: 04/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 07271d491460764f2c738e760e41c3492f2b6de9
ms.sourcegitcommit: 27f9dd837304ef9fc00f055a6e900fbf6fce1429
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 04/30/2021
ms.locfileid: "5965587"
---
# <a name="enrichment-of-customer-profiles-with-enhanced-addresses"></a>Klientu profilu bagātināšana ar uzlabotām adresēm

Datu adreses var būt nestrukturētas, nepilnīgas vai nepareizas. Izmantojiet Microsoft modeļus, lai normalizētu un bagātinātu adreses [Common Data Model formātā](/common-data-model/schema/core/applicationcommon/address), lai iegūtu labāku precizitāti un ieskatus.

## <a name="how-we-enhance-addresses"></a>Adrešu uzlabošana

Mūsu modelis iet cauri divsoļu procesam, lai uzlabotu adresi. Vispirms tiek parsēta adrese, lai identificētu tās komponentus, un tie tiek ievietoti strukturētā formātā. Pēc tam mēs izmantojam intelektu, lai labotu, pabeigtu un standartizētu adreses vērtības.

### <a name="example"></a>Piemērs

Adreses informācija var būt nestandarta formātā un ietvert pareizrakstības kļūdas. Modelis var novērst šīs problēmas un izveidot konsekventas adreses vienotā klientu profilos.

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

Modelis izmanto algoritmiskās mācīšanās metodes, lai uzlabotu adreses. Kamēr mēs izmantojam augstu precizitātes sliekšņa līmeni brīdī, kad modelis maina ievades vērtību, tāpat kā jebkurš modelis, kura pamatā ir AR ARV, netiek garantēta 100% precizitāte.

## <a name="supported-countries-or-regions"></a>Atbalstītās valstis vai reģioni

Pašlaik mēs atbalstītu adrešu bagātināšanu šajās valstīs vai reģionos: 

- Austrālija
- Kanāda
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
   > Gan vienas atribūta, gan vairāku atribūtu adresēs valsts/reģions ir obligāts. Adreses, kurās nav derīgu vai atbalstītu valsts/reģiona vērtību, netiks bagātinātas

1.  Kartējiet adreses laukus no savas vienotās klienta entītijas.

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="Paplašināta adrešu lauku kartējuma lapa.":::

1. Lai pabeigtu lauka kartēšanu, atlasiet **Tālāk**.

1. Norādiet bagātināto datu nosaukumu un izvades entitījas nosaukumu.

1. Pēc izvēļu pārskatīšanas atlasiet **Saglabāt vidi**.

## <a name="enrichment-results"></a>Bagātināšanas rezultāti

Lai sāktu bagātināšanas procesu, komandjoslā atlasiet **Palaist**. Varat arī ļaut sistēmai palaist bagātināšanu automātiski kā daļu no [plānotās atsvaidzināšanas](system.md#schedule-tab). Apstrādes laiks ir atkarīgs no klientu datu lieluma.

Pēc bagātināšanas procesa noslēgšanas varat pārskatīt tikko bagātinātos klientu profilu datus, dodoties uz sadaļu **Mana bagātināšana**. Turklāt jūs redzēsit pēdējā atjauninājuma laiku un bagātināto profilu skaitu.

Jūs varat piekļūt detalizētam katra bagātināta profila skatam, atlasot opciju **Skatīt bagātinātos datus**.

## <a name="next-steps"></a>Nākamās darbības

Būvējiet virs saviem bagātinātajiem klientu datiem. Veidojiet [segmentus](segments.md), [mērus](measures.md)un pat [eksportējiet datus](export-destinations.md), lai klientiem sniegtu personalizētas iespējas.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
