---
title: Uzņēmuma profilu bagātināšana ar Leadspace (priekšskatījums)
description: Vispārēja informācija par Leadspace trešās puses bagātināšanu.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: f45fabc036775e11fc439f69513678d0607729d0
ms.sourcegitcommit: b1d06fe26934f12f0c5ed13e8ef1d37e52e67cc7
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 08/08/2022
ms.locfileid: "9237959"
---
# <a name="enrich-company-profiles-with-leadspace-preview"></a>Uzņēmuma profilu bagātināšana ar Leadspace (priekšskatījums)

Leadspace ir datu uzņēmums, kas nodrošina datu platformu B2B klientam. Tas ļauj vidēm ar vienotiem klientu profiliem, kuru pamatā ir uzņēmumi, bagātināt viņu datus. Bagātināt *klientu profilus* ar atribūtiem, piemēram, uzņēmuma lielumu, atrašanās vietu vai nozari. Bagātināt *kontaktpersonu profilus* ar atribūtiem, piemēram, amatu, personu vai e-pasta pārbaudi.

## <a name="prerequisites"></a>Priekšnoteikumi

- Aktīva Leadspace licence.
- [Vienoti klientu profili,](customer-profiles.md) kuru pamatā ir konti.
- Leadspace [savienojumu](connections.md)[konfigurē](#configure-the-connection-for-leadspace) administrators. Tieši sazinieties ar [Leadspace](https://www.leadspace.com/leadspace-microsoft-dynamics-365/), lai iegūtu informāciju par produktu.

## <a name="configure-the-connection-for-leadspace"></a>Leadspace savienojuma konfigurēšana

Jums ir jābūt customer insights [administratoram](permissions.md#admin), un jums ir jābūt "pastāvīgajai atslēgai" (sauktai par **Leadspace marķieri**).

1. Atlasiet **Pievienot savienojumu**, konfigurējot bagātināšanu, vai dodieties uz **Administratoru** > **savienojumi** un leadspace elementā atlasiet **Iestatīt**.

   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Leadspace savienojuma konfigurēšanas lapa.":::

1. Ievadiet savienojuma nosaukumu un derīgu Leadspace marķieri.

1. Pārskatiet datu privātumu [un atbilstību](connections.md#data-privacy-and-compliance) un atlasiet **Es piekrītu**.

1. Atlasiet **Verificēt**, lai validētu konfigurāciju, un pēc tam atlasiet **Saglabāt**.

## <a name="configure-the-enrichment"></a>Bagātināto datu konfigurēšana

1. Dodieties uz **Dati** > **Bagātināšana** un atlasiet cilni **Atklāt**.

1. Atlasiet **Bagātināt manus datus** ar **uzņēmuma datiem** no elementa Leadspace.

   :::image type="content" source="media/leadspace-tile.png" alt-text="Leadspace mozaīkas ekrānuzņēmums.":::

1. Pārskatiet pārskatu un pēc tam atlasiet **Tālāk**.

1. Atlasiet savienojumu. Ja nav pieejamu savienojumu, sazinieties ar administratoru.

1. Atlasiet **Tālāk**.

1. **Atlasiet klienta datu kopu** un izvēlieties profilu vai segmentu, kuru vēlaties bagātināt ar uzņēmuma datiem no Leadspace. Klienta *entītija* bagātina visus jūsu klientu profilus, savukārt segments bagātina tikai šajā segmentā ietvertos klientu profilus.

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="Ekrānuzņēmums, izvēloties klientu datu kopu.":::

1. Definējiet, kāda veida laukus no saviem vienotajiem profiliem izmantot saskaņošanai: primāro un/vai sekundāro adresi. Jūs varat norādīt lauka kartējumu abām adresēm un atsevišķi bagātināt abu adrešu profilus. Piemēram, mājas adresei un uzņēmuma adresei. Atlasiet **Tālāk**.

1. Kartējiet laukus uz uzņēmuma datiem no Leadspace. Lauks **Uzņēmuma nosaukums** ir obligāts. Lielākai atbilstībai varat pievienot līdz diviem citiem laukiem - **Uzņēmuma tīmekļa vietne** un **Uzņēmuma atrašanās vieta**.

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Leadspace lauku kartējuma rūts.":::

1. Lai pabeigtu lauka kartēšanu, atlasiet **Tālāk**.

1. Atzīmējiet izvēles rūtiņu, ja jums ir *Kontaktpersonu profili*, ko vēlaties bagātināt. Customer Insights automātiski kartēs nepieciešamos laukus.

   :::image type="content" source="media/enrichment-leadspace-contacts.png" alt-text="Leadspace vietas kontaktpersonu ierakstu bagātināšana.":::

1. Atlasiet **Tālāk**.

1. **Norādiet bagātināšanas nosaukumu** un izvades entītijas **nosaukumu**.

1. Pēc izvēļu pārskatīšanas atlasiet **Saglabāt bagātināšanu**.

1. Atlasiet **Palaist**, lai sāktu bagātināšanas procesu, vai aizveriet, lai **atgrieztos bagātināšanas** lapā.

## <a name="view-enrichment-results"></a>Bagātināšanas rezultātu skatīšana

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

Papildinformāciju skatiet tēmā [Leadspace API](https://support.leadspace.com/hc/en-us/sections/201997649-API).

## <a name="next-steps"></a>Nākamās darbības

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
