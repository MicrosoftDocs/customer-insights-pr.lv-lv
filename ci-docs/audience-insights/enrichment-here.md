---
title: Bagātināšana ar trešās puses bagātināšanas HERE Technologies
description: Vispārēja informācija par HERE Technologies trešās puses bagātināšanu.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 1cbbad9bfe559bcb15b23894fc7475507aae8add
ms.sourcegitcommit: 50d32a4cab01421a5c3689af789e20857ab009c4
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 03/03/2022
ms.locfileid: "8376359"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a>Klientu profilu bagātināšana ar HERE Technologies (priekšskatījums)

HERE Technologies ir atrašanās vietas platformas uzņēmums, kas nodrošina atrašanās vietas datus un pakalpojumus. Izmantojot HERE Technologies datu bagātināšanas pakalpojumus, varat izveidot precīzāku atrašanās vietu, lai izprastu klientus, izmantojot adrešu normalizēšanu, platuma un garuma izgūšanu utt.

## <a name="prerequisites"></a>Priekšnosacījumi

Lai konfigurētu HERE Technologies, ir jāatbilst šādiem priekšnosacījumiem:

- Jums ir jābūt aktīvam HERE Technologies abonementam. Lai saņemtu abonementu, varat [pierakstīties šeit](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) vai [sazinieties ar HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) tieši. [Papildinformācija par HERE Technologies atrašanās vietas bagātināšanu.](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- HERE [savienojums](connections.md) ir pieejams *vai* jums ir [administratora](permissions.md#admin) atļaujas un HERE Technologies API atslēga.

## <a name="configure-the-enrichment"></a>Bagātināto datu konfigurēšana

1. Dodieties uz **Dati** > **Bagātināšana**. 

1. HERE Technologies elementā atlasiet **Bagātināt datus** un atlasiet **Sākt darbu**.

   > [!div class="mx-imgBorder"]
   > ![HERE Technologies elements.](media/HERE-tile.png "HERE Technologies elements")

1. Atlasiet [savienojumu](connections.md) nolaižamajā sarakstā. Ja nav pieejamu savienojumu, sazinieties ar administratoru. Ja esat administrators, jūs varat izveidot savienojumu, atlasot **Pievienot savienojumu**. Nolaižamajā sarakstā izvēlieties **HERE Technologies**. 

1. Atlasiet **Pieslēgties HERE Technologies**, lai apstiprinātu savienojuma atlasi.

1.  Atlasiet **Tālāk** un izvēlieties **Klientu datu kopu**, kuru vēlaties bagātināt ar atrašanās vietas datiem no HERE Technologies. Varat atlasīt entītiju **Klients**, lai bagātinātu visus klientu profilus, vai atlasīt segmenta entītiju, lai bagātinātu tikai šajā segmentā iekļautos klientu profilus.

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="Ekrānuzņēmums, izvēloties klientu datu kopu.":::

1. Izvēlieties, vai jākartē lauki primārajai un/vai sekundārajai adresei. Jūs varat norādīt lauka kartējumu abām adresēm un atsevišķi bagātināt abu adrešu profilus. Piemēram, ja ir mājas un darba adrese. Atlasiet **Tālāk**.

1. Definējiet, kurus vienoto profilu laukus vajadzētu izmantot, lai meklētu atbilstošos HERE Technologies atrašanās vietas datus. Atlasītajai primārajai un/vai sekundārajai adresei ir nepieciešami lauki **Adreses 1. rinda** un **Pasta indekss**. Lai iegūtu augstāku atbilstību precizitāti, var pievienot vairākus laukus.

   > [!div class="mx-imgBorder"]
   > ![HERE Technologies bagātināšanas konfigurācijas lapa.](media/enrichment-HERE-configuration.png "HERE Technologies bagātināšanas konfigurācijas lapa")

1. Lai pabeigtu lauka kartēšanu, atlasiet **Tālāk**.

1. Norādiet bagātināto datu nosaukumu. 

1. Pēc izvēļu pārskatīšanas atlasiet **Saglabāt bagātināšanu**.

## <a name="configure-the-connection-for-here-technologies"></a>HERE Technologies savienojuma konfigurēšana 

Lai konfigurētu savienojumus, jums ir jābūt administratoram. Konfigurējot bagātinātos datus, atlasiet **Pievienot savienojumu** *vai* dodieties uz **Administrators** > **Savienojumi** un HERE Technologies elementā atlasiet **Iestatīt**.

1. Lodziņā **Parādāmais nosaukums** ievadiet savienojuma nosaukumu.

1. Norādiet derīgu HERE Technologies API atslēgu.

1. Pārskatiet un sniedziet savu piekrišanu **Datu konfidencialitātei un atbilstībai**, atlasot **Es piekrītu**.

1. Lai pārbaudītu konfigurāciju, atlasiet **Pārbaudīt**.

1. Pēc pārbaudes pabeigšanas atlasiet **Saglabāt**.

   > [!div class="mx-imgBorder"]
   > ![HERE Technologies savienojuma konfigurēšanas lapa.](media/enrichment-HERE-connection.png "HERE Technologies savienojuma konfigurēšanas lapa")

## <a name="enrichment-results"></a>Bagātināšanas rezultāti

Lai sāktu bagātināšanas procesu, komandjoslā atlasiet **Palaist**. Varat arī ļaut sistēmai palaist bagātināšanu automātiski kā daļu no [plānotās atsvaidzināšanas](system.md#schedule-tab). Apstrādes laiks ir atkarīgs no jūsu klientu datu apjoma un API atbildes laikiem no HERE Technologies.

Pēc bagātināšanas procesa noslēgšanas varat pārskatīt tikko bagātinātos klientu profilu datus, dodoties uz sadaļu **Mana bagātināšana**. Turklāt jūs redzēsit pēdējā atjauninājuma laiku un bagātināto profilu skaitu.

Jūs varat piekļūt detalizētam katra bagātināta profila skatam, atlasot opciju **Skatīt bagātinātos datus**.

## <a name="next-steps"></a>Nākamās darbības

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Datu konfidencialitāte un atbilstība

Ja iespējojat Dynamics 365 Customer Insights datu pārsūtīšanu uz HERE Technologies, jūs atļaujat datu pārsūtīšanu ārpus atbilstības robežām Dynamics 365 Customer Insights, ieskaitot iespējami sensitīvus datus, piemēram, personas datus. Microsoft šos datus pārsūtīs pēc jūsu norādēm, bet jūs esat atbildīgs par to, lai HERE Technologies atbilstu visām jūsu konfidencialitātes vai drošības saistībām. Papildinformāciju skatiet rakstā [Microsoft Privātuma paziņojums](https://go.microsoft.com/fwlink/?linkid=396732).
Jūsu Dynamics 365 Customer Insights administrators var noņemt šo bagātināšanas funkciju jebkurā laikā, lai pārtrauktu šīs funkcijas izmantošanu.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
