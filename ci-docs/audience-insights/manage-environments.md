---
title: Vižu izveide un pārvaldība
description: Uzziniet, kā pierakstīties pakalpojumā un kā pārvaldīt vides.
ms.date: 07/22/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 2f115269b9d07dd118ec18cc48b55de8aea9b5bb
ms.sourcegitcommit: 98267da3f3eddbdfbc89600a7f54e5e664a8f069
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 07/28/2021
ms.locfileid: "6683482"
---
# <a name="manage-environments"></a>Pārvaldīt vides

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

## <a name="switch-environments"></a>Pārslēgt vides

Lai mainītu vides, lapas augšējā labajā stūrī atlasiet vadīklu **Vide**.

:::image type="content" source="media/home-page-environment-switcher.png" alt-text="Vadīklas ekrānuzņēmums, lai pārslēgtu vides.":::

Administratori var [izveidot](get-started-paid.md) un pārvaldīt vides.

## <a name="edit-an-existing-environment"></a>Esošas vides rediģēšana

Jūs varat rediģēt dažas esošās vides detaļas.

1.  Programmas galvenē atlasiet **Vides** atlasītāju.

2.  Atlasiet **Rediģēt** ikonu.

3. Lodziņā **Rediģēt vidi** var atjaunināt vides **Parādāmo nosaukumu**, taču nevar mainīt lauku **Reģions** vai **Tips**.

4. Ja vide ir konfigurēta datu glabāšanai programmā Azure Data Lake Storage, varat atjaunināt **Konta atslēgu**. Taču nevar mainīt **Konta nosaukumu** vai **Konteinera** nosaukumu.

5. Ja vēlaties, varat atjaunināt no uzņēmuma atslēgas savienojuma uz resursu vai abonementa bāzes savienojumu. Pēc jaunināšanas jūs nevarat atgriezties pie uzņēmuma atslēgas pēc atjaunināšanas. Papildinformāciju skatiet tēmā [Auditorijas ieskatu savienošana ar Azure Data Lake Storage Gen2 kontu, izmantojot Azure pakalpojuma primāro nosaukumu](connect-service-principal.md). Atjauninot savienojumu, nevar mainīt **Konteinera** informāciju.

6. Ja vēlaties, varat sniegt Microsoft Dataverse vides URL sadaļā **Konfigurēt datu kopīgošanu ar Microsoft Dataverse un iespējot papildu iespējas**. Šīs iespējas ietver datu kopīgošanu ar lietojumprogrammām un risinājumiem, balstoties Microsoft Dataverse, datu uzņemšanā no lokālajiem datu avotiem vai [prognožu](predictions.md) lietošanā. Atlasiet opciju **Iespējot datu kopīgošanu**, lai kopīgotu Customer Insights izvades datus ar programmas Microsoft Dataverse pārvaldīto Data Lake.

   > [!NOTE]
   > - Datu kopīgošana ar programmas Microsoft Dataverse pārvaldīto Data Lake pašlaik netiek atbalstīta, saglabājot visus savus datus jūsu Azure Data Lake Storage.
   > - [Trūkstošo vērtību prognozēšana entītijā](predictions.md) un PowerBI Embedded atskaitēs auditorijas ieskatos (ja tā ir iespējota jūsu vidē) patlaban nav atbalstīta, ja iespējojat datu kopīgošanu ar Microsoft Dataverse pārvaldīto datu ezeru.

   Kolīdz ir iespējota datu kopīgošana ar Microsoft Dataverse, tiks aktivizēta pilnā jūsu datu avotu atsvaidzināšana un citi procesi. Ja procesi pašlaik ir palaisti un gaida rindā, jums nebūs redzama opcija iespējot datu kopīgošanu ar Microsoft Dataverse. Lai iespējotu datu kopīgošanu, varat pagaidīt, kamēr šie procesi tiek pabeigti, vai tos atcelt. 
   
   :::image type="content" source="media/datasharing-with-DataverseMDL.png" alt-text="Konfigurēšanas opcijas, lai iespējotu datu kopīgošanu ar Microsoft Dataverse.":::
   
   Palaižot procesus, piemēram, datu uzņemšanas vai segmenta izveidi, tiek izveidotas atbilstošas mapes jūsu norādītajā krātuves kontā. Datu faili un model.json faili tiks izveidoti un pievienoti atbilstošajām apakšmapēm atkarībā no procesa, kuru palaižat.

## <a name="copy-the-environment-configuration"></a>Izveidojiet vides konfigurācijas kopiju

Izveidojot jaunu vidi, varat izvēlēties kopēt konfigurāciju no esošas vides. 

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Vides iestatījumos redzamo iestatījumu opciju ekrānuzņēmums.":::

Jūs redzēsiet sarakstu, kurā ir visas jūsu organizācijā pieejamās vides, no kurām varat kopēt datus.

Tiek kopēti tālāk norādītie konfigurācijas iestatījumi.

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
- Lomu piešķiršana

Nākamie *dati* nav kopēti:

- Klientu profili.
- Datu avota akreditācijas dati. Jums būs jāsniedz akreditācijas dati katram datu avotam un manuāli jāatsvaidzina datu avoti.
- Datu avoti no Common Data Model mapes un Dataverse pārvaldītā Data Lake. Šos datu avotus ir jāizveido manuāli, izmantojot tādu pašu nosaukumu kā avota vidē.

Kopējot vidi, tiks parādīts apstiprinājuma ziņojums par to, ka ir izveidota jauna vide. Atlasiet **Doties uz datu avotiem**, lai skatītu datu avotu sarakstu.

Visiem datu avotiem būs redzams statuss **Nepieciešami akreditācijas dati**. Rediģējiet datu avotus un ievadiet akreditācijas datus, lai tos atsvaidzinātu.

:::image type="content" source="media/data-sources-copied.png" alt-text="Kopēto un autentifikācijai nepieciešamo datu avotu saraksts.":::

Pēc datu avotu atsvaidzināšanas dodieties uz **Dati** > **Apvienot**. Šeit atradīsit avota vides iestatījumus. Rediģējiet tos pēc nepieciešamības vai atlasiet **Izpildīt**, lai sāktu datu unificēšanas procesu un izveidotu unificētu klienta entītiju.

Kad datu unificēšana ir pabeigta, dodieties uz **Pasākumi** un **Segmenti**, lai atsvaidzinātu arī tos.

## <a name="reset-an-existing-environment"></a>Esošās vides atiestatīšana

Kā administrators jūs varat atiestatīt vidi tukšā stāvoklī, ja vēlaties dzēst visas konfigurācijas un noņemt uzņemtos datus.

1.  Programmas galvenē atlasiet **Vides** atlasītāju. 

2.  Atlasiet vidi, kuru vēlaties atiestatīt, un atlasiet daudzpunkti (**...**). 

3. Izvēlieties opciju **Atiestatīt**. 

4.  Lai apstiprinātu dzēšanu, ievadiet vides nosaukumu un atlasiet **Atiestatīt**.

## <a name="delete-an-existing-environment"></a>Esošas vides dzēšana

Jūs kā administrators varat dzēst jūsu administrētu vidi.

1.  Programmas galvenē atlasiet **Vides** atlasītāju.

2.  Atlasiet vidi, kuru vēlaties atiestatīt, un atlasiet daudzpunkti (**...**). 

3. Izvēlieties opciju **Dzēst**. 

4.  Lai apstiprinātu dzēšanu, ievadiet vides nosaukumu un atlasiet **Dzēst**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
