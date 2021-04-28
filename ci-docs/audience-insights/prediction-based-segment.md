---
title: Prognozes izvadē balstīti segmenti
description: Izveidojiet segmentus, balstoties prognozes modeļa izvades entitījā.
ms.date: 03/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 488db1af865ce600ec012716327d053bee33aff8
ms.sourcegitcommit: a95c82f46c23f625cb34fceba021ccc70d4b1df6
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 03/30/2021
ms.locfileid: "5741438"
---
# <a name="create-a-segment-based-on-a-prediction-model-preview"></a><span data-ttu-id="d8237-103">Segmenta izveide, balstoties prognozes modelī (priekšskatījums)</span><span class="sxs-lookup"><span data-stu-id="d8237-103">Create a segment based on a prediction model (preview)</span></span>

<span data-ttu-id="d8237-104">Prognožu rezultāti reizēm attiecas tikai uz jūsu klientu apakškopu.</span><span class="sxs-lookup"><span data-stu-id="d8237-104">The results of predictions sometimes only apply to a subset of your customers.</span></span> <span data-ttu-id="d8237-105">Palieliniet ieteikumu personalizāciju, izveidojot segmentus no prognozes modeļu rezultātiem.</span><span class="sxs-lookup"><span data-stu-id="d8237-105">Increase the personalization of recommendations by creating segments from results of prediction models.</span></span> <span data-ttu-id="d8237-106">Piemēram, iespējams, vēlēsities sniegt konkrētus ieteikumus klientiem, kuri dod priekšroku noteikta veida pakalpojumam.</span><span class="sxs-lookup"><span data-stu-id="d8237-106">For example, you may want to give specific recommendations to customers that prefer a certain type of service.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="d8237-107">Priekšnosacījumi</span><span class="sxs-lookup"><span data-stu-id="d8237-107">Prerequisites</span></span>

- <span data-ttu-id="d8237-108">Vismaz [Līdzautora atļaujas](permissions.md) Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="d8237-108">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>

- <span data-ttu-id="d8237-109">Produkta ieteikumu, transakcijas zudumu, abonementa zudumu vai klienta darbības laika vērtības modeli konfigurē Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="d8237-109">A product recommendation, transactional churn, subscription churn, or customer lifetime value model configured in Customer Insights.</span></span> <span data-ttu-id="d8237-110">Lai iestatītu atšķirīgus modeļus, pārskatiet prasības:</span><span class="sxs-lookup"><span data-stu-id="d8237-110">Review the requirements to set up the different models:</span></span>

  - [<span data-ttu-id="d8237-111">Produktu ieteikumu modelis</span><span class="sxs-lookup"><span data-stu-id="d8237-111">Product recommendation model</span></span>](predict-product-recommendation.md)
  - [<span data-ttu-id="d8237-112">Abonementu zuduma modelis</span><span class="sxs-lookup"><span data-stu-id="d8237-112">Subscription churn model</span></span>](predict-subscription-churn.md)
  - [<span data-ttu-id="d8237-113">Transakciju zuduma modelis</span><span class="sxs-lookup"><span data-stu-id="d8237-113">Transactional churn model</span></span>](predict-transactional-churn.md)
  - [<span data-ttu-id="d8237-114">Klienta pastāvēšanas modeļa vērtība</span><span class="sxs-lookup"><span data-stu-id="d8237-114">Customer lifetime value model</span></span>](predict-customer-lifetime-value.md)

## <a name="create-a-customer-segment-based-on-predictions"></a><span data-ttu-id="d8237-115">Klientu segmenta izveide, pamatojoties uz prognozēm</span><span class="sxs-lookup"><span data-stu-id="d8237-115">Create a customer segment based on predictions</span></span>

1. <span data-ttu-id="d8237-116">Atveriet  **Informācija** > **Prognozes** un atlasiet cilni **Manas prognozes**.</span><span class="sxs-lookup"><span data-stu-id="d8237-116">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="d8237-117">Atlasiet vertikālo daudzpunkti blakus modelim, kuru vēlaties pārskatīt, un atlasiet **Skatīt**.</span><span class="sxs-lookup"><span data-stu-id="d8237-117">Select the vertical ellipses next to the model you want to review and select **View**.</span></span>

1. <span data-ttu-id="d8237-118">Rezultātu lapā atlasiet **Izveidot segmentu**.</span><span class="sxs-lookup"><span data-stu-id="d8237-118">On the results page, select **Create segment**.</span></span> <span data-ttu-id="d8237-119">Lai iegūtu papildu informāciju par rezultātu lapu, pārskatiet rakstu par modeli.</span><span class="sxs-lookup"><span data-stu-id="d8237-119">For more information about the results page, review the article about the model.</span></span>

   :::image type="content" source="media/prediction-create-segment.png" alt-text="Ekrānuzņēmums prognožu rezultātu lapai ar izceltu Segmenta izveides darbību.":::

1. <span data-ttu-id="d8237-121">Izveidojiet jaunu segmentu, balstoties atlasītā modeļa izvades entitījā.</span><span class="sxs-lookup"><span data-stu-id="d8237-121">Create a new segment based on the output entity of the selected model.</span></span> <span data-ttu-id="d8237-122">Papildinformācijai skatiet [Segmentu izveide un pārvaldība](segments.md).</span><span class="sxs-lookup"><span data-stu-id="d8237-122">For more information, see [Create and manage segments](segments.md).</span></span>