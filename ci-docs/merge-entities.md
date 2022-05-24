---
title: Klienta vai konta lauku apvienošana
description: Sapludiniet entītijas, lai izveidotu vienotus klientu profilus.
recommendations: false
ms.date: 05/04/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-merge
- ci-match
- ci-relationships
- customerInsights
ms.openlocfilehash: 78e2528d4a3058f879d83952f72ed88a1da065b6
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 05/11/2022
ms.locfileid: "8740866"
---
# <a name="unify-customer-fields"></a>Klientu lauku apvienošana

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

Šajā apvienošanas procesa solī izvēlieties un izslēdziet atribūtus, ko sapludināt vienotajā profila entītijā. Piemēram, ja trim entītijām bija e-pasta dati, iespējams, vēlēsities paturēt visus trīs atsevišķos e-pasta laukus vai sapludināt tos vienā vienotā profila e-pasta laukā. Dažus atribūtus sistēma automātiski apvieno. Varat izveidot stabilus un unikālus klientu ID un grupēt saistītos profilus klasterī.

:::image type="content" source="media/m3_unify.png" alt-text="Datu apvienošanas procesa sapludināšanas lapa, kurā redzama tabula ar sapludinātiem laukiem, kas definē vienoto klienta profilu.":::

## <a name="review-and-update-the-customer-fields"></a>Pārskatiet un atjauniniet debitora laukus

1. Pārskatiet lauku sarakstu, kas tiks vienoti **tabulas cilnē** Debitors. Ja nepieciešams, veiciet jebkādas izmaiņas.

   1. Jebkuram kombinētam laukam var:
      - [Labot](#edit-a-merged-field)
      - [Pārdēvēt](#rename-fields)
      - [Atdalīt](#separate-merged-fields)
      - [Neiekļaut](#exclude-fields)
      - [Pārvietoties uz augšu vai uz leju](#change-the-order-of-fields)

   1. Jebkuram atsevišķam laukam varat:
      - [Lauku apvienošana](#combine-fields-manually)
      - [Lauku grupas kombinēšana](#combine-a-group-of-fields)
      - [Pārdēvēt](#rename-fields)
      - [Neiekļaut](#exclude-fields)
      - [Pārvietoties uz augšu vai uz leju](#change-the-order-of-fields)

1. Pēc izvēles [ģenerējiet debitora ID konfigurāciju](#configure-customer-id-generation).

1. Pēc izvēles [grupu profili mājsaimniecībās vai kopās](#group-profiles-into-households-or-clusters).

> [!div class="nextstepaction"]
> [Nākamais solis: pārskatiet apvienošanu](review-unification.md)

### <a name="edit-a-merged-field"></a>Rediģējiet sapludinātu lauku

1. Atlasiet sapludinātu lauku un izvēlieties **Rediģēt**. Tiek parādīta lauku apvienošanas rūts.

1. Norādiet, kā laukus apvienot vai sapludināt no vienas no trim opcijām:
    - **Nozīme**: Norāda kā uzvarētāja vērtību, pamatojoties uz iesaistītajā laukā norādīto rangu. Tā ir noklusējuma sapludināšanas opcija. Atlasiet **Pārvietot uz augšu/uz leju**, lai iestatītu svarīguma reitingu.

      :::image type="content" source="media/importance-merge-option.png" alt-text="Svarīguma opcija sapludināšanas lauku dialoglodziņā.":::

    - **Jaunākais** : identificē uzvarētāja vērtību, pamatojoties uz visizplatītāko resnību. Lai definētu rekvizītus, nepieciešama katras sapludināšanas lauku tvērumā iesaistītās entītijas datums vai skaitlisks lauks.

      :::image type="content" source="media/recency-merge-option.png" alt-text="Svarīguma opcija sapludināšanas lauku dialoglodziņā.":::

    - **Jaunākais** : identificē uzvarētāja vērtību, pamatojoties uz visizplatītāko resnību. Lai definētu rekvizītus, nepieciešama katras sapludināšanas lauku tvērumā iesaistītās entītijas datums vai skaitlisks lauks.

1. Sapludināšanas procesā varat pievienot papildu laukus.

1. Sapludināto lauku var pārdēvēt.

1. Atlasiet **Labi**, lai piemērotu izmaiņas.

### <a name="rename-fields"></a>Lauku pārdēvēšana

Mainiet sapludināto vai atsevišķo lauku parādāmo nosaukumu. Izvades entītijas nosaukumu nevar mainīt.

1. Atlasiet lauku un izvēlieties **Pārdēvēt**.

1. Ievadiet jauno parādāmo nosaukumu.

1. Atlasiet **Gatavs**.

### <a name="separate-merged-fields"></a>Atdalīt sapludinātos laukus

Lai atdalītu sapludinātos laukus, atrodiet atribūtu tabulā. Atsevišķie lauki vienotā klienta profilā tiek rādīti kā atsevišķi datu punkti.

1. Atlasiet sapludināto lauku un izvēlieties **Atdalīt laukus**.

1. Apstipriniet atdali.

### <a name="exclude-fields"></a>Izslēgt laukus

Izslēgt sapludinātu vai atsevišķu lauku no vienotā debitora profila. Ja lauks tiek izmantots citos procesos, piemēram, segmentā, pirms lauka izslēgšanas no klienta profila, noņemiet to no šiem procesiem.

1. Atlasiet lauku un izvēlieties **Izslēgt**.

1. Apstipriniet izslēgšanu.

Lai skatītu visu izslēgto lauku sarakstu, atlasiet **Izslēgtie lauki**. Ja nepieciešams, varat izlasīt izslēgto lauku.

### <a name="change-the-order-of-fields"></a>Lauku secības maiņa

Dažās entītijās ir detalizētāka informācija nekā citās. Ja entītijā ir ietverti jaunākie dati par kādu lauku, sapludinot vērtības, par to var noteikt prioritātes citās entītijās.

1. Atlasiet lauku.
  
1. Izvēlieties **Pārvietot uz augšu/uz leju**, lai iestatītu pasūtījumu, vai velciet un nometiet to vēlamajā pozīcijā.

### <a name="combine-fields-manually"></a>Lauku manuāla kombinēšana

Apvienojiet atdalītos laukus, lai izveidotu sapludinātu atribūtu.

1. Atlasiet **Apvienot** > **laukus**. Tiek parādīta lauku apvienošanas rūts.

1. Nolaižamajā izvēlnē **Lauku apvienošana** norādiet sapludināšanas uzvarētāja politiku.

1. Atlasiet **Pievienot lauku**, lai apvienotu citus laukus.

1. Norādiet **Nosaukumu** un **Izvades lauka nosaukumu**.

1. Atlasiet **Labi**, lai piemērotu izmaiņas.

### <a name="combine-a-group-of-fields"></a>Lauku grupas kombinēšana

Lauku grupu uzskatīt par vienu vienību. Piemēram, ja mūsu ierakstos ir lauki Adrese1, Adrese2, Pilsēta, Valsts un Zip, mēs nevēlamies apvienoties cita ieraksta adresē2, domājot, ka tas padarītu mūsu datus pilnīgākus.

1. Atlasiet **Apvienot** > **lauku** grupu.

1. Norādiet sapludināšanas uzvarētāja politiku rangu **grupās pēc** nolaižamā saraksta.

1. Atlasiet **Pievienot** un izvēlieties, vai laukiem vēlaties pievienot papildu laukus vai grupas.

1. Norādiet **nosaukumu** un izvades **nosaukumu** katram kombinētajam laukam.

1. Norādiet **lauku grupas nosaukumu**.

1. Atlasiet **Labi**, lai piemērotu izmaiņas.

## <a name="configure-customer-id-generation"></a>Konfigurēt debitora ID ģenerēšanu

Definējiet, kā ģenerēt debitora ID vērtības, unikālos debitora profila identifikatorus. Datu apvienošanas procesa lauku apvienošanas solis unificē unikālo klienta profila identifikatoru. Identifikators ir *CustomerId* klienta *entītijā*, kas izriet no datu apvienošanas procesa.

*CustomerId* pamatā ir pirmatnējo atslēgu, kas nav null, pirmās vērtības jaukšana. Šīs atslēgas nāk no entītijām, kas tiek izmantotas datu apvienošanā, un tās ietekmē atbilstības secība.Tātad ģenerētais debitora ID var mainīties, mainoties atbilstības secības primārajai entītijai, mainās primārā atslēgas vērtība. Primārā atslēgas vērtība ne vienmēr pārstāv vienu un to pašu debitoru.

Konfigurējot stabilu klienta ID, varat izvairīties no šādas uzvedības.

1. Atlasiet cilni **Atslēgas**.

1. Novietojiet kursoru **rindā CustomerId** un atlasiet **Konfigurēt**.
   :::image type="content" source="media/customize-stable-id.png" alt-text="Vadīklu, lai pielāgotu ID ģenerēšanu.":::

1. Atlasiet līdz pieciem laukiem, kuros būs unikāls klienta ID un kuri ir ar daudz lielāku stabilitāti. Ieraksti, kas neatbilst jūsu konfigurācijai, tā vietā izmanto sistēmas konfigurētu ID.  

1. Atlasiet **Gatavs**.

## <a name="group-profiles-into-households-or-clusters"></a>Grupējiet profilus mājsaimniecībās vai klasteros

Varat definēt kārtulas, lai saistītus profilus grupētu klasterī. Pašlaik ir pieejami divu veidu klasteri — mājsaimniecības un pielāgoti klasteri. Sistēma automātiski izvēlas barību ar iepriekš definētām kārtulām, ja *Klienta* entītija ietver semantiskos laukus *Person.LastName* un *Location.Address*. Klasteru var izveidot arī ar savām kārtulām un nosacījumiem, kas līdzīgi [atbilstības kārtulām](match-entities.md#define-rules-for-match-pairs).

1. Atlasiet **Detalizētās** > **izveides klasteris**.

   :::image type="content" source="media/create-cluster.png" alt-text="Vadīkla, lai izveidotu jaunu klasteru.":::

1. Izvēlieties kādu no **Mājsaimniecībām** vai **Pielāgotu klasteru**. Ja semantiskie lauki *Person.LastName* un *Location.Address* ir *Klienta* entītijā, tiek automātiski atlasīta mājsaimniecība.

1. Norādiet klastera nosaukumu un atlasiet **Gatavs**.

1. Atlasiet cilni **Klasteri**, lai atrastu izveidoto klasteru.

1. Norādiet kārtulas un nosacījumus, lai definētu klasteru.

1. Atlasiet **Gatavs**. Klasteris tiek izveidots, kad apvienošanas process ir pabeigts. Klastera identifikatori entītijai *Klients* tiek pievienoti kā jauni lauki.

> [!div class="nextstepaction"]
> [Nākamais solis: pārskatiet apvienošanu](review-unification.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
