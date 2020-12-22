---
title: Customer Insights datu eksportēšana uz Facebook Ads Manager
description: Uzziniet, kā konfigurēt savienojumu ar Facebook Ads Manager.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 8260e3b5e529f3d54678d9d6e11aebb2795e27fd
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643692"
---
# <a name="connector-for-facebook-ads-manager-preview"></a>Facebook Ads Manager savienotājs (priekšskatījums)

Eksportējiet vienotu klientu profilu segmentus uz Facebook Ads Manager, lai izveidotu kampaņas platformās Facebook un Instagram.

## <a name="prerequisites"></a>Priekšnosacījumi

- Jums ir nepieciešams [**Facebook Reklāmu konts**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account), kas ietver [**Facebook Biznesa kontu**](https://business.facebook.com/).
- Jums ir jābūt [**Facebook Reklāmu konta**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) administratoram.

## <a name="connect-to-facebook-ads-manager"></a>Savienojuma izveide ar Facebook Ads Manager

1. Dodieties uz sadaļu **Administrators** > **Eksportēšanas galamērķi**.

1. Sadaļā **Facebook Ads Manager** atlasiet **Iestatīt**.

1. Piešķiriet eksportēšanas galamērķim atpazīstamu nosaukumu laukā **Parādāmais nosaukums**.

1. Atlasiet **Turpināt ar Facebook**, lai pierakstītos savā Facebook Reklāmu kontā.

1. Atļaut **ads_management** atļauju pēc autentificēšanās Facebook.

1. Atlasiet **Facebook Reklāmu kontu**, ar kuru vēlaties strādāt.

1. Nolaižamajā sarakstā atlasiet **Esošā pielāgotā auditorija** vai izveidojiet **Jaunu pielāgotu auditoriju**. Papildinformāciju skatiet rakstā [**Auditorijas Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).

1. Atlasiet **Piekrītu**, lai apstiprinātu **Datu konfidencialitāti un atbilstību**.

1. Lai konfigurētu eksportēšanu, atlasiet **Tālāk**.

## <a name="configure-the-connector"></a>Savienotāja konfigurēšana

1. Lodziņā **Izvēlieties atslēgas identifikatora lauku** atlasiet **E-pasts**, **Vārds, uzvārds un adrese** vai **Tālrunis**, ko nosūtīt Facebook Ads Manager.

1. Kartējiet atbilstošos atribūtus no savas vienotās klienta entītijas atlasītajam galvenajam identifikatoram.
   > [PADOMS] Labākās atbilstības iespējas parādās, ja kā galveno identifikatoru atlasāt **E-pastu**. Atbilstība var uzlaboties, pievienojot papildu identifikatorus.

1. Atlasiet **Pievienot atribūtu**, lai kartētu papildu atribūtus, kurus nosūtīt Facebook Ads Manager. Atribūti no Facebook Reklāmu pārvaldnieka tiek kartēti uz šādiem lietotājam draudzīgiem nosaukumiem: **FN** = **Vārds**, **LN** = **Uzvārds**, **FI** = **Pirmais iniciālis**, **PHONE** = **Tālrunis**, **GEN** = **Dzimums**, **DOB** = **Dzimšanas datums**, **ST** = **Štats**, **CT** = **Pilsēta**, **ZIP** = **Pasta indekss / ZIP kods**, **COUNTRY** = **Valsts/reģions**

1. Atlasiet segmentus, kurus vēlaties eksportēt.

1. Atlasiet vienumu **Saglabāt**.

## <a name="export-the-data"></a>Datu eksportēšana

Datus var [eksportēt pēc pieprasījuma](export-destinations.md). Eksportēšana arī tiks palaista ar katru [plānoto atsvaidzināšanu](system.md#schedule-tab).

## <a name="data-privacy-and-compliance"></a>Datu konfidencialitāte un atbilstība

Ja iespējojat Dynamics 365 Customer Insights datu pārsūtīšanai uz Facebook Ads Manager, jūs atļaujat datu pārsūtīšanu ārpus Dynamics 365 Customer Insights atbilstības robežām, ieskaitot iespējami sensitīvus datus, piemēram, personas datus. Microsoft šos datus pārsūtīs pēc jūsu norādēm, bet jūs esat atbildīgs par to, lai nodrošinātu Facebook Ads atbilstību konfidencialitātes vai drošības saistībām, kas jums varētu rasties. Papildinformāciju skatiet rakstā [Microsoft Privātuma paziņojums](https://go.microsoft.com/fwlink/?linkid=396732).
Jūsu Dynamics 365 Customer Insights administrators var noņemt šo eksportēšanas galamērķi jebkurā laikā, lai pārtrauktu izmantot šo funkcionalitāti.
