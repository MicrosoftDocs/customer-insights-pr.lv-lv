---
title: Noklusējuma piekrišanas kārtulu pārvaldība segmentos
description: Izmantojot piekrišanas pārvaldības iespēju, varat atspējot vai mainīt noklusējuma piekrišanas kārtulas, ja ir iespējota ignorēšana.
ms.date: 12/01/2021
mms.topic: how-to
author: smithy7
ms.author: smithc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 4eae4da67fd4c6e70800f495ba30366d4fc9a0dd
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 02/16/2022
ms.locfileid: "8228948"
---
# <a name="disable-or-change-default-consent-rules"></a>Noklusējuma piekrišanas kārtulu atspējošana vai mainīšana

Ja jūsu organizācijas izmanto [piekrišanas pārvaldības iespēju](../consent-management/overview.md) apvienojumā ar auditorijas ieskatiem, [administratori var ieviest piekrišanas kārtulas](activate-consent.md) segmentiem. 

Izmantojot piespiedu piekrišanas kārtulas segmenta apgabalā, katrs segments informē par piekrišanas pārbaudes stāvokli un noteikumiem. Ja ignorēšana ir atļauta, noklusējuma piekrišanas kārtulas ir izslēgtas noteiktiem segmentiem. Katrs segmenta veidotājs segmentam var pievienot papildu piekrišanas kārtulas papildus noklusējuma kārtulām. 

## <a name="for-administrators"></a>Administratoriem

:::image type="content" source="../consent-management/media/consent-rules-segment.png" alt-text="Segmentu veidotājs ar piekrišanas kārtulu opcijām.":::

**Lai deaktivizētu noklusējuma piekrišanas kārtulas:**

1. Paziņojumā Par **piekrišanas noteikumiem** atlasiet **Skatīt detalizētu informāciju**. 

1. **Iestatiet noklusējuma piekrišanas kārtulu** pārslēgšanu uz **Izslēgts**.

**Lai pievienotu papildu piekrišanas kārtulas:**

1. Paziņojumā Par **piekrišanas noteikumiem** atlasiet **Skatīt detalizētu informāciju**. 

1. Nolaižamajā izvēlnē Atlasīt piekrišanas datu tipu atlasiet **Pievienot piekrišanas kārtulas** un izvēlieties piekrišanas **kārtulu**.

1. Atlasiet **Saglabāt**, lai segmentam lietotu jauno kārtulu.

## <a name="for-contributors"></a>Līdzstrādniekiem

Lai izveidotu segmentu bez piespiedu piekrišanas kārtulām, jums ir jāsadarbojas ar administratoru, lai tos atspējotu segmentā. Tomēr varat pievienot savas piekrišanas kārtulas segmentiem, kas jums pieder un ko pārvaldāt.

Tas ir trīs soļu process: 
1. [Izveidojiet segmentu](segments.md) auditorijas ieskatos un saglabājiet to. 

1. Koplietojiet segmenta nosaukumu ar administratoru un lūdziet, lai [tas iespējo segmenta](activate-consent.md) ignorēšanu. 

1. Atveriet savus segmentus vēlreiz. Paziņojumā Par **piekrišanas noteikumiem** atlasiet **Skatīt detalizētu informāciju** un pievienojiet piekrišanas noteikumus, kurus vēlaties lietot. Pēc tam **saglabājiet** un **palaidiet** savu segmentu.



[!INCLUDE[footer-include](../includes/footer-banner.md)] 
