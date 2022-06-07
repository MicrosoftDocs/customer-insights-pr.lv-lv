---
title: Vides pārvaldība
description: Uzziniet, kā pārvaldīt esošās Customer Insights vides kā administrators."
ms.date: 05/31/2022
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-about
- customerInsights
ms.openlocfilehash: 62a5856edac5e66e5e42c93313d78fa6826469b3
ms.sourcegitcommit: f5af5613afd9c3f2f0695e2d62d225f0b504f033
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 06/01/2022
ms.locfileid: "8833501"
---
# <a name="how-to-manage-environments"></a>Vides pārvaldība

Administratori [izveido](create-environment.md) un pārvalda vides. Viņi var mainīt dažus iestatījumus esošajās vidēs. Pēc vides izveides tiek fiksēta biznesa, tipa, reģiona, krātuves opcija un Dataverse iestatījumi. Ja vēlaties mainīt šos iestatījumus, atiestatiet vidi vai izveidojiet jaunu vidi.

## <a name="edit-an-existing-environment"></a>Esošas vides rediģēšana

Jūs varat rediģēt dažas esošās vides detaļas.

1. Programmas galvenē atlasiet **Vides** atlasītāju.

1. Atlasiet **Rediģēt** ikonu.

   :::image type="content" source="media/edit-environment.png" alt-text="Ikona vides iestatījumu rediģēšanai.":::

1. Lodziņā **Rediģēt vidi** varat atjaunināt vides iestatījumus.

Lai sāktu ar svaigu vidi, skatiet rakstu [Jaunas vides izveide](create-environment.md).

## <a name="change-the-owner-of-an-environment"></a>Vides īpašnieka maiņa

Vairākiem lietotājiem var būt administratora atļaujas, bet tikai viens lietotājs ir vides īpašnieks. Pēc noklusējuma administrators sākotnēji izveido vidi. Kā vides administrators varat piešķirt īpašumtiesības citam lietotājam ar administratora atļaujām.

1. Programmas galvenē atlasiet **Vides** atlasītāju.

1. Atlasiet **Rediģēt** ikonu.

1. **Lodziņā Vides rediģēšana** dodieties uz soli **Pamatinformācija**.

1. Laukā **Mainīt vides** īpašnieku izvēlieties jauno vides īpašnieku.  

1. Atlasiet **Pārskatīšana un pabeigšana**, pēc tam **Atjauniniet**, lai lietotu izmaiņas.

## <a name="claim-ownership-of-an-environment"></a>Pieprasīt īpašumtiesības uz vidi

Ja īpašnieka lietotāja konts ir izdzēsts vai apturēts, videi nebūs īpašnieka. Katrs administratora lietotājs var pieprasīt īpašumtiesības un kļūt par jauno īpašnieku. Viņi var turpināt piederēt videi vai [mainīt īpašumtiesības uz citu administratoru](#change-the-owner-of-an-environment).

Lai pieprasītu īpašumtiesības, atlasiet **pogu Uzņemties īpašumtiesības**, kas tiek rādīta katras Customer Insights lapas augšdaļā, kad sākotnējais īpašnieks pameta organizāciju.

## <a name="reset-an-existing-environment-preview"></a>Esošas vides atiestatīšana (priekšskatījums)

Kā vides īpašnieks varat atiestatīt vidi tukšā stāvoklī, ja vēlaties izdzēst visas konfigurācijas un noņemt uzņemtos datus.

1. Programmas galvenē atlasiet **Vides** atlasītāju.

1. Atlasiet vidi, kuru vēlaties atiestatīt, un atlasiet vertikālo daudzpunkti (&vellip;).

1. Izvēlieties opciju **Atiestatīt**.

   :::image type="content" source="media/reset-environment.png" alt-text="Kontrolējiet, lai atiestatītu vidi.":::

1. Izvēlieties, vai vēlaties atiestatīt visu vidi, visu, izņemot datu avotus, vai jebko, kas ir konfigurēts virs vienotā klienta profila.

1. Lai apstiprinātu, ievadiet vides nosaukumu un atlasiet **Atiestatīt**.

## <a name="delete-an-existing-environment"></a>Esošas vides dzēšana

Kā vides īpašnieks varat izdzēst administrēto vidi.

1. Programmas galvenē atlasiet **Vides** atlasītāju.

1. Atlasiet vidi, kuru vēlaties atiestatīt, un atlasiet vertikālo daudzpunkti (&vellip;). 

1. Izvēlieties opciju **Dzēst**.

   :::image type="content" source="media/delete-environment.png" alt-text="Kontrolējiet, lai izdzēstu vidi.":::

1. Lai apstiprinātu dzēšanu, ievadiet vides nosaukumu un atlasiet **Dzēst**.

> [!IMPORTANT]
> Dzēšot vidi, netiek noņemts savienojums ar Dataverse vidi. Ja nākotnē plānojat savienot to pašu Dataverse vidi ar jaunu Customer Insights vidi, ir jānoņem šis savienojums Uzziniet, kā [noņemt esošu savienojumu ar Dataverse vidi](customer-insights-dataverse.md#remove-an-existing-connection-to-a-dataverse-environment).

[!INCLUDE [footer-include](includes/footer-banner.md)]
