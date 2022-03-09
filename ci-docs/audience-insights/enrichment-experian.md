---
title: Bagātināšana ar trešās puses bagātināšanas Experian
description: Vispārīga informācija par Experian trešo pušu bagātināšanu.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: ad1023135516ca9c49818d19aa84df68d16b2e3c
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 02/16/2022
ms.locfileid: "8229973"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Klientu profilu bagātināšana ar demogrāfiskajiem datiem no Experian (priekšskatījums)

Experian ir globālais līderis patērētāju un uzņēmumu kredītu pārskatu izveides un mārketinga pakalpojumos. Izmantojot Experian datu bagātināšanas pakalpojumus, jūs varat veidot lielāku izpratni par saviem klientiem, bagātinot savu klientu profilus ar tādiem demogrāfiskiem datiem kā mājsaimniecības lielums, ienākumi un daudz kas cits.

## <a name="prerequisites"></a>Priekšnosacījumi

Lai konfigurētu Experian, ir jāizpilda šādi priekšnosacījumi:

- Jums ir jābūt aktīvam Experian abonementam. Lai iegūtu abonementu, tieši [sazinieties ar Experian](https://www.experian.com/marketing-services/contact). [Papildinformācija par Experian datu bagātināšanu](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).

- Administrators jau ir konfigurējis Experian savienojumu *vai* jums ir [administratora](permissions.md#administrator) atļaujas. Jums ir nepieciešams arī lietotāja ID, puses ID un modeļa numurs jūsu SSH iespējotajam drošajam transporta (ST) kontam, ko Experian izveidoja jums.

## <a name="supported-countriesregions"></a>Atbalstītās valstis/reģioni

Pašlaik tiek atbalstīta klientu profilu bagātināšana tikai Amerikas Savienotajās Valstīs.

## <a name="configure-the-enrichment"></a>Bagātināto datu konfigurēšana

1. Dodieties uz **Dati** > **Bagātināšana** un atlasiet cilni **Atklāt**.

1. Atlasiet **Bagātināt manus datus** elementā Experian.

   > [!div class="mx-imgBorder"]
   > ![Experian elements.](media/experian-tile.png "Experian elements")
   > 

1. Atlasiet [savienojumu](connections.md) nolaižamajā sarakstā. Ja nav pieejamu savienojumu, sazinieties ar administratoru. Ja esat administrators, varat izveidot savienojumu, atlasot **Pievienot savienojumu** un izvēloties Experian nolaižamajā sarakstā. 

1. Atlasiet **Savienot ar Experian**, lai apstiprinātu savienojuma atlasi.

1.  Atlasiet **Nākamais** un izvēlieties **Klientu datu kopu**, kuru vēlaties bagātināt ar demogrāfiskajiem datiem no Experian. Varat atlasīt entītiju **Klients**, lai bagātinātu visus klientu profilus, vai atlasīt segmenta entītiju, lai bagātinātu tikai šajā segmentā iekļautos klientu profilus.

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Ekrānuzņēmums, izvēloties klientu datu kopu.":::

1. Atlasiet **Tālāk** un definējiet, kāda tipa lauki no jūsu vienotajiem profiliem ir jāizmanto, lai meklētu atbilstošos demogrāfisko datus no Experian. Ir obligāti jānorāda vismaz viens no laukiem **Vārds, uzvārds un adrese**, **Tālruņa numurs** vai **E-pasts**. Lai nodrošinātu augstāku atbilstības precizitāti, var pievienot līdz diviem citiem laukiem. Šāda atlase ietekmēs kartēšanas laukus, kuriem jums būs piekļuve nākamajā darbībā.

    > [!TIP]
    > Papildu atslēgas identifikatora atribūti, kas nosūtīti uz Experian, var nodrošināt augstāku atbilstības precizitāti.

1. Lai sāktu lauka kartēšanu, atlasiet **Tālāk**.

1. Definējiet, kāda tipa lauki no jūsu vienotajiem profiliem ir jāizmanto, lai meklētu atbilstošos demogrāfiskos datus no Experian. Obligātie lauki ir atzīmēti.

1. Norādiet bagātināto datu nosaukumu un izvades entitījas nosaukumu.

1. Pēc izvēļu pārskatīšanas atlasiet **Saglabāt bagātināšanu**.

## <a name="configure-the-connection-for-experian"></a>Savienojuma konfigurēšana Experian 

Lai konfigurētu savienojumus, jums ir jābūt administratoram. Atlasiet vienumu **Pievienot savienojumu**, konfigurējot bagātināšanu, *vai* pārejiet uz **Administrators** > **Savienojumi** un atlasiet opciju **Iestatīt** Experian elementā.

1. Atlasiet **Sākt**.

1. Lodziņā **Parādāmais nosaukums** ievadiet savienojuma nosaukumu.

1. Ievadiet savam Experian drošajam transporta kontam derīgu lietotāja ID, puses ID un modeļa numuru.

1. Pārskatiet un sniedziet savu piekrišanu **Datu konfidencialitātei un atbilstībai**, atlasot **Es piekrītu**.

1. Lai pārbaudītu konfigurāciju, atlasiet **Pārbaudīt**.

1. Pēc pārbaudes pabeigšanas atlasiet **Saglabāt**.
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Experian savienojuma konfigurācijas rūts.":::

## <a name="enrichment-results"></a>Bagātināšanas rezultāti

Lai sāktu bagātināšanas procesu, komandjoslā atlasiet **Palaist**. Varat arī ļaut sistēmai palaist bagātināšanu automātiski kā daļu no [plānotās atsvaidzināšanas](system.md#schedule-tab). Apstrādes laiks atkarīgs no klientu datu apjoma un bagātināšanas procesiem, ko jūsu kontam iestata Experian.

Pēc bagātināšanas procesa noslēgšanas varat pārskatīt tikko bagātinātos klientu profilu datus, dodoties uz sadaļu **Mana bagātināšana**. Turklāt jūs redzēsit pēdējā atjauninājuma laiku un bagātināto profilu skaitu.

Jūs varat piekļūt detalizētam katra bagātināta profila skatam, atlasot opciju **Skatīt bagātinātos datus**.

## <a name="next-steps"></a>Nākamās darbības

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Datu konfidencialitāte un atbilstība

Iespējojot Dynamics 365 Customer Insights datu pārsūtīšanai uz Experian, jūs atļaujat datu pārsūtīšanu ārpus atbilstības robežas, kas paredzēta Dynamics 365 Customer Insights, ieskaitot potenciāli sensitīvus datus, piemēram, personas datus. Microsoft šos datus pārsūtīs pēc jūsu norādījuma, bet jūs esat atbildīgs par to, lai Experian atbilstu visām jūsu konfidencialitātes vai drošības saistībām. Papildinformāciju skatiet rakstā [Microsoft Privātuma paziņojums](https://go.microsoft.com/fwlink/?linkid=396732).
Jūsu Dynamics 365 Customer Insights administrators var noņemt šo bagātināšanas funkciju jebkurā laikā, lai pārtrauktu šīs funkcijas izmantošanu.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
