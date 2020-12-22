---
title: Power Automate savienotājs | Microsoft Docs
description: Izveidojiet plūsmas Microsoft Power Automate no Dynamics 365 Customer Insights.
ms.date: 08/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: ffe92414365b0b777691a4a2d585100e4fbea591
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406320"
---
# <a name="power-automate-connector-preview"></a>Power Automate savienotājs (priekšskatījums)

Aktivizējiet automatizētu konkrētu notikumu norisi datu izmaiņu gadījumā un pārvaldiet sarežģītākas plūsmas tieši pakalpojumā [Power Automate](https://flow.microsoft.com/).

## <a name="power-automate-triggers"></a>Power Automate trigeri

Var izmantot dažādus trigerus, kas ļauj izveidot plūsmas, lai automatizētu atkārtojošos uzdevumus, piemēram, paziņojumus vai papildu darbības. 

- Trigeris, kad neizdodas atsvaidzināt datu avotu. 
- Trigeris, kad izdodas atsvaidzināt datu avotu.
- Trigeris, kad slieksnis ir šķērsots segmentā. Trigeris ir ierobežots, lai šķērsotu virs sliekšņa.
- Trigeris, kad biznesa pasākumā tiek pārsniegts slieksnis. Trigeris ir ierobežots, lai šķērsotu virs sliekšņa.
- Trigeris, kad tiek pabeigta pilnīga (datu avotu, segmentu, pasākumu,...) atsvaidzināšana.
- Trigeris, kad ir pabeigta apvienošanas procesa (karte, atbilstība, sapludināšana) atsvaidzināšana.

[Konfigurējiet trigerus programmā Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).

## <a name="power-automate-actions"></a>Power Automate darbības
Power Automate savienotājs nodrošina citas darbības, izņemot pieejamos trigerus. Papildinformāciju skatiet [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).

## <a name="create-a-power-automate-flow-in-audience-insights"></a>Power Automate plūsmas izveide no auditorijas ieskatiem

1. Sadaļā Auditorijas ieskati skatiet **Administrators** > **Sistēma**.

1. Lapā **Sistēma** atlasiet cilni **Statuss**.

1. Sadaļā **Datu avoti** atlasiet **Plūsmas** un nolaižamajā sarakstā atlasiet **Izveidot plūsmu**.
   > [!div class="mx-imgBorder"]
   > ![Power Automate savienotājs, kas rāda plūsmas darbības izveidošanu](media/power-automate-connector-create-flow.png "Power Automate savienotājs, kas rāda plūsmas izveides darbību")

1. Sadaļā Power Automate atlasiet vienu no pieejamajiem trigeriem, lai izveidotu vēlamo plūsmu. Ja veidojat savu pirmo plūsmu, vispirms ir jāautentificējas, izmantojot Power Automate savienotāju.
