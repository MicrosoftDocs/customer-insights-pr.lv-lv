---
title: Prognozējiet abonēšanas zudumu (satur video)
description: Paredziet, vai pastāv risks, ka klients vairs neizmantos jūsu uzņēmuma abonēšanas produktus vai pakalpojumus.
ms.date: 09/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 7464707864c418bfcc625ddfd245622131434b33
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610245"
---
# <a name="predict-subscription-churn"></a>Paredzēt abonēšanas mainību

Paredziet, vai pastāv risks, ka klients vairs neizmantos jūsu uzņēmuma abonēšanas produktus vai pakalpojumus. Abonēšanas dati ietver aktīvos un neaktīvos abonementus katram klientam, tāpēc katram klienta ID ir vairāki ieraksti.

Jums ir jābūt biznesa zināšanām, lai saprastu, ko jūsu biznesam nozīmē churn. Mēs atbalstām uz laiku balstītas zuduma definīcijas, kas nozīmē, ka tiek uzskatīts, ka klients ir noguris kādu laika periodu pēc abonēšanas beigām.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWOKNQ]

> [!TIP]
> Izmēģiniet abonēšanas fragmentu prognoze, izmantojot datu paraugus: [abonēšanas zuduma prognoze parauga ceļvedis](sample-guide-predict-subscription-churn.md).

## <a name="prerequisites"></a>Priekšnoteikumi

- Vismaz [Līdzdalībnieka atļaujas](permissions.md).
- Vismaz 10 klientu profili, vēlams vairāk nekā 1,000 unikālu klientu.
- Klienta identifikators — unikāls identifikators, kas saskaņo abonementus ar jūsu klientiem.
- Abonēšanas dati vismaz divreiz pārsniedz atlasīto laika logu. Vēlams, lai būtu abonēšanas dati par diviem vai trim gadiem. Abonementu vēsturē jāiekļauj:
  - **Abonēšanas ID:** abonementa unikālais identifikators.
  - **Abonēšanas beigu datums:** datums, kad klientam beidzas abonementa derīguma termiņš.
  - **Abonēšanas sākuma datums:** datums, kad klientam tiek sākts abonements.
  - **Transakcijas datums:** datums, kad notikusi abonementa maiņa. Piemēram, klientam, kas pērk vai atceļ abonementu.
  - **Vai tas ir periodisks abonements:** Būla patiess/aplams lauks, kas nosaka, vai abonements tiks atjaunots ar to pašu abonēšanas ID bez klienta iejaukšanās.
  - **Atkārtošanās biežums (mēnešos):** periodisku abonementu gadījumā — mēnesis, kurā abonements tiks atjaunots. Piemēram, gada abonements, kas klientam katru gadu automātiski atjaunojas uz vēl vienu gadu, vērtība ir 12.
  - **Abonēšanas summa**: valūtas summa, ko klients maksā par abonēšanas atjaunošanu. Tas var palīdzēt identificēt dažādu abonementu līmeņu shēmas.
- Vismaz divi darbību ieraksti par 50% klientu, par kuriem vēlaties aprēķināt zudumu. Klientu aktivitātēm jāietver:
  - **Primārā atslēga:** unikāls identifikators darbībai. Piemēram, tīmekļa vietnes apmeklējums vai lietojuma ieraksts, kas norāda klienta skatīto TV pārraides epizodi.
  - **Laikspiedols:** notikuma datums un laiks, kas identificēts ar primāro atslēgu.
  - **Notikums:** tā notikuma nosaukums, kuru vēlaties izmantot. Piemēram, straumēšanas video pakalpojuma laukā ar nosaukumu "UserAction" var būt vērtība "Apskatīts".
  - **Detalizēti:** detalizēta informācija par notikumu. Piemēram, straumēšanas video pakalpojuma laukā ar nosaukumu "ShowTitle" var būt tāda videoklipa vērtība, kuru klients ir skatījies.
- Mazāk nekā 20% trūkstošo vērtību norādītās entītijas datu laukā.

## <a name="create-a-subscription-churn-prediction"></a>Izveidot abonēšanas zuduma prognozi

Jebkurā laikā atlasiet **Saglabāt melnrakstu**, lai saglabātu prognoze kā melnrakstu. Melnraksts prognoze tiek parādīts **cilnē Manas prognozes**.

1. Dodieties uz **izlūkošanas** > **prognozēm**.

1. **Cilnē Izveide** atlasiet **Izmantot modeli** elementā **Customer churn modelis**.

1. Atlasiet **Abonēšana**, lai noteiktu zuduma veidu, un pēc tam **sāciet darbu**.

1. **Nosauciet šo modeli** un **Izvades entītijas nosaukumu**, lai nošķirtu tos no citiem modeļiem vai entītijām.

1. Atlasiet **Tālāk**.

### <a name="define-customer-churn"></a>Definēt klientu zudumu

1. Ievadiet **Dienu skaits, kopš abonements beidzies**, ko jūsu uzņēmums uzskata par klientu zuduma stāvokli. Šis periods parasti ir saistīts ar uzņēmējdarbības aktivitātēm, piemēram, piedāvājumiem vai citiem mārketinga pasākumiem, kuru mērķis ir novērst klienta zaudēšanu.

1. Ievadiet dienu skaitu **, lai izpētītu nākotni, lai prognozētu zudumu**. Piemēram, prognozētu kannas risku saviem klientiem nākamo 90 dienu laikā, lai pielīdzinātos jūsu mārketinga saglabāšanas pūliņiem. Zuduma riska prognozēšana ilgākiem vai garākiem laikposmiem var apgrūtināt jūsu zuduma risku profila faktoru atrisināšanu atkarībā no jūsu konkrētā biznesa prasībām.

1. Atlasiet **Tālāk**.

### <a name="add-required-data"></a>Pievienot nepieciešamos datus

1. Atlasiet **Pievienot datus** abonementu **vēsturei**.

1. Atlasiet semantiskās darbības veidu **Abonements**, kurā ir nepieciešamā informācija par abonementu vēsturi. Ja darbība nav iestatīta, atlasiet **šeit** un izveidojiet to.

1. Sadaļā **Darbības**, ja aktivitātes izveides laikā aktivitātes atribūti tika semantiski kartēti izvēlieties konkrētus atribūtus vai entītiju, uz kuru vēlaties koncentrēties aprēķinam. Ja semantiskā kartēšana nenotika, atlasiet **Rediģēt** un kartējiet savus datus.
  
   :::image type="content" source="media/subscription-churn-required.png" alt-text="Nepieciešamo datu pievienošana abonementa zuduma modelim":::

1. Atlasiet **Tālāk** un pārskatiet šim modelim nepieciešamos atribūtus.

1. Atlasiet **Saglabāt**.

1. Atlasiet **Pievienot datus** klientu **darbībām**.

1. Atlasiet semantiskās darbības veidu, kas sniedz informāciju par klientu darbībām. Ja darbība nav iestatīta, atlasiet **šeit** un izveidojiet to.

1. Sadaļā **Darbības**, ja aktivitātes izveides laikā aktivitātes atribūti tika semantiski kartēti izvēlieties konkrētus atribūtus vai entītiju, uz kuru vēlaties koncentrēties aprēķinam. Ja semantiskā kartēšana nenotika, atlasiet **Rediģēt** un kartējiet savus datus.

1. Atlasiet **Tālāk** un pārskatiet šim modelim nepieciešamos atribūtus.

1. Atlasiet **Saglabāt**.

1. Pievienojiet papildu aktivitātes vai atlasiet **Tālāk**.

### <a name="set-update-schedule"></a>Iestatīt grafika atjaunināšanu

1. Izvēlieties frekvenci, lai pārkvalificētu savu modeli. Šis iestatījums ir svarīgs, lai atjauninātu prognožu precizitāti, jo programmā Customer Insights tiek uzņemti jauni dati. Lielākā daļa uzņēmumu var pārkvalificēties reizi mēnesī un iegūt labu precizitāti to prognozēšanai.

1. Atlasiet **Tālāk**.

### <a name="review-and-run-the-model-configuration"></a>Modeļa konfigurācijas pārskatīšana un palaišana

Darbībā Pārskatīšana **un izpilde** tiek rādīts konfigurācijas kopsavilkums, un tā nodrošina iespēju veikt izmaiņas pirms prognoze izveides.

1. Atlasiet **Rediģēt**, veicot kādu no darbībām, lai pārskatītu un veiktu izmaiņas.

1. Ja esat apmierināts ar atlasi, atlasiet **Saglabāt un palaist**, lai sāktu modeļa darbību. Atlasiet **Gatavs**. Cilne **Manas prognozes** tiek rādīta, kamēr tiek veidota prognoze. Atkarībā no prognozēšanas laikā izmantojamā datu daudzuma process var aizņemt vairākas stundas.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-prediction-results"></a>Prognoze rezultātu skatīšana

1. Dodieties uz **izlūkošanas** > **prognozēm**.

1. **Cilnē Manas prognozes** atlasiet prognoze, kuru vēlaties skatīt.

Rezultātu lapā ir trīs primāro sadaļu dati:

- **Apmācības modeļa veiktspēja**: A, B vai C pakāpe norāda prognoze veiktspēju un var palīdzēt pieņemt lēmumu izmantot izvades entītijā saglabātos rezultātus.
  
  :::image type="content" source="media/subscription-churn-modelperformance.PNG" alt-text="Modeļa rezultātu informācijas lodziņa attēls ar atzīmi A.":::

  Kategorijas tiek noteiktas, pamatojoties uz šādām kārtulām:
  - **A** kad modelis precīzi prognozēja vismaz 50% no kopējām prognozēm un kad precīzu prognožu procents klientiem, kuri sačakarēja, ir lielāks par vēsturisko vidējo zuduma līmeni vismaz par 10%.
  - **B**, kad modelis precīzi prognozēja vismaz 50% no kopējām prognozēm un kad precīzu prognožu procents klientiem, kuri sačakarēja, ir līdz pat 10% lielāks nekā vēsturiskais vidējais zuduma ātrums.
  - **C**, ja modelis precīzi prognozēja mazāk nekā 50% no kopējām prognozēm vai ja precīzu prognožu procentuālais daudzums klientiem, kuri izplūda, ir mazāks par vēsturisko vidējo zuduma ātrumu.
  
- **Zuduma varbūtība (klientu skaits)**: klientu grupas, pamatojoties uz to prognozējamo zuduma risku. Pēc izvēles izveidojiet [klientu](prediction-based-segment.md) segmentus ar augstu zuduma risku. Šādi segmenti palīdz saprast, kur vajadzētu būt dalībai segmentā.  

  :::image type="content" source="media/subscription-churn-resultdistribution.PNG" alt-text="Grafiks, kurā tiek rādīts zuduma rezultātu sadalījums, sadalīts diapazonos no 0-100%":::

- **Ietekmīgākie faktori:** ir daudzi faktori, kas tiek ņemti vērā, veidojot jūsu prognozi. Katram faktoram ir nozīme, kas aprēķināta modeļa izveidotajos apkopotajās prognozēs. Izmantojiet šos faktorus, lai palīdzētu apstiprināt prognoze rezultātus. Vai arī izmantojiet šo informāciju vēlāk, lai [izveidotu segmentus](.//prediction-based-segment.md), kas varētu palīdzēt ietekmēt zuduma risku klientiem.

  :::image type="content" source="media/subscription-churn-influentialfactors.PNG" alt-text="Saraksts rāda svarīgākos faktorus un to nozīmi, prognozējot zuduma rezultātus.":::

> [!NOTE]
> Šī modeļa izvades vienībā ChurnScore *ir prognozētā zuduma varbūtība, un* IsChurn *ir bināra etiķete,* kuras pamatā *ir ChurnScore* ar 0,5 slieksni. Ja šis noklusējuma slieksnis nedarbojas jūsu scenārijam, [izveidojiet jaunu segmentu](segments.md) ar vēlamo slieksni. Lai skatītu zuduma rezultātu, dodieties uz **Datu** > **entītijas** un skatiet datu cilni izvades entītijai, kuru definējāt šim modelim.

[!INCLUDE [footer-include](includes/footer-banner.md)]
