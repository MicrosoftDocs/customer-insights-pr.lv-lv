---
title: Uzņēmuma profilu bagātināšana ar Dun & Bradstreet
description: Vispārīga informācija par Dun & Bradstreet trešo pušu bagātināšanu.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: b1038970b6aee3bbdd7f79cc457f79aaf1c38222
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 06/13/2022
ms.locfileid: "8953900"
---
# <a name="enrichment-of-company-profiles-with-dun--bradstreet-preview"></a>Uzņēmuma profilu bagātināšana ar Dun & Bradstreet (Preview)

Dun & Bradstreet nodrošina komerciālus datus, analīzi un ieskatus uzņēmumiem. Tā nodrošina klientiem vienotus klientu profilus, lai uzņēmumi bagātinātu datus. Bagātināšana ietver tādus atribūtus kā DUNS numurs, uzņēmuma lielums, atrašanās vieta, nozare un daudz kas cits.

## <a name="prerequisites"></a>Priekšnoteikumi

- Aktīva [Dun & Bradstreet](https://www.dnb.com/marketing/media/give-your-data-a-boost.html?source=microsoft_audience_insights) licence.
- [Vienoti](customer-profiles.md) debitoru profili uzņēmumiem.
- Ir izveidots Dun & Bradstreet [projekts](#set-up-your-dun--bradstreet-project).
- Dun & Bradstreet [savienojumu](connections.md)[konfigurē](#configure-a-connection-for-dun--bradstreet) administrators.

## <a name="set-up-your-dun--bradstreet-project"></a>Izveidojiet savu Dun & Bradstreet projektu

Kā licencēts Dun & Bradstreet lietotājs varat izveidot projektu [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights).

1. Piesakieties [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights). Lai izgūtu akreditācijas datus, [atjaunojiet paroli](https://sso.dnb.com/signin/forgot-password?lead_source=microsoft_audienceinsights).

1. Lejupielādējiet [mūsu csv veidnes failu](https://c360devenrichment.blob.core.windows.net/mapping/DnBCIdatamapping.csv), kas tiks izmantots, lai kartētu Customer Insights laukus uz atbilstošajiem Dun & Bradstreet laukiem.

1. Augšupielādējiet failu **Dun & Bradstreet projekta izveides pieredzes augšupielādes datu** solī.

1. Atlasiet horizontālos punktus zem atbilstošā **avota** jaunizveidotajā Dun & Bradstreet projektā, lai skatītu pieejamās opcijas.

   :::image type="content" source="media/enrichment-dnb-dots.png" alt-text="Ekrānuzņēmums ar punktiem Dun & Bradstreet projektā.":::

1. Izvēlieties **Iegūt detalizētu informāciju par** S3. Glabājiet šo informāciju drošā vietā. Jums tas būs nepieciešams, lai iestatītu [savienojumu bagātināšanai](#configure-a-connection-for-dun--bradstreet) customer insights.

   :::image type="content" source="media/enrichment-dnb-s3info.png" alt-text="Ekrānuzņēmums, kurā redzama s3 informācijas izlase Dun & Bradstreet projektā.":::

## <a name="configure-a-connection-for-dun--bradstreet"></a>Dun & Bradstreet savienojuma konfigurēšana

Jums jābūt Customer Insights administratoram [un](permissions.md#admin) jābūt Dun & Bradstreet Connect akreditācijas datiem.

1. Atlasiet **Pievienot savienojumu**, konfigurējot bagātināšanu, vai dodieties uz **Administrēšanas** > **savienojumi** un atlasiet **Iestatīt** uz Elementa Dun & Bradstreet.

1. Ievadiet savienojuma nosaukumu.

1. Norādiet derīgus Dun & Bradstreet akreditācijas datus un Dun & Bradstreet projekta detaļas *Reģions, Nometiet mapes ceļu un Nometiet mapes nosaukumu*. Jūs [saņemat šo informāciju](#set-up-your-dun--bradstreet-project) no Dun & Bradstreet projekta.

1. Pārskatiet un sniedziet savu piekrišanu [Datu konfidencialitātei un atbilstībai](#data-privacy-and-compliance), atlasot **Es piekrītu**.

1. Atlasiet **Pārbaudīt**, lai validētu konfigurāciju, un pēc tam atlasiet **Saglabāt**.

   :::image type="content" source="media/enrichment-dnb-connection.png" alt-text="Dun & Bradstreet savienojuma konfigurācijas lapa.":::

### <a name="data-privacy-and-compliance"></a>Datu konfidencialitāte un atbilstība

Kad iespējojat Dynamics 365 Customer Insights pārsūtīt datus uz Dun & Bradstreet, jūs atļaujat pārsūtīt datus ārpus atbilstības robežas, tostarp potenciāli sensitīviem Dynamics 365 Customer Insights datiem, piemēram, Personas datiem. Microsoft pārsūtīs šādus datus pēc jūsu norādījumiem, taču jūs esat atbildīgs par to, lai Dun & Bradstreet izpildītu visas jūsu konfidencialitātes vai drošības saistības. Papildinformāciju skatiet rakstā [Microsoft Privātuma paziņojums](https://go.microsoft.com/fwlink/?linkid=396732).
Jūsu Dynamics 365 Customer Insights administrators var noņemt šo bagātināšanas funkciju jebkurā laikā, lai pārtrauktu šīs funkcijas izmantošanu.

## <a name="supported-countries-or-regions"></a>Atbalstītās valstis vai reģioni

Pašlaik mēs atbalstām šādas valsts/reģiona iespējas: Kanāda (angļu) vai Amerikas Savienotās Valstis (angļu).

## <a name="configure-the-enrichment"></a>Bagātināto datu konfigurēšana

1. Dodieties uz **Dati** > **Bagātināšana** un atlasiet cilni **Atklāt**.

1. Atlasiet **Bagātināt manus** datus **par uzņēmuma datiem** dun & Bradstreet elementam.

   :::image type="content" source="media/enrichment-dnb-tile.png" alt-text="Dun & Bradstreet flīzes ekrānuzņēmums.":::

1. Pārskatiet pārskatu un pēc tam atlasiet **Tālāk**.

1. Atlasiet savienojumu un apstipriniet. Ja tāds nav pieejams, sazinieties ar administratoru.

1. Atlasiet **Tālāk**.

1. **Atlasiet klienta datu kopu** un izvēlieties profilu vai segmentu, kuru vēlaties bagātināt ar uzņēmuma datiem no Dun & Bradstreet. Klientu *uzņēmums* bagātina visus jūsu klientu profilus, savukārt segments bagātina tikai šajā segmentā esošos klientu profilus.

1. Definējiet, kāda veida laukus no vienotajiem profiliem izmantot, lai saskaņotu uzņēmuma datus no Dun & Bradstreet. Ir obligāti jānorāda vismaz viens no laukiem **Vārds, uzvārds un adrese**, **Tālruņa numurs** vai **E-pasts**.

1. Atlasiet **Tālāk**

1. Kartējiet savus laukus uz uzņēmuma datiem no Dun & Bradstreet. Nepieciešams vai nu **DUNS numurs**, vai **uzņēmuma** nosaukums un **valsts**.

      :::image type="content" source="media/enrichment-dnb-mapping.png" alt-text="Dun & Bradstreet lauku kartēšanas rūts.":::

1. Lai pabeigtu lauka kartēšanu, atlasiet **Tālāk**.

1. **Norādiet bagātināšanas nosaukumu** un entītijas **Izvade nosaukumu**.

1. Pēc izvēļu pārskatīšanas atlasiet **Saglabāt bagātināšanu**.

1. Atlasiet **Palaist**, lai sāktu bagātināšanas procesu, vai tuvu, lai **atgrieztos lapā Bagātinājumi**.

## <a name="enrichment-results"></a>Bagātināšanas rezultāti

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

## <a name="next-steps"></a>Nākamās darbības

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE[footer-include](includes/footer-banner.md)]
