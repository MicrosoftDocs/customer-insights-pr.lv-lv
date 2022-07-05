---
title: Bagātiniet uzņēmuma profilus ar Dun & Bradstreet (priekšskatījums)
description: Vispārīga informācija par Dun & Bradstreet trešās puses bagātināšanu.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 51f2e4e46aa25d10502d0feb5ea42eb7d2d637b9
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082557"
---
# <a name="enrich-company-profiles-with-dun--bradstreet-preview"></a>Bagātiniet uzņēmuma profilus ar Dun & Bradstreet (priekšskatījums)

Dun & Bradstreet nodrošina komerciālus datus, analītiku un ieskatus uzņēmumiem. Tā nodrošina klientiem vienotus klientu profilus, lai uzņēmumi bagātinātu datus. Bagātināšana ietver tādus atribūtus kā DUNS numurs, uzņēmuma lielums, atrašanās vieta, nozare un citi.

## <a name="prerequisites"></a>Priekšnoteikumi

- Aktīva [Dun & Bradstreet](https://www.dnb.com/marketing/media/give-your-data-a-boost.html?source=microsoft_audience_insights) licence.
- [Vienoti](customer-profiles.md) klientu profili uzņēmumiem.
- Tiek izveidots Dun & Bradstreet [projekts](#set-up-your-dun--bradstreet-project).
- Dun &Bradstreet [savienojumu](connections.md)[konfigurē](#configure-a-connection-for-dun--bradstreet) administrators.

## <a name="set-up-your-dun--bradstreet-project"></a>Iestatiet savu Dun & Bradstreet projektu

Kā licencēts Dun &Bradstreet lietotājs jūs varat iestatīt projektu Dun [& Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights).

1. [piesakieties Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights). Lai izgūtu akreditācijas datus, [atjaunojiet paroli](https://sso.dnb.com/signin/forgot-password?lead_source=microsoft_audienceinsights).

1. Lejupielādējiet [mūsu csv veidnes failu](https://c360devenrichment.blob.core.windows.net/mapping/DnBCIdatamapping.csv), kas tiks izmantots, lai kartētu Customer Insights laukus uz atbilstošajiem Dun &Bradstreet laukiem.

1. Augšupielādējiet failu **Dun &Bradstreet projekta izveides pieredzes datu** augšupielādes solī.

1. Atlasiet horizontālos punktus zem attiecīgā **avota** jaunizveidotajā Dun & Bradstreet projektā, lai skatītu pieejamās opcijas.

   :::image type="content" source="media/enrichment-dnb-dots.png" alt-text="Ekrānuzņēmums ar punktiem Dun & Bradstreet projektā.":::

1. Izvēlieties **Iegūt S3 detaļas**. Glabājiet šo informāciju drošā vietā. Tas būs nepieciešams, lai [iestatītu savienojumu bagātināšanai](#configure-a-connection-for-dun--bradstreet) programmā Customer Insights.

   :::image type="content" source="media/enrichment-dnb-s3info.png" alt-text="Ekrānuzņēmums, kurā redzama s3 informācijas atlase Dun &Bradstreet projektā.":::

## <a name="configure-a-connection-for-dun--bradstreet"></a>Dun &Bradstreet savienojuma konfigurēšana

Jums ir jābūt Customer Insights [administratoram](permissions.md#admin), un jums ir jābūt Dun &Bradstreet Connect akreditācijas datiem.

1. Atlasiet **Pievienot savienojumu**, konfigurējot bagātināšanu, vai dodieties uz **Administratoru** > **savienojumi** un dun &bradstreet elementā atlasiet **Iestatīt**.

1. Ievadiet savienojuma nosaukumu.

1. Norādiet derīgus Dun &Bradstreet akreditācijas datus un Dun &Bradstreet projekta informāciju reģions *, mapes nomešanas ceļš un mapes nosaukums* nomešana. Jūs [saņemat šo informāciju](#set-up-your-dun--bradstreet-project) no Dun & Bradstreet projekta.

1. Pārskatiet un sniedziet savu piekrišanu [Datu konfidencialitātei un atbilstībai](#data-privacy-and-compliance), atlasot **Es piekrītu**.

1. Atlasiet **Verificēt**, lai validētu konfigurāciju, un pēc tam atlasiet **Saglabāt**.

   :::image type="content" source="media/enrichment-dnb-connection.png" alt-text="Dun &Bradstreet savienojuma konfigurācijas lapa.":::

### <a name="data-privacy-and-compliance"></a>Datu konfidencialitāte un atbilstība

Kad jūs iespējojat Dynamics 365 Customer Insights datu pārsūtīšanu uz Dun &Bradstreet, jūs atļaujat pārsūtīt datus ārpus atbilstības robežas, tostarp potenciāli sensitīvus Dynamics 365 Customer Insights datus, piemēram, personas datus. Microsoft pārsūtīs šādus datus pēc jūsu norādījumiem, taču jūs esat atbildīgs par to, lai Dun &Bradstreet izpildītu visas jūsu iespējamās konfidencialitātes vai drošības saistības. Papildinformāciju skatiet rakstā [Microsoft Privātuma paziņojums](https://go.microsoft.com/fwlink/?linkid=396732).
Jūsu Dynamics 365 Customer Insights administrators var noņemt šo bagātināšanas funkciju jebkurā laikā, lai pārtrauktu šīs funkcijas izmantošanu.

## <a name="supported-countries-or-regions"></a>Atbalstītās valstis vai reģioni

Pašlaik mēs atbalstām šādas valsts/reģiona opcijas: Kanāda (angļu valodā) vai Amerikas Savienotās Valstis (angļu valodā).

## <a name="configure-the-enrichment"></a>Bagātināto datu konfigurēšana

1. Dodieties uz **Dati** > **Bagātināšana** un atlasiet cilni **Atklāt**.

1. Atlasiet **Bagātināt manus datus**, izmantojot **uzņēmuma datus** elementam Dun &Bradstreet.

   :::image type="content" source="media/enrichment-dnb-tile.png" alt-text="Dun & Bradstreet elementa ekrānuzņēmums.":::

1. Pārskatiet pārskatu un pēc tam atlasiet **Tālāk**.

1. Atlasiet savienojumu un apstipriniet. Sazinieties ar administratoru, ja tāds nav pieejams.

1. Atlasiet **Tālāk**.

1. **Atlasiet klientu datu kopu** un izvēlieties profilu vai segmentu, kuru vēlaties bagātināt ar uzņēmuma datiem no Dun &Bradstreet. Klienta *entītija* bagātina visus jūsu klientu profilus, savukārt segments bagātina tikai šajā segmentā ietvertos klientu profilus.

1. Definējiet, kāda veida laukus no saviem vienotajiem profiliem izmantot, lai saskaņotu uzņēmuma datus no Dun &Bradstreet. Ir obligāti jānorāda vismaz viens no laukiem **Vārds, uzvārds un adrese**, **Tālruņa numurs** vai **E-pasts**.

1. Atlasiet **Tālāk**

1. Kartējiet savus laukus uz uzņēmuma datiem no Dun &Bradstreet. Ir nepieciešams vai nu **DUNS numurs**, vai **uzņēmuma nosaukums** un **valsts** lauki.

      :::image type="content" source="media/enrichment-dnb-mapping.png" alt-text="Dun & Bradstreet lauku kartēšanas rūts.":::

1. Lai pabeigtu lauka kartēšanu, atlasiet **Tālāk**.

1. **Norādiet bagātināšanas nosaukumu** un izvades entītijas **nosaukumu**.

1. Pēc izvēļu pārskatīšanas atlasiet **Saglabāt bagātināšanu**.

1. Atlasiet **Palaist**, lai sāktu bagātināšanas procesu, vai aizveriet, lai **atgrieztos bagātināšanas** lapā.

## <a name="view-enrichment-results"></a>Bagātināšanas rezultātu skatīšana

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

## <a name="next-steps"></a>Nākamās darbības

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE[footer-include](includes/footer-banner.md)]
