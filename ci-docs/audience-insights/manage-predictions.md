---
title: Koplietojamie uzdevumi prognožu scenārijiem
description: Uzziniet, kā pārvaldīt, novērst problēmas un precizēt prognozes.
ms.date: 05/17/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: dccb8dcca8f65f64973e46fed9d83034d58282e2
ms.sourcegitcommit: bcc47d15d4f0eacf008e4dbc09baac7f062b3ca8
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 06/29/2021
ms.locfileid: "6315887"
---
# <a name="manage-predictions"></a><span data-ttu-id="d54cf-103">Pārvaldīt prognozes</span><span class="sxs-lookup"><span data-stu-id="d54cf-103">Manage predictions</span></span>

<span data-ttu-id="d54cf-104">Šajā rakstā ir aplūkoti daži uzdevumi, kas prognoze, kas tiek koplietoti.</span><span class="sxs-lookup"><span data-stu-id="d54cf-104">This article discusses some tasks that most prediction scenarios share.</span></span>

## <a name="troubleshoot-a-failed-prediction"></a><span data-ttu-id="d54cf-105">Neizdevušās prognozes problēmas novēršana</span><span class="sxs-lookup"><span data-stu-id="d54cf-105">Troubleshoot a failed prediction</span></span>

1. <span data-ttu-id="d54cf-106">Atveriet  **Informācija** > **Prognozes** un atlasiet cilni **Manas prognozes**.</span><span class="sxs-lookup"><span data-stu-id="d54cf-106">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="d54cf-107">Atlasiet vertikālās elipses, kas atrodas blakus prognozei, kurai vēlaties skatīt kļūdu žurnālus.</span><span class="sxs-lookup"><span data-stu-id="d54cf-107">Select the vertical ellipses next to the prediction you want to view error logs for.</span></span>

1. <span data-ttu-id="d54cf-108">Atlasiet **Žurnāli**.</span><span class="sxs-lookup"><span data-stu-id="d54cf-108">Select **Logs**.</span></span>

1. <span data-ttu-id="d54cf-109">Pārskatīt visas kļūdas.</span><span class="sxs-lookup"><span data-stu-id="d54cf-109">Review all the errors.</span></span> <span data-ttu-id="d54cf-110">Pastāv vairāki kļūdu tipi, kas var rasties, un tie apraksta to, kas izraisīja kļūdu.</span><span class="sxs-lookup"><span data-stu-id="d54cf-110">There are several types of errors that can occur, and they describe what condition caused the error.</span></span> <span data-ttu-id="d54cf-111">Piemēram, kļūda, kurā nav pietiekami daudz datu, lai precīzi prognozētu, parasti tiek novērsta, ielādējot papildu datus Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="d54cf-111">For example, an error that there's not enough data to accurately predict is typically resolved by loading additional data into Customer Insights.</span></span>

## <a name="input-data-usability-report"></a><span data-ttu-id="d54cf-112">Ievades datu lietojamības atskaite</span><span class="sxs-lookup"><span data-stu-id="d54cf-112">Input data usability report</span></span>

<span data-ttu-id="d54cf-113">Ievades datu lietojamības atskaite sniedz konsolidētu pārskatu par kļūdām un brīdinājumiem, ko var ģenerēt jūsu pirmās izvēles prognozes.</span><span class="sxs-lookup"><span data-stu-id="d54cf-113">The input data usability report provides a consolidated view of the errors and warnings that your out-of-box predictions may be generating.</span></span> <span data-ttu-id="d54cf-114">Tajā sniegti arī ieteikumi, kā uzlabot modeļa veiktspēju.</span><span class="sxs-lookup"><span data-stu-id="d54cf-114">It also gives recommendations how to improve the model performance.</span></span>

<span data-ttu-id="d54cf-115">Pārskats ir pieejams pēc tam, kad modelis ir pabeidzis apmācības procesu.</span><span class="sxs-lookup"><span data-stu-id="d54cf-115">The report is available after a model has completed its training process.</span></span> <span data-ttu-id="d54cf-116">Tas ir izveidots katram modelim atsevišķi, neatkarīgi no tā, vai tas ir veiksmīgi pabeigts.</span><span class="sxs-lookup"><span data-stu-id="d54cf-116">It's created for each model separately, regardless if it completed successfully or not.</span></span>

### <a name="view-the-input-data-usability-report"></a><span data-ttu-id="d54cf-117">Skatīt ievades datu lietojamības atskaiti</span><span class="sxs-lookup"><span data-stu-id="d54cf-117">View the input data usability report</span></span>

<span data-ttu-id="d54cf-118">Kad pirmās izvēles modelis ir pabeidzis apmācības darbību, skatiet atskaiti:</span><span class="sxs-lookup"><span data-stu-id="d54cf-118">After an out-of-box model has completed its training step, view the report:</span></span>
- <span data-ttu-id="d54cf-119">Atlasiet daudzpunktes blakus modeļa nosaukumam un izvēlieties **Ievades datu lietojamības atskaite**.</span><span class="sxs-lookup"><span data-stu-id="d54cf-119">Select the ellipses next to the model name and choose **Input data usability report**.</span></span>
- <span data-ttu-id="d54cf-120">Atlasiet modeļa statusu, atlasiet sānu rūtī **Skatīt ievades datu lietojamības atskaiti**.</span><span class="sxs-lookup"><span data-stu-id="d54cf-120">Select the status of a model select **See Input data usability report** in the side pane.</span></span>
- <span data-ttu-id="d54cf-121">Sarakstā atlasot vienu no modeļiem un komandjoslā atlasot **Ievades datu lietojamības atskaite**.</span><span class="sxs-lookup"><span data-stu-id="d54cf-121">Selecting one of the models in the list and select **Input data usability report** in the command bar.</span></span>
- <span data-ttu-id="d54cf-122">Sarakstā atlasot vienu no modeļiem un komandjoslā atlasot **Ievades datu lietojamības atskaite**.</span><span class="sxs-lookup"><span data-stu-id="d54cf-122">Open the model results page and select **Input data usability report** in the command bar.</span></span>

### <a name="information-in-the-input-data-usability-report"></a><span data-ttu-id="d54cf-123">Detalizēta informācija ievades datu lietojamības atskaitē</span><span class="sxs-lookup"><span data-stu-id="d54cf-123">Information in the input data usability report</span></span>

<span data-ttu-id="d54cf-124">Šajās atskaites kolonnās ir noderīga informācija, lai uzlabotu modeļa datus.</span><span class="sxs-lookup"><span data-stu-id="d54cf-124">The following columns in the report contain helpful information to improve the data for the model.</span></span>

:::image type="content" source="media/input-data-usability-report.png" alt-text="Ievades datu lietojamības atskaites piemērs, kurā redzama tabula ar kļūdām, brīdinājumiem un ieteikumiem.":::

- <span data-ttu-id="d54cf-126">Nosaukums: aprakstošs kļūdas, brīdinājuma vai ieteikuma nosaukums.</span><span class="sxs-lookup"><span data-stu-id="d54cf-126">Name: Descriptive name of the error, warning, or recommendation.</span></span>
- <span data-ttu-id="d54cf-127">Solis: Modeļa fāze, apmācība vai rezultāts, uz ko attiecas informācija.</span><span class="sxs-lookup"><span data-stu-id="d54cf-127">Step: Model phase, train or score, the information refers to.</span></span>
- <span data-ttu-id="d54cf-128">Stāvoklis: informācijas nopietnība (kļūda, brīdinājums, ieteikums).</span><span class="sxs-lookup"><span data-stu-id="d54cf-128">State: Severity of the information (error, warning, recommendation).</span></span>
- <span data-ttu-id="d54cf-129">Kolonnas nosaukums: kolonna entītijā, kas jāmodificē, lai uzlabotu modeļa veiktspēju.</span><span class="sxs-lookup"><span data-stu-id="d54cf-129">Column name: Column in an entity that needs to be modified to improve the model performance.</span></span>
- <span data-ttu-id="d54cf-130">Kolonnas nosaukums: kolonna entītijā, kas jāmodificē, lai uzlabotu modeļa veiktspēju.</span><span class="sxs-lookup"><span data-stu-id="d54cf-130">Entity name: Name of the entity that needs to be modified to improve the model performance.</span></span>
- <span data-ttu-id="d54cf-131">Detalizēta informācija: detalizēta informācija par kļūdu, brīdinājumu vai ieteikumu.</span><span class="sxs-lookup"><span data-stu-id="d54cf-131">Details: Details about the error, warning, or recommendation.</span></span>

## <a name="refresh-a-prediction"></a><span data-ttu-id="d54cf-132">Atsvaidzināt prognozi</span><span class="sxs-lookup"><span data-stu-id="d54cf-132">Refresh a prediction</span></span>

<span data-ttu-id="d54cf-133">Prognozes tiks automātiski atsvaidzinātas ar vienu un to pašu [grafiku, ko jūsu dati atsvaidzina](system.md#schedule-tab) kā konfigurēts iestatījumos.</span><span class="sxs-lookup"><span data-stu-id="d54cf-133">Predictions will automatically refresh on the same [schedule your data refreshes](system.md#schedule-tab) as configured in settings.</span></span> <span data-ttu-id="d54cf-134">Tos var atsvaidzināt arī manuāli.</span><span class="sxs-lookup"><span data-stu-id="d54cf-134">You can refresh them manually too.</span></span>

1. <span data-ttu-id="d54cf-135">Atveriet  **Informācija** > **Prognozes** un atlasiet cilni **Manas prognozes**.</span><span class="sxs-lookup"><span data-stu-id="d54cf-135">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="d54cf-136">Atlasiet vertikālās elipses, kas atrodas blakus prognozei, kuru vēlaties atsvaidzināt.</span><span class="sxs-lookup"><span data-stu-id="d54cf-136">Select the vertical ellipses next to the prediction you want to refresh.</span></span>

1. <span data-ttu-id="d54cf-137">Atlasiet **Atsvaidzināt**.</span><span class="sxs-lookup"><span data-stu-id="d54cf-137">Select **Refresh**.</span></span>

## <a name="delete-a-prediction"></a><span data-ttu-id="d54cf-138">Dzēst prognozi</span><span class="sxs-lookup"><span data-stu-id="d54cf-138">Delete a prediction</span></span>

<span data-ttu-id="d54cf-139">Dzēšot prognozi, tiek noņemta arī tās izvades entītija.</span><span class="sxs-lookup"><span data-stu-id="d54cf-139">Deleting a prediction also removes its output entity.</span></span>

1. <span data-ttu-id="d54cf-140">Atveriet  **Informācija** > **Prognozes** un atlasiet cilni **Manas prognozes**.</span><span class="sxs-lookup"><span data-stu-id="d54cf-140">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="d54cf-141">Atlasiet vertikālās elipses, kas atrodas blakus prognozei, kuru vēlaties dzēst.</span><span class="sxs-lookup"><span data-stu-id="d54cf-141">Select the vertical ellipses next to the prediction you want to delete.</span></span>

1. <span data-ttu-id="d54cf-142">Atlasiet **Dzēst**.</span><span class="sxs-lookup"><span data-stu-id="d54cf-142">Select **Delete**.</span></span>
