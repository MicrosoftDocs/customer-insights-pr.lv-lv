---
title: Instalējiet un konfigurējiet klienta kartes pievienojumprogrammu
description: Instalējiet un konfigurējiet klienta kartes pievienojumprogrammu programmai Dynamics 365 Customer Insights.
ms.date: 01/20/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: a6d5b49380ed129cf147698a16f5f3f597bf7fbc
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268053"
---
# <a name="customer-card-add-in-preview"></a><span data-ttu-id="66983-103">Klienta kartes pievienojumprogramma (priekšskatījums)</span><span class="sxs-lookup"><span data-stu-id="66983-103">Customer Card Add-in (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="66983-104">Iegūstiet pilnu ainu par saviem klientiem tieši risinājuma Dynamics 365 programmās.</span><span class="sxs-lookup"><span data-stu-id="66983-104">Get a 360-degree view of your customers directly in Dynamics 365 apps.</span></span> <span data-ttu-id="66983-105">Izmantojot klienta kartes pievienojumprogrammu, skatiet demogrāfiskos datus, ieskatus un darbību laika skalas.</span><span class="sxs-lookup"><span data-stu-id="66983-105">View demographics, insights, and activity timelines with the Customer Card Add-in.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="66983-106">Priekšnosacījumi</span><span class="sxs-lookup"><span data-stu-id="66983-106">Prerequisites</span></span>

- <span data-ttu-id="66983-107">Dynamics 365 programma (piemēram, Pārdošanas centrs vai Klientu apkalpošanas centrs), versija 9.0 vai jaunāka ar iespējotu vienoto interfeisu.</span><span class="sxs-lookup"><span data-stu-id="66983-107">Dynamics 365 app (such as Sales Hub or Customer Service Hub), version 9.0 and later with Unified Interface enabled.</span></span>
- <span data-ttu-id="66983-108">Klientu profili [iegūti programmā Dynamics 365, izmantojot programmu Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="66983-108">Customer profiles [ingested from the Dynamics 365 app using Common Data Service](connect-power-query.md).</span></span>
- <span data-ttu-id="66983-109">Klienta kartes pievienojumprogrammas lietotājiem ir jābūt [pievienotam kā lietotājiem](permissions.md) auditorijas ieskatiem.</span><span class="sxs-lookup"><span data-stu-id="66983-109">Users of the Customer Card Add-in need to be [added as users](permissions.md) in audience insights.</span></span>
- <span data-ttu-id="66983-110">[Konfigurētas meklēšanas un filtrēšanas iespējas](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="66983-110">[Configured search and filter capabilities](search-filter-index.md).</span></span>
- <span data-ttu-id="66983-111">Demogrāfiskā kontrole: demogrāfiskie lauki (piemēram, vecums vai dzimums) ir pieejami vienotajā klienta profilā.</span><span class="sxs-lookup"><span data-stu-id="66983-111">Demographic control: Demographic fields(such as age or gender) are available in the unified customer profile.</span></span>
- <span data-ttu-id="66983-112">Bagātināšanas vadīkla: Ir nepieciešama aktīva [bagātināšana](enrichment-hub.md), ko piemērot klientu profiliem.</span><span class="sxs-lookup"><span data-stu-id="66983-112">Enrichment control: Requires active [enrichments](enrichment-hub.md) applied to customer profiles.</span></span>
- <span data-ttu-id="66983-113">Intelekta kontrolēšana: Nepieciešami dati, kas ģenerēti, izmantojot Azure algoritmisko mācīšanos ([Prognozes](predictions.md) vai [Pielāgotus modeļus](custom-models.md))</span><span class="sxs-lookup"><span data-stu-id="66983-113">Intelligence control: Requires data generated using Azure Machine Learning ([Predictions](predictions.md) or [Custom Models](custom-models.md))</span></span>
- <span data-ttu-id="66983-114">Mērīt vadīklu: Nepieciešamas [konfigurētās mērvienības](measures.md).</span><span class="sxs-lookup"><span data-stu-id="66983-114">Measure control: Requires [configured measures](measures.md).</span></span>
- <span data-ttu-id="66983-115">Laika skalas vadīkla: Nepieciešamas [konfigurētās darbības](activities.md).</span><span class="sxs-lookup"><span data-stu-id="66983-115">Timeline control: Requires [configured activities](activities.md).</span></span>

## <a name="install-the-customer-card-add-in"></a><span data-ttu-id="66983-116">Klienta kartes pievienojumprogrammas instalēšana</span><span class="sxs-lookup"><span data-stu-id="66983-116">Install the Customer Card Add-in</span></span>

<span data-ttu-id="66983-117">Klienta kartes pievienojumprogramma ir risinājums klientu iesaistes programmām pakalpojumā Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="66983-117">The Customer Card Add-in is a solution for customer engagement apps in Dynamics 365.</span></span> <span data-ttu-id="66983-118">Lai instalētu šo risinājumu, dodieties uz AppSource un meklējiet **Dynamics Customer Card**.</span><span class="sxs-lookup"><span data-stu-id="66983-118">To install the solution, go to AppSource and search for **Dynamics Customer Card**.</span></span> <span data-ttu-id="66983-119">Atlasiet [Klienta kartes pievienojumprogramma pakalpojumā AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) un atlasiet **Iegūt to tūlīt**.</span><span class="sxs-lookup"><span data-stu-id="66983-119">Select the [Customer Card Add-in on AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) and select **Get It Now**.</span></span>

<span data-ttu-id="66983-120">Lai Dynamics 365 programma instalētu risinājumu, jums, iespējams, vajadzēs pieteikties ar saviem administratora akreditācijas datiem.</span><span class="sxs-lookup"><span data-stu-id="66983-120">You may need to sign in with your admin credentials for the Dynamics 365 app to install the solution.</span></span>

<span data-ttu-id="66983-121">Var paiet zināms laiks, līdz risinājums tiks instalēts jūsu vidē.</span><span class="sxs-lookup"><span data-stu-id="66983-121">It can take some time for the solution to be installed to your environment.</span></span>

## <a name="configure-the-customer-card-add-in"></a><span data-ttu-id="66983-122">Klienta kartes pievienojumprogrammas konfigurēšana</span><span class="sxs-lookup"><span data-stu-id="66983-122">Configure the Customer Card Add-in</span></span>

1. <span data-ttu-id="66983-123">Kā administrators atveriet sadaļu **Iestatījumi** pakalpojumā Dynamics 365 un atlasiet **Risinājumi**.</span><span class="sxs-lookup"><span data-stu-id="66983-123">As an admin, go to the **Settings** section in Dynamics 365 and select **Solutions**.</span></span>

1. <span data-ttu-id="66983-124">Atlasiet saiti **Parādāmais nosaukums** risinājumam **Dynamics 365 Customer Insights klienta kartes pievienojumprogramma (priekšskatījums)**.</span><span class="sxs-lookup"><span data-stu-id="66983-124">Select the **Display Name** link for the **Dynamics 365 Customer Insights Customer Card Add-in (Preview)** solution.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="66983-125">![Parādāmā nosaukuma atlasīšana](media/select-display-name.png "Parādāmā nosaukuma atlasīšana")</span><span class="sxs-lookup"><span data-stu-id="66983-125">![Select display name](media/select-display-name.png "Select display name")</span></span>

1. <span data-ttu-id="66983-126">Atlasiet **Pierakstīties** un ievadiet tā administratora konta akreditācijas datus, ko izmantojat, lai konfigurētu Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="66983-126">Select **Sign in** and enter the credentials for the admin account you use to configure Customer Insights.</span></span>

   > [!NOTE]
   > <span data-ttu-id="66983-127">Pārbaudiet, vai, atlasot pogu **Pierakstīties**, pārlūkprogrammas uznirstošo elementu bloķētājs nebloķē autentifikācijas logu.</span><span class="sxs-lookup"><span data-stu-id="66983-127">Check that the browser pop-up blocker does not block the authentication window when you select the **Sign in** button.</span></span>

1. <span data-ttu-id="66983-128">Atlasiet vidi, no kuras vēlaties izgūt datus.</span><span class="sxs-lookup"><span data-stu-id="66983-128">Select the environment you want to fetch data from.</span></span>

1. <span data-ttu-id="66983-129">Definējiet, kuru lauku kartējumu uz ierakstiem Dynamics 365 lietojumprogrammā.</span><span class="sxs-lookup"><span data-stu-id="66983-129">Define which the field mapping to records in the Dynamics 365 app.</span></span>
   - <span data-ttu-id="66983-130">Lai kartētu ar kontaktpersonu, atlasiet klientu entītijas lauku, kas atbilst jūsu kontaktpersonas entītijas ID.</span><span class="sxs-lookup"><span data-stu-id="66983-130">To map with a contact, select the field in the Customer entity that matches the ID of your contact entity.</span></span>
   - <span data-ttu-id="66983-131">Lai kartētu ar kontaktpersonu, atlasiet klientu entītijas lauku, kas atbilst jūsu konta entītijas ID.</span><span class="sxs-lookup"><span data-stu-id="66983-131">To map with an account, select the field in the Customer entity that matches the ID of your account entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="66983-132">![Lauks Kontaktpersonas ID](media/contact-id-field.png "Lauks Kontaktpersonas ID")</span><span class="sxs-lookup"><span data-stu-id="66983-132">![Contact ID field](media/contact-id-field.png "Contact ID field")</span></span>

1. <span data-ttu-id="66983-133">Atlasiet **Saglabāt konfigurāciju**, lai saglabātu iestatījumus.</span><span class="sxs-lookup"><span data-stu-id="66983-133">Select **Save configuration** to save the settings.</span></span>

1. <span data-ttu-id="66983-134">Pēc tam risinājumā Dynamics 365 ir jāpiešķir drošības lomas, lai lietotāji varētu pielāgot un apskatīt klienta karti.</span><span class="sxs-lookup"><span data-stu-id="66983-134">Next, you need to assign security roles in Dynamics 365 so users can customize and see the customer card.</span></span> <span data-ttu-id="66983-135">Programmā Dynamics 365 atveriet sadaļu **Iestatījumi** > **Drošība** > **Lietotāji**.</span><span class="sxs-lookup"><span data-stu-id="66983-135">In Dynamics 365, go to **Settings** > **Security** > **Users**.</span></span> <span data-ttu-id="66983-136">Atlasiet lietotājus, lai rediģētu lietotāju lomas, un atlasiet **Pārvaldīt lomas**.</span><span class="sxs-lookup"><span data-stu-id="66983-136">Select the users to edit user roles and select **Manage roles**.</span></span>

1. <span data-ttu-id="66983-137">Piešķiriet lomu **Customer Insights kartes pielāgotājs** lietotājiem, kuri visai organizācijai pielāgos kartē rādāmo saturu.</span><span class="sxs-lookup"><span data-stu-id="66983-137">Assign the **Customer Insights Card Customizer** role to users who will customize the content shown on the card for the whole organization.</span></span>

## <a name="add-customer-card-controls-to-forms"></a><span data-ttu-id="66983-138">Klienta karšu vadīklu pievienošana veidlapām</span><span class="sxs-lookup"><span data-stu-id="66983-138">Add Customer Card controls to forms</span></span>
  
1. <span data-ttu-id="66983-139">Lai savai kontaktpersonas veidlapai pievienotu klienta kartes vadīklas, dodieties uz **Iestatījumi** > **Pielāgojumi** risinājumā Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="66983-139">To add the Customer Card controls to your Contact form, go to the **Settings** > **Customizations** in Dynamics 365.</span></span>

1. <span data-ttu-id="66983-140">Atlasiet **Pielāgot sistēmu**.</span><span class="sxs-lookup"><span data-stu-id="66983-140">Select **Customize the System**.</span></span>

1. <span data-ttu-id="66983-141">Pārejiet uz entītiju **Kontaktpersona**, izvērsiet to un pēc tam atlasiet **Veidlapas**.</span><span class="sxs-lookup"><span data-stu-id="66983-141">Browse to the **Contact** entity, expand it and select **Forms**.</span></span>

1. <span data-ttu-id="66983-142">Atlasiet kontaktpersonas veidlapu, kurai vēlaties pievienot klienta kartes vadīklas.</span><span class="sxs-lookup"><span data-stu-id="66983-142">Select the contact form to which you want to add the Customer Card controls.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="66983-143">![Kontaktpersonas veidlapas atlase](media/contact-active-forms.png "Kontaktpersonas veidlapas atlase")</span><span class="sxs-lookup"><span data-stu-id="66983-143">![Select Contact form](media/contact-active-forms.png "Select Contact form")</span></span>

1. <span data-ttu-id="66983-144">Lai pievienotu vadīklu, veidlapu redaktorā velciet jebkuru lauku no **lauku pārlūka** uz vietu, kur vēlaties novietot vadīklu.</span><span class="sxs-lookup"><span data-stu-id="66983-144">To add a control, in the form editor, drag any field from the **Field Explorer** to where you want the control to appear.</span></span>

1. <span data-ttu-id="66983-145">Atlasiet tikko pievienoto lauku veidlapā un atlasiet **Mainīt rekvizītus**.</span><span class="sxs-lookup"><span data-stu-id="66983-145">Select the field on the form that you just added, and select **Change Properties**.</span></span>

1. <span data-ttu-id="66983-146">Dodieties uz cilni **Vadīklas** un atlasiet **Pievienot vadīklu**.</span><span class="sxs-lookup"><span data-stu-id="66983-146">Go to the **Controls** tab and select **Add Control**.</span></span> <span data-ttu-id="66983-147">Izvēlieties vienu no pieejamajām pielāgotajām vadīklām un atlasiet **Pievienot**.</span><span class="sxs-lookup"><span data-stu-id="66983-147">Choose one of the available custom controls and select **Add**.</span></span>

1. <span data-ttu-id="66983-148">Dialoglodziņā **Lauka rekvizīti** notīriet izvēles rūtiņu **Rādīt etiķeti veidlapā**.</span><span class="sxs-lookup"><span data-stu-id="66983-148">In the **Field Properties** dialog, clear the **Display label on the form** check box.</span></span>

1. <span data-ttu-id="66983-149">Vadīklai atlasiet opciju **Tīmeklis**.</span><span class="sxs-lookup"><span data-stu-id="66983-149">Select the **Web** option for the control.</span></span> <span data-ttu-id="66983-150">Bagātināšanas vadīklai atlasiet, kuru bagātināšanas veidu vēlaties rādīt, konfigurējot lauku **enrichmentType**.</span><span class="sxs-lookup"><span data-stu-id="66983-150">For the Enrichment control, select which enrichment type you want to display by configuring the **enrichmentType** field.</span></span> <span data-ttu-id="66983-151">Katram bagātināšanas tipam pievienojiet atsevišķu bagātināšanas vadīklu.</span><span class="sxs-lookup"><span data-stu-id="66983-151">Add a separate enrichment control for each enrichment type.</span></span>

1. <span data-ttu-id="66983-152">Atlasiet **Saglabāt** un **Publicēt**, lai publicētu atjaunināto kontaktpersonas veidlapu.</span><span class="sxs-lookup"><span data-stu-id="66983-152">Select **Save** and **Publish** to publish the updated contact form.</span></span>

1. <span data-ttu-id="66983-153">Atveriet publicēto kontaktpersonas veidlapu.</span><span class="sxs-lookup"><span data-stu-id="66983-153">Go to the published contact form.</span></span> <span data-ttu-id="66983-154">Tiek parādīta tikko pievienotā vadīkla.</span><span class="sxs-lookup"><span data-stu-id="66983-154">You'll see the newly added control.</span></span> <span data-ttu-id="66983-155">Iespējams, pirmajā lietošanas reizē būs jāpierakstās.</span><span class="sxs-lookup"><span data-stu-id="66983-155">You might need to sign in the first time you use it.</span></span>

1. <span data-ttu-id="66983-156">Lai pielāgotu pielāgotajā vadīklā rādāmo informāciju, augšējā labajā stūrī atlasiet rediģēšanas pogu.</span><span class="sxs-lookup"><span data-stu-id="66983-156">To customize what you want to show on the custom control, select the edit button in the upper-right corner.</span></span>

## <a name="upgrade-customer-card-add-in"></a><span data-ttu-id="66983-157">Klienta kartes pievienojumprogrammas jaunināšana</span><span class="sxs-lookup"><span data-stu-id="66983-157">Upgrade Customer Card Add-in</span></span>
<span data-ttu-id="66983-158">Klienta kartes pievienojumprogramma netiek automātiski jaunināta.</span><span class="sxs-lookup"><span data-stu-id="66983-158">The Customer Card Add-in doesn't upgrade automatically.</span></span> <span data-ttu-id="66983-159">Lai jauninātu uz jaunāko versiju, izpildiet šo procedūru programmā Dynamics 365, kurā ir instalēta pievienojumprogramma.</span><span class="sxs-lookup"><span data-stu-id="66983-159">To upgrade to the latest version, follow this procedure in the Dynamics 365 app that has the Add-in installed.</span></span>

1. <span data-ttu-id="66983-160">Programmā Dynamics 365 dodieties uz **Iestatījumi** > **Pielāgošana** un atlasiet **Risinājumi**.</span><span class="sxs-lookup"><span data-stu-id="66983-160">In the Dynamics 365 app, go to **Settings** > **Customization** and select **Solutions**.</span></span>

1. <span data-ttu-id="66983-161">Pievienojumprogrammu tabulā atrodiet **CustomerInsightsCustomerCard** un atlasiet rindu.</span><span class="sxs-lookup"><span data-stu-id="66983-161">In the table of add-ins look for **CustomerInsightsCustomerCard** and select the row.</span></span>

1. <span data-ttu-id="66983-162">Darbību joslā atlasiet **Lietot risinājuma jaunināšanu**.</span><span class="sxs-lookup"><span data-stu-id="66983-162">Select the **Apply Solution Upgrade** in the action bar.</span></span>

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Risinājuma jaunināšana Dynamics 365 programmu Pielāgošanas apgabalā":::

1. <span data-ttu-id="66983-164">Pēc jaunināšanas procesa sākšanas tiek rādīts ielādes rādītājs, līdz jaunināšana ir pabeigta.</span><span class="sxs-lookup"><span data-stu-id="66983-164">After starting the upgrade process, you'll see a loading indicator until the upgrade completes.</span></span> <span data-ttu-id="66983-165">Ja tajā nav jaunākas versijas, jaunināšanai tiks rādīts kļūdas ziņojums.</span><span class="sxs-lookup"><span data-stu-id="66983-165">If there's no newer version, the upgrade will show an error message.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]