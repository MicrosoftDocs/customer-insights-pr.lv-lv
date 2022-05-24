---
title: Datu avots bagātināšana
description: Bagātiniet datu avotus pirms datu apvienošanas procesa.
ms.date: 03/02/2022
ms.subservice: audience-insights
ms.topic: how-to
author: NimrodMagen
ms.author: nimagen
ms.reviewer: v-wendysmith
manager: shellyha
ms.openlocfilehash: d1e14d2d4e718d71ccbd2afd259a350ad5c9e69a
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755695"
---
# <a name="enrichment-for-data-sources-preview"></a>Datu avotu bagātināšana (priekšskatījums)

Izmantojiet datus no tādiem avotiem kā Microsoft un citi partneri, lai bagātinātu klientu datus pirms datu apvienošanas. Datu avots bagātināšana palīdz radīt augstāku datu pilnīgumu un kvalitāti, kas var palīdzēt sasniegt labākus rezultātus, kad esat apvienojis savus datus. Piemēram, normalizēta un standartizēta formāta izmantošana adresēm palielina atbilstības rezultātu kvalitāti. Atbalstīto bagātinājumu sarakstu skatīt [atbalstītajos datu avots bagātināšanas iespējās](#supported-data-source-enrichments).

## <a name="enrich-a-data-source"></a>Bagātiniet datu avots

Lai izveidotu vai rediģētu bagātinājumus, jums ir jābūt līdzstrādnieka vai administratora atļaujām. Lai iegūtu papildinformāciju, skatiet [Atļaujas](permissions.md).  

1. Dodieties uz **Data** > **Unify**. Atlasiet entītiju, kuru vēlaties bagātināt, un atlasiet vienu atribūtu kā entītijas primāro atslēgu. Papildinformāciju skatiet sadaļā [Primārās atslēgas atlasīšana](map-entities.md#select-primary-key-and-semantic-type-for-attributes).

1. Dodieties uz **Dati** > **Datu avoti**.

1. Atlasiet vertikālo daudzpunkti blakus datu avots, kuru vēlaties bagātināt, un atlasiet **Bagātināt**.

   :::image type="content" source="media/data_sources_enrich_discover.png" alt-text="Datu avotu bagātināšanas lapa.":::

   Cilnē **Atklāšana** tiek parādītas atbalstītās [datu avots bagātināšanas opcijas](#supported-data-source-enrichments).

1. Atlasiet **Bagātināt manus datus**, lai konfigurētu datu avots bagātināšanu. Izvades entītijas nosaukums tiek aizpildīts automātiski.

## <a name="supported-data-source-enrichments"></a>Atbalstītie datu avots bagātinājumi

Datu avotiem pašlaik ir pieejami šādi bagātinājumi. Pārskatiet detalizētus bagātināšanas soļus, lai uzzinātu, kā to konfigurēt.

- [Uzlabotas adreses](enrichment-enhanced-addresses.md)
- [Uzlaboti uzņēmuma dati](enrichment-enhanced-company-data.md)

## <a name="manage-existing-data-source-enrichments"></a>Esošo datu avots bagātināšanas pārvaldība

Lai skatītu visus konfigurētos bagātinātos datus, dodieties uz **Manas bagātināšanas** cilni.

Atlasiet bagātināšanu, lai redzētu pieejamās opcijas. Lai skatītu opcijas, varat arī saraksta elementā atlasīt daudzpunkti (...). Ja konfigurējāt vairākus bagātinātus uzlabojumus, varat izmantot meklēšanas lodziņu, lai to ātri atrastu.

Varat skatīt, rediģēt, palaist vai dzēst datu avots bagātināšanu. Papildinformāciju skatiet manage [existing enrichments](enrichment-hub.md).
