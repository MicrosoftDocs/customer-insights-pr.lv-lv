---
title: Attiecību izveide starp entītijām un entītiju ceļiem
description: Vairāku datu avotu entītiju relāciju izveide un pārvaldība.
ms.date: 04/14/2020
ms.reviewer: mukeshpo
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 292da986faa7f62d8aa73ed7214075612178e2e1
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269890"
---
# <a name="relationships-between-entities"></a>Relācijas starp entītijām

Relācijas palīdz entītijām izveidot savienojumu un ģenerēt datu grafiku, ja entītijām ir kopējs identifikators (ārējā atslēga), uz kuru var atsaukties no vienas entītijas uz citu. Savienotās entītijas ļauj definēt segmentus un pasākumus, par pamatu izmantojot vairākus datu avotus.

Ir divu tipu relācijas: Nerediģējamas sistēmas relācijas, kas tiek izveidotas automātiski, un pielāgotas relācijas, kuras veido un iestata lietotāji.

Atbilstības un sapludināšanas procesu laikā sistēmas relācijas tiek izveidotas, pamatojoties uz inteliģentu atbilstību. Šīs relācijas palīdz saistīt klientu profila ierakstus ar citu atbilstošo entītiju ierakstiem. Šajā shēmā ir parādīta trīs sistēmu relāciju izveide, kad klienta entītija tiek saskaņota ar papildu entītijām, lai izveidotu galīgo klienta profila entītiju.

> [!div class="mx-imgBorder"]
> ![Relāciju izveide](media/relationships-entities-merge.png "Relāciju izveide")

- Starp Klienta entītiju un Kontaktpersonas entītiju ir izveidota ***CustomerToContact* relācija**. Klienta entītija iegūst atslēgas lauku **Contact_contactId**, lai to saistītu ar kontaktpersonas entītijas atslēgas lauku **contactId**.
- Starp Klienta entītiju un Uzņēmuma entītiju ir izveidota ***CustomerToAccount* relācija**. Klienta entītija iegūst atslēgas lauku **Account_contactId**, lai to saistītu ar Uzņēmuma entītijas atslēgas lauku **accountId**.
- Starp Klienta entītiju un WebAccount entītiju ir izveidota ***CustomerToWebAccount* relācija**. Klienta entītija iegūst atslēgas lauku **WebAccount_webaccountId**, lai to saistītu ar WebAccount entītijas atslēgas lauku **webaccountId**.

## <a name="create-a-relationship"></a>Relācijas izveide

Lapā **Relācijas** definējiet pielāgotas relācijas. Katra relācija sastāv no avota entītijas (entītijas, kas glabā ārējo atslēgu) un mērķa entītijas (entītija, uz kuru norāda avota entītijas ārējā atslēga).

1. Sadaļā Auditorijas ieskati ejiet uz **Dati** > **Relācijas**.

2. Atlasiet **Jauna relācija**.

3. Rūtī **Jauna relācija** norādiet šādu informāciju:

   > [!div class="mx-imgBorder"]
   > ![Ievadiet relācijas informāciju](media/relationships-add.png "Ievadiet relācijas informāciju")

   - **Relācijas nosaukums**: nosaukums, kas atspoguļo relāciju mērķi (piemēram, **AccountWebLogs**).
   - **Apraksts**: Relācijas apraksts.
   - **Avota entītija**: Atlasiet entītiju, kas tiek izmantota kā relāciju avots (piemēram, WebLog).
   - **Kardinalitāte**: Atlasiet avota entītijas ierakstu kardinalitāti. Piemēram, "daudzi" nozīmē, ka vairāki Weblog ieraksti ir saistīti ar vienu WebAccount.
   - **Avota atslēgas lauks**: Tas norāda uz avota entītijas ārējās atslēgas lauku. Piemēram, WebLog ir **accountId** ārējās atslēgas lauks.
   - **Mērķa entītija**: Atlasiet entītiju, kas tiek izmantota kā relāciju mērķis (piemēram, WebAccount).
   - **Mērķa kardinalitāte**: Atlasiet mērķa entītijas ierakstu kardinalitāti. Piemēram, "viens" nozīmē, ka vairāki Weblog ieraksti ir saistīti ar vienu WebAccount.
   - **Mērķa atslēgas lauks**: Šis lauks norāda mērķa entītijas atslēgas lauku. Piemēram, WebAccount ir **accountId** ārējās atslēgas lauks.

> [!NOTE]
> Tiek atbalstītas tikai “daudzas pret vienu” un “viena pret vienu” relācijas. Relācijas “daudzas pret daudzām” var izveidot, izmantojot divas “daudzas pret vienu” relācijas un saišu entītiju (entītiju, kas tiek izmantota, lai savienotu avota entītiju un mērķa entītiju).

## <a name="delete-a-relationship"></a>Dzēst relāciju

1. Sadaļā Auditorijas ieskati ejiet uz **Dati** > **Relācijas**.

2. Atzīmējiet rūtiņas tām relācijām, kuras vēlaties dzēst.

3. Atlasiet **Dzēst** tabulas **Relācijas** augšpusē.

4. Apstipriniet dzēšanu.

## <a name="next-step"></a>Nākamā darbība

Sistēmas un pielāgotas relācijas tiek izmantotas, lai izveidotu segmentus, pamatojoties uz vairākiem datu avotiem, kas vairs nav sadrumstaloti. Papildinformāciju skatiet rakstā [Segmenti](segments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]