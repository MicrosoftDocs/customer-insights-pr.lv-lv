---
title: Vienoto klientu profilu bagātināšana
description: Izmantojiet iespējas, lai bagātinātu klientu datus.
ms.date: 11/02/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c25cfbf3808fc1534b54d2d834f1c63ff4c9fe0a
ms.sourcegitcommit: 334633cbd58f5659d20b4f87252c1a10cc7130db
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 12/03/2020
ms.locfileid: "4667103"
---
# <a name="enrichment-for-customer-profiles-preview"></a>Klientu profilu bagātināšana (priekšskatījums)

Izmantojiet avotu datus, piemēram, no Microsoft un citiem partneriem, lai bagātinātu klientu datus.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Bagātināšanas centra lapa":::

Informāciju par auditorijas ieskatiem skatiet sadaļā **Dati** > **Bagātināšana**, lai strādātu ar bagātināšanas iespējām.    
Lai izveidotu vai rediģētu bagātināšanos, jums ir nepieciešamas Līdzstrādnieka vai Administratora atļaujas. Lai iegūtu papildinformāciju, skatiet [Atļaujas](permissions.md).

Cilnē **Atklāt** atradīsiet šādus bagātinātājus:

- [Zīmoli](enrichment-microsoft-graph.md) nodrošina Microsoft Graph
- [Intereses](enrichment-microsoft-graph.md) nodrošina Microsoft Graph
- Leadspace nodrošinātie [uzņēmuma dati](enrichment-leadspace.md)
- Experian nodrošinātie [demogrāfijas dati](enrichment-experian.md)
- [Atrašanās vietas dati](enrichment-here.md) HERE Technologies nodrošinātie atrašanās vietas dati
- [Pielāgoti dati](enrichment-SFTP-custom-import.md), izmantojot Drošās failu pārsūtīšanas protokolu (SFTP)

Cilnē **Manas bagātināšanas** varat redzēt jūsu konfigurētos bagātinājumus un rediģēt to rekvizītus.

## <a name="manage-existing-enrichments"></a>Esošo papildinājumu pārvaldība

Lai redzētu visus konfigurētos bagātinājumus, dodieties uz **Mani papildinājumi**. Katrs bagātinājums tiek attēlots kā rinda, kurā ir iekļauta papildu informācija par bagātinājumu.

Atlasiet bagātinājumu, lai skatītu pieejamās opcijas. Vai arī, lai skatītu opcijas, varat atlasīt daudzpunkti (...) saraksta elementā.

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Opcijas bagātinājumu pārvaldībai papildinājumu sarakstā":::

- **Skatiet** detalizēto informāciju par bagātināšanu ar bagātināto klientu profilu skaitu.
- **Rediģējiet** bagātināšanas konfigurāciju.
- **Palaidiet** bagātinājumu, lai atjauninātu klientu profilus ar jaunākajiem datiem.
- **Deaktivizējiet** esošu bagātinājumu, lai neļautu tam automātiski atsvaidzināties ar katru plānoto atsvaidzināšanu. Dati no pēdējās sekmīgās atsvaidzināšanas joprojām būs pieejami. **Aktivizējiet** neaktīvu bagātināšanu, lai restartētu automātisko atsvaidzināšanu ar katru plānoto atsvaidzināšanu.
- **Dzēst** bagātināšanu.

Vairākus bagātinājumus var vienlaicīgi palaist vai deaktivizēt, tos atlasot sarakstā. Skatīšanas un rediģēšanas opcijas nav pieejamas kā lielapjoma darbība un vienlaicīgi darbojas tikai vienai veiktajai bagātināšanai.
