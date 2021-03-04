---
title: Tīmekļa datu integrēšana no iesaistes ieskatiem ar auditorijas ieskatiem
description: Tīmekļa informāciju par klientiem varat pārnest no iesaistes ieskatiem uz auditorijas ieskatiem.
ms.date: 12/17/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mukeshpo
manager: shellyha
ms.openlocfilehash: ba1cf6c7e85b8fe90baf34018f1309095573adf1
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267685"
---
# <a name="integrate-web-data-from-engagement-insights-with-audience-insights"></a><span data-ttu-id="168c9-103">Tīmekļa datu integrēšana no iesaistes ieskatiem ar auditorijas ieskatiem</span><span class="sxs-lookup"><span data-stu-id="168c9-103">Integrate web data from engagement insights with audience insights</span></span>

<span data-ttu-id="168c9-104">Klienti bieži vien veic ikdienas darījumus tiešsaistē, izmantojot interneta vietnes.</span><span class="sxs-lookup"><span data-stu-id="168c9-104">Customers often do their day to day transactions online using web sites.</span></span> <span data-ttu-id="168c9-105">Iesaistes ieskatu iespēja programmā Dynamics 365 Customer Insights ir parocīgs risinājums, kas ļauj tīmekļa datus integrēt kā avotu.</span><span class="sxs-lookup"><span data-stu-id="168c9-105">The engagement insights capability in Dynamics 365 Customer Insights is a handy solution to integrate web data as a source.</span></span> <span data-ttu-id="168c9-106">Papildus transakciju, demogrāfiskajiem vai uzvedības datiem mēs tīmeklī redzam darbības vienotos klientu profilos.</span><span class="sxs-lookup"><span data-stu-id="168c9-106">In addition to transactional, demographic, or behavioral data we can see activities on the web in unified customer profiles.</span></span> <span data-ttu-id="168c9-107">Mēs varam izmantot šo profilu, lai auditorijas aktivizēšanai gūtu papildu ieskatus, piemēram, segmentus, pasākumus vai prognozes.</span><span class="sxs-lookup"><span data-stu-id="168c9-107">We can use this profile to gain additional insights like segments, measures, or predictions for audience activation.</span></span>

<span data-ttu-id="168c9-108">Šajā rakstā ir aprakstītas darbības, kas jāveic, lai klientu tīmekļa darbību datus no iesaistes ieskatiem pārvērstu esošajā auditorijas ieskatu vidē.</span><span class="sxs-lookup"><span data-stu-id="168c9-108">This article describes the steps to bring your customers’ web activity data from engagement insights into your existing audience insights environment.</span></span>

<span data-ttu-id="168c9-109">Šajā piemērā mēs uzņemam vidi, kurā ir vienoti klientu profili.</span><span class="sxs-lookup"><span data-stu-id="168c9-109">In this example, we assume an environment that contains unified customer profiles.</span></span> <span data-ttu-id="168c9-110">Profili tika vienoti ar aptauju, mazumtirdzniecības un biļešu iegādes sistēmas avotiem.</span><span class="sxs-lookup"><span data-stu-id="168c9-110">The profiles were unified with sources from surveys, retail sales, and a ticketing system.</span></span> <span data-ttu-id="168c9-111">Tiek parādītas arī klientu saistītās darbības.</span><span class="sxs-lookup"><span data-stu-id="168c9-111">It also shows the related activities of the customers.</span></span> 

<span data-ttu-id="168c9-112">Tagad mēs vēlamies zināt, vai klients apmeklē mūsu tīmekļa rekvizītus un izprot savas darbības.</span><span class="sxs-lookup"><span data-stu-id="168c9-112">We now want to know if a customer visits our web properties and understand their activities.</span></span> <span data-ttu-id="168c9-113">Darbības ietver, piemēram, apmeklētas vietnes vai produktu lapu skatīšanu no e-pastā saņemtās saites.</span><span class="sxs-lookup"><span data-stu-id="168c9-113">Activities include, for example, visited websites or viewed product pages from a link received in an email.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="168c9-114">Priekšnosacījumi</span><span class="sxs-lookup"><span data-stu-id="168c9-114">Prerequisites</span></span>

<span data-ttu-id="168c9-115">Lai integrētu datus no iesaistes ieskatiem, ir jāizpilda daži priekšnosacījumi:</span><span class="sxs-lookup"><span data-stu-id="168c9-115">To integrate data from engagement insights, a few prerequisites need to be met:</span></span> 

- <span data-ttu-id="168c9-116">Integrējiet iesaistes ieskatu SDK savā vietnē.</span><span class="sxs-lookup"><span data-stu-id="168c9-116">Integrate the engagement insights SDK with your website.</span></span> <span data-ttu-id="168c9-117">Papildinformāciju skatiet rakstā [Darba sākšana ar tīmekļa SDK](../engagement-insights/instrument-website.md).</span><span class="sxs-lookup"><span data-stu-id="168c9-117">For more information, see [Get started with the web SDK](../engagement-insights/instrument-website.md).</span></span>
- <span data-ttu-id="168c9-118">Tīmekļa notikumu eksportēšanai no iesaistes ieskatiem ir nepieciešama piekļuve ADLS Gen 2 krātuves kontam, kas tiks izmantots, lai tīmekļa notikumu datus ievadītu auditorijas ieskatos.</span><span class="sxs-lookup"><span data-stu-id="168c9-118">Exporting web events from engagement insights requires access to an ADLS Gen 2 storage account that will be used to ingest the web events data to audience insights.</span></span> <span data-ttu-id="168c9-119">Papildinformāciju skatiet [Eksportēt notikumus](../engagement-insights/export-events.md).</span><span class="sxs-lookup"><span data-stu-id="168c9-119">For more information, see [Export events](../engagement-insights/export-events.md).</span></span>

## <a name="configure-refined-events-in-engagement-insights"></a><span data-ttu-id="168c9-120">Konfigurēt precizētos notikumus iesaistes ieskatos</span><span class="sxs-lookup"><span data-stu-id="168c9-120">Configure refined events in engagement insights</span></span>

<span data-ttu-id="168c9-121">Pēc tam, kad administrators ir izveidojis vietni ar iesaistes ieskatu SDK, tiek apkopoti *pamatnotikumi*, kad lietotājs skata tīmekļa lapu vai kaut kur noklikšķina.</span><span class="sxs-lookup"><span data-stu-id="168c9-121">After an administrator instrumented a website with the engagement insights SDK, *base events* are gathered when a user views a web page or clicks somewhere.</span></span> <span data-ttu-id="168c9-122">Pamatnotikumos parasti ir ietverta detalizēta informācija.</span><span class="sxs-lookup"><span data-stu-id="168c9-122">Base events tend to contain numerous details.</span></span> <span data-ttu-id="168c9-123">Atkarībā no izmantošanas gadījuma datu apakšgrupa ir nepieciešama tikai pamatnotikumā.</span><span class="sxs-lookup"><span data-stu-id="168c9-123">Depending on your use case, you only need a subset of the data in a base event.</span></span> <span data-ttu-id="168c9-124">Iesaistes ieskati jums ļauj izveidot *precizētus notikumus*, kuros ir tikai atlasītie pamatnotikuma rekvizīti.</span><span class="sxs-lookup"><span data-stu-id="168c9-124">Engagement insights let you create *refined events* that contain only the properties of a base event that you select.</span></span>     

<span data-ttu-id="168c9-125">Papildinformācijai skatiet [Precizēto notikumu izveide un modificēšana](../engagement-insights/refined-events.md).</span><span class="sxs-lookup"><span data-stu-id="168c9-125">For more information, see [Create and modify refined events](../engagement-insights/refined-events.md).</span></span>

<span data-ttu-id="168c9-126">Apsvērumi, kas rodas, izveidojot precizētos notikumus:</span><span class="sxs-lookup"><span data-stu-id="168c9-126">Considerations when creating refined events:</span></span> 

- <span data-ttu-id="168c9-127">Norādiet jēgpilnu precizētā notikuma nosaukumu.</span><span class="sxs-lookup"><span data-stu-id="168c9-127">Provide a meaningful name for the refined event.</span></span> <span data-ttu-id="168c9-128">Tas tiek izmantots kā darbības nosaukums auditorijas ieskatos.</span><span class="sxs-lookup"><span data-stu-id="168c9-128">It's be used as an activity name in audience insights.</span></span>
- <span data-ttu-id="168c9-129">Atlasiet vismaz sekojošos rekvizītus, lai izveidotu darbību auditorijas ieskatos:</span><span class="sxs-lookup"><span data-stu-id="168c9-129">Select at least the following properties to create an activity in audience insights:</span></span> 
    - <span data-ttu-id="168c9-130">Signal.Action.Name - darbības informācijas norādīšana</span><span class="sxs-lookup"><span data-stu-id="168c9-130">Signal.Action.Name - indicating the activity details</span></span>
    - <span data-ttu-id="168c9-131">Signal.User.Id - lieto, lai kartētu ar klienta ID</span><span class="sxs-lookup"><span data-stu-id="168c9-131">Signal.User.Id - used to map with the customer ID</span></span>
    - <span data-ttu-id="168c9-132">Signal.View.Uri - izmanto kā tīmekļa adresi segmentu vai pasākumu pamatam</span><span class="sxs-lookup"><span data-stu-id="168c9-132">Signal.View.Uri - used as a web address as a basis for segments or measures</span></span>
    - <span data-ttu-id="168c9-133">Signal.Export.Id - lai izmantotu kā primāro atslēgu notikumiem</span><span class="sxs-lookup"><span data-stu-id="168c9-133">Signal.Export.Id - to use as a primary key for events</span></span> <!-- system generated, do we need to list?-->
    - <span data-ttu-id="168c9-134">Signal.Timestamp - lai noteiktu darbības datumu un laiku</span><span class="sxs-lookup"><span data-stu-id="168c9-134">Signal.Timestamp - to determine the date and time for the activity</span></span>

<span data-ttu-id="168c9-135">Atlasiet filtrus, lai koncentrētos uz notikumiem un lapām, kas ir svarīgas jūsu gadījumam.</span><span class="sxs-lookup"><span data-stu-id="168c9-135">Select the filters to focus on the events and pages that matter for your use case.</span></span> <span data-ttu-id="168c9-136">Šajā piemērā tiks izmantots darbības nosaukums "E-pasta veicināšanas pasākums".</span><span class="sxs-lookup"><span data-stu-id="168c9-136">In this example, we'll use the "Email promotion" action name.</span></span>

## <a name="export-the-refined-web-events"></a><span data-ttu-id="168c9-137">Eksportējiet precizētos tīmekļa notikumus</span><span class="sxs-lookup"><span data-stu-id="168c9-137">Export the Refined Web Events</span></span> 

<span data-ttu-id="168c9-138">Pēc precizētā notikuma definēšanas ir jākonfigurē notikuma datu eksportēšana uz Azure Data Lake Storage, ko var iestatīt kā datu avota iekļaušanu auditorijas ieskatos.</span><span class="sxs-lookup"><span data-stu-id="168c9-138">After defining the refined event is defined, you have to configure the export of the event data to an Azure Data Lake Storage, that can be set as a data source for ingestion in audience insights.</span></span> <span data-ttu-id="168c9-139">Eksportēšana notiek pastāvīgi kā notikumu plūsma no tīmekļa rekvizīta.</span><span class="sxs-lookup"><span data-stu-id="168c9-139">Exports happen constantly as the events flow from the web property.</span></span>

<span data-ttu-id="168c9-140">Papildinformāciju skatiet [Eksportēt notikumus](../engagement-insights/export-events.md).</span><span class="sxs-lookup"><span data-stu-id="168c9-140">For more information, see [Export events](../engagement-insights/export-events.md).</span></span>

## <a name="ingest-event-data-to-audience-insights"></a><span data-ttu-id="168c9-141">Notikuma datu iesniegšana auditorijas ieskatos</span><span class="sxs-lookup"><span data-stu-id="168c9-141">Ingest event data to audience insights</span></span>

<span data-ttu-id="168c9-142">Tagad, kad esat definējis precizēto notikumu un konfigurējis tā eksportēšanu, mēs pārejam uz datu iesniegšanu auditorijas ieskatos.</span><span class="sxs-lookup"><span data-stu-id="168c9-142">Now that you have defined the refined event and configured its export, we move on to ingesting the data to audience insights.</span></span> <span data-ttu-id="168c9-143">Jums ir jāizveido jauns datu datu avots, pamatojoties uz Common Data Model mapi.</span><span class="sxs-lookup"><span data-stu-id="168c9-143">You need to create a new data source based on a Common Data Model folder.</span></span> <span data-ttu-id="168c9-144">Ievadiet detalizētu informāciju par to krātuves kontu, uz kuru eksportējat notikumus.</span><span class="sxs-lookup"><span data-stu-id="168c9-144">Enter the details for the storage account you export the events to.</span></span> <span data-ttu-id="168c9-145">Failā *default.cdm.json* atlasiet iesniedzamo, precizēto notikumu un izveidojiet entītiju auditorijas ieskatos.</span><span class="sxs-lookup"><span data-stu-id="168c9-145">In the *default.cdm.json* file, select the refined event to ingest and create the entity in audience insights.</span></span>

<span data-ttu-id="168c9-146">Papildinformāciju skatiet sadaļā [Savienojuma izveide ar Common Data Model mapi, izmantojot Azure Data Lake kontu](connect-common-data-model.md)</span><span class="sxs-lookup"><span data-stu-id="168c9-146">For more information, see [Connect to a Common Data Model folder using an Azure Data Lake account](connect-common-data-model.md)</span></span>


## <a name="relate-refined-event-data-as-an-activity-of-a-customer-profile"></a><span data-ttu-id="168c9-147">Saistiet precizētā notikuma datus kā klienta profila darbību</span><span class="sxs-lookup"><span data-stu-id="168c9-147">Relate refined event data as an activity of a customer profile</span></span>

<span data-ttu-id="168c9-148">Kad entītija ir pabeigta, varat konfigurēt klienta profila darbību.</span><span class="sxs-lookup"><span data-stu-id="168c9-148">After completing the entity ingestion, you can configure the activity for the customer profile.</span></span>

<span data-ttu-id="168c9-149">Papildinformācijai skatiet [Klientu darbības](activities.md).</span><span class="sxs-lookup"><span data-stu-id="168c9-149">For more information, see [Customer activities](activities.md).</span></span>

:::image type="content" source="media/web-event-activity.png" alt-text="Darbību lapa ar izvērstu darbību rediģēšanas rūti un aizpildītiem laukiem.":::

<span data-ttu-id="168c9-151">Konfigurējiet jauno darbību, izmantojot šādu kartējumu:</span><span class="sxs-lookup"><span data-stu-id="168c9-151">Configure the new activity with the following mapping:</span></span> 

- <span data-ttu-id="168c9-152">**Primārā atslēga:** Signal.Export.Id - unikāls ID, kas ir pieejams katram notikuma ierakstam iesaistes ieskatos.</span><span class="sxs-lookup"><span data-stu-id="168c9-152">**Primary Key:** Signal.Export.Id, a unique ID that is available for every event record in engagement insights.</span></span> <span data-ttu-id="168c9-153">Šis rekvizīts tiek ģenerēts automātiski.</span><span class="sxs-lookup"><span data-stu-id="168c9-153">This property is automatically generated.</span></span>

- <span data-ttu-id="168c9-154">**Laikspiedols:** Signal.Timestamp notikuma rekvizītā.</span><span class="sxs-lookup"><span data-stu-id="168c9-154">**Timestamp:** Signal.Timestamp in the event property.</span></span>

- <span data-ttu-id="168c9-155">**Notikums:** Signal.Name - notikuma nosaukums, kuru vēlaties izsekot.</span><span class="sxs-lookup"><span data-stu-id="168c9-155">**Event:** Signal.Name, the event name that you want to track.</span></span>

- <span data-ttu-id="168c9-156">**Tīmekļa adrese:** Signal.View.Uri norāda uz notikumu izveidojušās lapas uri.</span><span class="sxs-lookup"><span data-stu-id="168c9-156">**Web address:** Signal.View.Uri referring to the uri of the page that created the event.</span></span>

- <span data-ttu-id="168c9-157">**Detalizēta informācija:** Signal.Action.Name attēlo informāciju, kas jāsaista ar notikumu.</span><span class="sxs-lookup"><span data-stu-id="168c9-157">**Details:** Signal.Action.Name to represent the information to associate with the event.</span></span> <span data-ttu-id="168c9-158">Šajā gadījumā atlasītais rekvizīts norāda, ka notikums ir e-pasta veicināšanas pasākums.</span><span class="sxs-lookup"><span data-stu-id="168c9-158">The selected property in this case indicates that the event is for email promotion.</span></span>

- <span data-ttu-id="168c9-159">**Darbības tips:** šajā piemērā mēs izvēlamies esošo darbības tipu Tīmekļa žurnāls.</span><span class="sxs-lookup"><span data-stu-id="168c9-159">**Activity type:** In this example, we choose the exsting activity type WebLog.</span></span> <span data-ttu-id="168c9-160">Šī atlase ir noderīga filtrēšanas opcija, lai izpildītu prognozes modeļus vai izveidotu segmentus, pamatojoties uz šo darbības tipu.</span><span class="sxs-lookup"><span data-stu-id="168c9-160">This selection is a useful filter option to run prediction models or create segments based on this activity type.</span></span>

- <span data-ttu-id="168c9-161">**Iestatīt attiecības:** šis svarīgais iestatījums ir saistīts ar esošiem klientu profiliem.</span><span class="sxs-lookup"><span data-stu-id="168c9-161">**Set up relationship:** This important setting ties the activity to existing customer profiles.</span></span> <span data-ttu-id="168c9-162">**Signal.User.Id** ir identifikators, kas tiek konfigurēts SDK apkopošanai un ir saistīts ar lietotāja ID citos datu avotos, kuri ir konfigurēti auditorijas ieskatos.</span><span class="sxs-lookup"><span data-stu-id="168c9-162">**Signal.User.Id** is the identifier configured in the SDK to be collected and that relates to the user ID in other data sources that are configured in audience insights.</span></span> <span data-ttu-id="168c9-163">Šajā piemērā mēs konfigurējam attiecības starp Signal.User.Id un RetailCustomers:CustomerRetailId, kas ir primārā atslēga, kura tika noņemta datu apvienošanas procesa kartējuma solī.</span><span class="sxs-lookup"><span data-stu-id="168c9-163">In this example, we configure the relationship between Signal.User.Id and RetailCustomers:CustomerRetailId, which is the primary key that was deinfed in the map step of the data unification process.</span></span>


<span data-ttu-id="168c9-164">Pēc darbību apstrādes varat pārskatīt klientu ierakstus un atvērt klienta karti, lai skatītu darbības no iesaistes ieskatiem laika skalā.</span><span class="sxs-lookup"><span data-stu-id="168c9-164">After processing the activities, you can review customer records and open a customer card to see activities from engagement insights in the timeline.</span></span> 

> [!TIP]
> <span data-ttu-id="168c9-165">Lai atrastu klienta ID, kam ir iesaistes ieskatu darbība, dodieties uz **Entītijas** un priekšskatiet UnifiedActivity entītijas datus.</span><span class="sxs-lookup"><span data-stu-id="168c9-165">To find a customer id that has an engagement insights activity, go to **Entities** and preview the data for the UnifiedActivity entity.</span></span> <span data-ttu-id="168c9-166">ActivityTypeDisplay = Tīmekļa žurnāls ietver iesaistes ieskatu darbību, kas ir konfigurēta iepriekš minētajā piemērā.</span><span class="sxs-lookup"><span data-stu-id="168c9-166">ActivityTypeDisplay = WebLog contain the engagement insights activity configured in the example above.</span></span> <span data-ttu-id="168c9-167">Nokopējiet klienta ID vienam no šiem ierakstiem un šim ID lapā **Klienti**.</span><span class="sxs-lookup"><span data-stu-id="168c9-167">Copy the customer ID for one of those records and for that ID on the **Customers** page.</span></span>

## <a name="next-steps"></a><span data-ttu-id="168c9-168">Nākamās darbības</span><span class="sxs-lookup"><span data-stu-id="168c9-168">Next Steps</span></span>

<span data-ttu-id="168c9-169">Tagad varat izveidot [segmentus](segments.md), [pasākumus](measures.md) un [prognozes](predictions.md), lai izveidotu jēgpilnu savienojumu ar klientiem.</span><span class="sxs-lookup"><span data-stu-id="168c9-169">You can now create [segments](segments.md), [measures](measures.md), and [predictions](predictions.md) to make a meaningful connection with your customers.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]