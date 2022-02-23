---
title: Customer Insights datu eksportēšana uz Facebook Ads Manager (satur video)
description: Uzziniet, kā konfigurēt savienojumu un eksportēt uz Facebook Ads Manager.
ms.date: 04/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ce1e63f7b20b757780f05895b725003e286f9dac
ms.sourcegitcommit: 9132fdf54070cc551ab878378078e6285852818f
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 12/18/2021
ms.locfileid: "7935033"
---
# <a name="export-segments-list-to-facebook-ads-manager-preview"></a>Segmentu saraksta eksportēšana uz Facebook Ads Manager (priekšskatījums)

Eksportējiet vienotu klientu profilu segmentus uz Facebook Ads Manager, lai izveidotu kampaņas platformās Facebook un Instagram.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO1aN]

## <a name="prerequisites-for-connection"></a>Savienojuma priekšnosacījumi

- Jums ir nepieciešams [**Facebook reklāmu konts**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account), kurā ietverts [**Facebook biznesa konts**](https://business.facebook.com/).
- Jums ir jābūt administratoram [**Facebook reklāmu kontā**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).

## <a name="known-limitations"></a>Zināmie ierobežojumi

- Vienā reizē uz Facebook reklāmu pārvaldnieku var eksportēt līdz 10 miljoniem klientu profilu.
- Eksportēšana uz Facebook Ads Manager ir atļauta tikai segmentiem.
- Izveidojiet vai atjauniniet pielāgoto auditoriju Facebook no veida tikai *klientu saraksts*.
- 10 miljona klientu profilu segmentu eksports var ilgt līdz 90 minūtēm.

## <a name="set-up-connection-to-facebook-ads-manager"></a>Savienojuma ar Facebook Ads Manager izveidošana

Iekams lietotāji var izveidot eksportu, administratoram ir jākonfigurē savienojums ar pakalpojumu un jāļauj līdzstrādniekiem izmantot savienojumu.

1. Dodieties uz **Administrators** > **Savienojumi**.

1. Atlasiet vienumu **Pievienot savienojumu** un atlasiet **Facebook Ads Manager**, lai konfigurētu savienojumu.

1. Laukā **Parādāmais nosaukums** piešķiriet savienojumam atpazīstamu nosaukumu. Parādāmais nosaukums un nosaukuma veids raksturo šo savienojumu. Ir ieteicams izvēlēties nosaukumu, kas paskaidro savienojuma nolūku.

1. Izvēlieties, kurš var izmantot šo savienojumu. Ja nesāksit nekādas darbības, noklusējums būs Administratori. Papildinformāciju skatiet rakstā [Atļaut līdzstrādniekiem izmantot savienojumu eksportam](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Autentificējieties, izmantojot Facebook Ads: 

   1. Atlasiet **Turpināt ar Facebook**, lai pieteiktos savā Facebook reklāmu kontā.

   1. Atļaut **ads_management** atļauju pēc autentificēšanās Facebook.

   1. Atlasiet **Facebook Reklāmu kontu**, ar kuru vēlaties strādāt.

   1. Nolaižamajā sarakstā atlasiet **Esošu pielāgotu auditoriju** vai izveidojiet **Jaunu pielāgotu auditoriju**. Papildinformāciju skatiet rakstā [**Auditorijas Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).
      > [!NOTE]
      > Šajā eksportā jūs varat Facebook izveidot vai atjaunināt pielāgotās auditorijas vienīgi ar veidu *klientu saraksts*. Dažos gadījumos nolaižamajā sarakstā ir redzamas pielāgotas dažādu tipu auditorijas. Ja atlasīsiet auditoriju, kuras veids nav *klientu saraksts*, eksportēšana neizdosies. 

1. Pārskatiet lapu **Datu privātums un atbilstība** un atlasiet **Es piekrītu**.

1. Lai pabeigtu savienošanu, atlasiet **Saglabāt**.

## <a name="configure-an-export"></a>Eksporta konfigurēšana

Šo eksportu varat konfigurēt, ja jums ir piekļuve šā veida pieslēgumam. Papildinformāciju skatiet rakstā [Atļaujas, kas nepieciešamas eksporta konfigurēšanai](export-destinations.md#set-up-a-new-export).

1. Pārejiet uz **Dati** > **Eksportēšana**.

1. Lai izveidotu jaunu eksportu, atlasiet **Pievienot galamērķi**. 

1. Laukā **Savienošana eksportam** atlasiet savienojumu no sadaļas **Facebook Ads Manager** Ja neredzat šo sadaļas nosaukumu, tad jums nav pieejami šī tipa savienojumi.

1. Lodziņā **Izvēlieties atslēgas identifikatora lauku** atlasiet **E-pasts**, **Vārds, uzvārds un adrese** vai **Tālrunis**, ko nosūtīt Facebook Ads Manager. 

1. Laukā **Parādāmais nosaukums** piešķiriet savienojumam atpazīstamu nosaukumu.

1. Kartējiet atbilstošos atribūtus no savas vienotās klienta entītijas atlasītajam galvenajam identifikatoram.
   > [!TIP]
   > Labākās atbilstības iespējas parādās, ja kā galveno identifikatoru atlasāt **E-pastu**. Atbilstība var uzlaboties, pievienojot papildu identifikatorus.

1. Atlasiet **Pievienot atribūtu**, lai kartētu vairāk atribūtu, ko nosūtīt uz Facebook Ads Manager. Atribūti no Facebook reklāmu pārvaldnieka tiek kartēti uz šādiem lietotājam draudzīgiem nosaukumiem: **FN** = **Vārds**, **LN** = **Uzvārds**, **FI** = **Pirmais iniciālis**, **PHONE** = **Tālrunis**, **GEN** = **Dzimums**, **DOB** = **Dzimšanas datums**, **ST** = **Štats**, **CT** = **Pilsēta**, **ZIP** = **Pasta indekss / ZIP kods**, **COUNTRY** = **Valsts/reģions**

1. Atlasiet segmentus, kurus vēlaties eksportēt.

1. Atlasiet vienumu **Saglabāt**.

Eksporta saglabāšana automātiski nepalaiž eksportu.

Eksports tiek palaists ar katru [plānoto atsvaidzināšanu](system.md#schedule-tab). 

Varat arī [eksportēt datus pēc pieprasījuma](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Datu konfidencialitāte un atbilstība

Ja iespējojat Dynamics 365 Customer Insights datu pārsūtīšanai uz Facebook Ads Manager, jūs atļaujat datu pārsūtīšanu ārpus Dynamics 365 Customer Insights atbilstības robežām, ieskaitot iespējami sensitīvus datus, piemēram, personas datus. Microsoft šos datus pārsūtīs pēc jūsu norādēm, bet jūs esat atbildīgs par to, lai nodrošinātu Facebook Ads atbilstību konfidencialitātes vai drošības saistībām, kas jums varētu rasties. Papildinformāciju skatiet rakstā [Microsoft Privātuma paziņojums](https://go.microsoft.com/fwlink/?linkid=396732).
Jūsu Dynamics 365 Customer Insights administrators var noņemt šo eksportēšanas galamērķi jebkurā laikā, lai pārtrauktu izmantot šo funkcionalitāti.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
