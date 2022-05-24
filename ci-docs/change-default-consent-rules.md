---
title: Segmentu noklusējuma piekrišanas kārtulu pārvaldība
description: Izmantojot piekrišanas pārvaldības iespēju, varat atspējot vai mainīt noklusējuma piekrišanas kārtulas, ja ir iespējota ignorēšana.
ms.date: 12/01/2021
ms.topic: how-to
author: anubhav-t
ms.author: antando
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 764eeca9d99c95a34d9bd4c11d79f8b8e90701e2
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755225"
---
# <a name="disable-or-change-default-consent-rules"></a>Noklusējuma piekrišanas kārtulu atspējošana vai mainīšana

Ja jūsu organizācijas izmanto piekrišanas [pārvaldības iespējas](consent-management/overview.md) ar Dynamics 365 Customer Insights, [administratori var ieviest piekrišanas kārtulas](activate-consent.md) segmentiem. 

Izmantojot ieviestās piekrišanas kārtulas segmenta apgabalā, katrs segments informē par piekrišanas pārbaudes stāvokli un kārtulām. Ja ignorēšana ir atļauta, noklusējuma piekrišanas kārtulas tiek izslēgtas noteiktiem segmentiem. Katrs segmenta veidotājs segmentam papildus noklusējuma kārtulām var pievienot papildu piekrišanas kārtulas. 

## <a name="for-administrators"></a>Administratoriem

:::image type="content" source="consent-management/media/consent-rules-segment.png" alt-text="Segmentu veidotājs ar piekrišanas kārtulu opcijām.":::

**Lai deaktivizētu noklusējuma piekrišanas kārtulas:**

1. Paziņojumā par piekrišanas **kārtulām** atlasiet **Skatīt detaļas**. 

1. Iestatiet noklusējuma piekrišanas **kārtulu** slēdzi uz **Izslēgts**.

**Lai pievienotu papildu piekrišanas kārtulas:**

1. Paziņojumā par piekrišanas **kārtulām** atlasiet **Skatīt detaļas**. 

1. Nolaižamajā izvēlnē Atlasīt piekrišanas datu tipu atlasiet **Pievienot piekrišanas kārtulas** un izvēlieties piekrišanas **kārtulu.**

1. Atlasiet **Saglabāt**, lai segmentam lietotu jauno kārtulu.

## <a name="for-contributors"></a>Līdzstrādniekiem

Lai izveidotu segmentu bez piespiedu piekrišanas kārtulām, jums ir jāsadarbojas ar administratoru, lai tos atspējotu savā segmentā. Tomēr varat pievienot savas piekrišanas kārtulas segmentiem, kas jums pieder un ko jūs pārvaldāt.

Tas ir trīs soļu process: 
1. [Izveidojiet segmentu](segments.md) customer insights un saglabājiet to. 

1. Kopīgojiet segmenta nosaukumu ar administratoru un lūdziet viņiem [iespējot segmenta](activate-consent.md) ignorēšanu. 

1. Vēlreiz atveriet segmentus. Paziņojumā par piekrišanas **kārtulām** atlasiet **Skatīt detalizētu informāciju** un pievienojiet piekrišanas kārtulas, kuras vēlaties lietot. Pēc tam **saglabājiet** un **palaidiet** savu segmentu.



[!INCLUDE [footer-include](includes/footer-banner.md)] 
