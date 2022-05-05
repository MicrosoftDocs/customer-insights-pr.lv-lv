---
title: Eksportēt Customer Insights datus uz Braze
description: Uzziniet, kā konfigurēt savienojumu un eksportēt uz Braze.
ms.date: 03/29/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: bfc9b34506dc3385b5edf12b31e74d05f2d20655
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643151"
---
# <a name="export-segment-lists-to-braze-preview"></a>Segmentu sarakstu eksportēšana uz Braze (priekšskatījums)

Eksportējiet vienoto klientu profilu segmentus uz Braze un izmantojiet tos mārketinga aktivitātēm.

## <a name="prerequisites"></a>Priekšnoteikumi

-   Jums ir [Braze konts](https://www.braze.com/) un atbilstoši administratora akreditācijas dati.
-   Programmā Customer Insights ir [konfigurēti](segments.md) segmenti.
-   Eksportēto segmentu vienotajos klientu profilos ir lauks, kas attēlo e-pasta adresi un Braze klienta ID. 

## <a name="known-limitations"></a>Zināmie ierobežojumi

- Eksportēšana uz Braze ir ierobežota līdz segmentiem.
- Līdz pat 1 miljonam klientu profilu eksportēšana uz Braze var aizņemt līdz pat 40 minūtēm. 
- Klientu profilu skaits, ko varat eksportēt uz Braze, ir atkarīgs no līguma ar Braze un ir ierobežots.

## <a name="set-up-connection-to-braze"></a>Iestatīt savienojumu ar Braze

1. Dodieties uz **Administrators** > **Savienojumi**.

1. Atlasiet **Pievienot savienojumu** un izvēlieties **Dzēst,** lai konfigurētu savienojumu.

1. Laukā **Parādāmais nosaukums** piešķiriet savienojumam atpazīstamu nosaukumu. Parādāmais nosaukums un nosaukuma veids raksturo šo savienojumu. Ir ieteicams izvēlēties nosaukumu, kas paskaidro savienojuma nolūku.

1. Izvēlieties, kurš var izmantot šo savienojumu. Ja nesāksit nekādas darbības, noklusējums būs Administratori. Papildinformāciju skatiet rakstā [Atļaut līdzstrādniekiem izmantot savienojumu eksportam](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Norādiet braze [API atslēgu](https://www.braze.com/docs/api/basics/), lai turpinātu pieteikties. 

1. Atlasiet **Piekrītu**, lai apstiprinātu **Datu konfidencialitāti un atbilstību**.

1. Atlasiet **Izveidot savienojumu**, lai inicializētu savienojumu ar Braze.

1. Atlasiet opciju **Pievienot sevi kā eksporta lietotāju** un sniedziet savus Customer Insights akreditācijas datus.

1. Lai pabeigtu savienošanu, atlasiet **Saglabāt**.

## <a name="configure-an-export"></a>Eksporta konfigurēšana

Šo eksportu varat konfigurēt, ja jums ir piekļuve šā veida pieslēgumam. Papildinformāciju skatiet rakstā [Atļaujas, kas nepieciešamas eksporta konfigurēšanai](export-destinations.md#set-up-a-new-export).

1. Pārejiet uz **Dati** > **Eksportēšana**.

1. Lai izveidotu jaunu eksportu, atlasiet **Pievienot galamērķi**.

1. Laukā **Savienojums eksportēšanai** izvēlieties savienojumu no sadaļas Braze. Ja šis sadaļas nosaukums nav redzams, šāda veida savienojumi jums nav pieejami.  

3. **Sadaļas** Datu saskaņošana **laukā E-pasts** atlasiet lauku, kas attēlo klienta e-pasta adresi, laukā "Klienta ID" atlasiet lauku, kas attēlo klienta Kļūdas ID. Ir nepieciešams eksportēt segmentus uz Braze. Braze segmenti tiks izveidoti ar tādu pašu segmenta nosaukumu kā programmā Dynamics 365 Customer Insights. Datu saskaņošanai var izvēlēties papildu neobligātus laukus. 

1. Atlasiet **Saglabāt**.

Eksporta saglabāšana automātiski nepalaiž eksportu.

Eksports tiek palaists ar katru [plānoto atsvaidzināšanu](system.md#schedule-tab). Varat arī [eksportēt datus pēc pieprasījuma](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Datu konfidencialitāte un atbilstība

Kad iespējojat Dynamics 365 Customer Insights pārsūtīt datus uz Braze, jūs atļaujat pārsūtīt datus ārpus atbilstības robežas, tostarp potenciāli sensitīvus Dynamics 365 Customer Insights datus, piemēram, Personas datus. Microsoft pārsūtīs šādus datus pēc jūsu norādījumiem, bet jūs esat atbildīgs par to, lai Braze atbilstu visiem jūsu pienākumiem konfidencialitātes vai drošības jomā. Papildinformāciju skatiet rakstā [Microsoft Privātuma paziņojums](https://go.microsoft.com/fwlink/?linkid=396732).

Jūsu Dynamics 365 Customer Insights administrators var noņemt šo eksportēšanas galamērķi jebkurā laikā, lai pārtrauktu izmantot šo funkcionalitāti.
