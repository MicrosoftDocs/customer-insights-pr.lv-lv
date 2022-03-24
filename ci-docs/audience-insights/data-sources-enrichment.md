---
title: Datu avots bagātināšana
description: Bagātināt datu avotus pirms datu apvienošanas procesa.
ms.date: 03/02/2022
ms.subservice: audience-insights
ms.topic: how-to
author: NimrodMagen
ms.author: nimagen
ms.reviewer: v-wendysmith
manager: shellyha
ms.openlocfilehash: 56f6a8ad20224922f9968f0ad3b6a0e0a400214b
ms.sourcegitcommit: 50d32a4cab01421a5c3689af789e20857ab009c4
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 03/03/2022
ms.locfileid: "8376588"
---
# <a name="enrichment-for-data-sources-preview"></a>Datu avotu bagātināšana (priekšskatījums)

Izmantojiet datus no tādiem avotiem kā Microsoft un citi partneri, lai bagātinātu klientu datus pirms datu apvienošanas. Datu avots bagātināšana palīdz nodrošināt augstāku datu pilnīgumu un kvalitāti, kas var palīdzēt sasniegt labākus rezultātus, kad jūs apvienojat savus datus. Piemēram, normalizēta un standartizēta adrešu formāta izmantošana palielina atbilstības rezultātu kvalitāti. Atbalstīto bagātināšanu sarakstu skatiet [atbalstītajās datu avots bagātināšanas opcijās](#supported-data-source-enrichments).

## <a name="enrich-a-data-source"></a>Bagātināt datu avots

Lai izveidotu vai rediģētu bagātināšanas, jums ir jābūt līdzstrādnieka vai administratora atļaujām. Lai iegūtu papildinformāciju, skatiet [Atļaujas](permissions.md).  

1. Dodieties uz **DataUnify** > **·**. Atlasiet entītiju, kuru vēlaties bagātināt, un atlasiet vienu atribūtu kā entītijas primāro atslēgu. Plašāku informāciju skatiet [Select primary key](map-entities.md#select-primary-key-and-semantic-type-for-attributes).

1. Dodieties uz **Dati** > **Datu avoti**.
 
1. Atlasiet vertikālo daudzpunkti blakus datu avots, kuru vēlaties bagātināt, un atlasiet **Bagātināt**.

   :::image type="content" source="media/data_sources_enrich_discover.png" alt-text="Datu avotu bagātināšanas lapa.":::

   Cilnē **Atklāšana** tiek parādītas atbalstītās [datu avots bagātināšanas opcijas](#supported-data-source-enrichments).

1. Atlasiet **Bagātināt manus datus**, lai konfigurētu datu avots bagātināšanu. Izvades entītijas nosaukums tiek aizpildīts automātiski.

## <a name="supported-data-source-enrichments"></a>Atbalstītie datu avots bagātināšanas

Pašlaik datu avotiem ir pieejami šādi bagātināšanas gadījumi. Pārskatiet detalizētas bagātināšanas darbības, lai uzzinātu, kā to konfigurēt.

- [Uzlabotas adreses](enrichment-enhanced-addresses.md)
- [Uzlaboti uzņēmuma dati](enrichment-enhanced-company-data.md)

## <a name="manage-existing-data-source-enrichments"></a>Pārvaldīt esošās datu avots bagātināšanas

Lai skatītu visus konfigurētos bagātinātos datus, dodieties uz **Manas bagātināšanas** cilni.

Atlasiet bagātināšanu, lai redzētu pieejamās opcijas. Lai skatītu opcijas, varat arī saraksta elementā atlasīt daudzpunkti (...). Ja konfigurējāt vairākus bagātinātus uzlabojumus, varat izmantot meklēšanas lodziņu, lai to ātri atrastu.

Bagātināšanas datu avots var skatīt, rediģēt, palaist vai dzēst. Plašāku informāciju skatiet Manage [existing enrichments](enrichment-hub.md).
