---
title: Vižu izveide un pārvaldība
description: Uzziniet, kā pierakstīties pakalpojumā un kā pārvaldīt vides.
ms.date: 11/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 65c6a68f550c2873ec30c6ac54f1752d880ce12c
ms.sourcegitcommit: fb9f118b4e16b5aabb3e503463efca21718f5d72
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 11/12/2021
ms.locfileid: "7799645"
---
# <a name="manage-environments"></a>Pārvaldīt vides

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

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

## <a name="connect-to-microsoft-dataverse"></a>Savienojuma izveide ar Microsoft Dataverse
   
**Microsoft Dataverse solis ļauj savienot Customer** Insights ar Dataverse vidi.

Lai izmantotu [gatavus prognoze modeļus](predictions-overview.md#out-of-box-models), konfigurējiet datu koplietošanu ar Dataverse. Varat arī iespējot datu uzņemšanu no lokāls datu avotiem, norādot Microsoft Dataverse vides URL, ko administrē jūsu organizācija. Atlasiet **Iespējot datu** koplietošanu, lai koplietotu Customer Insights izvades datus ar Dataverse pārvaldīto datu ezeru.

:::image type="content" source="media/dataverse-data-sharing.png" alt-text="Konfigurācijas opcijas, lai iespējotu datu koplietošanu ar Microsoft Dataverse.":::

> [!NOTE]
> Customer Insights neatbalsta šādus datu kopīgošanas scenārijus:
> - Ja saglabāsit visus datus savā Azure Data Lake Storage, nevarēsit iespējot datu koplietošanu ar Dataverse pārvaldītu datu ezeru.
> - Ja iespējojat datu koplietošanu ar Dataverse, entītijā nevarēsit [izveidot prognozētas vai trūkstošas vērtības](predictions.md).

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

- Datu avoti no mapes Common Data Model un Dataverse pārvaldīto datu ezeru. Šos datu avotus ir jāizveido manuāli, izmantojot tādu pašu nosaukumu kā avota vidē.

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
