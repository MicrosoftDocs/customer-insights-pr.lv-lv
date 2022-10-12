---
ms.openlocfilehash: a67714de5aae80a0080c0e631ae6f8986eb2a003
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 09/30/2022
ms.locfileid: "9611130"
---
- **Apmācības modeļa veiktspēja**: A, B vai C pakāpe norāda prognoze veiktspēju un var palīdzēt pieņemt lēmumu izmantot izvades entītijā saglabātos rezultātus.

  Kategorijas tiek noteiktas, pamatojoties uz šādām kārtulām:
  - **A** Ja modelis precīzi prognozēja vismaz 50% no kopējām prognozēm un ja procentuālā daļa no precīzas prognozes klientiem, kuri ir zuduši, pārsniedz bāzes likmi vismaz par 10%.
  - **B** Ja modelis precīzi prognozēja vismaz 50% no kopējām prognozēm un ja procentuālā daļa no precīzas prognozes klientiem, kuri ir zuduši, ir līdz 10% lielāki nekā bāzes likme.
  - **C**, ja modelis precīzi prognozēja mazāk nekā 50% no kopējām prognozēm vai ja precīzu prognožu procentuālais daudzums klientiem, kuri ir samazinājušies, ir mazāks par bāzes līniju.
  - **Bāzlīnija** ņem prognoze modeļa laika loga ievadi (piemēram, vienu gadu) un izveido dažādas laika daļas, dalot to ar 2, līdz tas sasniedz vienu mēnesi vai mazāk. Šīs frakcijas izmanto, lai izveidotu biznesa kārtulu klientiem, kas nav veikuši pirkumus šajā laika periodā. Šie klienti tiek uzskatīti par zudušiem. Par pamatmodeli tiek izvēlēts uz laiku balstīts uzņēmējdarbības noteikums ar visaugstāko spēju paredzēt, kurš, iespējams, čurās.

- **Zuduma varbūtība (klientu skaits)**: klientu grupas, pamatojoties uz to prognozējamo zuduma risku. Pēc izvēles izveidojiet [klientu](../prediction-based-segment.md) segmentus ar augstu zuduma risku. Šādi segmenti palīdz saprast, kur vajadzētu būt dalībai segmentā.

- **Ietekmīgākie faktori**: ir daudzi faktori, kas tiek ņemti vērā, veidojot jūsu prognozi. Katram faktoram ir nozīme, kas aprēķināta modeļa izveidotajos apkopotajās prognozēs. Izmantojiet šos faktorus, lai palīdzētu apstiprināt prognoze rezultātus. Vai arī izmantojiet šo informāciju vēlāk, lai [izveidotu segmentus](../prediction-based-segment.md), kas varētu palīdzēt ietekmēt zuduma risku klientiem.