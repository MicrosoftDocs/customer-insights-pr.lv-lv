---
title: Ieplānojiet sistēmas atsvaidzināšanu
description: Ieplānojiet laiku, kad sistēma ir jāatsvaidzina
ms.date: 08/09/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-system-schedule
- customerInsights
ms.openlocfilehash: 949ea071ca41127b0c45488d5d7af3f6aa4e1c35
ms.sourcegitcommit: d7054a900f8c316804b6751e855e0fba4364914b
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 09/02/2022
ms.locfileid: "9395965"
---
# <a name="schedule-system-refresh"></a>Ieplānojiet sistēmas atsvaidzināšanu

Ieplānojiet visu uzņemto [datu avotu automātisku atsvaidzināšanu](data-sources.md). Automātiskā atsvaidzināšana palīdz nodrošināt, ka jūsu datu avotu atjauninājumi tiek atspoguļoti vienotajos klientu profilos.

> [!NOTE]
> Power Query jūsu pārvaldītie datu avoti tiek atsvaidzināti pēc saviem grafikiem. Lai ieplānotu šo Power Query datu avotu atsvaidzināšanu, konfigurējiet atsvaidzināšanas iestatījumus konkrētajā datu avots lapā **Datu avoti**.
> :::image type="content" source="media/PPDF-edit-refresh.png" alt-text="Power Platform Dataflow atsvaidzināšanas iestatījumi.":::

## <a name="set-system-refresh-schedule"></a>Sistēmas atsvaidzināšanas grafika iestatīšana

1. Dodieties uz administrēšanas sistēma un atlasiet cilni **Grafiks** > **.** **·**

   :::image type="content" source="media/schedule_refresh.png" alt-text="Cilne Ieplānot atsvaidzināšanu no lapas Sistēma.":::

1. Plānotās atsvaidzināšanas noklusējuma stāvoklis ir **Izslēgts**. Lai iespējotu plānoto atsvaidzināšanu, ekrāna augšdaļā mainiet slēdža pozīciju uz **Ieslēgta**.

1. Izvēlieties starp **Katru nedēļu** (noklusējuma) un **Katru dienu**. Ja plānojat iknedēļas atsvaidzināšanu, atlasiet vienu vai vairākas dienas, kurās vēlaties izpildīt atsvaidzināšanu.

1. Iestatiet **Laika joslu**, tad izmantojiet **Laika** nolaižamo sarakstu, lai iestatītu atsvaidzināšanas laiku. Ja vēlaties ieplānot vairākas atsvaidzināšanas vienā dienā, atlasiet **Pievienot citu laiku**. Varat pievienot ne vairāk kā četrus atsvaidzinājumus.

1. Lai veiktās izmaiņas stātos spēkā, atlasiet **Saglabāt**.

[!INCLUDE [footer-include](includes/footer-banner.md)]
