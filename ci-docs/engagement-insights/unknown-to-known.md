---
title: Atpazīt tīmekļa notikumus no iepriekš autentificētiem viesiem no nezināmiem uz zināmiem
description: Nezināmā un zināmā līdzeklis ļauj saistīt notikumus vietnē ar vēlamiem notikumiem, kuri iepriekš autentificēti.
ms.reviewer: mhart
ms.author: mkisel
author: mkisel11
ms.date: 7/15/2021
ms.subservice: engagement-insights
ms.topic: overview
ms.manager: shellyha
ms.openlocfilehash: 75ce776fd5be1c426508ae6f5c239c86bdd3ec39
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 02/16/2022
ms.locfileid: "8230689"
---
# <a name="recognize-web-events-from-previously-authenticated-visitors"></a>Atpazīt tīmekļa notikumus no iepriekš autentificētiem viesiem

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

**Nezināmā un zināmā** līdzeklis iesaistes ieskatu iespējas līdzeklī iespējo notikumu saistīšanu vietnē ar vēlamajiem notikumiem, kuri iepriekš autentificēti. Ja līdzeklis ir atspējots, autentificēšanas līdzeklis, kurš tika autentificēts agrākas apmeklējuma laikā un pēc tam atstāts, netiek identificēts, ja, atgriežoties atpakaļ, atkārtoti autentificējas. 

Piemēram, persona, kas pagājušajā nedēļā apmeklēja vietni, pieteikusies savas vietnes lietotāja kontā un pārlūkoja preču katalogu. Šī persona atgriežas nākamajā nedēļā, lai pārlūkotu vairāk produktu, nepiesakoties savā kontā. Vietnes īpašnieks, kurš izmanto **nezināmā un zināmā** līdzekli, zinātu, ka šī pati persona ir atgriezusies un ko tā bija darījusi šajā vietnē. Tas ļauj precīzāk ziņot par vietnes darbībām un to analīzi.

## <a name="enable-unknown-to-known"></a>No nezināmā uz zināmo — iespējot

Lai iespējotu šo līdzekli, jums jābūt [darbvietas administratoram](user-roles.md). 

1. Iesaistes ieskatos dodieties uz **Administrators** > **Darbvieta**. 
2. Atlasiet cilni **Iestatījumi**.
3. Sadaļā **Nezināms un zināms** iestatiet slēdzi uz **Iespējots**.

![No nezināmā uz zināmo — iespējot](media/U2Ktoggle.png "No nezināmā uz zināmo — iespējot")

## <a name="adding-javascript-code-to-your-sites-tracking-snippet"></a>JavaScript koda pievienošana vietnes izsekošanas fragmentam

Vietne var tvert **lietotāja authId** ar šādu JavaScript paraugu, izmantojot [iesaistes ieskatus tīmekļa SDK](advanced-SDK-implementation.md). Lai darbotos līdzeklis **nezināms un zināms**, jums ir nepieciešams tvert authId *un* iespējot userMapping:True jūsu JavaScript fragmentā, kā parādīts zemāk redzamajā paraugā.

```
[…]
window, document
{
src:"https://download.pi.dynamics.com/sdk/web/mspi-0.min.js",
name:"myproject",
cfg:{
ingestionKey:<paste your ingestion key>",
autoCapture:{
view:true,
click:true
},
userMapping: true
},
user:{
authId: getLoggedInUserId()*,
email: getLoggedInUserEmail()*,
authType: "MSA",
name: "Alex Jensen"
}
[…]
```

[!INCLUDE[footer-include](../includes/footer-banner.md)]
