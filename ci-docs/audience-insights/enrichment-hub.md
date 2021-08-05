---
title: Vienoto klientu profilu bagātināšana
description: Izmantojiet iespējas, lai bagātinātu klientu datus.
ms.date: 07/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: d12c0a9dd65d31f9ae8a9cafeafab2767d57893e
ms.sourcegitcommit: dab2cbf818fafc9436e685376df94c5e44e4b144
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 07/13/2021
ms.locfileid: "6555270"
---
# <a name="enrichment-for-customer-profiles-preview"></a>Klientu profilu bagātināšana (priekšskatījums)

Izmantojiet avotu datus, piemēram, no Microsoft un citiem partneriem, lai bagātinātu klientu datus.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Bagātināšanas centra lapa.":::

Informāciju par auditorijas ieskatiem skatiet sadaļā **Dati** > **Bagātināšana**, lai strādātu ar bagātināšanas iespējām.  

Lai izveidotu vai rediģētu bagātināšanos, jums ir nepieciešamas Līdzstrādnieka vai Administratora atļaujas. Lai iegūtu papildinformāciju, skatiet [Atļaujas](permissions.md).

Cilnē **Atklāt** atradīsiet šādus bagātinātājus:

- Microsoft nodrošinātie [Zīmoli](enrichment-microsoft.md)
- Microsoft nodrošinātās [Intereses](enrichment-microsoft.md)
- [Paplašinātās adreses](enrichment-enhanced-addresses.md), ko nodrošina Microsoft
- Leadspace nodrošinātie [uzņēmuma dati](enrichment-leadspace.md)
- [Demogrāfiskie dati](enrichment-experian.md), ko nodrošina Experian
- [Atrašanās vietas dati](enrichment-here.md) HERE Technologies nodrošinātie atrašanās vietas dati
- [Pielāgoti dati](enrichment-SFTP-custom-import.md), izmantojot Drošās failu pārsūtīšanas protokolu (SFTP)

Cilnē **Manas bagātināšanas** varat redzēt jūsu konfigurētos bagātinājumus un rediģēt to rekvizītus.

## <a name="manage-existing-enrichments"></a>Esošo papildinājumu pārvaldība

Lai skatītu visus konfigurētos bagātinātos datus, dodieties uz **Manas bagātināšanas** cilni. Katrs bagātinājums tiek attēlots kā rinda, kurā ir iekļauta papildu informācija par bagātinājumu.

Atlasiet bagātināšanu, lai redzētu pieejamās opcijas. Lai skatītu opcijas, varat arī saraksta elementā atlasīt daudzpunkti (...). Ja konfigurējāt vairākus bagātinātus uzlabojumus, varat izmantot meklēšanas lodziņu, lai to ātri atrastu.

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Opcijas bagātinājumu pārvaldībai papildinājumu sarakstā.":::

- **Skatiet** detalizēto informāciju par bagātināšanu ar bagātināto klientu profilu skaitu.
- **Rediģējiet** bagātināšanas konfigurāciju.
- **Palaidiet** bagātinājumu, lai atjauninātu klientu profilus ar jaunākajiem datiem.
- **Deaktivizējiet** esošu bagātinājumu, lai neļautu tam automātiski atsvaidzināties ar katru plānoto atsvaidzināšanu. Dati no pēdējās sekmīgās atsvaidzināšanas joprojām būs pieejami. **Aktivizējiet** neaktīvu bagātināšanu, lai restartētu automātisko atsvaidzināšanu ar katru plānoto atsvaidzināšanu.
- **Dzēst** bagātināšanu.

Vienlaicīgi izpildiet vai deaktivizējiet vairākus bagātinātos bagātinātos laukus, atlasot tos sarakstā. Skatīšanas un rediģēšanas opcijas nav pieejamas kā lielapjoma darbība. Viņi vienā reizē strādā tikai uz vienu bagātināšanu.

## <a name="enrichments-and-connections"></a>Bagātināšana un savienojumi

Trešo pušu bagātinātos datus konfigurē, izmantojot [savienojumus](connections.md), kurus administrators iestata ar akreditāciju un kuru pārnesei tiek sniegta piekrišana. Administratori un līdzstrādnieki var izmantot savienojumus, lai konfigurētu bagātinātos datus.  

## <a name="multiple-enrichments-of-the-same-type"></a>Vairāki viena veida bagātinātie dati

Bagātināmo entitīju norāda bagātināšanas konfigurēšanas laikā, kas ļauj bagātināt vienīgi jūsu profilu apakškopu. Piemēram, bagātināt datus tikai noteiktam segmentam. Jūs varat konfigurēt vairākus viena veida bagātinātos datus un atkārtoti izmantot to pašu savienojumu. Daži bagātinātie dati tiks ierobežoti līdz atļautajam bagātināmo datu izveides skaitam. Ierobežojumus un pašreizējo lietojumu var aplūkot lapā **Bagātināšana**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
