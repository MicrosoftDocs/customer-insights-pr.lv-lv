---
title: Drošības iestatījumu konfigurēšana
description: Uzziniet par drošības iestatījumiem sadaļā Dynamics 365 Customer Insights.
ms.date: 08/02/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: ea21163d7dd05370de28ca8340ae9583846adb26
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 08/10/2022
ms.locfileid: "9246071"
---
# <a name="configure-security-settings"></a>Drošības iestatījumu konfigurēšana

Pārvaldiet API atslēgas, piekļūstiet klientu datiem un iestatiet Azure privāto saiti.

## <a name="manage-api-keys"></a>PĀRVALDIET API atslēgas

Skatiet un pārvaldiet atslēgas, lai izmantotu [Customer Insights API](apis.md) ar datiem savā vidē.

1. Dodieties uz Sistēmas drošība un atlasiet **cilni API** > **.** **·**

1. Ja API piekļuve videi nav iestatīta, atlasiet **Iespējot**. Vai arī, lai bloķētu API piekļuvi videi, atlasiet **Atspējot** un apstiprināt.

1. Pārvaldiet primārās un sekundārās API atslēgas:

   1. Lai parādītu primāro vai sekundāro API atslēgu, atlasiet **simbolu Rādīt**.

   1. Lai kopētu primāro vai sekundāro API atslēgu, atlasiet **simbolu Kopēt**.

   1. Lai izveidotu jaunas primārās vai sekundārās API atslēgas, atlasiet **Atjaunot primāro** vai **Atjaunot sekundāro**.

## <a name="securely-access-customer-data-with-customer-lockbox-preview"></a>Droša piekļuve klientu datiem, izmantojot klientu bloķēšanas lodziņu (priekšskatījums)

Customer Insights izmanto Power Platform Customer Lockbox iespēju. Klientu bloķēšanas lodziņš nodrošina saskarni, lai pārskatītu un apstiprinātu (vai noraidītu) datu piekļuves pieprasījumus. Šie pieprasījumi rodas, ja ir nepieciešama piekļuve datiem klientu datiem, lai atrisinātu atbalsta pieteikumu. Lai izmantotu šo līdzekli, programmā Customer Insights ir jābūt esošam savienojumam ar nomnieka Microsoft Dataverse vidi.

Lai iegūtu papildinformāciju [par klientu bloķēšanas lodziņu, skatiet klientu bloķēšanas](/power-platform/admin/about-lockbox#summary) lodziņa kopsavilkumu Power Platform. Rakstā ir aprakstīta [arī darbplūsma](/power-platform/admin/about-lockbox#workflow) un nepieciešamie [iestatījumi](/power-platform/admin/about-lockbox#enable-the-lockbox-policy), lai iespējotu klientu bloķēšanas lodziņu.

> [!IMPORTANT]
> Globālie administratori Power Platform vai Power Platform administratori var apstiprināt Customer Lockbox pieprasījumus, kas izsniegti customer insights.

## <a name="set-up-an-azure-private-link"></a>Azure privātās saites iestatīšana

[Azure Private Link](/azure/private-link/private-link-overview) ļauj Customer Insights izveidot savienojumu ar jūsu Azure Data Lake Storage kontu, izmantojot privātu galapunktu jūsu virtuālajā tīklā. Datiem krātuves kontā, kas nav atvērts publiskajam internetam, Private Link iespējo savienojumu ar šo ierobežoto tīklu.

> [!IMPORTANT]
> Minimālās lomas prasības, lai izveidotu privātās saites savienojumu:
>
> - Customer Insights: administrators
> - Azure iebūvētā loma: [Krātuves konta līdzstrādnieks](/azure/role-based-access-control/built-in-roles#storage-account-contributor)
> - Atļaujas pielāgotai Azure lomai: [Microsoft.Storage/storageAccounts/read un Microsoft.Storage/storageAccounts/PrivateEndpointConnectionsApproval/action](/azure/role-based-access-control/resource-provider-operations#microsoftstorage)

1. Programmā Customer Insights dodieties uz **Administratora** > **drošība** un atlasiet **cilni Privātās saites**.

1. Atlasiet **Pievienot privātu saiti**.

   Rūtī Pievienot **privātu saiti** ir uzskaitīti nomnieka krātuves konti, kurus jums ir atļauts skatīt.

1. Atlasiet abonementu, resursu grupu un krātuves kontu.

1. Pārskatiet datu privātumu [un atbilstību](connections.md#data-privacy-and-compliance) un atlasiet **Es piekrītu**.

1. Atlasiet **Saglabāt**.

1. Dodieties uz savu Data Lake Storage kontu un atveriet ekrānā redzamo saiti.

1. Apstipriniet privāto saiti.


[!INCLUDE [footer-include](includes/footer-banner.md)]
