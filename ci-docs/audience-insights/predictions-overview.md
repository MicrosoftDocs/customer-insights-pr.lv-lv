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
ms.openlocfilehash: 69ae945b22819521db217508c6fc232876346747
ms.sourcegitcommit: 6b07c9c3102761be162e4842f3c9fbc19f948a9b
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 05/25/2021
ms.locfileid: "6095729"
---
# <a name="predictions-overview"></a><span data-ttu-id="48884-103">Prognožu pārskats</span><span class="sxs-lookup"><span data-stu-id="48884-103">Predictions overview</span></span>

<span data-ttu-id="48884-104">Dynamics 365 Customer Insights ir pieejamas dažādas iespējas, kas izmanto AI un algoritmisko mācīšanos, lai prognozētu datus.</span><span class="sxs-lookup"><span data-stu-id="48884-104">Dynamics 365 Customer Insights comes with a variety of options that leverage AI and machine learning to predict data.</span></span> 

## <a name="out-of-box-models"></a><span data-ttu-id="48884-105">Iekļautie modeļi</span><span class="sxs-lookup"><span data-stu-id="48884-105">Out-of-box models</span></span>

<span data-ttu-id="48884-106">Visvienkāršākais veids, kā sākt ar datu prognozēšanu, ir iepriekš definēti modeļi, ko bieži dēvē par pirmās palaišanas modeļiem.</span><span class="sxs-lookup"><span data-stu-id="48884-106">The easiest way to start with predicting data are predefined models, often referred to as out-of-box models.</span></span> <span data-ttu-id="48884-107">Tiem ir nepieciešami tikai noteikti dati un struktūra, lai ātri ģenerētu ieskatus.</span><span class="sxs-lookup"><span data-stu-id="48884-107">They only require certain data and structure to generate insights quickly.</span></span> <span data-ttu-id="48884-108">Pašlaik ir pieejami šādi modeļi:</span><span class="sxs-lookup"><span data-stu-id="48884-108">Currently, the following models are available:</span></span> 
- <span data-ttu-id="48884-109">[Klienta mūža vērtība](predict-customer-lifetime-value.md): prognozē iespējamos klienta ieņēmumus visā mijiedarbībā ar uzņēmumu.</span><span class="sxs-lookup"><span data-stu-id="48884-109">[Customer lifetime value](predict-customer-lifetime-value.md): Predicts the potential revenue of a customer throughout the entire interaction with a business.</span></span> 
- <span data-ttu-id="48884-110">[Produkta ieteikums](predict-product-recommendation.md): iesaka prognozēšanas produktu ieteikumu kopas, pamatojoties uz pirkumu uzvedību un klientiem ar līdzīgiem pirkšanas modeļiem.</span><span class="sxs-lookup"><span data-stu-id="48884-110">[Product recommendation](predict-product-recommendation.md): Suggests sets of predictive product recommendations based on purchase behavior and customers with similar purchase patterns.</span></span>
- <span data-ttu-id="48884-111">[Abonementu zudums](predict-subscription-churn.md): Prognozē, vai pastāv risks, ka klients var pārtraukt izmantot jūsu uzņēmuma abonējamos produktus vai pakalpojumus.</span><span class="sxs-lookup"><span data-stu-id="48884-111">[Subscription churn](predict-subscription-churn.md): Predicts whether a customer is at risk for no longer using your company’s subscription products or services.</span></span>
- <span data-ttu-id="48884-112">[Transakciju zudums](predict-transactional-churn.md): Prognozē, vai klients vairs nepirks jūsu produktus vai pakalpojumus noteiktā laika periodā.</span><span class="sxs-lookup"><span data-stu-id="48884-112">[Transactional churn](predict-transactional-churn.md): Predict if a customer will no longer purchase your products or services in a certain time frame.</span></span>

## <a name="azure-machine-learning-integration"></a><span data-ttu-id="48884-113">Azure algoritmiskās mācīšanās integrēšana</span><span class="sxs-lookup"><span data-stu-id="48884-113">Azure Machine Learning integration</span></span>

<span data-ttu-id="48884-114">Ja organizācija jau izmanto algoritmiskās mācīšanās scenārijus, kuru pamatā algoritmiskā mācīšanās Azure eksperimenti, pielāgoto modeļu līdzeklis programmā Customer Insights palīdz savienot punktus.</span><span class="sxs-lookup"><span data-stu-id="48884-114">If an organization already uses machine learning scenarios based on Azure Machine Learning experiments, the custom models feature in Customer Insights helps to connect the dots.</span></span> <span data-ttu-id="48884-115">Izveidojiet darbplūsmas, kas palīdz izvēlēties datus, no kuriem vēlaties ģenerēt ieskatus, un kartējiet rezultātus uz vienotajiem klientu profiliem.</span><span class="sxs-lookup"><span data-stu-id="48884-115">Create workflows that help you choose the data you want to generate insights from and map the results to your unified customer profiles.</span></span> <span data-ttu-id="48884-116">Papildinformācijai skatiet [Pielāgoti algoritmiskās mācīšanās modeļi](custom-models.md).</span><span class="sxs-lookup"><span data-stu-id="48884-116">For more information, see [Custom machine learning models](custom-models.md).</span></span>

## <a name="ai-builder-prediction"></a><span data-ttu-id="48884-117">AI Builder prognoze</span><span class="sxs-lookup"><span data-stu-id="48884-117">AI Builder prediction</span></span>

<span data-ttu-id="48884-118">Dažreiz datu kopas ir nepilnīgas un trūkst dažu vērtību.</span><span class="sxs-lookup"><span data-stu-id="48884-118">Sometimes, data sets are incomplete and some values are missing.</span></span> <span data-ttu-id="48884-119">Customer Insights var palīdzēt prognozēt trūkstošās vērtības klienta entītijai un segmentiem.</span><span class="sxs-lookup"><span data-stu-id="48884-119">Customer Insights can help to predict missing values for the Customer entity and segments.</span></span> <span data-ttu-id="48884-120">Papildinformāciju skatiet rakstā [Daļējo datu pabeigšana ar prognozēm](predictions.md).</span><span class="sxs-lookup"><span data-stu-id="48884-120">For more information, see [Complete your partial data with predictions](predictions.md).</span></span>
