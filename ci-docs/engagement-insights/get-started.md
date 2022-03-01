---
title: Darba sākšana ar iesaistes ieskatu iespēju
description: Kopsavilkums par palīdzības resursiem, lai ātri uzsāktu darbu.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 12/21/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 5ee1567cea834670a16aaa3253912b7957ce26b3
ms.sourcegitcommit: 86739a3f238162fc96837270b5d184e648fab15c
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 08/20/2021
ms.locfileid: "7405367"
---
# <a name="get-started-with-dynamics-365-customer-insights-engagement-insights-capability-public-preview"></a>Darba sākšana ar Dynamics 365 Customer Insights iesaistes ieskatu iespēju (publiskais priekšskatījums)

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Iesaistes ieskatu iespēja ļauj apkopot un izmērīt klientu uzvedību jūsu vietnē. Tā ir integrēta ar auditorijas ieskatu iespējām, lai kopā ar klientu profila pārskatiem būtu redzama bagātīga reāllaika uzvedības analīze. Šajā rakstā norādītās saites palīdz ātri konfigurēt un iestatīt vidi.

## <a name="step-1-review-prerequisites"></a>1. darbība. Pārskatiet priekšnosacījumus

Vispirms ir nepieciešams aktīvs Microsoft Azure Active Directory lietotāja konts. Pēc tam pirms iesaistes ieskatu darbvietas iestatīšanas izlasiet tālāk norādītos rakstus.

- Pārskatīt un piekrist [Pakalpojuma nosacījumiem](terms-of-service.md) ar Microsoft.  
- Izlasiet rakstu [Sīkfailu pārvaldība un lietotāja piekrišana](user-consent-storage.md). Pēc šī raksta pārskatīšanas novērtējiet, vai ir jāatjaunina lietotāja piekrišanas paziņojums. Ja jums iepriekš nav bijuši “nebūtiski” sīkfaili, iespējams, būs jāatjaunina vietnes politika.
- Pārskatiet [glosāriju](glossary.md), lai ātri iepazīstinātu ar galvenajiem terminiem un jēdzieniem.

## <a name="step-2-explore-engagement-insights"></a>2. darbība. Iepazīstieties ar iesaistes ieskatiem

Pirmoreiz apmeklējot iesaistes ieskatus, varat konfigurēt iestatījumus, pārskatīt politikas un izpētīt šo produktu.

1. Piesakieties [iesaistes ieskatu iespēju portālā](https://pi.dynamics.com), izmantojot savu Microsoft Azure Active Directory lietotāja kontu. (Tas var būt jūsu mācību vai darba konts.)

1. Atlasiet savu reģionu un izmantojiet šo izvēles rūtiņu, lai norādītu, vai vēlaties piedalīties atjauninājumu un piedāvājumu saņemšanai e-pasta ziņojumā.

1. Pārskatiet **iesaistes ieskatu (priekšskatījums) lietošanas noteikumus** un **Paziņojumu par konfidencialitāti** un tad atlasiet **Izpētīt demonstrāciju**, lai to akceptētu.

1. Izpētiet produktu, izmantojot datu paraugu kopu.

##  <a name="step-3-set-up-a-workspace-and-add-code-to-your-website"></a>3. darbība. Iestatīt darbvietu un pievienot kodu tīmekļa vietnei

Darbvietā varat apskatīt lietotāju aktivitātes reāllaikā, kā arī saglabāt un pārvaldīt atskaites. Pievienojiet tīmekļa vietnei kodu, lai sāktu apkopot *notikumus*, darbības datus, kas nāk no lietotājiem.

1. [Izveidot darbvietu](create-workspace.md) un pievienot dalībniekus.

1. [Pievienojiet kodu vietnei](instrument-website.md) vai [mobilajai programmai](developer-resources.md#capture-events-from-mobile-apps), lai savā darbvietā skatītu lietotāja darbības.

1. Skatīt [reāllaika atskaiti](view-reports.md), kurā aktīvie lietotāji tiek rādīti pēc pārlūkprogrammas, ierīces, operētājsistēmas, atrašanās vietas un valodas. Varat arī izveidot [pielāgotas atskaites](custom-reports.md), lai izveidotu savas vizualizācijas.
    
## <a name="step-4-export-data-to-other-channels"></a>4. darbība. Eksportēt datus citos kanālos

Varat izveidot *precizētus notikumus* (virtuālu skatu) no jūsu tīmekļa vietnes analīzes datiem. Pēc tam filtrējiet un eksportējiet datus uz Azure Data Lake Storage. Eksportētos datus var lietot kā datu avotu. Papildinformācija: [Izveidot saiti starp auditorijas ieskatiem un iesaistes ieskatiem](integrate-audience-insights-engagement-insights.md).

1. [Izveidojiet precizētus notikumus](refined-events.md) eksportēšanai.

1. [Eksportējiet datus](export-events.md) uz Data Lake Storage.

1. Uzziniet, kā [dzēst un eksportēt notikumu datus, kuros ir ietverta personiskā informācija](delete-export-personal-data.md).
 
## <a name="step-5-stay-connected"></a>5. darbība. Palikt savienotam

Mēs novērtējam jūsu aktīvo dalību un plānojam ņemt vērā visas attiecīgās atsauksmes, izstrādājot turpmākus laidienus. Dalieties ar savām atsauksmēm un ziņojiet par problēmām kādā no šiem kanāliem:
- [Kopiena](https://go.microsoft.com/fwlink/?linkid=2141648)
- [Sniegt atsauksmes](https://go.microsoft.com/fwlink/?linkid=2143222)
- [Atbalsta pieprasīšana](https://go.microsoft.com/fwlink/?linkid=2145734) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
