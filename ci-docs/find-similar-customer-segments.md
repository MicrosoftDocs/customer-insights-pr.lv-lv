---
title: Atrast līdzīgus klientus ar AI (satur video)
description: Atrodiet līdzīgu klientu segmentus, izmantojot mākslīgo intelektu
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-segment-builder
- ci-segment-insights
- customerInsights
ms.openlocfilehash: 7877349817829f7486a63a1355a81361e1cb2c13
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643385"
---
# <a name="similar-customers-preview"></a>Līdzīgi klienti (priekšskatījums)

Šis līdzeklis ļauj atrast līdzīgus klientus jūsu klientu bāzē, izmantojot mākslīgo intelektu. Lai izmantotu šo līdzekli, ir jābūt izveidotam vismaz vienam segmentam. Izvēršot esoša segmenta kritērijus, varat atrast šim segmentam līdzīgus klientus.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWOFou]

> [!NOTE]
> *Atrast līdzīgus klientus* izmanto automatizētus līdzekļus, lai izvērtētu datus un veiktu prognozes, pamatojoties uz šiem datiem, un tādējādi šo līdzekli var izmantot kā profilēšanas metodi, saskaņā ar šī jēdziena definīciju Vispārīgajā datu aizsardzības regulā ("VDAR"). Šī līdzekļa izmantošana klienta datu apstrādei var būt pakļauta VDAR vai citiem likumiem vai noteikumiem. Jūs esat atbildīgs par to, ka jūsu Dynamics 365 Customer Insights lietojums, ieskaitot prognozes, atbilst visiem piemērojamiem likumiem un noteikumiem, ieskaitot likumus, kas attiecas uz privātumu, personas datiem, biometrijas datiem, datu aizsardzību un saziņas konfidencialitāti.

## <a name="finding-similar-customers"></a>Līdzīgu klientu atrašana

1. Dodieties uz **Segmenti** un atlasiet segmentu, uz kuru vēlaties balstīt jauno segmentu. Tas būs jūsu *avota segments*.

1. Darbību joslā atlasiet **Atrast līdzīgus klientus**.

1. Pārskatiet jaunā segmenta ierosināto nosaukumu un, ja nepieciešams, to mainiet.

1. Pēc izvēles pievienojiet [atzīmes](work-with-tags-columns.md#manage-tags) jaunajam segmentam.

1. Pārskatiet laukus, kuri definē jauno segmentu. Šie lauki definē pamatu, uz kura sistēma centīsies atrast jūsu avota segmentam līdzīgus klientus. Sistēma pēc noklusējuma atlasīs ieteiktos laukos.
  Lauki, kuri var ievērojami samazināt modeļa veiktspēju, tiek automātiski izslēgti:
  
   - Lauki ar šādiem datu tipiem: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType
   - Lauki, kuros kardināls (elementu skaits laukā) ir mazāks par 2 vai lielāks par 30

1. Izvēlieties, vai savā jaunajā segmentā vēlaties iekļaut **Visus klientus** vai tikai klientus no **Konkrēta esošā segmenta**.

1. Sistēma pēc noklusējuma piedāvā iekļaut tikai 20% no jūsu izvades mērķauditorijas apjoma. Pēc nepieciešamības rediģējiet šo robežvērtību. Robežvērtības palielināšana samazinās precizitāti.

1. Iekļaujiet klientus avota segmentā, **atzīmējot izvēles rūtiņu Iekļaut dalībniekus no avota segmenta papildus klientiem ar līdzīgiem atribūtiem**.

1. Lapas lejasdaļā atlasiet opciju **Palaist**, lai uzsāktu binārās klasificēšanas uzdevumu (algoritmiskās mācīšanās metode), kas analizē datu kopu.

## <a name="view-the-similar-segment"></a>Līdzīga segmenta skatīšana

Pēc līdzīga segmenta apstrādes, jaunais segments būs iekļauts lapā **Segmenti**.

> [!div class="mx-imgBorder"]
> ![Līdzīgu klientu segments.](media/expanded-segment.png "Līdzīgu klientu segments")

Lai atvērtu segmenta informāciju, darbību joslā atlasiet **Skatīt**. Šajā skatā ir informācija par rezultātu sadali [līdzības rezultātos](#about-similarity-scores). Līdzības rezultāta vērtības ir pieejamas arī **Segmenta elementu priekšskatījumā**.

## <a name="use-the-output-of-a-similar-segment"></a>Līdzīga segmenta izvades izmantošana

Varat [strādāt ar līdzīga segmenta izvadi](segments.md) tāpat, kā to darāt ar citiem segmentiem. Piemēram, eksportējiet segmentu vai veidojiet mēru.

## <a name="refresh-and-edit-a-similar-segment"></a>Līdzīga segmenta atsvaidzināšana un rediģēšana

Lai atsvaidzinātu līdzīgu segmentu, atlasiet to lapā **Segmenti** un darbību joslā atlasiet **Atsvaidzināt**.

Rediģējot līdzīgu segmentu, dati tiks pārstrādāti. Iepriekš izveidotie segmenti tiek atjaunināti ar atsvaidzinātiem datiem.
Lai rediģētu līdzīgu segmentu, atlasiet to lapā **Segmenti** un darbību joslā atlasiet **Rediģēt**. Piemērojiet izmaiņas un atlasiet **Palaist**, lai sāktu apstrādi.

## <a name="delete-a-similar-segment"></a>Līdzīga segmenta dzēšana

Atlasiet segmentu lapā **Segmenti** un darbību joslā atlasiet **Dzēst**. Pēc tam apstipriniet dzēšanu.

## <a name="about-similarity-scores"></a>Par līdzības rezultātiem

Binārās klasificēšanas algoritmiskās mācīšanās modelis piešķir rezultātu lietotājiem līdzīgā segmentā. Rezultāts balstās līdzībā klientiem no avota segmenta.

- Līdzības rezultāti zem 0,55 ir klienti, kurus sistēma klasificē kā *nelīdzīgus* klientiem no avota segmenta.
- Līdzības rezultāti no 0,55 līdz 0,7 līdz klasificēti kā *nedaudz līdzīgi*
- Līdzības rezultāti no 0,7 līdz 0,85 līdz klasificēti kā *līdzīgi*
- Līdzības rezultāti no 0,85 līdz 1 ir klienti, kurus sistēma klasificē kā *ļoti līdzīgus*

Klienti ar līdzības rezultātu, kas zemāks par 0,4, netiek iekļauti modeļa izvadē. Sistēma tos neuzskata par pietiekami līdzīgiem avota segmentam.

[!INCLUDE [footer-include](includes/footer-banner.md)]