---
title: Papildu tīmekļa SDK scenāriji
description: Papildu scenāriji, kas jāņem vērā, izmantojot jūsu tīmekļa vietni ar SDK.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 09/27/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 4c6646ecadbb604000d6c95b685cf6e420969a6d
ms.sourcegitcommit: f1e3cc51ea4cf68210eaf0210ad6e14b15ac4fe8
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 09/27/2021
ms.locfileid: "7558711"
---
# <a name="advanced-web-sdk-instrumentation"></a>Papildu tīmekļa SDK dokumentācija

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Šajā rakstā ir sniegti papildu scenāriji, kas jāņem vērā, [izmantojot jūsu tīmekļa vietni](instrument-website.md) ar Dynamics 365 Customer Insights iesaistes ieskatu iespēju SDK.

## <a name="setting-user-details-for-your-event"></a>Lietotāja detalizētās informācijas iestatīšana notikumam

SDK ļauj definēt lietotāja informāciju, ko var nosūtīt kopā ar katru notikumu. Lietotāja informāciju var norādīt rekvizītā ar nosaukumu `user` (šim rekvizītam paredzamie dati ir `IUser` objekts), līdzīgi kā, `src`, `name` un `cfg` koda fragmenta konfigurācijā.

Objektam `IUser` ir šādi virknes rekvizīti:

- **localId**: lietotāja lokālais ID.
- **authId**: autentificēts lietotāja ID.
- **authType**: autentifikācijas tips, kas tiek izmantots, lai iegūtu autentificēto lietotāja ID.
- **name**: lietotāja vārds.
- **email**: lietotāja e-pasta adrese.

Šajā piemērā redzams koda fragments, kas nosūta lietotāja informāciju. Ja redzat funkcijas, pirms kuras ir zvaigznītes * simbols, aizstājiet šo funkciju ar jūsu pielāgoto ieviešanu:

```
[…]
window, document
{
    src:"https://download.pi.dynamics.com/sdk/web/msei-1.min.js",
    name:"myproject",
    cfg:{
      ingestionKey:<paste your ingestion key>",
      autoCapture:{
        view:true,
        click:true
      }
    },
    user:{
      authId: getLoggedInUserId()*,
      email: getLoggedInUserEmail()*,
      authType: "MSA",
      name: "John Doe"
    }
[…]
```

Varat arī norādīt lietotāja informāciju, izsaucot `setUser(user: IUser)` API. Telemetrija, kas tiks nosūtīta pēc `setUser` API zvanīšanas, satur lietotāja informāciju.

## <a name="adding-custom-properties-for-each-event"></a>Pielāgotu rekvizītu pievienošana katram notikumam

SDK ļauj norādīt pielāgotus rekvizītus, ko var nosūtīt kopā ar katru notikumu. Pielāgotos rekvizītus var norādīt kā objektu, kas ietver galveno vērtību pārus (vērtība var būt `string | number | boolean` tips). Objektu var pievienot rekvizītā, ko sauc par `props`, līdzīgi kā `src`, `name` un `cfg` koda fragmenta konfigurācijā.

Šajā piemērā redzams koda fragments, kas nosūta pielāgotus rekvizītus:

```
[…]
window, document
{
    src:"https://download.pi.dynamics.com/sdk/web/msei-1.min.js",
    name:"myproject",
    cfg:{
      ingestionKey:<paste your ingestion key>",
      autoCapture:{
        view:true,
        click:true
      }
    },
    props:{
      "key_name_string": "value",
      "key_name_number": 10,
      "key_name_bool": true
    }
[…]
```

Varat arī individuāli norādīt pielāgotos rekvizītus, izsaucot `setProperty(name: string, value: string | number | boolean)` API.

## <a name="sending-custom-events"></a>Pielāgoto notikumu sūtīšana

Varat lietot SDK, lai nosūtītu pielāgotus notikumus. Jānorāda notikuma nosaukums un rekvizīti, kas tiks nosūtīti kopā ar notikumu.

Šajā piemērā redzams koda fragments, kas izseko pielāgotu notikumu. Vērtība "NAME" ir vērtība `name` atslēgā konfigurācijas fragmentā. Tas ir arī mainīgā nosaukums loga objektā, kur tiek ielādēts SDK.

```
window["NAME"].trackEvent({
    name: "event_name",
    properties: {
        "duration": 320,
        "name": "getting_started",
        "ad_shown": true
    }
});
```


[!INCLUDE[footer-include](../includes/footer-banner.md)]
