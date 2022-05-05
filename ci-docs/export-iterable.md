---
title: Eksportēt Customer Insights datus uz Iterable
description: Uzziniet, kā konfigurēt savienojumu un eksportēt uz Iterable.
ms.date: 03/29/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 714a1323521be7d2f29ccaacd7799b2174e2937d
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643892"
---
# <a name="export-segment-lists-to-iterable-preview"></a>Eksportēt segmentu sarakstus uz Iterable (priekšskatījums)

Eksportēt vienoto klientu profilu segmentus uz Iterable un izmantot tos mārketinga aktivitātēm.

## <a name="prerequisites"></a>Priekšnoteikumi

-   Jums ir [iterable konts](https://iterable.com/) un atbilstoši administratora akreditācijas dati.
-   Programmā Customer Insights ir [konfigurēti](segments.md) segmenti.
-   Eksportētajos segmentos vienotajiem klientu profiliem ir lauks, kas norāda e-pasta adresi.

## <a name="known-limitations"></a>Zināmie ierobežojumi

- Eksportēšana uz Iterable attiecas tikai uz segmentiem.
- Eksportējot līdz 1 miljonam klientu profilu uz Iterable, var paiet līdz pat 30 minūtēm. 
- Klientu profilu skaits, ko varat eksportēt uz Iterable, ir atkarīgs no līguma ar Iterable un ierobežots.

## <a name="set-up-connection-to-iterable"></a>Iestatīt savienojumu ar Iterable

1. Dodieties uz **Administrators** > **Savienojumi**.

1. Atlasiet **Pievienot savienojumu** un izvēlieties **Iterable**, lai konfigurētu savienojumu.

1. Laukā **Parādāmais nosaukums** piešķiriet savienojumam atpazīstamu nosaukumu. Parādāmais nosaukums un nosaukuma veids raksturo šo savienojumu. Ir ieteicams izvēlēties nosaukumu, kas paskaidro savienojuma nolūku.

1. Izvēlieties, kurš var izmantot šo savienojumu. Ja nesāksit nekādas darbības, noklusējums būs Administratori. Papildinformāciju skatiet rakstā [Atļaut līdzstrādniekiem izmantot savienojumu eksportam](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Norādiet savu [Iterable API atslēgu](https://support.iterable.com/hc/en-us/articles/360043464871), lai turpinātu pieteikties. 

1. Atlasiet **Piekrītu**, lai apstiprinātu **Datu konfidencialitāti un atbilstību**.

1. Atlasiet **Izveidot savienojumu**, lai inicializētu savienojumu ar Iterable.

1. Atlasiet opciju **Pievienot sevi kā eksporta lietotāju** un sniedziet savus Customer Insights akreditācijas datus.

1. Lai pabeigtu savienošanu, atlasiet **Saglabāt**.

## <a name="configure-an-export"></a>Eksporta konfigurēšana

Šo eksportu varat konfigurēt, ja jums ir piekļuve šā veida pieslēgumam. Papildinformāciju skatiet rakstā [Atļaujas, kas nepieciešamas eksporta konfigurēšanai](export-destinations.md#set-up-a-new-export).

1. Pārejiet uz **Dati** > **Eksportēšana**.

1. Lai izveidotu jaunu eksportu, atlasiet **Pievienot galamērķi**.

1. Laukā **Savienojums eksportēšanai** izvēlieties savienojumu no sadaļas Iterable. Ja šis sadaļas nosaukums nav redzams, šāda veida savienojumi jums nav pieejami.

3. **Datu atbilstības noteikšanas** sadaļas laukā **E-pasts** atlasiet lauku, kas norāda klienta e-pasta adresi. Tas ir nepieciešams, lai eksportētu segmentus uz Iterable.Iterable izveidotais saraksts saņems tieši tādu pašu nosaukumu kā segmenta nosaukums programmā Dynamics 365 Customer Insights.

1. Atlasiet **Saglabāt**.

Eksporta saglabāšana automātiski nepalaiž eksportu.

Eksports tiek palaists ar katru [plānoto atsvaidzināšanu](system.md#schedule-tab). Varat arī [eksportēt datus pēc pieprasījuma](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Datu konfidencialitāte un atbilstība

Kad iespējojat Dynamics 365 Customer Insights pārsūtīt datus uz Iterable, jūs atļaujat pārsūtīt datus ārpus atbilstības robežas, tostarp potenciāli sensitīviem Dynamics 365 Customer Insights datiem, piemēram, Personas datiem. Microsoft pārsūtīs šādus datus pēc jūsu norādījumiem, bet jūs esat atbildīgs par to, lai Iterable izpildītu visus jūsu konfidencialitātes vai drošības pienākumus. Papildinformāciju skatiet rakstā [Microsoft Privātuma paziņojums](https://go.microsoft.com/fwlink/?linkid=396732).

Jūsu Dynamics 365 Customer Insights administrators var noņemt šo eksportēšanas galamērķi jebkurā laikā, lai pārtrauktu izmantot šo funkcionalitāti.
