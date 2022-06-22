---
title: Bagātināt klientu profilus ar atrašanās vietas datiem no Azure maps
description: Vispārīga informācija par Azure Maps pirmo pušu bagātināšanu.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: a806b2d0c791972c967c90694527608b4def9f3f
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 06/13/2022
ms.locfileid: "8953637"
---
# <a name="enrichment-of-customer-profiles-with-azure-maps-preview"></a>Klientu profilu bagātināšana ar Azure Maps (priekšskatījums)

Azure Maps nodrošina uz atrašanās vietu orientētus datus un pakalpojumus, lai sniegtu pieredzi, pamatojoties uz ģeotelpiskajiem datiem, ar iebūvētu atrašanās vietas informāciju. Azure Maps datu bagātināšanas pakalpojumi uzlabo atrašanās vietas informācijas precizitāti par klientiem. Tas sniedz iespējas, piemēram, adrešu normalizēšanu un platuma un garuma izvilkšanu Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Priekšnoteikumi

- Aktīvs Azure Maps abonements. Lai iegūtu abonementu, [reģistrējieties vai saņemiet bezmaksas izmēģinājumu](https://azure.microsoft.com/services/azure-maps/).

- Azure Maps [savienojumu](connections.md)[konfigurē](#configure-the-connection-for-azure-maps) administrators.

## <a name="configure-the-connection-for-azure-maps"></a>Konfigurējiet Azure Maps savienojumu

Jums jābūt Customer Insights administratoram [un](permissions.md#admin) jābūt aktīvai Azure Maps API atslēgai.

1. Konfigurējot bagātinātos datus, atlasiet **Pievienot savienojumu** vai dodieties uz **Administrators** > **Savienojumi** un atlasiet **Iestatīt** rūtī Azure Maps.

   :::image type="content" source="media/enrichment-azure-maps-connection.png" alt-text="Azure Maps bagātināšanas konfigurācijas lapa.":::

1. Ievadiet savienojuma nosaukumu un derīgu Azure Maps API atslēgu.

1. Pārskatiet un sniedziet savu piekrišanu [Datu konfidencialitātei un atbilstībai](#data-privacy-and-compliance), atlasot **Es piekrītu**.

1. Atlasiet **Pārbaudīt**, lai validētu konfigurāciju, un pēc tam atlasiet **Saglabāt**.

### <a name="data-privacy-and-compliance"></a>Datu konfidencialitāte un atbilstība

Iespējojot Dynamics 365 Customer Insights datu pārsūtīšanai uz Azure Maps, jūs atļaujat datu pārsūtīšanu ārpus atbilstības robežas, kas paredzēta Dynamics 365 Customer Insights, ieskaitot potenciāli sensitīvus datus, piemēram, personas datus. Microsoft pārsūtīs šādus datus pēc jūsu norādījumiem, bet jūs esat atbildīgs par to, lai Azure Maps atbilstu visiem jūsu konfidencialitātes vai drošības pienākumiem. Papildinformāciju skatiet [Microsoft paziņojumā par konfidencialitāti](https://go.microsoft.com/fwlink/?linkid=396732).
Jūsu Dynamics 365 Customer Insights administrators var noņemt šo bagātināšanas funkciju jebkurā laikā, lai pārtrauktu izmantot šo funkcionalitāti.

## <a name="configure-the-enrichment"></a>Bagātināto datu konfigurēšana

1. Dodieties uz **Dati** > **Bagātināšana** un atlasiet cilni **Atklāt**.

1. Atlasiet **Bagātināt manus datus** elementā **Atrašanās vieta** no Microsoft Azure elementa Maps.

   :::image type="content" source="media/azure-maps-tile.png" alt-text="elements Azure Maps.":::

1. Pārskatiet pārskatu un pēc tam atlasiet **Tālāk**.

1. Atlasiet savienojumu. Ja nav pieejamu savienojumu, sazinieties ar administratoru.

1. Atlasiet **Tālāk**.

1. **Atlasiet klienta datu kopu** un izvēlieties profilu vai segmentu, kuru vēlaties bagātināt ar Microsoft datiem. Klientu *uzņēmums* bagātina visus jūsu klientu profilus, savukārt segments bagātina tikai šajā segmentā esošos klientu profilus.

1. Definējiet, kāda tipa laukus no vienotajiem profiliem izmantot saskaņošanai: primārā un/vai sekundārā adrese. Jūs varat norādīt lauka kartējumu abām adresēm un atsevišķi bagātināt abu adrešu profilus. Piemēram, mājas adresei un uzņēmuma adresei. Atlasiet **Tālāk**.

1. Kartējiet savus laukus uz atrašanās vietas datiem no Azure Maps. Atlasītajai primārajai un/vai sekundārajai adresei ir nepieciešami lauki **Adreses 1. rinda** un **Pasta indekss**. Lai nodrošinātu augstāku atbilstības precizitāti, pievienojiet papildu laukus.

   :::image type="content" source="media/enrichment-azure-maps-attributes.png" alt-text="Azure Maps atribūtu kartēšana.":::

1. Lai pabeigtu lauka kartēšanu, atlasiet **Tālāk**.

1. Pārskatiet **papildu iestatījumus**, kas nodrošina maksimālu elastību, lai apstrādātu papildu lietošanas pieteikumus. Tomēr šādas noklusējuma vērtības parasti nav jāmaina.

   - **Adrešu** tips: labākā adreses atbilstība tiek atgriezta pat tad, ja tā ir nepilnīga. Lai iegūtu tikai pilnīgas adreses&mdash;, piemēram, adreses, kurās iekļauts mājas numurs&mdash;, notīriet visas izvēles rūtiņas, izņemot **Punktu adreses**.
   - **Valoda**: adreses atgriežas valodā, pamatojoties uz adreses reģionu. Lai lietotu standartizētu adrešu valodu, nolaižamajā izvēlnē atlasiet valodu. Piemēram, izvēloties **angļu valodu**, tiek atgriezta **Kopenhāgena, Dānija**, nevis **København, Danmark**.
   - **Maksimālais rezultātu** skaits: rezultātu skaits vienā adresē.

1. Atlasiet **Tālāk**.

1. **Norādiet bagātināšanas nosaukumu** un entītijas **Izvade nosaukumu**.

1. Pēc izvēļu pārskatīšanas atlasiet **Saglabāt bagātināšanu**.

1. Atlasiet **Palaist**, lai sāktu bagātināšanas procesu, vai tuvu, lai **atgrieztos lapā Bagātinājumi**.

## <a name="enrichment-results"></a>Bagātināšanas rezultāti

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

Klientu **skaits, kas bagātināts ar lauku**, nodrošina katra bagātinātā lauka aptvērumu.

## <a name="next-steps"></a>Nākamās darbības

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
