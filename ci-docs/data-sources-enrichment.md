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
ms.openlocfilehash: fb97b721cc82ccd23cfd1df74a0712b8fc277b8a
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082116"
---
# <a name="enrichment-for-data-sources-preview"></a>Datu avotu bagātināšana (priekšskatījums)

Izmantojiet datus no tādiem avotiem kā Microsoft un citi partneri, lai bagātinātu klientu datus pirms datu apvienošanas. Datu avots bagātināšana palīdz radīt augstāku datu pilnīgumu un kvalitāti, kas var palīdzēt sasniegt labākus rezultātus, kad esat apvienojis savus datus. Piemēram, izmantojot normalizētu un standartizētu adrešu formātu, tiek palielināta atbilstības rezultātu kvalitāte. Atbalstīto bagātinājumu sarakstu skatiet sadaļā [atbalstītās datu avots bagātināšanas iespējas](#supported-data-source-enrichments).

## <a name="enrich-a-data-source"></a>Bagātiniet datu avots

Jums ir jābūt līdzstrādnieka vai administratora atļaujām, lai izveidotu vai rediģētu bagātinājumus. Lai iegūtu papildinformāciju, skatiet [Atļaujas](permissions.md).  

1. Dodieties uz **Data** > **Unify**. Atlasiet entītiju, kuru vēlaties bagātināt, un atlasiet vienu atribūtu kā entītijas primāro atslēgu. Papildinformāciju skatiet sadaļā [Primārās atslēgas atlasīšana](map-entities.md#select-primary-key-and-semantic-type-for-attributes).

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

Lai skatītu visus konfigurētos bagātinātos datus, dodieties uz **Manas bagātināšanas** cilni.

Atlasiet bagātināšanu, lai redzētu pieejamās opcijas. Varat arī atlasīt vertikālo elipsi (&vellip;) saraksta elementā, lai redzētu opcijas. Ja konfigurējāt vairākus bagātinātus uzlabojumus, varat izmantot meklēšanas lodziņu, lai to ātri atrastu.

Varat skatīt, rediģēt, palaist vai dzēst datu avots bagātināšanu. Papildinformāciju skatiet sadaļā [Esošo bagātinājumu](enrichment-hub.md) pārvaldība.
