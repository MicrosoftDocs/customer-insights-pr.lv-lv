---
title: Bagātināšana ar trešās puses bagātināšanas programmu Experian
description: Vispārēja informācija par Experian trešās puses bagātināšanu.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 9cf2a7fa18ecc022ea67f6829f52381ad59f3172
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896382"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Bagātiniet klientu profilus ar demogrāfijas rādītājiem no Experian (priekšskatījums)

Experian ir pasaules mēroga līderis patērētāju un uzņēmumu kredītatskaišu un mārketinga pakalpojumu nodrošināšanā. Ar Experian datu bagātināšanas pakalpojumiem jūs varat veidot padziļinātāku izpratni par saviem klientiem, bagātinot klientu profilus ar demogrāfijas datiem, piemēram, mājsaimniecības izmēru, ieņēmumiem utt.

## <a name="prerequisites"></a>Priekšnosacījumi

Lai konfigurētu Experian, ir jāatbilst šādiem priekšnosacījumiem:

- Ir jābūt aktīvam Experian abonementam. Lai iegūtu abonementu, tieši [sazinieties ar Experian](https://www.experian.com/marketing-services/contact). [Uzziniet vairāk par Experian datu bagātināšanu](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).

- Administrators jau ir konfigurējis Experian savienojumu *vai* jums ir [administratora](permissions.md#administrator) atļaujas. Jums arī ir nepieciešams lietotāja ID, partijas ID un modeļa numurs jūsu SSH iespējotajam drošā transporta (ST) kontam, kuru jums izveidoja Experian.

## <a name="configure-the-enrichment"></a>Bagātināto datu konfigurēšana

1. dodieties uz **Dati** > **Bagātināšana** un atlasiet cilni **Atklāt**.

1. Experian elementā atlasiet **Bagātināt manus datus**.

   > [!div class="mx-imgBorder"]
   > ![Experian elements](media/experian-tile.png "Experian elements")
   > 

1. Nolaižamajā izvēlnē atlasiet [savienojums](connections.md). Ja nav pieejamu savienojumu, sazinieties ar administratoru. Ja esat administrators, jūs varat izveidot savienojumu, atlasot **Pievienot savienojumu** un nolaižamajā izvēlnē izvēloties Experian. 

1. Atlasiet **Pieslēgties Experian**, lai apstiprinātu savienojuma atlasi.

1.  Atlasiet **Tālāk** un izvēlieties **Klientu datu kopu**, kuru vēlaties bagātināt ar demogrāfijas datiem no Experian. Varat atlasīt entītiju **Klients**, lai bagātinātu visus klientu profilus, vai atlasīt segmenta entītiju, lai bagātinātu tikai šajā segmentā iekļautos klientu profilus.

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Ekrānuzņēmums, izvēloties klientu datu kopu.":::

1. Atlasiet **Tālāk** un definējiet kura veida laukus no jūsu vienotajiem profiliem vajadzētu izmantot, meklējot atbilstošus demogrāfijas datus no Experian. Ir obligāti jānorāda vismaz viens no laukiem **Vārds, uzvārds un adrese**, **Tālruņa numurs** vai **E-pasts**. Lai nodrošinātu augstāku atbilstības precizitāti, var pievienot līdz diviem citiem laukiem. Šāda atlase ietekmēs kartēšanas laukus, kuriem jums būs piekļuve nākamajā darbībā.

    > [!TIP]
    > Jo vairāk galveno identifikatoru atribūtu tiek nosūtīts Experian, jo augstāka iespēja iegūt augstāku atbilstības rādītāju.

1. Lai sāktu lauka kartēšanu, atlasiet **Tālāk**.

1. Definējiet, kura veida laukus no jūsu vienotajiem profiliem vajadzētu izmantot, meklējot atbilstošus demogrāfijas datus no Experian. Obligātie lauki ir atzīmēti.

1. Norādiet bagātināto datu nosaukumu un izvades entitījas nosaukumu.

1. Pēc izvēļu pārskatīšanas atlasiet **Saglabāt vidi**.

## <a name="configure-the-connection-for-experian"></a>Experian savienojuma konfigurēšana 

Lai konfigurētu savienojumus, jums ir jābūt administratoram. Konfigurējot bagātinātos datus, atlasiet **Pievienot savienojumu** *vai* dodieties uz **Administrators** > **Savienojumi** un Experian rūtī atlasiet **Iestatīt**.

1. Atlasiet **Sākt**.

1. Lodziņā **Parādāmais nosaukums** ievadiet savienojuma nosaukumu.

1. Ievadiet derīgu lietotāja ID, partijas ID un modeļa numuru no sava Experian Secure Transport konta.

1. Pārskatiet un sniedziet savu piekrišanu **Datu konfidencialitātei un atbilstībai**, atzīmējot izvēles rūtiņu **Piekrītu**

1. Lai pārbaudītu konfigurāciju, atlasiet **Pārbaudīt**.

1. Pēc pārbaudes pabeigšanas atlasiet **Saglabāt**.
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Experian savienojuma konfigurācijas rūts.":::

## <a name="enrichment-results"></a>Bagātināšanas rezultāti

Lai sāktu bagātināšanas procesu, komandjoslā atlasiet **Palaist**. Varat arī ļaut sistēmai palaist bagātināšanu automātiski kā daļu no [plānotās atsvaidzināšanas](system.md#schedule-tab). Apstrādes laiks būs atkarīgs no klientu datu izmēra un bagātināšanas procesiem, kurus jūsu kontam ir uzstādījis Experian.

Pēc bagātināšanas procesa noslēgšanas varat pārskatīt tikko bagātinātos klientu profilu datus, dodoties uz sadaļu **Mana bagātināšana**. Turklāt jūs redzēsit pēdējā atjauninājuma laiku un bagātināto profilu skaitu.

Jūs varat piekļūt detalizētam katra bagātināta profila skatam, atlasot opciju **Skatīt bagātinātos datus**.

## <a name="next-steps"></a>Nākamās darbības

Būvējiet virs saviem bagātinātajiem klientu datiem. Veidojiet [segmentus](segments.md), [mērus](measures.md)un pat [eksportējiet datus](export-destinations.md), lai klientiem sniegtu personalizētas iespējas.

## <a name="data-privacy-and-compliance"></a>Datu konfidencialitāte un atbilstība

Ja iespējojat Dynamics 365 Customer Insights datu pārsūtīšanu uz Experian, jūs atļaujat datu pārsūtīšanu ārpus atbilstības robežām Dynamics 365 Customer Insights, ieskaitot iespējami sensitīvus datus, piemēram, personas datus. Microsoft šos datus pārsūtīs pēc jūsu norādēm, bet jūs esat atbildīgs par to, lai nodrošinātu Experian atbilstību konfidencialitātes vai drošības saistībām, kas jums varētu rasties. Papildinformāciju skatiet rakstā [Microsoft Privātuma paziņojums](https://go.microsoft.com/fwlink/?linkid=396732).
Jūsu Dynamics 365 Customer Insights administrators var noņemt šo bagātināšanas funkciju jebkurā laikā, lai pārtrauktu izmantot šo funkcionalitāti.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
