---
title: Power Automate savienotājs | Microsoft Docs
description: Izveidojiet plūsmas Microsoft Power Automate no Dynamics 365 Customer Insights.
ms.date: 01/20/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: fb1df4e9ab1f78300b8ec1f8dfdfbfbac0e71447
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268833"
---
# <a name="power-automate-connector-preview"></a>Power Automate savienotājs (priekšskatījums)

Aktivizējiet automatizētu konkrētu notikumu norisi datu izmaiņu gadījumā un pārvaldiet sarežģītākas plūsmas tieši pakalpojumā [Power Automate](https://flow.microsoft.com/).

## <a name="power-automate-triggers"></a>Power Automate trigeri

Izmantojiet trigerus, kas ļauj izveidot mākoņa plūsma un automatizēt atkārtojošos uzdevumu, piemēram, paziņojumu vai papildu darbību automatizēšana. 

- Trigeris, kad neizdodas atsvaidzināt datu avotu. 
- Trigeris, kad izdodas atsvaidzināt datu avotu.
- Trigeris, kad slieksnis ir šķērsots segmentā. Trigeris ir ierobežots, lai šķērsotu virs sliekšņa.
- Trigeris, kad biznesa pasākumā tiek pārsniegts slieksnis. Trigeris ir ierobežots, lai šķērsotu virs sliekšņa.
- Trigeris, kad tiek pabeigta pilnīga (datu avotu, segmentu, pasākumu,...) atsvaidzināšana.
- Trigeris, kad ir pabeigta apvienošanas procesa (karte, atbilstība, sapludināšana) atsvaidzināšana.

[Konfigurējiet trigerus programmā Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).

## <a name="power-automate-actions"></a>Power Automate darbības
Power Automate savienotājs nodrošina citas darbības, izņemot pieejamos trigerus. Papildinformāciju skatiet [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).

## <a name="create-a-power-automate-flow"></a>Izveidot Power Automate plūsmu

1. Sadaļā Auditorijas ieskati ejiet uz **Administrators** > **Eksportēšanas galamērķi**.

1. Elementā **Power Automate** atlasiet **Iestatīt**.

1. Customer Insights savienotājs (priekšskatījums) atveras programmā Power Automate. **Pierakstieties risinājumā** Power Automate.

1. Izvēlieties kādu no pieejamajiem trigeriem un pievienojiet jaunajai plūsmai papildu soļus. Papildinformāciju skatiet [Mākoņa plūsmas izveide programmā Power Automate](https://docs.microsoft.com/power-automate/get-started-logic-flow).

Tālāk ir parādīts, kā izmantot plūsmas: 
- Publicē ziņojumu Microsoft Teams kanālā, ja neizdodas datu avota atsvaidzināšana. 
- Nosūtiet e-pasta ziņojumu datu īpašniekiem, kad tiek pārsvītrota segmenta sliekšņa vērtība.



[!INCLUDE[footer-include](../includes/footer-banner.md)]