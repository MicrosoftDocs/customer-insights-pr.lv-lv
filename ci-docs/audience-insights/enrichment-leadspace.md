---
title: Uzņēmumu profilu bagātināšana ar trešās puses bagātināšanas programmu Leadspace
description: Vispārēja informācija par Leadspace trešās puses bagātināšanu.
ms.date: 11/24/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 1b5c6e46e8e424df83e855d81fc4dd7ecb394e3c
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668732"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a>Uzņēmuma profilu bagātināšana ar Leadspace (priekšskatījums)

Leadspace ir datu zinātnes uzņēmums, kas nodrošina B2B klientu datu platformu. Tā nodrošina klientiem vienotus klientu profilus, lai uzņēmumi bagātinātu datus. Bagātinājumi ietver papildu atribūtus, kā uzņēmuma lielums, atrašanās vieta, nozare utt.

## <a name="prerequisites"></a>Priekšnosacījumi

Lai konfigurētu Leadspace, ir jāizpilda tālāk aprakstītie priekšnosacījumi:

- Jums ir aktīva Leadspace licence un "mūžīgā atslēga" (dēvēta par **Leadspace marķieri**). Lai iegūtu detalizētu informāciju par viņu produktu, sazinieties tieši ar [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/).
- ir nepieciešamas [Administratora](permissions.md#administrator) atļaujas.
- Jums ir [vienoti klientu profili](customer-profiles.md) uzņēmumiem.

## <a name="configuration"></a>Konfigurācija

1. Sadaļā Auditorijas ieskati skatiet **Dati** > **Darbības**.

1. Leadspace rūtī atlasiet **Bagātināt manus datus**.

   :::image type="content" source="media/leadspace-tile.png" alt-text="Leadspace mozaīkas ekrānuzņēmums.":::

1. Atlasiet vienumu **Sākt darbu** un pēc tam ievadiet aktīvu **Leadspace marķieri** (mūžīgo atslēgu). Pārskatiet un sniedziet savu piekrišanu **Datu konfidencialitātei un atbilstībai**, atzīmējot izvēles rūtiņu **Piekrītu**. Apstipriniet abas ievades, atlasot **Izveidot savienojumu ar Leadspace**.

1. Atlasiet **Kartēt datus** un definējiet, kuri no vienoto profilu laukiem ir jāizmanto, lai meklētu atbilstošus uzņēmuma datus no Leadspace. Lauks **Uzņēmuma nosaukums** ir obligāts. Lielākai atbilstībai varat pievienot līdz diviem citiem laukiem - **Uzņēmuma tīmekļa vietne** un **Uzņēmuma atrašanās vieta**.

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Leadspace lauku kartējuma rūts.":::
   
1. Atlasiet **Piemērot**, lai pabeigtu lauka kartēšanu.

1. Atlasiet **Palaist**, lai bagātinātu uzņēmuma profilus. Bagātināšanas ilgums ir atkarīgs no vienoto klientu profilu skaita.

## <a name="enrichment-results"></a>Bagātināšanas rezultāti

Pēc bagātināšanas atsvaidzināšanas varat apskatīt nesen papildinātā uzņēmuma datus [Mani papildinājumi](enrichment-hub.md). Varat atrast pēdējās atjaunināšanas laiku un bagātināto profilu skaitu.

Jūs varat piekļūt detalizētam katra bagātināta profila skatam, atlasot opciju **Skatīt bagātinātos datus**.

Papildinformāciju skatiet tēmā [Leadspace API](https://support.leadspace.com/hc/en-us/sections/201997649-API).

## <a name="next-steps"></a>Nākamās darbības

Būvējiet virs saviem bagātinātajiem klientu datiem. Veidojiet [segmentus](segments.md), [mērus](measures.md)un pat [eksportējiet datus](export-destinations.md), lai klientiem sniegtu personalizētas iespējas.

## <a name="data-privacy-and-compliance"></a>Datu konfidencialitāte un atbilstība

Ja iespējojat Dynamics 365 Customer Insights datu pārsūtīšanu uz Leadspace, jūs atļaujat datu pārsūtīšanu ārpus atbilstības robežām Dynamics 365 Customer Insights, ieskaitot iespējami sensitīvus datus, piemēram, personas datus. Microsoft šos datus pārsūtīs pēc jūsu norādēm, bet jūs esat atbildīgs par to, lai nodrošinātu Leadspace atbilstību konfidencialitātes vai drošības saistībām, kas jums varētu rasties. Papildinformāciju skatiet rakstā [Microsoft Privātuma paziņojums](https://go.microsoft.com/fwlink/?linkid=396732).
Jūsu Dynamics 365 Customer Insights administrators var noņemt šo bagātināšanas funkciju jebkurā laikā, lai pārtrauktu izmantot šo funkcionalitāti.