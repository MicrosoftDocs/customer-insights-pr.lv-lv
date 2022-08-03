---
title: Attiecību izveide starp entītijām un entītiju ceļiem
description: Vairāku datu avotu entītiju relāciju izveide un pārvaldība.
ms.date: 09/27/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
searchScope:
- ci-semantic-mapping
- ci-entities
- ci-relationships
- ci-activities
- ci-activities-wizard
- ci-measures
- ci-segments
- ci-segment-builder
- ci-measure-builder
- ci-measure-template
- ci-permissions
- customerInsights
ms.openlocfilehash: e622e5fa0b5738e31db1c668d95312adbc4f7d36
ms.sourcegitcommit: ad74ace653db9a25fce4343adef7db1c9b0d8904
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 07/21/2022
ms.locfileid: "9183575"
---
# <a name="relationships-between-entities-and-entity-paths"></a>Attiecību izveide starp entītijām un entītiju ceļiem

Attiecības savieno entītijas un definē datu grafiku, kad entītijas koplieto kopēju identifikatoru — ārēju atslēgu. Šī ārējā atslēga var tikt atsaukties no vienas entītijas uz citu. Savienotās entītijas ļauj definēt segmentus un pasākumus, par pamatu izmantojot vairākus datu avotus.

Ir trīs attiecību tipi: 
- Nerediģējamas sistēmas relācijas sistēma izveido kā daļu no datu apvienošanas procesa
- Nerediģējamas pārmantotas relācijas tiek veidotas automātiski no datu avotu uzņemšanas
- Rediģējamas pielāgotas relācijas izveido un konfigurē lietotāji

## <a name="non-editable-system-relationships"></a>Nerediģējamas sistēmu attiecības

Datu apvienošanas laikā sistēmas attiecības tiek izveidotas automātiski, pamatojoties uz informācijas atbilstību. Šīs relācijas palīdz saistīt klientu profila ierakstus ar citu atbilstošo entītiju ierakstiem. Šajā shēmā parādīta trīs sistēmas attiecību izveide. Lai izveidotu vienoto *Klienta* entītiju, klienta entītija tiek saskaņoti ar citām entītijām.

:::image type="content" source="media/relationships-entities-merge.png" alt-text="Shēma ar klienta entītijas attiecību ceļiem ar trim 1-n attiecībām.":::

- Starp *Klienta* entītiju un *Kontaktpersonas* entītiju ir izveidota ***CustomerToContact* relācija**. *Klienta* entītija iegūst atslēgas lauku **Contact_contactID**, lai to saistītu ar *Kontaktpersonas* entītijas atslēgas lauku **contactID**.
- Starp *Klienta* entītiju un *Kontaktpersonas* entītiju ir izveidota ***CustomerToContact* relācija**. *Klienta* entītija iegūst atslēgas lauku **Account_accountID**, lai to saistītu ar *Uzņēmuma* entītijas atslēgas lauku **accountID**.
- Starp *Klienta* entītiju un *WebAccount* entītiju ir izveidota ***CustomerToWebAccount* relācija**. *Klienta* entītija iegūst atslēgas lauku **WebAccount_webaccountID**, lai to saistītu ar *WebAccount* entītijas atslēgas lauku **webaccountID**.

## <a name="non-editable-inherited-relationships"></a>Nerediģējamas mantojamas attiecības

Datu ietveršanas procesa laikā sistēma pārbauda datu avotus esošām attiecībām. Ja attiecību nav, sistēma tās izveido automātiski. Šīs attiecības tiek lietotas arī lejupstraumes procesos.

## <a name="create-a-custom-relationship"></a>Izveidot pielāgotu relāciju

Attiecības sastāv no *avota entītijas*, kurā ir iekļaujošā atslēga un *mērķa entītija*, uz ko norāda avota entītijas nosakošā atslēga. 

1. Dodieties uz **Dati** > **Attiecības**.

2. Atlasiet **Jauna relācija**.

3. Rūtī **Jauna relācija** norādiet šādu informāciju:

   :::image type="content" source="media/relationship-add.png" alt-text="Jauna attiecību sānu rūts ar tukšiem ievades laukiem.":::

   - **Relāciju nosaukums**: nosaukums, kas atspoguļo attiecību mērķi. Piemērs: CustomerToSupportCase.
   - **Apraksts**: Relācijas apraksts.
   - **Avota entītija**: entītija, kas attiecībās tiek izmantota kā relāciju avots. Piemērs: SupportCase.
   - **Mērķa entītija**: entītija, kas attiecībās tiek izmantota kā relāciju mērķis. Piemērs: klients.
   - **Avota kardinalitāte**: avota entītijas kardinalitāte. Kardinalitāte apraksta iespējamo elementu skaitu kopā. Tā vienmēr ir saistīta ar mērķa kardinalitāti. Var izvēlēties starp **vienu** un **vairākiem**. Tiek atbalstītas tikai “daudzas pret vienu” un “viena pret vienu” relācijas.  
     - Daudzi pret vienu: vairāki avota ieraksti var būt saistīti ar vienu mērķa ierakstu. Piemērs: vairāki atbalsta pieteikumi no viena klienta.
     - Viens pret vienu: viens avota ieraksts ir saistīts ar vienu mērķa ierakstu. Piemērs: viens atsevišķa klienta gaidīšanas ID.

     > [!NOTE]
     > Attiecības daudzi pret daudziem var izveidot, izmantojot divas attiecības daudzi pret vienu, un saistot entītiju, kas savieno avota entītiju un mērķa entītiju.

   - **Mērķa kardinalitāte**: mērķa entītijas ierakstu kardinalitāte.
   - **Avota atslēgas lauks**: ārējās atslēgas lauks avota entītijā. Piemērs: SupportCase izmanto **CaseID** kā ārējās atslēgas lauku.
   - **Mērķa atslēgas lauks**: mērķa entītijas atslēgas lauks. Piemērs: Klients izmanto **CustomerID** kā atslēgas lauku.

4. Lai izveidotu pielāgotu relāciju, atlasiet **Saglabāt**.

## <a name="set-up-account-hierarchies"></a>Iestatīt konta hierarhijas

Vides, kas ir konfigurētas, lai izmantotu biznesa kontus kā primāro mērķauditoriju, var konfigurēt kontu hierarhijas saistītiem biznesa kontiem. Piemēram, uzņēmums, kam ir atsevišķas struktūrvienības.

Organizācijas veido uzņēmumu hierarhijas, lai labāk pārvaldītu uzņēmumus un to attiecības citam ar citu. Customer Insights atbalsta vecāku un bērnu kontu hierarhijas, kas jau pastāv uzņemtajos klientu datos. Piemēram, uzņēmumi no Dynamics 365 Sales. Šīs hierarhijas var konfigurēt **lapā Relācijas**.

1. Dodieties uz **Dati** > **Attiecības**.
1. Atlasiet cilni **Uzņēmuma hierarhija**.
1. Atlasiet **Jauna uzņēmuma hierarhija**.
1. **Uzņēmumu hierarhijas** rūtī norādiet hierarhijas nosaukumu. Sistēma izveido izvades entītijas nosaukumu, bet to var mainīt.
1. Atlasiet entītiju, kurā ir iekļauta jūsu uzņēmumu hierarhija. Parasti tā atrodas tajā pašā entītijā, kurā ir uzņēmumi.
1. Atlasītajā entītijā **atlasiet konta UID** un **vecāku UID**.
1. Atlasiet **Saglabāt**, lai pabeigtu konta hierarhiju.

## <a name="manage-existing-relationships"></a>Pārvaldīt esošās relācijas

Dodieties uz **lapu Relācijas**, lai skatītu visas izveidotās relācijas, to avota entītiju, mērķa entītiju un kardinalitāti.

:::image type="content" source="media/relationships-list.png" alt-text="Attiecību un opciju saraksts attiecību lapas darbību joslā.":::

Izmantojiet **opcijas Filtrēt pēc** vai **Meklēt relācijas**, lai atrastu noteiktu relāciju. Lai skatītu tīkla diagrammu par esošajām relācijām un to kardinalitāti, atlasiet [**Vizualizētājs**](#explore-the-relationship-visualizer).

Atlasiet relāciju, lai skatītu pieejamās darbības:
- **Rediģēšana**: atjauniniet pielāgotu attiecību rekvizītus rediģēšanas rūtī un saglabājiet izmaiņas.
- **Dzēšana**: dzēsiet pielāgotas attiecības.
- **Skatīt**: skatiet sistēmas izveidotās un mantotās attiecības.

### <a name="explore-the-relationship-visualizer"></a>Izpētīt relāciju visualatoru

Relāciju vizualizētājs parāda esošo attiecību tīkla diagrammu starp savienotajām entītijām un to kardinalitāti. Tā arī vizualizē attiecību ceļu.

:::image type="content" source="media/relationship-visualizer.png" alt-text="Relāciju visualizēšanas tīkla shēmas ekrānuzņēmumu ar savienojumiem starp saistītajām entītijām.":::

Lai pielāgotu skatu, lodziņu atrašanās vietu var mainīt, velkot tos uz pamatnes. Citas iespējas ietver: 
- **Eksportēt kā attēlu**: saglabāt pašreizējo skatu kā attēla failu.
- **Mainīt uz horizontālo/vertikālo izkārtojumu**: mainiet entītiju un attiecību līdzinājumu.
- **Rediģēšana**: atjauniniet pielāgotu attiecību rekvizītus rediģēšanas rūtī un saglabājiet izmaiņas.

## <a name="relationship-paths"></a>Attiecību ceļi

Attiecību ceļš apraksta entītijas, kas saistītas ar avota entītijas un mērķa entītijas attiecībām. Tas tiek izmantots, veidojot segmentu vai mēru, kas ietver entītijas, kas nav vienotā profila entītija, un ir vairākas opcijas, lai sasniegtu vienoto profila entītiju. Dažādi attiecību ceļi var iegūt atšķirīgus rezultātus.

Piemēram, entītijai *eCommerce_eCommercePurchases* ir šādas attiecības ar vienoto profila entītiju *Klients*:

- eCommerce_eCommercePurchases > Klients
- eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > Klients
- eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > loyaltyScheme_loyCustomers > Klients

Attiecību ceļš nosaka, kuras entītijas var izmantot, izveidojot kārtulas mērījumiem vai segmentiem. Izvēloties opciju ar garāko attiecību ceļu, iespējams, tiks iegūts mazāk rezultātu, jo atbilstības noteikšanas ierakstiem ir jābūt daļai no visām entītijām. Šajā piemērā klientam ir jāiegādājas preces, izmantojot e-tirdzniecības (eCommerce_eCommercePurchases), pārdošanas punktu (POS_posPurchases), un jāpiedalās mūsu lojalitātes programmā (loyaltyScheme_loyCustomers). Izvēloties pirmo opciju, iespējams, saņemsiet vairāk rezultātu, jo klientiem ir nepieciešama tikai viena papildu entītija.

### <a name="direct-relationship"></a>Tiešās attiecības

Attiecības tiek klasificētas kā **tiešas attiecības**, ja avota entītija ir saistīta ar mērķa entītiju ar tikai vienu attiecību.

Piemēram, ja darbības entītija, kas saukta par *eCommerce_eCommercePurchases*, tiek pievienota mērķa entītijai *eCommerce_eCommerceContacts* tikai ar *ContactId*, tā ir tieša attiecība,

:::image type="content" source="media/direct_Relationship.png" alt-text="Avota entītija izveido tiešu savienojumu ar mērķa entītiju.":::

#### <a name="multi-path-relationship"></a>Vairākceļu attiecības

**Vairākceļu attiecības** ir īpašs tiešo attiecību tips, kas avota entītiju savieno ar vairākām mērķa entītijām.

Piemēram, ja darbības entītija, saukta par *eCommerce_eCommercePurchases*, ir saistīta ar divām mērķa entītijām, gan *eCommerce_eCommerceContacts*, gan *loyaltyScheme_loyCustomers*, tā ir vairākceļu attiecība.

:::image type="content" source="media/multi-path_relationship.png" alt-text="Izmantojot attiecības ar vairākām entītijām, avota entītija izveido tiešu savienojumu ar vairākām mērķa entītijām.":::

### <a name="indirect-relationship"></a>Netiešās attiecības

Attiecības tiek klasificētas kā **netiešas attiecības**, ja avota entītija ir saistīta ar vienu vai vairākām papildu entītijām, pirms tiek saistīta ar mērķa entītiju.

#### <a name="multi-hop-relationship"></a>Vairāklēcienu attiecības

**Vairāklēcienu attiecības** ir *netiešas attiecības*, kas ļauj izveidot avota entītijas savienojumu ar mērķa entītiju, izmantojot vienu vai vairākas citas starpnieka entītijas.

Piemēram, ja darbības entītija, saukta par *eCommerce_eCommercePurchasesWest*, izveido savienojumu ar entītiju *eCommerce_eCommercePurchasesEast* un pēc tam izveido savienojumu ar mērķa entītiju *eCommerce_eCommerceContacts*, tā ir vairāklēcienu attiecība.

:::image type="content" source="media/multi-hop_relationship.png" alt-text="Avota entītija izveido tiešu savienojumu ar mērķa entītiju, izmantojot starpnieka entītiju.":::

### <a name="multi-hop-multi-path-relationship"></a>Vairāklēcienu, vairākceļu attiecība

Vairāklēcienu un vairākceļu attiecības var izmantot kopā, lai izveidotu **vairāklēcienu, vairākceļu attiecības**. Šis īpašais tips apvieno **vairāklēcienu** un **vairākceļu attiecību** funkcijas. Tās ļauj izveidot savienojumu ar vairākām mērķa entītijām, izmantojot starpnieka entītijas.

Piemēram, ja darbības entītija, saukta par *eCommerce_eCommercePurchasesWest*, izveido savienojumu ar entītiju *eCommerce_eCommercePurchasesEast* un pēc tam izveido savienojumu ar divām mērķa entītijām, gan *eCommerce_eCommerceContacts*, gan *loyaltyScheme_loyCustomers*, tā ir vairāklēcienu, vairākceļu attiecība.

:::image type="content" source="media/multi-hop_multi-path_relationship.png" alt-text="Avota entītija izveido tiešu savienojumu ar vienu mērķa entītiju un izveido savienojumu ar citu mērķa entītiju, izmantojot starpnieka entītiju.":::

## <a name="next-step"></a>Nākamā darbība

Sistēmas un pielāgotas attiecības tiek izmantotas, lai [izveidotu segmentus](segments.md) un [pasākumus](measures.md), pamatojoties uz vairākiem datu avotiem, kas vairs nav pielāgoti.

[!INCLUDE [footer-include](includes/footer-banner.md)]
