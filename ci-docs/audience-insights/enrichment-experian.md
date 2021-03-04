---
title: Bagātināšana ar trešās puses bagātināšanas programmu Experian
description: Vispārēja informācija par Experian trešās puses bagātināšanu.
ms.date: 12/10/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: baf3cc58a233b70c48fb94ac4a543d162f91bdd1
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269569"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Bagātiniet klientu profilus ar demogrāfijas rādītājiem no Experian (priekšskatījums)

Experian ir pasaules mēroga līderis patērētāju un uzņēmumu kredītatskaišu un mārketinga pakalpojumu nodrošināšanā. Ar Experian datu bagātināšanas pakalpojumiem jūs varat veidot padziļinātāku izpratni par saviem klientiem, bagātinot klientu profilus ar demogrāfijas datiem, piemēram, mājsaimniecības izmēru, ieņēmumiem utt.

## <a name="prerequisites"></a>Priekšnosacījumi

Lai konfigurētu Experian, ir jāatbilst šādiem priekšnosacījumiem:

- Ir jābūt aktīvam Experian abonementam. Lai iegūtu abonementu, tieši [sazinieties ar Experian](https://www.experian.com/marketing-services/contact). [Uzziniet vairāk par Experian datu bagātināšanu](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).
- Jums ir lietotāja ID, partijas ID un modeļa numurs jūsu SSH iespējotajam drošās transportēšanas (ST) kontam, kuru Experian jums ir izveidojis.
- Jums ir [Administratora](permissions.md#administrator) tiesības skatīt auditorijas ieskatus.

## <a name="configuration"></a>Konfigurācija

1. dodieties uz **Dati** > **Bagātināšana** un atlasiet cilni **Atklāt**.

1. Experian elementā atlasiet **Bagātināt manus datus**.

   > [!div class="mx-imgBorder"]
   > ![Experian elements](media/experian-tile.png "Experian elements")

1. Atlasiet **Sākt darbu** un ievadiet lietotāja ID, partijas ID un modeļa numuru jūsu Experian drošās transportēšanas kontam. Pārskatiet un sniedziet savu piekrišanu **Datu konfidencialitātei un atbilstībai**, atzīmējot izvēles rūtiņu **Piekrītu**. Apstipriniet visus datus, atlasot **Piemērot**.

## <a name="map-your-fields"></a>Lauku kartēšana

1.  Atlasiet **Pievienot datus** un izvēlieties **Klienta datu kopu**, ko vēlaties bagātināt ar demogrāfiskajiem datiem no programmas Experian. Varat atlasīt entītiju **Klients**, lai bagātinātu visus klientu profilus, vai atlasīt segmenta entītiju, lai bagātinātu tikai šajā segmentā iekļautos klientu profilus.

1. Atlasiet galvenos identifikatorus no laukiem **Vārds un adrese**, **E-pasts** vai **Tālrunis**, lai tos nosūtītu uz Experian identitātes noteikšanai.

   > [!TIP]
   > Jo vairāk galveno identifikatoru atribūtu tiek nosūtīts Experian, jo augstāka iespēja iegūt augstāku atbilstības rādītāju.

1. Atlasiet **Nākamais** un kartējiet atbilstošos atribūtus no jūsu vienotās klientu entītijas atlasītajiem galvenajiem identifikatoru laukiem.

1. Atlasiet **Pievienot atribūtus**, lai kartētu papildu atribūtus, kurus vēlaties nosūtīt uz Experian.

1.  Atlasiet **Saglabāt**, lai pabeigtu lauka kartēšanu.

    > [!div class="mx-imgBorder"]
    > ![Experian lauka kartēšana](media/experian-field-mapping.png "Experian lauka kartēšana")

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