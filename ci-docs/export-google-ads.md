---
title: Segmentu eksportēšana uz Google Ads (priekšskatījums)
description: Uzziniet, kā konfigurēt savienojumu un eksportēt uz Google Ads.
ms.date: 03/31/2022
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: b7f08936d7d90322cb4e62396a2961fe06273b76
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082998"
---
# <a name="export-segments-to-google-ads-preview"></a>Segmentu eksportēšana uz Google Ads (priekšskatījums)

Eksportējiet vienoto klientu profilu segmentus uz Google Ads auditoriju sarakstu un izmantojiet tos, lai reklāma tiktu rādīta Google meklēšanā, Gmail, YouTube un Google Display Network. 


## <a name="prerequisites-for-connection"></a>Savienojuma priekšnosacījumi

-   Jums ir [Google Ads konts](https://ads.google.com/) un atbilstošie administratora akreditācijas dati.
-   Jūs atbilstat [Klientu atbilstības politikas](https://support.google.com/adspolicy/answer/6299717) prasībām.
-   Jūs atbilstat [atkārtota mārketinga adresātu saraksta izmēru](https://support.google.com/google-ads/answer/7558048) prasībām.
-   Jums ir [konfigurēti segmenti](segments.md).
-   Vienoti klientu profili eksportētajos segmentos satur laukus, kuros norādīta e-pasta adrese, tālrunis, mobilā reklāmdevēja ID, trešās puses lietotāja ID vai adrese.

## <a name="known-limitations"></a>Zināmie ierobežojumi

- Eksportēšana uz Google Ads ir ierobežota līdz segmentiem.
- Eksportējot segmentus, kuru kopējais klientu profilu skaits ir 1 miljons, pakalpojumu sniedzēju puses ierobežojumu dēļ var ilgt 30 minūtes. 
- Google Ads savienošana var aizņemt līdz 48 stundām.

## <a name="set-up-connection-to-google-ads"></a>Savienojuma ar Google Ads iestatīšana

1. Dodieties uz **Administrators** > **Savienojumi**.

1. Atlasiet vienumu **Pievienot savienojumu** un atlasiet **Google Ads**, lai konfigurētu savienojumu.

1. Laukā **Parādāmais nosaukums** piešķiriet savienojumam atpazīstamu nosaukumu. Parādāmais nosaukums un nosaukuma veids raksturo šo savienojumu. Ir ieteicams izvēlēties nosaukumu, kas paskaidro savienojuma nolūku.

1. Izvēlieties, kurš var izmantot šo savienojumu. Ja nesāksit nekādas darbības, noklusējums būs Administratori. Papildinformāciju skatiet rakstā [Atļaut līdzstrādniekiem izmantot savienojumu eksportam](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Ievadiet savu **[Google Ads klienta ID](https://support.google.com/google-ads/answer/1704344)**.

1. Atlasiet **Piekrītu**, lai apstiprinātu **Datu konfidencialitāti un atbilstību**.

1. Atlasiet **Autentificēties ar Google Ads** un sniedziet savus Google Ads akreditācijas datus.

1. Atlasiet opciju **Pievienot sevi kā eksporta lietotāju** un sniedziet savus Customer Insights akreditācijas datus.

1. Lai pabeigtu savienošanu, atlasiet **Saglabāt**. 

## <a name="configure-an-export"></a>Eksporta konfigurēšana

Šo eksportu varat konfigurēt, ja jums ir piekļuve šā veida pieslēgumam. Papildinformāciju skatiet rakstā [Atļaujas, kas nepieciešamas eksporta konfigurēšanai](export-destinations.md#set-up-a-new-export).

1. Pārejiet uz **Dati** > **Eksportēšana**.

1. Lai izveidotu jaunu eksportu, atlasiet **Pievienot galamērķi**.

1. Laukā **Savienošana eksportam** atlasiet savienojumu no sadaļas Google Ads. Ja neredzat šo sadaļas nosaukumu, tad jums nav pieejami šī tipa savienojumi.

1. Ja vēlaties izveidot jaunu mērķauditoriju, atstājiet lauku Google auditorijas ID tukšu. Mēs automātiski izveidosim jaunu mērķauditoriju jūsu Google Ads kontā un izmantosim eksportētā segmenta nosaukumu. Ja vēlaties atjaunināt esošu Google Ads mērķauditoriju, ievadiet savu [Google Ads mērķauditorijas ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)

1. **Sadaļā Datu saskaņošana atlasiet vienu vai vairākus eksportējamos** datu laukus un atlasiet lauku, kas programmā Customer Insights attēlo atbilstošos datu laukus.

1. Atlasiet segmentus, kurus vēlaties eksportēt. 

Eksporta saglabāšana automātiski nepalaiž eksportu.

Eksports tiek palaists ar katru [plānoto atsvaidzināšanu](system.md#schedule-tab). 

Varat arī [eksportēt datus pēc pieprasījuma](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Datu konfidencialitāte un atbilstība

Ja iespējojat Dynamics 365 Customer Insights datu pārsūtīšanai uz Google Ads, jūs atļaujat datu pārsūtīšanu ārpus atbilstības robežām Dynamics 365 Customer Insights, ieskaitot iespējami sensitīvus datus, piemēram, personas datus. Microsoft šos datus pārsūtīs pēc jūsu norādēm, bet jūs esat atbildīgs par to, lai nodrošinātu Google Ads atbilstību konfidencialitātes vai drošības saistībām, kas jums varētu rasties. Papildinformāciju skatiet rakstā [Microsoft Privātuma paziņojums](https://go.microsoft.com/fwlink/?linkid=396732).
Jūsu Dynamics 365 Customer Insights administrators var noņemt šo eksportēšanas galamērķi jebkurā laikā, lai pārtrauktu izmantot šo funkcionalitāti.


[!INCLUDE [footer-include](includes/footer-banner.md)]
