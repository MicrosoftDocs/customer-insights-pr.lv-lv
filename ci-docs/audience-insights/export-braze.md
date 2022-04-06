---
title: Customer Insights datu eksportēšana uz Braze
description: Uzziniet, kā konfigurēt savienojumu un eksportēt uz Braze.
ms.date: 03/29/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8d7cf95c1f157c771b2d655346464e5af03d73b9
ms.sourcegitcommit: 5bd07f3a1288f003704acd576741cf6aedc1ac33
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 03/31/2022
ms.locfileid: "8524598"
---
# <a name="export-segment-lists-to-braze-preview"></a>Segmentu sarakstu eksportēšana uz Braze (priekšskatījums)

Eksportējiet vienoto klientu profilu segmentus uz Braze un izmantojiet tos mārketinga aktivitātēm.

## <a name="prerequisites"></a>Priekšnoteikumi

-   Jums ir [Braze konts](https://www.braze.com/) un atbilstoši administratora akreditācijas dati.
-   Jums ir [konfigurēti segmenti](segments.md) auditorijas ieskatos.
-   Vienotajos klientu profilos eksportētajos segmentos ir lauks, kas apzīmē e-pasta adresi un Braze klienta ID. 

## <a name="known-limitations"></a>Zināmie ierobežojumi

- Eksportēšana uz Braze ir ierobežota līdz segmentiem.
- Līdz 1 miljonam klientu profilu eksportēšana uz Braze var ilgt līdz 40 minūtēm. 
- Klientu profilu skaits, ko varat eksportēt uz Braze, ir atkarīgs un ierobežots no līguma ar Braze.

## <a name="set-up-connection-to-braze"></a>Iestatīt savienojumu ar Braze

1. Dodieties uz **Administrators** > **Savienojumi**.

1. Atlasiet **Pievienot savienojumu** un izvēlieties **Braze**, lai konfigurētu savienojumu.

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

1. Laukā **Savienojums eksportam** izvēlieties savienojumu no sadaļas Braze. Ja šis sadaļas nosaukums nav redzams, šāda veida savienojumi jums nav pieejami.  

3. **Sadaļas** Datu atbilstība **laukā E-pasts** atlasiet lauku, kas pārstāv klienta e-pasta adresi, laukā "Klienta ID" atlasiet lauku, kas pārstāv klienta Braze ID. Ir nepieciešams eksportēt segmentus uz Braze. Segmenti programmā Braze tiks izveidoti ar tādu pašu segmenta nosaukumu kā programmā Dynamics 365 Customer Insights. Datu salīdzināšanai var izvēlēties papildu neobligātus laukus. 

1. Atlasiet **Saglabāt**.

Eksporta saglabāšana automātiski nepalaiž eksportu.

Eksports tiek palaists ar katru [plānoto atsvaidzināšanu](system.md#schedule-tab). Varat arī [eksportēt datus pēc pieprasījuma](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Datu konfidencialitāte un atbilstība

Kad iespējojat Dynamics 365 Customer Insights datu pārsūtīšanu Braze, jūs atļaujat pārsūtīt datus ārpus atbilstības robežām, tostarp potenciāli sensitīvus Dynamics 365 Customer Insights datus, piemēram, Personas datus. Korporācija Microsoft pārsūtīs šādus datus pēc jūsu norādījumiem, taču jūs esat atbildīgs par to, lai Braze atbilstu visām jūsu konfidencialitātes vai drošības saistībām. Papildinformāciju skatiet rakstā [Microsoft Privātuma paziņojums](https://go.microsoft.com/fwlink/?linkid=396732).

Jūsu Dynamics 365 Customer Insights administrators var noņemt šo eksportēšanas galamērķi jebkurā laikā, lai pārtrauktu izmantot šo funkcionalitāti.
