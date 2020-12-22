---
title: Customer Insights datu eksportēšana uz Google Ads
description: Uzziniet, kā konfigurēt savienojumu ar Google Ads.
ms.date: 11/18/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 06aa0b6ff3125d8735adc8c8f9f6dad69087d9f8
ms.sourcegitcommit: ff824bbbd31fd666ab0da682bf48ea31580d242c
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 11/18/2020
ms.locfileid: "4568469"
---
# <a name="connector-for-google-ads-preview"></a>Google Ads savienotājs (priekšskatījums)

Eksportējiet klientu profilu unificētos segmentus uz Google Ads auditorijas sarakstu un izmantojiet tos reklāmām pakalpojumā Google Search, Gmail, YouTube un Google Display Network. 

## <a name="prerequisites"></a>Priekšnosacījumi

-   Jums ir [Google Ads konts](https://ads.google.com/) un atbilstošie administratora akreditācijas dati.
-   Google Ads ir esošas auditorijas un attiecīgie ID. Papildinformāciju skatiet rakstā [Google Ads auditorijas](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).
-   Jums ir [konfigurēti segmenti](segments.md)
-   Eksportētajos segmentos vienotajiem klientu profiliem ir lauki, kas norāda e-pasta adresi, vārdu un uzvārdu.

## <a name="connect-to-google-ads"></a>Izveidot savienojumu ar Google Ads

1. Dodieties uz sadaļu **Administrators** > **Eksportēšanas galamērķi**.

1. Sadaļā **Google Ads** atlasiet **Iestatīt**.

1. Piešķiriet eksportēšanas galamērķim atpazīstamu nosaukumu laukā **Parādāmais nosaukums**.

1. Ievadiet savu **[Google Ads klienta ID](https://support.google.com/google-ads/answer/1704344)**.

1. Ievadiet savas **[Google Ads apstiprinātu izstrādātāja marķieri](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.

1. Atlasiet **Piekrītu**, lai apstiprinātu **Datu privātumu un atbilstību**.

1. Ievadiet savas **[Google reklāmu auditorijas ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** un atlasiet opciju **Izveidot savienojumu**, lai inicializētu savienojumu ar Google Ads.

1. Atlasiet **Autentificēties ar Google Ads** un sniedziet savus Google Ads akreditācijas datus.

1. Atlasiet opciju **Pievienot sevi kā eksporta lietotāju** un sniedziet savus Customer Insights akreditācijas datus.

   :::image type="content" source="media/export-segments-googleads.PNG" alt-text="Eksportēt ekrānuzņēmumu Google Ads savienojumā":::

1. Lai konfigurētu eksportēšanu, atlasiet **Tālāk**.

## <a name="configure-the-connector"></a>Savienotāja konfigurēšana

1. Sadaļas **Datu atbilstības** laukā **E-pasts** atlasiet lauku, kas iekļauts vienotajā klientu profilā, kas pārstāv klienta e-pasta adresi. Atkārtojiet šīs pašas darbības ar laukiem **Vārds** un **Uzvārds**.

1. Atlasiet segmentus, kurus vēlaties eksportēt. Kopsummā varat eksportēt līdz 1 000 000 klientu profilu uz Google Ads.

1. Atlasiet vienumu **Saglabāt**.

## <a name="export-the-data"></a>Datu eksportēšana

Datus var [eksportēt pēc pieprasījuma](export-destinations.md). Eksportēšana arī tiks palaista ar katru [plānoto atsvaidzināšanu](system.md#schedule-tab). Google Ads tagad varat atrast jūsu segmentus sadaļā [Google Ads auditorija](https://support.google.com/google-ads/answer/7558048?hl=en/).

## <a name="known-limitations"></a>Zināmie ierobežojumi

- Līdz 1 000 000 profilu, eksportējot uz Google Ads.
- Eksportēšana uz Google Ads ir ierobežota līdz segmentiem.
- Segmentu eksportēšanai kopā ar 1 000 000 profilu var būt nepieciešamas 5 minūtes, jo pastāv ierobežojumi no pakalpojuma sniedzēja puses. 
- Google Ads savienošana var aizņemt līdz 48 stundām.

## <a name="data-privacy-and-compliance"></a>Datu konfidencialitāte un atbilstība

Ja iespējojat Dynamics 365 Customer Insights datu pārsūtīšanai uz Google Ads, jūs atļaujat datu pārsūtīšanu ārpus atbilstības robežām Dynamics 365 Customer Insights, ieskaitot iespējami sensitīvus datus, piemēram, personas datus. Microsoft šos datus pārsūtīs pēc jūsu norādēm, bet jūs esat atbildīgs par to, lai nodrošinātu Google Ads atbilstību konfidencialitātes vai drošības saistībām, kas jums varētu rasties. Papildinformāciju skatiet rakstā [Microsoft Privātuma paziņojums](https://go.microsoft.com/fwlink/?linkid=396732).
Jūsu Dynamics 365 Customer Insights administrators var noņemt šo eksportēšanas galamērķi jebkurā laikā, lai pārtrauktu izmantot šo funkcionalitāti.
