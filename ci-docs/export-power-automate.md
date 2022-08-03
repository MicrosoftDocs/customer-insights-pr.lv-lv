---
title: Power Automate savienotājs (priekšskatījums) | Microsoft dokumenti
description: Plūsmu veidošana programmā Microsoft Power Automate no Dynamics 365 Customer Insights.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f87bd6db7143294a264813f6c5c7d7963f303628
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196127"
---
# <a name="power-automate-connector-preview"></a>Power Automate savienotājs (priekšskatījums)

Aktivizējiet automatizētu konkrētu notikumu norisi datu izmaiņu gadījumā un pārvaldiet sarežģītākas plūsmas tieši pakalpojumā [Microsoft Power Automate](https://flow.microsoft.com/).

## <a name="known-limitations"></a>Zināmie ierobežojumi

- Ne vairāk kā 100 zvani uz 60 sekundēm. Izmantojiet [parametru](/connectors/customerinsights/#get-items-from-an-entity) $skip, lai vairākas reizes izsauktu API galapunktu.

## <a name="power-automate-triggers"></a>Power Automate trigeri

Izmantojiet trigerus, kas ļauj izveidot mākoņa plūsma un automatizēt atkārtojošos uzdevumu, piemēram, paziņojumu vai papildu darbību automatizēšana. Izmantojiet trigerus, ja:

- Neizdodas datu avots atsvaidzināt.
- Izdodas datu avots atsvaidzināšana.
- Segmentā tiek šķērsots slieksnis. Trigeris ir ierobežots, lai šķērsotu virs sliekšņa.
- Uzņēmējdarbības pasākumam tiek pārkāpts slieksnis. Tiek atbalstīti tikai uzņēmuma mērījumi bez dimensijas. Trigeris ir ierobežots, lai šķērsotu virs sliekšņa.
- Ir pabeigta pilna ieplānotā atsvaidzināšana. Šis trigeris nedarbojas manuāli sāktai atsvaidzināšanai.
- Ir pabeigta apvienošanās procesa atsvaidzināšana.

[Konfigurējiet trigerus programmā Power Automate.](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)

## <a name="power-automate-actions"></a>Power Automate darbības

Power Automate savienotājs nodrošina citas darbības, izņemot pieejamos trigerus. Papildinformāciju skatiet [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).

## <a name="create-a-power-automate-flow"></a>Izveidot Power Automate plūsmu

1. Dodieties uz **Administrators** > **Savienojumi**.

1. Elementā **Power Automate** atlasiet **Iestatīt**.

1. Customer Insights savienotājs (priekšskatījums) atveras programmā Power Automate. **Pierakstieties risinājumā** Power Automate.

1. Izvēlieties kādu no pieejamajiem trigeriem un pievienojiet jaunajai plūsmai papildu soļus. Papildinformāciju skatiet [Mākoņa plūsmas izveide programmā Power Automate](/power-automate/get-started-logic-flow).

Plūsmu izmantošanas piemēri: 
- Publicē ziņojumu Microsoft Teams kanālā, ja neizdodas datu avota atsvaidzināšana. 
- Nosūtiet e-pasta ziņojumu datu īpašniekiem, kad tiek pārsvītrota segmenta sliekšņa vērtība.

[!INCLUDE [footer-include](includes/footer-banner.md)]
