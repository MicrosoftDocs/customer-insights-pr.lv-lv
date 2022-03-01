---
title: Customer Insights datu eksportēšana uz Sendinblue
description: Uzziniet, kā konfigurēt savienojumu un eksportēt uz Sendinblue.
ms.date: 06/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: be52554763b57e1c1ef2f960d52bbae79ac9827913c97ac73b429f66bbf4db37
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036064"
---
# <a name="export-segments-to-sendinblue-preview"></a>Segmentu eksportēšana uz Sendinblue (priekšskatījums)

Eksportējiet vienotos klienta profila segmentus, lai ģenerētu kampaņas, nodrošinātu e-pasta mārketingu un izmantotu specifiskas klientu grupas pakalpojumā Sendinblue.

## <a name="prerequisites-for-connection"></a>Savienojuma priekšnosacījumi

-   Jums ir [Sendinblue konts](https://www.sendinblue.com/) un atbilstošie administratora akreditācijas dati.
-   Sendinblue un atbilstošajos ID ir iekļauti jau esošie saraksti.
-   Jums ir [konfigurēti segmenti](segments.md).
-   Eksportētajos segmentos vienotajiem klientu profiliem ir lauks, kas norāda e-pasta adresi.

## <a name="known-limitations"></a>Zināmie ierobežojumi

- Vienā eksportēšanas reizē uz Sendinblue var eksportēt līdz 1 miljonam profilu.
- Eksportēšana uz Sendinblue attiecas tikai uz segmentiem.
- Segmentu eksportēšana, kur kopējais profilu skaits ir 1 miljons, var ilgt līdz 90 minūtēm. 
- Profilu skaits, ko var eksportēt uz Sendinblue ir atkarīgs un to ierobežo jūsu līgums ar Sendinblue.

## <a name="set-up-connection-to-sendinblue"></a>Savienojuma ar Sendinblue iestatīšana

1. Dodieties uz **Administrators** > **Savienojumi**.

1. Atlasiet vienumu **Pievienot savienojumu** un izvēlieties **Sendinblue**, lai konfigurētu savienojumu.

1. Laukā **Parādāmais nosaukums** piešķiriet savienojumam atpazīstamu nosaukumu. Parādāmais nosaukums un nosaukuma veids raksturo šo savienojumu. Ir ieteicams izvēlēties nosaukumu, kas paskaidro savienojuma nolūku.

1. Izvēlieties, kurš var izmantot šo savienojumu. Pēc noklusējuma ir tikai administratori. Papildinformāciju skatiet rakstā [Atļaut līdzstrādniekiem izmantot savienojumu eksportam](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Ievadiet savu **[Sendinblue API atslēgu](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)**.

1. Atlasiet **Es piekrītu**, lai apstiprinātu **Datu konfidencialitāti un atbilstību** un atlasiet **Savienot**, lai inicializētu savienojumu ar Sendinblue.

1. Atlasiet opciju **Pievienot sevi kā eksporta lietotāju** un sniedziet savus Customer Insights akreditācijas datus.

1. Lai pabeigtu savienošanu, atlasiet **Saglabāt**.

## <a name="configure-an-export"></a>Eksporta konfigurēšana

Šo eksportu varat konfigurēt, ja jums ir piekļuve šā veida pieslēgumam. Papildinformāciju skatiet rakstā [Atļaujas, kas nepieciešamas eksporta konfigurēšanai](export-destinations.md#set-up-a-new-export).

1. Pārejiet uz **Dati** > **Eksportēšana**.

1. Lai izveidotu jaunu eksportu, atlasiet **Pievienot galamērķi**.

1. Laukam **Savienojums eksportēšanai** izvēlieties savienojumu no Sendinblue sadaļas. Ja šis sadaļas nosaukums nav redzams, šāda veida savienojumi jums nav pieejami.

1. Ievadiet savu **Sendinblue saraksta ID** 

1. Sadaļas **Datu atbilstības** laukā **E-pasts** atlasiet lauku, kas iekļauts vienotajā klientu profilā, kas pārstāv klienta e-pasta adresi. 

1. Pēc izvēles, varat eksportēt **vārdu**, **uzvārdu** un **tālruņa numuru**, lai izveidotu personalizētākus e-pasta ziņojumus. Atlasiet **Pievienot atribūtu**, lai kartētu šos laukus.

1. Atlasiet segmentus, kurus vēlaties eksportēt. 

1. Atlasiet vienumu **Saglabāt**.

Eksporta saglabāšana automātiski nepalaiž eksportu.

Eksports tiek palaists ar katru [plānoto atsvaidzināšanu](system.md#schedule-tab). Varat arī [eksportēt datus pēc pieprasījuma](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Datu konfidencialitāte un atbilstība

Iespējojot Dynamics 365 Customer Insights datu pārsūtīšanai uz Sendinblue, jūs atļaujat datu pārsūtīšanu ārpus atbilstības robežas, kas paredzēta Dynamics 365 Customer Insights, ieskaitot potenciāli sensitīvus datus, piemēram, personas datus. Microsoft šos datus pārsūtīs pēc jūsu norādījuma, bet jūs esat atbildīgs par to, lai Sendinblue atbilstu visām jūsu konfidencialitātes vai drošības saistībām. Papildinformāciju skatiet rakstā [Microsoft Privātuma paziņojums](https://go.microsoft.com/fwlink/?linkid=396732).
Jūsu Dynamics 365 Customer Insights administrators var noņemt šo eksportēšanas galamērķi jebkurā laikā, lai pārtrauktu izmantot šo funkcionalitāti.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
