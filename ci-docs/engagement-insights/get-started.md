---
title: Darba sākšana ar iesaistes ieskatu iespēju
description: Kopsavilkums par palīdzības resursiem, lai ātri uzsāktu darbu.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: c435810e712bbbf69f8f1cfb582fc0a971566de6
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 02/16/2022
ms.locfileid: "8225607"
---
# <a name="get-started-with-dynamics-365-customer-insights-engagement-insights-capability-public-preview"></a>Darba sākšana ar Dynamics 365 Customer Insights iesaistes ieskatu iespēju (publiskais priekšskatījums)

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Iesaistes ieskatu iespēja ļauj apkopot un izmērīt klientu uzvedību jūsu vietnē. Tā ir integrēta ar auditorijas ieskatu iespējām, lai kopā ar klientu profila pārskatiem būtu redzama bagātīga reāllaika uzvedības analīze. Šajā rakstā norādītās saites palīdz ātri konfigurēt un iestatīt vidi.

## <a name="step-1-review-prerequisites"></a>1. darbība. Pārskatiet priekšnosacījumus

Vispirms ir nepieciešams aktīvs Microsoft Azure Active Directory (AAD) lietotāja konts. Pēc tam pirms iesaistes ieskatu darbvietas iestatīšanas izlasiet tālāk norādītos rakstus.

- Pārskatiet un piekrītiet [Pakalpojuma nosacījumiem](terms-of-service.md) ar Microsoft.  
- Izlasiet rakstu [Sīkfailu pārvaldība un lietotāja piekrišana](user-consent-storage.md). Izvērtējiet, vai ir jāatjaunina lietotāja piekrišanas paziņojums. Ja jums iepriekš nav bijuši “nebūtiski” sīkfaili, iespējams, būs jāatjaunina vietnes politika.
- Pārskatiet [glosāriju](glossary.md), lai ātri iepazīstinātu ar galvenajiem terminiem un jēdzieniem.

## <a name="step-2-explore-engagement-insights"></a>2. darbība. Iepazīstieties ar iesaistes ieskatiem

Pirmoreiz apmeklējot iesaistes ieskatus, varat konfigurēt iestatījumus, pārskatīt politikas un izpētīt iespējas.

1. Piesakieties [iesaistes ieskatu iespēju portālā](https://home.ci.ai.dynamics.com/app/engagement-insights), izmantojot savu Microsoft AAD lietotāja (mācību vai darba) kontu.

1. Atlasiet savu reģionu un atzīmējiet izvēles rūtiņu, ja vēlaties saņemt atjauninājumus un piedāvājumus e-pastā.

1. Pārskatiet iesaistes ieskatu (priekšskatījuma) **Lietošanas noteikumus** un **Paziņojumu par konfidencialitāti** un pēc tam atlasiet **Izpētīt demonstrāciju**, lai akceptētu šos iestatījumus.

1. Izpētiet produktu, izmantojot datu paraugu kopu.

##  <a name="step-3-set-up-a-workspace-and-create-reports"></a>3. darbība. Darbvietas iestatīšana un atskaišu izveide

Darbvieta ir vieta, kurā lietotāja darbību varat skatīt reāllaikā un glabāt un pārvaldīt atskaites. Pievienojiet tīmekļa vietnei kodu, lai sāktu apkopot *notikumus*, darbības datus, kas nāk no lietotājiem.

1. [Izveidot darbvietu](create-workspace.md) un pievienot dalībniekus.

1. [Pievienojiet kodu tīmekļa vietnei](instrument-website.md) vai [mobilajai programmai](developer-resources.md#capture-events-from-mobile-apps), lai savā darbvietā skatītu lietotāja darbības.

1. Skatiet [reāllaika atskaiti](view-reports.md), kurā aktīvie lietotāji tiek rādīti pēc pārlūkprogrammas, ierīces, operētājsistēmas, atrašanās vietas un valodas. Varat arī izveidot [pielāgotas atskaites](custom-reports.md), lai izveidotu savas vizualizācijas.

1. Izveidojiet [dimensijas](dimensions.md), lai šķirotu palīgus pēc jauniem un lietotājiem, kas atgriežas, [metrikas](metrics.md), kas palīdz labāk izprast lietotāja uzvedību, un [segmentus](segments.md), lai identificētu bardošanas apakškopas, pamatojoties uz rādītājiem vai mijiedarbību ar vietni.
    
## <a name="step-4-export-data-to-other-channels"></a>4. darbība. Eksportēt datus citos kanālos

Varat izveidot *precizētus notikumus* (virtuālu skatu) no jūsu tīmekļa vietnes analīzes datiem. Pēc tam filtrējiet un eksportējiet datus uz Azure Data Lake Storage. Eksportētos datus var lietot kā datu avotu.

1. [Izveidojiet precizētus notikumus](refined-events.md) eksportēšanai.

1. [Datu eksportēšana](export-events.md) uz Azure Data Lake Storage.

1. [Izveidojiet saiti starp auditorijas ieskatiem un iesaistes ieskatiem](integrate-audience-insights-engagement-insights.md), lai kopīgotu datus starp abām iespējām.

1. [Atpazīstiet tīmekļa notikumus no iepriekš autentificētiem lietotājiem](unknown-to-known.md) ar līdzekli **nav zināms**.

1. Uzziniet, kā [dzēst un eksportēt notikumu datus, kuros ir ietverta personiskā informācija](delete-export-personal-data.md).

## <a name="step-5-create-and-manage-funnel-reports"></a>5. darbība. Piltuves atskaišu izveide un pārvaldība

Piltuves atskaitē tiek apkopota informācija par darbībām, kas tiek veiktas automatizētas kampaņas laikā jūsu tīmekļa vietnē vai mobilajā programmā. Papildus standarta profila atskaišu un pielāgotu atskaišu veidošanai varat izveidot piltuves atskaiti, lai identificētu klientu ceļus pirms iegādes. 

1. [Izveidojiet piltuves atskaiti, ](funnel-reports.md), lai informētu lēmumus un identificētu jomas, kurās jāveic optimizācijas un procesa uzlabojumi.

1. Izveidojiet starpkanālu piltuves atskaites, kad mobilā programma ir pielāgota, izmantojot iesaistes ieskatus [Android SDK](get-started-android.md) vai [iOS SDK](get-started-ios.md).

1. Izmantojiet [piltuves ieskatus](funnel-reports.md#funnel-insights), lai gūtu dziļāku ieskatu par klientu uzvedību attiecībā uz piltuves atskaites darbībām.
 
## <a name="step-6-stay-connected"></a>6. darbība. Palikt savienotam

Mēs novērtējam jūsu aktīvo dalību un izvērtējam visas attiecīgās atsauksmes, izstrādājot turpmākus laidienus. Dalieties ar savām atsauksmēm un ziņojiet par problēmām kādā no šiem kanāliem:
- [Kopiena](https://go.microsoft.com/fwlink/?linkid=2141648)
- [Sniegt atsauksmes](https://go.microsoft.com/fwlink/?linkid=2143222)
- [Atbalsta pieprasīšana](https://go.microsoft.com/fwlink/?linkid=2145734) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
