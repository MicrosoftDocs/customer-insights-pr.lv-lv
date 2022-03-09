---
title: Bagātināt klientu profilus ar atrašanās vietas datiem no Azure maps
description: Vispārīga informācija par Azure Maps pirmo pušu bagātināšanu.
ms.date: 08/31/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: cb1c0778a398ef6d338ce6cf9e199eae0c344a5c
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 02/16/2022
ms.locfileid: "8226458"
---
# <a name="enrichment-of-customer-profiles-with-azure-maps-preview"></a>Klientu profilu bagātināšana ar Azure Maps (priekšskatījums)

Azure Maps nodrošina uz atrašanās vietu balstītus datus un pakalpojumus, lai, izmantojot iebūvētu atrašanās vietas informāciju, sniegtu pieredzi, kuras pamatā ir iebūvētas atrašanās vietas dati. Azure Maps datu bagātināšanas pakalpojumi uzlabo atrašanās vietas informācijas precizitāti par klientiem. Tas sniedz iespējas, piemēram, adrešu normalizēšanu un platuma un garuma izvilkšanu Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Priekšnosacījumi

Lai konfigurētu Azure Maps datu bagātināšanu, ir jāizpilda tālāk noteiktie priekšnosacījumi:

- Jums ir jābūt aktīvam Azure Maps abonementam. Lai iegūtu abonementu, varat [pierakstīties vai iegūt izmēģinājumversiju bez maksas](https://azure.microsoft.com/services/azure-maps/).

- Ir pieejams Azure Maps [savienojums](connections.md) *vai* jums ir [administratora](permissions.md#administrator) atļaujas un aktīva Azure Maps API atslēga.

## <a name="configure-the-enrichment"></a>Bagātināto datu konfigurēšana

1. Dodieties uz **Dati** > **Bagātināšana**. 

1. Elementā **Atrašanās vieta** atlasiet **Bagātināt manus datus**.

   :::image type="content" source="media/azure-maps-tile.png" alt-text="elements Azure Maps.":::

1. Atlasiet [savienojumu](connections.md) nolaižamajā sarakstā. Sazinieties ar administratoru, ja nav pieejams neviens Azure Maps savienojums. Ja esat administrators, varat konfigurēt [savienojumu ar Azure Maps](#configure-the-connection-for-azure-maps). 

1. Atlasiet **Tālāk**, lai apstiprinātu atlasi.

1. Izvēlieties **Klientu datu kopu**, kuru vēlaties bagātināt ar atrašanās vietas datiem no Azure Maps. Varat atlasīt entītiju **Klients**, lai bagātinātu visus savus vienotos klientu profilus, vai atlasīt segmenta entītiju, lai bagātinātu tikai šajā segmentā iekļautos klientu profilus.

    :::image type="content" source="media/enrichment-azure-maps-configuration-customer-data-set.png" alt-text="Izvēloties klienta datu kopu, veiciet ekrānuzņēmumu.":::

1. Izvēlieties, vai vēlaties kartēt laukus ar primāro un/vai sekundāro adresi. Varat norādīt lauku kartējumu gan adresēm, gan bagātināt abu adrešu profilus atsevišķi&mdash;, piemēram, kā sākuma adresi un uzņēmuma adresi. Atlasiet **Tālāk**.

1. Definējiet, kāda tipa lauki no jūsu vienotajiem profiliem ir jāizmanto, lai meklētu atbilstošos atrašanās vietu datus no Azure Maps. Atlasītajai primārajai un/vai sekundārajai adresei ir nepieciešami lauki **Adreses 1. rinda** un **Pasta indekss**. Lai nodrošinātu lielāku atbilstības precizitāti, var pievienot papildu laukus.

   :::image type="content" source="media/enrichment-azure-maps-configuration.png" alt-text="Azure Maps bagātināšanas konfigurācijas lapa.":::

1. Lai pabeigtu lauka kartēšanu, atlasiet **Tālāk**.

1. Novērtējiet, vai vēlaties modificēt **Papildu iestatījumus**. Tie ir nodrošināti, lai nodrošinātu maksimāli elastīgu iespēju apstrādāt detalizētās izmantošanas pieteikumus, taču noklusējuma vērtības vairumā gadījumu būs atbilstošas:
   - **Adrešu tips**: noklusējuma uzvedība ir tāda, ka bagātināšana atgriezīs vislabāko adrešu atbilstību pat tad, ja tā ir nepilnīga. Lai iegūtu tikai pilnīgas adreses&mdash;, piemēram, adreses, kurās iekļauts mājas numurs&mdash;, notīriet visas izvēles rūtiņas, izņemot **Punktu adreses**. 
   - **Valoda**: pēc noklusējuma adreses tiek atgrieztas tā reģiona valodā, kuram ir noteikta adrese. Lai lietotu standartizētu adrešu valodu, nolaižamajā izvēlnē atlasiet valodu. Piemēram, atlasot **angļu valodu**, jūs atgriezīs **Kopenhāgena, Dānija**, nevis **København, Danmark**.

1. Norādiet bagātināto datu nosaukumu.

1. Pēc izvēļu pārskatīšanas atlasiet **Saglabāt bagātināšanu**.

## <a name="configure-the-connection-for-azure-maps"></a>Konfigurējiet Azure Maps savienojumu

Lai konfigurētu savienojumus, jums ir jābūt audiences ieskatu administratoram. Konfigurējot bagātinātos datus, atlasiet **Pievienot savienojumu** vai dodieties uz **Administrators** > **Savienojumi** un atlasiet **Iestatīt** rūtī Azure Maps.

1. Lodziņā **Parādāmais nosaukums** ievadiet savienojuma nosaukumu.

1. Norādiet derīgu Azure maps API atslēgu.

1. Pārskatiet un sniedziet savu piekrišanu **Datu konfidencialitātei un atbilstībai**, atzīmējot izvēles rūtiņu **Piekrītu**

1. Lai pārbaudītu konfigurāciju, atlasiet **Pārbaudīt**.

1. Pēc pārbaudes pabeigšanas atlasiet **Saglabāt**.

:::image type="content" source="media/enrichment-azure-maps-connection.png" alt-text="Azure Maps bagātināšanas konfigurācijas lapa.":::

## <a name="enrichment-results"></a>Bagātināšanas rezultāti

Lai sāktu bagātināšanas procesu, komandjoslā atlasiet **Palaist**. Varat arī ļaut sistēmai palaist bagātināšanu automātiski kā daļu no [plānotās atsvaidzināšanas](system.md#schedule-tab). Apstrādes laiks ir atkarīgs no jūsu klientu datu apjoma un API atbildes laikiem.

Kad bagātināšanas process ir pabeigts, sadaļā **Mani bagātinājumi** varat pārskatīt tikko bagātinātos klientu profilu datus. Turklāt jūs redzēsit pēdējā atjauninājuma laiku un bagātināto profilu skaitu.

Jūs varat piekļūt detalizētam katra bagātināta profila skatam, atlasot opciju **Skatīt bagātinātos datus**.

## <a name="next-steps"></a>Nākamās darbības

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Datu konfidencialitāte un atbilstība

Iespējojot Dynamics 365 Customer Insights datu pārsūtīšanai uz Azure Maps, jūs atļaujat datu pārsūtīšanu ārpus atbilstības robežas, kas paredzēta Dynamics 365 Customer Insights, ieskaitot potenciāli sensitīvus datus, piemēram, personas datus. Microsoft šos datus pārsūtīs pēc jūsu norādījuma, bet jūs esat atbildīgs par to, lai Azure Maps atbilstu visām jūsu konfidencialitātes vai drošības saistībām. Papildinformāciju skatiet [Microsoft paziņojumā par konfidencialitāti](https://go.microsoft.com/fwlink/?linkid=396732).
Jūsu Dynamics 365 Customer Insights administrators var noņemt šo bagātināšanas funkciju jebkurā laikā, lai pārtrauktu izmantot šo funkcionalitāti.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
