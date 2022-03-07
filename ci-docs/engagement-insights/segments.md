---
title: Skatīt un izveidot segmentus
description: Kā izveidot, rediģēt un dzēst segmentus un kur tos izmantot.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: e99c04e6c92d8ca16c2d69957e0f5b7dba0ac757
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 02/16/2022
ms.locfileid: "8225385"
---
# <a name="view-and-create-segments"></a>Skatīt un izveidot segmentus

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Segmenti ļauj identificēt apakškopas, kas ir nostituļas, pamatojoties uz rādītājiem vai mijiedarbību ar vietni. Izmantojot segmentus, var lietot filtrus un analizēt šīs apakškopas. Šī analīze var palīdzēt pārbaudīt jūsu uzņēmuma tendences un reaģēt uz tiem. 

:::image type="content" source="media/segments-page.png" alt-text="Iesaistes ieskatu ekrānuzņēmums, kurā redzams darbvietā esošo segmentu saraksts.":::

## <a name="view-segments"></a>Skatīt segmentus

1. Kreisās puses navigācijas rūtī dodieties uz **Dati**. 

1. Atlasiet cilni **Segmenti**, lai skatītu visu segmentu sarakstu darbvietā. 

## <a name="create-a-segment"></a>Segmenta izveide

Segmentos ir kārtulas un nosacījumi, kas saistīti ar loģiskajiem operatoriem. Nosacījumi lieto filtrus atlasītajai dimensijai. Katrs segments var izmantot līdz piecām dimensijām.

Šajā piemērā ir redzams segments ar diviem nosacījumiem vienā kārtulā. Tas filtrē visus vietņu notikumus, kuros pārlūks ir Chrome un operētājsistēmas ir iOS vai Android.

:::image type="content" source="media/segment-sample.png" alt-text="Piemēram, segmenti ar diviem kārtulas nosacījumiem, lai filtrētu vietņu notikumus.":::

Šajā sadaļā ir aprakstīts, kā izveidot *tukšu segmentu* no jauna.

1. Dodieties uz **Dati** > **Segmenti**.

1. Atlasiet **Jauns segments**.

1. **Resursu bibliotēkā** atlasiet (+) blakus atribūtam, pēc kura vēlaties filtrēt. Pašlaik var izveidot tikai segmentus, kas balstīti uz dimensijām.

   :::image type="content" source="media/create-new-segment.png" alt-text="Izveidot jaunu segmentu.":::

1. Sadaļā **Kārtula** izvēlieties operatoru un atlasītā atribūta vērtību. Tiek atbalstītas šīs darbības.

   :::image type="content" source="media/choose-operator-segment.png" alt-text="Izvēlieties jaunā segmenta operatoru.":::

   - **ir** : lai ietvertu vērtības, ir nepieciešama precīza atbilstība. Tiek izmantots **vienāds ar** vienu vērtību vai **jebkuru no**, lai iekļautu vairākas vērtības.
   - **nav** : lai izslēgtu vērtības, ir nepieciešama precīza atbilstība. Tiek izmantots **vienāds ar** vienu vērtību vai **jebkuru no**, lai iekļautu vairākas vērtības.
   - **sākas ar**: virkne, ar kuru sākas atbilstošās vērtības.
   - **beidzas ar**: virkne, ar kuru beidzas atbilstošās vērtības.
   - **satur**: virkne, kas satur atbilstības vērtībās.

1. Lai grupai pievienotu papildu nosacījumus, var izmantot loģiskos operatorus. Plānotie atribūti tiek faktorizēti, izmantojot kopas operatorus.
   - **UN** operators: Ir jāizpilda abi nosacījumi kā daļa no segmentācijas procesa. Šī opcija ir visnoderīgākā, kad definējat nosacījumus dažādās entītijās.
   - **Vai** operators: Viens vai otrs no nosacījumiem ir jāizpilda kā segmentācijas procesa daļa. Šī opcija ir visnoderīgākā, kad definējat vairākus nosacījumus vienai entītijai.

1. Nosauciet segmentu un atlasiet **Saglabāt**. 

Segments tiks norādīts lapā **Segmenti**, un to var lietot visām darbvietā iekļautām atskaitēm un piltuvēm.

## <a name="use-a-segment-in-a-report-or-funnel"></a>Segmenta izmantošana atskaitē vai piltuvē

Atskaitei vai piltuvei var lietot segmentus, lai tos filtrētu, pamatojoties uz segmenta nosacījumiem. Taču reāllaika lietojuma atskaitei nevar lietot segmentus.

:::image type="content" source="media/segment-reports-filter.png" alt-text="Lapas skatīšanas pārskats ar izvērstu nolaižamo sarakstu, lai izvēlētos, kurus segmentus lietot.":::

Lai lietotu segmentu, atveriet atskaiti vai piltuvi. Atlasiet **+ Pievienot nosacījumu** un izvēlieties **Filtrēt pēc segmenta**. Izvēlieties no saraksta segmentu, kuru vēlaties lietot. Segments tiek lietots atskaitei. Ja diagramma neatbalsta segmentu, tajā ir redzama kļūda. Papildinformāciju skatiet sadaļā [Piltuves atskaišu izveide un pārvaldība](funnel-reports.md).
 
Atskaitei vai piltuvei var lietot *ne vairāk kā trīs segmentus*.

## <a name="edit-a-segment"></a>Segmenta rediģēšana

1. Dodieties uz **Dati** > **Segmenti**.
1. Atlasiet no saraksta segmentu, lai to atvērtu. 
1. Ja nepieciešams, mainiet vai pievienojiet vērtības.
1. Lai veiktās izmaiņas stātos spēkā, atlasiet **Saglabāt**.

## <a name="change-the-name-of-a-segment"></a>Mainīt segmenta nosaukumu

1. Dodieties uz **Dati** > **Segmenti**.
1. Segmentu sarakstā atlasiet **Vēl [...]**. 
1. Nolaižamajā sarakstā izvēlieties **Rediģēt nosaukumu**.
1. Ievadiet atjaunināto nosaukumu un atlasiet **Pārdēvēt**.

## <a name="delete-a-segment"></a>Dzēst segmentu

1. Dodieties uz **Dati** > **Segmenti**.
1. Segmentu sarakstā atlasiet **Vēl [...]**. 
1. Nolaižamajā sarakstā izvēlieties **Dzēst**.
1. Lai apstiprinātu, atlasiet **Dzēst**.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
