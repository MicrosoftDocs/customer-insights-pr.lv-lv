---
title: Segmentu eksportēšana uz Facebook reklāmu pārvaldnieku (priekšskatījums) (satur video)
description: Uzziniet, kā konfigurēt savienojumu un eksportēt uz Facebook Ads Manager.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c7a4b1be1c959d70fad929b56452169b40e5b592
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724613"
---
# <a name="export-segments-to-facebook-ads-manager-preview"></a>Segmentu eksportēšana uz Facebook reklāmu pārvaldnieku (priekšskatījums)

Eksportējiet vienotu klientu profilu segmentus uz Facebook Ads Manager, lai izveidotu kampaņas platformās Facebook un Instagram.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO1aN]

## <a name="prerequisites"></a>Priekšnoteikumi

- Reklāmu [Facebook konts, kurā ir iekļauts](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) uzņēmuma konts [Facebook](https://business.facebook.com/).
- Administratora [Facebook atļaujas Ads kontā](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).
- Lietotājam, kas iestata savienojumu programmā Customer Insights, ir jāpieņem pielāgotas mērķauditorijas nosacījumi.

## <a name="known-limitations"></a>Zināmie ierobežojumi

- Līdz 10 miljoniem klientu profilu vienā eksportēšanas reizē uz Facebook Ads Manager, kas var aizņemt līdz pat 90 minūtēm.
- Tikai segmenti.
- Facebook Reklāmu integrācija neatbalsta lietotājus ar vairāk nekā 25 reklāmu kontiem.
- Facebook *Klientu saraksta* tips [tikai pielāgotām auditorijām](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).
  > [!NOTE]
  > Dažos gadījumos nolaižamajā sarakstā var būt redzamas dažādu veidu pielāgotas mērķauditorijas. Ja atlasāt citu tipu, kas nav *debitoru saraksts*, eksportēšana neizdodas.

## <a name="set-up-connection-to-facebook-ads-manager"></a>Savienojuma ar Facebook Ads Manager izveidošana

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Dodieties uz **Administrators** > **Savienojumi**.

1. Atlasiet **Pievienot savienojumu** un izvēlieties **Facebook Reklāmu pārvaldnieks**.

1. Laukā **Parādāmais nosaukums** piešķiriet savienojumam atpazīstamu nosaukumu. Parādāmais nosaukums un nosaukuma veids raksturo šo savienojumu. Ir ieteicams izvēlēties nosaukumu, kas paskaidro savienojuma nolūku.

1. [Ļaujiet līdzstrādniekiem izmantot savienojumu eksportēšanai](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Autentificējieties, izmantojot Facebook Ads:

   1. Atlasiet **Turpināt ar Facebook**, lai pieteiktos savā Facebook reklāmu kontā.

   1. Atļaut **ads_management** atļauju pēc autentificēšanās Facebook.

   1. Atlasiet **Facebook Reklāmu kontu**, ar kuru vēlaties strādāt.

   1. Nolaižamajā sarakstā atlasiet **Esošu pielāgotu auditoriju** vai izveidojiet **Jaunu pielāgotu auditoriju**.

1. Pārskatiet datu konfidencialitāti [un atbilstību](connections.md#data-privacy-and-compliance) un atlasiet **Es piekrītu**.

1. Lai pabeigtu savienošanu, atlasiet **Saglabāt**.

## <a name="configure-an-export"></a>Eksporta konfigurēšana

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Pārejiet uz **Dati** > **Eksportēšana**.

1. Atlasiet **Pievienot eksportu**.

1. **Laukā Savienojums eksportēšanai** sadaļā Reklāmu pārvaldnieks izvēlieties savienojumu Facebook. Ja nav pieejamu savienojumu, sazinieties ar administratoru.

1. Ievadiet eksportēšanas nosaukumu.

1. **Laukā Datu savienošana** atlasiet **E-pasts**, **Vārds un adrese** vai **Tālrunis**, lai nosūtītu ziņojumus Facebook reklāmu pārvaldniekam.

1. Kartējiet atbilstošos atribūtus no savas vienotās klienta entītijas atlasītajam galvenajam identifikatoram.
   > [!TIP]
   > Labākās atbilstības iespējas parādās, ja kā galveno identifikatoru atlasāt **E-pastu**. Atbilstība var uzlaboties, pievienojot papildu identifikatorus.

1. Atlasiet **Pievienot atribūtu**, lai kartētu vairāk atribūtu, ko nosūtīt uz Facebook Ads Manager. Atribūti no Facebook reklāmu pārvaldnieka tiek kartēti uz šādiem lietotājam draudzīgiem nosaukumiem: **FN** = **Vārds**, **LN** = **Uzvārds**, **FI** = **Pirmais iniciālis**, **PHONE** = **Tālrunis**, **GEN** = **Dzimums**, **DOB** = **Dzimšanas datums**, **ST** = **Štats**, **CT** = **Pilsēta**, **ZIP** = **Pasta indekss / ZIP kods**, **COUNTRY** = **Valsts/reģions**

1. Atlasiet segmentus, kurus vēlaties eksportēt.

1. Atlasiet **Saglabāt**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
