---
title: Lietotāju atļauju piešķiršana
description: Uzziniet vairāk par lietotāju lomām un atļaujām
ms.date: 08/08/2022
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
ms.openlocfilehash: a59a672b6f7e1e67c2162ea14bb9860df0d551aa
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245428"
---
# <a name="assign-user-permissions"></a>Lietotāju atļauju piešķiršana

Piekļuve Customer Insights ir atļauta tikai tiem lietotājiem jūsu organizācijā, kurus lietojumprogrammai ir pievienojis administrators. Administrators var pievienot, rediģēt vai noņemt lietotājus. Lietotājs var būt viens lietotājs, grupa vai lietojumprogramma. Lietotājam var būt trīs veidu lomas:

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
- Pilnīga **datu apvienošana**, kuras rezultātā tiek izveidota vienota klienta profila entītija.
- Definējiet **relācijas** un **darbības**.
- Izveidojiet segmentus, izmantojot lapu **Segmenti**.
- Izveidojiet mērus, izmantojot lapu **Mēri**.
- Pārvaldiet konfigurāciju un bagātiniet klientu profilus no **Bagātināšanas** lapas (tikai pirmās puses bagātināšanai).
- Pārvaldiet un izveidojiet eksportēšanu, pamatojoties uz [savienojumiem, kas kopīgoti ar līdzstrādniekiem](connections.md#allow-contributors-to-use-a-connection-for-exports).

## <a name="admin"></a>Admin.

- Visas līdzstrādniekam pieejamās atļaujas.
- Mainiet iestatījumus **lapā Sistēma**, tostarp darba valodu, sistēmas procesu atsvaidzināšanas grafikus un diagnostikas žurnālu eksportēšanu.
- Mainiet iestatījumus **drošības** lapā, tostarp lietotājus, API atslēgas, privātās saites un atslēgu glabātuvi.
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

## <a name="add-users"></a>Lietotāju pievienošana

1. Dodieties uz **Administratora** > **drošība** un atlasiet **cilni Lietotāji**.

1. Atlasiet vienumu **Pievienot lietotājus**, lai atvērtu rūti **Pievienot/Rediģēt atļaujas**.

1. Izmantojiet **lauku Meklēšana**, lai atrastu Azure Active Directory lietotāju vai grupu, kuru vēlaties pievienot. Atlasiet **Lomu**, kas jāpiešķir šim lietotājam vai grupai.

1. Atlasiet **Saglabāt**. Pašreizējā vide tiek automātiski kopīgota ar lietotāju vai grupas dalībniekiem. Lietotāji var piekļūt Customer Insights programmai un strādāt, vadoties pēc to noteiktās lomas.

## <a name="view-current-permissions"></a>Pašreizējo atļauju skatīšana

Dodieties uz **Administratora** > **drošība** un atlasiet **cilni Lietotāji**, lai skatītu aktīvo lietotāju un viņu lomu piešķiršanas sarakstu. Varat kārtot lietotāju sarakstu pēc jebkuras kolonnas vai izmantot meklēšanas lodziņu, lai atrastu konkrētu lietotāju.

## <a name="manage-current-users"></a>Pašreizējo lietotāju pārvaldība

Dodieties uz **Administratora** > **drošība** un atlasiet **cilni Lietotāji** . Varat kārtot lietotāju sarakstu pēc jebkuras kolonnas vai izmantot meklēšanas lodziņu, lai atrastu lietotāju, kuru vēlaties pārvaldīt.

Atlasiet lietotāju, lai skatītu pieejamās darbības.

- **Rediģējiet**, lai rediģētu lietotāja lomu programmā Customer Insights. Atlasiet **Saglabāt**, lai apstiprinātu izmaiņas.
- **Noņemiet**, lai noņemtu lietotāju no piekļuves Customer Insights. Lai apstiprinātu dzēšanu, atlasiet **Dzēst**.

[!INCLUDE [footer-include](includes/footer-banner.md)]
