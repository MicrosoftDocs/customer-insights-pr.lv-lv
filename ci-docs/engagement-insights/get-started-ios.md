---
title: Darba sākšana ar iOS SDK
description: Uzziniet, kā personalizēt un palaist iOS SDK
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 06/23/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: de8291fc429ae6433301a47bfdf9a3271b1b77294fd58448c7aa6bd0783edc97
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036882"
---
# <a name="get-started-with-the-ios-sdk"></a>Darba sākšana ar iOS SDK

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Šī apmācība palīdz izmantot savu iOS lietojumprogrammu, izmantojot Dynamics 365 Customer Insights iesaistes ieskatu SDK. Notikumus savā portālā varēsit skatīt pēc piecām minūtēm vai ātrāk.

## <a name="configuration-options"></a>Konfigurācijas opcijas

Tālāk uzskaitītās konfigurācijas opcijas ir iespējams nodot SDK, izmantojot nodrošināto `EIConfig.plist` failu:

- **ingestionKey**: pieņemšanas atslēgu izmanto, lai nosūtītu notikumus uz projektu.
- **autoactionlectAction:** būla vērtība, lai iespējotu vai atspējotu darbības notikuma automātisko instrumentāciju.
- **autocollectView**: būla vērtība, lai iespējotu vai atspējotu skatīšanas notikuma automātisko instrumentāciju.
- **endpointUrl**: galapunkta vietrādis URL uz kuru tiks novirzīti notikumi.

## <a name="prerequisites"></a>Priekšnosacījumi

- Xcode versija 9+
- iOS versija 8.2+
- Pieņemšanas atslēga (lai iegūtu, skatiet tālāk sniegtos norādījumus)

## <a name="integrate-the-sdk-into-your-application"></a>SDK integrēšana programmā

Sāciet procesu, atlasot darbvietu, kurā strādāt, atlasot iOS mobilo platformu un lejupielādējot SDK.

- Lai atlasītu darbvietu, izmantojiet darbvietas pārslēdzēju kreisās puses navigācijas rūtī.

- Ja jums nav esošas darbvietas, atlasiet **Jauna darbvieta** un izpildiet tālāk norādītās darbības, lai izveidotu [jaunu darbvietu](create-workspace.md).

## <a name="configure-the-sdk"></a>SDK konfigurēšana

Pēc SDK lejupielādes ar to var strādāt, izmantojot Xcode, lai iespējotu un definētu notikumus.

1. Pēc darbvietas izveides dodieties uz **Administrators** > **Darbvieta** un pēc tam atlasiet **Instalēšanas rokasgrāmata**.

1. Lejupielādējiet [iesaistes ieskatus iOS SDK](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-ios-sdk.zip) un ievietojiet `EIObjC.xcframework` failu `Frameworks` mapē.

1. Ja `Frameworks` mape nepastāv, izveidojiet to projekta mapē.

## <a name="enable-auto-instrumentation"></a>Automātiskās instrumentācijas iespējošana
 
Automātisko instrumentāciju var viegli iespējot bez kodēšanas. Kad projekts tiks izpildīts, tas automātiski izsekos `view` un `action` notikumiem, izmantojot konfigurēto pieņemšanas atslēgu. 

1. Atjauniniet un iekļaujiet nodrošināto `EIConfig.plist` failu savā projektu direktorija mapē šādiem laukiem:
    - ingestionKey = `"Your-Ingestion-Key"`
    - autocollectView = JĀ
    - autocollectAction = JĀ

2. Pēc tam pievienojiet `EIConfig.plist` failu savam projektam programmā Xcode. 



Lai atspējotu automātisko instrumentāciju, atjauniniet tālāk norādītos laukus no `EIConfig.plist` faila, kas ir jūsu projektu direktorija mapē. 

```objectivec
'autocollectView' = NO (to disable)
'autocollectAction' = NO (to disable)
```


## <a name="implement-custom-events"></a>Pielāgotu notikumu ieviešana

1. Atveriet savu projektu Xcode un dodieties uz **Vispārīgiem** iestatījumiem. 
1. Projektam zem sadaļas “Struktūras, bibliotēkas un iegultais saturs” pievienojiet `EIObjC.xcframework`.

1. Importējiet failā AppDelegate.m struktūras galvenes failu ar šo fragmentu:

    ```objectivec
    #import <EIObjC/EIObjC.h>
    ```

1. Inicializējiet iesaistes ieskatus SDK no programmas: didFinishLaunchingWithOptions.
1. Kopējiet XML fragmentu no **Instalēšanas rokasgrāmatas**.

    ```objectivec
    NSError *error = [NSError new];
    id<EIIAnalytics> analytics = [EIAnalyticsProvider analyticsForIngestionKey:nil error:&error];
    ```

1. Notikuma izsekošana:

    ```objectivec
    EIEvent *event = [EIEvent new];
    event.name = @"video.log";
    [event setLongValue:320 forKey:@"duration"];
    [event setBoolValue:YES forKey:@"ad_shown"];
    [analytics trackEvent:event];
    ```

## <a name="set-user-details-for-your-event"></a>Lietotāja informācijas iestatīšana savam notikumam

SDK ļauj definēt lietotāja informāciju, ko var nosūtīt kopā ar katru notikumu. Varat norādīt lietotāja informāciju, izsaucot `setUser:(nonnull EIUser *)user` API uz SDK.

Lietotāja informācijas norādīšana `Analytics` līmenī nozīmē, ka šī informācija būs pieejama visām telemetrijām. Tomēr, ja tā tiek norādīta notikuma līmenī, izsaucot `setUser:(nonnull EIUser *)user` API uz EIEvent objektu, informāciju saturēs tikai konkrētais notikums.

Datu klase `EIUser` satur šādus NSString rekvizītus:

- **localId**: lietotāja lokālais ID.
- **authId**: autentificēts lietotāja ID.
- **authType**: autentifikācijas tips, kas tiek izmantots, lai iegūtu autentificēto lietotāja ID.
- **name**: lietotāja vārds.
- **email**: lietotāja e-pasta adrese.


[!INCLUDE[footer-include](../includes/footer-banner.md)]