---
title: Android SDK paraugs
description: Projekta paraugs, lai uzzinātu par Android SDK
author: britl
ms.reviewer: m-hartmann
ms.author: britl
ms.date: 06/23/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: ba51961bc7f9555d7dba5b6a21c8636011438d75cba87bc132b896841c467a33
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035835"
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
