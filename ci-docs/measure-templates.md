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
ms.openlocfilehash: 6dc7fce78d10ba91de4b2abf54c6c6ab1c919d3a
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170782"
---
# <a name="create-measures-from-templates"></a>Pasākumu izveide no veidnēm

Lai tos izveidotu, izmantojiet iepriekš definētas bieži izmantoto [mēru](measures.md) veidnes. Veidnes tiek veidotas uz kartētajiem datiem no *Vienotās darbības* entitījas. Tāpēc, pirms no veidnes izveidojat mērījumu, pārliecinieties, ka esat konfigurējuši [klientu darbības](activities.md).

Mēru veidnes tiek atbalstītas tikai vidēs, kas paredzētas atsevišķiem **klientiem**. Lai izveidotu pielāgotus mērus vai izveidotu mērus no B līdz B, skatiet rakstu [Mēru veidotāja izmantošana](measure-builder.md).

Pieejamās mērījumu veidnes:
- Vidējā transakcijas vērtība (ATV)
- Kopējā transakciju vērtība
- Vidējie ieņēmumi dienā
- Vidējie mēneša ieņēmumi
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

1. **Sadaļā Laika perioda** iestatīšana definējiet datu laika periodu. Izvēlieties, vai jaunajam mērījumam jāaptver visa datu kopa, atlasot **Viss laiks**, vai vēlaties, lai mērījums koncentrētos uz **Noteiktu laika periodu**.

   :::image type="content" source="media/measure-set-time-period.png" alt-text="Ekrānuzņēmums, kurā redzama laika perioda sadaļa, kad mērījumu konfigurē no veidnes.":::

1. Nākamajā sadaļā atlasiet **Pievienot datus**, lai izvēlētos darbībs un kartētu atbilstošos datus no savas *Vienotās darbības* entitījas.

    1. 1. darbība no 2: Sadaļā **Darbības veids** izvēlieties entitījas veidu, kuru vēlaties lietot. Sadaļā **Darbības** atlasiet entītijas, kuras vēlaties kartēt, un pēc tam atlasiet **Tālāk**.
    1. 2. darbība no 2: Atlasiet atribūtu no *Vienotās darbības* entitījas formulas prasītajam komponentam. Piemēram, vidējai transakcijas vērtībai tas ir komponents, kas apzīmē transakcijas vērtību. Sadaļā **Aktivitātes laikspiedols** izvēlieties atribūtu no vienotās *aktivitātes* entītijas, kas attēlo darbības datumu un laiku.
    1. Atlasiet **Saglabāt**.

    Kad datu kartēšana ir veiksmīga, statuss tiek rādīts **Pabeigts** un tiek parādīts kartēto darbību un atribūtu nosaukums.

1. Atlasiet **Palaist**, lai aprēķinātu mēra rezultātus. Atlasiet **Saglabāt melnrakstu**, ja vēlaties saglabāt pašreizējo konfigurāciju, un palaidiet mēru vēlāk. Tiek **parādīta lapa Mēri**.

## <a name="next-step"></a>Nākamā darbība

Izmantojiet esošos mērus, lai izveidotu [klientu segmentu](segments.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
