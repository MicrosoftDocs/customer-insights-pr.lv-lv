---
title: Segmentu eksportēšana uz Braze (priekšskatījums)
description: Uzziniet, kā konfigurēt savienojumu un eksportēt uz Braze.
ms.date: 06/29/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 314a61f82c4040a8dbd6dff1dd5d92e20464f82a
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082683"
---
# <a name="export-segments-to-braze-preview"></a>Segmentu eksportēšana uz Braze (priekšskatījums)

Eksportējiet vienotu klientu profilu segmentus uz Braze un izmantojiet tos mārketinga aktivitātēm.

## <a name="prerequisites"></a>Priekšnoteikumi

- [Braze konts](https://www.braze.com/) un atbilstošie administratora akreditācijas dati.
- Esošie [segmenti Brazē](https://www.braze.com/docs/user_guide/engagement_tools/segments/creating_a_segment/).
- [Konfigurētie segmenti](segments.md) programmā Customer Insights.
- Vienoti klientu profili eksportētajos segmentos satur lauku, kas attēlo e-pasta adresi un Braze klienta ID.

## <a name="known-limitations"></a>Zināmie ierobežojumi

- Eksports uz Braze attiecas tikai uz segmentiem.
- Līdz pat 1 miljona klientu profilu eksportēšana uz Braze var aizņemt līdz pat 40 minūtēm.
- Klientu profilu skaits, ko varat eksportēt uz Braze, ir atkarīgs un ierobežots no jūsu līguma ar Braze.

## <a name="set-up-connection-to-braze"></a>Savienojuma ar Braze iestatīšana

1. Dodieties uz **Administrators** > **Savienojumi**.

1. Atlasiet **Pievienot savienojumu** un izvēlieties **Braze**, lai konfigurētu savienojumu.

1. Laukā **Parādāmais nosaukums** piešķiriet savienojumam atpazīstamu nosaukumu. Parādāmais nosaukums un nosaukuma veids raksturo šo savienojumu. Ir ieteicams izvēlēties nosaukumu, kas paskaidro savienojuma nolūku.

1. Izvēlieties, kurš var izmantot šo savienojumu. Ja nesāksit nekādas darbības, noklusējums būs Administratori. Papildinformāciju skatiet rakstā [Atļaut līdzstrādniekiem izmantot savienojumu eksportam](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Norādiet savu [Braze API atslēgu](https://www.braze.com/docs/api/basics/), lai turpinātu pieteikties.

1. Atlasiet **Piekrītu**, lai apstiprinātu **Datu konfidencialitāti un atbilstību**.

1. Atlasiet **Izveidot savienojumu**, lai inicializētu savienojumu ar Braze.

1. Atlasiet opciju **Pievienot sevi kā eksporta lietotāju** un sniedziet savus Customer Insights akreditācijas datus.

1. Lai pabeigtu savienošanu, atlasiet **Saglabāt**.

## <a name="configure-an-export"></a>Eksporta konfigurēšana

Šo eksportu varat konfigurēt, ja jums ir piekļuve šā veida pieslēgumam. Papildinformāciju skatiet rakstā [Atļaujas, kas nepieciešamas eksporta konfigurēšanai](export-destinations.md#set-up-a-new-export).

1. Pārejiet uz **Dati** > **Eksportēšana**.

1. Lai izveidotu jaunu eksportu, atlasiet **Pievienot galamērķi**.

1. **Laukā Savienojums eksportēšanai** izvēlieties savienojumu no sadaļas Braze. Ja neredzat šo sadaļu, jums nav pieejami šāda veida savienojumi.  

1. **Pievienojiet parādāmo nosaukumu** eksportēšanai.

1. Laukā Braze segmenta **IDENTIFIKATORS pievienojiet tā Braze segmenta API identifikatoru, uz** kuru vēlaties eksportēt. Jūs varat atrast identifikatoru segmenta informācijā Braze platformā.

1. **Datu atbilstības noteikšanas** sadaļas laukā **E-pasts** atlasiet lauku, kas norāda klienta e-pasta adresi. Laukā **Klienta ID** atlasiet lauku, kas apzīmē klienta Braze ID. Tas ir nepieciešams, lai eksportētu segmentus uz Braze. Pēc izvēles varat izvēlēties vairāk lauku.

1. Atlasiet **Saglabāt**.

Eksporta saglabāšana automātiski nepalaiž eksportu.

Eksports tiek palaists ar katru [plānoto atsvaidzināšanu](system.md#schedule-tab). Varat arī [eksportēt datus pēc pieprasījuma](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Datu konfidencialitāte un atbilstība

Kad jūs iespējojat Dynamics 365 Customer Insights datu pārsūtīšanu uz Braze, jūs atļaujat pārsūtīt datus ārpus atbilstības robežas, tostarp potenciāli sensitīviem Dynamics 365 Customer Insights datiem, piemēram, Personas datiem. Microsoft pārsūtīs šādus datus pēc jūsu norādījumiem, taču jūs esat atbildīgs par to, lai Braze izpildītu visas jūsu iespējamās konfidencialitātes vai drošības saistības. Papildinformāciju skatiet rakstā [Microsoft Privātuma paziņojums](https://go.microsoft.com/fwlink/?linkid=396732).

Jūsu Dynamics 365 Customer Insights administrators var noņemt šo eksportēšanas galamērķi jebkurā laikā, lai pārtrauktu izmantot šo funkcionalitāti.
