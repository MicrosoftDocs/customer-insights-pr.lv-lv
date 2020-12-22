---
title: Bagātināšana ar trešās puses bagātināšanas programmu HERE Technologies
description: Vispārēja informācija par HERE Technologies trešās puses bagātināšanu.
ms.date: 10/27/2020
ms.reviewer: jodahl
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 7082fcfec099c3c9436b233c193be23625f6691a
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668687"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a>Klientu profilu bagātināšana ar HERE Technologies (priekšskatījums)

HERE Technologies ir atrašanās vietas platformas uzņēmums, kas nodrošina atrašanās vietas datus un pakalpojumus. Izmantojot HERE Technologies datu bagātināšanas pakalpojumus, varat izveidot precīzāku atrašanās vietu, lai izprastu klientus, izmantojot adrešu normalizēšanu, platuma un garuma izgūšanu utt.

## <a name="prerequisites"></a>Priekšnosacījumi

Lai konfigurētu HERE Technologies, ir jāatbilst šādiem priekšnosacījumiem:

- Jums ir jābūt aktīvam HERE Technologies abonementam. Lai saņemtu abonementu, varat [pierakstīties šeit](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) vai [sazinieties ar HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) tieši. [Papildinformācija par HERE Technologies atrašanās vietas bagātināšanu.](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- Jums ir HERE Technologies API atslēga.

- ir nepieciešamas [Administratora](permissions.md#administrator) atļaujas.

## <a name="configuration"></a>Konfigurācija

1. Dodieties uz **Dati** > **Bagātināšana**.

1. Atlasiet HERE Technologies elementu **Bagātināt manus datus**.

   > [!div class="mx-imgBorder"]
   > ![HERE Technologies elements](media/HERE-tile.png "HERE Technologies elements")

1. Ievadiet aktīvu **HERE Technologies API atslēgu**. Pārskatiet un sniedziet savu piekrišanu **Datu konfidencialitātei un atbilstībai**, atzīmējot izvēles rūtiņu **Piekrītu**. 

1. Apstipriniet abas ievades, atlasot **Izveidot savienojumu ar HERE**.

1. Atlasiet vienumu **pievienot datus** un izvēlieties, vai jākartē lauki primārajai un/vai sekundārajai adresei. Varat norādīt lauka kartējumu abām adresēm (piemēram, mājas un darba adrese), kā arī bagātināt abu adrešu profilus atsevišķi. Atlasiet **Tālāk**.

1. Definējiet, kurus vienoto profilu laukus vajadzētu izmantot, lai meklētu atbilstošos HERE Technologies atrašanās vietas datus. Atlasītajai primārajai un/vai sekundārajai adresei ir nepieciešami lauki **1.adrese** un **Pasta indekss**. Lai iegūtu augstāku atbilstību precizitāti, var pievienot vairākus laukus.

   > [!div class="mx-imgBorder"]
   > ![HERE Technologies bagātināšanas konfigurācijas lapa](media/enrichment-HERE-configuration.png "HERE Technologies bagātināšanas konfigurācijas lapa")

1. Atlasiet **Piemērot**, lai pabeigtu lauka kartēšanu.

## <a name="enrichment-results"></a>Bagātināšanas rezultāti

Lai sāktu bagātināšanas procesu, komandjoslā atlasiet **Palaist**. Varat arī ļaut sistēmai palaist bagātināšanu automātiski kā daļu no [plānotās atsvaidzināšanas](system.md#schedule-tab). Apstrādes laiks ir atkarīgs no jūsu klientu datu izmēra un API atbildes laikiem no HERE Technologies.

Pēc bagātināšanas procesa noslēgšanas varat pārskatīt tikko bagātinātos klientu profilu datus, dodoties uz sadaļu **Mana bagātināšana**. Turklāt jūs redzēsit pēdējā atjauninājuma laiku un bagātināto profilu skaitu.

Jūs varat piekļūt detalizētam katra bagātināta profila skatam, atlasot opciju **Skatīt bagātinātos datus**.

## <a name="next-steps"></a>Nākamās darbības

Būvējiet virs saviem bagātinātajiem klientu datiem. Veidojiet [segmentus](segments.md), [mērus](measures.md)un pat [eksportējiet datus](export-destinations.md), lai klientiem sniegtu personalizētas iespējas.

## <a name="data-privacy-and-compliance"></a>Datu konfidencialitāte un atbilstība

Ja iespējojat Dynamics 365 Customer Insights datu pārsūtīšanu uz HERE Technologies, jūs atļaujat datu pārsūtīšanu ārpus atbilstības robežām Dynamics 365 Customer Insights, ieskaitot iespējami sensitīvus datus, piemēram, personas datus. Microsoft šos datus pārsūtīs pēc jūsu norādēm, bet jūs esat atbildīgs par to, lai nodrošinātu HERE Technologies atbilstību konfidencialitātes vai drošības saistībām, kas jums varētu rasties. Papildinformāciju skatiet rakstā [Microsoft Privātuma paziņojums](https://go.microsoft.com/fwlink/?linkid=396732).
Jūsu Dynamics 365 Customer Insights administrators var noņemt šo bagātināšanas funkciju jebkurā laikā, lai pārtrauktu izmantot šo funkcionalitāti.
