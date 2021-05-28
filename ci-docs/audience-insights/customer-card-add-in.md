---
title: Dynamics 365 Apps klienta kartes pievienojumprogramma
description: Rādīt auditorijas ieskatu datus Dynamics 365 programmās, izmantojot šo pievienojumprogrammu.
ms.date: 05/18/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 88492943ddbf9ae30c64d92b261433b74f34f682
ms.sourcegitcommit: d74430270f1b754322287c4f045d7febdae35be2
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 05/18/2021
ms.locfileid: "6059597"
---
# <a name="customer-card-add-in-preview"></a><span data-ttu-id="8cc5f-103">Klienta kartes pievienojumprogramma (priekšskatījums)</span><span class="sxs-lookup"><span data-stu-id="8cc5f-103">Customer Card Add-in (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="8cc5f-104">Iegūstiet pilnu ainu par saviem klientiem tieši risinājuma Dynamics 365 programmās.</span><span class="sxs-lookup"><span data-stu-id="8cc5f-104">Get a 360-degree view of your customers directly in Dynamics 365 apps.</span></span> <span data-ttu-id="8cc5f-105">Kad klienta kartes pievienojumprogramma ir instalēta atbalstītajā Dynamics 365 programmā, varat izvēlēties rādīt demogrāfiskos datus, ieskatus un darbību laika grafikus.</span><span class="sxs-lookup"><span data-stu-id="8cc5f-105">With the Customer Card Add-in installed in a supported Dynamics 365 app you can choose to display demographics, insights, and activity timelines.</span></span> <span data-ttu-id="8cc5f-106">Pievienojumprogramma izgūs datus no programmas Customer Insights, neietekmējot pievienotās Dynamics 365 programmas datus.</span><span class="sxs-lookup"><span data-stu-id="8cc5f-106">The add-in will retrieve data from Customer Insights without affecting the data in the connected Dynamics 365 app.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="8cc5f-107">Priekšnosacījumi</span><span class="sxs-lookup"><span data-stu-id="8cc5f-107">Prerequisites</span></span>

- <span data-ttu-id="8cc5f-108">Pievienojumprogramma darbojas tikai ar Dynamics 365 modeļa vadītām programmām, piemēram, Sales vai Customer Service versiju 9.0 un jaunāku versiju.</span><span class="sxs-lookup"><span data-stu-id="8cc5f-108">The add-in only works with Dynamics 365 model-driven apps, such as Sales or Customer Service, version 9.0 and later.</span></span>
- <span data-ttu-id="8cc5f-109">Lai kartētu Dynamics 365 datus uz auditorijas ieskatu klientu profiliem, kas nepieciešami, lai tos varētu lietot [Dynamics 365 programmā, izmantojot Common Data Service savienotāju](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="8cc5f-109">For your Dynamics 365 data to map to the audience insights customer profiles they need to be [ingested from the Dynamics 365 app using the Common Data Service connector](connect-power-query.md).</span></span>
- <span data-ttu-id="8cc5f-110">Visi Dynamics 365 lietotāji, kas izmanto klienta kartes pievienojumprogrammu, ir [jāpievieno kā lietotāji](permissions.md) auditorijas ieskatos, lai redzētu datus.</span><span class="sxs-lookup"><span data-stu-id="8cc5f-110">All Dynamics 365 users of the Customer Card Add-in must be [added as users](permissions.md) in audience insights to see the data.</span></span>
- <span data-ttu-id="8cc5f-111">Lai darbotos datu uzmeklēšana, ir nepieciešama [konfigurēta meklēšanas un filtrēšanas iespēja](search-filter-index.md) auditorijas ieskatos.</span><span class="sxs-lookup"><span data-stu-id="8cc5f-111">[Configured search and filter capabilities](search-filter-index.md) in audience insights are required for lookup of data to work.</span></span>
- <span data-ttu-id="8cc5f-112">Katra pievienojumprogrammas vadīkla ir atkarīga no noteiktiem datiem auditorijas ieskatos:</span><span class="sxs-lookup"><span data-stu-id="8cc5f-112">Each add-in control relies on specific data in audience insights:</span></span>
  - <span data-ttu-id="8cc5f-113">Mērīt vadīklu: Nepieciešamas [konfigurētās mērvienības](measures.md).</span><span class="sxs-lookup"><span data-stu-id="8cc5f-113">Measure control: Requires [configured measures](measures.md).</span></span>
  - <span data-ttu-id="8cc5f-114">Informācijas vadīkla: nepieciešami dati, kas ģenerēti, lietojot [prognozes](predictions.md) vai [pielāgotus modeļus](custom-models.md).</span><span class="sxs-lookup"><span data-stu-id="8cc5f-114">Intelligence control: Requires data generated using [predictions](predictions.md) or [custom models](custom-models.md).</span></span>
  - <span data-ttu-id="8cc5f-115">Demogrāfiskā kontrole: demogrāfiskie lauki (piemēram, vecums vai dzimums) ir pieejami vienotajā klienta profilā.</span><span class="sxs-lookup"><span data-stu-id="8cc5f-115">Demographic control: Demographic fields(such as age or gender) are available in the unified customer profile.</span></span>
  - <span data-ttu-id="8cc5f-116">Bagātināšanas vadīkla: Ir nepieciešama aktīva [bagātināšana](enrichment-hub.md), ko piemērot klientu profiliem.</span><span class="sxs-lookup"><span data-stu-id="8cc5f-116">Enrichment control: Requires active [enrichments](enrichment-hub.md) applied to customer profiles.</span></span>
  - <span data-ttu-id="8cc5f-117">Laika skalas vadīkla: Nepieciešamas [konfigurētās darbības](activities.md).</span><span class="sxs-lookup"><span data-stu-id="8cc5f-117">Timeline control: Requires [configured activities](activities.md).</span></span>

## <a name="install-the-customer-card-add-in"></a><span data-ttu-id="8cc5f-118">Klienta kartes pievienojumprogrammas instalēšana</span><span class="sxs-lookup"><span data-stu-id="8cc5f-118">Install the Customer Card Add-in</span></span>

<span data-ttu-id="8cc5f-119">Klienta kartes pievienojumprogramma ir risinājums klientu iesaistes programmām pakalpojumā Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="8cc5f-119">The Customer Card Add-in is a solution for customer engagement apps in Dynamics 365.</span></span> <span data-ttu-id="8cc5f-120">Lai instalētu šo risinājumu, dodieties uz AppSource un meklējiet **Dynamics Customer Card**.</span><span class="sxs-lookup"><span data-stu-id="8cc5f-120">To install the solution, go to AppSource and search for **Dynamics Customer Card**.</span></span> <span data-ttu-id="8cc5f-121">Atlasiet [Klienta kartes pievienojumprogramma pakalpojumā AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) un atlasiet **Iegūt to tūlīt**.</span><span class="sxs-lookup"><span data-stu-id="8cc5f-121">Select the [Customer Card Add-in on AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) and select **Get It Now**.</span></span>

<span data-ttu-id="8cc5f-122">Lai Dynamics 365 programma instalētu risinājumu, jums, iespējams, vajadzēs pieteikties ar saviem administratora akreditācijas datiem.</span><span class="sxs-lookup"><span data-stu-id="8cc5f-122">You may need to sign in with your admin credentials for the Dynamics 365 app to install the solution.</span></span>

<span data-ttu-id="8cc5f-123">Var paiet zināms laiks, līdz risinājums tiks instalēts jūsu vidē.</span><span class="sxs-lookup"><span data-stu-id="8cc5f-123">It can take some time for the solution to be installed to your environment.</span></span>

## <a name="configure-the-customer-card-add-in"></a><span data-ttu-id="8cc5f-124">Klienta kartes pievienojumprogrammas konfigurēšana</span><span class="sxs-lookup"><span data-stu-id="8cc5f-124">Configure the Customer Card Add-in</span></span>

1. <span data-ttu-id="8cc5f-125">Kā administrators atveriet sadaļu **Iestatījumi** pakalpojumā Dynamics 365 un atlasiet **Risinājumi**.</span><span class="sxs-lookup"><span data-stu-id="8cc5f-125">As an admin, go to the **Settings** section in Dynamics 365 and select **Solutions**.</span></span>

1. <span data-ttu-id="8cc5f-126">Atlasiet saiti **Parādāmais nosaukums** risinājumam **Dynamics 365 Customer Insights klienta kartes pievienojumprogramma (priekšskatījums)**.</span><span class="sxs-lookup"><span data-stu-id="8cc5f-126">Select the **Display Name** link for the **Dynamics 365 Customer Insights Customer Card Add-in (Preview)** solution.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="8cc5f-127">![Parādāmā nosaukuma atlasīšana](media/select-display-name.png "Parādāmā nosaukuma atlasīšana")</span><span class="sxs-lookup"><span data-stu-id="8cc5f-127">![Select display name](media/select-display-name.png "Select display name")</span></span>

1. <span data-ttu-id="8cc5f-128">Atlasiet **Pierakstīties** un ievadiet tā administratora konta akreditācijas datus, ko izmantojat, lai konfigurētu Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="8cc5f-128">Select **Sign in** and enter the credentials for the admin account you use to configure Customer Insights.</span></span>

   > [!NOTE]
   > <span data-ttu-id="8cc5f-129">Pārbaudiet, vai, atlasot pogu **Pierakstīties**, pārlūkprogrammas uznirstošo elementu bloķētājs nebloķē autentifikācijas logu.</span><span class="sxs-lookup"><span data-stu-id="8cc5f-129">Check that the browser pop-up blocker does not block the authentication window when you select the **Sign in** button.</span></span>

1. <span data-ttu-id="8cc5f-130">Atlasiet Customer Insights vidi, no kuras vēlaties izgūt datus.</span><span class="sxs-lookup"><span data-stu-id="8cc5f-130">Select the Customer Insights environment you want to fetch data from.</span></span>

1. <span data-ttu-id="8cc5f-131">Definējiet lauku kartējumu ierakstiem Dynamics 365 programmā.</span><span class="sxs-lookup"><span data-stu-id="8cc5f-131">Define the field mapping to records in the Dynamics 365 app.</span></span> <span data-ttu-id="8cc5f-132">Atkarībā no datiem programmā Customer Insights varat izvēlēties kartēt šādas opcijas:</span><span class="sxs-lookup"><span data-stu-id="8cc5f-132">Depending on your data in Customer Insights you can choose to map the following options:</span></span>
   - <span data-ttu-id="8cc5f-133">Lai kartētu ar kontaktpersonu, atlasiet klientu entītijas lauku, kas atbilst jūsu kontaktpersonas entītijas ID.</span><span class="sxs-lookup"><span data-stu-id="8cc5f-133">To map with a contact, select the field in the Customer entity that matches the ID of your contact entity.</span></span>
   - <span data-ttu-id="8cc5f-134">Lai kartētu ar kontaktpersonu, atlasiet klientu entītijas lauku, kas atbilst jūsu konta entītijas ID.</span><span class="sxs-lookup"><span data-stu-id="8cc5f-134">To map with an account, select the field in the Customer entity that matches the ID of your account entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="8cc5f-135">![Lauks Kontaktpersonas ID](media/contact-id-field.png "Lauks Kontaktpersonas ID")</span><span class="sxs-lookup"><span data-stu-id="8cc5f-135">![Contact ID field](media/contact-id-field.png "Contact ID field")</span></span>

1. <span data-ttu-id="8cc5f-136">Atlasiet **Saglabāt konfigurāciju**, lai saglabātu iestatījumus.</span><span class="sxs-lookup"><span data-stu-id="8cc5f-136">Select **Save configuration** to save the settings.</span></span>

1. <span data-ttu-id="8cc5f-137">Pēc tam risinājumā Dynamics 365 ir jāpiešķir drošības lomas, lai lietotāji varētu pielāgot un apskatīt klienta karti.</span><span class="sxs-lookup"><span data-stu-id="8cc5f-137">Next, you need to assign security roles in Dynamics 365 so users can customize and see the customer card.</span></span> <span data-ttu-id="8cc5f-138">Programmā Dynamics 365 atveriet sadaļu **Iestatījumi** > **Drošība** > **Lietotāji**.</span><span class="sxs-lookup"><span data-stu-id="8cc5f-138">In Dynamics 365, go to **Settings** > **Security** > **Users**.</span></span> <span data-ttu-id="8cc5f-139">Atlasiet lietotājus, lai rediģētu lietotāju lomas, un atlasiet **Pārvaldīt lomas**.</span><span class="sxs-lookup"><span data-stu-id="8cc5f-139">Select the users to edit user roles and select **Manage roles**.</span></span>

1. <span data-ttu-id="8cc5f-140">Piešķiriet lomu **Customer Insights kartes pielāgotājs** lietotājiem, kuri visai organizācijai pielāgos kartē rādāmo saturu.</span><span class="sxs-lookup"><span data-stu-id="8cc5f-140">Assign the **Customer Insights Card Customizer** role to users who will customize the content shown on the card for the whole organization.</span></span>

## <a name="add-customer-card-controls-to-forms"></a><span data-ttu-id="8cc5f-141">Klienta karšu vadīklu pievienošana veidlapām</span><span class="sxs-lookup"><span data-stu-id="8cc5f-141">Add Customer Card controls to forms</span></span>
  
1. <span data-ttu-id="8cc5f-142">Lai savai kontaktpersonas veidlapai pievienotu klienta kartes vadīklas, dodieties uz **Iestatījumi** > **Pielāgojumi** risinājumā Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="8cc5f-142">To add the Customer Card controls to your Contact form, go to the **Settings** > **Customizations** in Dynamics 365.</span></span>

1. <span data-ttu-id="8cc5f-143">Atlasiet **Pielāgot sistēmu**.</span><span class="sxs-lookup"><span data-stu-id="8cc5f-143">Select **Customize the System**.</span></span>

1. <span data-ttu-id="8cc5f-144">Pārejiet uz entītiju **Kontaktpersona**, izvērsiet to un pēc tam atlasiet **Veidlapas**.</span><span class="sxs-lookup"><span data-stu-id="8cc5f-144">Browse to the **Contact** entity, expand it and select **Forms**.</span></span>

1. <span data-ttu-id="8cc5f-145">Atlasiet kontaktpersonas veidlapu, kurai vēlaties pievienot klienta kartes vadīklas.</span><span class="sxs-lookup"><span data-stu-id="8cc5f-145">Select the contact form to which you want to add the Customer Card controls.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="8cc5f-146">![Kontaktpersonas veidlapas atlase](media/contact-active-forms.png "Kontaktpersonas veidlapas atlase")</span><span class="sxs-lookup"><span data-stu-id="8cc5f-146">![Select Contact form](media/contact-active-forms.png "Select Contact form")</span></span>

1. <span data-ttu-id="8cc5f-147">Lai pievienotu vadīklu, veidlapu redaktorā velciet jebkuru lauku no **lauku pārlūka** uz vietu, kur vēlaties novietot vadīklu.</span><span class="sxs-lookup"><span data-stu-id="8cc5f-147">To add a control, in the form editor, drag any field from the **Field Explorer** to where you want the control to appear.</span></span>

1. <span data-ttu-id="8cc5f-148">Atlasiet tikko pievienoto lauku veidlapā un atlasiet **Mainīt rekvizītus**.</span><span class="sxs-lookup"><span data-stu-id="8cc5f-148">Select the field on the form that you just added, and select **Change Properties**.</span></span>

1. <span data-ttu-id="8cc5f-149">Dodieties uz cilni **Vadīklas** un atlasiet **Pievienot vadīklu**.</span><span class="sxs-lookup"><span data-stu-id="8cc5f-149">Go to the **Controls** tab and select **Add Control**.</span></span> <span data-ttu-id="8cc5f-150">Izvēlieties vienu no pieejamajām pielāgotajām vadīklām un atlasiet **Pievienot**.</span><span class="sxs-lookup"><span data-stu-id="8cc5f-150">Choose one of the available custom controls and select **Add**.</span></span>

1. <span data-ttu-id="8cc5f-151">Dialoglodziņā **Lauka rekvizīti** notīriet izvēles rūtiņu **Rādīt etiķeti veidlapā**.</span><span class="sxs-lookup"><span data-stu-id="8cc5f-151">In the **Field Properties** dialog, clear the **Display label on the form** check box.</span></span>

1. <span data-ttu-id="8cc5f-152">Vadīklai atlasiet opciju **Tīmeklis**.</span><span class="sxs-lookup"><span data-stu-id="8cc5f-152">Select the **Web** option for the control.</span></span> <span data-ttu-id="8cc5f-153">Bagātināšanas vadīklai atlasiet, kuru bagātināšanas veidu vēlaties rādīt, konfigurējot lauku **enrichmentType**.</span><span class="sxs-lookup"><span data-stu-id="8cc5f-153">For the Enrichment control, select which enrichment type you want to display by configuring the **enrichmentType** field.</span></span> <span data-ttu-id="8cc5f-154">Katram bagātināšanas tipam pievienojiet atsevišķu bagātināšanas vadīklu.</span><span class="sxs-lookup"><span data-stu-id="8cc5f-154">Add a separate enrichment control for each enrichment type.</span></span>

1. <span data-ttu-id="8cc5f-155">Atlasiet **Saglabāt** un **Publicēt**, lai publicētu atjaunināto kontaktpersonas veidlapu.</span><span class="sxs-lookup"><span data-stu-id="8cc5f-155">Select **Save** and **Publish** to publish the updated contact form.</span></span>

1. <span data-ttu-id="8cc5f-156">Atveriet publicēto kontaktpersonas veidlapu.</span><span class="sxs-lookup"><span data-stu-id="8cc5f-156">Go to the published contact form.</span></span> <span data-ttu-id="8cc5f-157">Tiek parādīta tikko pievienotā vadīkla.</span><span class="sxs-lookup"><span data-stu-id="8cc5f-157">You'll see the newly added control.</span></span> <span data-ttu-id="8cc5f-158">Iespējams, pirmajā lietošanas reizē būs jāpierakstās.</span><span class="sxs-lookup"><span data-stu-id="8cc5f-158">You might need to sign in the first time you use it.</span></span>

1. <span data-ttu-id="8cc5f-159">Lai pielāgotu pielāgotajā vadīklā rādāmo informāciju, augšējā labajā stūrī atlasiet rediģēšanas pogu.</span><span class="sxs-lookup"><span data-stu-id="8cc5f-159">To customize what you want to show on the custom control, select the edit button in the upper-right corner.</span></span>

## <a name="upgrade-customer-card-add-in"></a><span data-ttu-id="8cc5f-160">Klienta kartes pievienojumprogrammas jaunināšana</span><span class="sxs-lookup"><span data-stu-id="8cc5f-160">Upgrade Customer Card Add-in</span></span>
<span data-ttu-id="8cc5f-161">Klienta kartes pievienojumprogramma netiek automātiski jaunināta.</span><span class="sxs-lookup"><span data-stu-id="8cc5f-161">The Customer Card Add-in doesn't upgrade automatically.</span></span> <span data-ttu-id="8cc5f-162">Lai jauninātu uz jaunāko versiju, izpildiet šo procedūru programmā Dynamics 365, kurā ir instalēta pievienojumprogramma.</span><span class="sxs-lookup"><span data-stu-id="8cc5f-162">To upgrade to the latest version, follow this procedure in the Dynamics 365 app that has the Add-in installed.</span></span>

1. <span data-ttu-id="8cc5f-163">Programmā Dynamics 365 dodieties uz **Iestatījumi** > **Pielāgošana** un atlasiet **Risinājumi**.</span><span class="sxs-lookup"><span data-stu-id="8cc5f-163">In the Dynamics 365 app, go to **Settings** > **Customization** and select **Solutions**.</span></span>

1. <span data-ttu-id="8cc5f-164">Pievienojumprogrammu tabulā atrodiet **CustomerInsightsCustomerCard** un atlasiet rindu.</span><span class="sxs-lookup"><span data-stu-id="8cc5f-164">In the table of add-ins look for **CustomerInsightsCustomerCard** and select the row.</span></span>

1. <span data-ttu-id="8cc5f-165">Darbību joslā atlasiet **Lietot risinājuma jaunināšanu**.</span><span class="sxs-lookup"><span data-stu-id="8cc5f-165">Select the **Apply Solution Upgrade** in the action bar.</span></span>

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Risinājuma jaunināšana Dynamics 365 programmu Pielāgošanas apgabalā":::

1. <span data-ttu-id="8cc5f-167">Pēc jaunināšanas procesa sākšanas tiek rādīts ielādes rādītājs, līdz jaunināšana ir pabeigta.</span><span class="sxs-lookup"><span data-stu-id="8cc5f-167">After starting the upgrade process, you'll see a loading indicator until the upgrade completes.</span></span> <span data-ttu-id="8cc5f-168">Ja tajā nav jaunākas versijas, jaunināšanai tiks rādīts kļūdas ziņojums.</span><span class="sxs-lookup"><span data-stu-id="8cc5f-168">If there's no newer version, the upgrade will show an error message.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
