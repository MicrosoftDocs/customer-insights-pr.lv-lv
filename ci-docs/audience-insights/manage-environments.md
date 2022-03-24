---
title: Vižu izveide un pārvaldība
description: Uzziniet, kā pierakstīties pakalpojumā un kā pārvaldīt vides.
ms.date: 02/09/2022
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
searchScope:
- ci-system-about
- customerInsights
ms.openlocfilehash: 4f4e5a8415f6c2128b0480edf67f317124eeeba9
ms.sourcegitcommit: 50d32a4cab01421a5c3689af789e20857ab009c4
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 03/03/2022
ms.locfileid: "8376885"
---
# <a name="manage-environments"></a>Pārvaldīt vides

## <a name="switch-environments"></a>Pārslēgt vides

Lai mainītu vides, lapas augšējā labajā stūrī atlasiet vadīklu **Vide**.

:::image type="content" source="media/home-page-environment-switcher.png" alt-text="Vadīklas ekrānuzņēmums, lai pārslēgtu vides.":::

Administratori var [izveidot](create-environment.md) un pārvaldīt vides.

## <a name="edit-an-existing-environment"></a>Esošas vides rediģēšana

Jūs varat rediģēt dažas esošās vides detaļas.

1.  Programmas galvenē atlasiet **Vides** atlasītāju.

2.  Atlasiet **Rediģēt** ikonu.

3. Lodziņā **Rediģēt vidi** varat atjaunināt vides iestatījumus.

Papildinformāciju par vides iestatījumiem skatiet sadaļā [Jaunas vides izveide](create-environment.md).

## <a name="connect-to-microsoft-dataverse"></a>Izveidot savienojumu ar Microsoft Dataverse
   
Šī **Microsoft Dataverse** darbība ļauj izveidot Customer Insights savienojumu ar savu Dataverse vidi.

Lai izmantotu [standarta prognožu modeļus](predictions-overview.md#out-of-box-models), konfigurējiet datu kopīgošanu ar Dataverse. Varat arī iespējot datu inaktivizēšanu no lokāls avotiem, norādot Microsoft Dataverse jūsu organizācijas administrējamo vides URL.

> [!IMPORTANT]
> Customer Insights, un Dataverse, lai iespējotu datu koplietošanu, tam jāatrodas vienā reģionā.

:::image type="content" source="media/dataverse-provisioning.png" alt-text="Konfigurēšanas opcijas, lai iespējotu datu kopīgošanu ar Microsoft Dataverse.":::

> [!NOTE]
> Customer Insights neatbalsta šādus datu kopīgošanas scenārijus:
> - Ja saglabāsit visus datus pats savā Azure Data Lake Storage, jūs nevarēsit iespējot datu kopīgošanu ar Dataverse pārvaldīto Data Lake.
> - Ja iespējosit datu kopīgošanu ar Dataverse, jūs nevarēsit [izveidot paredzamas vai trūkstošas vērtības entītijā](predictions.md).

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

- Datu avoti no mapes Common Data Model un Dataverse pārvaldītā data lake. Šos datu avotus ir jāizveido manuāli, izmantojot tādu pašu nosaukumu kā avota vidē.

Kopējot vidi, tiks parādīts apstiprinājuma ziņojums par to, ka ir izveidota jauna vide. Atlasiet **Doties uz datu avotiem**, lai skatītu datu avotu sarakstu.

Visiem datu avotiem būs redzams statuss **Nepieciešami akreditācijas dati**. Rediģējiet datu avotus un ievadiet akreditācijas datus, lai tos atsvaidzinātu.

:::image type="content" source="media/data-sources-copied.png" alt-text="Kopēto un autentifikācijai nepieciešamo datu avotu saraksts.":::

Pēc datu avotu atsvaidzināšanas dodieties uz **Dati** > **Apvienot**. Šeit atradīsit avota vides iestatījumus. Rediģējiet tos pēc nepieciešamības vai atlasiet **Izpildīt**, lai sāktu datu unificēšanas procesu un izveidotu unificētu klienta entītiju.

Kad datu unificēšana ir pabeigta, dodieties uz **Pasākumi** un **Segmenti**, lai atsvaidzinātu arī tos.

## <a name="change-the-owner-of-an-environment"></a>Vides īpašnieka maiņa

Lai gan vairākiem lietotājiem programmā Customer Insights var būt administratora atļaujas, vides īpašnieks ir tikai viens lietotājs. Pēc noklusējuma tas ir administrators, kurš sākotnēji izveido vidi. Kā vides administrators varat piešķirt īpašumtiesības citam lietotājam ar administratora atļaujām.

1. Programmas galvenē atlasiet **Vides** atlasītāju.

1. Atlasiet **Rediģēt** ikonu.

1. Lodziņā **Rediģēt vidi** dodieties uz **darbību Pamatinformācija**.

1. Laukā **Mainīt vides** īpašnieku izvēlieties jauno vides īpašnieku.  

1. Atlasiet **Pārskatīšana un pabeigšana**, pēc tam **atjauniniet**, lai lietotu izmaiņas. 

## <a name="claim-ownership-of-an-environment"></a>Pieprasīt īpašumtiesības uz vidi

Ja vides īpašnieks pamet organizāciju vai tā lietotāja konts tiek dzēsts, videi nebūs īpašnieka. Lietotājs ar administratora atļaujām var pieprasīt īpašumtiesības un kļūt par jauno īpašnieku. Viņi var turpināt piederēt videi vai [mainīt īpašumtiesības uz citu administratoru](#change-the-owner-of-an-environment). 

Lai pieprasītu īpašumtiesības, atlasiet **pogu Uzņemties īpašumtiesības**, kas tiek rādīta katras Customer Insights lapas augšdaļā, kad sākotnējais īpašnieks atstāja organizāciju.

## <a name="reset-an-existing-environment"></a>Esošās vides atiestatīšana

Ja vēlaties dzēst visas konfigurācijas un noņemt uzņemtos datus, kā vides īpašnieks varat atiestatīt vidi tukšā stāvoklī.

1.  Programmas galvenē atlasiet **Vides** atlasītāju. 

2.  Atlasiet vidi, kuru vēlaties atiestatīt, un atlasiet daudzpunkti (**...**). 

3. Izvēlieties opciju **Atiestatīt**. 

4.  Lai apstiprinātu dzēšanu, ievadiet vides nosaukumu un atlasiet **Atiestatīt**.

## <a name="delete-an-existing-environment"></a>Esošas vides dzēšana

Kā vides īpašnieks varat izdzēst administrējamo vidi.

1.  Programmas galvenē atlasiet **Vides** atlasītāju.

2.  Atlasiet vidi, kuru vēlaties atiestatīt, un atlasiet daudzpunkti (**...**). 

3. Izvēlieties opciju **Dzēst**. 

4.  Lai apstiprinātu dzēšanu, ievadiet vides nosaukumu un atlasiet **Dzēst**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
