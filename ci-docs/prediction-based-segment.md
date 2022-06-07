---
title: Prognozes izvadē balstīti segmenti
description: Izveidojiet segmentus, balstoties prognozes modeļa izvades entitījā.
ms.date: 03/24/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: b0b3357cdf3c049bd92f6c3f690f27433df9117b
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643752"
---
# <a name="create-a-segment-based-on-a-prediction-model-preview"></a>Segmenta izveide, balstoties prognozes modelī (priekšskatījums)

Prognožu rezultāti reizēm attiecas tikai uz jūsu klientu apakškopu. Palieliniet ieteikumu personalizāciju, izveidojot segmentus no prognozes modeļu rezultātiem. Piemēram, iespējams, vēlēsities sniegt konkrētus ieteikumus klientiem, kuri dod priekšroku noteikta veida pakalpojumam. 

## <a name="prerequisites"></a>Priekšnosacījumi

- Vismaz [Līdzautora atļaujas](permissions.md) Customer Insights.

- Produkta ieteikumu, transakcijas zudumu, abonementa zudumu vai klienta darbības laika vērtības modeli konfigurē Customer Insights. Lai iestatītu atšķirīgus modeļus, pārskatiet prasības:

  - [Produktu ieteikumu modelis](predict-product-recommendation.md)
  - [Abonementu zuduma modelis](predict-subscription-churn.md)
  - [Transakciju zuduma modelis](predict-transactional-churn.md)
  - [Klienta pastāvēšanas modeļa vērtība](predict-customer-lifetime-value.md)

## <a name="create-a-customer-segment-based-on-predictions"></a>Klientu segmenta izveide, pamatojoties uz prognozēm

1. Atveriet  **Informācija** > **Prognozes** un atlasiet cilni **Manas prognozes**.

1. Atlasiet vertikālo daudzpunkti blakus modelim, kuru vēlaties pārskatīt, un atlasiet **Skatīt**.

1. Rezultātu lapā atlasiet **Izveidot segmentu**. Lai iegūtu papildu informāciju par rezultātu lapu, pārskatiet rakstu par modeli.

   :::image type="content" source="media/prediction-create-segment.png" alt-text="Ekrānuzņēmums prognožu rezultātu lapai ar izceltu Segmenta izveides darbību.":::

1. Izveidojiet jaunu segmentu, balstoties atlasītā modeļa izvades entitījā. Papildinformācijai skatiet [Segmentu izveide un pārvaldība](segments.md).