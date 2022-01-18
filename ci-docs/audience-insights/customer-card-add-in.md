---
title: Klienta kartes pievienojumprogramma Dynamics 365 programmām (satur video)
description: Rādīt auditorijas ieskatu datus Dynamics 365 programmās, izmantojot šo pievienojumprogrammu.
ms.date: 12/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: 3927b5a13a5f9b4d2b39c7f0b389bc51cafeb213
ms.sourcegitcommit: 3811dede65946c37aa7ed3cc364251f20ffd4d17
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 12/22/2021
ms.locfileid: "7945436"
---
# <a name="customer-card-add-in-preview"></a>Klienta kartes pievienojumprogramma (priekšskatījums)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Iegūstiet pilnu ainu par saviem klientiem tieši risinājuma Dynamics 365 programmās. Kad klienta kartītes pievienojumprogramma ir instalēta atbalstītajā Dynamics 365 programmā, varat izvēlēties rādīt klientu profila laukus, ieskatus un darbību laika grafiku. Pievienojumprogramma izgūs datus no programmas Customer Insights, neietekmējot pievienotās Dynamics 365 programmas datus.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN1qv]

## <a name="prerequisites"></a>Priekšnosacījumi

- Pievienojumprogramma darbojas tikai ar Dynamics 365 modeļa vadītām programmām, piemēram, Sales vai Customer Service versiju 9.0 un jaunāku versiju.
- Lai jūsu Dynamics 365 dati kartētu uz auditorijas ieskatu klientu profiliem, ieteicams tos [uzņemt no Dynamics 365 programmas, izmantojot Microsoft Dataverse savienotāju](connect-power-query.md). Ja izmantojat citu metodi, lai uzņemtu Dynamics 365 kontaktpersonas (vai uzņēmumus), jums `contactid` jāpārliecinās, vai lauks (vai ) ir `accountid` iestatīts kā šīs datu avots primārā [atslēga datu apvienošanas procesa kartes posmā](map-entities.md#select-primary-key-and-semantic-type-for-attributes). 
- Visi Dynamics 365 lietotāji, kas izmanto klienta kartes pievienojumprogrammu, ir [jāpievieno kā lietotāji](permissions.md) auditorijas ieskatos, lai redzētu datus.
- Lai darbotos datu uzmeklēšana, ir nepieciešama [konfigurēta meklēšanas un filtrēšanas iespēja](search-filter-index.md) auditorijas ieskatos.
- Katra pievienojumprogrammas vadīkla ir atkarīga no noteiktiem datiem auditorijas ieskatos. Daži dati un vadīklas ir pieejamas tikai īpašu tipu vidēs. Pievienojumprogrammas konfigurācija jūs informēs, ja atlasītā vides tipa dēļ vadīkla nav pieejama. Uzziniet vairāk par [vides izmantošanas gadījumiem](work-with-business-accounts.md).
  - **Mērvienību vadīkla**: ir nepieciešami [konfigurēti klienta atribūtu](measures.md) tipa pasākumi.
  - **Informācijas kontrole** : pieprasa datus, kas ģenerēti, izmantojot prognozes vai [pielāgotus modeļus](predictions-overview.md).
  - **Klienta detalizētās informācijas vadīkla**: visi šī profila lauki ir pieejami vienotā klienta profilā.
  - **Bagātināšanas vadīkla**: Ir nepieciešama aktīva [bagātināšana](enrichment-hub.md), ko piemērot klientu profiliem. Kartes pievienojumprogramma atbalsta šīs bagātināšanas: [Korporācijas](enrichment-microsoft.md) Microsoft nodrošinātie zīmoli, [Microsoft nodrošinātās intereses](enrichment-microsoft.md) un Microsoft [nodrošinātie Office iesaistes](enrichment-office.md) dati.
  - **Kontaktpersonu vadīkla**: nepieciešama kontaktpersonu tipa semantiskās entītijas definīcija.
  - **Laika skalas vadīkla**: Nepieciešamas [konfigurētās darbības](activities.md).

## <a name="install-the-customer-card-add-in"></a>Klienta kartes pievienojumprogrammas instalēšana

Klienta kartes pievienojumprogramma ir risinājums klientu iesaistes programmām pakalpojumā Dynamics 365. Lai instalētu šo risinājumu, dodieties uz AppSource un meklējiet **Dynamics Customer Card**. Atlasiet [Klienta kartes pievienojumprogramma pakalpojumā AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) un atlasiet **Iegūt to tūlīt**.

Lai Dynamics 365 programma instalētu risinājumu, jums, iespējams, vajadzēs pieteikties ar saviem administratora akreditācijas datiem. Var paiet zināms laiks, līdz risinājums tiks instalēts jūsu vidē.

## <a name="configure-the-customer-card-add-in"></a>Klienta kartes pievienojumprogrammas konfigurēšana

1. Kā administrators atveriet sadaļu **Iestatījumi** pakalpojumā Dynamics 365 un atlasiet **Risinājumi**.

1. Atlasiet saiti **Parādāmais nosaukums** risinājumam **Dynamics 365 Customer Insights klienta kartes pievienojumprogramma (priekšskatījums)**.

   > [!div class="mx-imgBorder"]
   > ![Parādāmā nosaukuma atlasīšana.](media/select-display-name.png "Parādāmā nosaukuma atlasīšana.")

1. Atlasiet **Pierakstīties** un ievadiet tā administratora konta akreditācijas datus, ko izmantojat, lai konfigurētu Customer Insights.

   > [!NOTE]
   > Pārbaudiet, vai, atlasot pogu **Pierakstīties**, pārlūkprogrammas uznirstošo elementu bloķētājs nebloķē autentifikācijas logu.

1. Atlasiet Customer Insights vidi, no kuras vēlaties izgūt datus.

1. Definējiet lauku kartējumu ierakstiem Dynamics 365 programmā. Atkarībā no datiem programmā Customer Insights varat izvēlēties kartēt šādas opcijas:
   - Lai kartētu ar kontaktpersonu, atlasiet klientu entītijas lauku, kas atbilst jūsu kontaktpersonas entītijas ID.
   - Lai kartētu ar kontaktpersonu, atlasiet klientu entītijas lauku, kas atbilst jūsu konta entītijas ID.

   > [!div class="mx-imgBorder"]
   > ![Lauks Kontaktpersonas ID.](media/contact-id-field.png "Lauks Kontaktpersonas ID.")

1. Atlasiet **Saglabāt konfigurāciju**, lai saglabātu iestatījumus.

1. Pēc tam risinājumā Dynamics 365 ir jāpiešķir drošības lomas, lai lietotāji varētu pielāgot un apskatīt klienta karti. Programmā Dynamics 365 atveriet sadaļu **Iestatījumi** > **Drošība** > **Lietotāji**. Atlasiet lietotājus, lai rediģētu lietotāju lomas, un atlasiet **Pārvaldīt lomas**.

1. Piešķiriet lomu **Customer Insights kartes pielāgotājs** lietotājiem, kuri visai organizācijai pielāgos kartē rādāmo saturu.

## <a name="add-customer-card-controls-to-forms"></a>Klienta karšu vadīklu pievienošana veidlapām

Atkarībā no scenārija varat izvēlēties pievienot vadīklas veidlapai **Kontaktpersona** vai veidlapai **Uzņēmums**. Ja auditorijas ieskatu vide ir biznesa uzņēmumiem, ieteicams vadīklas pievienot veidlapai Uzņēmums. Šādā gadījumā nākamajās darbībās "kontaktpersona" aizstājiet ar "uzņēmumu."

1. Lai savai kontaktpersonas veidlapai pievienotu klienta kartes vadīklas, dodieties uz **Iestatījumi** > **Pielāgojumi** risinājumā Dynamics 365.

1. Atlasiet **Pielāgot sistēmu**.

1. Pārejiet uz entītiju **Kontaktpersona**, izvērsiet to un pēc tam atlasiet **Veidlapas**.

1. Atlasiet kontaktpersonas veidlapu, kurai vēlaties pievienot klienta kartes vadīklas.

    > [!div class="mx-imgBorder"]
    > ![Kontaktpersonas veidlapas atlase.](media/contact-active-forms.png "Kontaktpersonas veidlapas atlase.")

1. Lai pievienotu vadīklu, veidlapu redaktorā velciet jebkuru lauku no **lauku pārlūka** uz vietu, kur vēlaties novietot vadīklu.

1. Atlasiet tikko pievienoto lauku veidlapā un atlasiet **Mainīt rekvizītus**.

1. Dodieties uz cilni **Vadīklas** un atlasiet **Pievienot vadīklu**. Izvēlieties vienu no pieejamajām pielāgotajām vadīklām un atlasiet **Pievienot**.

1. Dialoglodziņā **Lauka rekvizīti** notīriet izvēles rūtiņu **Rādīt etiķeti veidlapā**.

1. Vadīklai atlasiet opciju **Tīmeklis**. Bagātināšanas vadīklai atlasiet, kuru bagātināšanas veidu vēlaties rādīt, konfigurējot lauku **enrichmentType**. Katram bagātināšanas tipam pievienojiet atsevišķu bagātināšanas vadīklu.

1. Atlasiet **Saglabāt** un **Publicēt**, lai publicētu atjaunināto kontaktpersonas veidlapu.

1. Atveriet publicēto kontaktpersonas veidlapu. Tiek parādīta tikko pievienotā vadīkla. Iespējams, pirmajā lietošanas reizē būs jāpierakstās.

1. Lai pielāgotu pielāgotajā vadīklā rādāmo informāciju, augšējā labajā stūrī atlasiet rediģēšanas pogu.

## <a name="upgrade-customer-card-add-in"></a>Klienta kartes pievienojumprogrammas jaunināšana

Klienta kartes pievienojumprogramma netiek automātiski jaunināta. Lai jauninātu uz jaunāko versiju, veiciet šīs darbības Dynamics 365 programmā, kurā ir instalēta pievienojumprogramma.

1. Programmā Dynamics 365 dodieties uz **Iestatījumi** > **Pielāgošana** un atlasiet **Risinājumi**.

1. Pievienojumprogrammu tabulā atrodiet **CustomerInsightsCustomerCard** un atlasiet rindu.

1. Darbību joslā atlasiet **Lietot risinājuma jaunināšanu**.

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Risinājuma jaunināšana Dynamics 365 programmu Pielāgošanas apgabalā.":::

1. Pēc jaunināšanas procesa sākšanas tiek rādīts ielādes rādītājs, līdz jaunināšana ir pabeigta. Ja tajā nav jaunākas versijas, jaunināšanai tiks rādīts kļūdas ziņojums.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
