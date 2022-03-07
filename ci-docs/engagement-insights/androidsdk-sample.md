---
title: Android SDK paraugs
description: Projekta paraugs, lai uzzinātu par Android SDK
author: britl
ms.reviewer: m-hartmann
ms.author: britl
ms.date: 06/23/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 2ee29a98192bb53bd92241d71c1a76ec2b7bf846
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 02/16/2022
ms.locfileid: "8229927"
---
# <a name="run-the-android-sdk-sample"></a>Android SDK parauga izpilde

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Šis Android projekta paraugs palīdz saprast, kā SDK darbojas programmā. Jums nevajadzēs rakstīt kodu. Vienkārši pievienojiet savu pieņemšanas atslēgu un uzreiz varēsit redzēt notikumus savā darbvietā.

## <a name="prerequisites"></a>Priekšnosacījumi

- [Android Studio](https://developer.android.com/studio)
- [Pieņemšanas atslēga](get-started-android.md)

## <a name="download-the-android-sdk-sample"></a>Android SDK parauga lejupielāde

1. [Lejupielādējiet iesaistes ieskatu Android SDK paraugu](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-android-sample.zip).
1. Atarhivēt saspiesto failu `ei-android-sample.zip`.
1. Atveriet tilpatspiedes mapi programmā Android Studio.
1. Failā `AndroidManifest.xml` aizstājiet virkni `"Your-Ingestion-Key"` ar savu darbvietas pieņemšanas atslēgu no iesaistes ieskatu sadaļas **Administrators** > **Darbvieta** > **Instalēšanas rokasgrāmata**. 

   > [!NOTE]
   > Sadaļu `${applicationId}` nav nepieciešams aizstāt. Tā tiek aizpildīta automātiski.

   ```xml
   <application>
   ...
       <provider
           android:authorities="${applicationId}.com.microsoft.engagementinsights.eiandroidsdk.AnalyticsContentProvider"
           android:name="microsoft.dynamics.engagementinsights.eiandroidsdk.AnalyticsContentProvider" />
       <meta-data
           android:name="com.microsoft.engagementinsights.ingestionKey"
           android:value="Your-Ingestion-Key" />
       <meta-data
           android:name="com.microsoft.engagementinsights.autoCapture"
           android:value="true" />
   ...
   </application>
   ```

1. Atlasiet **Palaist**, lai saktu projekta paraugu.
1. Skatiet darbvietas notikumus.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
