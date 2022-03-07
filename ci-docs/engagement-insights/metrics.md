---
title: Skatīt un izveidot metriku
description: Kā izveidot, rediģēt un dzēst metriku.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 7e8c96f38af74f25080a40fd92e73f05c71320a8
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 02/16/2022
ms.locfileid: "8229825"
---
# <a name="view-and-create-metrics"></a>Skatīt un izveidot metriku

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Metrikas palīdz izprast jūsu palīga izturēšanos. Viņi apkopo notikumu rekvizītus un mēra statistiku un jūsu tīmekļa rekvizītu veiktspēju.  

Jūs savā vietnē izmantojat mārketinga akcijas. Metrikas var izmantot, lai izsekotu unikālo lietotāju skaitu, kuri ir sācās jūsu vietnē akcijas laikā. Metrikas analizēšana palīdz labāk izprast jūsu vietnes mērķauditoriju. Apvienojot metriku ar [dimensijām](dimensions.md) [pielāgotā atskaitē](custom-reports.md) ļauj noteikt uzvedību, lai izprastu lietotājus. Piemēram, varat nošķirt kategoriju ar aizsācību jaunajās un atgriežas kategorijās, lai identificētu ieinteresētības atšķirības, kā arī grupu interesi un ieinteresētību.

## <a name="view-metrics"></a>Skatīt metrikas

Iesaistes ieskati ietver biežāk izmantoto notikumu rekvizītu apkopošanu kā sistēmas metriku: 

- Apmeklētāji
- Apmeklējumi
- Lapas skatījumi
- Klikšķi

Šīs sistēmas metrikas pamatā ir esošie notikumu rekvizīti pamata notikumos.

1. Kreisās puses navigācijas rūtī dodieties uz **Dati**. 
1. Atlasiet cilni **Metrika**, lai skatītu visu metriku sarakstu darbvietā. 
   > [!NOTE]
   > Sistēmas ģenerētas metrikas ir tikai lasāmas. Tos nevar rediģēt vai dzēst. Var izveidot un rediģēt tikai pielāgotas metrikas.

## <a name="create-a-metric"></a>Izveidot metriku

Vides un darbvietu administratori var izveidot metrikas. Pirms metrikas izveides uz darbvietu ir jānosūta notikuma rekvizīti. Varat izveidot metrikas, par pamatu izmantojot notikumu rekvizītus, kuri ir nosūtīti, izmantojot pamata notikumus, vai izmantot tīmekļa SDK, lai [nosūtītu pielāgotus notikumu rekvizītus](advanced-SDK-implementation.md).

1. Ejiet uz **Dati** > **Metrikas**.
1. Atlasiet **Jauna metrika**, lai atvērtu **Resursu bibliotēku** un dialoglodziņu **Jauna metrika bez nosaukuma**.

   :::image type="content" source="media/new-metric.png" alt-text="Pievienojiet notikumam metriku.":::

1. Dialoglodziņā **Jauna metrika bez nosaukuma** atlasiet nolaižamo sarakstu **Formāts** un izvēlieties **Vesela skaitļa** vai **Dubulto** datu tipu. Skaitlis ir vesels skaitlis. Dubultajam varat izvēlēties vienu un trīs decimāldaļu vietas.

   :::image type="content" source="media/create-new-metric.png" alt-text="Jaunas metrikas izveide.":::
   
5. Rūtī **Resursu bibliotēka** atrodiet notikuma rekvizītu, kas ir metrikas pamatā.
6. Atlasiet **pluszīmi (+)** blakus rekvizītam, lai to izmantotu formulā. Varat izveidot tikai formul, kas balstīta uz vienu rekvizītu. 
7. Izvēlieties vienu no šīm papildu funkcijām. 

   - Summa: visu vērtību kopējais aritmētiskais 
   - Vidējais: visu vērtību vidējā vērtība
   - Skaits: vērtību kopējais skaits
   - Noteikts skaits: noteiktu vērtību kopējais skaits

   Pēc metrikas definēšanas tiek rādīts pēdējās stundas metrikas darbības priekšskatījums.

1. Atlasiet vienumu **Saglabāt**. 
1. Ievadiet darba grupas nosaukumu un pēc tam atlasiet **Saglabāt**.

Metrikā var paiet minūte, pirmsto var izmantot [pielāgotu ziņojumu izveidē](custom-reports.md).

## <a name="edit-a-metric"></a>Metrikas rediģēšana

Var rediģēt tikai pielāgotas metrikas.

1. Ejiet uz **Dati** > **Metrikas**.
1. Sarakstā atlasiet metriku.
1. Metrikas definīcijas maiņa
1. Atlasiet vienumu **Saglabāt**.

## <a name="change-the-name-of-a-metric"></a>Mainīt metrikas nosaukumu

Var mainīt tikai pielāgoto metriku nosaukumu.

1. Ejiet uz **Dati** > **Metrikas**.
1. Metrikai atlasiet **Vēl [...]** un izvēlieties **Rediģēt nosaukumu**.
1. Mainīt nosaukumu. 
1. Atlasiet **Pārdēvēt**.

## <a name="delete-a-metric"></a>Dzēst metriku

Var dzēst tikai pielāgotas metrikas.

1. Ejiet uz **Dati** > **Metrikas**.
1. Metrikai atlasiet **Vēl [...]** un izvēlieties **Dzēst**.

   :::image type="content" source="media/delete-metric.png" alt-text="Dzēst notikuma metriku.":::

1. Lai apstiprinātu dzēšanu, atlasiet **Dzēst**.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
