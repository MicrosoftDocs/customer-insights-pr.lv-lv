---
title: Darbs ar API
description: Izmantojiet API un izprotiet ierobežojumus.
ms.date: 05/10/2021
ms.reviewer: wimohabb
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
searchScope:
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: 9a04276f7326533cd389cba6554f468123463bac
ms.sourcegitcommit: bf65bc0a54cdab71680e658e1617bee7b2c2bb68
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 05/27/2022
ms.locfileid: "8808515"
---
# <a name="work-with-customer-insights-apis"></a>Darbs ar API Customer Insights

Dynamics 365 Customer Insights nodrošina API, lai būvētu savas lietojumprogrammas, pamatojoties uz jūsu datiem programmā Customer Insights.

> [!IMPORTANT]
> Detalizēta informācija par šiem API ir iekļauta [atsaucē API Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). Tajos ir iekļauta papildinformācija par operācijām, parametriem un atbildēm.

Šajā rakstā ir aprakstīts, kā piekļūt Customer Insights API, izveidot Azure lietotnes reģistrāciju un sākt darbu ar klientu bibliotēkām.

## <a name="get-started-trying-the-customer-insights-apis"></a>Darba sākšana ar API Customer Insights

1. [Pierakstieties](https://home.ci.ai.dynamics.com) risinājumā Customer Insights . Ja jums vēl nav abonementa, [pierakstieties Customer Insights izmēģinājumversijai](https://aka.ms/tryci).

1. Lai iespējotu API klientu ieskatu vidē, dodieties uz **Administrēšanas** > **drošība**. Lai to izdarītu, jums ir nepieciešamas administratora atļaujas.

1. Atveriet **API** cilni un atlasiet pogu **Iespējot**.    
 
   Iespējojot API, tiek izveidota primārā un sekundārā abonēšanas atslēga jūsu instancei, kas tiek izmantota API pieprasījumos. Atslēgas var atkārtoti ģenerēt, administratora drošības API atlasot **Ģenerēt primāro** vai **Ģenerēt sekundāro** **.** > **·** > **·**

<!--  :::image type="content" source="media/enable-apis.gif" alt-text="Enable Customer Insights APIs."::: -->

1. Atlasiet **Izpētīt mūsu API**, lai [izmēģinātu API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).

1. Izvēlieties API darbību un atlasiet **Izmēģināt to**.

1. Sānu rūts sadaļas **Autorizācija** nolaižamajā sarakstā iestatiet vērtību uz **netieša**. Šī `Authorization` galvene tiek pievienota ar nesēja pilnvaru. Jūsu abonementa atslēga tiek automātiski pārnesta.
  
1. Ja vēlaties, pievienojiet visus nepieciešamos vaicājuma parametrus.

1. Ritiniet uz sānu rūts lejasdaļu un atlasiet vienumu **Nosūtīt**.

HTTP atbilde drīz būs redzama tālāk.

<!--   :::image type="content" source="media/try-apis.gif" alt-text="How to test the APIs."::: -->

## <a name="create-a-new-app-registration-in-the-azure-portal"></a>Jaunas programmas reģistrēšanas izveide Azure portālā

Šīs darbības palīdz sākt darbu Customer Insights API Azure lietojumprogrammā, izmantojot deleģētās atļaujas. Noteikti vispirms pabeidziet [sadaļu Darba sākšana](#get-started-trying-the-customer-insights-apis).

1. Pierakstieties [Azure portālā](https://portal.azure.com) ar kontu, kas var piekļūt Customer Insights datiem.

1. Pa kreisi atlasiet **Programmu reģistrācijas**.

1. Atlasiet **Jauna reģistrācija**, norādiet lietojumprogrammas nosaukumu un izvēlieties konta veidu.

   Ja nepieciešams, pievienojiet novirzīšanas URL. Ar http://localhost pietiek, lai izstrādātu lietojumprogrammu jūsu lokālajā datorā.

1. Jaunās programmas reģistrācijā ejiet uz **API atļaujas**.

1. Atlasiet **Pievienot atļauju** un sānu rūtī atlasiet **Dynamics 365 AI for Customer Insights**.

1. Sadaļā **Atļaujas veids** atlasiet **Deleģētās atļaujas** un pēc tam atlasiet **lietotāja personificēšanas** atļauju.

1. Atlasiet **Pievienot atļaujas**. Ja nepieciešams piekļūt API, neveicot lietotāja pieteikšanos, skatiet sadaļu [Servera-servera lietojumprogrammu atļaujas](#server-to-server-application-permissions).

1. Atlasiet **Piešķirt administratora piekrišanu...**, lai pabeigtu programmas reģistrāciju.

Varat izmantot šīs programmas reģistrēšanas lietojumprogrammas/klienta ID Microsoft autentifikācijas bibliotēkā (MSAL), lai iegūtu nesēja marķieri, kas jānosūta kopā ar jūsu pieprasījumu API.

<!-- :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

Papildinformāciju par MSAL skatiet rakstā [Microsoft autentifikācijas bibliotēkas pārskats (MSAL)](/azure/active-directory/develop/msal-overview).

Papildinformāciju par programmas reģistrāciju Azure skatiet sadaļā [Lietojumprogrammas reģistrēšana](/graph/auth-register-app-v2).

Informāciju kā izmantot API, kas ir mūsu klientu bibliotēkās, skatiet sadaļā [Customer Insights klientu bibliotēkās](#customer-insights-client-libraries).

### <a name="server-to-server-application-permissions"></a>Servera-servera lietojumprogrammas atļaujas

Sadaļa [Lietojumprogrammas reģistrācijas](#create-a-new-app-registration-in-the-azure-portal) ieskicē, kā reģistrēt programmu, kas liek lietotājam pieteikties autentifikācijai. Uzziniet, kā izveidot programmas reģistrāciju, kurai nav nepieciešama lietotāja mijiedarbība un kuru var palaist serverī.

1. Ejiet uz **API permissions** jūsu programmas reģistrācijas Azure portālā.

1. Atlasiet **Pievienot atļauju**. 

1. Sarakstā atlasiet **Manas organizācijas lietotie API** un sarakstā izvēlieties **Dynamics 365 AI for Customer Insights**. 

1. Sadaļā **Atļaujas veids** atlasiet **Lietojumprogrammas atļaujas** un pēc tam atlasiet **CustomerInsights.Api.All** atļauju.

1. Atlasiet **Pievienot atļaujas**.

1. Atgriezieties **API atļaujas**, lai reģistrētu savu lietojumprogrammu.

1. Atlasiet **Piešķirt administratora piekrišanu...**, lai pabeigtu programmas reģistrāciju.

 <!--  :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

1. Lai to izdarītu, ir jāpievieno lietojumprogrammas reģistrācijas nosaukums kā lietotājs Customer Insights.  
   
   Atveriet Customer Insights, dodieties uz **Administrēšanas** > **drošība** un atlasiet **Pievienot lietotāju**.

1. Meklējiet savas programmas reģistrācijas nosaukumu, meklēšanas rezultātos atlasiet to un atlasiet vienumu **Saglabāt**.

## <a name="sample-queries"></a>Vaicājumu paraugi

Mēs esam izveidojuši īsu sarakstu ar OData paraugu vaicājumiem darbam ar API: [OData vaicājumu piemēri](odata-examples.md).

## <a name="customer-insights-client-libraries"></a>Customer Insights klientu bibliotēkas

Šī sadaļa palīdz sākt darbu ar API Customer Insights, izmantojot pieejamās klientu bibliotēkas. Viss bibliotēkas avota kods un programmu paraugi ir atrodami [Customer Insights GitHub lapā](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries). 

### <a name="c-nuget"></a>C# NuGet

Uzziniet, kā sākt lietot C# klienta bibliotēkas no NuGet.org. Papildinformāciju par NuGet pakotni skatiet [Microsoft.Dynamics.CustomerInsights.API](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/). Pašlaik šī pakotne tiek aptver uz netstandard 2.0 un netcoreapp 2.0 ietvarus.

#### <a name="add-the-c-client-library-to-a-c-project"></a>Pievienot C# klienta bibliotēku C# projektam

1. Rīkā Visual Studio atveriet jūsu projekta **NuGet pakotņu pārvaldnieku**.

1. Meklējiet **Microsoft.Dynamics.CustomerInsights.API**.

1. Atlasiet **Instalēt**, lai projektam pievienotu pakotni.
 
   Vai arī izpildiet šo komandu, kas atrodas **NuGet pakotņu pārvaldnieka konsolē**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`

 <!--  :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Add NuGet package to Visual Studio project."::: -->

#### <a name="use-the-c-client-library"></a>Izmantojiet C# klienta bibliotēku

1. Izmantojiet [Microsoft autentifikācijas bibliotēku (MSAL)](/azure/active-directory/develop/msal-overview), lai iegūtu `AccessToken`, izmantojot esošo [Azure programmu reģistrāciju](#create-a-new-app-registration-in-the-azure-portal).

1. Pēc veiksmīgas pilnvaras autentifikācijas un iegūšanas izveidojiet jaunu vai izmantojiet esošu `HttpClient`, **izmantojot DefaultRequestHeaders "Authorization"** iestatītu uz **Uzrādītāja "piekļuves marķieris"** un **Ocp-Apim-Subscription-Key**, kas iestatīts uz [**abonementa atslēgu** no jūsu Customer Insights vides](#get-started-trying-the-customer-insights-apis).   
 
   Ja nepieciešams, atiestatiet galveni **Autorizācija**. Piemēram, ja ir izbeidzies marķieris.

1. Nododiet to `HttpClient`, veidojot `CustomerInsights` klientu.

<!--   :::image type="content" source="media/httpclient-sample.png" alt-text="Sample of httpclient."::: -->

1. Piemēram, veiciet zvanus ar klientu uz “paplašinājuma metodēm” – `GetAllInstancesAsync`. Ja ir vēlama piekļuve pamatdatiem `Microsoft.Rest.HttpOperationResponse`, izmantojiet, piemēram, “http ziņojumu metodes” – `GetAllInstancesWithHttpMessagesAsync`.

1. Visticamāk, atbilde būs `object` veidā, jo šī metode var atgriezt vairākus tipus (piemēram, `IList<InstanceInfo>` un `ApiErrorResult`). Lai pārbaudītu atgriešanas tipu, šai operācijai izmantojat objektus atbilžu tipos [, kas norādīti lapā](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) API detaļas.    
   
   Ja ir nepieciešama papildu informācija par pieprasījumu, izmantojiet **http ziņojumu metodes**, lai piekļūtu neapstrādātam atbildes objektam.

### <a name="nodejs-package"></a>NodeJS pakotne

Izmantojiet NodeJS klientu bibliotēkas, kas ir pieejamas, izmantojot NPM: https://www.npmjs.com/package/@microsoft/customerinsights

### <a name="python-package"></a>Python pakotne

Izmantojiet Python klientu bibliotēkas, kas ir pieejamas, izmantojot PyPi: https://pypi.org/project/customerinsights/

[!INCLUDE [footer-include](includes/footer-banner.md)]
