---
title: Darba sākšana ar iesaistes ieskatu iespēju
description: Kopsavilkums par palīdzības resursiem, lai ātri uzsāktu darbu.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 08/31/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 644b125f5d140627d357630ded88dd6838d6edb7
ms.sourcegitcommit: fecdee73e26816c42d39d160d4d5cfb6c8a91596
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 09/15/2021
ms.locfileid: "7494603"
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

1. Pārskatiet **iesaistes ieskatu (priekšskatījuma) Lietošanas noteikumus** un **Paziņojumu par konfidencialitāti** un pēc tam atlasiet **Izpētīt demonstrāciju**, lai akceptētu šos iestatījumus.

1. Izpētiet produktu, izmantojot datu paraugu kopu.

##  <a name="step-3-set-up-a-workspace-and-add-code-to-your-website"></a>3. darbība. Iestatīt darbvietu un pievienot kodu tīmekļa vietnei

Darbvieta ir vieta, kurā lietotāja darbību varat skatīt reāllaikā un glabāt un pārvaldīt atskaites. Pievienojiet tīmekļa vietnei kodu, lai sāktu apkopot *notikumus*, darbības datus, kas nāk no lietotājiem.

1. [Izveidot darbvietu](create-workspace.md) un pievienot dalībniekus.

1. [Pievienojiet kodu vietnei](instrument-website.md) vai [mobilajai programmai](developer-resources.md#capture-events-from-mobile-apps), lai savā darbvietā skatītu lietotāja darbības.

1. Skatiet [reāllaika atskaiti](view-reports.md), kurā aktīvie lietotāji tiek rādīti pēc pārlūkprogrammas, ierīces, operētājsistēmas, atrašanās vietas un valodas. Varat arī izveidot [pielāgotas atskaites](custom-reports.md), lai izveidotu savas vizualizācijas.
    
## <a name="step-4-export-data-to-other-channels"></a>4. darbība. Eksportēt datus citos kanālos

Varat izveidot *precizētus notikumus* (virtuālu skatu) no jūsu tīmekļa vietnes analīzes datiem. Pēc tam filtrējiet un eksportējiet datus uz Azure Data Lake Storage. Eksportētos datus var lietot kā datu avotu. Papildinformācija: [Izveidot saiti starp auditorijas ieskatiem un iesaistes ieskatiem](integrate-audience-insights-engagement-insights.md).

1. [Izveidojiet precizētus notikumus](refined-events.md) eksportēšanai.

1. [Eksportējiet datus](export-events.md) uz Data Lake Storage.

1. [Izveidojiet saiti starp auditorijas ieskatiem un iesaistes ieskatiem](integrate-audience-insights-engagement-insights.md), lai kopīgotu datus starp abām iespējām.

1. Uzziniet, kā [dzēst un eksportēt notikumu datus, kuros ir ietverta personiskā informācija](delete-export-personal-data.md).
 
## <a name="step-5-stay-connected"></a>5. darbība. Palikt savienotam

Mēs novērtējam jūsu aktīvo dalību un izvērtējam visas attiecīgās atsauksmes, izstrādājot turpmākus laidienus. Dalieties ar savām atsauksmēm un ziņojiet par problēmām kādā no šiem kanāliem:
- [Kopiena](https://go.microsoft.com/fwlink/?linkid=2141648)
- [Sniegt atsauksmes](https://go.microsoft.com/fwlink/?linkid=2143222)
- [Atbalsta pieprasīšana](https://go.microsoft.com/fwlink/?linkid=2145734) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
