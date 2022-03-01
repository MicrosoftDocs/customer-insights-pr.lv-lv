---
title: Customer Insights datu eksportēšana uz Dynamics 365 Marketing
description: Uzziniet, kā konfigurēt savienojumu un eksportēt uz Dynamics 365 Marketing.
ms.date: 08/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 2c673c432f308efa289625a159de608d07f8d2b3
ms.sourcegitcommit: f988114ac7a288ccadf2db35b02dbef5cacea4d9
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 01/14/2022
ms.locfileid: "7975133"
---
# <a name="use-segments-in-dynamics-365-marketing-preview"></a>Segmentu lietošana Dynamics 365 Marketing (priekšskatījums)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Izmantojiet [segmentus](segments.md) kampaņu veidošanai un saziņai ar specifisku klientu grupu pakalpojumā Dynamics 365 Marketing. Papildinformāciju skatiet tēmā [Segmentu izmantošana no Dynamics 365 Customer Insights ar Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments).

Ja izmantojat jaunās iespējas Dynamics 365 Marketing reāllaika automatizētas kampaņas orķestrācijai Dataverse org, nav nepieciešams izveidot standarta eksportēšanu uz Dynamics 365 Marketing. Kontaktpersonas un segmenti no auditorijas ieskatiem ir pieejami tieši programmā Dynamics 365 Marketing pēc Marketing un Customer Insights pievienošanas. Pirms dzēšat esošu eksportēšanu, pārskatiet dokumentāciju par to, [kā auditorijas ieskatus savienot ar Dynamics 365 Marketing automatizētas kampaņas orķestrāciju](/dynamics365/marketing/real-time-marketing-ci-profile).

## <a name="prerequisite-for-a-connection"></a>Savienojuma priekšnosacījums

- Lai varētu eksportēt segmentu no programmas Customer Insights uz programmu Marketing, programmā Dynamics 365 Marketing ir jābūt kontaktpersonu ierakstiem. Papildinformācija par kontaktpersonu uzņemšanu programmā [Dynamics 365 Marketing, izmantojot Microsoft Dataverse](connect-power-query.md).

  > [!NOTE]
  > Eksportējot segmentus no auditorijas ieskatiem uz programmu Marketing, netiek veidoti jauni kontaktpersonu ieraksti. Kontaktpersonu ieraksti no programmas Marketing jābūt uzņemtiem auditorijas ieskatos un izmantotiem kā datu avotam. Tie ir jāiekļauj arī vienotā Klienta entītijā, lai kartētu klientu ID uz kontaktu ID pirms segmentu eksportēšanas.

## <a name="set-up-connection-to-marketing"></a>Savienojuma ar Marketing iestatīšana

1. Dodieties uz **Administrators** > **Savienojumi**.

1. Atlasiet vienumu **Pievienot savienojumu** un atlasiet **Dynamics 365 Marketing**, lai konfigurētu savienojumu.

1. Laukā **Parādāmais nosaukums** piešķiriet savienojumam atpazīstamu nosaukumu. Parādāmais nosaukums un nosaukuma veids raksturo šo savienojumu. Ir ieteicams izvēlēties nosaukumu, kas paskaidro savienojuma nolūku.

1. Izvēlieties, kurš var izmantot šo savienojumu. Ja nesāksit nekādas darbības, noklusējums būs Administratori. Papildinformāciju skatiet rakstā [Atļaut līdzstrādniekiem izmantot savienojumu eksportam](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Ievadiet jūsu organizācijas Marketing URL laukā **Servera adrese**.

1. Sadaļā **Servera administratora konts** atlasiet **Pieteikties** un izvēlieties Dynamics 365 Marketing kontu.

1. Kartēt kontaktpersonas ID entītijā uz Dynamics 365 Kontaktpersonas ID.

1. Lai pabeigtu savienošanu, atlasiet **Saglabāt**. 

## <a name="configure-an-export"></a>Eksporta konfigurēšana

Šo eksportu varat konfigurēt, ja jums ir piekļuve šā veida pieslēgumam. Papildinformāciju skatiet rakstā [Atļaujas, kas nepieciešamas eksporta konfigurēšanai](export-destinations.md#set-up-a-new-export).

1. Pārejiet uz **Dati** > **Eksportēšana**.

1. Lai izveidotu jaunu eksportu, atlasiet **Pievienot galamērķi**.

1. Laukā **Savienošana eksportam** atlasiet savienojumu no sadaļas Dynamics 365 Marketing. Ja šis sadaļas nosaukums nav redzams, šāda veida savienojumi jums nav pieejami.

1. Izvēlieties vienu vai vairākus segmentus.

1. Atlasiet vienumu **Saglabāt**.

Eksporta saglabāšana automātiski nepalaiž eksportu.

Eksports tiek palaists ar katru [plānoto atsvaidzināšanu](system.md#schedule-tab). Varat arī [eksportēt datus pēc pieprasījuma](export-destinations.md#run-exports-on-demand). 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
