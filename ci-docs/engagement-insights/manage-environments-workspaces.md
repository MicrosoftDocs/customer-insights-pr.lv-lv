---
title: Pārvaldīt darbvietas un vides
description: Kā izveidot, pārdēvēt un dzēst darbvietas un vides.
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 09cb3ddf0f8b4507b7eae6668ea3dad08cfcea29
ms.sourcegitcommit: 31985755c7c973fb1eb540c52fd1451731d2bed2
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 10/22/2021
ms.locfileid: "7673799"
---
# <a name="manage-environments-and-workspaces"></a>Vides un darbvietu pārvaldība

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

## <a name="overview"></a>Pārskats

Šajā tēmā apspriests, kā pārvaldīt darbvietas un vides, kad tās jau ir izveidotas. 

- *Darbvieta* ir notikumu un atskaišu glabāšanas un pārvaldīšanas vieta. Tā ir vieta, kur varat skatīt lietotāja darbību reāllaikā. Veidojot darbvietu, atlasiet to datu tipu, kuru sūtīt uz darbvietu. Pašlaik tiek atbalstīti tīmekļa dati un mobilās programmas. Papildinformāciju skatiet rakstā [Jaunas darbvietas izveide un dalībnieku pievienošana](create-workspace.md).

- *Vide* ir vieta, kurā pārvaldīt darbvietas un savienojumus. Papildinformāciju skatiet sadaļā [Jaunas vides izveide](create-new-environment.md).

## <a name="manage-an-existing-workspace"></a>Pārvaldīt esošu darbvietu

Vidē varat uzturēt vairākas darbvietas. Jūsu [loma](user-roles.md) nosaka, kā tajās varat strādāt. 

 - Lai pārvaldītu darbvietu, jums ir jābūt vides vai darbvietas administratoram.
 - Kā darbvietas administrators varat pārdēvēt vai dzēst esošās darbvietas. 

:::image type="content" source="media/workspace-edit.png" alt-text="Darbvietas administratoru centrs.":::

### <a name="edit-a-workspace-name"></a>Rediģēt darbvietas nosaukumu

1. Dodieties uz **Administrators** > **Darbvieta** un atlasiet **Iestatījumi**.

1. Lodziņā **Darbvietas nosaukums** ievadiet jaunu nosaukumu.

1. Lai veiktās izmaiņas stātos spēkā, atlasiet **Saglabāt**.

### <a name="delete-a-workspace"></a>Dzēst darbvietu

Dzēšot darbvietu, tiek neatgriezeniski noņemts viss tās saturs, dati, iestatījumi un atļaujas. To nevar atsaukt.

1. Dodieties uz **Administrators** > **Darbvieta** un atlasiet **Iestatījumi**.

1. Atlasiet **Dzēst darbvietu**. 

1. Dialoglodziņā **Dzēst darbvietu** ievadiet ar lielajiem burtiem **APSTIPRINĀT DZĒŠANU**. 

1. Lai neatgriezeniski dzēstu darbvietu, atlasiet **Dzēst**.

### <a name="manage-workspace-members"></a>Darbvietas dalībnieku pārvaldīšana

1. Dodieties uz **Administrators** > **Darbvieta** un atlasiet **Dalībnieki**.

1. Atlasiet vienumu **Pievienot dalībniekus**, lai piešķirtu piekļuvi un [piešķirtu lomas](user-roles.md). Pašlaik ir pieejams tikai **Darbvietas administrators**.

1. Atlasiet vienumu **Pievienot dalībniekus**, lai tos pievienotu darbvietai.

## <a name="manage-an-existing-environment"></a>Pārvaldīt esošu vidi

Kā vides administrators varat piekļūt videi kreisajā navigācijas rūtī. Varat konfigurēt vides iestatījumus, citus vides administratorus un darbvietas. Atlasiet cilnes, lai pārvietotos starp dažādiem administrēšanas centra apgabaliem.

:::image type="content" source="media/environment-edit.png" alt-text="Vides administrēšanas centrs.":::

### <a name="edit-an-environment-name"></a>Vides nosaukuma rediģēšana

1. Dodieties uz **Administrators** > **Vide** un atlasiet **Iestatījumi**.

1. Atjauniniet **Vides nosaukumu** un atlasiet **Saglabāt**, lai lietotu izmaiņas.

### <a name="delete-an-environment"></a>Vides dzēšana

Vides administratori var dzēst vides. Lai varētu dzēst vidi, ir jānoņem visas tajā esošās darbvietas.

1. Dodieties uz **Administrators** > **Vide** un atlasiet **Iestatījumi**.

1. Atlasiet **Dzēst vidi**. 

1. Dialoglodziņā **Dzēst darbvietu** ievadiet ar lielajiem burtiem **APSTIPRINĀT DZĒŠANU**. 

1. Lai neatgriezeniski dzēstu vidi, atlasiet **Dzēst**.

### <a name="manage-environment-members"></a>Vides dalībnieku pārvaldība

1. Dodieties uz **Administrators** > **Vide** un atlasiet **Dalībnieki**.

1. Atlasiet vienumu **Pievienot dalībniekus**, lai atjaunotu dalībniekus un [piešķirtu lomas](user-roles.md). Pašlaik ir pieejams tikai **Vides administrators**.

1. Atlasiet vienumu **Pievienot dalībniekus**, lai tos pievienotu videi.

## <a name="manage-connections"></a>Pārvaldīt savienojumus

Izveidojot savienojumus ar auditorijas ieskatiem, varat skatīt atskaites iesaistes ieskatos, pamatojoties uz vienotiem klientu profiliem. 

Papildinformācija: [Izveidot saiti starp auditorijas ieskatiem un iesaistes ieskatiem](integrate-audience-insights-engagement-insights.md).

## <a name="manage-personal-data"></a>Personisko datu pārvaldība

Lai aizsargātu klienta personiskos datus, varat dzēst vai eksportēt lietotāja identificējamos datus.

Papildinformāciju skatiet sadaļā [Dzēst un eksportēt notikumu datus, kuros ir ietverta personiskā informācija](../dsr-rights-requests.md#deleting-and-exporting-event-data-containing-end-user-identifiable-information).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
