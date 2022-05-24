---
title: Segmentu piekrišanas kārtulu aktivizēšana
description: Veiciet šīs darbības, lai saistītu piekrišanas datus un aktivizētu piekrišanas pārbaudes programmā Dynamics 365 Customer Insights. Administrators var arī atspējot piekrišanas pārbaudes.
ms.date: 04/27/2022
ms.topic: how-to
author: anubhav-t
ms.author: antando
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: f82e3a4031fee8bcaa88575cbd68b37385a7fffb
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755179"
---
# <a name="activate-consent-rules"></a>Aktivizēt piekrišanas kārtulas

Piekrišanas [centrs (priekšskatījums)](consent-management/overview.md) palīdz saskaņot piekrišanas datus no dažādiem avotiem. Izmantojiet vienoto *piekrišanas entītiju*, lai lietotu noklusējuma piekrišanas pārbaudes. Pēc piekrišanas datu importēšanas un kartes kārtulu konfigurēšanas piekrišanas entītija *tiek* automātiski sinhronizēta ar Dynamics 365 Customer Insights.

## <a name="enable-consent-checks"></a>Iespējot piekrišanas pārbaudes

Ja piekrišanas dati tiek importēti piekrišanas centrā (priekšskatījumā) un iestatītas kārtulas, varat iespējot piekrišanas pārbaudes. 

:::image type="content" source="consent-management/media/enable-consent-checks.png" alt-text="Piekrišanas cilne Customer Insights iestatījumos ar aktivizētiem piekrišanas datiem.":::

1. Sadaļā Customer Insights dodieties uz **Administrators** > **Sistēma**.

1. **Atlasiet cilni Piekrišana (priekšskatījums).**

1. Sadaļā Piekrišanas **pārbaužu** iespējošana iestatiet slēdzi uz **Ieslēgts** visiem apgabaliem, kurus vēlaties iespējot.

1. **Atzīmējiet izvēles rūtiņu Atļaut ignorēt noklusējuma piekrišanas kārtulas**, lai noņemtu noklusējuma piekrišanas pārbaudes, kas ieviestas noteiktā segmentā. 

1. Nolaižamajā izvēlnē atlasiet vietu, kur vēlaties atļaut ignorēšanu.     

1. **Sadaļā Saistīt piekrišanu klientu profiliem** izvēlieties atribūtu, kas tiek izmantots kā identifikators, lai saistītu piekrišanas datus ar klientu datiem. Tas, visticamāk, būs tālruņa numurs vai e-pasta adrese. 

1. Atlasiet **Saglabāt**, lai lietotu iestatījumus.

## <a name="disable-consent-checks"></a>Atspējot piekrišanas pārbaudes

Lai pārtrauktu piekrišanas datu izmantošanu customer insights, administratoram ir attiecīgi jāatjaunina sistēmas iestatījumi.

1. Sadaļā Customer Insights dodieties uz **Administrators** > **Sistēma**.

1. **Atlasiet cilni Piekrišana (priekšskatījums).**

1. Sadaļā Piekrišanas **pārbaužu iespējošana iestatiet slēdzi izslēgts** **·**.

> [!TIP]
> Lai pārtrauktu piekrišanas pārvaldības iespēju izmantošanu, skatiet sadaļu [Sistēmas iestatījumi piekrišanas centrā (priekšskatījums)](consent-management/system-settings.md).
