---
title: Pievienojiet kodu savai tīmekļa vietnei
description: Kā pievienot tīmekļa koda fragmentu, lai tvertu notikumus jūsu tīmekļa vietnē.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 04/30/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: b5467da775a621c436bd9ddedb272506acc1e2b31dcf7c87feb5dd11e2daae2b
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035103"
---
# <a name="install-the-code-snippet-on-a-website"></a>Koda fragmenta instalēšana tīmekļa vietnē

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Šajā rakstā ir aprakstīts, kā administrators var instalēt koda fragmentu tīmekļa vietnē. Drīz pēc skripta pievienošanas jūsu vietnei savā darbvietā sāksiet redzēt notikumus. Papildinformāciju skatiet sadaļā [Darbvietu un vides pārvaldība](manage-environments-workspaces.md). Lai mobilajās programmās tvertu notikumus, skatiet [Izstrādātāju resursu pārskatu](developer-resources.md).


### <a name="prerequisites"></a>Priekšnosacījumi

* Lai glabātu datus, darbvietai ir jābūt administratora atļaujām.
* Lai nosūtītu darbību datus, jūsu vietnei vai projektam jābūt viesotam tiešsaistē. Serveris nevar pieņemt datus, kas ir nosūtīti no lokālā faila.


## <a name="add-code-to-your-website"></a>Pievienojiet kodu savai tīmekļa vietnei
1.  Dodieties uz **Administrators** > **Darbvieta**  un tad atlasiet **Instalēšanas rokasgrāmata**.
1. Atlasiet **Kopēt kodu**, lai kopētu koda fragmentu. Pēc noklusējuma jūsu darbvietas ievades atslēga ir iegulta koda fragmentā.
:::image type="content" source="media/copy-code.png" alt-text="Koda fragmenta lapas ekrānuzņēmums.":::
3. Kopēto datu koda fragmentu pievienojiet tīmekļa vietnei blakus <head> atzīmei un pirms jebkādiem citiem skriptiem vai CSS atzīmēm.
4.  Publicējiet atjaunināto tīmekļa vietni un uzgaidiet dažas minūtes, lai tvertu ienākošo tīmekļa datplūsmu.
5.  Lai skatītu savus datus, navigācijas rūtī darbvietas pārslēdzēja sadaļā atlasiet darbvietu. Pēc tam sadaļā **Atklāt** atlasiet kādu no atskaitēm.

## <a name="configuration-options"></a>Konfigurācijas opcijas

Koda fragmentā varat mainīt šādas konfigurācijas iespējas:

- **ingestionKey**: ievades atslēga izmantota, lai sūtītu notikumus uz jūsu darbvietu. Varat mainīt uzņemšanas atslēgu, lai notikumus nosūtītu uz citu darbvietu. Katras darbvietas uzņemšanas atslēga ir unikāla. 
- **autoCapture**: norāda, vai tiek tverti lapas skati un mijiedarbības ar tīmekļa vietni. Tajā ir divas iespējas:
    - **view**: iestatīt uz *patiess*, lai tvertu lapu skatus. Lapu skati tiek tverti kā *Skatīt* [notikumus](glossary.md#event), [pamata notikuma](glossary.md#base-event) tips.
    - **click**: iestatīts uz *patiess*, lai vietnē tvertu apmeklētāju mijiedarbību. Mijiedarbības tiek tvertas kā *Rīcības* [notikumi](glossary.md#event), [pamata notikuma](glossary.md#base-event) tips.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
