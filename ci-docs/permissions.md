---
title: Lietotāju atļauju pārvaldīšana
description: Uzziniet vairāk par lietotāju lomām un atļaujām
ms.date: 02/09/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
searchScope:
- ci-permissions
- ci-system-security
- customerInsights
ms.openlocfilehash: 30b37645cad4e795ef20579e20e3f2bbdb2afbf6
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 06/29/2022
ms.locfileid: "9054884"
---
# <a name="manage-user-permissions"></a>Lietotāju atļauju pārvaldīšana

Atļauju **lapā** varat iestatīt lomas un atļaujas Customer Insights izmantošanai.

Lai skatītu šo lapu, jums ir nepieciešamas administratora atļaujas. Lai piekļūtu atļauju lapai, dodieties uz **Administratoru** > **drošības** > **lietotāji**.

Pastāv trīs lomu tipi:

## <a name="viewer"></a>Skatītājs

- Izpētiet ieskatus un segmentus **Sākumlapā** un lapā **Segmenti**.
- Meklējiet un filtrējiet klientu profilus, izmantojot lapu **Klienti**. Laukiem jābūt meklējamiem.
- Skatiet un pārlūkojiet lapu **Bagātināšana**.
- Izpētiet un eksportējiet entītijas, izmantojot lapu **Entītijas**.
- Skatiet sistēmas procesu statusu, izmantojot lapu **Sistēma**.
- Skatiet eksportus lapā **Eksportēšana**.
- Instalējiet un izmantojiet **Power BI Customer Insights** informācijas paneli.

## <a name="contributor"></a>Līdzstrādnieks

- Visas skatītājam pieejamās atļaujas.
- Ielādējiet un pārveidojiet datus, izmantojot lapu **Datu avoti**.
- Pilnīga ***Datu apvienošana**, kuras rezultātā tiek izveidota vienota klienta profila entītija.
- Definējiet **relācijas** un **darbības**.
- Izveidojiet segmentus, izmantojot lapu **Segmenti**.
- Izveidojiet mērus, izmantojot lapu **Mēri**.
- Pārvaldiet konfigurāciju un bagātiniet klientu profilus no **Bagātināšanas** lapas (tikai pirmās puses bagātināšanai).
- Pārvaldiet un izveidojiet eksportus, balstoties ar līdzstrādniekiem izveidotajos savienojumos. [Papildinformācija par to, kā administratori atļauj līdzstrādniekiem izmantot savienojumu eksportēšanai](connections.md#allow-contributors-to-use-a-connection-for-exports).

## <a name="admin"></a>Admin.

- Visas līdzstrādniekam pieejamās atļaujas.
- Mainiet iestatījumus lapā **Sistēmas**, tostarp darba valodu un atsvaidziniet sistēmas procesu grafikus.
- Skatiet un pievienojiet atļaujas, izmantojot lapu **Atļaujas**.
- Iestatiet meklēšanas un filtrēšanas definīcijas lapai Klienti, izmantojot lapu **Meklēšana un filtrēšana** (pieejama no lapas **Klienti**).
- Pārvaldiet savienojumus un atļaujiet tos citām lietotāju lomām lapā **Savienojumi**.
- Pārvaldiet konfigurāciju un bagātiniet klientu profilus no **Bagātināšanas** lapas (visām bagātināšanām).
- Pārvaldiet un izveidojiet eksportus lapā **Eksportēšana**.
- Instalējiet un izmantojiet **klienta kartes pievienojumprogrammu**.
- Pievienojiet un izmantojiet **Power Apps savienotāju**.
- [Iespējot API Customer Insights izmantošanu](apis.md)
- [Piešķiriet vides īpašumtiesības](manage-environments.md#change-the-owner-of-an-environment) citam administratoram.

## <a name="admin-owner"></a>Administrators (īpašnieks)

- Visas administratoram pieejamās atļaujas.
- [Atiestatiet un izdzēsiet](manage-environments.md#reset-an-existing-environment-preview) vidi.

## <a name="assign-roles-and-permissions"></a>Lomu un atļauju piešķiršana

1. Dodieties uz **administratoru** > **drošības** > **Lietotāji***.

1. Atlasiet vienumu **Pievienot lietotājus**, lai atvērtu rūti **Pievienot/Rediģēt atļaujas**.

1. Izmantojiet **Meklēšanas** lauku, lai atrastu Azure Active Directory lietotāju vai grupu, kuras atļaujas vēlaties pielāgot. Atlasiet **Lomu**, kas jāpiešķir šim lietotājam vai grupai.

1. Atlasiet vienumu **Saglabāt**. Pašreizējā vide tiek automātiski kopīgota ar lietotāju vai grupas dalībniekiem, kuru atļaujas esat mainījis. Lietotāji var piekļūt Customer Insights programmai un strādāt, vadoties pēc to noteiktās lomas.

## <a name="view-current-permissions"></a>Pašreizējo atļauju skatīšana

Dodieties uz **Administratoru** > **drošības** > **lietotāji**, lai uzzinātu, kādas lomu piešķires pašlaik ir aktīvas.

- Kolonnā **Tips** ir norādīts atsevišķs lietotājs, grupa vai lietojumprogramma. Sistēma atbalsta atsevišķus lietotājus un grupas.
- Lomas ir norādītas kolonnā **Loma**.
- Atlasiet jebkuru kolonnas virsrakstu, lai rezultātus kārtotu pēc šīs kolonnas vērtības.
- Izmantojiet lapas augšdaļā esošo lauku **Meklēt**, lai atrastu konkrētus lietotājus.


[!INCLUDE [footer-include](includes/footer-banner.md)]
