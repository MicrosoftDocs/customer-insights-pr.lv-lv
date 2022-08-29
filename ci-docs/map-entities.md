---
title: Avota lauku atlasīšana datu apvienošanai
description: Pirmais apvienošanās procesa solis ir entītiju, atribūtu, primāro atslēgu un semantisko tipu atlasīšana, lai kartētu datus uz vienoto klienta profilu.
recommendations: false
ms.date: 08/12/2022
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
ms.openlocfilehash: bc120aa7a3713e1184ff278edf0942925faafa12
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304574"
---
# <a name="select-source-fields-for-data-unification"></a>Avota lauku atlasīšana datu apvienošanai

Pirmais apvienošanās solis ir atlasīt entītijas un laukus savās datu kopās, kuras vēlaties apvienot. Atlasiet entītijas, kas satur ar klientiem saistītu informāciju, piemēram, vārdu, adresi, tālruņa numuru un e-pastu. Varat atlasīt vienu vai vairākas entītijas.

[!INCLUDE [m3-first-run-note](includes/m3-first-run-note.md)]

## <a name="select-entities-and-fields"></a>Atlasīt entītijas un laukus

1. Dodieties uz **Data** > **Unify**.

   Atsevišķiem klientiem (no B-līdz C) **unify** galvenajā lapā tiek parādīts, ka tiek rādīti **darba sākšana** pirmajā darbībā — **lauki Avots**.

   :::image type="content" source="media/m3_unify_land.png" alt-text="Ekrānuzņēmums, kurā redzama galvenās lapas apvienošana pirmās palaišanas pieredzei atsevišķiem klientiem.":::

   Uzņēmumu kontiem (B-to-B) unify **galvenajā lapā tiek rādīti Unify konti**, kuros tiek rādīts **darbs** **, veicot pirmo darbību Avota** lauki **.** Unify **kontaktpersonu (priekšskatījuma)** darbības nav obligātas un gaida konta apvienošanas pabeigšanu.

   :::image type="content" source="media/b2b_unify_land.png" alt-text="Ekrānuzņēmums, kurā redzama galvenās lapas apvienošana, lai iegūtu pirmo darbības pieredzi biznesa kontiem.":::

1. Atlasiet **Sākt darbu**.

1. **Lapā Avota lauki** atlasiet **Atlasīt entītijas un laukus**. Tiek **parādīta entītiju un lauku** atlases rūts.

1. Atlasiet vismaz vienu entītiju.

1. Katrai atlasītajai entītijai nosakiet laukus, kurus vēlaties izmantot, lai atbilstu klientu ierakstiem un laukiem, kas jāiekļauj vienotajā profilā. Šos laukus sauc par *atribūtiem*. Nepieciešamos atribūtus var atlasīt atsevišķi no entītijas vai iekļaut visus entītijas atribūtus, atzīmējot izvēles rūtiņu entītijas līmenī. Visos atribūtos un entītijās varat meklēt atslēgvārdus, lai atlasītu nepieciešamos atribūtus, ko vēlaties kartēt.

   :::image type="content" source="media/m3_select_entities.png" alt-text="Atlasīto entītiju un atribūtu ekrānuzņēmums.":::

   Šajā piemērā mēs pievienojam entītijas **e-komercijaskontakti** un **loyCustomer**. Izvēloties šīs entītijas, varat gūt ieskatu par to, kuri tiešsaistes biznesa klienti ir lojalitātes programmas dalībnieki.

1. Atlasiet **Lietot**, lai apstiprinātu atlasi. Tiek rādītas atlasītās entītijas un atribūti.

## <a name="select-primary-key-and-semantic-type-for-attributes"></a>Atribūtu primārās atslēgas un semantiskā tipa atlasīšana

   :::image type="content" source="media/m3_select_primary.png" alt-text="Ekrānuzņēmums, kurā redzamas atlasītās entītijas, kuru primārā atslēga vēl nav atlasīta." lightbox="media/m3_select_primary.png":::

Katrai entītijai veiciet tālāk norādītās darbības.

1. **Izvēlieties primāro atslēgu**. Primārā atslēga ir entītijai unikāls atribūts. Lai atribūts būtu derīga primārā atslēga, tajā nedrīkst ietvert vērtību dublikātus, trūkstošās vērtības vai nulles vērtības. Virknes, vesela skaitļa un GUID datu tipa atribūti tiek atbalstīti kā primārās atslēgas.

1. Lai izmantotu AI modeļus gudrai semantikas prognoze, kas ietaupa laiku un uzlabo precizitāti, pārliecinieties, vai **ir ieslēgta inteliģentā kartēšana**. Inteliģentā kartēšana nodrošina uz AI balstītus semantiskos **ieteikumus laukā Tips**.

1. Katram atribūtam izvēlieties semantisko **tipu**, kas vislabāk raksturo šo atribūtu, piemēram, vārdu, pilsētu vai e-pasta adresi.

   > [!NOTE]
   > Sadaļā B-to-C vienam laukam ir jākartē uz semantisko tipu *Person.FullName*, lai aizpildītu klienta vārdu klienta kartē. Sadaļā B-to-B konta nosaukumam ir jābūt kartētam uz *Organization.Name*. Pretējā gadījumā klientu kartes tiks rādītas kā anonīmas.

   1. Lai ignorētu sistēmas identificēto atribūta tipu, atlasiet citu opciju. Ja tipa nav, izveidojiet pielāgotu semantisko tipu, atlasot **atribūta lauku Tips** un ievadot pielāgotā semantiskā tipa nosaukumu.

   1. Lai publiski pieejamiem profila attēliem vai logotipiem pievienotu atribūtu, kas satur URL, atlasiet entītiju un lauku, kurā ir vietrādis URL. **Laukā Tips** ievadiet šādu informāciju:
      - Personai: Person.ProfileImage
      - Organizācijai: Organization.LogoImage

1. Pārskatiet atribūtus, kuros semantiskais tips tiek automātiski identificēts. Šie atribūti ir uzskaitīti sadaļā **Pārskatīt kartētos laukus**. Darbībā Unify debitora lauki var apvienot tikai tāda paša tipa **atribūtus**. Semantiskie tipi tiek izmantoti, lai automātiski ieteiktu ieskatus. Pārliecinieties, vai izvēlētie tipi ir konsekventi visās atlasītajās entītijās.

1. Atribūtiem, kas netiek automātiski kartēti uz semantisko tipu, atlasiet semantiskā tipa lauku, ievadiet sava pielāgotā atribūta tipa nosaukumu vai atstājiet tos nekartētus. Šie atribūti ir uzskaitīti sadaļā **Datu definēšana neapgrieztajos laukos**.

1. Pēc katras entītijas darbību veikšanas atlasiet **Saglabāt avota laukus**.

1. Atlasiet **Tālāk**.

> [!div class="nextstepaction"]
> [Nākamais solis: Dublikātu noņemšana](remove-duplicates.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
