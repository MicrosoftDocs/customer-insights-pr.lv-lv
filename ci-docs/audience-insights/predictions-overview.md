---
title: Pārskats par atbalstītajiem prognožu scenārijiem
description: Prognoze scenārijiem un iespējām, uz kurām attiecas Dynamics 365 Customer Insights pieteikums.
ms.date: 05/18/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: get-started
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: b73046844f6009a2b163b5eaadf5f63f75cda1d8
ms.sourcegitcommit: b78c9680b213204e6b0ed47f0147205083f6a98f
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 07/12/2021
ms.locfileid: "6539170"
---
# <a name="predictions-overview"></a>Prognožu pārskats

Dynamics 365 Customer Insights ir pieejamas dažādas iespējas, kas izmanto AI un algoritmisko mācīšanos, lai prognozētu datus. 

## <a name="out-of-box-models"></a>Iekļautie modeļi

Visvienkāršākais veids, kā sākt ar datu prognozēšanu, ir iepriekš definēti modeļi, ko bieži dēvē par pirmās palaišanas modeļiem. Tiem ir nepieciešami tikai noteikti dati un struktūra, lai ātri ģenerētu ieskatus. Pašlaik ir pieejami šādi modeļi: 
- [Klienta mūža vērtība](predict-customer-lifetime-value.md): prognozē iespējamos klienta ieņēmumus visā mijiedarbībā ar uzņēmumu. 
- [Produkta ieteikums](predict-product-recommendation.md): iesaka prognozēšanas produktu ieteikumu kopas, pamatojoties uz pirkumu uzvedību un klientiem ar līdzīgiem pirkšanas modeļiem.
- [Abonementu zudums](predict-subscription-churn.md): Prognozē, vai pastāv risks, ka klients var pārtraukt izmantot jūsu uzņēmuma abonējamos produktus vai pakalpojumus.
- [Transakciju zudums](predict-transactional-churn.md): Prognozē, vai klients vairs nepirks jūsu produktus vai pakalpojumus noteiktā laika periodā.

## <a name="azure-machine-learning-integration"></a>Azure algoritmiskās mācīšanās integrēšana

Ja organizācija jau izmanto algoritmiskās mācīšanās scenārijus, kuru pamatā algoritmiskā mācīšanās Azure eksperimenti, pielāgoto modeļu līdzeklis programmā Customer Insights palīdz savienot punktus. Izveidojiet darbplūsmas, kas palīdz izvēlēties datus, no kuriem vēlaties ģenerēt ieskatus, un kartējiet rezultātus uz vienotajiem klientu profiliem. Papildinformācijai skatiet [Pielāgoti algoritmiskās mācīšanās modeļi](custom-models.md).

## <a name="ai-builder-prediction"></a>AI Builder prognoze

Dažreiz datu kopas ir nepilnīgas un trūkst dažu vērtību. Customer Insights var palīdzēt prognozēt trūkstošās vērtības klienta entītijai un segmentiem. Papildinformāciju skatiet rakstā [Daļējo datu pabeigšana ar prognozēm](predictions.md).
