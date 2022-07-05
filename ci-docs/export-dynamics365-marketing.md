---
title: Segmentu eksportēšana uz Dynamics 365 Marketing (priekšskatījums)
description: Uzziniet, kā konfigurēt savienojumu un eksportēt uz Dynamics 365 Marketing.
ms.date: 08/24/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- customerInsights
ms.openlocfilehash: fed4ae1b017cca2b6060c4dda155859cd77e0daf
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 06/29/2022
ms.locfileid: "9054625"
---
# <a name="export-segments-to-dynamics-365-marketing-preview"></a>Segmentu eksportēšana uz Dynamics 365 Marketing (priekšskatījums)

Izmantojiet [segmentus](segments.md) kampaņu veidošanai un saziņai ar specifisku klientu grupu pakalpojumā Dynamics 365 Marketing. Papildinformāciju skatiet tēmā [Segmentu izmantošana no Dynamics 365 Customer Insights ar Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments).

Ja izmantojat jaunās iespējas Dynamics 365 Marketing reāllaika automatizētas kampaņas orķestrācijai Dataverse org, nav nepieciešams izveidot standarta eksportēšanu uz Dynamics 365 Marketing. Kontaktpersonas un segmenti no Customer Insights ir pieejami tieši programmā Dynamics 365 Marketing pēc tam, kad ir izveidots savienojums ar Marketing un Customer Insights. Pirms esošo eksportēšanas dzēšanas pārskatiet dokumentāciju par [to, kā savienot Customer Insights un Dynamics 365 Marketing automatizēta kampaņa orķestrāciju](/dynamics365/marketing/real-time-marketing-ci-profile).

## <a name="prerequisite-for-a-connection"></a>Savienojuma priekšnosacījums

- Lai varētu eksportēt segmentu no programmas Customer Insights uz programmu Marketing, programmā Dynamics 365 Marketing ir jābūt kontaktpersonu ierakstiem. Papildinformācija par kontaktpersonu uzņemšanu programmā [Dynamics 365 Marketing, izmantojot Microsoft Dataverse](connect-dataverse-managed-lake.md).

  > [!NOTE]
  > Eksportējot segmentus no Customer Insights uz Marketing, mārketinga instancēs netiks izveidoti jauni kontaktpersonu ieraksti. Mārketinga kontaktpersonu ieraksti ir jāuzņem programmā Customer Insights un jāizmanto kā datu avots. Tie ir jāiekļauj arī vienotā Klienta entītijā, lai kartētu klientu ID uz kontaktu ID pirms segmentu eksportēšanas.

## <a name="set-up-connection-to-marketing"></a>Savienojuma ar Marketing iestatīšana

1. Dodieties uz **Administrators** > **Savienojumi**.

1. Atlasiet vienumu **Pievienot savienojumu** un atlasiet **Dynamics 365 Marketing**, lai konfigurētu savienojumu.

1. Laukā **Parādāmais nosaukums** piešķiriet savienojumam atpazīstamu nosaukumu. Parādāmais nosaukums un nosaukuma veids raksturo šo savienojumu. Ir ieteicams izvēlēties nosaukumu, kas paskaidro savienojuma nolūku.

1. Izvēlieties, kurš var izmantot šo savienojumu. Ja nesāksit nekādas darbības, noklusējums būs Administratori. Papildinformāciju skatiet rakstā [Atļaut līdzstrādniekiem izmantot savienojumu eksportam](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Ievadiet jūsu organizācijas Marketing URL laukā **Servera adrese**.

1. Sadaļā **Servera administratora konts** atlasiet **Pieteikties** un izvēlieties Dynamics 365 Marketing kontu.

1. Kartējiet entītijas Klienta ID lauku Kontaktpersona ID uz Dynamics 365 kontaktpersonas ID.

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

[!INCLUDE [footer-include](includes/footer-banner.md)]
