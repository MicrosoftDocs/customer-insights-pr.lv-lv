---
title: Customer Insights datu eksportēšana uz ActiveCampaign
description: Uzziniet, kā konfigurēt savienojumu un eksportēt uz ActiveCampaign.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 4fbdd5a51a3df35d31ad072eef64d20ee967d7ee
ms.sourcegitcommit: 23c8973a726b15050e368cc6e0aab78b266a89f6
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 10/08/2021
ms.locfileid: "7618162"
---
# <a name="export-segments-to-activecampaign-preview"></a>Segmentu eksportēšana uz ActiveCampaign (priekšskatījums)

Eksportējiet vienoto klientu profilu segmentus uz ActiveCampaign un izmantojiet tos mārketinga darbībām.

## <a name="prerequisites"></a>Priekšnosacījumi

-   Jums ir [ActiveCampaign konts](https://www.activecampaign.com/) un atbilstošie administratora akreditācijas dati.
-   Jums ir [konfigurēti segmenti](segments.md) auditorijas ieskatos.
-   Eksportētajos segmentos vienoto klientu profilos ir lauks ar e-pasta adresi.

## <a name="known-limitations"></a>Zināmie ierobežojumi

- Uz programmu ActiveCampaign var eksportēt līdz pat 1 miljoniem klientu profilu, un to pabeigšana var ilgt līdz 90 minūtēm.
- Eksportēšana uz ActiveCampaign attiecas tikai uz segmentiem.
- To klientu profilu skaits, ko var eksportēt uz ActiveCampaign, ir atkarīgs no jūsu līguma ar ActiveCampaign.

## <a name="set-up-connection-to-activecampaign"></a>Savienojuma izveide ar ActiveCampaign

1. Dodieties uz **Administrators** > **Savienojumi**.

1. Atlasiet vienumu **Pievienot savienojumu** un izvēlieties **ActiveCampaign**, lai konfigurētu savienojumu.

1. Laukā **Parādāmais nosaukums** piešķiriet savienojumam atpazīstamu nosaukumu. Parādāmais nosaukums un nosaukuma veids raksturo šo savienojumu. Ir ieteicams izvēlēties nosaukumu, kas paskaidro savienojuma nolūku.

1. Izvēlieties, kurš var izmantot šo savienojumu. Pēc noklusējuma tie ir tikai administratori. Papildinformāciju skatiet rakstā [Atļaut līdzstrādniekiem izmantot savienojumu eksportam](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Ievadiet savu [ActiveCampaign API atslēgu un REST galapunkta resursdatora nosaukumu](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key). REST galapunkta resursdatora nosaukums ir tikai viesošanas nosaukums bez https://. 

1. Atlasiet **Piekrītu**, lai apstiprinātu **Datu konfidencialitāti un atbilstību**.

1. Atlasiet **Savienot**, lai uzsāktu savienojuma izveidi ar ActiveCampaign.

1. Atlasiet opciju **Pievienot sevi kā eksporta lietotāju** un sniedziet savus Customer Insights akreditācijas datus.

1. Lai pabeigtu savienošanu, atlasiet **Saglabāt**.

## <a name="configure-an-export"></a>Eksporta konfigurēšana

Šo eksportu varat konfigurēt, ja jums ir piekļuve šā veida pieslēgumam. Papildinformāciju skatiet rakstā [Atļaujas, kas nepieciešamas eksporta konfigurēšanai](export-destinations.md#set-up-a-new-export).

1. Pārejiet uz **Dati** > **Eksportēšana**.

1. Lai izveidotu jaunu eksportu, atlasiet **Pievienot galamērķi**.

1. Laukam **Savienojums eksportēšanai** izvēlieties savienojumu no ActiveCampaign sadaļas. Ja šis sadaļas nosaukums nav redzams, šāda veida savienojumi jums nav pieejami.

1. Ievadiet savu [**ActiveCampaign saraksta ID**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).    

1. **Datu atbilstības noteikšanas** sadaļas laukā **E-pasts** atlasiet lauku, kas norāda klienta e-pasta adresi. Tas ir nepieciešams, lai eksportētu segmentus uz ActiveCampaign. Pēc izvēles, varat eksportēt vārdu, uzvārdu un tālruņa numuru, lai izveidotu personalizētākus e-pasta ziņojumus. Atlasiet Pievienot atribūtu, lai kartētu šos laukus.

1. Atlasiet vienumu **Saglabāt**.

Eksporta saglabāšana automātiski nepalaiž eksportu.

Eksports tiek palaists ar katru [plānoto atsvaidzināšanu](system.md#schedule-tab). Varat arī [eksportēt datus pēc pieprasījuma](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Datu konfidencialitāte un atbilstība

Iespējojot Dynamics 365 Customer Insights datu pārsūtīšanai uz ActiveCampaign, jūs atļaujat datu pārsūtīšanu ārpus atbilstības robežas, kas paredzēta Dynamics 365 Customer Insights, ieskaitot potenciāli sensitīvus datus, piemēram, personas datus. Microsoft šos datus pārsūtīs pēc jūsu norādījuma, bet jūs esat atbildīgs par to, lai ActiveCampaign atbilstu visām jūsu konfidencialitātes vai drošības saistībām. Papildinformāciju skatiet rakstā [Microsoft Privātuma paziņojums](https://go.microsoft.com/fwlink/?linkid=396732).

Jūsu Dynamics 365 Customer Insights administrators var noņemt šo eksportēšanas galamērķi jebkurā laikā, lai pārtrauktu izmantot šo funkcionalitāti.
