---
title: Pārvaldīt vides
description: Uzziniet, kā pārvaldīt esošās Customer Insights vides kā administratoram."
ms.date: 08/15/2022
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-about
- customerInsights
ms.openlocfilehash: 8b4a88bdb75c6e638a76c39d18647681ad4556d7
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304293"
---
# <a name="manage-environments"></a>Pārvaldīt vides

Administratori [izveido](create-environment.md) un pārvalda vides. Viņi var mainīt dažus iestatījumus esošajās vidēs. Bizness, tips, reģions, krātuves opcija un Dataverse iestatījumi tiek fiksēti pēc vides izveides. Ja vēlaties mainīt šos iestatījumus, [atiestatiet vidi](#reset-an-existing-environment-preview) vai [izveidojiet jaunu vidi](create-environment.md).

## <a name="edit-an-existing-environment"></a>Esošas vides rediģēšana

Rediģējiet detalizētu informāciju par esošu vidi, piemēram, nosaukumu vai noklusējuma vides iestatījumu.

1. Programmas galvenē atlasiet **Vides** atlasītāju.

1. Atlasiet **Rediģēt** ikonu.

   :::image type="content" source="media/edit-environment.png" alt-text="Ikona, lai rediģētu vides iestatījumus.":::

1. Vides rediģēšanas **rūtī** atjauniniet vides iestatījumus.

1. Atlasiet **Pārskatīt un pabeigt**, pēc tam **Atjaunināt**, lai lietotu izmaiņas.

## <a name="change-the-owner-of-an-environment"></a>Vides īpašnieka maiņa

Vairākiem lietotājiem var būt administratora atļaujas, bet tikai viens lietotājs ir vides īpašnieks. Pēc noklusējuma tas ir administrators, kurš sākotnēji izveido vidi. Kā vides administrators varat piešķirt īpašumtiesības citam lietotājam ar administratora atļaujām.

1. Programmas galvenē atlasiet **Vides** atlasītāju.

1. Atlasiet **Rediģēt** ikonu.

1. Vides rediģēšanas **rūtī** pārejiet uz **darbību Pamatinformācija**.

1. **Laukā Mainīt vides** īpašnieku izvēlieties jauno vides īpašnieku.  

1. Atlasiet **Pārskatīt un pabeigt**, pēc tam **Atjaunināt**, lai lietotu izmaiņas.

## <a name="claim-ownership-of-an-environment"></a>Pieprasiet īpašumtiesības uz vidi

Ja īpašnieka lietotāja konts tiek izdzēsts vai apturēts, videi nebūs īpašnieka. Jebkurš administratora lietotājs var pieprasīt īpašumtiesības un kļūt par jauno īpašnieku. Īpašnieka administrators var turpināt piederēt videi vai [mainīt īpašumtiesības uz citu administratoru](#change-the-owner-of-an-environment).

Lai pieprasītu īpašumtiesības, atlasiet **pogu Veikt īpašumtiesības**, kas tiek rādīta katras Customer Insights lapas augšdaļā, kad sākotnējais īpašnieks pameta organizāciju.

## <a name="reset-an-existing-environment-preview"></a>Esošas vides atiestatīšana (priekšskatījums)

Kā vides īpašnieks atiestatiet vidi tukšā stāvoklī, ja vēlaties izdzēst visas konfigurācijas un noņemt uzņemtos datus.

1. Programmas galvenē atlasiet **Vides** atlasītāju.

1. Atlasiet vidi, kuru vēlaties atiestatīt, un atlasiet vertikālo elipsi (&vellip;).

1. Izvēlieties **Atiestatīt (priekšskatījums)**.

   :::image type="content" source="media/reset-environment.png" alt-text="Kontrolējiet, lai atiestatītu vidi.":::

1. Izvēlieties, vai vēlaties atiestatīt visu vidi, visu, izņemot datu avotus, vai jebko, kas ir konfigurēts virs vienotā klienta profila.

1. Lai apstiprinātu, ievadiet vides nosaukumu un atlasiet **Atiestatīt**.

## <a name="delete-an-existing-environment"></a>Esošas vides dzēšana

Kā vides īpašnieks jūs varat to izdzēst.

> [!IMPORTANT]
> Dzēšot vidi, netiek noņemts savienojums ar Dataverse vidi. Ja nākotnē plānojat savienot to pašu Dataverse vidi ar jaunu Customer Insights vidi, šis savienojums ar [vidi Dataverse ir](customer-insights-dataverse.md#remove-an-existing-connection-to-a-dataverse-environment) jānoņem.

1. Programmas galvenē atlasiet **Vides** atlasītāju.

1. Atlasiet vidi, kuru vēlaties dzēst, un atlasiet vertikālo elipsi (&vellip;). 

1. Izvēlieties **Dzēst**.

   :::image type="content" source="media/delete-environment.png" alt-text="Kontrolējiet, lai izdzēstu vidi.":::

1. Lai apstiprinātu dzēšanu, ievadiet vides nosaukumu un atlasiet **Dzēst**.

[!INCLUDE [footer-include](includes/footer-banner.md)]
