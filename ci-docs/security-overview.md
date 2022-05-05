---
title: Drošības iestatījumi Dynamics 365 Customer Insights
description: Uzziniet par drošības iestatījumiem programmā Dynamics 365 Customer Insights.
ms.date: 04/28/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 5d73bacccadc9193d76d8dfafd0365dabc911e00
ms.sourcegitcommit: cf74b8c20d88eb96e1ac86e18cd44fe27aad5ab9
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 04/28/2022
ms.locfileid: "8653816"
---
# <a name="security-overview-page"></a>Drošības pārskata lapa

Lapā Drošība **ir** uzskaitītas opcijas, lai konfigurētu lietotāju atļaujas un līdzekļus, kas palīdz padarīt Dynamics 365 Customer Insights drošākus. Šai lapai var piekļūt tikai administratori. 

Dodieties uz **AdminSecurity** > **·**, lai konfigurētu iestatījumus.

Lapā **Drošība** ir šādas cilnes:
- [Lietotāji](#users-tab)
- [API](#apis-tab)
- [Key Vault](#key-vault-tab)

## <a name="users-tab"></a>Cilne Lietotāji

Piekļuve Customer Insights ir atļauta tikai lietotājiem jūsu organizācijā, kurus lietojumprogrammai pievienoja administrators. Cilne **Lietotāji** ļauj pārvaldīt lietotāju piekļuvi un viņa atļaujas. Papildinformāciju skatiet sadaļā [Lietotāja atļaujas](permissions.md).

## <a name="apis-tab"></a>Cilne API

Skatiet un pārvaldiet atslēgas, lai izmantotu [Customer Insights API](apis.md) ar vides datiem.

Varat izveidot jaunas primārās un sekundārās atslēgas, atlasot **Atkārtoti ģenerēt primāro** vai **Atkārtoti ģenerēt sekundāro**. 

Lai bloķētu API piekļuvi videi, atlasiet **Atspējot**. Ja API ir atspējoti, varat atlasīt **Iespējot**, lai vēlreiz piešķirtu piekļuvi.

## <a name="key-vault-tab"></a>Cilne Atslēgas seifs

Cilne **Key Vault** ļauj saistīt un pārvaldīt savu [Azure atslēgas glabātuvi](/azure/key-vault/general/basic-concepts) ar vidi.
Īpašo atslēgas akreditācijas datu glabātuvi var izmantot, lai izveidotu un izmantotu slepeno informāciju organizācijas ierobežojošajā robežu ietvaros. Customer Insights var izmantot Azure Key Seifu noslēpumus, lai [iestatītu savienojumus](connections.md) ar trešo pušu sistēmām.

Papildinformāciju skatiet [Ievadiet savu Azure Key Vault](use-azure-key-vault.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]
