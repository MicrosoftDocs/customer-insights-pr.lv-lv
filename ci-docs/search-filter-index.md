---
title: Klientu profilu meklēšanas un filtrēšanas indeksa pārvaldība
description: Ātri atrodiet informāciju par vienotajiem klientu profiliem un filtrējiet norādītos atribūtus.
ms.date: 07/22/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
searchScope:
- ci-search-filter
- customerInsights
ms.openlocfilehash: dfbfcbff3ffb3e4483252377e591229631d38556
ms.sourcegitcommit: c45c3e044034bf866b0662f80a59166cee4ababe
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 07/22/2022
ms.locfileid: "9187918"
---
# <a name="manage-the-search--filter-index-for-customer-profiles"></a>Klientu profilu meklēšanas un filtrēšanas indeksa pārvaldība

Klientu datu apvienošanas rezultāts ir klienta *entītija*, kas nodrošina vienotu skatu uz jūsu kopējo klientu bāzi. Lai lietotāji varētu ātri [atrast informāciju par konkrētu klientu vai klientu](customer-profiles.md) grupu, administratoram ir jākonfigurē **meklēšanas** un **filtrēšanas** **iespējas lapai Klienti**.

   :::image type="content" source="media/search-filter.png" alt-text="Meklēšanas rezultātu filtrs":::

## <a name="define-searchable-attributes-and-indexed-fields"></a>Meklējamu atribūtu un indeksētu lauku definēšana

Ja šī ir pirmā reize, kad kā administrators definējat meklējamus atribūtus, vispirms definējiet indeksētos laukus. Ieteicams izvēlēties visus atribūtus, pēc kuriem lietotāji var meklēt un filtrēt klientus lapā **Klienti**. Var norādīt tikai tos atribūtus, kas pastāv Klienta *entītijā*, kas izveidoti datu apvienošanas procesa laikā.

1. Dodieties uz **Klienti un atlasiet** Meklēt un filtrēt **indeksu**.

1. Atlasiet **+ Pievienot**.

1. Sarakstā atlasiet atribūtus, kurus vēlaties pievienot kā indeksētus laukus, un noklikšķiniet uz **Lietot**.

1. Lai pievienotu papildu atribūtus, atlasiet **Pievienot**. Lai noņemtu atlasīto atribūtu, atlasiet atribūtu un pēc tam **dzēsiet**.

   :::image type="content" source="media/search-filter-index.png" alt-text="Meklēšanas un filtrēšanas indeksa lapa.":::

1. Atlasiet **Palaist**, kad esat gatavs lietot meklēšanas un filtrēšanas iestatījumus. Kad izmaiņas ir apstrādātas, skatiet tās [klienta kartēs lapā](customer-profiles.md) Klients.

## <a name="define-filtering-options-for-a-given-attribute"></a>Filtrēšanas opciju definēšana noteiktam atribūtam

Iestatiet laukus, kurus var izmantot klientu **filtrēšanai lapā Klienti**.

1. Dodieties uz **Klienti un atlasiet** Meklēt un filtrēt **indeksu**.

1. Atlasiet atribūtu un **Pievienojiet filtru**. Definējiet rezultātu skaitu un secību, kādā tie tiks organizēti. Atkarībā no atribūta datu tipa tiek parādīta viena no tālāk norādītajām rūtīm.

   - Virknes tipa atribūti: norādiet vēlamo rezultātu **skaitu virknes filtra** rūtī un secības politiku, pēc kuras tie tiks organizēti.

   - Skaitliski tipa atribūti: norādiet intervālus, kas iekļauti **rūtī Skaitļu filtrs**, un secības politiku, pēc kuras tie tiks organizēti.

   - Datuma tipa atribūti: norādiet intervālus, **kas iekļauti rūtī Datuma filtrs**, un pasūtījumu politiku, pēc kuras tie tiks organizēti.

1. Atlasiet **Labi**. Atkārtojiet to visiem atribūtiem, pēc kuriem vēlaties filtrēt.

1. Atlasiet **Palaist**, kad esat gatavs lietot meklēšanas un filtrēšanas iestatījumus. Kad izmaiņas ir apstrādātas, skatiet tās [klienta kartēs lapā](customer-profiles.md) Klients.

## <a name="view-indexed-customer-fields"></a>Indeksēto klientu lauku skatīšana

Lapā **Meklēšanas un filtrēšanas indekss** tiek parādīta šāda informācija:

- **Nosaukums**: attēlo atribūta nosaukumu, kāds tas tiek rādīts *klienta* entītijā.
- **Datu tips**: norāda, vai datu tips ir virkne, skaitlis vai datums.
- **Iekļauts meklēšanā**: norāda, vai šo atribūtu var izmantot, lai meklētu klientus lapā **Klienti**, izmantojot **meklēšanas** lauku.
- **Pievienot filtru**: vadīkla, lai definētu, kā šo atribūtu var izmantot filtrēšanai lapā **Klienti**.

## <a name="next-steps"></a>Nākamās darbības

Pārskatiet [vienoto profilu lapu](customer-profiles.md), lai meklētu profilus vai izmantotu indeksētos laukus, lai redzētu visu vienoto profilu apakškopu.

[!INCLUDE [footer-include](includes/footer-banner.md)]
