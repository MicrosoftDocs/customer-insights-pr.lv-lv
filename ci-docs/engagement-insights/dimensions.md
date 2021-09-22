---
title: Skatīt un izveidot dimensijas
description: Kā izveidot, rediģēt un dzēst dimensijas.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 06/09/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: b575c5e84197d76f53a722bac60c5af928c917f9671720ede1de38c4a7478be4
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034006"
---
# <a name="view-and-create-dimensions"></a>Skatīt un izveidot dimensijas

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Dimensijas ir notikumu atribūti, kas var raksturot, filtrēt vai grupēt datus. Ja savā vietnē esat palaidis mārketinga veicināšanas atbalstu, varat izmantot dimensijas, lai šķirotu kampaņas pēc jauniem un lietotājiem, kas atgriežas.  

Iesaistes ieskati ietver standarta dimensijas notikuma rekvizītos. Piemēri:

- Pārlūkprogrammas nosaukums
- Lapas nosaukums
- Ierīces modelis
- Operētājsistēma
- Valsts/reģions

## <a name="view-dimensions"></a>Skatīt dimensijas

Dimensijas balstās uz esošo notikumu rekvizītiem. Izmantojot izsekošanas kodu iesaistes ieskatos, sistēmas dimensijas tiek automātiski izveidotas.

1. Kreisās puses navigācijas rūtī dodieties uz **Dati**. 
1. Atlasiet **Dimensijas**, lai skatītu visu darbvietas dalībnieku sarakstu. 
   > [!NOTE]
   > Sistēmas ģenerētas dimensijas ir tikai lasāmas. Tās nevar rediģēt. Var izveidot un rediģēt tikai pielāgotas dimensijas.

## <a name="create-a-dimension"></a>Dimensijas izveidošana

Papildus sistēmas ģenerētajam darba vides un darbvietas administratoram var tikt radīts pielāgots ieišana. Pielāgotas dimensijas balstās uz pamata notikumu noklusējuma rekvizītiem vai arī tās var lietot [pielāgotus notikuma rekvizītus](advanced-SDK-implementation.md).

1. Ejiet uz **Dati** > **Dimensijas**.
1. Atlasiet **Pievienot dimensiju**.

   :::image type="content" source="media/add-dimension.png" alt-text="Pievienojiet notikumam dimensiju.":::

1. Rūtī **Izveidot dimensiju** atlasiet rekvizītu, uz kura tiks balstīta dimensija. Rekvizītu sarakstā tiks rādīti visi tās darbvietas rekvizīti, kas nav piešķirti dimensijai.
1. Lodziņā **Parādāmais nosaukums** ievadiet nosaukumu. Pēc izvēles varat pievienot aprakstu.
1. Lai saglabātu dimensiju, atlasiet **Izveidot**. Lai [pielāgotā atskaitē](custom-reports.md) vai [segmentā](segments.md) varētu lietot dimensiju, var paiet viena minūte. 

## <a name="edit-a-dimension"></a>Dimensijas rediģēšana

Varat mainīt dimensijas nosaukumu un aprakstu.

1. Ejiet uz **Dati** > **Dimensijas**.
1. Izvēlieties dimensiju, kuru vēlaties dzēst.
1. Rūtī **Rediģēt dimensiju** atjauniniet dimensiju.
1. Lai saglabātu izmaiņas, atlasiet **Lietot**.

## <a name="delete-a-dimension"></a>Dzēst dimensiju

Var izdzēst tikai lietotāja izveidotas dimensijas, taču nevar noņemt sistēmas dimensijas.

Dimensijas dzēšana ir neatgriezeniska. Atskaites un segmenti, kas izmanto dzēstu dimensiju, vairs nedarbosies. 

1. Ejiet uz **Dati** > **Dimensijas**.
1. Izvēlieties dimensiju, kuru vēlaties dzēst.
1. Rūtī **Rediģēt dimensiju** atlasiet **Dzēst dimensiju**.

   :::image type="content" source="media/delete-dimension.png" alt-text="Dzēsiet notikuma dimensiju.":::

1. Ievadiet **APSTIPRINĀT DZĒŠANU** (ar lielajiem burtiem), lai apstiprinātu dzēšanu. 
1. Atlasiet **Dzēst**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]