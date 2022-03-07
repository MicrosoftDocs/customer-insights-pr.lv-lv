---
title: Pievienojiet kodu savai tīmekļa vietnei
description: Kā pievienot tīmekļa koda fragmentu, lai tvertu Dynamics 365 Customer Insights notikumus jūsu tīmekļa vietnē.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 09/27/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: ad835f762226d62fdb0f544627f2a76ff09a1ffd
ms.sourcegitcommit: f1e3cc51ea4cf68210eaf0210ad6e14b15ac4fe8
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 09/27/2021
ms.locfileid: "7558902"
---
# <a name="install-the-web-sdk-on-a-website"></a>Tīmekļa SDK instalēšana vietnē

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Šajā rakstā ir aprakstīts, kā administrators tīmekļa programmatūras izstrādes rīku komplektu (SDK) instalē vietnē. Jūs savā darbvietā drīz pēc vietnes pārraudzīšanas sākat skatīt notikumus. Papildinformāciju skatiet sadaļā [Darbvietu un vides pārvaldība](manage-environments-workspaces.md). Lai mobilajās programmās tvertu notikumus, skatiet [Izstrādātāju resursu pārskatu](developer-resources.md).


### <a name="prerequisites"></a>Priekšnosacījumi

* Lai glabātu datus, darbvietai ir jābūt administratora atļaujām.
* Lai nosūtītu darbību datus, jūsu vietnei vai projektam jābūt viesotam tiešsaistē. Serveris nevar pieņemt datus, kas ir nosūtīti no lokālā faila.


## <a name="add-web-sdk-to-your-website"></a>Pievienojiet tīmekļa SDK savā tīmekļa vietnē

Dodieties uz **Administrators** > **Darbvieta**  un tad atlasiet **Instalēšanas rokasgrāmata**. Pastāv divas tīmekļa SDK instalēšanas iespējas. Pirmā ir izmantot lejupielādes saiti, bet otrā ir mezgla pakotnes pārvaldnieka (NPM) pakotnes instalēšana.

### <a name="option-1-using-the-download-link"></a>1. opcija: izmantojot lejupielādes saiti

1. Atlasiet **Kopēt kodu**, lai kopētu koda fragmentu. Pēc noklusējuma jūsu darbvietas ievades atslēga ir iegulta koda fragmentā.
  :::image type="content" source="media/copy-code.png" alt-text="Koda fragmenta lapas ekrānuzņēmums.":::

1. Pievienojiet kopēto kodu jūsu vietnei blakus <head> atzīmei un pirms jebkādiem citiem skriptiem vai CSS atzīmēm.
1. Publicējiet atjaunināto tīmekļa vietni un uzgaidiet dažas minūtes, lai tvertu ienākošo tīmekļa datplūsmu.
1. Lai skatītu savus datus, navigācijas rūtī darbvietas pārslēdzēja sadaļā atlasiet darbvietu. Pēc tam sadaļā **Atklāt** atlasiet kādu no atskaitēm.

### <a name="option-2-using-the-npm-package-recommended-for-javascript-based-web-apps"></a>2. opcija: izmantojot NPM pakotni (ieteicams JavaScript bāzes tīmekļa programmām)

1. Dodieties uz mūsu [NPM tīmekļa lapu](https://www.npmjs.com/package/engagementinsights-web) un izpildiet norādījumus, kas sniegti, lai instalētu un iestatītu tīmekļa SDK NPM pakotni.
1. Publicējiet atjaunināto tīmekļa vietni un uzgaidiet dažas minūtes, lai tvertu ienākošo tīmekļa datplūsmu.
1. Lai skatītu savus datus, navigācijas rūtī darbvietas pārslēdzēja sadaļā atlasiet darbvietu. Pēc tam sadaļā **Atklāt** atlasiet kādu no atskaitēm.

## <a name="configuration-options"></a>Konfigurācijas opcijas

Koda fragmentā varat mainīt šādas konfigurācijas iespējas:

- **ingestionKey**: ievades atslēga izmantota, lai sūtītu notikumus uz jūsu darbvietu. Varat mainīt uzņemšanas atslēgu, lai notikumus nosūtītu uz citu darbvietu. Katras darbvietas uzņemšanas atslēga ir unikāla.
- **autoCapture**: norāda, vai tiek tverti lapas skati un mijiedarbības ar tīmekļa vietni. Tajā ir divas iespējas:
    - **view**: iestatīt uz *patiess*, lai tvertu lapu skatus. Lapu skati tiek tverti kā *Skatīt* [notikumus](glossary.md#event), [pamata notikuma](glossary.md#base-event) tips.
    - **click**: iestatīts uz *patiess*, lai vietnē tvertu apmeklētāju mijiedarbību. Mijiedarbības tiek tvertas kā *Rīcības* [notikumi](glossary.md#event), [pamata notikuma](glossary.md#base-event) tips.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
