---
title: Līdzīgu klientu atrašana, izmantojot AI (priekšskatījums) (satur video)
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
ms.openlocfilehash: 09fe36a4da45d114cbfccf8dad1e7b80b4b7e320
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170736"
---
# <a name="find-similar-customers-with-ai-preview"></a>Līdzīgu klientu atrašana, izmantojot AI (priekšskatījums)

Atrodiet līdzīgus klientus savā klientu bāzē, izmantojot mākslīgo intelektu. Lai izmantotu šo funkciju, ir jāizveido vismaz viens segments. Paplašinot esoša segmenta kritērijus, var atrast klientus, kas ir līdzīgi šim segmentam.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWOFou]

> [!NOTE]
> *Atrodiet līdzīgus klientus*, kas izmanto automatizētus līdzekļus, lai novērtētu datus un veiktu prognozes, pamatojoties uz šiem datiem. Tāpēc to var izmantot kā profilēšanas metodi, jo šis termins ir definēts Vispārīgajā datu aizsardzības regulā ("VDAR"). Šī līdzekļa izmantošana klienta datu apstrādei var būt pakļauta VDAR vai citiem likumiem vai noteikumiem. Jūs esat atbildīgs par to, ka jūsu Dynamics 365 Customer Insights lietojums, ieskaitot prognozes, atbilst visiem piemērojamiem likumiem un noteikumiem, ieskaitot likumus, kas attiecas uz privātumu, personas datiem, biometrijas datiem, datu aizsardzību un saziņas konfidencialitāti.

## <a name="find-similar-customers"></a>Atrast līdzīgus klientus

1. Dodieties uz **Sadaļu Segmenti** un atlasiet segmentu, uz kuru vēlaties balstīt savu jauno segmentu. Tas būs jūsu *avota segments*.

1. Atlasiet **Atrast līdzīgus klientus**.

1. Pārskatiet jaunā segmenta ierosināto nosaukumu un, ja nepieciešams, to mainiet.

1. Pēc izvēles pievienojiet [tagus](work-with-tags-columns.md#manage-tags) jaunajam segmentam.

1. Pārskatiet laukus, kuri definē jauno segmentu. Šie lauki definē pamatu, uz kura sistēma centīsies atrast jūsu avota segmentam līdzīgus klientus. Sistēma pēc noklusējuma atlasa ieteicamos laukus. Ja nepieciešams, pievienojiet vairāk lauku.
  Lauki, kuri var ievērojami samazināt modeļa veiktspēju, tiek automātiski izslēgti:
  
   - Lauki ar šādiem datu tipiem: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType
   - Lauki, kuros kardināls (elementu skaits laukā) ir mazāks par 2 vai lielāks par 30

1. Izvēlieties, vai jaunajā segmentā vēlaties iekļaut **visus klientus**, izņemot avota segmentu, vai tikai klientus **citā segmentā**.

1. Sistēma pēc noklusējuma piedāvā iekļaut tikai 20% no jūsu izvades mērķauditorijas apjoma. Pēc nepieciešamības rediģējiet šo robežvērtību. Robežvērtības palielināšana samazinās precizitāti.

1. Iekļaujiet klientus savā avota segmentā, atzīmējot izvēles **rūtiņu Iekļaut dalībniekus no avota segmenta papildus klientiem ar līdzīgiem atribūtiem**.

1. Lapas apakšdaļā atlasiet **Palaist**, lai sāktu bināro klasifikācijas [uzdevumu](#about-similarity-scores) (algoritmiskā mācīšanās metode), kas analizē datu kopu.

## <a name="view-the-similar-segment"></a>Līdzīga segmenta skatīšana

Pēc līdzīga segmenta apstrādes lapā Segmenti atradīsit jauno segmentu **ar** tipu **Paplašināšana**.

Atlasiet **Skatīt**, lai skatītu rezultātu sadalījumu starp [līdzības rādītājiem](#about-similarity-scores) un līdzības vērtējuma vērtībām sadaļā **Segmenta dalībnieku priekšskatījums**.

:::image type="content" source="media/expanded-segment.png" alt-text="Līdzīgu klientu segments.":::

## <a name="manage-a-similar-segment"></a>Līdzīga segmenta pārvaldība

[Strādājiet ar līdzīgu segmentu](segments.md#manage-existing-segments) un pārvaldiet to kā ar citiem segmentiem. Piemēram, eksportējiet segmentu vai veidojiet mēru.

Rediģējiet, atsvaidziniet, pārdēvējiet, lejupielādējiet un dzēsiet līdzīgu segmentu. Rediģējot līdzīgu segmentu, dati tiek apstrādāti. Iepriekš izveidotie segmenti tiek atjaunināti ar atsvaidzinātiem datiem.

## <a name="about-similarity-scores"></a>Par līdzības rezultātiem

Binārās klasificēšanas algoritmiskās mācīšanās modelis piešķir rezultātu lietotājiem līdzīgā segmentā. Rezultāts balstās līdzībā klientiem no avota segmenta.

- Līdzības rezultāti zem 0,55 ir klienti, kurus sistēma klasificē kā *nelīdzīgus* klientiem no avota segmenta.
- Līdzības rezultāti no 0,55 līdz 0,7 līdz klasificēti kā *nedaudz līdzīgi*
- Līdzības rezultāti no 0,7 līdz 0,85 līdz klasificēti kā *līdzīgi*
- Līdzības rezultāti no 0,85 līdz 1 ir klienti, kurus sistēma klasificē kā *ļoti līdzīgus*

Klienti ar līdzības rezultātu, kas zemāks par 0,4, netiek iekļauti modeļa izvadē. Sistēma tos neuzskata par pietiekami līdzīgiem avota segmentam.

[!INCLUDE [footer-include](includes/footer-banner.md)]
