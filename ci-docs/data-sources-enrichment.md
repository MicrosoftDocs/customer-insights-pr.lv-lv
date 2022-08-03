---
title: Datu avotu bagātināšana (priekšskatījums)
description: Pirms datu apvienošanas procesa bagātiniet datu avotus.
ms.date: 05/20/2022
ms.subservice: audience-insights
ms.topic: how-to
author: NimrodMagen
ms.author: nimagen
ms.reviewer: v-wendysmith
manager: shellyha
ms.openlocfilehash: 98e9e330e7ef9cf085caa94a506fa788cebdd67b
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 07/28/2022
ms.locfileid: "9207192"
---
# <a name="enrichment-for-data-sources-preview"></a>Datu avotu bagātināšana (priekšskatījums)

Izmantojiet datus no tādiem avotiem kā Microsoft un citi partneri, lai bagātinātu klientu datus pirms datu apvienošanas. Datu avots bagātināšana palīdz radīt augstāku datu pilnīgumu un kvalitāti, kas var palīdzēt sasniegt labākus rezultātus, kad esat apvienojis savus datus. Piemēram, izmantojot normalizētu un standartizētu adrešu formātu, tiek palielināta atbilstības rezultātu kvalitāte. Atbalstīto bagātinājumu sarakstu skatiet sadaļā [atbalstītās datu avots bagātināšanas iespējas](#supported-data-source-enrichments).

## <a name="enrich-a-data-source"></a>Bagātiniet datu avots

Jums ir jābūt līdzstrādnieka [vai administratora](permissions.md) atļaujām, lai izveidotu vai rediģētu bagātinājumus.  

1. Dodieties uz **Data** > **Unify**. Atlasiet entītiju, kuru vēlaties bagātināt, un atlasiet vienu atribūtu [kā entītijas primāro atslēgu](map-entities.md#select-primary-key-and-semantic-type-for-attributes).

1. Dodieties uz **Dati** > **Datu avoti**.

1. Atlasiet vertikālo elipsi (&vellip;) blakus datu avots, kuru vēlaties bagātināt, un atlasiet **Bagātināt**.

   :::image type="content" source="media/data_sources_enrich.png" alt-text="Datu avotu lapa ar iezīmētu bagātinājumu":::

   Cilnē **Discover** tiek parādītas atbalstītās [datu avots bagātināšanas opcijas](#supported-data-source-enrichments).

   :::image type="content" source="media/data_sources_enrich_discover.png" alt-text="Datu avotu bagātināšanas lapa.":::

1. Atlasiet **Bagātināt manus datus**, lai konfigurētu datu avots bagātināšanu. Izvades entītijas nosaukums tiek aizpildīts automātiski.

## <a name="supported-data-source-enrichments"></a>Atbalstītie datu avots bagātinājumi

Datu avotiem pašlaik ir pieejami šādi bagātinājumi. Pārskatiet detalizētas darbības bagātināšanai, lai uzzinātu, kā to konfigurēt.

- [Uzlabotas adreses](enrichment-enhanced-addresses.md)
- [Uzlaboti uzņēmuma dati](enrichment-enhanced-company-data.md)
- [Identitātes dati no LiveRamp](enrichment-liveramp.md)

## <a name="manage-existing-data-source-enrichments"></a>Esošo datu avots bagātināšanas pārvaldība

Dodieties uz **Dati** > **Bagātināšana**. **Cilnē Mani bagātinājumi** skatiet konfigurētos bagātinājumus, to statusu, bagātināto klientu skaitu un pēdējo reizi, kad dati tika atsvaidzināti. Bagātinājumu sarakstu var kārtot pēc jebkuras kolonnas vai izmantot meklēšanas lodziņu, lai atrastu bagātinājumu, kuru vēlaties pārvaldīt.

Atlasiet bagātināšanu, lai redzētu pieejamās opcijas. Varat arī atlasīt vertikālo elipsi (&vellip;) saraksta elementā, lai redzētu opcijas.

Varat skatīt, rediģēt, palaist vai dzēst datu avots bagātināšanu. Papildinformāciju skatiet sadaļā [Esošo bagātinājumu](enrichment-hub.md#manage-existing-enrichments) pārvaldība.
