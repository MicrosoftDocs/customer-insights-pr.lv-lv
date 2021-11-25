---
title: Aktivizēt piekrišanas noteikumus segmentiem
description: Veiciet šīs darbības, lai saistītu piekrišanas datus un aktivizētu piekrišanas pārbaudes auditorijas ieskatos. Administrators var arī atspējot piekrišanas pārbaudes.
ms.date: 11/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: smithy7
ms.author: smithc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 45899738d39bd5caa433e123f9fe59020e831998
ms.sourcegitcommit: 79b09498d1328e5551fb8684c44af1fb149f9881
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 11/10/2021
ms.locfileid: "7790785"
---
# <a name="activate-consent-rules"></a>Aktivizēt piekrišanas noteikumus

[Piekrišanas centrs (priekšskatījums)](../consent-management/overview.md) palīdz saskaņot piekrišanas datus no dažādiem avotiem. Izmantojiet vienoto *·* piekrišanas entītiju, lai lietotu noklusējuma piekrišanas pārbaudes. Pēc piekrišanas datu importēšanas piekrišanas centrā un datu kārtulu konfigurēšanas *entītija Piekrišana* tiek automātiski sinhronizēta ar auditorijas ieskatiem.

## <a name="enable-consent-checks"></a>Iespējot piekrišanas pārbaudes

Izmantojot piekrišanas datus, kas importēti piekrišanas centrā (priekšskatījumā) un iestatītās kārtulas, varat iespējot piekrišanas pārbaudes. 

:::image type="content" source="../consent-management/media/enable-consent-checks-audience-insights.png" alt-text="Cilne Piekrišana auditorijas ieskatu iestatījumos ar aktivizētiem piekrišanas datiem.":::

1. Sadaļā Auditorijas ieskati skatiet **Administrators** > **Sistēma**.

1. Atlasiet **cilni Piekrišana (priekšskatījums).**

1. Sadaļā **Piekrišanas pārbaudes** iespējošana iestatiet pārslēgšanu uz **·** Ieslēgts visiem apgabaliem, kurus vēlaties iespējot.

1. Atzīmējiet **izvēles rūtiņu Atļaut ignorēt noklusējuma piekrišanas** kārtulas, lai noņemtu noklusējuma piekrišanas pārbaudes, kas ieviestas noteiktā segmentā. 

1. Nolaižamajā izvēlnē atlasiet, kur vēlaties atļaut ignorēšanu.     

1. Sadaļā **Saistīt piekrišanu klientu profiliem** izvēlieties atribūtu, kas tiek izmantots kā identifikators, lai saistītu piekrišanas datus ar klientu datiem. Tas, visticamāk, būs tālruņa numurs vai e-pasta adrese. 

1. Atlasiet **·** Saglabāt, lai lietotu iestatījumus.

## <a name="disable-consent-checks"></a>Atspējot piekrišanas pārbaudes

Lai pārtrauktu piekrišanas datu izmantošanu auditorijas ieskatos, administratoram ir atbilstoši jāatjaunina sistēmas iestatījumi.

1. Sadaļā Auditorijas ieskati skatiet **Administrators** > **Sistēma**.

1. Atlasiet **cilni Piekrišana (priekšskatījums).**

1. Sadaļā **Piekrišanas pārbaudes iespējošana** iestatiet slēdzi uz **·** Izslēgts.
