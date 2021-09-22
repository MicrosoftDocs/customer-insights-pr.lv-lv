---
title: Iespējot neiekļautās profila atskaites
description: Kā izveidot neiekļautās profila atskaites, sagrupētas pēc dzimtes, vecuma un izcelsmes apgabala vai reģiona.
author: darrinw-docs
ms.reviewer: mhart
ms.author: darrinw
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 3aa9599fc780098a2f7f31f0210d76ed2ef27ece774dd6212b5cb2a599ad537e
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 08/10/2021
ms.locfileid: "7033961"
---
# <a name="out-of-box-profile-reports"></a>Neiekļautās profila atskaites

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Atskaite ir datu vizualizāciju kolekcija, lai palīdzētu izprast lietotāja uzvedību. Izveidojot savienojumu ar Customer Insights auditoriju ieskatiem, iesaistes ieskati var rādīt atskaiti ar informāciju par vienotajam klientu profiliem. Šajā atskaitē ir iekļauts jūsu profilu skaits, kas sagrupēti pēc dzimtes, vecuma un ģeogrāfiskā atrašanās vietas.

## <a name="prerequisites"></a>Priekšnosacījumi

Auditorijas ieskatu vidē ir jāsaglabā dati klienta pārvaldītā Azure Data Lake Storage kontā.

Ja izmantojat auditorijas ieskatu iespējas izmēģinājumversiju vai vidi Customer Insights pārvaldīto datu ezeru, [sazinieties ar mums](https://go.microsoft.com/fwlink/?linkid=2145734), lai saņemtu palīdzību.  


## <a name="enable-the-customer-profile-report"></a>Klienta profila atskaites iespējošana

Vides administratoram ir [jāizveido savienojums ar auditorijas ieskatiem](configure-connections.md).

Pēc savienojuma informācijas norādīšanas administrators var piešķirt piekļuvi citiem organizācijas darbiniekiem, lai redzētu atskaiti. Vides administrators, kurš ir iestatījis savienojumu, automātiski var piekļūt atskaitei. 

Pēc savienojuma izveides **Profilu** līdzeklis būs pieejams kreisajā navigācijas rūtī. 

- Lai skatītu atskaiti, dodieties uz **Atklāt** > **Profili**.

**Profilu** atskaitē ir ietvertas vizualizācijas par piesaistīto klientu profilu dzimti, vecumu un ģeogrāfisko atrašanās vietu.

:::image type="content" source="media/customer-profiles.png" alt-text="Klienta profila atskaite.":::

[!INCLUDE[footer-include](../includes/footer-banner.md)]