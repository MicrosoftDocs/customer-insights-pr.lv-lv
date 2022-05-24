---
title: Atlasīt avota laukus datu apvienošanai
description: Pirmais apvienošanas procesa solis ir entītiju, atribūtu, primāro atslēgu un semantisko tipu atlase, lai kartētu datus uz vienoto klienta profilu.
recommendations: false
ms.date: 04/22/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-map
- ci-match
- customerInsights
ms.openlocfilehash: a962f1353b6e25b40c60b39a81ac936873f34d92
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741004"
---
# <a name="select-source-fields-for-data-unification"></a>Atlasīt avota laukus datu apvienošanai

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

Pirmais apvienošanas solis ir to datu kopu entītiju un lauku atlase, kurus vēlaties apvienot. Atlasiet entītijas, kas satur ar klientu saistītu informāciju, piemēram, vārdu, adresi, tālruņa numuru un e-pastu. Varat atlasīt vienu vai vairākas entītijas.

## <a name="select-entities-and-fields"></a>Entītiju un lauku atlase

1. Dodieties uz **Data** > **Unify**.

   :::image type="content" source="media/m3_unify_land.png" alt-text="Ekrānuzņēmums, kurā redzama galvenās lapas vienādošana pirmās palaišanas pieredzei, izmantojot iezīmētu opciju Sākt darbu.":::

1. Atlasiet **Sākt darbu**.

1. **Lapā Avota lauki** atlasiet **Atlasīt entītijas un laukus**. Tiek **parādīta rūts Entītiju un lauku** atlase.

1. Atlasiet vismaz vienu entītiju.

1. Katrai atlasītajai entītijai norādiet laukus, kurus vēlaties izmantot, lai saskaņotu klientu ierakstus un laukus, kas jāiekļauj vienotajā profilā. Šos laukus sauc par *atribūtiem*. Nepieciešamos atribūtus var atlasīt atsevišķi no entītijas vai iekļaut visus entītijas atribūtus, atzīmējot izvēles rūtiņu entītijas līmenī. Visos atribūtos un entītijās varat meklēt atslēgvārdus, lai atlasītu nepieciešamos atribūtus, ko vēlaties kartēt.

   :::image type="content" source="media/m3_select_entities.png" alt-text="Atlasīto entītiju un atribūtu ekrānuzņēmums.":::

   Šajā piemērā mēs pievienojam kontaktpersonas **un** **klientu lojalitātes** programmas entītijas. Izvēloties šīs entītijas, varat gūt ieskatu par to, kuri tiešsaistes biznesa klienti ir lojalitātes programmas dalībnieki.

1. Atlasiet **Lietot**, lai apstiprinātu atlasi. Tiek parādītas atlasītās entītijas un atribūti.

## <a name="select-primary-key-and-semantic-type-for-attributes"></a>Atribūtu primārās atslēgas un semantiskā tipa atlasīšana

   :::image type="content" source="media/m3_select_primary.png" alt-text="Atlasīto entītiju ekrānuzņēmums ar neatlasītu primāro atslēgu." lightbox="media/m3_select_primary.png":::

Katrai entītijai veiciet šādas darbības.

1. **Izvēlieties atslēgu Primārais**. Primārā atslēga ir atribūts, kas ir unikāls entītijai. Lai atribūts būtu derīga primārā atslēga, tajā nedrīkst ietvert vērtību dublikātus, trūkstošās vērtības vai nulles vērtības. Virknes, vesela skaitļa un GUID datu tipa atribūti tiek atbalstīti kā primārie taustiņi.

1. Lai izmantotu MI modeļus viedai semantikas prognoze, ietaupītu laiku un uzlabotu precizitāti, pārliecinieties, ka **ir ieslēgta inteliģentā kartēšana**. Inteliģentā kartēšana izceļ mākslīgā intelekta semantikas ieteikumu laukā **Veids**. Ieteikto atlasi var ignorēt, izvēloties jebkuru semantisko tipu no pieejamā opciju saraksta.

1. Katram atribūtam izvēlieties semantisko **tipu**, kas vislabāk raksturo šo atribūtu, piemēram, nosaukumu, pilsētu vai e-pasta adresi.

   > [!NOTE]
   > Vienam laukam ir jākartē uz semantisko tipu *Person.FullName*, lai klienta kartē aizpildītu klienta vārdu. Pretējā gadījumā klientu kartes tiks rādītas kā anonīmas.

   1. Lai mainītu sistēmas identificēto atribūta tipu, atlasiet citu tipu. Ja tips nepastāv, izveidojiet pielāgotu semantisko tipu, atlasot **atribūta lauku Tips** un ievadot pielāgoto semantiskā tipa nosaukumu.

   1. Lai publiski pieejamiem profila attēliem vai logotipiem pievienotu atribūtu, kurā ir URL, atlasiet entītiju un lauku, kurā ir URL. Laukā **Tips** ievadiet:
      - Personai: Person.ProfileImage
      - Organizācijai: Organization.LogoImage

   1. Konta nosaukuma atribūtam laukā Tips **ievadiet "Organization.Name"**.

1. Pārskatiet atribūtus, kuros semaniskais tips tiek identificēts automātiski. Šie atribūti ir norādīti sadaļā **Pārskatīt kartētos laukus**. Solī Vienotie debitori **var kombinēt tikai tāda paša tipa atribūtus**. Semantiskos tipus izmanto, lai automātiski ieteiktu ieskatus. Pārliecinieties, vai izvēlētie tipi ir konsekventi visās atlasītajās entītijās.

1. Atribūtiem, kas netiek automātiski kartēti uz semantisko tipu, atlasiet semantiskā tipa lauku, ievadiet pielāgoto atribūta tipa nosaukumu vai atstājiet tos nekartētus. Šie atribūti ir uzskaitīti sadaļā **Datu definēšana nekartētajos laukos**.

1. Pēc katras entītijas darbību veikšanas atlasiet **Saglabāt avota laukus**.

1. Atlasiet **Tālāk**.

> [!div class="nextstepaction"]
> [Nākamā darbība: dublikātu noņemšana](remove-duplicates.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
