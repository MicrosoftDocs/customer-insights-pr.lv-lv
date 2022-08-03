---
title: Bagātiniet klientu profilus ar identitātes datiem no LiveRamp (priekšskatījums)
description: Bagātiniet klientu profilus ar LiveRamp datiem.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 49bf558209ca91ab9d8db945862a57adccee1f6b
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196357"
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

1. Pārskatiet un sniedziet savu piekrišanu [Datu konfidencialitātei un atbilstībai](#data-privacy-and-compliance), atlasot **Es piekrītu**.

1. Atlasiet **Verificēt**, lai validētu konfigurāciju, un pēc tam atlasiet **Saglabāt**.

### <a name="data-privacy-and-compliance"></a>Datu konfidencialitāte un atbilstība

Kad jūs iespējojat Dynamics 365 Customer Insights datu pārsūtīšanu uz LiveRamp, jūs atļaujat pārsūtīt datus ārpus atbilstības robežas, tostarp potenciāli sensitīvus Dynamics 365 Customer Insights datus, piemēram, Personas datus. Microsoft pārsūtīs šādus datus pēc jūsu norādījumiem, taču jūs esat atbildīgs par to, lai LiveRamp izpildītu visas jūsu iespējamās konfidencialitātes vai drošības saistības. Lai iegūtu papildinformāciju, pārskatiet [Microsoft paziņojumu par konfidencialitāti](https://go.microsoft.com/fwlink/?linkid=396732). Jūsu Dynamics 365 Customer Insights administrators var noņemt šo bagātināšanas funkciju jebkurā laikā, lai pārtrauktu izmantot šo funkcionalitāti.

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
