---
title: Segmenta izveide, pamatojoties uz prognoze modeli
description: Izveidojiet segmentus, balstoties prognozes modeļa izvades entitījā.
ms.date: 09/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: ed9c6247a1f9148628dc9b5217484e98a576224e
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610429"
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

1. Atlasiet modeli, kuru vēlaties pārskatīt, un atlasiet **Skats**.

1. Rezultātu lapā atlasiet **Izveidot segmentu**. Lai iegūtu papildu informāciju par rezultātu lapu, pārskatiet rakstu par modeli.

   :::image type="content" source="media/prediction-create-segment.png" alt-text="Ekrānuzņēmums prognožu rezultātu lapai ar izceltu Segmenta izveides darbību.":::

1. Izveidojiet jaunu segmentu, izmantojot atribūtus no atlasītā modeļa izvades entītijas. Papildinformācijai skatiet [Segmentu izveide un pārvaldība](segments.md).

> [!TIP]
> Segmentu prognoze modelim var izveidot arī lapā Segmenti **,** atlasot **Jauns** un izvēloties **Izveidot no** > **informācijas**. Papildinformāciju skatiet sadaļā [Jauna segmenta izveide ar ātriem segmentiem](segment-quick.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
