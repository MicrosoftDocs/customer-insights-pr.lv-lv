---
title: Bagātiniet klientu profilus, izmantojot HERE Technologies (priekšskatījums)
description: Vispārēja informācija par HERE Technologies trešās puses bagātināšanu.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: d88085b6be156dd1c895e9e5b38cc9d77acbdb95
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 06/29/2022
ms.locfileid: "9052060"
---
# <a name="enrich-customer-profiles-with-here-technologies-preview"></a>Bagātiniet klientu profilus, izmantojot HERE Technologies (priekšskatījums)

HERE Technologies ir atrašanās vietas platformas uzņēmums, kas nodrošina atrašanās vietas datus un pakalpojumus. HERE Technologies datu bagātināšanas pakalpojumi uzlabo atrašanās vietas informācijas precizitāti par jūsu klientiem. Tas nodrošina adrešu normalizāciju, platuma un garuma ieguvi un daudz ko citu.

## <a name="prerequisites"></a>Priekšnoteikumi

- Aktīvs HERE Technologies abonements. Lai saņemtu abonementu, [reģistrējieties šeit](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) vai [sazinieties tieši ar HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you). [Papildinformācija par HERE Technologies atrašanās vietas bagātināšanu.](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- HERE [savienojumu](connections.md)[konfigurē](#configure-the-connection-for-here-technologies) administrators.

## <a name="configure-the-connection-for-here-technologies"></a>HERE Technologies savienojuma konfigurēšana

Jums ir jābūt Customer Insights [administratoram](permissions.md#admin), un jums ir jābūt aktīvai HERE Technologies API atslēgai.

1. Atlasiet **Pievienot savienojumu**, konfigurējot bagātināšanu, vai dodieties uz **Administratoru** > **savienojumi** un **atlasiet Iestatīt** elementā HERE Technologies.

1. Ievadiet savienojuma nosaukumu un derīgu HERE Technologies API atslēgu.

1. Pārskatiet un sniedziet savu piekrišanu [Datu konfidencialitātei un atbilstībai](#data-privacy-and-compliance), atlasot **Es piekrītu**.

1. Atlasiet **Verificēt**, lai validētu konfigurāciju, un pēc tam atlasiet **Saglabāt**.

   :::image type="content" source="media/enrichment-HERE-connection.png" alt-text="HERE Technologies savienojuma konfigurēšanas lapa.":::

### <a name="data-privacy-and-compliance"></a>Datu konfidencialitāte un atbilstība

Ja iespējojat Dynamics 365 Customer Insights datu pārsūtīšanu uz HERE Technologies, jūs atļaujat datu pārsūtīšanu ārpus atbilstības robežām Dynamics 365 Customer Insights, ieskaitot iespējami sensitīvus datus, piemēram, personas datus. Microsoft šos datus pārsūtīs pēc jūsu norādēm, bet jūs esat atbildīgs par to, lai HERE Technologies atbilstu visām jūsu konfidencialitātes vai drošības saistībām. Papildinformāciju skatiet rakstā [Microsoft Privātuma paziņojums](https://go.microsoft.com/fwlink/?linkid=396732).
Jūsu Dynamics 365 Customer Insights administrators var noņemt šo bagātināšanas funkciju jebkurā laikā, lai pārtrauktu šīs funkcijas izmantošanu.

## <a name="configure-the-enrichment"></a>Bagātināto datu konfigurēšana

1. Dodieties uz **Dati** > **Bagātināšana** un atlasiet cilni **Atklāt**.

1. Atlasiet **Bagātināt manus datus** par atrašanās **vietu** no HERE Technologies.

   :::image type="content" source="media/HERE-tile.png" alt-text="HERE Technologies elements.":::

1. Pārskatiet pārskatu un pēc tam atlasiet **Tālāk**.

1. Atlasiet savienojumu. Sazinieties ar administratoru, ja tāds nav pieejams.

1. Atlasiet **Tālāk**.

1. **Atlasiet klienta datu kopu** un izvēlieties profilu vai segmentu, kuru vēlaties bagātināt ar HERE Technologies datiem. Klienta *entītija* bagātina visus jūsu klientu profilus, savukārt segments bagātina tikai šajā segmentā ietvertos klientu profilus.

1. Definējiet, kāda veida laukus no saviem vienotajiem profiliem izmantot saskaņošanai: primāro un/vai sekundāro adresi. Jūs varat norādīt lauka kartējumu abām adresēm un atsevišķi bagātināt abu adrešu profilus. Piemēram, mājas adresei un uzņēmuma adresei. Atlasiet **Tālāk**.

1. Kartējiet savus laukus uz datiem no HERE Technologies. Atlasītajai primārajai un/vai sekundārajai adresei ir nepieciešami lauki **Adreses 1. rinda** un **Pasta indekss**. Lai nodrošinātu lielāku atbilstības precizitāti, pievienojiet papildu laukus.

1. Lai pabeigtu lauka kartēšanu, atlasiet **Tālāk**.

1. **Norādiet bagātināšanas nosaukumu** un izvades entītijas **nosaukumu**.

1. Pēc izvēļu pārskatīšanas atlasiet **Saglabāt bagātināšanu**.

1. Atlasiet **Palaist**, lai sāktu bagātināšanas procesu, vai aizveriet, lai **atgrieztos bagātināšanas** lapā.

## <a name="view-enrichment-results"></a>Bagātināšanas rezultātu skatīšana

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

Klientu **skaits, kas bagātināts ar lauku**, nodrošina detalizētu informāciju par katra bagātinātā lauka pārklājumu.

## <a name="next-steps"></a>Nākamās darbības

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
