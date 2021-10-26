---
title: Customer Insights datu eksportēšana uz DotDigital
description: Uzziniet, kā konfigurēt savienojumu un eksportēt uz DotDigital.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3e3a79603f9f5746ee176d3d4299a30510c7459e
ms.sourcegitcommit: 23c8973a726b15050e368cc6e0aab78b266a89f6
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 10/08/2021
ms.locfileid: "7618392"
---
# <a name="export-segments-to-dotdigital-preview"></a>Segmentu eksportēšana uz DotDigital (priekšskatījums)

Eksportējiet vienoto klientu profilu segmentus uz DotDigital adrešu grāmatām un izmantojiet tās kampaņām, e-pasta mārketingā un klientu segmentu izveidei ar DotDigital. 

## <a name="prerequisites-for-a-connection"></a>Savienojuma priekšnosacījumi

-   Jums ir [DotDigital konts](https://dotdigital.com/) un esat izveidojis [API lietotāju](https://support.dotdigital.com/hc/articles/115001718730-How-do-I-create-an-API-user). Lai izveidotu savienojumu, jums ir jāizmanto API lietotāja akreditācijas dati
-   DotDigital ir esošas adrešu grāmatas un attiecīgie ID. ID var atrast URL, kad atlasāt un atverat adrešu grāmatu. Papildinformāciju skatiet vietnē [DotDigital adrešu grāmatas](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).
-   Jums ir [konfigurēti segmenti](segments.md) auditorijas ieskatos.
-   Eksportētajos segmentos vienotajiem klientu profiliem ir lauks, kas norāda e-pasta adresi.

## <a name="known-limitations"></a>Zināmie ierobežojumi

- Līdz 1 miljoniem klientu profilu vienai eksportēšanai uz DotDigital.
- Eksportēšana uz DotDigital ir ierobežota līdz segmentiem.
- Eksportējot segmentus, kuru kopējais klientu profilu skaits ir 1 miljonus klientu, pakalpojumu sniedzēju puses ierobežojumu dēļ var ilgt 3 stundas. 
- To klientu profilu skaits, kurus varat eksportēt uz DotDigital, ir atkarīgs un ierobežots atkarībā no jūsu līguma ar DotDigital.

## <a name="set-up-connection-to-dotdigital"></a>Savienojuma ar DotDigital iestatīšana

1. Dodieties uz **Administrators** > **Savienojumi**.

1. Atlasiet vienumu **Pievienot savienojumu** un atlasiet **DotDigital**, lai konfigurētu savienojumu.

1. Laukā **Parādāmais nosaukums** piešķiriet savienojumam atpazīstamu nosaukumu. Parādāmais nosaukums un nosaukuma veids raksturo šo savienojumu. Ir ieteicams izvēlēties nosaukumu, kas paskaidro savienojuma nolūku.

1. Izvēlieties, kurš var izmantot šo savienojumu. Ja nesāksit nekādas darbības, noklusējums būs Administratori. Papildinformāciju skatiet rakstā [Atļaut līdzstrādniekiem izmantot savienojumu eksportam](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Ievadiet savu **DotDigital API lietotājvārdu un paroli**. 

1. Ievadiet savu **[DotDigital adrešu grāmatas ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.

1. Atlasiet **Piekrītu**, lai apstiprinātu **Datu privātumu un atbilstību**.

1. Atlasiet **Izveidot savienojumu**, lai inicializētu savienojumu ar DotDigital.

1. Atlasiet opciju **Pievienot sevi kā eksporta lietotāju** un sniedziet savus Customer Insights akreditācijas datus.

1. Lai pabeigtu savienošanu, atlasiet **Saglabāt**. 

## <a name="configure-an-export"></a>Eksporta konfigurēšana

Šo eksportu varat konfigurēt, ja jums ir piekļuve šā veida pieslēgumam. Papildinformāciju skatiet rakstā [Atļaujas, kas nepieciešamas eksporta konfigurēšanai](export-destinations.md#set-up-a-new-export).

1. Pārejiet uz **Dati** > **Eksportēšana**.

1. Lai izveidotu jaunu eksportu, atlasiet **Pievienot galamērķi**.

1. Laukā **Savienošana eksportam** atlasiet savienojumu no sadaļas DotDigital. Ja šis sadaļas nosaukums nav redzams, šāda veida savienojumi jums nav pieejami.


1. **Datu atbilstības noteikšanas** sadaļas laukā **E-pasts** atlasiet lauku, kas norāda klienta e-pasta adresi. Veiciet tās pašas darbības ar citiem neobligātajiem laukiem, piemēram, **Vārds**, **Uzvārds**, **Pilns vārds**, **Dzimums** un **Pasta indekss**.

1. Atlasiet segmentus, kurus vēlaties eksportēt. Kopsummā var eksportēt līdz 1 000 000 klientu profilu uz DotDigital.

1. Atlasiet vienumu **Saglabāt**.

Eksporta saglabāšana automātiski nepalaiž eksportu.

Eksports tiek palaists ar katru [plānoto atsvaidzināšanu](system.md#schedule-tab). Varat arī [eksportēt datus pēc pieprasījuma](export-destinations.md#run-exports-on-demand). 
 
DotDigital tagad varat atrast savus segmentus [DotDigital adrešu grāmatās](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).


## <a name="data-privacy-and-compliance"></a>Datu konfidencialitāte un atbilstība

Ja iespējojat Dynamics 365 Customer Insights datu pārsūtīšanai uz DotDigital, jūs atļaujat datu pārsūtīšanu ārpus atbilstības robežām Dynamics 365 Customer Insights, ieskaitot iespējami sensitīvus datus, piemēram, personas datus. Microsoft šos datus pārsūtīs pēc jūsu norādēm, bet jūs esat atbildīgs par to, lai nodrošinātu DotDigital atbilstību konfidencialitātes vai drošības saistībām, kas jums varētu rasties. Papildinformāciju skatiet rakstā [Microsoft Privātuma paziņojums](https://go.microsoft.com/fwlink/?linkid=396732).
Jūsu Dynamics 365 Customer Insights administrators var noņemt šo eksportēšanas galamērķi jebkurā laikā, lai pārtrauktu izmantot šo funkcionalitāti.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
