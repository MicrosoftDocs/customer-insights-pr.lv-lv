---
title: Uzņēmuma datu uzlabošana
description: Bagātiniet un normalizējiet uzņēmuma datus ar Microsoft modeļiem.
ms.date: 11/05/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 9bfb96d47de4ec98325e644c60752fc7cab2706c
ms.sourcegitcommit: 6efcba688d1db1a5d6343c229f292a26c48fc007
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 11/05/2021
ms.locfileid: "7770179"
---
# <a name="enrichment-of-company-profiles-with-enhanced-company-data"></a>Uzņēmuma profilu bagātināšana ar uzlabotiem uzņēmuma datiem

Izmantojiet Microsoft modeļus un apkopotos uzņēmuma datus, lai labotu, papildinātu un standartizētu uzņēmuma profilus. Mēs izmantosim [common data model](/common-data-model/schema/core/applicationcommon/account) formātu, lai uzlabotu precizitāti un ieskatus.

## <a name="how-we-enhance-company-data"></a>Kā mēs uzlabojam uzņēmuma datus

Mūsu modelis iziet divpakāpju procesu, lai uzlabotu uzņēmuma profilu. Pirmkārt, tas normalizē uzņēmuma nosaukumu. *Piemēram, Microsoft Corp tiks* labots un standartizēts Microsoft *corporation*. Tā mēģina atrast atbilstību Microsoft apkopotajos uzņēmuma datos. Ja tiek atrasta atbilstība, mēs bagātinām uzņēmuma profilu ar informāciju no mūsu apkopotajiem uzņēmuma datiem, ieskaitot uzņēmuma nosaukumu.


### <a name="example"></a>Piemērs

Iespējams, jūsu uzņēmuma informācija neatbilst standartizētam formātam un satur pareizrakstības kļūdas. Modelis mēģina novērst šīs problēmas un izveidot konsekventu informāciju.

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

Uzlabotajiem datiem ir daži ierobežojumi. Modelis neatbalsta vienumus zemāk redzamajā sarakstā.

1.  Apstipriniet uzņēmuma identitāti. Mēs nepārbaudām, vai ievade ir esoša organizācija vai vai uzņēmums izmanto izvadi kā savu standarta nosaukumu.
2.  Visaptveroši aptver uzņēmumus visā pasaulē. Microsoft apkopotajiem uzņēmuma datiem ir globāls pārklājums, bet tie piedāvā lielāko pārklājumu Austrālijā, Kanādā, Apvienotajā Karalistē un Amerikas Savienotajās Valstīs.
3.  Garantēt datu precizitāti vai svaigumu. Tā kā biznesa informācija bieži mainās, mēs nevaram garantēt, ka sniegtie uzlabotie uzņēmuma dati vienmēr ir precīzi vai atjaunināti.

## <a name="configure-the-enrichment"></a>Bagātināto datu konfigurēšana

1. Dodieties uz **Dati** > **Bagātināšana**.

1. Elementā Uzlabotie uzņēmuma dati atlasiet **Bagātināt** **·** manus datus.

   :::image type="content" source="media/enhanced-company-data-tile.png" alt-text="Bagātināšanas flīzes bagātināšanas mezglā uzņēmuma datiem.":::

1. Atlasiet **Klientu datu kopu** un izvēlieties entītiju, kurā ir ietvertas bagātināmās adreses. Varat atlasīt entītiju *Klients*, lai bagātinātu adreses visos klientu profilos, vai atlasīt segmenta entītiju, lai bagātinātu adreses tikai šajā segmentā iekļautajos klientu profilos.

1. Atlasiet, kāda tipa lauki no uzņēmuma profiliem jāizmanto saskaņošanai ar Microsoft apkopotajiem uzņēmuma datiem. Šāda atlase ietekmēs kartēšanas laukus, kuriem jums būs piekļuve nākamajā darbībā.

1.  Kartējiet uzņēmuma laukus no vienotās klienta entītijas. Jo vairāk atslēgas identifikatoru un lauku tiek kartēti, jo lielāka ir lielāka atbilstības līmeņa iespējamība.

    :::image type="content" source="media/enhanced-company-data-mapping.png" alt-text="Datu kartēšanas darbība, konfigurējot uzņēmuma bagātināšanu.":::

1. Lai pabeigtu lauka kartēšanu, atlasiet **Tālāk**.

1. Norādiet bagātināto datu nosaukumu un izvades entitījas nosaukumu.

1. Pēc izvēļu pārskatīšanas atlasiet **Saglabāt vidi**.

## <a name="enrichment-results"></a>Bagātināšanas rezultāti

Lai sāktu bagātināšanas procesu, komandjoslā atlasiet **Palaist**. Varat arī ļaut sistēmai palaist bagātināšanu automātiski kā daļu no [plānotās atsvaidzināšanas](system.md#schedule-tab). Apstrādes laiks ir atkarīgs no klientu datu lieluma.

Pēc bagātināšanas procesa noslēgšanas varat pārskatīt tikko bagātinātos klientu profilu datus, dodoties uz sadaļu **Mana bagātināšana**. Turklāt jūs redzēsit pēdējā atjauninājuma laiku un bagātināto profilu skaitu.

Jūs varat piekļūt detalizētam katra bagātināta profila skatam, atlasot opciju **Skatīt bagātinātos datus**.

## <a name="next-steps"></a>Nākamās darbības

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

[!INCLUDE[footer-include](../includes/footer-banner.md)]
