---
title: Darba sākšana ar iOS SDK
description: Uzziniet, kā personalizēt un palaist iOS SDK
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 09/15/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: f05929435eeee9cf3f891ab18842c5861e39d5ba
ms.sourcegitcommit: fecdee73e26816c42d39d160d4d5cfb6c8a91596
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 09/15/2021
ms.locfileid: "7494239"
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

- Pēc darbvietas izveides dodieties uz **Administrators** > **Darbvieta** un pēc tam atlasiet **Instalēšanas rokasgrāmata**.

## <a name="configure-the-sdk"></a>SDK konfigurēšana

Pēc SDK lejupielādes ar to var strādāt, izmantojot Xcode, lai iespējotu un definētu notikumus. Pastāv divi meklēšanas veidi

### <a name="option-1-using-cocoapods-recommended"></a>1. opcija. CocoaPods izmantošana (ieteicams)
CocoaPods ir Swift un Objective-C Cocoa projektu atkarību pārvaldnieks. Izmantojot to, būs vienkāršāk integrēt iesaistes ieskatus SDK darbam ar iOS. CocoaPods jums arī ļauj jaunināt uz jaunāko iesaistes ieskatu SDK versiju. Lūk, kā izmantot CocoaPods, lai integrētu iesaistes ieskatu SDK savā Xcode projektā. 

1. Instalējiet CocoaPods. 

1. Izveidojiet jaunu failu ar nosaukumu Podfile projekta saknes direktorijā un pievienojiet tam tālāk norādītos priekšrakstus.Aizstājiet YOUR_TARGET_PROJECT_NAME ar sava Xcode projekta nosaukumu. 
```objectivec
platform :ios, '9.0'  

 target '${YOUR_TARGET_PROJECT_NAME}' do 

     use_frameworks!   

     pod 'EIObjC.framework.debug' 

     pod 'EIObjC.framework.release' 

 end 
```
Iepriekš minētajā pod konfigurācijā ir ietvertas gan SDK atkļūdotāja, gan laidiena versijas. Izvēlieties, kurš no tiem ir vislabākais jūsu projektam.

1. Instalējiet šo atjauninājumu, izpildot šādu komandu: `pod install --repo-update `

### <a name="option-2-using-download-link"></a>2. opcija. Lejupielādes saites izmantošana

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
