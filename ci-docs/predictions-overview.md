---
title: Pārskats par atbalstītajiem prognožu scenārijiem
description: Prognoze scenārijiem un iespējām, uz kurām attiecas Dynamics 365 Customer Insights pieteikums.
ms.date: 03/24/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: overview
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 11b0efeecf8bea893272e67d29b1c6622771110c
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643932"
---
# <a name="predictions-overview"></a>Prognožu pārskats

Dynamics 365 Customer Insights ir pieejamas dažādas iespējas, kas izmanto AI un algoritmisko mācīšanos, lai prognozētu datus. 

## <a name="out-of-box-models"></a>Iekļautie modeļi

Visvienkāršākais veids, kā sākt ar datu prognozēšanu, ir iepriekš definēti modeļi, ko bieži dēvē par pirmās palaišanas modeļiem. Tiem ir nepieciešami tikai noteikti dati un struktūra, lai ātri ģenerētu ieskatus. Pašlaik ir pieejami šādi modeļi: 

# <a name="individual-consumers-b-to-c"></a>[Atsevišķi patērētāji (B2C)](#tab/b2c)

- [Klienta mūža vērtība](predict-customer-lifetime-value.md): prognozē iespējamos klienta ieņēmumus visā mijiedarbībā ar uzņēmumu.
- [Produkta ieteikums](predict-product-recommendation.md): iesaka prognozēšanas produktu ieteikumu kopas, pamatojoties uz pirkumu uzvedību un klientiem ar līdzīgiem pirkšanas modeļiem.
- [Abonementu zudums](predict-subscription-churn.md): Prognozē, vai pastāv risks, ka klients var pārtraukt izmantot jūsu uzņēmuma abonējamos produktus vai pakalpojumus.
- [Transakciju zudums](predict-transactional-churn.md): Prognozē, vai klients vairs nepirks jūsu produktus vai pakalpojumus noteiktā laika periodā.
- [Sentimenta analīze](sentiment-analysis.md): analizējiet klientu atsauksmju noskaņojumu un identificējiet bieži minētos biznesa aspektus.

# <a name="business-accounts-b-to-b"></a>[Uzņēmumu konti (B2B)](#tab/b2b)

- [Transakciju zudums](predict-transactional-churn.md): Prognozē, vai klients vairs nepirks jūsu produktus vai pakalpojumus noteiktā laika periodā.

---

> [!TIP]
> Mēs iesakām regulāri atsvaidzināt ārpus kastes esošos modeļus ar atjauninātiem datiem, lai nodrošinātu, ka tie precīzi informē jūsu biznesa lietošanas gadījumu. Dati tiek atsvaidzināti ekspromta laikā, kad sistēma uzņem jaunus vai atjauninātus datu avotus. Tomēr modeļi tikai šajā gadījumā tiks atkārtoti uzsvērti un turpinās izmantot esošos mācību datus.
> 
> Atjaunināšanas **grafiku** var konfigurēt, konfigurācijas pieredzē iestatot modeļa pārkvalifikācijas grafiku. Modelis pārkvalificēsies un reģistrēsies šajā grafikā, kuru varat mainīt jebkurā laikā.


## <a name="azure-machine-learning-integration"></a>Azure algoritmiskās mācīšanās integrēšana

Ja organizācija jau izmanto algoritmiskās mācīšanās scenārijus, kuru pamatā algoritmiskā mācīšanās Azure eksperimenti, pielāgoto modeļu līdzeklis programmā Customer Insights palīdz savienot punktus. Izveidojiet darbplūsmas, kas palīdz izvēlēties datus, no kuriem vēlaties ģenerēt ieskatus, un kartējiet rezultātus uz vienotajiem klientu profiliem. Papildinformācijai skatiet [Pielāgoti algoritmiskās mācīšanās modeļi](custom-models.md).

## <a name="ai-builder-prediction"></a>AI Builder prognoze

Dažreiz datu kopas ir nepilnīgas un trūkst dažu vērtību. Customer Insights var palīdzēt prognozēt trūkstošās vērtības klienta entītijai un segmentiem. Papildinformāciju skatiet rakstā [Daļējo datu pabeigšana ar prognozēm](predictions.md).