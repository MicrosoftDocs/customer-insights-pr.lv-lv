---
title: Customer Insights datu eksportēšana uz Google Ads
description: Uzziniet, kā konfigurēt savienojumu un eksportēt uz Google Ads.
ms.date: 09/27/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: c958f58c927b76364f305dad8f524dde29b2a638
ms.sourcegitcommit: f1e3cc51ea4cf68210eaf0210ad6e14b15ac4fe8
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 09/27/2021
ms.locfileid: "7558981"
---
# <a name="export-segments-to-google-ads-preview"></a>Segmentu eksportēšana uz Google Ads (priekšskatījums)

Eksportējiet vienoto klientu profilu segmentus uz Google Ads auditoriju sarakstu un izmantojiet tos, lai reklāma tiktu rādīta Google meklēšanā, Gmail, YouTube un Google Display Network. 

> [!IMPORTANT]
> Pašlaik jūs varat izveidot jaunu savienojumu un eksportēt datus uz Google Ads tikai tad, ja jums jau ir apstiprināts Google Ads izstrādātāja marķieris. Politikas izmaiņu dēļ mēs drīz atjaunināsim Google Ads eksportēšanu un nodrošināsim eksportēšanas opciju, kurai nebūs nepieciešams izstrādātāja marķieris, lai nodrošinātu jūsu pieredzes turpināšanu un vienkāršotu eksportēšanu uz Google Ads. Lai atvieglotu pāreju uz jauno eksportēšanas opciju, ieteicams neiestatīt vairāk savienojumu ar Google Ads.

## <a name="prerequisites-for-connection"></a>Savienojuma priekšnosacījumi

-   Jums ir [Google Ads konts](https://ads.google.com/) un atbilstošie administratora akreditācijas dati.
-   Jums ir [apstiprināts Google Ads izstrādātāja marķieris](https://developers.google.com/google-ads/api/docs/first-call/dev-token). 
-   Jūs atbilstat [Klientu atbilstības politikas](https://support.google.com/adspolicy/answer/6299717) prasībām.
-   Jūs atbilstat [atkārtota mārketinga adresātu saraksta izmēru](https://support.google.com/google-ads/answer/7558048) prasībām.
-   Google Ads ir esošas auditorijas un attiecīgie ID. Papildinformāciju skatiet rakstā [Google Ads auditorijas](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).
-   Jums ir [konfigurēti segmenti](segments.md).
-   Eksportētajos segmentos vienotajiem klientu profiliem ir lauki, kas norāda e-pasta adresi, vārdu un uzvārdu.

## <a name="known-limitations"></a>Zināmie ierobežojumi

- Līdz 1 000 000 profilu, eksportējot uz Google Ads.
- Eksportēšana uz Google Ads ir ierobežota līdz segmentiem.
- Segmentu eksportēšanai kopā ar 1 000 000 profilu var būt nepieciešamas 5 minūtes, jo pastāv ierobežojumi no pakalpojuma sniedzēja puses. 
- Google Ads savienošana var aizņemt līdz 48 stundām.

## <a name="set-up-connection-to-google-ads"></a>Savienojuma ar Google Ads iestatīšana

1. Dodieties uz **Administrators** > **Savienojumi**.

1. Atlasiet vienumu **Pievienot savienojumu** un atlasiet **Google Ads**, lai konfigurētu savienojumu.

1. Laukā **Parādāmais nosaukums** piešķiriet savienojumam atpazīstamu nosaukumu. Parādāmais nosaukums un nosaukuma veids raksturo šo savienojumu. Ir ieteicams izvēlēties nosaukumu, kas paskaidro savienojuma nolūku.

1. Izvēlieties, kurš var izmantot šo savienojumu. Ja nesāksit nekādas darbības, noklusējums būs Administratori. Papildinformāciju skatiet rakstā [Atļaut līdzstrādniekiem izmantot savienojumu eksportam](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Ievadiet savu **[Google Ads klienta ID](https://support.google.com/google-ads/answer/1704344)**.

1. Ievadiet savas **[Google Ads apstiprinātu izstrādātāja marķieri](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.

1. Atlasiet **Piekrītu**, lai apstiprinātu **Datu konfidencialitāti un atbilstību**.

1. Atlasiet **Autentificēties ar Google Ads** un sniedziet savus Google Ads akreditācijas datus.

1. Atlasiet opciju **Pievienot sevi kā eksporta lietotāju** un sniedziet savus Customer Insights akreditācijas datus.

1. Lai pabeigtu savienošanu, atlasiet **Saglabāt**. 

## <a name="configure-an-export"></a>Eksporta konfigurēšana

Šo eksportu varat konfigurēt, ja jums ir piekļuve šā veida pieslēgumam. Papildinformāciju skatiet rakstā [Atļaujas, kas nepieciešamas eksporta konfigurēšanai](export-destinations.md#set-up-a-new-export).

1. Pārejiet uz **Dati** > **Eksportēšana**.

1. Lai izveidotu jaunu eksportu, atlasiet **Pievienot galamērķi**.

1. Laukā **Savienošana eksportam** atlasiet savienojumu no sadaļas Google Ads. Ja neredzat šo sadaļas nosaukumu, tad jums nav pieejami šī tipa savienojumi.

1. Ievadiet savas **[Google reklāmu auditorijas ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** un atlasiet opciju **Izveidot savienojumu**, lai inicializētu savienojumu ar Google Ads.

1. Sadaļas **Datu atbilstības** laukā **E-pasts** atlasiet lauku, kas iekļauts vienotajā klientu profilā, kas pārstāv klienta e-pasta adresi.

1. Atlasiet segmentus, kurus vēlaties eksportēt. Kopsummā varat eksportēt līdz 1 000 000 klientu profilu uz Google Ads.

Eksporta saglabāšana automātiski nepalaiž eksportu.

Eksports tiek palaists ar katru [plānoto atsvaidzināšanu](system.md#schedule-tab). 

Varat arī [eksportēt datus pēc pieprasījuma](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Datu konfidencialitāte un atbilstība

Ja iespējojat Dynamics 365 Customer Insights datu pārsūtīšanai uz Google Ads, jūs atļaujat datu pārsūtīšanu ārpus atbilstības robežām Dynamics 365 Customer Insights, ieskaitot iespējami sensitīvus datus, piemēram, personas datus. Microsoft šos datus pārsūtīs pēc jūsu norādēm, bet jūs esat atbildīgs par to, lai nodrošinātu Google Ads atbilstību konfidencialitātes vai drošības saistībām, kas jums varētu rasties. Papildinformāciju skatiet rakstā [Microsoft Privātuma paziņojums](https://go.microsoft.com/fwlink/?linkid=396732).
Jūsu Dynamics 365 Customer Insights administrators var noņemt šo eksportēšanas galamērķi jebkurā laikā, lai pārtrauktu izmantot šo funkcionalitāti.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
