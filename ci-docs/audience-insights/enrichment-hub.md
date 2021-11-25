---
title: Vienoto klientu profilu bagātināšana
description: Izmantojiet iespējas, lai bagātinātu klientu datus.
ms.date: 11/05/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: de27da92118b83dafa0742b6a1e10ee315750c61
ms.sourcegitcommit: 6efcba688d1db1a5d6343c229f292a26c48fc007
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 11/05/2021
ms.locfileid: "7770133"
---
# <a name="enrichment-for-customer-profiles-preview"></a>Klientu profilu bagātināšana (priekšskatījums)

Izmantojiet avotu datus, piemēram, no Microsoft un citiem partneriem, lai bagātinātu klientu datus.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Bagātināšanas centra lapa.":::

Informāciju par auditorijas ieskatiem skatiet sadaļā **Dati** > **Bagātināšana**, lai strādātu ar bagātināšanas iespējām.  

Lai izveidotu vai rediģētu bagātināšanos, jums ir nepieciešamas Līdzstrādnieka vai Administratora atļaujas. Lai iegūtu papildinformāciju, skatiet [Atļaujas](permissions.md).

Cilnē **Atklāt** ir pieejamas visas atbalstītās bagātināšanas opcijas.

# <a name="individual-consumers-b-to-c"></a>[Atsevišķi patērētāji (B2C)](#tab/b2c)

- Microsoft nodrošinātie [Zīmoli](enrichment-microsoft.md)
- Microsoft nodrošinātās [Intereses](enrichment-microsoft.md)
- [Paplašinātās adreses](enrichment-enhanced-addresses.md), ko nodrošina Microsoft 
- Experian nodrošinātie [demogrāfijas dati](enrichment-experian.md)
- [Pielāgoti dati](enrichment-SFTP-custom-import.md), izmantojot Drošās failu pārsūtīšanas protokolu (SFTP) 
- [Azure Maps](enrichment-azure-maps.md), ko nodrošina Microsoft

# <a name="business-accounts-b-to-b"></a>[Uzņēmumu konti (B2B)](#tab/b2b)

- Leadspace nodrošinātie [uzņēmuma dati](enrichment-leadspace.md)
- [Paplašinātās adreses](enrichment-enhanced-addresses.md), ko nodrošina Microsoft 
- [Microsoft nodrošinātie uzlabotie uzņēmuma dati](enrichment-enhanced-company-data.md)
- [Atrašanās vietas dati](enrichment-here.md) HERE Technologies nodrošinātie atrašanās vietas dati 
- [Pielāgoti dati](enrichment-SFTP-custom-import.md), izmantojot Drošās failu pārsūtīšanas protokolu (SFTP) 
- [Azure Maps](enrichment-azure-maps.md), ko nodrošina Microsoft

---

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

Trešo pušu bagātinātos datus konfigurē, izmantojot [savienojumus](connections.md), kurus administrators iestata ar akreditāciju un kuru pārnesei tiek sniegta piekrišana. Šos savienojumus bagātinājumu konfigurēšanai var izmantot administratori un līdzstrādnieki.  

## <a name="multiple-enrichments-of-the-same-type"></a>Vairāki viena veida bagātinātie dati

Bagātināmo entitīju norāda bagātināšanas konfigurēšanas laikā, kas ļauj bagātināt vienīgi jūsu profilu apakškopu. Piemēram, bagātināt datus tikai noteiktam segmentam. Jūs varat konfigurēt vairākus viena veida bagātinātos datus un atkārtoti izmantot to pašu savienojumu. Daži bagātinātie dati tiks ierobežoti līdz atļautajam bagātināmo datu izveides skaitam. Ierobežojumus un pašreizējo lietojumu var aplūkot lapā **Bagātināšana**.

## <a name="see-the-progress-of-the-enrichment-process"></a>Bagātinātā procesa norises gaita

Atsvaidzinot vai pēc atsvaidzināšanas pabeigšanas, varat atrast detalizētu informāciju par bagātināšanas apstrādi, tostarp tā statusu un iespējamām problēmām. Izpratne par to, kuri procesi ir saistīti ar bagātinātā procesa atsvaidzināšanu un to, cik ilgs laiks bija nepieciešams šo procesu palaišanai. Bagātināšanas statuss tiek atbalstīts Experian, Leadspace, HERE Technologies, SFTP Import un Azure Maps.

Lai redzētu bagātināšanas statusu

1. Dodieties uz **Dati** > **Bagātināšana**. 
1. Cilnē **Mani bagātinājumi** atlasiet bagātinājuma statusu, lai atvērtu sānu rūti. 
1. Detalizētas informācijas rūtī **Norise** izvērsiet sadaļu **Bagātinātjumi**. 
1. Sadaļā Bagātināšana, kuras norisi vēlaties redzēt, atlasiet **Skatīt informāciju**. 
1. **Uzdevumu detalizētās informācijas** rūtī atlasiet **Rādīt detalizētu informāciju**, lai skatītu procesus, kas saistīti ar bagātināšanas atjaunināšanu un to statusu. 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
