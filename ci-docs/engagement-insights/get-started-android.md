---
title: Darba sākšana ar Android SDK
description: Uzziniet, kā personalizēt un palaist Android SDK
author: britl
ms.reviewer: mhart
ms.custom: intro-internal
ms.author: britl
ms.date: 10/19/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: b06822b2c2d6a859bdf808f7800baef43c4ab874
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 02/16/2022
ms.locfileid: "8226178"
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

## <a name="integrate-the-sdk-into-your-application"></a>SDK integrēšana programmā
Sāciet procesu, atlasot darbvietu, atlasot Android mobilo platformu un lejupielādējot Android SDK.

- Lai atlasītu darbvietu, izmantojiet darbvietas pārslēdzēju kreisās puses navigācijas rūtī.

- Ja jums nav esošas darbvietas, atlasiet **Jauna darbvieta** un izpildiet tālāk norādītās darbības, lai izveidotu [jaunu darbvietu](create-workspace.md).

- Pēc darbvietas izveides dodieties uz **Administrators** > **Darbvieta** un pēc tam atlasiet **Instalēšanas rokasgrāmata**.

## <a name="configure-the-sdk"></a>SDK konfigurēšana

Pēc SDK lejupielādes ar to var strādāt, izmantojot Android Studio, lai iespējotu un definētu notikumus. Ir divi veidi:
### <a name="option-1-use-jitpack-recommended"></a>1. iespēja: izmantojiet JitPack (ieteicams)
1. Pievienojiet JitPack krātuvi saknes `build.gradle`:
    ```gradle
    allprojects {
        repositories {
            ...
            maven { url 'https://jitpack.io' }
        }
    }
    ```

1. Pievienojiet atkarību:
    ```gradle
    dependencies {
        implementation 'com.github.microsoft:engagementinsights-sdk-android:v1.0.0'
        api 'com.google.code.gson:gson:2.8.1'
    }
    ```

### <a name="option-2-use-download-link"></a>2. iespēja: izmantojiet lejupielādes saiti
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

## <a name="enable-auto-instrumentation"></a>Automātiskās instrumentācijas iespējošana

1. Pievienojiet tīkla un interneta atļaujas `AndroidManifest.xml` failā, kas atrodas mapē `manifests`.
    ```xml
    <manifest>
        ...
        <uses-permission android:name="android.permission.INTERNET" />
        <uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
    ```

1. Iestatiet iesaistes ieskatus SDK konfigurācijai, izmantojot savu `AndroidManifest.xml` failu, kas atrodas mapē .

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

   >[!NOTE]
   >`Action` notikumi jāpievieno manuāli.

1. (Nav obligāti) Citas konfigurācijas ietver galapunkta kolektora URL iestatīšanu. Tos var pievienot zem norīšanas galvenajiem metadatiem programmā `AndroidManifest.xml`.

   ```xml
        <meta-data
            android:name="com.microsoft.engagementinsights.endpointUrl"
            android:value="https://some-endpoint-url.com" />
   ```

## <a name="implement-custom-events"></a>Pielāgotu notikumu ieviešana

Pēc SDK inicializēšanas varat strādāt ar notikumiem un to rekvizītiem `MainActivity` vidē.


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

## <a name="set-user-details-for-your-event-optional"></a>Lietotāja informācijas iestatīšana savam notikumam (nav obligāti)

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
