---
title: Uzņēmuma profilu bagātināšana ar Dun & Bradstreet
description: Vispārīga informācija par Dun & Bradstreet trešo pušu bagātināšanu.
ms.date: 04/26/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: ecbbf2c94020bf395f4eb70a99a63cea335af2dd
ms.sourcegitcommit: cf74b8c20d88eb96e1ac86e18cd44fe27aad5ab9
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 04/28/2022
ms.locfileid: "8653797"
---
# <a name="enrichment-of-company-profiles-with-dun--bradstreet-preview"></a>Uzņēmuma profilu bagātināšana ar Dun & Bradstreet (priekšskatījums)

Dun & Bradstreet nodrošina komerciālus datus, analīzi un ieskatus uzņēmumiem. Tā nodrošina klientiem vienotus klientu profilus, lai uzņēmumi bagātinātu datus. Bagātināšana ietver tādus atribūtus kā DUNS numurs, uzņēmuma lielums, atrašanās vieta, nozare un daudz kas cits.

## <a name="prerequisites"></a>Priekšnoteikumi

Lai konfigurētu Dun & Bradstreet bagātināšanu, jāievēro šādi priekšnosacījumi:

- Jums ir aktīva [Dun & Bradstreet](https://www.dnb.com/marketing/media/give-your-data-a-boost.html?source=microsoft_audience_insights) licence.
- Jums ir [vienoti klientu profili](customer-profiles.md) uzņēmumiem.
- Dun & Bradstreet [savienojumu](connections.md) konfigurē administrators. Varat to izveidot, ja jums ir [administratora](permissions.md#admin) atļaujas un Dun & Bradstreet Connect akreditācijas dati. 

## <a name="setting-up-your-dun--bradstreet-project"></a>Dun & Bradstreet projekta iestatīšana

Kā licencēts Dun & Bradstreet lietotājs varat izveidot projektu [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights). 


1. Piesakieties [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights). Lai izgūtu akreditācijas datus, [atjaunojiet paroli](https://sso.dnb.com/signin/forgot-password?lead_source=microsoft_audienceinsights).

1. Lejupielādējiet [mūsu csv veidnes failu](https://c360devenrichment.blob.core.windows.net/mapping/DnBCIdatamapping.csv), kas tiks izmantots, lai kartētu auditorijas ieskatu laukus uz atbilstošajiem Dun & Bradstreet laukiem. 

1. Augšupielādējiet failu **Dun & Bradstreet projekta izveides pieredzes augšupielādes datu** solī. 

1. Atlasiet horizontālos punktus zem atbilstošā **avota** jaunizveidotajā Dun & Bradstreet projektā, lai skatītu pieejamās opcijas.

   :::image type="content" source="media/enrichment-dnb-dots.png" alt-text="Ekrānuzņēmums ar punktiem Dun & Bradstreet projektā.":::

1. Izvēlieties **Iegūt detalizētu informāciju par** S3. Glabājiet šo informāciju drošā vietā. Jums tas būs nepieciešams, lai [iestatītu savienojumu auditorijas ieskatu bagātināšanai](#configure-a-connection-for-dun--bradstreet). 

   :::image type="content" source="media/enrichment-dnb-s3info.png" alt-text="Ekrānuzņēmums, kurā redzama s3 informācijas izlase Dun & Bradstreet projektā.":::



## <a name="configure-the-enrichment"></a>Bagātināto datu konfigurēšana

1. Sadaļā Auditorijas ieskati skatiet **Dati** > **Darbības**.

1. Atlasiet **Bagātināt manus datus** dun & Bradstreet flīzē un atlasiet **Sākt darbu**.

   :::image type="content" source="media/enrichment-dnb-tile.png" alt-text="Dun & Bradstreet flīzes ekrānuzņēmums.":::

1. Atlasiet [savienojumu](connections.md) nolaižamajā sarakstā. Ja nav pieejamu savienojumu, sazinieties ar administratoru. Ja esat administrators, varat izveidot savienojumu. Atlasiet **Pievienot savienojumu** un izvēlieties **Dun & Bradstreet**. 

1. Atlasiet **Izveidot savienojumu ar Dun & Bradstreet**, lai apstiprinātu savienojumu.

1. Atlasiet **Tālāk** un izvēlieties **klientu datu kopu**, kuru vēlaties bagātināt ar uzņēmuma datiem no Dun & Bradstreet. Varat atlasīt entītiju Klients **,** lai bagātinātu visus klientu profilus, vai atlasīt segmenta entītiju, lai bagātinātu tikai vienotus klientu profilus, kas atrodas šajā segmentā.

1. Atlasiet **Tālāk** un definējiet, kuri lauki no jūsu vienotajiem profiliem tiek izmantoti, lai meklētu atbilstošus uzņēmuma datus no Dun & Bradstreet. Nepieciešams vai nu **DUNS numurs**, vai **uzņēmuma nosaukums** un **valsts**. Lauks Valsts atbalsta [divu vai trīs burtu valstu kodus](https://www.iso.org/iso-3166-country-codes.html), valsts nosaukumu angļu valodā, valsts nosaukumu dzimtajā valodā un tālruņa prefiksu. Daži kopīgu valstu varianti ietver:

   * ASV: Amerikas Savienotās Valstis, Amerikas Savienotās Valstis, ASV, Amerika.
   * CA: Kanāda.
   * GB: Apvienotā Karaliste, Lielbritānija, Lielbritānija, GB, Lielbritānijas un Ziemeļīrijas Apvienotā Karaliste, Lielbritānijas Apvienotā Karaliste.
   * ĀM: Austrālija, Austrālijas Sadraudzība.
   * FR: Francija, Francijas Republika.
   * DE: Vācija, Vācija, Deutschland, Allemagne, Vācijas Federatīvā Republika, Vācijas Republika.

   :::image type="content" source="media/enrichment-dnb-mapping.png" alt-text="Dun & Bradstreet lauku kartēšanas rūts.":::

1. Lai pabeigtu lauka kartēšanu, atlasiet **Tālāk**.

1. Norādiet bagātināto datu nosaukumu un pēc izvēles pārskatīšanas atlasiet **Saglabāt bagātinātos datus**.


## <a name="configure-a-connection-for-dun--bradstreet"></a>Dun & Bradstreet savienojuma konfigurēšana 

Lai konfigurētu savienojumus, jums ir jābūt administratoram. Atlasiet **Pievienot savienojumu**, konfigurējot bagātināšanu *, vai* dodieties uz **AdminConnections** > **un** atlasiet **Iestatīt** uz elementa Dun & Bradstreet.

1. Atlasiet **Sākt**. 

1. Lodziņā **Parādāmais nosaukums** ievadiet savienojuma nosaukumu.

1. Norādiet derīgus Dun & Bradstreet akreditācijas datus un Dun & Bradstreet projekta detaļas *Reģions, Nometiet mapes ceļu un Nometiet mapes nosaukumu*. Jūs [saņemat šo informāciju](#setting-up-your-dun--bradstreet-project) no Dun & Bradstreet projekta.

1. Pārskatiet un sniedziet savu piekrišanu **Datu konfidencialitātei un atbilstībai**, atlasot **Es piekrītu**.

1. Lai pārbaudītu konfigurāciju, atlasiet **Pārbaudīt**.

1. Pēc pārbaudes pabeigšanas atlasiet **Saglabāt**.
   
   :::image type="content" source="media/enrichment-dnb-connection.png" alt-text="Dun & Bradstreet savienojuma konfigurācijas lapa.":::

## <a name="enrichment-results"></a>Bagātināšanas rezultāti

Pēc bagātināšanas atsvaidzināšanas varat apskatīt nesen papildinātā uzņēmuma datus [Mani papildinājumi](enrichment-hub.md). Varat atrast pēdējās atjaunināšanas laiku un bagātināto profilu skaitu.

Jūs varat piekļūt detalizētam katra bagātināta profila skatam, atlasot opciju **Skatīt bagātinātos datus**.

## <a name="next-steps"></a>Nākamās darbības

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Datu konfidencialitāte un atbilstība

Kad iespējojat Dynamics 365 Customer Insights pārsūtīt datus uz Dun & Bradstreet, jūs atļaujat pārsūtīt datus ārpus atbilstības robežas, tostarp potenciāli sensitīviem Dynamics 365 Customer Insights datiem, piemēram, Personas datiem. Microsoft pārsūtīs šādus datus pēc jūsu norādījumiem, taču jūs esat atbildīgs par to, lai Dun & Bradstreet izpildītu visas jūsu konfidencialitātes vai drošības saistības. Papildinformāciju skatiet rakstā [Microsoft Privātuma paziņojums](https://go.microsoft.com/fwlink/?linkid=396732).
Jūsu Dynamics 365 Customer Insights administrators var noņemt šo bagātināšanas funkciju jebkurā laikā, lai pārtrauktu šīs funkcijas izmantošanu.


[!INCLUDE[footer-include](includes/footer-banner.md)]
