---
title: Skatīt un izveidot metriku
description: Kā izveidot, rediģēt un dzēst metriku.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 06/09/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 97189168e0f5586aad8be8089a1f9e27893c2115c7e805ddaab1efc00e11b860
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034278"
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
   > Sistēmas ģenerētas metrikas ir tikai lasāmas. Tās nevar ne mainīt, ne dzēst. Var izveidot un rediģēt tikai pielāgotas metrikas.

## <a name="create-a-metric"></a>Izveidot metriku

Vides un darbvietu administratori var izveidot metrikas. Pirms metrikas izveides uz darbvietu ir jānosūta notikuma rekvizīti. Varat izveidot metrikas, par pamatu izmantojot notikumu rekvizītus, kuri ir nosūtīti, izmantojot pamata notikumus, vai izmantot tīmekļa SDK, lai [nosūtītu pielāgotus notikumu rekvizītus](advanced-SDK-implementation.md).

1. Ejiet uz **Dati** > **Metrikas**.
1. Atlasiet **Jauna metrika**.

   :::image type="content" source="media/new-metric.png" alt-text="Pievienojiet notikumam metriku.":::

1. Formātam atlasiet **veselā skaitļa** vai **dubulto** datu tipu. Skaitlis ir vesels skaitlis. Dubultajam var izvēlēties vienu līdz trīs decimāldaļu vietas aiz komata.
1. Rūtī **Resursu bibliotēka** atrodiet notikuma rekvizītu, kas ir metrikas pamatā.
1. Atlasiet **pluszīmi (+)** blakus rekvizītam, lai to izmantotu formulā. Varat izveidot tikai formul, kas balstīta uz vienu rekvizītu. 
1. Izvēlieties vienu no šīm papildu funkcijām. 

   - Summa: visu vērtību kopējais aritmētiskais 
   - Vidējais: visu vērtību vidējā vērtība
   - Skaits: vērtību kopējais skaits
   - Noteikts skaits: noteiktu vērtību kopējais skaits

   Pēc metrikas definēšanas tiek rādīts pēdējās stundas metrikas darbības priekšskatījums.

1. Atlasiet vienumu **Saglabāt**. 
1. Ievadiet darba grupas nosaukumu un pēc tam atlasiet **Saglabāt**.

Metrikā var paiet minūte, pirmsto var izmantot [pielāgotu ziņojumu izveidē](custom-reports.md).

## <a name="edit-a-metric"></a>Metrikas rediģēšana

1. Ejiet uz **Dati** > **Metrikas**.
1. Sarakstā atlasiet metriku.
1. Metrikas definīcijas maiņa
1. Atlasiet vienumu **Saglabāt**.

## <a name="change-the-name-of-a-metric"></a>Mainīt metrikas nosaukumu

1. Ejiet uz **Dati** > **Metrikas**.
1. Metrikai atlasiet **Vēl [...]** un izvēlieties **Rediģēt nosaukumu**.
1. Mainīt nosaukumu. 
1. Atlasiet **Pārdēvēt**.

## <a name="delete-a-metric"></a>Dzēst metriku

1. Ejiet uz **Dati** > **Metrikas**.
1. Metrikai atlasiet **Vēl [...]** un izvēlieties **Dzēst**.

   :::image type="content" source="media/delete-metric.png" alt-text="Dzēst notikuma metriku.":::

1. Lai apstiprinātu dzēšanu, atlasiet **Dzēst**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
