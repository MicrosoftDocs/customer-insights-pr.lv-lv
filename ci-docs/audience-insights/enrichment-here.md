---
title: Bagātināšana ar trešās puses bagātināšanas programmu HERE Technologies
description: Vispārēja informācija par HERE Technologies trešās puses bagātināšanu.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 5d1f037377010153045c9255d2d01f98ebf1fdfd
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896060"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a>Klientu profilu bagātināšana ar HERE Technologies (priekšskatījums)

HERE Technologies ir atrašanās vietas platformas uzņēmums, kas nodrošina atrašanās vietas datus un pakalpojumus. Izmantojot HERE Technologies datu bagātināšanas pakalpojumus, varat izveidot precīzāku atrašanās vietu, lai izprastu klientus, izmantojot adrešu normalizēšanu, platuma un garuma izgūšanu utt.

## <a name="prerequisites"></a>Priekšnosacījumi

Lai konfigurētu HERE Technologies, ir jāatbilst šādiem priekšnosacījumiem:

- Jums ir jābūt aktīvam HERE Technologies abonementam. Lai saņemtu abonementu, varat [pierakstīties šeit](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) vai [sazinieties ar HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) tieši. [Papildinformācija par HERE Technologies atrašanās vietas bagātināšanu.](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- Ir pieejams HERE [savienojums](connections.md) *vai* jums ir [administratora](permissions.md#administrator) atļaujas un HERE Technologies API atslēga.

## <a name="configure-the-enrichment"></a>Bagātināto datu konfigurēšana

1. Dodieties uz **Dati** > **Bagātināšana**. 

1. HERE Technologies rūtī atlasiet **Bagātināt datus** un atlasiet **Sākt darbu**.

   > [!div class="mx-imgBorder"]
   > ![HERE Technologies elements](media/HERE-tile.png "HERE Technologies elements")

1. Nolaižamajā izvēlnē atlasiet [savienojums](connections.md). Ja nav pieejamu savienojumu, sazinieties ar administratoru. Ja esat administrators, jūs varat izveidot savienojumu, atlasot **Pievienot savienojumu**. Nolaižamajā izvēlnē atlasiet **HERE Technologies**. 

1. Atlasiet **Pieslēgties HERE Technologies**, lai apstiprinātu savienojuma atlasi.

1.  Atlasiet **Tālāk** un izvēlieties **Klientu datu kopu**, kuru vēlaties bagātināt ar atrašanās vietas datiem no HERE Technologies. Varat atlasīt entītiju **Klients**, lai bagātinātu visus klientu profilus, vai atlasīt segmenta entītiju, lai bagātinātu tikai šajā segmentā iekļautos klientu profilus.

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="Ekrānuzņēmums, izvēloties klientu datu kopu.":::

1. Izvēlieties, vai jākartē lauki primārajai un/vai sekundārajai adresei. Jūs varat norādīt lauka kartējumu abām adresēm un atsevišķi bagātināt abu adrešu profilus. Piemēram, ja ir mājas un darba adrese. Atlasiet **Tālāk**.

1. Definējiet, kurus vienoto profilu laukus vajadzētu izmantot, lai meklētu atbilstošos HERE Technologies atrašanās vietas datus. Atlasītajai primārajai un/vai sekundārajai adresei ir nepieciešami lauki **1.adrese** un **Pasta indekss**. Lai iegūtu augstāku atbilstību precizitāti, var pievienot vairākus laukus.

   > [!div class="mx-imgBorder"]
   > ![HERE Technologies bagātināšanas konfigurācijas lapa](media/enrichment-HERE-configuration.png "HERE Technologies bagātināšanas konfigurācijas lapa")

1. Lai pabeigtu lauka kartēšanu, atlasiet **Tālāk**.

1. Norādiet bagātināto datu nosaukumu. 

1. Pēc izvēļu pārskatīšanas atlasiet **Saglabāt vidi**.

## <a name="configure-the-connection-for-here-technologies"></a>HERE Technologies savienojuma konfigurēšana 

Lai konfigurētu savienojumus, jums ir jābūt administratoram. Konfigurējot bagātinātos datus, atlasiet **Pievienot savienojumu** *vai* dodieties uz **Administrators** > **Savienojumi** un HERE Technologies rūtī atlasiet **Iestatīt**.

1. Lodziņā **Parādāmais nosaukums** ievadiet savienojuma nosaukumu.

1. Norādiet derīgu HERE Technologies API atslēgu.

1. Pārskatiet un sniedziet savu piekrišanu **Datu konfidencialitātei un atbilstībai**, atzīmējot izvēles rūtiņu **Piekrītu**

1. Lai pārbaudītu konfigurāciju, atlasiet **Pārbaudīt**.

1. Pēc pārbaudes pabeigšanas atlasiet **Saglabāt**.

> [!div class="mx-imgBorder"]
   > ![HERE Technologies savienojuma konfigurēšanas lapa](media/enrichment-HERE-connection.png "HERE Technologies savienojuma konfigurēšanas lapa")

## <a name="enrichment-results"></a>Bagātināšanas rezultāti

Lai sāktu bagātināšanas procesu, komandjoslā atlasiet **Palaist**. Varat arī ļaut sistēmai palaist bagātināšanu automātiski kā daļu no [plānotās atsvaidzināšanas](system.md#schedule-tab). Apstrādes laiks ir atkarīgs no jūsu klientu datu izmēra un API atbildes laikiem no HERE Technologies.

Pēc bagātināšanas procesa noslēgšanas varat pārskatīt tikko bagātinātos klientu profilu datus, dodoties uz sadaļu **Mana bagātināšana**. Turklāt jūs redzēsit pēdējā atjauninājuma laiku un bagātināto profilu skaitu.

Jūs varat piekļūt detalizētam katra bagātināta profila skatam, atlasot opciju **Skatīt bagātinātos datus**.

## <a name="next-steps"></a>Nākamās darbības

Būvējiet virs saviem bagātinātajiem klientu datiem. Veidojiet [segmentus](segments.md), [mērus](measures.md)un pat [eksportējiet datus](export-destinations.md), lai klientiem sniegtu personalizētas iespējas.

## <a name="data-privacy-and-compliance"></a>Datu konfidencialitāte un atbilstība

Ja iespējojat Dynamics 365 Customer Insights datu pārsūtīšanu uz HERE Technologies, jūs atļaujat datu pārsūtīšanu ārpus atbilstības robežām Dynamics 365 Customer Insights, ieskaitot iespējami sensitīvus datus, piemēram, personas datus. Microsoft šos datus pārsūtīs pēc jūsu norādēm, bet jūs esat atbildīgs par to, lai nodrošinātu HERE Technologies atbilstību konfidencialitātes vai drošības saistībām, kas jums varētu rasties. Papildinformāciju skatiet rakstā [Microsoft Privātuma paziņojums](https://go.microsoft.com/fwlink/?linkid=396732).
Jūsu Dynamics 365 Customer Insights administrators var noņemt šo bagātināšanas funkciju jebkurā laikā, lai pārtrauktu izmantot šo funkcionalitāti.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
