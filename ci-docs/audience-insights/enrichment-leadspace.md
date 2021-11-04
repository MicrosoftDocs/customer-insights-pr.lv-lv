---
title: Uzņēmumu profilu bagātināšana ar trešās puses bagātināšanas programmu Leadspace
description: Vispārēja informācija par Leadspace trešās puses bagātināšanu.
ms.date: 09/30/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 685b1683b0c90eab04b130552d2cb23a8ab7a235
ms.sourcegitcommit: 31985755c7c973fb1eb540c52fd1451731d2bed2
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 10/22/2021
ms.locfileid: "7673241"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a>Uzņēmuma profilu bagātināšana ar Leadspace (priekšskatījums)

Leadspace ir datu uzņēmums, kas nodrošina datu platformu B2B klientam. Tas ļauj vidēm ar vienotiem klientu profiliem, kuru pamatā ir uzņēmumi, bagātināt viņu datus. Bagātināt *klientu profilus* ar atribūtiem, piemēram, uzņēmuma lielumu, atrašanās vietu vai nozari. Bagātināt *kontaktpersonu profilus* ar atribūtiem, piemēram, amatu, personu vai e-pasta pārbaudi.

## <a name="prerequisites"></a>Priekšnosacījumi

Lai konfigurētu Leadspace, ir jāizpilda tālāk aprakstītie priekšnosacījumi:

- Jums ir aktīva Leadspace licence.
- Jums ir [vienoti klientu profili](customer-profiles.md), kuru pamatā ir uzņēmumi.
- Administrators jau ir konfigurējis Leadspace savienojumu vai jums ir [administratora](permissions.md#administrator) atļaujas un “pastāvīgā atslēga” (jeb **Leadspace marķieris**). Tieši sazinieties ar [Leadspace](https://www.leadspace.com/leadspace-microsoft-dynamics-365/), lai iegūtu informāciju par produktu.

## <a name="configure-the-enrichment"></a>Bagātināto datu konfigurēšana

1. Sadaļā Auditorijas ieskati skatiet **Dati** > **Darbības**.

1. Leadspace rūtī atlasiet **Bagātināt datus** un atlasiet **Sākt darbu**.

   :::image type="content" source="media/leadspace-tile.png" alt-text="Leadspace mozaīkas ekrānuzņēmums.":::

1. Atlasiet [savienojumu](connections.md) nolaižamajā sarakstā. Ja nav pieejamu savienojumu, sazinieties ar administratoru. Ja esat administrators, jūs varat izveidot savienojumu, atlasot **Pievienot savienojumu** un izvēloties **Leadspace**. 

1. Lai apstiprinātu savienojumu, atlasiet **Pieslēgties Leadspace**.

1. Atlasiet **Tālāk** un izvēlieties **Klientu datu kopu**, kuru vēlaties bagātināt ar uzņēmuma datiem no Leadspace. Varat atlasīt entītiju **Klients**, lai bagātinātu visus klientu profilus, vai atlasīt segmenta entītiju, lai bagātinātu tikai šajā segmentā iekļautos klientu profilus.

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="Ekrānuzņēmums, izvēloties klientu datu kopu.":::

1. Atlasiet **Tālāk** un definējiet kuri lauki no jūsu vienotajiem profiliem tiek izmantoti, lai meklētu atbilstošus uzņēmuma datus no Leadspace. Lauks **Uzņēmuma nosaukums** ir obligāts. Lielākai atbilstībai varat pievienot līdz diviem citiem laukiem - **Uzņēmuma tīmekļa vietne** un **Uzņēmuma atrašanās vieta**.

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Leadspace lauku kartējuma rūts.":::

1. Lai pabeigtu lauka kartēšanu, atlasiet **Tālāk**.

1. Atzīmējiet izvēles rūtiņu, ja jums ir *Kontaktpersonu profili*, ko vēlaties bagātināt. Auditorijas ieskati automātiski kartē nepieciešamos laukus.

   :::image type="content" source="media/enrichment-leadspace-contacts.png" alt-text="Leadspace vietas kontaktpersonu ierakstu bagātināšana.":::
 
1. Norādiet bagātināto datu nosaukumu un pēc izvēles pārskatīšanas atlasiet **Saglabāt bagātinātos datus**.


## <a name="configure-the-connection-for-leadspace"></a>Leadspace savienojuma konfigurēšana 

Lai konfigurētu savienojumus, jums ir jābūt administratoram. Konfigurējot bagātinātos datus, atlasiet **Pievienot savienojumu** *vai* dodieties uz **Administrators** > **Savienojumi** un Leadspace rūtī atlasiet **Iestatīt**.

1. Atlasiet **Sākt**. 

1. Lodziņā **Parādāmais nosaukums** ievadiet savienojuma nosaukumu.

1. Iesniedziet derīgu Leadspace marķieri.

1. Pārskatiet un sniedziet savu piekrišanu **Datu konfidencialitātei un atbilstībai**, atlasot **Es piekrītu**.

1. Lai pārbaudītu konfigurāciju, atlasiet **Pārbaudīt**.

1. Pēc pārbaudes pabeigšanas atlasiet **Saglabāt**.
   
   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Leadspace savienojuma konfigurēšanas lapa.":::

## <a name="enrichment-results"></a>Bagātināšanas rezultāti

Pēc bagātināšanas atsvaidzināšanas varat apskatīt nesen papildinātā uzņēmuma datus [Mani papildinājumi](enrichment-hub.md). Varat atrast pēdējās atjaunināšanas laiku un bagātināto profilu skaitu.

Jūs varat piekļūt detalizētam katra bagātināta profila skatam, atlasot opciju **Skatīt bagātinātos datus**.

Papildinformāciju skatiet tēmā [Leadspace API](https://support.leadspace.com/hc/en-us/sections/201997649-API).

## <a name="next-steps"></a>Nākamās darbības


[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Datu konfidencialitāte un atbilstība

Ja iespējojat Dynamics 365 Customer Insights datu pārsūtīšanu uz Leadspace, jūs atļaujat datu pārsūtīšanu ārpus atbilstības robežām Dynamics 365 Customer Insights, ieskaitot iespējami sensitīvus datus, piemēram, personas datus. Microsoft šos datus pārsūtīs pēc jūsu norādēm, bet jūs esat atbildīgs par to, lai nodrošinātu Leadspace atbilstību konfidencialitātes vai drošības saistībām, kas jums varētu rasties. Papildinformāciju skatiet rakstā [Microsoft Privātuma paziņojums](https://go.microsoft.com/fwlink/?linkid=396732).
Jūsu Dynamics 365 Customer Insights administrators var noņemt šo bagātināšanas funkciju jebkurā laikā, lai pārtrauktu šīs funkcijas izmantošanu.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
