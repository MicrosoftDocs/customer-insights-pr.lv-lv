---
title: Darbs ar API Customer Insights
description: Izmantojiet API un izprotiet ierobežojumus.
ms.date: 08/31/2022
ms.reviewer: wimohabb
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
searchScope:
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: f499bff4a6ac07a88ff0f773b9cee77dc74989e8
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387349"
---
# <a name="work-with-customer-insights-apis"></a>Darbs ar API Customer Insights

Dynamics 365 Customer Insights nodrošina API, lai būvētu savas lietojumprogrammas, pamatojoties uz jūsu datiem programmā Customer Insights.

> [!IMPORTANT]
> Detalizēta informācija par šiem API ir iekļauta [atsaucē API Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). Tajos ir iekļauta papildinformācija par operācijām, parametriem un atbildēm.

Izmēģiniet Customer Insights API, izveidojiet Azure programmu reģistrāciju un sāciet darbu ar klientu bibliotēkām.

## <a name="get-started-trying-the-customer-insights-apis"></a>Darba sākšana ar API Customer Insights

Iespējojiet Customer Insights API un izmēģiniet tos. Customer Insights administratoram ir jāiespējo API piekļuve customer insights. Kad piekļuve ir iespējota, jebkurš lietotājs var izmantot API ar abonēšanas atslēgu.

1. [Pierakstieties](https://home.ci.ai.dynamics.com) risinājumā Customer Insights . Ja jums vēl nav abonementa, [pierakstieties Customer Insights izmēģinājumversijai](https://aka.ms/tryci).

1. Dodieties uz Administratora drošība un atlasiet **cilni API** > **.** **·**

1. Ja API piekļuve videi nav iestatīta, atlasiet **Iespējot**.

   Iespējojot API, tiek izveidota primārā un sekundārā abonēšanas atslēga jūsu instancei, kas tiek izmantota API pieprasījumos. Lai atkārtoti instalētu taustiņus, cilnē API atlasiet Atjaunot sekundāro **vai** Atjaunot **sekundāro**.**·**

1. Atlasiet [**Izpētīt mūsu API**](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances) , lai izmēģinātu API.

1. Meklējiet un atlasiet API darbību un atlasiet **Izmēģināt**.

   :::image type="content" source="media/try-api.png" alt-text="Kā pārbaudīt API.":::

1. Sānu rūts sadaļas **Autorizācija** nolaižamajā sarakstā iestatiet vērtību uz **netieša**. Šī `Authorization` galvene tiek pievienota ar nesēja pilnvaru. Jūsu abonementa atslēga tiek aizpildīta automātiski.
  
1. Ja vēlaties, pievienojiet visus nepieciešamos vaicājuma parametrus.

1. Ritiniet uz sānu rūts lejasdaļu un atlasiet vienumu **Nosūtīt**.

   HTTP atbilde tiek parādīta rūts apakšdaļā.

## <a name="create-a-new-app-registration-in-the-azure-portal"></a>Jaunas programmas reģistrēšanas izveide Azure portālā

Izveidojiet jaunu [programmas reģistrāciju](/graph/auth-register-app-v2) , lai izmantotu Customer Insights API Azure lietojumprogrammā, izmantojot deleģētās atļaujas.

1. Aizpildiet [sadaļu](#get-started-trying-the-customer-insights-apis) Darba sākšana.

1. Pierakstieties [Azure portālā](https://portal.azure.com) ar kontu, kas var piekļūt Customer Insights datiem.

1. Meklējiet un pēc tam atlasiet **Programmu reģistrācijas**.

1. Atlasiet **Jauna reģistrācija**, norādiet lietojumprogrammas nosaukumu un izvēlieties konta veidu.

   Ja nepieciešams, pievienojiet novirzīšanas URL. Ar http://localhost pietiek, lai izstrādātu lietojumprogrammu jūsu lokālajā datorā.

1. Atlasiet **Reģistrēt**.

1. Jaunās programmas reģistrācijā ejiet uz **API atļaujas**.

1. Atlasiet **Pievienot atļauju** un sānu rūtī atlasiet **Dynamics 365 AI for Customer Insights** .

1. Sadaļā **Atļaujas veids** atlasiet **Deleģētās atļaujas** un pēc tam atlasiet **lietotāja personificēšanas** atļauju.

1. Atlasiet **Pievienot atļaujas**.

1. Atlasiet **Piešķirt administratora piekrišanu...**, lai pabeigtu programmas reģistrāciju.

1. Lai piekļūtu API bez lietotāja pierakstīšanās, dodieties uz [lietojumprogrammu](#server-to-server-application-permissions) atļaujas no servera uz serveri.

Varat izmantot lietojumprogrammas/klienta ID šai programmas reģistrācijai [Microsoft autentifikācijas bibliotēkā (MSAL),](/azure/active-directory/develop/msal-overview) lai iegūtu uzrādītāja pilnvaru, ko kopā ar pieprasījumu nosūtīt API.

<!-- :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

Informāciju kā izmantot API, kas ir mūsu klientu bibliotēkās, skatiet sadaļā [Customer Insights klientu bibliotēkās](#customer-insights-client-libraries).

### <a name="server-to-server-application-permissions"></a>Servera-servera lietojumprogrammas atļaujas

Izveidojiet programmas reģistrāciju, kurai nav nepieciešama lietotāja mijiedarbība un kuru var palaist serverī.

1. Ejiet uz **API permissions** jūsu programmas reģistrācijas Azure portālā.

1. Atlasiet **Pievienot atļauju**.

1. Sarakstā atlasiet **Manas organizācijas lietotie API** un sarakstā izvēlieties **Dynamics 365 AI for Customer Insights**.

1. Sadaļā **Atļaujas veids** atlasiet **Lietojumprogrammas atļaujas** un pēc tam atlasiet **CustomerInsights.Api.All** atļauju.

1. Atlasiet **Pievienot atļaujas**.

1. Atgriezieties **API atļaujas**, lai reģistrētu savu lietojumprogrammu.

1. Atlasiet **Piešķirt administratora piekrišanu...**, lai pabeigtu programmas reģistrāciju.

   <!--  :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

1. Pievienojiet programmas kā lietotāja reģistrācijas nosaukumu programmā Customer Insights.

   1. Atveriet Customer Insights, dodieties uz **Administratora** > **drošība** un atlasiet **Pievienot lietotājus**.

   1. Meklējiet savas programmas reģistrācijas nosaukumu, meklēšanas rezultātos atlasiet to un atlasiet vienumu **Saglabāt**.

## <a name="sample-queries"></a>Vaicājumu paraugi

Īsu sarakstu ar OData vaicājumu paraugiem darbam ar API skatiet sadaļā [OData vaicājumu piemēri](odata-examples.md).

## <a name="customer-insights-client-libraries"></a>Customer Insights klientu bibliotēkas

Sāciet darbu ar klientu bibliotēkām, kas pieejamas Customer Insights API. Viss bibliotēkas avota kods un programmu paraugi ir atrodami [Customer Insights GitHub lapā](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries).

### <a name="c-nuget"></a>C# NuGet

Izmantojiet C# klientu bibliotēkas no NuGet.org. Pašlaik pakotnes mērķauditorija ir netstandard2.0 un netcoreapp2.0 ietvari. Papildinformāciju NuGet par pakotni skatiet rakstā [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).

#### <a name="add-the-c-client-library-to-a-c-project"></a>Pievienot C# klienta bibliotēku C# projektam

1. Rīkā Visual Studio atveriet jūsu projekta **NuGet pakotņu pārvaldnieku**.

1. Meklējiet **Microsoft.Dynamics.CustomerInsights.API**.

1. Atlasiet **Instalēt**, lai projektam pievienotu pakotni.

   Vai arī izpildiet šo komandu, kas atrodas **NuGet pakotņu pārvaldnieka konsolē**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`

   <!--  :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Add NuGet package to Visual Studio project."::: -->

#### <a name="use-the-c-client-library"></a>Izmantojiet C# klienta bibliotēku

1. Izmantojiet [Microsoft autentifikācijas bibliotēku (MSAL)](/azure/active-directory/develop/msal-overview), lai iegūtu `AccessToken`, izmantojot esošo [Azure programmu reģistrāciju](#create-a-new-app-registration-in-the-azure-portal).

1. Pēc veiksmīgas marķiera autentificēšanas un iegūšanas izveidojiet jaunu vai izmantojiet esošu `HttpClient` ar **DefaultRequestHeaders "Autorizāciju"**, kas iestatīta uz **Bearer "piekļuves pilnvara"** un **Ocp-Apim-Subscription-Key**, kas iestatīta uz [**abonēšanas atslēgu** no jūsu Customer Insights vides](#get-started-trying-the-customer-insights-apis).   

   Ja nepieciešams, atiestatiet galveni **Autorizācija**. Piemēram, ja ir izbeidzies marķieris.

1. Nododiet to `HttpClient`, veidojot `CustomerInsights` klientu.

   <!--   :::image type="content" source="media/httpclient-sample.png" alt-text="Sample of httpclient."::: -->

1. Piemēram, veiciet zvanus ar klientu uz "paplašinājuma metodēm" `GetAllInstancesAsync`. Ja priekšroka tiek dota piekļuvei pamatā esošajam `Microsoft.Rest.HttpOperationResponse` , izmantojiet, piemēram, "http ziņojumu metodes", `GetAllInstancesWithHttpMessagesAsync`.

1. Atbilde, visticamāk, `object` tiek ierakstīta, jo metode var atgriezt vairākus veidus (piemēram, `IList<InstanceInfo>` un `ApiErrorResult`). Lai pārbaudītu atgriešanas tipu, izmantojiet objektus atbilžu tipos, [kas norādīti šīs operācijas lapā](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) Detalizēta informācija par API.

   Ja ir nepieciešama papildu informācija par pieprasījumu, izmantojiet **http ziņojumu metodes**, lai piekļūtu neapstrādātam atbildes objektam.

### <a name="nodejs-package"></a>NodeJS pakotne

Izmantojiet NodeJS klientu bibliotēkas, kas ir pieejamas, izmantojot NPM: https://www.npmjs.com/package/@microsoft/customerinsights

### <a name="python-package"></a>Python pakotne

Izmantojiet Python klientu bibliotēkas, kas ir pieejamas, izmantojot PyPi: https://pypi.org/project/customerinsights/

[!INCLUDE [footer-include](includes/footer-banner.md)]
