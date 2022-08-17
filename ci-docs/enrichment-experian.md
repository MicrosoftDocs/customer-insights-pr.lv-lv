---
title: Klientu profilu bagātināšana ar demogrāfiskajiem datiem no Experian (priekšskatījums)
description: Vispārīga informācija par Experian trešo pušu bagātināšanu.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: fccb37cde3f05a70009c18b6c52db01a5ede094d
ms.sourcegitcommit: b1d06fe26934f12f0c5ed13e8ef1d37e52e67cc7
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 08/08/2022
ms.locfileid: "9238005"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Klientu profilu bagātināšana ar demogrāfiskajiem datiem no Experian (priekšskatījums)

Experian ir globālais līderis patērētāju un uzņēmumu kredītu pārskatu izveides un mārketinga pakalpojumos. Izmantojot Experian datu bagātināšanas pakalpojumus, jūs varat veidot lielāku izpratni par saviem klientiem, bagātinot savu klientu profilus ar tādiem demogrāfiskiem datiem kā mājsaimniecības lielums, ienākumi un daudz kas cits.

## <a name="supported-countriesregions"></a>Atbalstītās valstis/reģioni

Pašlaik tiek atbalstīta klientu profilu bagātināšana tikai Amerikas Savienotajās Valstīs.

## <a name="prerequisites"></a>Priekšnoteikumi

- Aktīvs Experian abonements. Lai iegūtu abonementu, tieši [sazinieties ar Experian](https://www.experian.com/marketing-services/contact). [Papildinformācija par Experian datu bagātināšanu](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).

- Savienojumu Experian [...](connections.md)[konfigurē](#configure-the-connection-for-experian) administrators.

- Experian Lietotāja ID, party ID un modeļa numurs jūsu SSH iespējotajam drošajam transporta (ST) kontam, kas Experian izveidots jums.

## <a name="configure-the-connection-for-experian"></a>Savienojuma konfigurēšana Experian

Jums ir jābūt administratoram [programmā](permissions.md#admin) Customer Insights, un jums ir jābūt Experian lietotāja ID, puses ID un modeļa numuram.

1. Konfigurējot bagātināšanu, atlasiet **Pievienot savienojumu** vai dodieties uz **Administratoru** > **savienojumi** un mozaīkā **atlasiet** Iestatīt Experian.

   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Experian savienojuma konfigurācijas rūts.":::

1. Ievadiet savienojuma nosaukumu un derīgu drošo pārvadājumu konta lietotāja ID, puses ID un modeļa numuru Experian.

1. Pārskatiet datu privātumu [un atbilstību](connections.md#data-privacy-and-compliance) un atlasiet **Es piekrītu**.

1. Atlasiet **Verificēt**, lai validētu konfigurāciju, un pēc tam atlasiet **Saglabāt**.

## <a name="configure-the-enrichment"></a>Bagātināto datu konfigurēšana

1. Dodieties uz **Dati** > **Bagātināšana** un atlasiet cilni **Atklāt**.

1. Atlasiet **Bagātināt manus datus** par **elementu Demogrāfiskie** Experian dati.

   :::image type="content" source="media/experian-tile.png" alt-text="Experian elements bagātināšanas pārskata lapā.":::

1. Pārskatiet pārskatu un pēc tam atlasiet **Tālāk**.

1. Atlasiet savienojumu. Ja nav pieejamu savienojumu, sazinieties ar administratoru.

1. Atlasiet **Tālāk**.

1. **Atlasiet klienta datu kopu** un izvēlieties profilu vai segmentu, no Experian kura vēlaties bagātināties ar demogrāfiskiem datiem. Klienta *entītija* bagātina visus jūsu klientu profilus, savukārt segments bagātina tikai šajā segmentā ietvertos klientu profilus.

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Ekrānuzņēmums, izvēloties klientu datu kopu.":::

1. Definējiet, kāda veida laukus no saviem vienotajiem profiliem izmantot, lai saskaņotu demogrāfiskos datus no Experian. Ir obligāti jānorāda vismaz viens no laukiem **Vārds, uzvārds un adrese**, **Tālruņa numurs** vai **E-pasts**. Lai iegūtu lielāku atbilstības precizitāti, pievienojiet citus laukus. Atlasiet **Tālāk**.

1. Kartējiet laukus uz demogrāfiskajiem datiem no Experian.

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
