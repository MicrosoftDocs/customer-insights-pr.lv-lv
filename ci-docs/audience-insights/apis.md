---
title: Darbs ar API
description: Izmantojiet API un izprotiet ierobežojumus.
ms.date: 05/10/2021
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 4d41d7d328dfa6699b5f5e992d3a5bf3179490d8
ms.sourcegitcommit: 33a8e21b3bf6521bdb8346f81f79fce88091ddfd
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 05/10/2021
ms.locfileid: "6016629"
---
# <a name="work-with-customer-insights-apis"></a><span data-ttu-id="6c9e8-103">Darbs ar API Customer Insights</span><span class="sxs-lookup"><span data-stu-id="6c9e8-103">Work with Customer Insights APIs</span></span>

<span data-ttu-id="6c9e8-104">Dynamics 365 Customer Insights nodrošina API iespēju veidot savas lietojumprogrammas, pamatojoties uz Customer Insights datiem.</span><span class="sxs-lookup"><span data-stu-id="6c9e8-104">Dynamics 365 Customer Insights provides APIs to build your own applications based you data in Customer Insights.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6c9e8-105">Detalizēta informācija par šiem API ir iekļauta [atsaucē API Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span><span class="sxs-lookup"><span data-stu-id="6c9e8-105">Details of these APIs, are listed on the [Customer Insights APIs reference](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span></span> <span data-ttu-id="6c9e8-106">Tajos ir iekļauta papildinformācija par operācijām, parametriem un atbildēm.</span><span class="sxs-lookup"><span data-stu-id="6c9e8-106">They include additional information about operations, parameters, and responses.</span></span>

<span data-ttu-id="6c9e8-107">Šajā rakstā ir norādīts, kā varat piekļūt API Customer Insights, izveidot reģistrāciju Azure programmā un palīdzēt iepazīties ar pieejamajām klientu bibliotēkām.</span><span class="sxs-lookup"><span data-stu-id="6c9e8-107">This article guides you to access to the Customer Insights APIs, create an Azure App Registration, and help you get started with the available client libraries.</span></span>

## <a name="get-started-trying-the-customer-insights-apis"></a><span data-ttu-id="6c9e8-108">Darba sākšana ar API Customer Insights</span><span class="sxs-lookup"><span data-stu-id="6c9e8-108">Get started trying the Customer Insights APIs</span></span>

1. <span data-ttu-id="6c9e8-109">[Pierakstieties](https://home.ci.ai.dynamics.com) risinājumā Customer Insights .</span><span class="sxs-lookup"><span data-stu-id="6c9e8-109">[Sign in](https://home.ci.ai.dynamics.com) to Customer Insights.</span></span> <span data-ttu-id="6c9e8-110">Ja jums vēl nav abonementa, [pierakstieties Customer Insights izmēģinājumversijai](https://aka.ms/tryci).</span><span class="sxs-lookup"><span data-stu-id="6c9e8-110">If you don't have a subscription yet, [sign up for a trial of Customer Insights](https://aka.ms/tryci).</span></span>

1. <span data-ttu-id="6c9e8-111">Lai iespējotu API Customer Insights vidē, apmeklējiet **Administrators** > **Atļaujas**.</span><span class="sxs-lookup"><span data-stu-id="6c9e8-111">To enable APIs on your Customer Insights environment, go to **Admin** > **Permissions**.</span></span> <span data-ttu-id="6c9e8-112">Lai to izdarītu, jums ir nepieciešamas administratora atļaujas.</span><span class="sxs-lookup"><span data-stu-id="6c9e8-112">You'll need admin permissions to do so.</span></span>

1. <span data-ttu-id="6c9e8-113">Atveriet **API** cilni un atlasiet pogu **Iespējot**.</span><span class="sxs-lookup"><span data-stu-id="6c9e8-113">Go to the **APIs** tab and select the **Enable** button.</span></span>    
   <span data-ttu-id="6c9e8-114">Iespējojot API, tiek izveidota primārā un sekundārā abonēšanas atslēga jūsu instancei, kas tiek izmantota API pieprasījumos.</span><span class="sxs-lookup"><span data-stu-id="6c9e8-114">Enabling the APIs creates a primary and secondary subscription key for your instance that gets used in the API requests.</span></span> <span data-ttu-id="6c9e8-115">Varat atkārtoti ģenerēt atslēgas, atlasot opciju **Atjaunot primāro** vai **Atjaunot sekundāro** sadaļā **Administrators** > **Atļaujas** > **API**.</span><span class="sxs-lookup"><span data-stu-id="6c9e8-115">You can regenerate the keys by selecting the **Regenerate primary** or **Regenerate secondary** on **Admin** > **Permissions** > **APIs**.</span></span>

   :::image type="content" source="media/enable-apis.gif" alt-text="Iespējot API Customer Insights":::

1. <span data-ttu-id="6c9e8-117">Atlasiet **Izpētīt mūsu API**, lai [izmēģinātu API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).</span><span class="sxs-lookup"><span data-stu-id="6c9e8-117">Select **Explore our APIs** to [try out the APIs](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).</span></span>

1. <span data-ttu-id="6c9e8-118">Izvēlieties API darbību un atlasiet **Izmēģināt to**.</span><span class="sxs-lookup"><span data-stu-id="6c9e8-118">Choose an API operation and select **Try it**.</span></span>

1. <span data-ttu-id="6c9e8-119">Sānu rūtī iestatiet nolaižamās izvēlnes **Autorizācija** vērtību uz **Netiešs**.</span><span class="sxs-lookup"><span data-stu-id="6c9e8-119">In the side pane, set the value in the **Authorization** drop-down menu to **implicit**.</span></span> <span data-ttu-id="6c9e8-120">Virsrakstam `Authorization` ir pievienots nesēja marķieris.</span><span class="sxs-lookup"><span data-stu-id="6c9e8-120">The `Authorization` header gets with a bearer token added.</span></span> <span data-ttu-id="6c9e8-121">Jūsu abonementa atslēga tiek automātiski pārnesta.</span><span class="sxs-lookup"><span data-stu-id="6c9e8-121">Your subscription key will be automatically populated.</span></span>
  
1. <span data-ttu-id="6c9e8-122">Ja vēlaties, pievienojiet visus nepieciešamos vaicājuma parametrus.</span><span class="sxs-lookup"><span data-stu-id="6c9e8-122">Optionally, add all necessary query parameters.</span></span>

1. <span data-ttu-id="6c9e8-123">Ritiniet uz sānu rūts lejasdaļu un atlasiet vienumu **Nosūtīt**.</span><span class="sxs-lookup"><span data-stu-id="6c9e8-123">Scroll to the bottom of the side pane and select **Send**.</span></span>

<span data-ttu-id="6c9e8-124">HTTP atbilde drīz būs redzama tālāk.</span><span class="sxs-lookup"><span data-stu-id="6c9e8-124">The HTTP response will soon appear below.</span></span>


   :::image type="content" source="media/try-apis.gif" alt-text="Animēts GIF attēls, kurā parādīts, kā atlasīt API testēšanu.":::

## <a name="create-a-new-app-registration-in-the-azure-portal"></a><span data-ttu-id="6c9e8-126">Jaunas programmas reģistrēšanas izveide Azure portālā</span><span class="sxs-lookup"><span data-stu-id="6c9e8-126">Create a new app registration in the Azure portal</span></span>

<span data-ttu-id="6c9e8-127">Šīs darbības palīdz iepazīties ar API Customer Insights lietojumprogrammā Azure, izmantojot deleģētās atļaujas.</span><span class="sxs-lookup"><span data-stu-id="6c9e8-127">These steps help you get started in using the Customer Insights APIs in an Azure application using delegated permissions.</span></span> <span data-ttu-id="6c9e8-128">Vispirms pārliecinieties, vai esat pabeidzis [sadaļu Darba sākšana](#get-started-trying-the-customer-insights-apis).</span><span class="sxs-lookup"><span data-stu-id="6c9e8-128">Make sure to have completed [Getting started section](#get-started-trying-the-customer-insights-apis) first.</span></span>

1. <span data-ttu-id="6c9e8-129">Pierakstieties [Azure portālā](https://portal.azure.com) ar kontu, kas var piekļūt Customer Insights datiem.</span><span class="sxs-lookup"><span data-stu-id="6c9e8-129">Sign in to the [Azure portal](https://portal.azure.com) with the account that can access the Customer Insights data.</span></span>

1. <span data-ttu-id="6c9e8-130">Pa kreisi atlasiet **Programmu reģistrācijas**.</span><span class="sxs-lookup"><span data-stu-id="6c9e8-130">On the left, select **App registrations**.</span></span>

1. <span data-ttu-id="6c9e8-131">Atlasiet **Jauna reģistrācija**, norādiet lietojumprogrammas nosaukumu un izvēlieties konta veidu.</span><span class="sxs-lookup"><span data-stu-id="6c9e8-131">Select **New registration** provide an application name and choose the account type.</span></span>
   <span data-ttu-id="6c9e8-132">Ja nepieciešams, pievienojiet novirzīšanas URL.</span><span class="sxs-lookup"><span data-stu-id="6c9e8-132">Optionally, add a redirect URL.</span></span> <span data-ttu-id="6c9e8-133">Ar http://localhost pietiek, lai izstrādātu lietojumprogrammu jūsu lokālajā datorā.</span><span class="sxs-lookup"><span data-stu-id="6c9e8-133">http://localhost is sufficient for developing an application on your local computer.</span></span>

1. <span data-ttu-id="6c9e8-134">Jaunās programmas reģistrācijā ejiet uz **API atļaujas**.</span><span class="sxs-lookup"><span data-stu-id="6c9e8-134">On your new App registration, go to **API permissions**.</span></span>

   :::image type="content" source="media/app-registration-1.gif" alt-text="Animēts GIF attēls, lai iestatītu API atļauju programmas reģistrācijā.":::

1. <span data-ttu-id="6c9e8-136">Atlasiet **Pievienot atļauju** un atlasiet sānu rūtī **Customer Insights**.</span><span class="sxs-lookup"><span data-stu-id="6c9e8-136">Select **Add a permission** and select **Customer Insights** in the side pane.</span></span>

1. <span data-ttu-id="6c9e8-137">**Atļauju tipam** atlasiet **Deleģētās atļaujas** un atlasiet atļauju **Lietotāja personificēšana**.</span><span class="sxs-lookup"><span data-stu-id="6c9e8-137">For **Permission type**, select **Delegated permissions** and select the **user_impersonation** permission.</span></span>

1. <span data-ttu-id="6c9e8-138">Atlasiet **Pievienot atļaujas**.</span><span class="sxs-lookup"><span data-stu-id="6c9e8-138">Select **Add permissions**.</span></span> <span data-ttu-id="6c9e8-139">Ja nepieciešams piekļūt API, neveicot lietotāja pieteikšanos, skatiet sadaļu [Servera-servera lietojumprogrammu atļaujas](#server-to-server-application-permissions).</span><span class="sxs-lookup"><span data-stu-id="6c9e8-139">If you need to access the API without a user signing in, review the [Server-to-server application permissions](#server-to-server-application-permissions) section.</span></span>

1. <span data-ttu-id="6c9e8-140">Atlasiet **Piešķirt administratora piekrišanu...**, lai pabeigtu programmas reģistrāciju.</span><span class="sxs-lookup"><span data-stu-id="6c9e8-140">Select **Grant admin consent for...** to complete the app registration.</span></span>

<span data-ttu-id="6c9e8-141">Varat izmantot šīs programmas reģistrēšanas lietojumprogrammas/klienta ID Microsoft autentifikācijas bibliotēkā (MSAL), lai iegūtu nesēja marķieri, kas jānosūta kopā ar jūsu pieprasījumu API.</span><span class="sxs-lookup"><span data-stu-id="6c9e8-141">You can use the Application/Client ID for this app registration with the Microsoft Authentication Library (MSAL) to obtain a bearer token to send with your request to the API.</span></span>

:::image type="content" source="media/grant-admin-consent.gif" alt-text="Animēts GIF attēls, lai piešķirtu administratora piekrišanu.":::

<span data-ttu-id="6c9e8-143">Papildinformāciju par MSAL skatiet rakstā [Microsoft autentifikācijas bibliotēkas pārskats (MSAL)](/azure/active-directory/develop/msal-overview).</span><span class="sxs-lookup"><span data-stu-id="6c9e8-143">For more information about MSAL, see [Overview of Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview).</span></span>

<span data-ttu-id="6c9e8-144">Lai iegūtu papildinformāciju par lietojumprogrammas reģistrēšanu pakalpojumā Azure, skatiet [Jauno Azure portāla programmas reģistrācijas pieredzi](/azure/active-directory/develop/app-registration-portal-training-guide).</span><span class="sxs-lookup"><span data-stu-id="6c9e8-144">For more information about app registration in Azure, see [The new Azure portal app registration experience](/azure/active-directory/develop/app-registration-portal-training-guide).</span></span>

<span data-ttu-id="6c9e8-145">Informāciju par API izmantošanu mūsu klientu bibliotēkās skatiet sadaļā [Customer Insights klientu bibliotēkas](#customer-insights-client-libraries).</span><span class="sxs-lookup"><span data-stu-id="6c9e8-145">For information on using the APIs our client libraries, see [Customer Insights client libraries](#customer-insights-client-libraries).</span></span>

### <a name="server-to-server-application-permissions"></a><span data-ttu-id="6c9e8-146">Servera-servera lietojumprogrammas atļaujas</span><span class="sxs-lookup"><span data-stu-id="6c9e8-146">Server-to-server application permissions</span></span>

<span data-ttu-id="6c9e8-147">Sadaļa [Lietojumprogrammas reģistrācijas](#create-a-new-app-registration-in-the-azure-portal) ieskicē, kā reģistrēt programmu, kas liek lietotājam pieteikties autentifikācijai.</span><span class="sxs-lookup"><span data-stu-id="6c9e8-147">The [app registration section](#create-a-new-app-registration-in-the-azure-portal) outlines how to register an app that requires a user to sign in for authentication.</span></span> <span data-ttu-id="6c9e8-148">Uzziniet, kā izveidot programmas reģistrāciju, kurai nav nepieciešama lietotāja mijiedarbība, un ko var palaist serverī.</span><span class="sxs-lookup"><span data-stu-id="6c9e8-148">Learn how to create an app registration that does not need user interaction and can be run on a server.</span></span>

1. <span data-ttu-id="6c9e8-149">Ejiet uz **API permissions** jūsu programmas reģistrācijas Azure portālā.</span><span class="sxs-lookup"><span data-stu-id="6c9e8-149">On your App registration in the Azure portal, go to **API permissions**.</span></span>

1. <span data-ttu-id="6c9e8-150">Atlasiet **Pievienot atļauju**.</span><span class="sxs-lookup"><span data-stu-id="6c9e8-150">Select **Add a permission**.</span></span> 

1. <span data-ttu-id="6c9e8-151">Sarakstā atlasiet **Manas organizācijas lietotie API** un sarakstā izvēlieties **Dynamics 365 AI for Customer Insights**.</span><span class="sxs-lookup"><span data-stu-id="6c9e8-151">Select the **APIs my organization uses** tab and choose **Dynamics 365 AI for Customer Insights** from the list.</span></span> 

1. <span data-ttu-id="6c9e8-152">**Atļauju tipam** atlasiet **Deleģētās atļaujas** un atlasiet atļauju **CustomerInsights.Api.All**.</span><span class="sxs-lookup"><span data-stu-id="6c9e8-152">For **Permission type**, select **Application permissions** and select the **CustomerInsights.Api.All** permission.</span></span>

1. <span data-ttu-id="6c9e8-153">Atlasiet **Pievienot atļaujas**.</span><span class="sxs-lookup"><span data-stu-id="6c9e8-153">Select **Add permissions**.</span></span>

1. <span data-ttu-id="6c9e8-154">Atgriezieties **API atļaujas**, lai reģistrētu savu lietojumprogrammu.</span><span class="sxs-lookup"><span data-stu-id="6c9e8-154">Go back to **API permissions** for your app registration.</span></span>

1. <span data-ttu-id="6c9e8-155">Atlasiet **Piešķirt administratora piekrišanu...**, lai pabeigtu programmas reģistrāciju.</span><span class="sxs-lookup"><span data-stu-id="6c9e8-155">Select **Grant admin consent for...** to complete the app registration.</span></span>

   :::image type="content" source="media/grant-admin-consent.gif" alt-text="Animēts GIF attēls, lai piešķirtu administratora piekrišanu.":::

1. <span data-ttu-id="6c9e8-157">Lai to izdarītu, ir jāpievieno lietojumprogrammas reģistrācijas nosaukums kā lietotājs Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="6c9e8-157">To conclude, we have to add the name of the app registration as a user in Customer Insights.</span></span>    
   <span data-ttu-id="6c9e8-158">Atveriet sadaļu Customer Insights, atveriet **Administrators** > **Atļaujas** un atlasiet vienumu **Pievienot lietotāju**.</span><span class="sxs-lookup"><span data-stu-id="6c9e8-158">Open Customer Insights, go to **Admin** > **Permissions** and select **Add user**.</span></span>

1. <span data-ttu-id="6c9e8-159">Meklējiet savas programmas reģistrācijas nosaukumu, meklēšanas rezultātos atlasiet to un atlasiet vienumu **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="6c9e8-159">Search for the name of your app registration, select it from the search results, and select **Save**.</span></span>

## <a name="customer-insights-client-libraries"></a><span data-ttu-id="6c9e8-160">Customer Insights klientu bibliotēkas</span><span class="sxs-lookup"><span data-stu-id="6c9e8-160">Customer Insights client libraries</span></span>

<span data-ttu-id="6c9e8-161">Šī sadaļa palīdz sākt darbu ar API Customer Insights, izmantojot pieejamās klientu bibliotēkas.</span><span class="sxs-lookup"><span data-stu-id="6c9e8-161">This section helps you get started using the client libraries available for the Customer Insights APIs.</span></span> <span data-ttu-id="6c9e8-162">Viss bibliotēkas avota kods un programmu paraugi ir atrodami [Customer Insights GitHub lapā](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries).</span><span class="sxs-lookup"><span data-stu-id="6c9e8-162">All library source code and sample applications can be found on the [Customer Insights GitHub page](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries).</span></span> 

### <a name="c-nuget"></a><span data-ttu-id="6c9e8-163">C# NuGet</span><span class="sxs-lookup"><span data-stu-id="6c9e8-163">C# NuGet</span></span>

<span data-ttu-id="6c9e8-164">Uzziniet, kā sākt lietot C# klienta bibliotēkas no NuGet.org. Papildinformāciju par NuGet pakotni skatiet [Microsoft.Dynamics.CustomerInsights.API](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).</span><span class="sxs-lookup"><span data-stu-id="6c9e8-164">Learn how to get started using the C# client libraries from NuGet.org. For more information on the NuGet package, see [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).</span></span> <span data-ttu-id="6c9e8-165">Pašlaik šī pakotne tiek aptver uz netstandard 2.0 un netcoreapp 2.0 ietvarus.</span><span class="sxs-lookup"><span data-stu-id="6c9e8-165">Currently, this package targets the netstandard2.0 and netcoreapp2.0 frameworks.</span></span>

#### <a name="add-the-c-client-library-to-a-c-project"></a><span data-ttu-id="6c9e8-166">Pievienot C# klienta bibliotēku C# projektam</span><span class="sxs-lookup"><span data-stu-id="6c9e8-166">Add the C# client library to a C# project</span></span>

1. <span data-ttu-id="6c9e8-167">Rīkā Visual Studio atveriet jūsu projekta **NuGet pakotņu pārvaldnieku**.</span><span class="sxs-lookup"><span data-stu-id="6c9e8-167">In Visual Studio, open the **NuGet Package Manager** for your project.</span></span>

1. <span data-ttu-id="6c9e8-168">Meklējiet **Microsoft.Dynamics.CustomerInsights.API**.</span><span class="sxs-lookup"><span data-stu-id="6c9e8-168">Search for **Microsoft.Dynamics.CustomerInsights.Api**.</span></span>

1. <span data-ttu-id="6c9e8-169">Atlasiet **Instalēt**, lai projektam pievienotu pakotni.</span><span class="sxs-lookup"><span data-stu-id="6c9e8-169">Select **Install** to add the package to the project.</span></span>
   <span data-ttu-id="6c9e8-170">Vai arī izpildiet šo komandu, kas atrodas **NuGet pakotņu pārvaldnieka konsolē**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span><span class="sxs-lookup"><span data-stu-id="6c9e8-170">Alternatively, run this command in the **NuGet Package Manager Console**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span></span>

   :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Pievienot NuGet pakotni projektam Visual Studio":::

#### <a name="use-the-c-client-library"></a><span data-ttu-id="6c9e8-172">Izmantojiet C# klienta bibliotēku</span><span class="sxs-lookup"><span data-stu-id="6c9e8-172">Use the C# client library</span></span>

1. <span data-ttu-id="6c9e8-173">Izmantojiet [Microsoft autentifikācijas bibliotēku (MSAL)](/azure/active-directory/develop/msal-overview), lai iegūtu `AccessToken`, izmantojot esošo [Azure programmu reģistrāciju](#create-a-new-app-registration-in-the-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="6c9e8-173">Use the [Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview) to get an `AccessToken` using your existing [Azure app registration](#create-a-new-app-registration-in-the-azure-portal).</span></span>

1. <span data-ttu-id="6c9e8-174">Pēc sekmīgas autentificēšanās un marķiera iegādes izbūvējiet jaunu vai izmantojiet esošu `HttpClient` ar papildu **DefaultRequestHeaders "Autorizāciju"**, kas iestatīta kā **<access token>nesējs** un **Ocp-Apim-abonementa atslēga**, kas iestatīta uz [**abonementa atslēgu** no vides Customer Insights](#get-started-trying-the-customer-insights-apis).</span><span class="sxs-lookup"><span data-stu-id="6c9e8-174">After successfully authenticating and acquiring a token, construct a new or use an existing `HttpClient` with the additional **DefaultRequestHeaders "Authorization"** set to **Bearer <access token>** and **Ocp-Apim-Subscription-Key** set to the [**subscription key** from your Customer Insights environment](#get-started-trying-the-customer-insights-apis).</span></span>    
   <span data-ttu-id="6c9e8-175">Ja nepieciešams, atiestatiet galveni **Autorizācija**.</span><span class="sxs-lookup"><span data-stu-id="6c9e8-175">Reset the **Authorization** header when appropriate.</span></span> <span data-ttu-id="6c9e8-176">Piemēram, ja ir izbeidzies marķieris.</span><span class="sxs-lookup"><span data-stu-id="6c9e8-176">For example, when the token expired.</span></span>

1. <span data-ttu-id="6c9e8-177">Nododiet to `HttpClient`, veidojot `CustomerInsights` klientu.</span><span class="sxs-lookup"><span data-stu-id="6c9e8-177">Pass this `HttpClient` into the construction of the `CustomerInsights` client.</span></span>

   :::image type="content" source="media/httpclient-sample.png" alt-text="Httpclient paraugs":::

1. <span data-ttu-id="6c9e8-179">Piemēram, veiciet zvanus ar klientu uz "paplašinājuma metodēm" `GetAllInstancesAsync`.</span><span class="sxs-lookup"><span data-stu-id="6c9e8-179">Make calls with the client to the "extension methods", for example, `GetAllInstancesAsync`.</span></span> <span data-ttu-id="6c9e8-180">Ja ir vēlama piekļuve pamatdatiem `Microsoft.Rest.HttpOperationResponse`, izmantojiet, piemēram, "http ziņojumu metodes" `GetAllInstancesWithHttpMessagesAsync`.</span><span class="sxs-lookup"><span data-stu-id="6c9e8-180">If access to the underlying `Microsoft.Rest.HttpOperationResponse` is preferred, use the "http message methods", for example `GetAllInstancesWithHttpMessagesAsync`.</span></span>

1. <span data-ttu-id="6c9e8-181">Visticamāk, atbilde būs `object` veidā, jo šī metode var atgriezt vairākus tipus (piemēram, `IList<InstanceInfo>` un `ApiErrorResult`).</span><span class="sxs-lookup"><span data-stu-id="6c9e8-181">The response will likely be of type `object` because the method can return multiple types (for example, `IList<InstanceInfo>` and `ApiErrorResult`).</span></span> <span data-ttu-id="6c9e8-182">Lai pārbaudītu atgriešanas tipu, varat droši ielikt objektus to atbilžu tipos, kas ir norādītas [API detalizētās informācijas lapā](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights), kas paredzēta šai operācijai.</span><span class="sxs-lookup"><span data-stu-id="6c9e8-182">To check the return type, you can safely cast the objects into the response types specified on the [API details page](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) for that operation.</span></span>    
   <span data-ttu-id="6c9e8-183">Ja ir nepieciešama papildu informācija par pieprasījumu, izmantojiet **http ziņojumu metodes**, lai piekļūtu neapstrādātam atbildes objektam.</span><span class="sxs-lookup"><span data-stu-id="6c9e8-183">If more information on the request is needed, use the **http message methods** to access the raw response object.</span></span>

### <a name="nodejs-package"></a><span data-ttu-id="6c9e8-184">NodeJS pakotne</span><span class="sxs-lookup"><span data-stu-id="6c9e8-184">NodeJS package</span></span>

<span data-ttu-id="6c9e8-185">Izmantojiet NodeJS klientu bibliotēkas, kas ir pieejamas, izmantojot NPM: https://www.npmjs.com/package/@microsoft/customerinsights</span><span class="sxs-lookup"><span data-stu-id="6c9e8-185">Use the NodeJS client libraries available through NPM: https://www.npmjs.com/package/@microsoft/customerinsights</span></span>

### <a name="python-package"></a><span data-ttu-id="6c9e8-186">Python pakotne</span><span class="sxs-lookup"><span data-stu-id="6c9e8-186">Python package</span></span>

<span data-ttu-id="6c9e8-187">Izmantojiet Python klientu bibliotēkas, kas ir pieejamas, izmantojot PyPi: https://pypi.org/project/customerinsights/</span><span class="sxs-lookup"><span data-stu-id="6c9e8-187">Use the Python client libraries available through PyPi: https://pypi.org/project/customerinsights/</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
