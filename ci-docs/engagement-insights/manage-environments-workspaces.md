---
title: Pārvaldīt darbvietas un vides
description: Kā izveidot, pārdēvēt un dzēst darbvietas un vides.
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 09/09/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: a5b48db5ae23ea65bf608d67348d493bfdc7678f
ms.sourcegitcommit: 0ceb46c4f57ab49d3a2ebb1c8a816bbafe979e3d
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 09/09/2021
ms.locfileid: "7486044"
---
# <a name="manage-environments-and-workspaces"></a>Vides un darbvietu pārvaldība

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

## <a name="overview"></a>Pārskats

Darbvieta ir notikumu un atskaišu glabāšanas un pārvaldīšanas vieta. Tā ir vieta, kur varat skatīt lietotāja darbību reāllaikā. Veidojot darbvietu, atlasiet to datu tipu, kuru sūtīt uz darbvietu. Pašlaik tiek atbalstīti tīmekļa dati un mobilās programmas.

Vide ir vieta, kurā pārvaldīt darbvietas un savienojumus. Vides izmantošanas veids ir atkarīgs no uzņēmuma un lietošanas gadījuma. Piemēram, varat izveidot:

-   Vienu vidi.
-   Atsevišķas vides testēšanai un ražošanai.
-   Atsevišķas vides noteiktām organizācijas darba grupām vai departamentiem, kuros ir ietverti katrai auditorijai atbilstoši notikumi.
-   Atsevišķas vides dažādiem jūsu uzņēmuma globālajām filiālēm.
-   Savienojumi ar Customer Insights auditorijas ieskatu iespējām.

## <a name="choose-an-environment-and-create-a-workspace"></a>Izvēlieties vidi un izveidojiet darbvietu 

Katrai darbvietai ir jābūt vidē. Izveidojot darbvietu, var atlasīt iepriekš esošu vidi vai izveidot jaunu. Pēc tam varat pievienot darbvietas dalībniekus un sākt datu apkopošanu.

**Lai izveidotu savu pirmo darbvietu**

1. Iesaistes ieskatos no darbvietas pārslēdzēja atlasiet **Jauns**. 

   :::image type="content" source="media/New-workspace.png" alt-text="Customer Insights lapas darbvietas atlasītājs.":::

1. Sarakstā izvēlieties vidi vai atlasiet **Izveidot jaunu vidi**.

1. Ievadiet nosaukumu laukā **Darbvietas nosaukums**. 

1. Atlasiet vides tipu, kuru vēlaties izveidot, atkarībā no tā, vai vēlaties izmērīt, kas notiek tīmekļa vietnē vai mobilajā programmā. 

1. Varat pievienot dalībniekus un piešķirt viņu atļauju līmeni sarakstā **Loma**. Pēc tam atlasiet **Pabeigt**, lai izveidotu darbvietu, vai atlasiet **Tālāk**, lai instalētu kodu. 

1. Instalējiet datu koda fragmentu, lai sāktu saņemt datus, un pēc tam atlasiet **Gatavs**. 

## <a name="manage-a-workspace"></a>Darbvietas pārvaldīšana

Vidē varat uzturēt vairākas darbvietas. Jūsu [loma](user-roles.md) nosaka, kā tajās varat strādāt. 

 - Lai pārvaldītu darbvietu, jums ir jābūt vides vai darbvietas administratoram.
 - Kā darbvietas administrators varat pārdēvēt vai dzēst esošās darbvietas. 

### <a name="edit-a-workspace-name"></a>Rediģēt darbvietas nosaukumu

1. Dodieties uz **Administrators** > **Darbvieta** un atlasiet **Iestatījumi**.

1. Lodziņā **Darbvietas nosaukums** ievadiet jaunu nosaukumu.

1. Lai veiktās izmaiņas stātos spēkā, atlasiet **Saglabāt**.

### <a name="delete-a-workspace"></a>Dzēst darbvietu

Dzēšot darbvietu, tiks neatgriezeniski noņemts viss tās saturs, dati, iestatījumi un atļaujas. To nevar atsaukt.

1. Dodieties uz **Administrators** > **Darbvieta** un atlasiet **Iestatījumi**.

1. Atlasiet **Dzēst darbvietu**. 

1. Dialoglodziņā **Dzēst darbvietu** ievadiet **APSTIPRINĀT DZĒŠANU**. 

1. Lai neatgriezeniski dzēstu darbvietu, atlasiet **Dzēst**.

### <a name="manage-workspace-members"></a>Darbvietas dalībnieku pārvaldīšana

1. Dodieties uz **Administrators** > **Darbvieta** un atlasiet **Dalībnieki**.

1. Atlasiet vienumu **Pievienot dalībniekus**, lai piešķirtu piekļuvi un [piešķirtu lomas](user-roles.md). Pašlaik ir pieejams tikai **Darbvietas administrators**.

1. Atlasiet vienumu **Pievienot dalībniekus**, lai tos pievienotu darbvietai.

## <a name="manage-an-environment"></a>Pārvaldīt vidi

Kā vides administrators varat piekļūt videi kreisajā navigācijas rūtī. Varat konfigurēt vides iestatījumus, citus vides administratorus un darbvietas. Atlasiet cilnes, lai pārvietotos starp dažādiem administrēšanas centra apgabaliem.

:::image type="content" source="media/New-environment.png" alt-text="Vides administrēšanas centrs.":::

### <a name="create-an-environment"></a>Vides izveide

1. Darbvietas atlasītājā atlasiet **+Jauns**.

1. Vadītajā darbā atveriet nolaižamo izvēlni **Vide** un atlasiet **Izveidot jaunu vidi**. 

1. Norādiet **Vides nosaukumu**.

   :::image type="content" source="media/create-environment.png" alt-text="Solis vadītajā darbā, lai norādītu detalizētu informāciju par vidi.":::

1. Izvēlieties **Reģionu** un atlasiet **Tālāk**. 

1. Norādiet darbvietas nosaukumu un izvēlieties, kāda tipa darbvietu vēlaties izveidot. 

1.  Ja vēlaties, pievienojiet dalībniekus un kopējiet koda fragmentu izveides procesa pabeigšanai.

### <a name="rename-an-environment"></a>Vides pārdēvēšana

1. Dodieties uz **Administrators** > **Vide** un atlasiet **Iestatījumi**.

1. Atjauniniet **Vides nosaukumu** un atlasiet **Saglabāt**, lai lietotu izmaiņas.

### <a name="manage-environment-members"></a>Vides dalībnieku pārvaldība

1. Dodieties uz **Administrators** > **Vide** un atlasiet **Dalībnieki**.

1. Atlasiet vienumu **Pievienot dalībniekus**, lai atjaunotu dalībniekus un [piešķirtu lomas](user-roles.md). Pašlaik ir pieejams tikai **Vides administrators**.

1. Atlasiet vienumu **Pievienot dalībniekus**, lai tos pievienotu videi.

### <a name="delete-an-environment"></a>Vides dzēšana

Vides administratori var dzēst vides. Lai varētu dzēst vidi, ir jānoņem visas tajā esošās darbvietas.

1. Dodieties uz **Administrators** > **Vide** un atlasiet **Iestatījumi**.

1. Atlasiet **Dzēst vidi**. 

1. Dialoglodziņā **Dzēst darbvietu** ievadiet **APSTIPRINĀT DZĒŠANU**. 

1. Lai neatgriezeniski dzēstu vidi, atlasiet **Dzēst**.

## <a name="manage-connections"></a>Pārvaldīt savienojumus

Izveidojot savienojumus ar auditorijas ieskatiem, varat skatīt atskaites iesaistes ieskatos, pamatojoties uz vienotiem klientu profiliem. 

Papildinformācija: [Izveidot saiti starp auditorijas ieskatiem un iesaistes ieskatiem](integrate-audience-insights-engagement-insights.md).

## <a name="manage-personal-data"></a>Personisko datu pārvaldība

Lai aizsargātu klienta personiskos datus, varat dzēst vai eksportēt lietotāja identificējamos datus.

Papildinformāciju skatiet sadaļā [Dzēst un eksportēt notikumu datus, kuros ir ietverta personiskā informācija](delete-export-personal-data.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
