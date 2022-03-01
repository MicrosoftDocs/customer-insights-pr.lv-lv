---
title: Attiecību izveide starp entītijām un entītiju ceļiem
description: Vairāku datu avotu entītiju relāciju izveide un pārvaldība.
ms.date: 06/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: d5b9566ec88096fec31d8e164a51598159ec26d4
ms.sourcegitcommit: ece48f80a7b470fb33cd36e3096b4f1e9190433a
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 06/03/2021
ms.locfileid: "6171173"
---
# <a name="relationships-between-entities"></a>Relācijas starp entītijām

Attiecības savieno entītijas un definē datu grafiku, kad entītijas koplieto kopēju identifikatoru — ārēju atslēgu. Šī ārējā atslēga var tikt atsaukties no vienas entītijas uz citu. Savienotās entītijas ļauj definēt segmentus un pasākumus, par pamatu izmantojot vairākus datu avotus.

Ir trīs attiecību tipi: 
- Nerediģējamas sistēmas attiecības, ko sistēma izveidoja kā daļu no datu apvienošanas procesa
- Nerediģējamas mantotas attiecības, kas tiek automātiski izveidotas, ietverot datu avotus 
- Rediģējamas pielāgotas attiecības, ko izveido un konfigurē lietotāji

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

1. Sadaļā Auditorijas ieskati ejiet uz **Dati** > **Relācijas**.

2. Atlasiet **Jauna relācija**.

3. Rūtī **Jauna relācija** norādiet šādu informāciju:

   :::image type="content" source="media/relationship-add.png" alt-text="Jauna attiecību sānu rūts ar tukšiem ievades laukiem.":::

   - **Relāciju nosaukums**: nosaukums, kas atspoguļo attiecību mērķi. Piemērs: CustomerToSupportCase.
   - **Apraksts**: Relācijas apraksts.
   - **Avota entītija**: entītija, kas attiecībās tiek izmantota kā relāciju avots. Piemērs: SupportCase.
   - **Mērķa entītija**: entītija, kas attiecībās tiek izmantota kā relāciju mērķis. Piemērs: klients.
   - **Avota kardinalitāte**: norādiet avota entītijas kardinalitāti. Kardinalitāte apraksta iespējamo elementu skaitu kopā. Tā vienmēr ir saistīta ar mērķa kardinalitāti. Var izvēlēties starp **vienu** un **vairākiem**. Tiek atbalstītas tikai “daudzas pret vienu” un “viena pret vienu” relācijas.  
     - Daudzi pret vienu: vairāki avota ieraksti var būt saistīti ar vienu mērķa ierakstu. Piemērs: vairāki atbalsta pieteikumi no viena klienta.
     - Viens pret vienu: viens avota ieraksts ir saistīts ar vienu mērķa ierakstu. Piemērs: viens atsevišķa klienta gaidīšanas ID.

     > [!NOTE]
     > Attiecības daudzi pret daudziem var izveidot, izmantojot divas attiecības daudzi pret vienu, un saistot entītiju, kas savieno avota entītiju un mērķa entītiju.

   - **Mērķa kardinalitāte**: Atlasiet mērķa entītijas ierakstu kardinalitāti. 
   - **Avota atslēgas lauks**: avota entītijas avota atslēgas lauks. Piemērs: SupportCase kā noslogotu galveno lauku var izmantot CaseID.
   - **Mērķa atslēgas lauks**: Šis lauks norāda mērķa entītijas atslēgas lauku. Piemēram, klients var izmantot atslēgas lauku **CustomerID**.

4. Lai izveidotu pielāgotu relāciju, atlasiet **Saglabāt**.

## <a name="view-relationships"></a>Skatīt relācijas

Lapā Attiecības ir uzskaitītas visas izveidotās relācijas. Katra rinda ir attiecības, kurās ir iekļauta arī detalizēta informācija par avota entītiju, mērķa entītiju un jucību. 

:::image type="content" source="media/relationships-list.png" alt-text="Attiecību un opciju saraksts attiecību lapas darbību joslā.":::

Šajā lapā ir opciju kopa esošām un jaunām attiecībām: 
- **Jaunas attiecības**: [Izveidot pielāgotas attiecības](#create-a-custom-relationship).
- **Visualizētājs**: [izpētiet relāciju vizualizētāju](#explore-the-relationship-visualizer), lai redzētu esošo attiecību tīkla diagrammu un to kardinalitāti.
- **Filtrēt pēc**: izvēlieties sarakstā rādīto attiecību tipu.
- **Meklēšanas attiecības**: izmantojiet teksta meklēšanu, kas balstīta uz attiecību rekvizītiem.

### <a name="explore-the-relationship-visualizer"></a>Izpētīt relāciju visualatoru

Relāciju vizualizētājs parāda esošo attiecību tīkla diagrammu starp savienotajām entītijām un to kardinalitāti.

Lai pielāgotu skatu, lodziņu atrašanās vietu var mainīt, velkot tos uz pamatnes.

:::image type="content" source="media/relationship-visualizer.png" alt-text="Relāciju visualizēšanas tīkla shēmas ekrānuzņēmumu ar savienojumiem starp saistītajām entītijām.":::

Pieejamās opcijas: 
- **Eksportēt kā attēlu**: saglabāt pašreizējo skatu kā attēla failu.
- **Mainīt uz horizontālo/vertikālo izkārtojumu**: mainiet entītiju un attiecību līdzinājumu.
- **Rediģēšana**: atjauniniet pielāgotu attiecību rekvizītus rediģēšanas rūtī un saglabājiet izmaiņas.

## <a name="manage-existing-relationships"></a>Pārvaldīt esošās relācijas 

Lapā Attiecības katra attiecība ir apzīmēta ar rindu. 

Atlasiet relāciju un izvēlieties vienu no šīm opcijām: 
 
- **Rediģēšana**: atjauniniet pielāgotu attiecību rekvizītus rediģēšanas rūtī un saglabājiet izmaiņas.
- **Dzēšana**: dzēsiet pielāgotas attiecības.
- **Skatīt**: skatiet sistēmas izveidotās un mantotās attiecības. 

## <a name="next-step"></a>Nākamā darbība

Sistēmas un pielāgotas relācijas tiek izmantotas, lai [izveidotu segmentus](segments.md), pamatojoties uz vairākiem datu avotiem, kas vairs nav sadrumstaloti.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
