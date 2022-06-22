---
title: Bagātināšana ar trešās puses bagātināšanas Experian
description: Vispārīga informācija par Experian trešo pušu bagātināšanu.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 735da18e584b0d9db76b557f4d16dbdf1757f33c
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 06/13/2022
ms.locfileid: "8954096"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Klientu profilu bagātināšana ar demogrāfiskajiem datiem no Experian (priekšskatījums)

Experian ir globālais līderis patērētāju un uzņēmumu kredītu pārskatu izveides un mārketinga pakalpojumos. Izmantojot Experian datu bagātināšanas pakalpojumus, jūs varat veidot lielāku izpratni par saviem klientiem, bagātinot savu klientu profilus ar tādiem demogrāfiskiem datiem kā mājsaimniecības lielums, ienākumi un daudz kas cits.

## <a name="supported-countriesregions"></a>Atbalstītās valstis/reģioni

Pašlaik tiek atbalstīta klientu profilu bagātināšana tikai Amerikas Savienotajās Valstīs.

## <a name="prerequisites"></a>Priekšnoteikumi

- Aktīvs Experian abonements. Lai iegūtu abonementu, tieši [sazinieties ar Experian](https://www.experian.com/marketing-services/contact). [Papildinformācija par Experian datu bagātināšanu](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).

- Savienojumu Experian [...](connections.md)[konfigurē](#configure-the-connection-for-experian) administrators.

- Experian Lietotāja ID, puses ID un modeļa numurs jūsu SSH iespējotajam drošajam transporta (ST) kontam, kas Experian izveidots jums.

## <a name="configure-the-connection-for-experian"></a>Savienojuma konfigurēšana Experian

Jums ir jābūt customer insights administratoram [un](permissions.md#admin) jābūt Experian lietotāja ID, puses ID un modeļa numuram.

1. Konfigurējot bagātināšanu, atlasiet **Pievienot savienojumu** vai dodieties uz **Administrēšanas** > **savienojumi** un atlasiet **Iestatīt** uz Experian elementa.

   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Experian savienojuma konfigurācijas rūts.":::

1. Ievadiet savienojuma nosaukumu un derīgu lietotāja ID, puses ID un modeļa numuru savam Experian drošajam transporta kontam.

1. Pārskatiet un sniedziet savu piekrišanu [Datu konfidencialitātei un atbilstībai](#data-privacy-and-compliance), atlasot **Es piekrītu**.

1. Atlasiet **Pārbaudīt**, lai validētu konfigurāciju, un pēc tam atlasiet **Saglabāt**.

### <a name="data-privacy-and-compliance"></a>Datu konfidencialitāte un atbilstība

Iespējojot Dynamics 365 Customer Insights datu pārsūtīšanai uz Experian, jūs atļaujat datu pārsūtīšanu ārpus atbilstības robežas, kas paredzēta Dynamics 365 Customer Insights, ieskaitot potenciāli sensitīvus datus, piemēram, personas datus. Microsoft šos datus pārsūtīs pēc jūsu norādījuma, bet jūs esat atbildīgs par to, lai Experian atbilstu visām jūsu konfidencialitātes vai drošības saistībām. Papildinformāciju skatiet rakstā [Microsoft Privātuma paziņojums](https://go.microsoft.com/fwlink/?linkid=396732). Jūsu Dynamics 365 Customer Insights administrators var noņemt šo bagātināšanas funkciju jebkurā laikā, lai pārtrauktu šīs funkcijas izmantošanu.

## <a name="configure-the-enrichment"></a>Bagātināto datu konfigurēšana

1. Dodieties uz **Dati** > **Bagātināšana** un atlasiet cilni **Atklāt**.

1. Atlasiet **Bagātināt manus datus** elementā **Demogrāfiskie** dati no Experian elementa.

   :::image type="content" source="media/experian-tile.png" alt-text="Experian elements bagātināšanas pārskata lapā.":::

1. Pārskatiet pārskatu un pēc tam atlasiet **Tālāk**.

1. Atlasiet savienojumu. Ja tāds nav pieejams, sazinieties ar administratoru.

1. Atlasiet **Tālāk**.

1. **Atlasiet klienta datu kopu** un izvēlieties profilu vai segmentu, kuru vēlaties bagātināt ar demogrāfiskajiem datiem no Experian programmas. Klientu *uzņēmums* bagātina visus jūsu klientu profilus, savukārt segments bagātina tikai šajā segmentā esošos klientu profilus.

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Ekrānuzņēmums, izvēloties klientu datu kopu.":::

1. Definējiet, kāda tipa laukus no vienotajiem profiliem izmantot, lai saskaņotu demogrāfiskos datus no Experian. Ir obligāti jānorāda vismaz viens no laukiem **Vārds, uzvārds un adrese**, **Tālruņa numurs** vai **E-pasts**. Lai nodrošinātu augstāku atbilstības precizitāti, pievienojiet citus laukus. Atlasiet **Tālāk**.

1. Kartējiet laukus uz demogrāfiskajiem datiem no Experian.

1. Lai pabeigtu lauka kartēšanu, atlasiet **Tālāk**.

1. **Norādiet bagātināšanas nosaukumu** un entītijas **Izvade nosaukumu**.

1. Pēc izvēļu pārskatīšanas atlasiet **Saglabāt bagātināšanu**.

1. Atlasiet **Palaist**, lai sāktu bagātināšanas procesu, vai tuvu, lai **atgrieztos lapā Bagātinājumi**.

## <a name="enrichment-results"></a>Bagātināšanas rezultāti

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

Klientu **skaits, kas bagātināts ar lauku**, nodrošina katra bagātinātā lauka aptvērumu.

## <a name="next-steps"></a>Nākamās darbības

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
