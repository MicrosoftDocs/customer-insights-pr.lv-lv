---
title: Power Automate savienotājs | Microsoft Docs
description: Plūsmu veidošana programmā Microsoft Power Automate no Dynamics 365 Customer Insights.
ms.date: 01/20/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e973bb11b31c9e70b695ebec8aa2700fdaa5e44f
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597934"
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
Power Automate savienotājs nodrošina citas darbības, izņemot pieejamos trigerus. Papildinformāciju skatiet [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).

## <a name="create-a-power-automate-flow"></a>Izveidot Power Automate plūsmu

1. Sadaļā Auditorijas ieskati ejiet uz **Administrators** > **Eksportēšanas galamērķi**.

1. Elementā **Power Automate** atlasiet **Iestatīt**.

1. Customer Insights savienotājs (priekšskatījums) atveras programmā Power Automate. **Pierakstieties risinājumā** Power Automate.

1. Izvēlieties kādu no pieejamajiem trigeriem un pievienojiet jaunajai plūsmai papildu soļus. Papildinformāciju skatiet [Mākoņa plūsmas izveide programmā Power Automate](/power-automate/get-started-logic-flow).

Tālāk ir parādīts, kā izmantot plūsmas: 
- Publicē ziņojumu Microsoft Teams kanālā, ja neizdodas datu avota atsvaidzināšana. 
- Nosūtiet e-pasta ziņojumu datu īpašniekiem, kad tiek pārsvītrota segmenta sliekšņa vērtība.



[!INCLUDE[footer-include](../includes/footer-banner.md)]