---
title: Segmentu eksportēšana uz iterable (priekšskatījums)
description: Uzziniet, kā konfigurēt savienojumu un eksportēt uz iterable.
ms.date: 03/29/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 98d5aeab6b0e932d291213053d509ec72da82e47
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 06/29/2022
ms.locfileid: "9052244"
---
# <a name="export-segments-to-iterable-preview"></a>Segmentu eksportēšana uz iterable (priekšskatījums)

Eksportējiet vienotu klientu profilu segmentus uz Iterable un izmantojiet tos mārketinga aktivitātēm.

## <a name="prerequisites"></a>Priekšnoteikumi

-   Jums ir [iterable konts](https://iterable.com/) un atbilstošie administratora akreditācijas dati.
-   Jūs esat [konfigurējis segmentus](segments.md) programmā Customer Insights.
-   Eksportētajos segmentos vienotajiem klientu profiliem ir lauks, kas norāda e-pasta adresi.

## <a name="known-limitations"></a>Zināmie ierobežojumi

- Eksports uz Iterable attiecas tikai uz segmentiem.
- Eksportējot līdz 1 miljonam klientu profilu uz Iterable, var paiet līdz pat 30 minūtēm. 
- Klientu profilu skaits, ko varat eksportēt uz Iterable, ir atkarīgs un ierobežots no jūsu līguma ar Iterable.

## <a name="set-up-connection-to-iterable"></a>Savienojuma ar iterable iestatīšana

1. Dodieties uz **Administrators** > **Savienojumi**.

1. Atlasiet **Pievienot savienojumu** un izvēlieties **Iterable**, lai konfigurētu savienojumu.

1. Laukā **Parādāmais nosaukums** piešķiriet savienojumam atpazīstamu nosaukumu. Parādāmais nosaukums un nosaukuma veids raksturo šo savienojumu. Ir ieteicams izvēlēties nosaukumu, kas paskaidro savienojuma nolūku.

1. Izvēlieties, kurš var izmantot šo savienojumu. Ja nesāksit nekādas darbības, noklusējums būs Administratori. Papildinformāciju skatiet rakstā [Atļaut līdzstrādniekiem izmantot savienojumu eksportam](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Norādiet savu [iterable API atslēgu](https://support.iterable.com/hc/en-us/articles/360043464871), lai turpinātu pieteikties. 

1. Atlasiet **Piekrītu**, lai apstiprinātu **Datu konfidencialitāti un atbilstību**.

1. Atlasiet **Izveidot savienojumu**, lai inicializētu savienojumu ar iterable.

1. Atlasiet opciju **Pievienot sevi kā eksporta lietotāju** un sniedziet savus Customer Insights akreditācijas datus.

1. Lai pabeigtu savienošanu, atlasiet **Saglabāt**.

## <a name="configure-an-export"></a>Eksporta konfigurēšana

Šo eksportu varat konfigurēt, ja jums ir piekļuve šā veida pieslēgumam. Papildinformāciju skatiet rakstā [Atļaujas, kas nepieciešamas eksporta konfigurēšanai](export-destinations.md#set-up-a-new-export).

1. Pārejiet uz **Dati** > **Eksportēšana**.

1. Lai izveidotu jaunu eksportu, atlasiet **Pievienot galamērķi**.

1. **Laukā Savienojums eksportēšanai** izvēlieties savienojumu no sadaļas Iterable. Ja šis sadaļas nosaukums nav redzams, šāda veida savienojumi jums nav pieejami.

3. **Datu atbilstības noteikšanas** sadaļas laukā **E-pasts** atlasiet lauku, kas norāda klienta e-pasta adresi. Tas ir nepieciešams, lai eksportētu segmentus uz Iterable.Iterable izveidotais saraksts saņems tieši tādu pašu nosaukumu kā jūsu segmenta nosaukums .Dynamics 365 Customer Insights

1. Atlasiet **Saglabāt**.

Eksporta saglabāšana automātiski nepalaiž eksportu.

Eksports tiek palaists ar katru [plānoto atsvaidzināšanu](system.md#schedule-tab). Varat arī [eksportēt datus pēc pieprasījuma](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Datu konfidencialitāte un atbilstība

Kad jūs iespējojat Dynamics 365 Customer Insights datu pārsūtīšanu uz Iterable, jūs atļaujat pārsūtīt datus ārpus atbilstības robežas, tostarp potenciāli sensitīvus Dynamics 365 Customer Insights datus, piemēram, Personas datus. Microsoft pārsūtīs šādus datus pēc jūsu norādījumiem, taču jūs esat atbildīgs par to, lai iterable izpildītu visas jūsu iespējamās konfidencialitātes vai drošības saistības. Papildinformāciju skatiet rakstā [Microsoft Privātuma paziņojums](https://go.microsoft.com/fwlink/?linkid=396732).

Jūsu Dynamics 365 Customer Insights administrators var noņemt šo eksportēšanas galamērķi jebkurā laikā, lai pārtrauktu izmantot šo funkcionalitāti.
