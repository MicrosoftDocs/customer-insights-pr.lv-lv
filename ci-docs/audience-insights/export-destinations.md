---
title: Datu eksportēšana no Customer Insights
description: Pārvaldiet eksportēšanu, lai kopīgotu datus.
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c1078ed0ba259a6e9cde3c7ede3570890ae48e67
ms.sourcegitcommit: 33a8e21b3bf6521bdb8346f81f79fce88091ddfd
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 05/10/2021
ms.locfileid: "6016623"
---
# <a name="exports-preview-overview"></a>Eksportēšanas (priekšskatījuma) pārskats

Lapā **Eksportēšana** tiek rādītas visas konfigurētās eksportēšanas. Eksportēšana kopīgo konkrētus datus ar dažādām lietojumprogrammām. Tie var ietvert klientu profilus vai entitījas, shēmas un kartēšanas informāciju. Katrai eksportēšanai ir nepieciešams [administratora iestatīts savienojums, lai pārvaldītu autentifikāciju un piekļuvi](connections.md).

Dodieties uz lapu **Dati** > **Eksportēšana**, lai skatītu eksportēšanas lapu. Visām lietotāju lomām ir piekļuve konfigurētajai eksportēšanai. Izmantojiet komandjoslas meklēšanas lauku, lai meklētu eksportus pēc nosaukuma, savienojuma nosaukuma vai savienojuma veida.

## <a name="set-up-a-new-export"></a>Jauna eksporta iestatīšana

Lai iestatītu vai rediģētu eksportu, ir jābūt pieejamiem savienojumiem. Savienojumi ir atkarīgi no jūsu [lietotāja lomas](permissions.md):
- Administratoriem ir piekļuve visiem savienojumiem. Viņi var arī eksportēšanas iestatīšanas laikā izveidot jaunus savienojumus.
- Līdzstrādniekiem nav piekļuves konkrētiem savienojumiem. Viņi ir atkarīgi no administratoriem, kuri konfigurē un kopīgo savienojumus. Papildinformāciju skatiet rakstā [Atļaut līdzstrādniekiem izmantot savienojumu eksportam](connections.md#allow-contributors-to-use-a-connection-for-exports).
- Skatītāji var tikai skatīt esošos eksportus, bet nevar tos izveidot.

1. Pārejiet uz **Dati** > **Eksportēšana**.

1. Lai izveidotu jaunu eksporta galamērķi, atlasiet **Pievienot eksportu**.

1. Rūtī **Iestatīt eksportu** atlasiet, kuru savienojumu izmantot. [Savienojumus](connections.md) pārvalda administratori. 

1. Norādiet prasīto informāciju un atlasiet **Saglabāt**, lai izveidotu ziņojumu.

### <a name="edit-an-export"></a>Eksporta rediģēšana

1. Atlasiet eksportēšanas galamērķa vertikālo elipsi, ko vēlaties rediģēt.

1. Nolaižamajā izvēlnē atlasiet **Rediģēt**.

1. Mainiet vērtības, kuras vēlaties atjaunināt, un atlasiet **Saglabāt**.

## <a name="view-exports-and-export-details"></a>Skatīt eksportus un eksportēšanas informāciju

Pēc eksporta galamērķu izveides tās tiek uzskaitītas lapā **Dati** > **Eksporti**. Visi lietotāji var redzēt, kuri dati tiek kopīgoti, kā arī to jaunāko statusu.

1. Pārejiet uz **Dati** > **Eksportēšana**.

1. Lietotājiem bez rediģēšanas atļaujas ir **Rediģēt** vietā jāizvēlas **Skatīt**, lai redzētu eksportēšanas informāciju.

1. Sānu rūti redzami eksporta iestatījumi. Bez rediģēšanas atļaujas vērtības nav iespējams mainīt. Atlasiet **Aizvērt**, lai atgrieztos eksportēšanas lapā.

## <a name="run-exports-on-demand"></a>Eksportēšanas palaišana pēc pieprasījuma

Pēc eksporta konfigurēšanas tas tiks palaists ar katru [plānoto atsvaidzināšanu](system.md#schedule-tab), kamēr vien ir funkcionējošs savienojums.

Lai datus eksportētu, negaidot uz plānoto atsvaidzināšanu, dodieties uz **Dati** > **Eksportēšana**. Ir divas iespējas:

- Lai palaistu visus eksportus, komandjoslā atlasiet **Palaist visus**. 
- Lai palaistu vienreizējo eksportēšanu, sarakstu elementā atlasiet daudzpunkti (...) un atlasiet **Palaist**.

## <a name="remove-an-export"></a>Eksporta noņemšana

1. Pārejiet uz **Dati** > **Eksportēšana**.

1. Atlasiet vertikālo daudzpunkti eksportam, kuru vēlaties noņemt.

1. Atlasiet **Noņemt** nolaižamajā izvēlnē.

1. Apstipriniet noņemšanu, apstiprinājuma ekrānā atlasot pogu **Noņemt**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
