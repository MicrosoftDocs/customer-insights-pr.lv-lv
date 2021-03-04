---
title: Reāllaika datu uzņemšana un ierobežojumi
description: Vispārīga informācija par reāllaika iespējām rīkā auditorijas ieskati.
ms.date: 10/27/2020
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 7421ed9d2cb399d546815b2d1b0ea5ec51ca6b6d
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270289"
---
# <a name="real-time-data-ingestion-preview"></a><span data-ttu-id="bfef9-103">Reāllaika datu uzņemšana (priekšskatījums)</span><span class="sxs-lookup"><span data-stu-id="bfef9-103">Real-time data ingestion (preview)</span></span>

<span data-ttu-id="bfef9-104">Teju reāllaika funkcionalitāte ļauj sekunžu laikā redzēt pēdējo mijiedarbību, kura jūsu klientiem ir bijusi ar jūsu precēm vai pakalpojumiem.</span><span class="sxs-lookup"><span data-stu-id="bfef9-104">The near real-time functionality lets you see, within seconds, the latest interactions that your customers have made with your products or services.</span></span>

<span data-ttu-id="bfef9-105">[Plānotā atjaunināšana](system.md#schedule-tab) ietver lielu skaitu ierakstu un vairākas sarežģītas operācijas.</span><span class="sxs-lookup"><span data-stu-id="bfef9-105">[Scheduled refreshes](system.md#schedule-tab) include large numbers of records and several complex operations.</span></span> <span data-ttu-id="bfef9-106">Vispirms dati tiek izvilkti no datu avota.</span><span class="sxs-lookup"><span data-stu-id="bfef9-106">First, data is pulled from the data source.</span></span> <span data-ttu-id="bfef9-107">Pēc tam dati ir apvienoti un bagātināti ar papildinformāciju.</span><span class="sxs-lookup"><span data-stu-id="bfef9-107">Next, the data is unified, and then enriched with additional information.</span></span> <span data-ttu-id="bfef9-108">Katra šī procesa palaišana var aizņemt vairākas minūtes vai stundas.</span><span class="sxs-lookup"><span data-stu-id="bfef9-108">Every run of this process can take minutes to hours.</span></span>

<span data-ttu-id="bfef9-109">Reāllaika funkcionalitāte nodrošina tūlītēju datu patēriņu, kamēr turpmāk plānotā atsvaidzināšana izrauj šos datus no datu avota.</span><span class="sxs-lookup"><span data-stu-id="bfef9-109">The real-time functionality provides data immediately for consumption, until the subsequent scheduled refresh pulls this data from the data source.</span></span>

<span data-ttu-id="bfef9-110">Reāllaika atjauninājumiem ir derīguma laiks, pēc kura tie vairs nepārlabo vērtību no datu avota:</span><span class="sxs-lookup"><span data-stu-id="bfef9-110">Real-time updates have an expiration time after which they no longer override the value from the data source:</span></span>

- <span data-ttu-id="bfef9-111">Profila atjauninājumi tiks saglabāti 4 stundas</span><span class="sxs-lookup"><span data-stu-id="bfef9-111">Profile updates will be kept for 4 hours</span></span>
- <span data-ttu-id="bfef9-112">Darbības tiks saglabātas 30 dienas</span><span class="sxs-lookup"><span data-stu-id="bfef9-112">Activities will be kept for 30 days</span></span>

<span data-ttu-id="bfef9-113">Šīs vērtības ir API izsaukuma parametri, kuras varat mainīt.</span><span class="sxs-lookup"><span data-stu-id="bfef9-113">These values are API call parameters that you can change.</span></span> <span data-ttu-id="bfef9-114">To mērķis ir nodrošināt, lai avota dati paliktu jūsu patiesības avots.</span><span class="sxs-lookup"><span data-stu-id="bfef9-114">They aim to ensure that your source data remains your source of truth.</span></span> <span data-ttu-id="bfef9-115">Ja vēlaties, lai reāllaika atjauninājumi tiktu iekļauti ilgāku laiku, tie ir jāpievieno datu avotam tā, lai tie tiktu vilkti nākamajā plānotajā atsvaidzināšanas laikā.</span><span class="sxs-lookup"><span data-stu-id="bfef9-115">If you want real-time updates to be included for longer, you need to add them to a data source so they get pulled during the next scheduled refresh.</span></span>

## <a name="real-time-update-of-the-unified-customer-profile-fields"></a><span data-ttu-id="bfef9-116">Vienotā klienta profila lauku atjaunināšana reāllaikā</span><span class="sxs-lookup"><span data-stu-id="bfef9-116">Real-time update of the unified customer profile fields</span></span>

<span data-ttu-id="bfef9-117">Atjauninātie profili tiks parādīti klienta kartīšu skatā vai jebkurā citā vizualizācijā dažu sekunžu laikā.</span><span class="sxs-lookup"><span data-stu-id="bfef9-117">Updated profiles will show in the customer card view, or any other visualization, within a few seconds.</span></span>

<span data-ttu-id="bfef9-118">Tā kā reāllaika operācijas notiek pēc tam, kad ir notikusi datu apvienošana, tās attiecas vienīgi uz vienotiem klientu profiliem.</span><span class="sxs-lookup"><span data-stu-id="bfef9-118">Because real-time operations take place after the data unification has happened, they only apply to the unified customer profiles.</span></span> <span data-ttu-id="bfef9-119">Līdz ar to reāllaika profila izmaiņas neatjauninās mērus, segmentu elementus vai bagātināšanu.</span><span class="sxs-lookup"><span data-stu-id="bfef9-119">Consequently, real-time profile changes will not update measures, segment membership, or enrichments.</span></span>

### <a name="limitations"></a><span data-ttu-id="bfef9-120">Ierobežojumi</span><span class="sxs-lookup"><span data-stu-id="bfef9-120">Limitations</span></span>

- <span data-ttu-id="bfef9-121">Klientu profilus var atjaunināt, taču ne izveidot vai dzēst.</span><span class="sxs-lookup"><span data-stu-id="bfef9-121">Customer profiles can be updated, but not created or deleted.</span></span>
- <span data-ttu-id="bfef9-122">Reāllaika atjauninājumu eksportēšana ārējās sistēmās, piemēram Power BI, pašlaik nav iespējama.</span><span class="sxs-lookup"><span data-stu-id="bfef9-122">Exporting real-time updates to external systems, like Power BI, is not possible at the moment.</span></span>

## <a name="real-time-creation-of-activities"></a><span data-ttu-id="bfef9-123">Darbību izveide reāllaikā</span><span class="sxs-lookup"><span data-stu-id="bfef9-123">Real-time creation of activities</span></span>

<span data-ttu-id="bfef9-124">Reāllaika API ļauj publicēt jaunu darbību no avota sistēmas (atsevišķa avota ieraksta) uz vienoto klienta profilu.</span><span class="sxs-lookup"><span data-stu-id="bfef9-124">The real-time API lets you publish a new activity from your source system (an individual source record) to a unified customer profile.</span></span> <span data-ttu-id="bfef9-125">Jaunā darbība dažu sekunžu laikā būs pieejama kā vienota darbība šī vienota klienta profila laika skalā.</span><span class="sxs-lookup"><span data-stu-id="bfef9-125">The new activity will be available as a unified activity in that unified customer profile's timeline within seconds.</span></span> <span data-ttu-id="bfef9-126">Laika skalu varat skatīt klienta kartes skatā vai jebkurā citā jūsu konfigurētajā laika skalas integrācijā.</span><span class="sxs-lookup"><span data-stu-id="bfef9-126">You can see the timeline in the customer card view or any other timeline integration you configured.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="bfef9-127">Darbības ir nemaināmas.</span><span class="sxs-lookup"><span data-stu-id="bfef9-127">Activities are immutable.</span></span> <span data-ttu-id="bfef9-128">Pēc savas izveidošanas tās nemainās.</span><span class="sxs-lookup"><span data-stu-id="bfef9-128">They don't change once created.</span></span>
> - <span data-ttu-id="bfef9-129">Pašlaik segmenti un mēri netiks atjaunināti, pamatojoties uz jaunām darbībām.</span><span class="sxs-lookup"><span data-stu-id="bfef9-129">Currently, segments and measures won't update based on the new activity.</span></span>
> - <span data-ttu-id="bfef9-130">Darbības, kas pievienotas vienīgi ar reāllaika API, nav daļa no eksporta un netiks rādītas PowerBI.</span><span class="sxs-lookup"><span data-stu-id="bfef9-130">Activities added only through the real-time API are not part of exports and won't show up in PowerBI.</span></span>

<span data-ttu-id="bfef9-131">Ir divi paņēmieni, kā izveidot savienojumu ar reāllaika API.</span><span class="sxs-lookup"><span data-stu-id="bfef9-131">There are two ways to connect to the real-time API:</span></span>

- <span data-ttu-id="bfef9-132">[netieši](#connect-via-the-dynamics-365-customer-insights-connector), izmantojot [Dynamics 365 Customer Insights savienotāju](https://docs.microsoft.com/connectors/customerinsights/)</span><span class="sxs-lookup"><span data-stu-id="bfef9-132">[indirectly](#connect-via-the-dynamics-365-customer-insights-connector), using the [Dynamics 365 Customer Insights connector](https://docs.microsoft.com/connectors/customerinsights/)</span></span>
- <span data-ttu-id="bfef9-133">[tieši](#connect-directly-to-the-real-time-api), ar kodu</span><span class="sxs-lookup"><span data-stu-id="bfef9-133">[directly](#connect-directly-to-the-real-time-api), with code</span></span>

<span data-ttu-id="bfef9-134">Abiem veidiem ir šādi priekšnosacījumi:</span><span class="sxs-lookup"><span data-stu-id="bfef9-134">Both ways share the following prerequisites:</span></span>

- <span data-ttu-id="bfef9-135">Customer Insights vide</span><span class="sxs-lookup"><span data-stu-id="bfef9-135">A Customer Insights environment</span></span>
- <span data-ttu-id="bfef9-136">Vienoti klientu profili</span><span class="sxs-lookup"><span data-stu-id="bfef9-136">Unified customer profiles</span></span>
- <span data-ttu-id="bfef9-137">Konfigurētās un palaistās darbības</span><span class="sxs-lookup"><span data-stu-id="bfef9-137">Activities configured and run</span></span>
- <span data-ttu-id="bfef9-138">Līdzstrādnieka vai administratora atļauja jūsu uzņēmuma autentificēšanai</span><span class="sxs-lookup"><span data-stu-id="bfef9-138">Contributor or Administrator permissions to authenticate your account</span></span>

## <a name="connect-via-the-dynamics-365-customer-insights-connector"></a><span data-ttu-id="bfef9-139">Pieslēdzieties, izmantojot Dynamics 365 Customer Insights savienotāju</span><span class="sxs-lookup"><span data-stu-id="bfef9-139">Connect via the Dynamics 365 Customer Insights connector</span></span>

<span data-ttu-id="bfef9-140">Reāllaika API var uzņemt datus no īpaša Power Platform savienotāja, [Dynamics 365 Customer Insights savienotāja ](https://docs.microsoft.com/connectors/customerinsights/) bez vajadzības rakstīt un izvietot kodu.</span><span class="sxs-lookup"><span data-stu-id="bfef9-140">The real-time API can ingest data from a dedicated Power Platform connector, the [Dynamics 365 Customer Insights connector](https://docs.microsoft.com/connectors/customerinsights/), without the need to write and deploy any code.</span></span>    
<span data-ttu-id="bfef9-141">Savienotājs var veikt tādas pašas reāllaika darbības kā API.</span><span class="sxs-lookup"><span data-stu-id="bfef9-141">The connector can do the same real-time actions as the API.</span></span> <span data-ttu-id="bfef9-142">Premium savienotājiem ir nepieciešama derīga licence.</span><span class="sxs-lookup"><span data-stu-id="bfef9-142">You need a valid license for premium connectors.</span></span> <span data-ttu-id="bfef9-143">Papildinformāciju skatiet sadaļā [Power Apps un Power Automate licencēšanas BUJ](https://docs.microsoft.com/power-platform/admin/powerapps-flow-licensing-faq).</span><span class="sxs-lookup"><span data-stu-id="bfef9-143">For more information, see [Power Apps and Power Automate licensing FAQs](https://docs.microsoft.com/power-platform/admin/powerapps-flow-licensing-faq).</span></span>

- <span data-ttu-id="bfef9-144">Power Platform [Power Apps un/vai Power Automate](https://docs.microsoft.com/connectors/)</span><span class="sxs-lookup"><span data-stu-id="bfef9-144">Power Platform [Power Apps and/or Power Automate](https://docs.microsoft.com/connectors/)</span></span>
- <span data-ttu-id="bfef9-145">Azure [Logic Apps](https://docs.microsoft.com/azure/connectors/apis-list)</span><span class="sxs-lookup"><span data-stu-id="bfef9-145">Azure [Logic Apps](https://docs.microsoft.com/azure/connectors/apis-list)</span></span>

<span data-ttu-id="bfef9-146">Papildinformāciju par plūsmu izveidi skatiet [Power Automate dokumentācijā](https://docs.microsoft.com/power-automate/).</span><span class="sxs-lookup"><span data-stu-id="bfef9-146">For details about creating flows, see the [Power Automate documentation](https://docs.microsoft.com/power-automate/).</span></span>

## <a name="connect-directly-to-the-real-time-api"></a><span data-ttu-id="bfef9-147">Tieša savienojuma izveide ar reāllaika API</span><span class="sxs-lookup"><span data-stu-id="bfef9-147">Connect directly to the real-time API</span></span>

<span data-ttu-id="bfef9-148">Varat izmantot reāllaika iespējas, veidojot savu konveijeru un izveidojot savienojumu tieši ar reāllaika API.</span><span class="sxs-lookup"><span data-stu-id="bfef9-148">You can use the real-time capabilities by building your own pipeline and connecting directly to the real-time API.</span></span>    
<span data-ttu-id="bfef9-149">Darbību varat publicēt savas avotsistēmas formātā vai UnifiedActivity formātā.</span><span class="sxs-lookup"><span data-stu-id="bfef9-149">You can post an activity in the format of your source system or in the UnifiedActivity format.</span></span> <span data-ttu-id="bfef9-150">Iegūstiet formātu, veicot API izsaukumu uz /api/instances/{instanceId}/manage/entities/UnifiedActivity.</span><span class="sxs-lookup"><span data-stu-id="bfef9-150">Get the format by making an API call to /api/instances/{instanceId}/manage/entities/UnifiedActivity.</span></span>

<span data-ttu-id="bfef9-151">Detalizēta informācija par šo API, ieskaitot parametrus un atbildes, ir atrodama **EntityData** sadaļā [Customer Insights API atsauce](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span><span class="sxs-lookup"><span data-stu-id="bfef9-151">Details of this API, including parameters and responses, can be found in the **EntityData** section on the [Customer Insights APIs reference](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span></span> <span data-ttu-id="bfef9-152">Papildinformāciju skatiet tēmā [Darbs ar Customer Insights API](apis.md).</span><span class="sxs-lookup"><span data-stu-id="bfef9-152">For more information, see [Work with Customer Insights APIs](apis.md).</span></span>

## <a name="understand-your-real-time-usage-with-telemetry"></a><span data-ttu-id="bfef9-153">Reāllaika lietojuma izprašana, izmantojot telemetriju</span><span class="sxs-lookup"><span data-stu-id="bfef9-153">Understand your real-time usage with telemetry</span></span>

<span data-ttu-id="bfef9-154">Iegūstiet pārskatu par reāllaika API pieprasījumu apjomu un informāciju par problēmām, kas sistēmai var rasties.</span><span class="sxs-lookup"><span data-stu-id="bfef9-154">Get an overview of the volume of requests to the real-time API and information about issues the system may encounter.</span></span> <span data-ttu-id="bfef9-155">Varat piekļūt [reāllaika telemetrijai](system.md#api-usage-tab).</span><span class="sxs-lookup"><span data-stu-id="bfef9-155">You can [access the real-time telemetry](system.md#api-usage-tab).</span></span> 


[!INCLUDE[footer-include](../includes/footer-banner.md)]