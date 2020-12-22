---
title: Klientu profilu meklēšana un filtrēšana
description: Ātri atrodiet informāciju par vienotajiem klientu profiliem un filtrējiet norādītos atribūtus.
ms.date: 04/16/2020
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 1842ad333c23bb155abc89167556163ae79cdd34
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406367"
---
# <a name="customer-profiles-search--filter-index"></a>Klientu profili: Meklēšanas un filtrēšanas indekss

Klientu datu apvienošanas rezultāts ir entītija Klientu profils, kas nodrošina vienotu skatu uz visu jūsu klientu bāzi. Lai ātri [atrastu informāciju par konkrētu klientu vai klientu grupu](customer-profiles.md), varat konfigurēt **meklēšanas** un **filtrēšanas** iespējas lapā **Klienti**. Tālāk uzzināsiet, kā administratori var rediģēt atribūtus lapā **Rādītāja meklēšana un filtrēšana**, ko lietotāji var izmantot meklēšanai un filtrēšanai.

> [!div class="mx-imgBorder"]
> ![Meklēšanas rezultātu filtrs](media/search-filter.png "Meklēšanas rezultātu filtrs")

## <a name="add-fields-and-specify-attributes"></a>Lauku pievienošana un atribūtu norādīšana

Ja šī ir pirmā reize, kad definējat meklējamos atribūtus kā administrators, vispirms ir jādefinē indeksētie lauki. Ieteicams izvēlēties visus atribūtus, pēc kuriem lietotāji var meklēt un filtrēt klientus lapā **Klienti**. Ir iespējams norādīt tikai tos atribūtus, kas pastāv entītijā Klienta profils, ko izveidojāt datu apvienošanas procesā.

1. Atveriet lapu **Klienti** un atlasiet **Meklēšanas un filtra indekss**.

> [!NOTE]
> Noklusējuma meklēšanas indeksa konfigurāciju var izveidot Klienta entītijā pieejamajos atribūtos, izmantojot tālāk norādītos semantiskos tipus, kā tas ir definēts Kartes lapā.
> - Personas vārds, uzvārds, otrais vārds, pilns vārds un uzvārds
> - Organizācijas nosaukums
> - E-pasta adrese
> - Tālruņa numurs
> - Atrašanās vietas informācija

2. Atlasiet **+ Pievienot**, lai precizētu indeksētos laukus.

3. Sarakstā atlasiet atribūtus, kurus vēlaties pievienot kā indeksētos laukus. Jūs jebkurā laikā varat pievienot papildu atribūtus, atlasot **Pievienot**. Varat arī noņemt jebkurus atlasītos atribūtus, atzīmējot **Noņemt** simbolu.

## <a name="explore-the-indexed-customer-fields-table"></a>Tabulas Indeksētie klienta lauki izpēte

Šajā tabulā ir pieejama tālāk norādītā informācija.

- **Nosaukums**: norāda atribūta nosaukumu, kāds tas tiek rādīts entītija Klienta profils.
- **Datu tips**: norāda, vai datu tips ir virkne, skaitlis vai datums.
- **Iekļauts meklēšanā**: norāda, vai šo atribūtu var izmantot, lai meklētu klientus lapā **Klienti**, izmantojot **meklēšanas** lauku.
- **Pievienot filtru**: vadīkla, lai definētu, kā šo atribūtu var izmantot filtrēšanai lapā **Klienti**.

## <a name="editing-filtering-options-for-a-given-attribute"></a>Filtrēšanas opciju rediģēšana noteiktam atribūtam

Lapas **Klienti** izvēlnē **Filtrēt** var būt ietverts atšķirīgs atribūtu līmeņu skaits (piemēram, dažādas vecuma grupas, pēc kurām filtrēt klientus).

1. Atlasiet **Pievienot filtru** konkrētajam atribūtam lapā **Rādītāja meklēšana un filtrēšana**. Varat noteikt rezultātu skaitu un secību, kādā tie tiks sakārtoti. Atkarībā no atribūta datu tipa tiek rādīta viena no tālāk redzamajām rūtīm.

- Virknes tipa atribūts: norādiet vēlamo rezultātu skaitu rūtī **Virknes filtrēšanas opcijas** un rezultātu rādīšanas secības politiku.

- Skaitliska tipa atribūts: norādiet iekļaujamo intervālu rūtī **Skaitļa filtrēšanas opcijas** un rezultātu rādīšanas secības politiku.

- Datuma tipa atribūts: norādiet iekļaujamo intervālu rūtī **Datuma filtrēšanas opcijas** un rezultātu rādīšanas secības politiku.

2. Lai veiktās izmaiņas stātos spēkā, atlasiet **Saglabāt**.

3. Kad būsiet gatavs lietot iestatījumus, atlasiet **Palaist**.
