---
title: Pasākumu izveide no veidnēm
description: Definējiet pasākumus, izmantojot veidnes koplietošanas gadījumiem.
ms.date: 02/28/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-measure-template
- customerInsights
ms.openlocfilehash: 0fe846691825b93732cbbe6d1c942a79e4a3934f
ms.sourcegitcommit: cf6a0ed44915908a44c70889a2dd199a9d0d4798
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 02/28/2022
ms.locfileid: "8359963"
---
# <a name="use-a-template-to-build-a-measure"></a>Veidnes izmantošana mērījuma veidošanā

Lai tos izveidotu, var izmantot iepriekš definētas bieži lietotu [pasākumu](measures.md) veidnes. Detalizēti veidņu apraksti un vadība palīdzēs jums sekmīgi izveidot mērījumu. Veidnes tiek veidotas uz kartētajiem datiem no *Vienotās darbības* entitījas. Tāpēc, pirms no veidnes izveidojat mērījumu, pārliecinieties, ka esat konfigurējuši [klientu darbības](activities.md).

Lai izveidotu pielāgotus pasākumus, skatiet rakstu [Mērvienību veidotāja izmantošana, lai izveidotu pasākumus no nulles](measure-builder.md).

# <a name="individual-consumers-b-to-c"></a>[Atsevišķi patērētāji (B2C)](#tab/b2c)

Pieejamās mērījumu veidnes: 
- Vidējā transakcijas vērtība (ATV)
- Kopējā transakciju vērtība
- Vidējie ieņēmumi dienā
- Gada vidējie ieņēmumi
- Transakciju skaits
- Iegūtie lojalitātes punkti
- Izmantotie lojalitātes punkti
- Lojalitātes punktu bilance
- Klienta aktivitātes laika periods
- Dalības ilgums lojalitātes programmā
- Laiks kopš pēdējā pirkuma

## <a name="build-a-new-measure-using-a-template"></a>Jauna pasākuma izveide, izmantojot veidni

1. Dodieties uz **Pasākumi**.

1. Atlasiet **Jauns** un atlasiet **Izvēlieties veidni**.

   :::image type="content" source="media/measure-use-template.png" alt-text="Nolaižamās izvēlnes ekrānuzņēmums, veidojot jaunu mērījumu ar iezīmētu veidni.":::

1. Atrodiet sev atbilstošo veidni un atlasiet **Izvēlēties veidni**.

1. Pārskatiet prasītos datus un atlasiet **Sākt darbu**, ja visi dati ir pareizi.

1. Rūtī **Rediģēt nosaukumu** ievadiet sava mērījuma nosaukumu un izvades entitīju. 

1. Atlasiet **Gatavs**.

1. Sadaļā **Iestatīt laikposmu** definējiet lietojamo datu laika periodu. Izvēlieties, vai jaunajam mērījumam jāaptver visa datu kopa, atlasot **Viss laiks**, vai vēlaties, lai mērījums koncentrētos uz **Noteiktu laika periodu**.

   :::image type="content" source="media/measure-set-time-period.png" alt-text="Ekrānuzņēmums, kurā redzama laika perioda sadaļa, kad mērījumu konfigurē no veidnes.":::

1. Nākamajā sadaļā atlasiet **Pievienot datus**, lai izvēlētos darbībs un kartētu atbilstošos datus no savas *Vienotās darbības* entitījas.

    1. 1. darbība no 2: Sadaļā **Darbības veids** izvēlieties entitījas veidu, kuru vēlaties lietot. **Darbībām** atlasiet entitījas, kuras vēlaties kartēt.
    1. 2. darbība no 2: Atlasiet atribūtu no *Vienotās darbības* entitījas formulas prasītajam komponentam. Piemēram, vidējai transakcijas vērtībai tas ir komponents, kas apzīmē transakcijas vērtību. **Darbības laikspiedolam** atlasiet atribūtu no Vienotās darbības entitījas, kas apzīmē darbības datumu un laiku.
   
1. Kad datu kartēšana ir izdevusies, varat redzēt statusu kā **Pabeigts** un kartēto darbību un atribūtu nosaukumu.

1. Tagad varat atlasīt **Palaist**, lai aprēķinātu mērījuma rezultātus. Lai to precizētu vēlāk, atlasiet **Saglabāt melnrakstu**.

# <a name="business-accounts-b-to-b"></a>[Uzņēmumu konti (B2B)](#tab/b2b)

Šis līdzeklis ir pieejams tikai pasākumiem, kas izveidoti vidē, kurā kā primāro mērķauditoriju ir individuālie klienti.

---
