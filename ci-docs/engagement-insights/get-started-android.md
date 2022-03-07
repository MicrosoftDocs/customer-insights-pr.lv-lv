---
title: Darba sākšana ar Android SDK
description: Uzziniet, kā personalizēt un palaist Android SDK
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 06/23/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 77e63929bbcc7ecff34a3839af525b76ec3c7f21173ddc5f8f2d69f11c25c441
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036927"
---
# <a name="get-started-with-the-android-sdk"></a>Darba sākšana ar Android SDK

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Šajā ceļvedī ir sniegtas norādes par instrumentācijas procesu jūsu Android programmā ar Dynamics 365 Customer Insights iesaistes ieskatu SDK. Notikumus savā portālā varēsit skatīt pēc piecām minūtēm vai ātrāk.

## <a name="configuration-options"></a>Konfigurācijas opcijas
Tālāk uzskaitītās konfigurācijas opcijas ir iespējams nodot SDK:

- **ingestionKey**: pieņemšanas atslēgu izmanto, lai nosūtītu notikumus uz darbvietu.

## <a name="prerequisites"></a>Priekšnosacījumi

- Android Studio

- Minimālais Android API līmenis: 16 (Jelly Bean)

- Pieņemšanas atslēga (lai iegūtu, skatiet tālāk sniegtos norādījumus)

## <a name="step-1-integrate-the-sdk-into-your-application"></a>1. darbība. SDK integrēšana programmā
Sāciet procesu, atlasot darbvietu, atlasot Android mobilo platformu un lejupielādējot Android SDK.

- Lai atlasītu darbvietu, izmantojiet darbvietas pārslēdzēju kreisās puses navigācijas rūtī.

- Ja jums nav esošas darbvietas, atlasiet **Jauna darbvieta** un izpildiet tālāk norādītās darbības, lai izveidotu [jaunu darbvietu](create-workspace.md).

## <a name="step-2-configure-the-sdk"></a>2. darbība. SDK konfigurēšana

1. Pēc darbvietas izveides dodieties uz **Administrators** > **Darbvieta** un pēc tam atlasiet **Instalēšanas rokasgrāmata**. 

1. Lejupielādējiet [iesaistes ieskatus Android SDK](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-android-sdk.zip) un ievietojiet `eiandroidsdk-debug.aar` failu `libs` mapē.

1. Atveriet projekta līmeņa `build.gradle` failu un pievienojiet norādītos fragmentus:
    ```gradle
    dependencies {
        implementation(name: 'eiandroidsdk-debug', ext: 'aar')
        api 'com.google.code.gson:gson:2.8.1'
    }

    repositories {
        flatDir {
            dirs 'libs'
        }
    }
    ```

1. Iestatiet iesaistes ieskatus SDK konfigurācijai, izmantojot savu `AndroidManifest.xml` failu, kas atrodas mapē `manifests`. 
1. Kopējiet XML fragmentu no **Instalēšanas rokasgrāmatas**. `Your-Ingestion-Key` jābūt automātiski aizpildītam.

   > [!NOTE]
   > Sadaļu `${applicationId}` nav nepieciešams aizstāt. Tā tiek aizpildīta automātiski.
   

   ```xml
   <application>
   ...
       <provider
           android:authorities="${applicationId}.com.microsoft.engagementinsights.AnalyticsContentProvider"
           android:name="com.microsoft.engagementinsights.AnalyticsContentProvider" />
       <meta-data
           android:name="com.microsoft.engagementinsights.ingestionKey"
           android:value="Your-Ingestion-Key" />
       <meta-data
           android:name="com.microsoft.engagementinsights.autoCapture"
           android:value="true" />
   ...
   </application>
   ```

1. Iespējojiet vai atspējojiet `View` notikumu automātisku tveršanu, iestatot iepriekš minētajā `autoCapture` laukā vērtību `true` vai `false`.

1. (Nav obligāti) Citas konfigurācijas ietver galapunkta kolektora URL iestatīšanu. Tās var pievienot zem pieņemšanas atslēgas metadatiem sadaļā `AndroidManifest.xml`:
    ```xml
        <meta-data
            android:name="com.microsoft.engagementinsights.endpointUrl"
            android:value="https://some-endpoint-url.com" />
    ```

## <a name="step-3-initialize-the-sdk-from-mainactivity"></a>3. darbība. Inicializējiet SDK sadaļā MainActivity 

Pēc SDK inicializēšanas varat strādāt ar notikumiem un to rekvizītiem MainActivity vidē.

    
Java:
```java
Analytics analytics = new Analytics();
```

Kotlin:
```kotlin
var analytics = Analytics()
```

### <a name="set-property-for-all-events-optional"></a>Iestatīt rekvizītu visiem notikumiem (nav obligāti)
    
Java:
```java
analytics.setProperty("year", 2021);
```

Kotlin:
```kotlin
analytics.setProperty("year", 2021)
```

Konteksta notikumu rekvizītiem tiek atbalstīti šādi tipi:
- String
- Datums
- Dubulta
- Garš
- Boolean
- UUID

### <a name="track-an-event"></a>Izsekojiet notikumu

Java:
```java
Event event = new Event("video");
event.setProperty("duration", 320);
event.setProperty("ad_shown", true);
analytics.trackEvent(event);
```

Kotlin:
```kotlin
var event = Event("video")
event.setProperty("duration", 320)
event.setProperty("ad_shown", true)
analytics.trackEvent(event)
```

### <a name="set-user-details-for-your-event-optional"></a>Lietotāja informācijas iestatīšana savam notikumam (nav obligāti)

SDK ļauj definēt lietotāja informāciju, ko var nosūtīt kopā ar katru notikumu. Varat norādīt lietotāja informāciju, izsaucot `setUser(user: User)` API uz `Analytics` līmeni.

Java:
```java
User user = new User();
user.setName("testuser");
user.setEmail("abc@xyz.com");
analytics.setUser(user);
```

Kotlin:
```kotlin
var user = User()
user.name = "testuser"
user.email = "abc@xyz.com"
analytics.setUser(user)
```

Datu klase `User` satur šādus virknes rekvizītus:

- **localId**: lietotāja lokālais ID.
- **authId**: autentificēts lietotāja ID.
- **authType**: autentifikācijas tips, kas tiek izmantots autentificēta lietotāja ID iegūšanai.
- **name**: lietotāja vārds.
- **email**: lietotāja e-pasta adrese.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
