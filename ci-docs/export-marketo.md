---
title: Segmentu eksportēšana uz Marketo (priekšskatījums)
description: Uzziniet, kā konfigurēt savienojumu un eksportēt uz Marketo.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8cd24cf436bd5fdfd4ec3834d35baa1495e37ca4
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 06/29/2022
ms.locfileid: "9053214"
---
# <a name="export-segments-to-marketo-preview"></a>Segmentu eksportēšana uz Marketo (priekšskatījums)

Izmantojiet pakalpojumā Customer Insights izveidotos segmentus kampaņu veidošanai, e-pasta mārketinga sniegšanai un specifisku klientu grupu atlases iespējas pakalpojumā Marketo.

## <a name="prerequisites-for-connection"></a>Savienojuma priekšnosacījumi

-   Jums ir [Marketo konts](https://login.marketo.com/) un atbilstošie administratora akreditācijas dati.
-   Marketo ir esošas auditorijas un attiecīgie ID. Lai iegūtu papildinformāciju, skatiet [Marketo sarakstus](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).
-   Jums ir [konfigurēti segmenti](segments.md).
-   Eksportētajos segmentos vienotajiem klientu profiliem ir lauks, kas norāda e-pasta adresi.

## <a name="known-limitations"></a>Zināmie ierobežojumi

- Līdz 1 miljoniem klientu profilu vienai eksportēšanai uz Marketo.
- Eksportēšana uz Marketo ir ierobežota līdz segmentiem.
- 1 miljona klientu profilu segmentu eksports var ilgt līdz 3 minūtēm. 
- To klientu profilu skaits, kurus varat eksportēt uz Marketo, ir atkarīgs un ierobežots atkarībā no jūsu līguma ar Marketo.

## <a name="set-up-connection-to-marketo"></a>Savienojuma ar Marketo iestatīšana

1. Dodieties uz **Administrators** > **Savienojumi**.

1. Atlasiet vienumu **Pievienot savienojumu** un atlasiet **Marketo**, lai konfigurētu savienojumu.

1. Laukā **Parādāmais nosaukums** piešķiriet savienojumam atpazīstamu nosaukumu. Parādāmais nosaukums un nosaukuma veids raksturo šo savienojumu. Ir ieteicams izvēlēties nosaukumu, kas paskaidro savienojuma nolūku.

1. Izvēlieties, kurš var izmantot šo savienojumu. Ja nesāksit nekādas darbības, noklusējums būs Administratori. Papildinformāciju skatiet rakstā [Atļaut līdzstrādniekiem izmantot savienojumu eksportam](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Ievadiet savu **[Marketo klienta ID, klienta slepeno vārdu un REST galapunktu resursdatorā](https://developers.marketo.com/rest-api/authentication/)**. REST galapunkta viesošanas nosaukums ir tikai viesošanas nosaukums bez `https://`. Piemērs: `xyz-abc-123.mktorest.com`. 

1. Atlasiet **Es piekrītu**, lai apstiprinātu **Datu konfidencialitāti un atbilstību**, un atlasiet opciju **Izveidot savienojumu**, lai inicializētu savienojumu ar Marketo.

1. Atlasiet opciju **Pievienot sevi kā eksporta lietotāju** un sniedziet savus Customer Insights akreditācijas datus.

1. Lai pabeigtu savienošanu, atlasiet **Saglabāt**.

## <a name="configure-an-export"></a>Eksporta konfigurēšana

Šo eksportu varat konfigurēt, ja jums ir piekļuve šā veida pieslēgumam. Papildinformāciju skatiet rakstā [Atļaujas, kas nepieciešamas eksporta konfigurēšanai](export-destinations.md#set-up-a-new-export).

1. Pārejiet uz **Dati** > **Eksportēšana**.

1. Lai izveidotu jaunu eksportu, atlasiet **Pievienot galamērķi**.

1. Laukā **Savienošana eksportam** atlasiet savienojumu no sadaļas Marketo. Ja šis sadaļas nosaukums nav redzams, šāda veida savienojumi jums nav pieejami.

1. Ievadiet savu **[Marketo saraksta ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**. Saraksta ID ir tikai skaitliska vērtība. Piemēram, ja Marketo saraksta ID ir ST12345A7, noņemiet rakstzīmi pirms un pēc cipariem un ievadiet `12345`. 

1. **Sadaļā Datu saskaņošana** atlasiet vismaz vienu lauku, kas apzīmē klienta e-pasta adresi vai klienta Marketo ID. 

1. Ja vēlaties, varat eksportēt **Vārdu**, **Uzvārdu**, **Pilsētu**, **Pavalsti** un **Valsti/reģionu**, lai izveidotu personalizētākus e-pastus. Atlasiet **Pievienot atribūtu**, lai kartētu šos laukus.

1. Atlasiet segmentus, kurus vēlaties eksportēt. Kopsummā var eksportēt līdz 1 000 000 klientu profilu uz Marketo.

1. Atlasiet vienumu **Saglabāt**.

Eksporta saglabāšana automātiski nepalaiž eksportu.

Eksports tiek palaists ar katru [plānoto atsvaidzināšanu](system.md#schedule-tab). Varat arī [eksportēt datus pēc pieprasījuma](export-destinations.md#run-exports-on-demand). Marketo tagad varat atrast jūsu segmentus sadaļā [Marketo saraksti](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).


## <a name="data-privacy-and-compliance"></a>Datu konfidencialitāte un atbilstība

Ja iespējojat Dynamics 365 Customer Insights datu pārsūtīšanu uz Marketo, jūs atļaujat datu pārsūtīšanu ārpus atbilstības robežām Dynamics 365 Customer Insights, ieskaitot iespējami sensitīvus datus, piemēram, personas datus. Microsoft šos datus pārsūtīs pēc jūsu norādēm, bet jūs esat atbildīgs par to, lai nodrošinātu Marketo atbilstību konfidencialitātes vai drošības saistībām, kas jums varētu rasties. Papildinformāciju skatiet rakstā [Microsoft Privātuma paziņojums](https://go.microsoft.com/fwlink/?linkid=396732).
Jūsu Dynamics 365 Customer Insights administrators var noņemt šo eksportēšanas galamērķi jebkurā laikā, lai pārtrauktu izmantot šo funkcionalitāti.


[!INCLUDE [footer-include](includes/footer-banner.md)]
