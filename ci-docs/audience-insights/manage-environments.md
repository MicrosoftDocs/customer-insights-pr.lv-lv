---
title: Vižu izveide un pārvaldība
description: Uzziniet, kā pierakstīties pakalpojumā un kā pārvaldīt vides.
ms.date: 06/15/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 06310ea6fc72f26e21e185a6abcb5d19d4b201f6
ms.sourcegitcommit: e5425f060c8d80f9510283dc610ce70a4e709b1e
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 06/15/2021
ms.locfileid: "6259108"
---
# <a name="manage-environments"></a>Pārvaldīt vides

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Šajā rakstā ir paskaidrots, kā izveidot jaunu organizāciju un kā nodrošināt vidi.

## <a name="sign-up-and-create-an-organization"></a>Pierakstīšanās un organizācijas izveide

1. Dodieties uz [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/) tīmekļa vietni.

2. Atlasiet **Sākt**.

3. Izvēlieties vēlamo reģistrēšanās scenāriju un atlasiet atbilstošo saiti.

4. Piekrītiet noteikumiem un nosacījumiem un atlasiet **Turpināt**, lai sāktu organizācijas izveidi.

5. Pēc vides izveides jūs novirzīs uz [Customer Insights](https://home.ci.ai.dynamics.com).

6. Izmantojiet demonstrācijas vidi, lai iepazītu programmu vai izveidotu jaunu vidi, veicot nākamajā sadaļā norādītās darbības.

7. Pēc vides iestatījumu norādīšanas atlasiet **Izveidot**.

8. Jūs būsit pieteicies pēc vides sekmīgas izveides.

## <a name="create-an-environment-in-an-existing-organization"></a>Vides izveide esošā organizācijā

Pastāv divi veidi, ka izveidot jaunu vidi. Varat norādīt pilnīgi jaunu konfigurāciju vai arī var kopēt dažus konfigurācijas iestatījumus no esošas vides.

> [!NOTE]
> Organizācijas katrai Customer Insights licencei var izveidot *divas* vides. Ja jūsu organizācija iegādājas vairāk nekā vienu licenci, [sazinieties ar mūsu atbalsta komandu](https://go.microsoft.com/fwlink/?linkid=2079641), lai tiktu paaugstināts pieejamo vižu skaists. Papildinformāciju par noslodzi un pievienojumprogrammu noslodzi skatiet [Dynamics 365 licencēšanas rokasgrāmatā](https://go.microsoft.com/fwlink/?LinkId=866544).

Lai izveidotu vidi:

1. Programmas galvenē atlasiet **Vides** atlasītāju.

1. Atlasiet **Jauns**.

   > [!div class="mx-imgBorder"]
   > ![Vides iestatījumi](media/environment-settings-dialog.png)

1. Dialoglodziņā **Jaunas vides izveide** atlasiet **Jauna vide**.

   Ja vēlaties [kopēt datus no pašreizējās vides](#considerations-for-copy-configuration-preview), atlasiet **Kopēt no esošās vides**. Jūs redzēsiet sarakstu, kurā ir visas jūsu organizācijā pieejamās vides, no kurām varat kopēt datus.

1. Sniedziet šādu informāciju:
   - **Nosaukums**: Šīs vides nosaukums. Šis lauks jau ir aizpildīts, ja esat kopējis no esošas vides, bet varat to mainīt.
   - **Reģions**: Reģions, kurā tiek izvietots un viesots pakalpojums.
   - **Veids**: Atlasiet, vai vēlaties veidot ražošanas vai smilškastes vidi.

1. Pēc izvēles varat arī atlasīt **Papildu iestatījumus**:

   - **Saglabāt visus datus uz** : Norāda, kur saglabāt no Customer Insights ģenerētos izvades datus. Jums ir divas opcijas: **Customer Insights krātuve** (Azure Data Lake, ko pārvalda Customer Insights darba grupa) un **Azure Data Lake Storage Gen2** (jūsu Azure Data Lake Storage). Pēc noklusējuma tiek atlasīta opcija Customer Insights krātuve.

   > [!NOTE]
   > Saglabājot datus Azure Data Lake Storage, jūs piekrītat, ka dati tiks pārsūtīti uz un uzglabāti šī Azure krātuves konta atbilstošajā ģeogrāfiskajā atrašanās vietā, kas var atšķirties no vietas, kur dati tiek glabāti programmā Dynamics 365 Customer Insights. [Uzziniet vairāk Microsoft Trust Center.](https://www.microsoft.com/trust-center)
   >
   > Pašlaik pārņemtās entītijas vienmēr tiek glabātas Customer Insights pārvaldītajā datu ezerā.
   > Mēs atbalstām tikai Azure Data Lake Gen2 krātuves kontus tajā pašā Azure reģionā, kas atlasīts, veidojot vidi.
   > Mēs atbalstām tikai Azure Data Lake Gen2 Hierarchical Name Space (HNS) iespējotos krātuves kontus.

   - Azure Data Lake Storage Gen2 iespējai varat izvēlēties, vai, izmantojot opciju, kuras pamatā ir resurss, vai abonementa opciju, lai autentificētos. Papildinformāciju skatiet tēmā [Auditorijas ieskatu savienošana ar Azure Data Lake Storage Gen2 kontu, izmantojot Azure pakalpojuma primāro nosaukumu](connect-service-principal.md). **Konteinera** nosaukumu nevar mainīt, un tas būs `customerinsights`.
   
   - Ja vēlaties izmantot [prognozes](predictions.md), konfigurējiet datu kopīgošanu ar lietojumprogrammām un risinājumiem, balstoties Microsoft Dataverse, vai iespējojiet datu uzņemšanu no lokāliem datu avotiem, sadaļā **Konfigurēt datu kopīgošanu ar Microsoft Dataverse un iespējojiet papildu iespējas** norādiet Microsoft Dataverse vides URL. Atlasiet opciju **Iespējot datu kopīgošanu**, lai kopīgotu Customer Insights izvades datus ar Microsoft Dataverse Managed Data Lake.

     > [!NOTE]
     > - Datu kopīgošana ar Microsoft Dataverse Managed Data Lake pašlaik netiek atbalstīta, saglabājot visus savus datus jūsu Azure Data Lake Storage.
     > - [Trūkstošo vērtību prognoze entītijā](predictions.md) pašlaik netiek atbalstīta, iespējojot datu kopīgošanu ar Microsoft Dataverse Managed Data Lake.

     > [!div class="mx-imgBorder"]
     > ![Konfigurēšanas opcijas, lai iespējotu datu kopīgošanu ar Microsoft Dataverse](media/datasharing-with-DataverseMDL.png)

   Palaižot procesus, piemēram, datu uzņemšanas vai segmenta izveidi, tiek izveidotas atbilstošas mapes jūsu norādītajā krātuves kontā. Datu faili un model.json faili tiks izveidoti un pievienoti atbilstošajām apakšmapēm atkarībā no procesa, kuru palaižat.

   Ja izveidojat vairāku veidu Customer Insights un izvēlaties saglabāt izvades entītijas, izmantojot savas krātuves konta vides, katrai videi, kurai ir ci_ konteinerā, tiks izveidotas atsevišķas mapes <environmentid>.

### <a name="considerations-for-copy-configuration-preview"></a>Konfigurēšanas kopēšanas apsvērumi (priekšskatījums)

Tiek kopēti tālāk norādītie konfigurācijas iestatījumi.

- Līdzekļu konfigurācija
- Ievadītie/importētie datu avoti
- Datu apvienošanas (kartējums, atbilstība, sapludināšana) konfigurācija
- Segmenti
- Mēri
- Attiecības
- Darbības
- Meklēšanas un filtrēšanas rādītājs
- Eksportēšanas galamērķi
- Plānotā atsvaidzināšana
- Bagātinājumi
- Modeļu pārvaldība
- Lomu piešķīrumi

*Netiek* kopēti tālāk norādītie konfigurācijas iestatījumi.

- Klientu profili.
- Datu avota akreditācijas dati. Jums būs jāsniedz akreditācijas dati katram datu avotam un manuāli jāatsvaidzina datu avoti.
- Datu avoti no Common Data Model mapes un Common Data Service pārvaldīta datu ezera. Šos datu avotus ir jāizveido manuāli, izmantojot tādu pašu nosaukumu kā avota vidē.

Kopējot vidi, tiks parādīts apstiprinājuma ziņojums par to, ka ir izveidota jauna vide. Atlasiet **Doties uz datu avotiem**, lai skatītu datu avotu sarakstu.

Visiem datu avotiem būs redzams statuss **Nepieciešami akreditācijas dati**. Rediģējiet datu avotus un ievadiet akreditācijas datus, lai tos atsvaidzinātu.

> [!div class="mx-imgBorder"]
> ![Kopēti datu avoti](media/data-sources-copied.png)

Pēc datu avotu atsvaidzināšanas dodieties uz **Dati** > **Apvienot**. Šeit atradīsit avota vides iestatījumus. Rediģējiet tos pēc nepieciešamības vai atlasiet **Izpildīt**, lai sāktu datu unificēšanas procesu un izveidotu unificētu klienta entītiju.

Kad datu unificēšana ir pabeigta, dodieties uz **Pasākumi** un **Segmenti**, lai atsvaidzinātu arī tos.

## <a name="edit-an-existing-environment"></a>Esošas vides rediģēšana

Jūs varat rediģēt dažas esošās vides detaļas.

1.  Programmas galvenē atlasiet **Vides** atlasītāju.

2.  Atlasiet **Rediģēt** ikonu.

3. Lodziņā **Rediģēt vidi** var atjaunināt vides **Parādāmo nosaukumu**, taču nevar mainīt lauku **Reģions** vai **Tips**.

4. Ja vide ir konfigurēta saglabāt datus pakalpojumā Azure Data Lake Storage Gen2, jūs varat atjaunināt **Konta atslēgu**. Taču nevar mainīt **Konta nosaukumu** vai **Konteinera** nosaukumu.

5. Ja vēlaties, varat atjaunināt no uzņēmuma atslēgas savienojuma uz resursu vai abonementa bāzes savienojumu. Pēc jaunināšanas jūs nevarat atgriezties pie uzņēmuma atslēgas pēc atjaunināšanas. Papildinformāciju skatiet tēmā [Auditorijas ieskatu savienošana ar Azure Data Lake Storage Gen2 kontu, izmantojot Azure pakalpojuma primāro nosaukumu](connect-service-principal.md). Atjauninot savienojumu, nevar mainīt **Konteinera** informāciju.

6. Ja vēlaties, varat sniegt Microsoft Dataverse vides URL sadaļā **Konfigurēt datu kopīgošanu ar Microsoft Dataverse un iespējot papildu iespējas**. Šīs iespējas ietver datu kopīgošanu ar lietojumprogrammām un risinājumiem, balstoties Microsoft Dataverse, datu uzņemšanā no lokālajiem datu avotiem vai [prognožu](predictions.md) lietošanā. Atlasiet opciju **Iespējot datu kopīgošanu**, lai kopīgotu Customer Insights izvades datus ar Microsoft Dataverse Managed Data Lake.

   > [!NOTE]
   > - Datu kopīgošana ar Microsoft Dataverse Managed Data Lake pašlaik netiek atbalstīta, saglabājot visus savus datus jūsu Azure Data Lake Storage.
   > - [Entitījā trūkstošo vērtību prognozēšana](predictions.md) pašlaik netiek atbalstīta, ja iespējojat datu kopīgošanu ar Microsoft Dataverse Managed Data Lake.

   Kolīdz ir iespējota datu kopīgošana ar Microsoft Dataverse, tiks aktivizēta pilnā jūsu datu avotu atsvaidzināšana un citi procesi. Ja procesi pašlaik ir palaisti un gaida rindā, jums nebūs redzama opcija iespējot datu kopīgošanu ar Microsoft Dataverse. Lai iespējotu datu kopīgošanu, varat pagaidīt, kamēr šie procesi tiek pabeigti, vai tos atcelt. 
   
   :::image type="content" source="media/datasharing-with-DataverseMDL.png" alt-text="Konfigurēšanas opcijas, lai iespējotu datu kopīgošanu ar Microsoft Dataverse.":::
   
   Palaižot procesus, piemēram, datu uzņemšanas vai segmenta izveidi, tiek izveidotas atbilstošas mapes jūsu norādītajā krātuves kontā. Datu faili un model.json faili tiks izveidoti un pievienoti atbilstošajām apakšmapēm atkarībā no procesa, kuru palaižat.

## <a name="reset-an-existing-environment"></a>Esošās vides atiestatīšana

Kā administrators jūs varat atiestatīt vidi tukšā stāvoklī, ja vēlaties dzēst visas konfigurācijas un noņemt uzņemtos datus.

1.  Programmas galvenē atlasiet **Vides** atlasītāju. 

2.  Atlasiet vidi, kuru vēlaties atiestatīt, un atlasiet daudzpunkti **...**. 

3. Izvēlieties opciju **Atiestatīt**. 

4.  Lai apstiprinātu dzēšanu, ievadiet vides nosaukumu un atlasiet **Atiestatīt**.

## <a name="delete-an-existing-environment-available-only-for-admins"></a>Esošas vides dzēšana (pieejama tikai administratoriem)

Jūs kā administrators varat dzēst jūsu administrētu vidi.

1.  Programmas galvenē atlasiet **Vides** atlasītāju.

2.  Atlasiet vidi, kuru vēlaties atiestatīt, un atlasiet daudzpunkti **...**. 

3. Izvēlieties opciju **Dzēst**. 

4.  Lai apstiprinātu dzēšanu, ievadiet vides nosaukumu un atlasiet **Dzēst**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
