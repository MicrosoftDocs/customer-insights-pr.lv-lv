---
title: Darbs ar API
description: Izmantojiet API un izprotiet ierobežojumus.
ms.date: 03/10/2021
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 011fa700563c53534554a6b73e87c2391bfdf714
ms.sourcegitcommit: a872f59e6febe4d4bd678ddd0b60a1660acca0f3
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 03/24/2021
ms.locfileid: "5710469"
---
# <a name="work-with-customer-insights-apis"></a>Darbs ar API Customer Insights

Dynamics 365 Customer Insights nodrošina API iespēju veidot savas lietojumprogrammas, pamatojoties uz Customer Insights datiem.

> [!IMPORTANT]
> Detalizēta informācija par šiem API ir iekļauta [atsaucē API Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). Tajos ir iekļauta papildinformācija par operācijām, parametriem un atbildēm.

Šajā rakstā ir norādīts, kā varat piekļūt API Customer Insights, izveidot reģistrāciju Azure programmā un palīdzēt iepazīties ar pieejamajām klientu bibliotēkām.

## <a name="get-started-trying-the-customer-insights-apis"></a>Darba sākšana ar API Customer Insights

1. [Pierakstieties](https://home.ci.ai.dynamics.com) risinājumā Customer Insights . Ja jums vēl nav abonementa, [pierakstieties Customer Insights izmēģinājumversijai](https://aka.ms/tryci).

1. Lai iespējotu API Customer Insights vidē, apmeklējiet **Administrators** > **Atļaujas**. Lai to izdarītu, jums ir nepieciešamas administratora atļaujas.

1. Atveriet **API** cilni un atlasiet pogu **Iespējot**.    
   Iespējojot API, tiek izveidota primārā un sekundārā abonēšanas atslēga jūsu instancei, kas tiek izmantota API pieprasījumos. Varat atkārtoti ģenerēt atslēgas, atlasot opciju **Atjaunot primāro** vai **Atjaunot sekundāro** sadaļā **Administrators** > **Atļaujas** > **API**.

   :::image type="content" source="media/enable-apis.gif" alt-text="Iespējot API Customer Insights":::

1. Atlasiet **Izpētīt mūsu API**, lai [izmēģinātu API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).

1. Izvēlieties API darbību un atlasiet **Izmēģināt to**.

1. Sānu rūtī iestatiet nolaižamās izvēlnes **Autorizācija** vērtību uz **Netiešs**. Virsrakstam `Authorization` ir pievienots nesēja marķieris. Jūsu abonementa atslēga tiek automātiski pārnesta.
  
1. Ja vēlaties, pievienojiet visus nepieciešamos vaicājuma parametrus.

1. Ritiniet uz sānu rūts lejasdaļu un atlasiet vienumu **Nosūtīt**.

HTTP atbilde drīz būs redzama tālāk.


   :::image type="content" source="media/try-apis.gif" alt-text="Animēts GIF attēls, kurā parādīts, kā atlasīt API testēšanu.":::

## <a name="create-a-new-app-registration-in-the-azure-portal"></a>Jaunas programmas reģistrēšanas izveide Azure portālā

Šīs darbības palīdz iepazīties ar API Customer Insights lietojumprogrammā Azure, izmantojot deleģētās atļaujas. Vispirms pārliecinieties, vai esat pabeidzis [sadaļu Darba sākšana](#get-started-trying-the-customer-insights-apis).

1. Pierakstieties [Azure portālā](https://portal.azure.com) ar kontu, kas var piekļūt Customer Insights datiem.

1. Pa kreisi atlasiet **Programmu reģistrācijas**.

1. Atlasiet **Jauna reģistrācija**, norādiet lietojumprogrammas nosaukumu un izvēlieties konta veidu.
   Ja nepieciešams, pievienojiet novirzīšanas URL. Ar http://localhost pietiek, lai izstrādātu lietojumprogrammu jūsu lokālajā datorā.

1. Jaunās programmas reģistrācijā ejiet uz **API atļaujas**.

   :::image type="content" source="media/app-registration-1.gif" alt-text="Animēts GIF attēls, lai iestatītu API atļauju programmas reģistrācijā.":::

1. Atlasiet **Pievienot atļauju** un atlasiet sānu rūtī **Customer Insights**.

1. **Atļauju tipam** atlasiet **Deleģētās atļaujas** un atlasiet atļauju **Lietotāja personificēšana**.

1. Atlasiet **Pievienot atļaujas**. Ja nepieciešams piekļūt API, neveicot lietotāja pieteikšanos, skatiet sadaļu [Servera-servera lietojumprogrammu atļaujas](#server-to-server-application-permissions).

1. Atlasiet **Piešķirt administratora piekrišanu...**, lai pabeigtu programmas reģistrāciju.

Varat izmantot šīs programmas reģistrēšanas lietojumprogrammas/klienta ID Microsoft autentifikācijas bibliotēkā (MSAL), lai iegūtu nesēja marķieri, kas jānosūta kopā ar jūsu pieprasījumu API.

:::image type="content" source="media/grant-admin-consent.gif" alt-text="Animēts GIF attēls, lai piešķirtu administratora piekrišanu.":::

Papildinformāciju par MSAL skatiet rakstā [Microsoft autentifikācijas bibliotēkas pārskats (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview).

Lai iegūtu papildinformāciju par lietojumprogrammas reģistrēšanu pakalpojumā Azure, skatiet [Jauno Azure portāla programmas reģistrācijas pieredzi](/azure/active-directory/develop/app-registration-portal-training-guide).

Informāciju par API izmantošanu mūsu klientu bibliotēkās skatiet sadaļā [Customer Insights klientu bibliotēkas](#customer-insights-client-libraries).

### <a name="server-to-server-application-permissions"></a>Servera-servera lietojumprogrammas atļaujas

Sadaļa [Lietojumprogrammas reģistrācijas](#create-a-new-app-registration-in-the-azure-portal) ieskicē, kā reģistrēt programmu, kas liek lietotājam pieteikties autentifikācijai. Uzziniet, kā izveidot programmas reģistrāciju, kurai nav nepieciešama lietotāja mijiedarbība, un ko var palaist serverī.

1. Ejiet uz **API permissions** jūsu programmas reģistrācijas Azure portālā.

1. Atlasiet **Pievienot atļauju** un atlasiet sānu rūtī **Customer Insights**.

1. **Atļauju tipam** atlasiet **Deleģētās atļaujas** un atlasiet atļauju **CustomerInsights.Api.All**.

1. Atlasiet **Pievienot atļaujas**.

1. Lai šai lietojumprogrammai atļaujai piešķirtu administratora piekrišanu, ir jāpievieno pakalpojuma primārais nosaukums.

   1. Instalējiet Azure Active Directory (AD) PowerShell moduli: `Install-Module -Name AzureAD -AllowClobber -Scope AllUsers`
   1. Izveidot savienojumu ar jūsu AD kontu: `Connect-AzureAD -TenantId <your tenant id>`. Savu nomnieka ID varat atrast sadaļā **Pārskats** > **Azure Active Directory**.
   1. Izpildiet tālāk norādīto komandu, lai pievienotu Azure AD servisa primāro nosaukumu: `New-AzureADServicePrincipal -AppId "38c77d00-5fcb-4cce-9d93-af4738258e3c" -DisplayName "Microsoft Dynamics 365 Customer Insights"` AppId parametrs attiecas uz programmu API Customer Insights.

   :::image type="content" source="media/azureAD-service-principal.png" alt-text="pakalpojuma primārais paraugs":::

1. Atgriezieties **API atļaujas**, lai reģistrētu savu lietojumprogrammu.

1. Atlasiet **Piešķirt administratora piekrišanu...**, lai pabeigtu programmas reģistrāciju.

   :::image type="content" source="media/grant-admin-consent.gif" alt-text="Animēts GIF attēls, lai piešķirtu administratora piekrišanu.":::

1. Lai to izdarītu, ir jāpievieno lietojumprogrammas reģistrācijas nosaukums kā lietotājs Customer Insights.    
   Atveriet sadaļu Customer Insights, atveriet **Administrators** > **Atļaujas** un atlasiet vienumu **Pievienot lietotāju**.

1. Meklējiet savas programmas reģistrācijas nosaukumu, meklēšanas rezultātos atlasiet to un atlasiet vienumu **Saglabāt**.

## <a name="customer-insights-client-libraries"></a>Customer Insights klientu bibliotēkas

Šī sadaļa palīdz sākt darbu ar API Customer Insights, izmantojot pieejamās klientu bibliotēkas. Viss bibliotēkas avota kods un programmu paraugi ir atrodami [Customer Insights GitHub lapā](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries). 

### <a name="c-nuget"></a>C# NuGet

Uzziniet, kā sākt lietot C# klienta bibliotēkas no NuGet.org. Papildinformāciju par NuGet pakotni skatiet [Microsoft.Dynamics.CustomerInsights.API](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/). Pašlaik šī pakotne tiek aptver uz netstandard 2.0 un netcoreapp 2.0 ietvarus.

#### <a name="add-the-c-client-library-to-a-c-project"></a>Pievienot C# klienta bibliotēku C# projektam

1. Rīkā Visual Studio atveriet jūsu projekta **NuGet pakotņu pārvaldnieku**.

1. Meklējiet **Microsoft.Dynamics.CustomerInsights.API**.

1. Atlasiet **Instalēt**, lai projektam pievienotu pakotni.
   Vai arī izpildiet šo komandu, kas atrodas **NuGet pakotņu pārvaldnieka konsolē**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`

   :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Pievienot NuGet pakotni projektam Visual Studio":::

#### <a name="use-the-c-client-library"></a>Izmantojiet C# klienta bibliotēku

1. Izmantojiet [Microsoft autentifikācijas bibliotēku (MSAL)](/azure/active-directory/develop/msal-overview), lai iegūtu `AccessToken`, izmantojot esošo [Azure programmu reģistrāciju](#create-a-new-app-registration-in-the-azure-portal).

1. Pēc sekmīgas autentificēšanās un marķiera iegādes izbūvējiet jaunu vai izmantojiet esošu `HttpClient` ar papildu **DefaultRequestHeaders "Autorizāciju"**, kas iestatīta kā **<access token>nesējs** un **Ocp-Apim-abonementa atslēga**, kas iestatīta uz [**abonementa atslēgu** no vides Customer Insights](#get-started-trying-the-customer-insights-apis).    
   Ja nepieciešams, atiestatiet galveni **Autorizācija**. Piemēram, ja ir izbeidzies marķieris.

1. Nododiet to `HttpClient`, veidojot `CustomerInsights` klientu.

   :::image type="content" source="media/httpclient-sample.png" alt-text="Httpclient paraugs":::

1. Piemēram, veiciet zvanus ar klientu uz "paplašinājuma metodēm" `GetAllInstancesAsync`. Ja ir vēlama piekļuve pamatdatiem `Microsoft.Rest.HttpOperationResponse`, izmantojiet, piemēram, "http ziņojumu metodes" `GetAllInstancesWithHttpMessagesAsync`.

1. Visticamāk, atbilde būs `object` veidā, jo šī metode var atgriezt vairākus tipus (piemēram, `IList<InstanceInfo>` un `ApiErrorResult`). Lai pārbaudītu atgriešanas tipu, varat droši ielikt objektus to atbilžu tipos, kas ir norādītas [API detalizētās informācijas lapā](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights), kas paredzēta šai operācijai.    
   Ja ir nepieciešama papildu informācija par pieprasījumu, izmantojiet **http ziņojumu metodes**, lai piekļūtu neapstrādātam atbildes objektam.

### <a name="nodejs-package"></a>NodeJS pakotne

Izmantojiet NodeJS klientu bibliotēkas, kas ir pieejamas, izmantojot NPM: https://www.npmjs.com/package/@microsoft/customerinsights

### <a name="python-package"></a>Python pakotne

Izmantojiet Python klientu bibliotēkas, kas ir pieejamas, izmantojot PyPi: https://pypi.org/project/customerinsights/

[!INCLUDE[footer-include](../includes/footer-banner.md)]
