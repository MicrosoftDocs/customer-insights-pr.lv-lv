---
title: Instalējiet un konfigurējiet klienta kartes pievienojumprogrammu
description: Instalējiet un konfigurējiet klienta kartes pievienojumprogrammu programmai Dynamics 365 Customer Insights.
ms.date: 01/20/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: a6d5b49380ed129cf147698a16f5f3f597bf7fbc
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268053"
---
# <a name="customer-card-add-in-preview"></a>Klienta kartes pievienojumprogramma (priekšskatījums)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Iegūstiet pilnu ainu par saviem klientiem tieši risinājuma Dynamics 365 programmās. Izmantojot klienta kartes pievienojumprogrammu, skatiet demogrāfiskos datus, ieskatus un darbību laika skalas.

## <a name="prerequisites"></a>Priekšnosacījumi

- Dynamics 365 programma (piemēram, Pārdošanas centrs vai Klientu apkalpošanas centrs), versija 9.0 vai jaunāka ar iespējotu vienoto interfeisu.
- Klientu profili [iegūti programmā Dynamics 365, izmantojot programmu Common Data Service](connect-power-query.md).
- Klienta kartes pievienojumprogrammas lietotājiem ir jābūt [pievienotam kā lietotājiem](permissions.md) auditorijas ieskatiem.
- [Konfigurētas meklēšanas un filtrēšanas iespējas](search-filter-index.md).
- Demogrāfiskā kontrole: demogrāfiskie lauki (piemēram, vecums vai dzimums) ir pieejami vienotajā klienta profilā.
- Bagātināšanas vadīkla: Ir nepieciešama aktīva [bagātināšana](enrichment-hub.md), ko piemērot klientu profiliem.
- Intelekta kontrolēšana: Nepieciešami dati, kas ģenerēti, izmantojot Azure algoritmisko mācīšanos ([Prognozes](predictions.md) vai [Pielāgotus modeļus](custom-models.md))
- Mērīt vadīklu: Nepieciešamas [konfigurētās mērvienības](measures.md).
- Laika skalas vadīkla: Nepieciešamas [konfigurētās darbības](activities.md).

## <a name="install-the-customer-card-add-in"></a>Klienta kartes pievienojumprogrammas instalēšana

Klienta kartes pievienojumprogramma ir risinājums klientu iesaistes programmām pakalpojumā Dynamics 365. Lai instalētu šo risinājumu, dodieties uz AppSource un meklējiet **Dynamics Customer Card**. Atlasiet [Klienta kartes pievienojumprogramma pakalpojumā AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) un atlasiet **Iegūt to tūlīt**.

Lai Dynamics 365 programma instalētu risinājumu, jums, iespējams, vajadzēs pieteikties ar saviem administratora akreditācijas datiem.

Var paiet zināms laiks, līdz risinājums tiks instalēts jūsu vidē.

## <a name="configure-the-customer-card-add-in"></a>Klienta kartes pievienojumprogrammas konfigurēšana

1. Kā administrators atveriet sadaļu **Iestatījumi** pakalpojumā Dynamics 365 un atlasiet **Risinājumi**.

1. Atlasiet saiti **Parādāmais nosaukums** risinājumam **Dynamics 365 Customer Insights klienta kartes pievienojumprogramma (priekšskatījums)**.

   > [!div class="mx-imgBorder"]
   > ![Parādāmā nosaukuma atlasīšana](media/select-display-name.png "Parādāmā nosaukuma atlasīšana")

1. Atlasiet **Pierakstīties** un ievadiet tā administratora konta akreditācijas datus, ko izmantojat, lai konfigurētu Customer Insights.

   > [!NOTE]
   > Pārbaudiet, vai, atlasot pogu **Pierakstīties**, pārlūkprogrammas uznirstošo elementu bloķētājs nebloķē autentifikācijas logu.

1. Atlasiet vidi, no kuras vēlaties izgūt datus.

1. Definējiet, kuru lauku kartējumu uz ierakstiem Dynamics 365 lietojumprogrammā.
   - Lai kartētu ar kontaktpersonu, atlasiet klientu entītijas lauku, kas atbilst jūsu kontaktpersonas entītijas ID.
   - Lai kartētu ar kontaktpersonu, atlasiet klientu entītijas lauku, kas atbilst jūsu konta entītijas ID.

   > [!div class="mx-imgBorder"]
   > ![Lauks Kontaktpersonas ID](media/contact-id-field.png "Lauks Kontaktpersonas ID")

1. Atlasiet **Saglabāt konfigurāciju**, lai saglabātu iestatījumus.

1. Pēc tam risinājumā Dynamics 365 ir jāpiešķir drošības lomas, lai lietotāji varētu pielāgot un apskatīt klienta karti. Programmā Dynamics 365 atveriet sadaļu **Iestatījumi** > **Drošība** > **Lietotāji**. Atlasiet lietotājus, lai rediģētu lietotāju lomas, un atlasiet **Pārvaldīt lomas**.

1. Piešķiriet lomu **Customer Insights kartes pielāgotājs** lietotājiem, kuri visai organizācijai pielāgos kartē rādāmo saturu.

## <a name="add-customer-card-controls-to-forms"></a>Klienta karšu vadīklu pievienošana veidlapām
  
1. Lai savai kontaktpersonas veidlapai pievienotu klienta kartes vadīklas, dodieties uz **Iestatījumi** > **Pielāgojumi** risinājumā Dynamics 365.

1. Atlasiet **Pielāgot sistēmu**.

1. Pārejiet uz entītiju **Kontaktpersona**, izvērsiet to un pēc tam atlasiet **Veidlapas**.

1. Atlasiet kontaktpersonas veidlapu, kurai vēlaties pievienot klienta kartes vadīklas.

    > [!div class="mx-imgBorder"]
    > ![Kontaktpersonas veidlapas atlase](media/contact-active-forms.png "Kontaktpersonas veidlapas atlase")

1. Lai pievienotu vadīklu, veidlapu redaktorā velciet jebkuru lauku no **lauku pārlūka** uz vietu, kur vēlaties novietot vadīklu.

1. Atlasiet tikko pievienoto lauku veidlapā un atlasiet **Mainīt rekvizītus**.

1. Dodieties uz cilni **Vadīklas** un atlasiet **Pievienot vadīklu**. Izvēlieties vienu no pieejamajām pielāgotajām vadīklām un atlasiet **Pievienot**.

1. Dialoglodziņā **Lauka rekvizīti** notīriet izvēles rūtiņu **Rādīt etiķeti veidlapā**.

1. Vadīklai atlasiet opciju **Tīmeklis**. Bagātināšanas vadīklai atlasiet, kuru bagātināšanas veidu vēlaties rādīt, konfigurējot lauku **enrichmentType**. Katram bagātināšanas tipam pievienojiet atsevišķu bagātināšanas vadīklu.

1. Atlasiet **Saglabāt** un **Publicēt**, lai publicētu atjaunināto kontaktpersonas veidlapu.

1. Atveriet publicēto kontaktpersonas veidlapu. Tiek parādīta tikko pievienotā vadīkla. Iespējams, pirmajā lietošanas reizē būs jāpierakstās.

1. Lai pielāgotu pielāgotajā vadīklā rādāmo informāciju, augšējā labajā stūrī atlasiet rediģēšanas pogu.

## <a name="upgrade-customer-card-add-in"></a>Klienta kartes pievienojumprogrammas jaunināšana
Klienta kartes pievienojumprogramma netiek automātiski jaunināta. Lai jauninātu uz jaunāko versiju, izpildiet šo procedūru programmā Dynamics 365, kurā ir instalēta pievienojumprogramma.

1. Programmā Dynamics 365 dodieties uz **Iestatījumi** > **Pielāgošana** un atlasiet **Risinājumi**.

1. Pievienojumprogrammu tabulā atrodiet **CustomerInsightsCustomerCard** un atlasiet rindu.

1. Darbību joslā atlasiet **Lietot risinājuma jaunināšanu**.

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Risinājuma jaunināšana Dynamics 365 programmu Pielāgošanas apgabalā":::

1. Pēc jaunināšanas procesa sākšanas tiek rādīts ielādes rādītājs, līdz jaunināšana ir pabeigta. Ja tajā nav jaunākas versijas, jaunināšanai tiks rādīts kļūdas ziņojums.


[!INCLUDE[footer-include](../includes/footer-banner.md)]