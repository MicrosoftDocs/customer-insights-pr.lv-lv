---
title: Customer Card pievienojumprogramma Dynamics 365 programmām (priekšskatījums) (satur video)
description: Parādiet klienta profila datus no Customer Insights Dynamics 365 programmās, izmantojot šo pievienojumprogrammu.
ms.date: 02/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
searchScope:
- ci-customers-page
- ci-search-filter
- ci-customer-card
- customerInsights
ms.openlocfilehash: 65fd80cc563b8b3b8c8874b66f179f8b0c7a19f0
ms.sourcegitcommit: fe33cc76d015232ff8737f77193f44f2b884bb6b
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 09/13/2022
ms.locfileid: "9473651"
---
# <a name="customer-card-add-in-for-dynamics-365-apps-preview"></a>Klienta kartes pievienojumprogramma Dynamics 365 programmām (priekšskatījums)

Iegūstiet pilnu ainu par saviem klientiem tieši risinājuma Dynamics 365 programmās. Kad klienta kartītes pievienojumprogramma ir instalēta atbalstītajā Dynamics 365 programmā, varat izvēlēties rādīt klientu profila laukus, ieskatus un darbību laika grafiku. Pievienojumprogramma izgūs datus no programmas Customer Insights, neietekmējot pievienotās Dynamics 365 programmas datus.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN1qv]

## <a name="prerequisites"></a>Priekšnoteikumi

- Dynamics 365 modeļa vadītas programmas, piemēram, Sales vai klientu apkalpošana, versija 9.0 un jaunākas versijas.
- Lai jūsu Dynamics 365 dati tiktu kartēti uz Customer Insights klientu profiliem, ieteicams tos [uzņemt no Dynamics 365 programmas, izmantojot savienotāju Microsoft Dataverse](connect-power-query.md). Ja izmantojat citu metodi, lai uzņemtu Dynamics 365 kontaktpersonas (vai kontus), pārliecinieties `contactid`, vai lauks (vai`accountid`) ir iestatīts kā [primārā atslēga šim datu avots datu apvienošanas procesa laikā](map-entities.md#select-primary-key-and-semantic-type-for-attributes).
- Lai skatītu datus, visiem Dynamics 365 pievienojumprogrammas Customer Card lietotājiem programmā Customer Insights ir jābūt [pievienotiem kā lietotājiem](permissions.md).
- [Konfigurētās meklēšanas un filtrēšanas iespējas](search-filter-index.md) programmā Customer Insights.
- Daži dati un vadīklas ir pieejamas tikai īpašu tipu vidēs. Pievienojumprogrammas konfigurācija informēs jūs, ja vadīkla nav pieejama atlasītā vides tipa dēļ. Šī kļūda tiks parādīta vadīklā, to atveidojot. Uzziniet vairāk par [vides izmantošanas gadījumiem](work-with-business-accounts.md).
- Katra pievienojumprogrammas vadīkla balstās uz konkrētiem datiem programmā Customer Insights.
  - **Mērīšanas vadīklai** ir nepieciešami [konfigurēti klienta atribūtu mēri](measures.md).
  - **Izlūkošanas kontrolei** ir nepieciešami dati, kas ģenerēti, izmantojot [prognozes vai pielāgotus modeļus](predictions-overview.md).
  - **Klienta detalizētas informācijas vadīkla** parāda visus laukus no profila, kas pieejams vienotajā klienta profilā.
  - **Bagātināšanas kontrolei** nepieciešama aktīva [bagātināšana](enrichment-hub.md), ko piemēro klientu profiliem. Kartes pievienojumprogramma atbalsta šos bagātinājumus: [Microsoft nodrošinātie zīmoli](enrichment-microsoft.md), [Microsoft nodrošinātie intereses](enrichment-microsoft.md) un [Microsoft nodrošinātie Office iesaistes dati](enrichment-office.md).
  - **Kontaktpersonu kontrolei** ir nepieciešams kontakta semantiskās entītijas tips.
  - **Laika grafika kontrolei** ir nepieciešamas [konfigurētas darbības](activities.md).

## <a name="install-the-customer-card-add-in"></a>Klienta kartes pievienojumprogrammas instalēšana

Klienta kartes pievienojumprogramma ir risinājums klientu iesaistes programmām pakalpojumā Dynamics 365. Lai instalētu risinājumu:

1. Dodieties uz AppSource Dynamics klienta karti **un meklējiet to**.

1. Atlasiet [Klienta kartes pievienojumprogramma pakalpojumā AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) un atlasiet **Iegūt to tūlīt**.

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

Atkarībā no scenārija varat izvēlēties pievienot vadīklas veidlapai **Kontaktpersona** vai veidlapai **Uzņēmums**. Ja jūsu Customer Insights vide ir paredzēta uzņēmumu kontiem, ieteicams šīs vadīklas pievienot veidlapai Konts. Šādā gadījumā nākamajās darbībās "kontaktpersona" aizstājiet ar "uzņēmumu."

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

## <a name="troubleshooting"></a>Problēmu novēršana

### <a name="controls-from-customer-card-add-in-dont-find-data"></a>Vadīklas no customer card pievienojumprogrammas neatrod datus

**Problēma:**

Pat ar pareizi konfigurētiem ID laukiem vadīklas nevar atrast datus nevienam klientam.  

**Risinājums**

1. Pārliecinieties, vai esat konfigurējis kartes pievienojumprogrammu saskaņā ar instrukcijām: [Klienta kartes pievienojumprogrammas konfigurēšana](#configure-the-customer-card-add-in)

1. Pārskatiet datu uzņemšanas konfigurāciju. Rediģējiet dynamics 365 sistēmas datu avots, kurā ir kontaktpersonas ID GUID. Ja redaktorā kontaktpersonas ID GUID tiek rādīts ar lielajiem burtiem Power Query, mēģiniet veikt šādas darbības:
    1. Rediģējiet datu avots, lai datu avots atvērtu redaktorā Power Query.
    1. Atlasiet kolonnu kontaktpersonas ID.
    1. Galvenes joslā atlasiet **Transformēt**, lai skatītu pieejamās darbības.
    1. Atlasiet **mazos burtus**. Pārbaudiet, vai tabulā norādītie GUID tagad ir ar mazajiem burtiem.
    1. Saglabājiet datu avotu.
    1. Palaidiet datu norīšanas, apvienošanas un pakārtotos procesus, lai izplatītu GUID izmaiņas.

Kad sistēma ir pabeigusi pilnu atsvaidzināšanu, customercard pievienojumprogrammas vadīklās ir jāparāda paredzamie dati.

[!INCLUDE [footer-include](includes/footer-banner.md)]
