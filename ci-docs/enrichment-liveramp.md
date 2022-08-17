---
title: Bagātiniet klientu profilus ar identitātes datiem no LiveRamp (priekšskatījums)
description: Bagātiniet klientu profilus ar LiveRamp datiem.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 0aa6dc144602741b87843a5373779855ee3e334c
ms.sourcegitcommit: b1d06fe26934f12f0c5ed13e8ef1d37e52e67cc7
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 08/08/2022
ms.locfileid: "9237821"
---
# <a name="enrich-customer-profiles-with-identity-data-from-liveramp-preview"></a>Bagātiniet klientu profilus ar identitātes datiem no LiveRamp (priekšskatījums)

LiveRamp nodrošina deterministisku bezsaistes identitātes izšķirtspēju un klientu datu konsolidāciju. Jūs varat kartēt personiskos identifikatorus savos klientu datos uz AbiliTec identitātes diagrammu un saņemt AbiliTec ID. Pēc tam varat izmantot šos ID, lai labāk apvienotu savus klientu datus.

## <a name="supported-countriesregions"></a>Atbalstītās valstis/reģioni

Pašlaik mēs atbalstām klientu profilu bagātināšanu ar LiveRamp datiem tikai Amerikas Savienotajās Valstīs.

## <a name="prerequisites"></a>Priekšnoteikumi

- Aktīvs LiveRamp abonements. Lai saņemtu abonementu, sazinieties ar LiveRamp konta komandu vai lūdziet papildinformāciju [dynamics@liveramp.com](mailto:dynamics@liveramp.com).

- Aktīvs AbiliTec abonements ar klienta ID un noslēpumu, lai piekļūtu API. Papildinformāciju skatiet sadaļā [AbiliTec API izstrādātāju centrmezgls](https://developers.liveramp.com/abilitec-api/).

- LiveRamp [savienojumu](connections.md)[konfigurē](#configure-the-connection-for-liveramp) administrators.

## <a name="configure-the-connection-for-liveramp"></a>LiveRamp savienojuma konfigurēšana

Jums ir jābūt Customer Insights [administratoram](permissions.md#admin), un jums ir jābūt aktīvam LiveRamp klienta ID un slepenam.

1. Atlasiet **Pievienot savienojumu**, konfigurējot bagātināšanu, vai dodieties uz **Administratoru** > **savienojumi** un liveramp elementā atlasiet **Iestatīt**.

   :::image type="content" source="media/liveramp-connection.png" alt-text="Konfigurācijas rūts, lai iestatītu savienojumu ar LiveRamp AbiliTec pakalpojumu.":::

1. Ievadiet savienojuma nosaukumu un derīgu LiveRamp klienta ID un noslēpumu.

1. Pārskatiet datu privātumu [un atbilstību](connections.md#data-privacy-and-compliance) un atlasiet **Es piekrītu**.

1. Atlasiet **Verificēt**, lai validētu konfigurāciju, un pēc tam atlasiet **Saglabāt**.

## <a name="configure-the-enrichment"></a>Bagātināto datu konfigurēšana

1. Dodieties uz **Dati** > **Bagātināšana** un atlasiet cilni **Atklāt**.

1. Atlasiet **Bagātināt manus datus**, izmantojot **elementu Identitāte** no LiveRamp.

   :::image type="content" source="media/liveramp-tile.png" alt-text="Identitātes elements bagātināšanas pārskata lapā.":::

1. Pārskatiet pārskatu un pēc tam atlasiet **Tālāk**.

1. Atlasiet savienojumu. Ja nav pieejamu savienojumu, sazinieties ar administratoru.

1. Atlasiet **Tālāk**.

1. **Atlasiet klienta datu kopu** un izvēlieties profilu vai segmentu, kuru vēlaties bagātināt ar identitātes datiem no LiveRamp. Klienta *entītija* bagātina visus jūsu klientu profilus, savukārt segments bagātina tikai šajā segmentā ietvertos klientu profilus.

1. Definējiet, kāda veida laukus no saviem vienotajiem profiliem izmantot, lai atbilstu LiveRamp identitātes datiem. Ir nepieciešams vismaz viens no laukiem **Nosaukums un adrese**, **E-pasts** vai **Tālrunis**. Lai iegūtu lielāku atbilstības precizitāti, pievienojiet citus laukus. Atlasiet **Tālāk**.

1. Kartējiet savus laukus uz LiveRamp identifikācijas datiem.

   :::image type="content" source="media/liveramp-data-mapping.png" alt-text="Datu kartēšanas iespējas LiveRamp bagātināšanai.":::

1. Lai pabeigtu lauka kartēšanu, atlasiet **Tālāk**.

1. **Norādiet bagātināšanas nosaukumu** un izvades entītijas **nosaukumu**.

1. Pēc izvēļu pārskatīšanas atlasiet **Saglabāt bagātināšanu**.

1. Atlasiet **Palaist**, lai sāktu bagātināšanas procesu, vai aizveriet, lai **atgrieztos bagātināšanas** lapā.

## <a name="view-enrichment-results"></a>Bagātināšanas rezultātu skatīšana

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

Klientu **skaits, kas bagātināts ar lauku**, nodrošina detalizētu informāciju par katra bagātinātā lauka pārklājumu.

## <a name="next-steps"></a>Nākamās darbības

Pilnveidojiet savus bagātinātos klientu datus. Izmantojiet AbiliTec ID, lai konsolidētu klientu profilus uz personu balstītā skatā.
[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
