---
title: Pasākumu izveide no veidnēm
description: Definējiet mērus, izmantojot veidnes bieži lietotiem lietošanas gadījumiem.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.author: wameng
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-measure-template
- customerInsights
ms.openlocfilehash: f6bcdfc45a49c36f22d6ebc6e919f43b27f899d8
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 06/29/2022
ms.locfileid: "9051692"
---
# <a name="create-measures-from-templates"></a>Pasākumu izveide no veidnēm

Lai tos izveidotu, varat izmantot iepriekš definētas bieži izmantoto [mēru](measures.md) veidnes. Detalizēti veidņu apraksti un vadība palīdzēs jums sekmīgi izveidot mērījumu. Veidnes tiek veidotas uz kartētajiem datiem no *Vienotās darbības* entitījas. Tāpēc, pirms no veidnes izveidojat mērījumu, pārliecinieties, ka esat konfigurējuši [klientu darbības](activities.md).

Lai izveidotu pielāgotus mērus, skatiet rakstu [Mēru veidotāja izmantošana, lai izveidotu mērus no nulles](measure-builder.md).

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

## <a name="build-a-new-measure-using-a-template"></a>Jauna mēra izveide, izmantojot veidni

1. Dodieties uz **sadaļu Pasākumi**.

1. Atlasiet **Jauns** un atlasiet **Izvēlieties veidni**.

   :::image type="content" source="media/measure-use-template.png" alt-text="Nolaižamās izvēlnes ekrānuzņēmums, veidojot jaunu mērījumu ar iezīmētu veidni.":::

1. Atrodiet sev atbilstošo veidni un atlasiet **Izvēlēties veidni**.

1. Pārskatiet prasītos datus un atlasiet **Sākt darbu**, ja visi dati ir pareizi.

1. Atlasiet **Rediģēt detalizētu informāciju** blakus Vienumam Novērtēt nosaukumu. Norādiet pasākuma nosaukumu. Pēc izvēles pievienojiet [pasākumam tagus](work-with-tags-columns.md#manage-tags).

   :::image type="content" source="media/measures_edit_details.png" alt-text="Dialoglodziņš Detalizētas informācijas rediģēšana.":::

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
