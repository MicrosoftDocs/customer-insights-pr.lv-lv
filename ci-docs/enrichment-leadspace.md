---
title: Uzņēmumu profilu bagātināšana ar trešās puses bagātināšanas programmu Leadspace
description: Vispārēja informācija par Leadspace trešās puses bagātināšanu.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: ca53f15bd7c71b3b4acb396c4daf52d7c7aff9eb
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 06/13/2022
ms.locfileid: "8954188"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a>Uzņēmuma profilu bagātināšana ar Leadspace (priekšskatījums)

Leadspace ir datu uzņēmums, kas nodrošina datu platformu B2B klientam. Tas ļauj vidēm ar vienotiem klientu profiliem, kuru pamatā ir uzņēmumi, bagātināt viņu datus. Bagātināt *klientu profilus* ar atribūtiem, piemēram, uzņēmuma lielumu, atrašanās vietu vai nozari. Bagātināt *kontaktpersonu profilus* ar atribūtiem, piemēram, amatu, personu vai e-pasta pārbaudi.

## <a name="prerequisites"></a>Priekšnoteikumi

- Aktīva Leadspace licence.
- [Vienoti debitoru profili,](customer-profiles.md) kuru pamatā ir konti.
- Leadspace [savienojumu](connections.md)[konfigurē](#configure-the-connection-for-leadspace) administrators. Tieši sazinieties ar [Leadspace](https://www.leadspace.com/leadspace-microsoft-dynamics-365/), lai iegūtu informāciju par produktu.

## <a name="configure-the-connection-for-leadspace"></a>Leadspace savienojuma konfigurēšana

Jums jābūt customer insights administratoram [un](permissions.md#admin) jābūt "beztermiņa atslēgai" (sauktai par **Leadspace token**).

1. Atlasiet **Pievienot savienojumu**, konfigurējot bagātināšanu, vai dodieties uz **Administrēšanas** > **savienojumiem** un atlasiet **Iestatīt** nosaukumā Leadspace.

   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Leadspace savienojuma konfigurēšanas lapa.":::

1. Ievadiet savienojuma nosaukumu un derīgu ievadtelpas marķieri.

1. Pārskatiet un sniedziet savu piekrišanu [Datu konfidencialitātei un atbilstībai](#data-privacy-and-compliance), atlasot **Es piekrītu**.

1. Atlasiet **Pārbaudīt**, lai validētu konfigurāciju, un pēc tam atlasiet **Saglabāt**.

### <a name="data-privacy-and-compliance"></a>Datu konfidencialitāte un atbilstība

Ja iespējojat Dynamics 365 Customer Insights datu pārsūtīšanu uz Leadspace, jūs atļaujat datu pārsūtīšanu ārpus atbilstības robežām Dynamics 365 Customer Insights, ieskaitot iespējami sensitīvus datus, piemēram, personas datus. Microsoft šos datus pārsūtīs pēc jūsu norādēm, bet jūs esat atbildīgs par to, lai nodrošinātu Leadspace atbilstību konfidencialitātes vai drošības saistībām, kas jums varētu rasties. Papildinformāciju skatiet rakstā [Microsoft Privātuma paziņojums](https://go.microsoft.com/fwlink/?linkid=396732).
Jūsu Dynamics 365 Customer Insights administrators var noņemt šo bagātināšanas funkciju jebkurā laikā, lai pārtrauktu šīs funkcijas izmantošanu.

## <a name="configure-the-enrichment"></a>Bagātināto datu konfigurēšana

1. Dodieties uz **Dati** > **Bagātināšana** un atlasiet cilni **Atklāt**.

1. Atlasiet **Bagātināt manus datus** uzņēmuma datos **no** Elementa LeadSpace.

   :::image type="content" source="media/leadspace-tile.png" alt-text="Leadspace mozaīkas ekrānuzņēmums.":::

1. Pārskatiet pārskatu un pēc tam atlasiet **Tālāk**.

1. Atlasiet savienojumu. Ja tāds nav pieejams, sazinieties ar administratoru.

1. Atlasiet **Tālāk**.

1. Atlasiet klienta datu kopu **un** izvēlieties profilu vai segmentu, kuru vēlaties bagātināt ar uzņēmuma datiem no Leadspace. Klientu *uzņēmums* bagātina visus jūsu klientu profilus, savukārt segments bagātina tikai šajā segmentā esošos klientu profilus.

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="Ekrānuzņēmums, izvēloties klientu datu kopu.":::

1. Definējiet, kāda tipa laukus no vienotajiem profiliem izmantot saskaņošanai: primārā un/vai sekundārā adrese. Jūs varat norādīt lauka kartējumu abām adresēm un atsevišķi bagātināt abu adrešu profilus. Piemēram, mājas adresei un uzņēmuma adresei. Atlasiet **Tālāk**.

1. Kartējiet savus laukus uz uzņēmuma datiem no LeadSpace. Lauks **Uzņēmuma nosaukums** ir obligāts. Lielākai atbilstībai varat pievienot līdz diviem citiem laukiem - **Uzņēmuma tīmekļa vietne** un **Uzņēmuma atrašanās vieta**.

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Leadspace lauku kartējuma rūts.":::

1. Lai pabeigtu lauka kartēšanu, atlasiet **Tālāk**.

1. Atzīmējiet izvēles rūtiņu, ja jums ir *Kontaktpersonu profili*, ko vēlaties bagātināt. Customer Insights automātiski kartēs nepieciešamos laukus.

   :::image type="content" source="media/enrichment-leadspace-contacts.png" alt-text="Leadspace vietas kontaktpersonu ierakstu bagātināšana.":::

1. Atlasiet **Tālāk**.

1. **Norādiet bagātināšanas nosaukumu** un entītijas **Izvade nosaukumu**.

1. Pēc izvēļu pārskatīšanas atlasiet **Saglabāt bagātināšanu**.

1. Atlasiet **Palaist**, lai sāktu bagātināšanas procesu, vai tuvu, lai **atgrieztos lapā Bagātinājumi**.

## <a name="enrichment-results"></a>Bagātināšanas rezultāti

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

Papildinformāciju skatiet tēmā [Leadspace API](https://support.leadspace.com/hc/en-us/sections/201997649-API).

## <a name="next-steps"></a>Nākamās darbības

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
