---
title: Darbs ar API
description: Izmantojiet API un izprotiet ierobežojumus.
ms.date: 12/04/2020
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 5a03e916676800afdd8692da865a1060952d5c4f
ms.sourcegitcommit: b50c754481d0af6d0cf4b550775d7b31d95846ef
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 12/06/2020
ms.locfileid: "4689139"
---
# <a name="work-with-customer-insights-apis"></a><span data-ttu-id="8947b-103">Darbs ar API Customer Insights</span><span class="sxs-lookup"><span data-stu-id="8947b-103">Work with Customer Insights APIs</span></span>

<span data-ttu-id="8947b-104">Dynamics 365 Customer Insights nodrošina API iespēju veidot savas lietojumprogrammas, pamatojoties uz Customer Insights datiem.</span><span class="sxs-lookup"><span data-stu-id="8947b-104">Dynamics 365 Customer Insights provides APIs to build your own applications based you data in Customer Insights.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8947b-105">Detalizēta informācija par šiem API ir iekļauta [atsaucē API Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span><span class="sxs-lookup"><span data-stu-id="8947b-105">Details of these APIs, are listed on the [Customer Insights APIs reference](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span></span> <span data-ttu-id="8947b-106">Tajos ir iekļauta papildinformācija par operācijām, parametriem un atbildēm.</span><span class="sxs-lookup"><span data-stu-id="8947b-106">They include additional information about operations, parameters, and responses.</span></span>

<span data-ttu-id="8947b-107">Šajā rakstā ir norādīts, kā varat piekļūt API Customer Insights, izveidot reģistrāciju Azure programmā un palīdzēt iepazīties ar pieejamajām klientu bibliotēkām.</span><span class="sxs-lookup"><span data-stu-id="8947b-107">This article guides you to access to the Customer Insights APIs, create an Azure App Registration, and help you get started with the available client libraries.</span></span>

## <a name="get-started-trying-the-customer-insights-apis"></a><span data-ttu-id="8947b-108">Darba sākšana ar API Customer Insights</span><span class="sxs-lookup"><span data-stu-id="8947b-108">Get started trying the Customer Insights APIs</span></span>

1. <span data-ttu-id="8947b-109">[Pierakstieties](https://home.ci.ai.dynamics.com) risinājumā Customer Insights .</span><span class="sxs-lookup"><span data-stu-id="8947b-109">[Sign in](https://home.ci.ai.dynamics.com) to Customer Insights.</span></span> <span data-ttu-id="8947b-110">Ja jums vēl nav abonementa, [pierakstieties Customer Insights izmēģinājumversijai](https://aka.ms/tryci).</span><span class="sxs-lookup"><span data-stu-id="8947b-110">If you don't have a subscription yet, [sign up for a trial of Customer Insights](https://aka.ms/tryci).</span></span>

1. <span data-ttu-id="8947b-111">Lai iespējotu API Customer Insights vidē, apmeklējiet **Administrators** > **Atļaujas**.</span><span class="sxs-lookup"><span data-stu-id="8947b-111">To enable APIs on your Customer Insights environment, go to **Admin** > **Permissions**.</span></span> <span data-ttu-id="8947b-112">Lai to izdarītu, jums ir nepieciešamas administratora atļaujas.</span><span class="sxs-lookup"><span data-stu-id="8947b-112">You'll need admin permissions to do so.</span></span>

1. <span data-ttu-id="8947b-113">Atveriet **API** cilni un atlasiet pogu **Iespējot**.</span><span class="sxs-lookup"><span data-stu-id="8947b-113">Go to the **APIs** tab and select the **Enable** button.</span></span>    
   <span data-ttu-id="8947b-114">Iespējojot API, tiek izveidota primārā un sekundārā abonēšanas atslēga jūsu instancei, kas tiek izmantota API pieprasījumos.</span><span class="sxs-lookup"><span data-stu-id="8947b-114">Enabling the APIs creates a primary and secondary subscription key for your instance that gets used in the API requests.</span></span> <span data-ttu-id="8947b-115">Varat atkārtoti ģenerēt atslēgas, atlasot opciju **Atjaunot primāro** vai **Atjaunot sekundāro** sadaļā **Administrators** > **Atļaujas** > **API**.</span><span class="sxs-lookup"><span data-stu-id="8947b-115">You can regenerate the keys by selecting the **Regenerate primary** or **Regenerate secondary** on **Admin** > **Permissions** > **APIs**.</span></span>

   :::image type="content" source="media/enable-apis.gif" alt-text="Iespējot API Customer Insights":::

1. <span data-ttu-id="8947b-117">Atlasiet **Izpētīt mūsu API**, lai izmēģinātu API.</span><span class="sxs-lookup"><span data-stu-id="8947b-117">Select **Explore our APIs** to try out the APIs.</span></span>

1. <span data-ttu-id="8947b-118">Izvēlieties API darbību un atlasiet **Izmēģināt to**.</span><span class="sxs-lookup"><span data-stu-id="8947b-118">Choose an API operation and select **Try it**.</span></span>

1. <span data-ttu-id="8947b-119">Sānu rūtī iestatiet nolaižamās izvēlnes **Autorizācija** vērtību uz **Netiešs**.</span><span class="sxs-lookup"><span data-stu-id="8947b-119">In the side pane, set the value in the **Authorization** drop-down menu to **implicit**.</span></span> <span data-ttu-id="8947b-120">Virsrakstam `Authorization` ir pievienots nesēja marķieris.</span><span class="sxs-lookup"><span data-stu-id="8947b-120">The `Authorization` header gets with a bearer token added.</span></span> <span data-ttu-id="8947b-121">Jūsu abonementa atslēga tiek automātiski pārnesta.</span><span class="sxs-lookup"><span data-stu-id="8947b-121">Your subscription key will be automatically populated.</span></span>
  
1. <span data-ttu-id="8947b-122">Ja vēlaties, pievienojiet visus nepieciešamos vaicājuma parametrus.</span><span class="sxs-lookup"><span data-stu-id="8947b-122">Optionally, add all necessary query parameters.</span></span>

1. <span data-ttu-id="8947b-123">Ritiniet uz sānu rūts lejasdaļu un atlasiet vienumu **Nosūtīt**.</span><span class="sxs-lookup"><span data-stu-id="8947b-123">Scroll to the bottom of the side pane and select **Send**.</span></span>

<span data-ttu-id="8947b-124">HTTP atbilde drīz būs redzama tālāk.</span><span class="sxs-lookup"><span data-stu-id="8947b-124">The HTTP response will soon appear below.</span></span>

## <a name="create-a-new-app-registration-in-the-azure-portal"></a><span data-ttu-id="8947b-125">Jaunas programmas reģistrēšanas izveide Azure portālā</span><span class="sxs-lookup"><span data-stu-id="8947b-125">Create a new app registration in the Azure portal</span></span>

<span data-ttu-id="8947b-126">Šīs darbības palīdz iepazīties ar API Customer Insights lietojumprogrammā Azure, izmantojot deleģētās atļaujas.</span><span class="sxs-lookup"><span data-stu-id="8947b-126">These steps help you get started in using the Customer Insights APIs in an Azure application using delegated permissions.</span></span> <span data-ttu-id="8947b-127">Vispirms pārliecinieties, vai esat pabeidzis [sadaļu Darba sākšana](#get-started-trying-the-customer-insights-apis).</span><span class="sxs-lookup"><span data-stu-id="8947b-127">Make sure to have completed [Getting started section](#get-started-trying-the-customer-insights-apis) first.</span></span>

1. <span data-ttu-id="8947b-128">Pierakstieties [Azure portālā](https://portal.azure.com) ar kontu, kas var piekļūt Customer Insights datiem.</span><span class="sxs-lookup"><span data-stu-id="8947b-128">Sign in to the [Azure portal](https://portal.azure.com) with the account that can access the Customer Insights data.</span></span>

1. <span data-ttu-id="8947b-129">Pa kreisi atlasiet **Programmu reģistrācijas**.</span><span class="sxs-lookup"><span data-stu-id="8947b-129">On the left, select **App registrations**.</span></span>

1. <span data-ttu-id="8947b-130">Atlasiet **Jauna reģistrācija**, norādiet lietojumprogrammas nosaukumu un izvēlieties konta veidu.</span><span class="sxs-lookup"><span data-stu-id="8947b-130">Select **New registration** provide an application name and choose the account type.</span></span>
   <span data-ttu-id="8947b-131">Ja nepieciešams, pievienojiet novirzīšanas URL.</span><span class="sxs-lookup"><span data-stu-id="8947b-131">Optionally, add a redirect URL.</span></span> <span data-ttu-id="8947b-132">Ar http://localhost pietiek, lai izstrādātu lietojumprogrammu jūsu lokālajā datorā.</span><span class="sxs-lookup"><span data-stu-id="8947b-132">http://localhost is sufficient for developing an application on your local computer.</span></span>

1. <span data-ttu-id="8947b-133">Jaunās programmas reģistrācijā ejiet uz **API atļaujas**.</span><span class="sxs-lookup"><span data-stu-id="8947b-133">On your new App registration, go to **API permissions**.</span></span>

1. <span data-ttu-id="8947b-134">Atlasiet **Pievienot atļauju** un atlasiet sānu rūtī **Customer Insights**.</span><span class="sxs-lookup"><span data-stu-id="8947b-134">Select **Add a permission** and select **Customer Insights** in the side pane.</span></span>

1. <span data-ttu-id="8947b-135">**Atļauju tipam** atlasiet **Deleģētās atļaujas** un atlasiet atļauju **Lietotāja personificēšana**.</span><span class="sxs-lookup"><span data-stu-id="8947b-135">For **Permission type**, select **Delegated permissions** and select the **user_impersonation** permission.</span></span>

1. <span data-ttu-id="8947b-136">Atlasiet **Pievienot atļaujas**.</span><span class="sxs-lookup"><span data-stu-id="8947b-136">Select **Add permissions**.</span></span> <span data-ttu-id="8947b-137">Ja nepieciešams piekļūt API, neveicot lietotāja pieteikšanos, skatiet sadaļu [Servera-servera lietojumprogrammu atļaujas](#server-to-server-application-permissions).</span><span class="sxs-lookup"><span data-stu-id="8947b-137">If you need to access the API without a user signing in, review the [Server-to-server application permissions](#server-to-server-application-permissions) section.</span></span>

1. <span data-ttu-id="8947b-138">Atlasiet **Piešķirt administratora piekrišanu...**, lai pabeigtu programmas reģistrāciju.</span><span class="sxs-lookup"><span data-stu-id="8947b-138">Select **Grant admin consent for...** to complete the app registration.</span></span>

<span data-ttu-id="8947b-139">Varat izmantot šīs programmas reģistrēšanas lietojumprogrammas/klienta ID Microsoft autentifikācijas bibliotēkā (MSAL), lai iegūtu nesēja marķieri, kas jānosūta kopā ar jūsu pieprasījumu API.</span><span class="sxs-lookup"><span data-stu-id="8947b-139">You can use the Application/Client ID for this app registration with the Microsoft Authentication Library (MSAL) to obtain a bearer token to send with your request to the API.</span></span>

<span data-ttu-id="8947b-140">Papildinformāciju par MSAL skatiet rakstā [Microsoft autentifikācijas bibliotēkas pārskats (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview).</span><span class="sxs-lookup"><span data-stu-id="8947b-140">For more information about MSAL, see [Overview of Microsoft Authentication Library (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview).</span></span>

<span data-ttu-id="8947b-141">Lai iegūtu papildinformāciju par lietojumprogrammas reģistrēšanu pakalpojumā Azure, skatiet [Jauno Azure portāla programmas reģistrācijas pieredzi](https://docs.microsoft.com/azure/active-directory/develop/app-registration-portal-training-guide).</span><span class="sxs-lookup"><span data-stu-id="8947b-141">For more information about app registration in Azure, see [The new Azure portal app registration experience](https://docs.microsoft.com/azure/active-directory/develop/app-registration-portal-training-guide).</span></span>

<span data-ttu-id="8947b-142">Informāciju par API izmantošanu mūsu klientu bibliotēkās skatiet sadaļā [Customer Insights klientu bibliotēkas](#customer-insights-client-libraries).</span><span class="sxs-lookup"><span data-stu-id="8947b-142">For information on using the APIs our client libraries, see [Customer Insights client libraries](#customer-insights-client-libraries).</span></span>

### <a name="server-to-server-application-permissions"></a><span data-ttu-id="8947b-143">Servera-servera lietojumprogrammas atļaujas</span><span class="sxs-lookup"><span data-stu-id="8947b-143">Server-to-server application permissions</span></span>

<span data-ttu-id="8947b-144">Sadaļa [Lietojumprogrammas reģistrācijas](#create-a-new-app-registration-in-the-azure-portal) ieskicē, kā reģistrēt programmu, kas liek lietotājam pieteikties autentifikācijai.</span><span class="sxs-lookup"><span data-stu-id="8947b-144">The [app registration section](#create-a-new-app-registration-in-the-azure-portal) outlines how to register an app that requires a user to sign in for authentication.</span></span> <span data-ttu-id="8947b-145">Uzziniet, kā izveidot programmas reģistrāciju, kurai nav nepieciešama lietotāja mijiedarbība, un ko var palaist serverī.</span><span class="sxs-lookup"><span data-stu-id="8947b-145">Learn how to create an app registration that does not need user interaction and can be run on a server.</span></span>

1. <span data-ttu-id="8947b-146">Ejiet uz **API permissions** jūsu programmas reģistrācijas Azure portālā.</span><span class="sxs-lookup"><span data-stu-id="8947b-146">On your App registration in the Azure portal, go to **API permissions**.</span></span>

1. <span data-ttu-id="8947b-147">Atlasiet **Pievienot atļauju** un atlasiet sānu rūtī **Customer Insights**.</span><span class="sxs-lookup"><span data-stu-id="8947b-147">Select **Add a permission** and select **Customer Insights** in the side pane.</span></span>

1. <span data-ttu-id="8947b-148">**Atļauju tipam** atlasiet **Deleģētās atļaujas** un atlasiet atļauju **CustomerInsights.Api.All**.</span><span class="sxs-lookup"><span data-stu-id="8947b-148">For **Permission type**, select **Application permissions** and select the **CustomerInsights.Api.All** permission.</span></span>

1. <span data-ttu-id="8947b-149">Atlasiet **Pievienot atļaujas**.</span><span class="sxs-lookup"><span data-stu-id="8947b-149">Select **Add permissions**.</span></span>

1. <span data-ttu-id="8947b-150">Lai šai lietojumprogrammai atļaujai piešķirtu administratora piekrišanu, ir jāpievieno pakalpojuma primārais nosaukums.</span><span class="sxs-lookup"><span data-stu-id="8947b-150">To give admin consent on this Application permission, you need to add a Service Principal.</span></span>

   1. <span data-ttu-id="8947b-151">Instalējiet Azure Active Directory (AD) PowerShell moduli: `Install-Module -Name AzureAD -AllowClobber -Scope AllUsers`</span><span class="sxs-lookup"><span data-stu-id="8947b-151">Install the Azure Active Directory (AD) PowerShell module: `Install-Module -Name AzureAD -AllowClobber -Scope AllUsers`</span></span>
   1. <span data-ttu-id="8947b-152">Izveidot savienojumu ar jūsu AD kontu: `Connect-AzureAD -TenantId <your tenant id>`.</span><span class="sxs-lookup"><span data-stu-id="8947b-152">Connect to your AD account: `Connect-AzureAD -TenantId <your tenant id>`.</span></span> <span data-ttu-id="8947b-153">Savu nomnieka ID varat atrast sadaļā **Pārskats** > **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="8947b-153">You can find your tenant ID on **Overview** > **Azure Active Directory**.</span></span>
   1. <span data-ttu-id="8947b-154">Izpildiet tālāk norādīto komandu, lai pievienotu Azure AD servisa primāro nosaukumu: `New-AzureADServicePrincipal -AppId "38c77d00-5fcb-4cce-9d93-af4738258e3c" -DisplayName "Microsoft Dynamics 365 Customer Insights"` AppId parametrs attiecas uz programmu API Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="8947b-154">Run the following command to add an Azure AD Service Principal: `New-AzureADServicePrincipal -AppId "38c77d00-5fcb-4cce-9d93-af4738258e3c" -DisplayName "Microsoft Dynamics 365 Customer Insights"` The AppId parameter pertains to the Customer Insights API app.</span></span>

   :::image type="content" source="media/azureAD-service-principal.png" alt-text="pakalpojuma primārais paraugs":::

1. <span data-ttu-id="8947b-156">Atgriezieties **API atļaujas**, lai reģistrētu savu lietojumprogrammu.</span><span class="sxs-lookup"><span data-stu-id="8947b-156">Go back to **API permissions** for your app registration.</span></span>

1. <span data-ttu-id="8947b-157">Atlasiet **Piešķirt administratora piekrišanu...**, lai pabeigtu programmas reģistrāciju.</span><span class="sxs-lookup"><span data-stu-id="8947b-157">Select **Grant admin consent for...** to complete the app registration.</span></span>

1. <span data-ttu-id="8947b-158">Lai to izdarītu, ir jāpievieno lietojumprogrammas reģistrācijas nosaukums kā lietotājs Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="8947b-158">To conclude, we have to add the name of the app registration as a user in Customer Insights.</span></span>    
   <span data-ttu-id="8947b-159">Atveriet sadaļu Customer Insights, atveriet **Administrators** > **Atļaujas** un atlasiet vienumu **Pievienot lietotāju**.</span><span class="sxs-lookup"><span data-stu-id="8947b-159">Open Customer Insights, go to **Admin** > **Permissions** and select **Add user**.</span></span>

1. <span data-ttu-id="8947b-160">Meklējiet savas programmas reģistrācijas nosaukumu, meklēšanas rezultātos atlasiet to un atlasiet vienumu **Saglabāt**.</span><span class="sxs-lookup"><span data-stu-id="8947b-160">Search for the name of your app registration, select it from the search results, and select **Save**.</span></span>

## <a name="customer-insights-client-libraries"></a><span data-ttu-id="8947b-161">Customer Insights klientu bibliotēkas</span><span class="sxs-lookup"><span data-stu-id="8947b-161">Customer Insights client libraries</span></span>

<span data-ttu-id="8947b-162">Šī sadaļa palīdz sākt darbu ar API Customer Insights, izmantojot pieejamās klientu bibliotēkas.</span><span class="sxs-lookup"><span data-stu-id="8947b-162">This section helps you get started using the client libraries available for the Customer Insights APIs.</span></span>

### <a name="c-nuget"></a><span data-ttu-id="8947b-163">C# NuGet</span><span class="sxs-lookup"><span data-stu-id="8947b-163">C# NuGet</span></span>

<span data-ttu-id="8947b-164">Uzziniet, kā sākt lietot C# klienta bibliotēkas no NuGet.org. Papildinformāciju par NuGet pakotni skatiet [Microsoft.Dynamics.CustomerInsights.API](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).</span><span class="sxs-lookup"><span data-stu-id="8947b-164">Learn how to get started using the C# client libraries from NuGet.org. For more information on the NuGet package, see [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).</span></span> <span data-ttu-id="8947b-165">Pašlaik šī pakotne tiek aptver uz netstandard 2.0 un netcoreapp 2.0 ietvarus.</span><span class="sxs-lookup"><span data-stu-id="8947b-165">Currently, this package targets the netstandard2.0 and netcoreapp2.0 frameworks.</span></span>

#### <a name="add-the-c-client-library-to-a-c-project"></a><span data-ttu-id="8947b-166">Pievienot C# klienta bibliotēku C# projektam</span><span class="sxs-lookup"><span data-stu-id="8947b-166">Add the C# client library to a C# project</span></span>

1. <span data-ttu-id="8947b-167">Rīkā Visual Studio atveriet jūsu projekta **NuGet pakotņu pārvaldnieku**.</span><span class="sxs-lookup"><span data-stu-id="8947b-167">In Visual Studio, open the **NuGet Package Manager** for your project.</span></span>

1. <span data-ttu-id="8947b-168">Meklējiet **Microsoft.Dynamics.CustomerInsights.API**.</span><span class="sxs-lookup"><span data-stu-id="8947b-168">Search for **Microsoft.Dynamics.CustomerInsights.Api**.</span></span>

1. <span data-ttu-id="8947b-169">Atlasiet **Instalēt**, lai projektam pievienotu pakotni.</span><span class="sxs-lookup"><span data-stu-id="8947b-169">Select **Install** to add the package to the project.</span></span>
   <span data-ttu-id="8947b-170">Vai arī izpildiet šo komandu, kas atrodas **NuGet pakotņu pārvaldnieka konsolē**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span><span class="sxs-lookup"><span data-stu-id="8947b-170">Alternatively, run this command in the **NuGet Package Manager Console**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span></span>

   :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Pievienot NuGet pakotni projektam Visual Studio":::

#### <a name="use-the-c-client-library"></a><span data-ttu-id="8947b-172">Izmantojiet C# klienta bibliotēku</span><span class="sxs-lookup"><span data-stu-id="8947b-172">Use the C# client library</span></span>

1. <span data-ttu-id="8947b-173">Izmantojiet [Microsoft autentifikācijas bibliotēku (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview), lai iegūtu `AccessToken`, izmantojot esošo [Azure programmu reģistrāciju](#create-a-new-app-registration-in-the-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="8947b-173">Use the [Microsoft Authentication Library (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview) to get an `AccessToken` using your existing [Azure app registration](#create-a-new-app-registration-in-the-azure-portal).</span></span>

1. <span data-ttu-id="8947b-174">Pēc sekmīgas autentificēšanās un marķiera iegādes izbūvējiet jaunu vai izmantojiet esošu `HttpClient` ar papildu **DefaultRequestHeaders "Autorizāciju"**, kas iestatīta kā **<access token>nesējs** un **Ocp-Apim-abonementa atslēga**, kas iestatīta uz [**abonementa atslēgu** no vides Customer Insights](#get-started-trying-the-customer-insights-apis).</span><span class="sxs-lookup"><span data-stu-id="8947b-174">After successfully authenticating and acquiring a token, construct a new or use an existing `HttpClient` with the additional **DefaultRequestHeaders "Authorization"** set to **Bearer <access token>** and **Ocp-Apim-Subscription-Key** set to the [**subscription key** from your Customer Insights environment](#get-started-trying-the-customer-insights-apis).</span></span>    
   <span data-ttu-id="8947b-175">Ja nepieciešams, atiestatiet galveni **Autorizācija**.</span><span class="sxs-lookup"><span data-stu-id="8947b-175">Reset the **Authorization** header when appropriate.</span></span> <span data-ttu-id="8947b-176">Piemēram, ja ir izbeidzies marķieris.</span><span class="sxs-lookup"><span data-stu-id="8947b-176">For example, when the token expired.</span></span>

1. <span data-ttu-id="8947b-177">Nododiet to `HttpClient`, veidojot `CustomerInsights` klientu.</span><span class="sxs-lookup"><span data-stu-id="8947b-177">Pass this `HttpClient` into the construction of the `CustomerInsights` client.</span></span>

   :::image type="content" source="media/httpclient-sample.png" alt-text="Httpclient paraugs":::

1. <span data-ttu-id="8947b-179">Piemēram, veiciet zvanus ar klientu uz "paplašinājuma metodēm" `GetAllInstancesAsync`.</span><span class="sxs-lookup"><span data-stu-id="8947b-179">Make calls with the client to the "extension methods", for example, `GetAllInstancesAsync`.</span></span> <span data-ttu-id="8947b-180">Ja ir vēlama piekļuve pamatdatiem `Microsoft.Rest.HttpOperationResponse`, izmantojiet, piemēram, "http ziņojumu metodes" `GetAllInstancesWithHttpMessagesAsync`.</span><span class="sxs-lookup"><span data-stu-id="8947b-180">If access to the underlying `Microsoft.Rest.HttpOperationResponse` is preferred, use the "http message methods", for example `GetAllInstancesWithHttpMessagesAsync`.</span></span>

1. <span data-ttu-id="8947b-181">Visticamāk, atbilde būs `object` veidā, jo šī metode var atgriezt vairākus tipus (piemēram, `IList<InstanceInfo>` un `ApiErrorResult`).</span><span class="sxs-lookup"><span data-stu-id="8947b-181">The response will likely be of type `object` because the method can return multiple types (for example, `IList<InstanceInfo>` and `ApiErrorResult`).</span></span> <span data-ttu-id="8947b-182">Lai pārbaudītu atgriešanas tipu, varat droši ielikt objektus to atbilžu tipos, kas ir norādītas [API detalizētās informācijas lapā](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights), kas paredzēta šai operācijai.</span><span class="sxs-lookup"><span data-stu-id="8947b-182">To check the return type, you can safely cast the objects into the response types specified on the [API details page](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) for that operation.</span></span>    
   <span data-ttu-id="8947b-183">Ja ir nepieciešama papildu informācija par pieprasījumu, izmantojiet **http ziņojumu metodes**, lai piekļūtu neapstrādātam atbildes objektam.</span><span class="sxs-lookup"><span data-stu-id="8947b-183">If more information on the request is needed, use the **http message methods** to access the raw response object.</span></span>
