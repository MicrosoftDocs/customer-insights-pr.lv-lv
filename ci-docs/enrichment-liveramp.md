---
title: LiveRamp identitātes datu bagātināšana
description: Bagātiniet klientu profilus ar LiveRamp datiem.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: e8a130865267b57c89157b44be3d4bba3dc2fb4e
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 06/13/2022
ms.locfileid: "8954004"
---
# <a name="enrich-customer-profiles-with-identity-data-from-liveramp-preview"></a>Bagātiniet klientu profilus ar LiveRamp identitātes datiem (priekšskatījums)

LiveRamp nodrošina deterministisku bezsaistes identitātes izšķirtspēju un klientu datu konsolidāciju. Klienta datu personiskos identifikatorus varat kartēt uz AbiliTec identitātes grafiku un saņemt AbiliTec ID. Pēc tam varat izmantot šos ID, lai labāk apvienotu klientu datus.

## <a name="supported-countriesregions"></a>Atbalstītās valstis/reģioni

Pašlaik mēs atbalstām klientu profilu bagātināšanu tikai ar LiveRamp datiem Amerikas Savienotajās Valstīs.

## <a name="prerequisites"></a>Priekšnoteikumi

- Aktīvs LiveRamp abonements. Lai iegūtu abonementu, sazinieties ar LiveRamp konta komandu vai lai iegūtu papildinformāciju [dynamics@liveramp.com](mailto:dynamics@liveramp.com).

- Aktīvs AbiliTec abonements ar klienta ID un noslēpumu, lai piekļūtu API. Papildinformāciju skatiet abiliTec [API izstrādātāju centrmezglā](https://developers.liveramp.com/abilitec-api/).

- LiveRamp [savienojumu](connections.md)[konfigurē](#configure-the-connection-for-liveramp) administrators.

## <a name="configure-the-connection-for-liveramp"></a>LiveRamp savienojuma konfigurēšana

Jums jābūt Customer Insights administratoram [un](permissions.md#admin) aktīvam LiveRamp klienta ID un slepenam.

1. Konfigurējot bagātināšanu, atlasiet **Pievienot savienojumu** vai dodieties uz **Administrēšanas** > **savienojumi** un atlasiet **Iestatīt** elementā LiveRamp.

   :::image type="content" source="media/liveramp-connection.png" alt-text="Konfigurācijas rūts, lai iestatītu savienojumu ar LiveRamp AbiliTec pakalpojumu.":::

1. Ievadiet savienojuma nosaukumu un derīgu LiveRamp klienta ID un noslēpumu.

1. Pārskatiet un sniedziet savu piekrišanu [Datu konfidencialitātei un atbilstībai](#data-privacy-and-compliance), atlasot **Es piekrītu**.

1. Atlasiet **Pārbaudīt**, lai validētu konfigurāciju, un pēc tam atlasiet **Saglabāt**.

### <a name="data-privacy-and-compliance"></a>Datu konfidencialitāte un atbilstība

Kad iespējojat Dynamics 365 Customer Insights pārsūtīt datus uz LiveRamp, jūs atļaujat pārsūtīt datus ārpus atbilstības robežas, tostarp potenciāli sensitīvus Dynamics 365 Customer Insights datus, piemēram, Personas datus. Microsoft pārsūtīs šādus datus pēc jūsu norādījumiem, bet jūs esat atbildīgs par to, lai LiveRamp atbilstu visiem jūsu konfidencialitātes vai drošības pienākumiem. Lai iegūtu papildinformāciju, pārskatiet Microsoft paziņojumu par [konfidencialitāti](https://go.microsoft.com/fwlink/?linkid=396732). Jūsu Dynamics 365 Customer Insights administrators var noņemt šo bagātināšanas funkciju jebkurā laikā, lai pārtrauktu izmantot šo funkcionalitāti.

## <a name="configure-the-enrichment"></a>Bagātināto datu konfigurēšana

1. Dodieties uz **Dati** > **Bagātināšana** un atlasiet cilni **Atklāt**.

1. Atlasiet **Bagātināt manus datus** elementā **Identitāte** no LiveRamp elementa.

   :::image type="content" source="media/liveramp-tile.png" alt-text="Identitātes elements bagātināšanas pārskata lapā.":::

1. Pārskatiet pārskatu un pēc tam atlasiet **Tālāk**.

1. Atlasiet savienojumu. Ja tāds nav pieejams, sazinieties ar administratoru.

1. Atlasiet **Tālāk**.

1. **Atlasiet klienta datu kopu** un izvēlieties profilu vai segmentu, kuru vēlaties bagātināt ar LiveRamp identitātes datiem. Klientu *uzņēmums* bagātina visus jūsu klientu profilus, savukārt segments bagātina tikai šajā segmentā esošos klientu profilus.

1. Definējiet, kāda tipa laukus no vienotajiem profiliem izmantot, lai saskaņotu identitātes datus no LiveRamp. Nepieciešams vismaz viens no laukiem **Nosaukums un adrese**, **E-pasts** vai **Tālrunis**. Lai nodrošinātu augstāku atbilstības precizitāti, pievienojiet citus laukus. Atlasiet **Tālāk**.

1. Kartējiet savus laukus uz LiveRamp identifikācijas datiem.

   :::image type="content" source="media/liveramp-data-mapping.png" alt-text="LiveRamp bagātināšanas datu kartēšanas opcijas.":::

1. Lai pabeigtu lauka kartēšanu, atlasiet **Tālāk**.

1. **Norādiet bagātināšanas nosaukumu** un entītijas **Izvade nosaukumu**.

1. Pēc izvēļu pārskatīšanas atlasiet **Saglabāt bagātināšanu**.

1. Atlasiet **Palaist**, lai sāktu bagātināšanas procesu, vai tuvu, lai **atgrieztos lapā Bagātinājumi**.

## <a name="enrichment-results"></a>Bagātināšanas rezultāti

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

Klientu **skaits, kas bagātināts ar lauku**, nodrošina katra bagātinātā lauka aptvērumu.

## <a name="next-steps"></a>Nākamās darbības

Pilnveidojiet savus bagātinātos klientu datus. Izmantojiet AbiliTec ID, lai konsolidētu klientu profilus personas skatā.
[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
