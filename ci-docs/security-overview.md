---
title: Drošības iestatījumi customer insights
description: Uzziniet par drošības iestatījumiem programmā Dynamics 365 Customer Insights.
ms.date: 06/08/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 163deb9bed4f82d742c46cace27dd128f0aca18b
ms.sourcegitcommit: 8e9f0a9693fd8d91ad0227735ff03688fef5406f
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 06/10/2022
ms.locfileid: "8947424"
---
# <a name="security-settings-in-customer-insights"></a>Drošības iestatījumi customer insights

Lapā Drošība **ir** uzskaitītas opcijas, lai konfigurētu lietotāju atļaujas un līdzekļus, kas palīdz padarīt Dynamics 365 Customer Insights drošākus. Šai lapai var piekļūt tikai administratori.

Lai konfigurētu iestatījumus, dodieties uz **Administrēšanas** > **drošība**.

Lapā **Drošība** ir šādas cilnes:

- [Lietotāji](#users-tab)
- [API](#apis-tab)
- [Privātas saites](#private-links-tab)
- [Key Vault](#key-vault-tab)
- [Droša piekļuve klientu datiem, izmantojot customer Lockbox (Preview)](#securely-access-customer-data-with-customer-lockbox-preview)

## <a name="users-tab"></a>Cilne Lietotāji

Piekļuve Customer Insights ir atļauta tikai lietotājiem jūsu organizācijā, kurus lietojumprogrammai pievienoja administrators. Cilne **Lietotāji** ļauj pārvaldīt lietotāju piekļuvi un viņa atļaujas. Papildinformāciju skatiet sadaļā [Lietotāja atļaujas](permissions.md).

## <a name="apis-tab"></a>Cilne API

Skatiet un pārvaldiet atslēgas, lai izmantotu [Customer Insights API](apis.md) ar vides datiem.

Varat izveidot jaunas primārās un sekundārās atslēgas, atlasot **Atkārtoti ģenerēt primāro** vai **Atkārtoti ģenerēt sekundāro**. 

Lai bloķētu API piekļuvi videi, atlasiet **Atspējot**. Ja API ir atspējoti, varat atlasīt **Iespējot**, lai vēlreiz piešķirtu piekļuvi.

## <a name="private-links-tab"></a>Cilne Privātās saites

[Azure Private Link](/azure/private-link/private-link-overview) izveidosim savienojumu ar jūsu Azure Data Lake Storage kontu, izmantojot privātu galapunktu jūsu virtuālajā tīklā. Attiecībā uz datiem krātuves kontā, kas nav pakļauts publiskajam internetam, Private Link iespējo savienojumu ar šo ierobežoto tīklu.

> [!IMPORTANT]
> Minimālās lomas prasība, lai iestatītu Private Link savienojumu:
>
> - Klientu ieskati: administrators
> - Azure iebūvētā loma: [Krātuves konta līdzstrādnieks](/azure/role-based-access-control/built-in-roles#storage-account-contributor)
> - Pielāgotas Azure lomas atļaujas: [Microsoft.Storage/storageAccounts/read un Microsoft.Storage/storageAccounts/PrivateEndpointConnectionsApproval/action](/azure/role-based-access-control/resource-provider-operations#microsoftstorage)
>

Privātās saites iestatīšana customer insights ir divpakāpju process. Vispirms jūs uzsākat privātas saites izveidi no **administrēšanas** > **drošības** > **privātajām saitēm** customer insights. Rūtī **Pievienot privāto saiti** ir uzskaitīti nomnieka krātuves konti, kurus jums ir atļaujas skatīt. Atlasiet krātuves kontu un sniedziet piekrišanu privātās saites izveidei.

Pēc tam jums jāapstiprina privātā saite datu ezera krātuves konta pusē. Atveriet ekrānā parādīto saiti, lai apstiprinātu jauno privāto saiti.

## <a name="key-vault-tab"></a>Cilne Atslēgas seifs

Cilne **Key Vault** ļauj saistīt un pārvaldīt savu [Azure atslēgas glabātuvi](/azure/key-vault/general/basic-concepts) ar vidi.
Īpašo atslēgas akreditācijas datu glabātuvi var izmantot, lai izveidotu un izmantotu slepeno informāciju organizācijas ierobežojošajā robežu ietvaros. Customer Insights var izmantot Azure Key Seifu noslēpumus, lai [iestatītu savienojumus](connections.md) ar trešo pušu sistēmām.

Papildinformāciju skatiet [Ievadiet savu Azure Key Vault](use-azure-key-vault.md).

## <a name="securely-access-customer-data-with-customer-lockbox-preview"></a>Droša piekļuve klientu datiem, izmantojot customer Lockbox (Preview)

Customer Insights izmanto Power Platform customer Lockbox iespēju. Customer Lockbox nodrošina interfeisu, lai pārskatītu un apstiprinātu (vai noraidītu) datu piekļuves pieprasījumus. Šie pieprasījumi rodas, ja atbalsta pieteikuma atrisināšanai ir nepieciešama piekļuve klientu datiem. Lai izmantotu šo līdzekli, Customer Insights ir jābūt esošam savienojumam ar nomnieka Microsoft Dataverse vidi.

Papildinformāciju par customer Lockbox skatiet customer lockbox [kopsavilkumā](/power-platform/admin/about-lockbox#summary)Power Platform. Rakstā aprakstīta [arī darbplūsma](/power-platform/admin/about-lockbox#workflow) un nepieciešamie [iestatījumi](/power-platform/admin/about-lockbox#enable-the-lockbox-policy), lai iespējotu klientu bloķēšanas lodziņu.

> [!IMPORTANT]
> Globālie administratori Power Platform vai Power Platform administratori var apstiprināt Customer Lockbox pieprasījumus, kas izsniegti Customer Insights.

[!INCLUDE [footer-include](includes/footer-banner.md)]
