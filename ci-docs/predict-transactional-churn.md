---
title: Transakciju zuduma prognoze (satur video)
description: Prognozējiet, vai pastāv risks, ka klients vairs neiegādāsies jūsu uzņēmuma produktus vai pakalpojumus.
ms.date: 09/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: fd8df0f0a168ddfab9e8ad3af9e1f1fc0bc1b7a2
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610521"
---
# <a name="predict-transaction-churn"></a>Prognozējiet transakcijas zudumu

Transakciju zudumu prognoze palīdz paredzēt, vai klients vairs nepirks jūsu produktus vai pakalpojumus noteiktā laika logā.

Jums ir jābūt biznesa zināšanām, lai saprastu, ko jūsu biznesam nozīmē churn. Mēs atbalstām uz laiku balstītu zudumu definīcijas, kas nozīmē, ka klients ir uzskatāms par zudušu pēc perioda bez pirkumiem.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6Eg]

Attiecībā uz vidēm, kuru pamatā ir uzņēmuma konti, mēs varam paredzēt uzņēmuma transakciju procesu, kā arī uzņēmuma un cita līmeņa informācijas kombināciju, piemēram, produktu kategoriju. Piemēram, kategorijas pievienošana var palīdzēt noteikt, cik liela ir varbūtība, ka konts "Contoso" pārtrauks produktu kategorijas "biroja kancelejas preces" iegādi. Turklāt attiecībā uz uzņēmuma kontiem mēs varam izmantot arī AI, lai ģenerētu iespējamo iemeslu sarakstu, kāpēc uzņēmums, visticamāk, būs sekundāra līmeņa informācijas kategorijai.

> [!TIP]
> Izmēģiniet transakciju prognoze, izmantojot parauga datus: [Transakciju zuduma prognoze paraugu ceļvedis](sample-guide-predict-transactional-churn.md).

## <a name="prerequisites"></a>Priekšnoteikumi

- Vismaz [Līdzdalībnieka atļaujas](permissions.md).
- Vismaz 10 klientu profili, vēlams vairāk nekā 1,000 unikālu klientu.
- Klienta identifikators — unikāls identifikators, lai saskaņotu darījumus ar jūsu klientiem.
- Darījumu dati par vismaz divreiz lielāku par atlasīto laika periodu, piemēram, par diviem līdz trim gadiem darījumu vēsturē. Ideālā gadījumā vismaz divi darījumi uz vienu klientu. Darījumu vēsturē jāiekļauj:
  - **Transakcijas ID**: pirkuma vai transakcijas unikālais identifikators.
  - **Transakcijas datums**: pirkuma vai transakcijas datums.
  - **Darījuma** vērtība: darījuma valūta vai skaitliskā vērtība.
  - **Unikāls produkta ID**: iegādātā produkta vai pakalpojuma ID, ja jūsu dati ir rindas vienuma līmenī.
  - **Tas, vai šī transakcija bija atgriešanās**: patiess/aplams lauks, kas identificē, vai transakcija bija vai nebija atgriezta. **Ja darījuma** vērtība ir negatīva, mēs secinām atdevi.
- Dati par klientu darbībām:
  - Klienta identifikators — unikāls identifikators, lai kartētu darbības uz jūsu klientiem.
  - **Primārā atslēga:** unikāls identifikators darbībai. Piemēram, vietnes apmeklējums vai lietojuma ieraksts, kas norāda, ka klients ir izmēģinājis jūsu produkta paraugu.
  - **Laikspiedols:** notikuma datums un laiks, kas identificēts ar primāro atslēgu.
  - **Notikums:** tā notikuma nosaukums, kuru vēlaties izmantot. Piemēram, lauks "UserAction" pārtikas preču veikalā varētu būt klientam piemērots kupona lietojums.
  - **Detalizēti:** Detalizēta informācija par notikumu. Piemēram, preču veikala lauks ar nosaukumu "CouponValue" var būt kupona valūtas vērtība.
- Mazāk nekā 20% no trūkstošajām vērtībām sniegtā uzņēmuma datu laukā

Biznesa kontiem (B-to-B) pievienojiet klientu datus, kas līdzināti statiskākiem atribūtiem, lai nodrošinātu, ka modelis darbojas vislabāk:
- **CustomerID:** unikāls klienta identifikators.
- **Izveides datums:** datums, kad debitors sākotnēji tika pievienots.
- **Štats vai province:** klienta štata vai provinces atrašanās vieta.
- **Valsts:** Klienta valsts.
- **Nozare:** Nozares klienta tips. Piemēram, lauks ar nosaukumu "Nozare" kafijas grauzdēšanā var norādīt, vai klients ir mazumtirdzniecībā.
- **Klasifikācija:** klienta kategorizēšana jūsu biznesam. Piemēram, lauks ar nosaukumu "ValueSegment" kafijas grauzdēšanā var būt klientu līmenis, uz kura balstās klientu lielums.

> [!NOTE]
> Uzņēmumiem ar augstu klientu pirkšanas biežumu (reizi dažās nedēļās) ir ieteicams izvēlēties īsāku prognozēšanas logu un zuduma definīciju. Ja pirkšanas biežums ir zems (reizi dažos mēnešos vai reizi gadā), izvēlieties garāku prognozēšanas logu un zuduma definīciju.

## <a name="create-a-transaction-churn-prediction"></a>Transakciju zuduma prognozes izveide

1. Dodieties uz **izlūkošanas** > **prognozēm**.

1. **Cilnē Izveide** atlasiet **Izmantot modeli** elementā **Customer churn modelis**.

1. Atlasiet **Transakcija**, lai noteiktu zuduma veidu, un pēc tam **sākt darbu**.

1. **Nosauciet šo modeli** un **Izvades entītijas nosaukumu**, lai nošķirtu tos no citiem modeļiem vai entītijām.

1. Atlasiet **Tālāk**.

### <a name="define-customer-churn"></a>Definēt klientu zudumu

Jebkurā laikā atlasiet **Saglabāt melnrakstu**, lai saglabātu prognoze kā melnrakstu. Melnraksts prognoze tiek parādīts **cilnē Manas prognozes**.

1. Iestatiet **prognoze logu**. Piemēram, prognozētu kannas risku saviem klientiem nākamo 90 dienu laikā, lai pielīdzinātos jūsu mārketinga saglabāšanas pūliņiem. Prognozējot zudumu risku ilgākā vai īsākā laika periodā var apgrūtināt, lai risinātu faktorus jūsu zudumu riska profilu, bet tas ir atkarīgs no jūsu uzņēmuma specifiskajām prasībām.

1. Ievadiet dienu skaitu, lai definētu zuduma **definīciju laukā Churn definīcija**. Piemēram, ja klients pēdējo 30 dienu laikā nav veicis pirkumu, viņš var tikt uzskatīts par jūsu uzņēmumam paredzētu.

1. Atlasiet **Tālāk**.

### <a name="add-purchase-history"></a>Pievienot pirkuma vēsturi

1. Atlasiet **Pievienot datus** klientu darījumu **vēsturei**.

1. Atlasiet semantiskās darbības tipu SalesOrder **vai** **SalesOrderLine**, kas satur transakciju vēstures informāciju. Ja darbība nav iestatīta, atlasiet **šeit** un izveidojiet to.

1. Sadaļā **Darbības**, ja aktivitātes izveides laikā aktivitātes atribūti tika semantiski kartēti izvēlieties konkrētus atribūtus vai entītiju, uz kuru vēlaties koncentrēties aprēķinam. Ja semantiskā kartēšana nenotika, atlasiet **Rediģēt** un kartējiet savus datus.

   :::image type="content" source="media/transaction-churn-select-activity.PNG" alt-text="Sānu rūts, kurā redzama noteiktu darbību izvēle zem semantiskā tipa.":::

1. Atlasiet **Tālāk** un pārskatiet šim modelim nepieciešamos atribūtus.

1. Atlasiet **Saglabāt**.

1. Pievienojiet papildu aktivitātes vai atlasiet **Tālāk**.

# <a name="individual-consumers-b-to-c"></a>[Atsevišķi patērētāji (B2C)](#tab/b2c)

### <a name="add-additional-data-optional"></a>Pievienot papildu datus (neobligāti)

1. Atlasiet **Pievienot datus** klientu **darbībām**.

1. Atlasiet semantiskās darbības tipu, kurā ir dati, kurus vēlaties izmantot. Ja darbība nav iestatīta, atlasiet **šeit** un izveidojiet to.

1. Sadaļā **Darbības**, ja aktivitātes izveides laikā aktivitātes atribūti tika semantiski kartēti izvēlieties konkrētus atribūtus vai entītiju, uz kuru vēlaties koncentrēties aprēķinam. Ja semantiskā kartēšana nenotika, atlasiet **Rediģēt** un kartējiet savus datus.

1. Atlasiet **Tālāk** un pārskatiet šim modelim nepieciešamos atribūtus.

1. Atlasiet **Saglabāt**.

1. Atlasiet **Tālāk**

# <a name="business-accounts-b-to-b"></a>[Uzņēmumu konti (B2B)](#tab/b2b)

### <a name="select-prediction-level"></a>Atlasīt prognozes līmenis

Vairums prognožu ir izveidotas klientu līmenī. Dažās situācijās, iespējams, tās nav pietiekoši detalizētas, lai atbilstu jūsu uzņēmuma vajadzībām. Izmantojiet šo līdzekli, lai prognozētu, piemēram, klienta filiāli, nevis klientu kopumā.

1. Atlasiet **Atlasīt entītiju sekundārajam līmenim**. Ja šī opcija nav pieejama, pārliecinieties, vai iepriekšējā sadaļa ir pabeigta.

1. Izvērsiet entītijas, no kurām vēlaties izvēlēties sekundāro līmeni, vai izmantojiet meklēšanas filtra lodziņu, lai filtrētu atlasītās opcijas.

1. Izvēlieties atribūtu, ko vēlaties izmantot kā sekundāro līmeni, un pēc tam atlasiet vienumu **Pievienot**.

1. Atlasiet **Tālāk**.

> [!NOTE]
> Šajā sadaļā pieejamās entītijas tiek parādītas, jo tām ir attiecības ar entītiju, ko izvēlējāties iepriekšējā sadaļā. Ja neredzat entītiju, kuru vēlaties pievienot, pārliecinieties, vai tai ir spēkā esošas attiecības sadaļā **Attiecības**. Šai konfigurācijai ir derīgas tikai attiecības viens pret vienu un daudzi pret vienu.

### <a name="add-additional-data-optional"></a>Pievienot papildu datus (neobligāti)

1. Atlasiet **Pievienot datus** klientu **darbībām**.

1. Atlasiet semantiskās darbības tipu, kurā ir dati, kurus vēlaties izmantot. Ja darbība nav iestatīta, atlasiet **šeit** un izveidojiet to.

1. Sadaļā **Darbības**, ja aktivitātes izveides laikā aktivitātes atribūti tika semantiski kartēti izvēlieties konkrētus atribūtus vai entītiju, uz kuru vēlaties koncentrēties aprēķinam. Ja semantiskā kartēšana nenotika, atlasiet **Rediģēt** un kartējiet savus datus.

1. Atlasiet **Tālāk** un pārskatiet šim modelim nepieciešamos atribūtus.

1. Atlasiet **Saglabāt**.

1. Atlasiet **Tālāk**

1. Ja vēlaties, atlasiet **Pievienot datus** **Klientu datiem**.

1. Kartējiet semantiskos atribūtus uz laukiem, kas ir jūsu identificētie klientu dati. Izmantotajiem laukiem vajadzētu bieži mainīties, lai nodrošinātu modeļa vislabāko veiktspēju. Piemēram, atlasot lauku "Klasifikācija", kas mainīs katru mēnesi, tiks izmantota tikai pēdējā vērtība laukā prognoze, lai gan vēsturiski tā pati vērtība var nebūt piemērojama klientam, veidojot prognoze shēmas.

1. Atlasiet **Tālāk**.

### <a name="provide-an-optional-list-of-benchmark-accounts"></a>Norādiet neobligātu sarakstu ar procesu mērījumu uzņēmumiem

Pievienojiet biznesa klientu un uzņēmumu sarakstu, kurus vēlaties izmantot kā procesu mērījumus. Šo [etalonkontu](#view-prediction-results) informācija ietver to zuduma rezultātu un visietekmīgākās funkcijas, kas ietekmēja to zuduma prognoze.

1. Atlasīt **+ Pievienot klientus**.

1. Izvēlieties klientus, kas darbojas kā procesu mērījumi.

1. Atlasiet **Tālāk**.

---

### <a name="set-update-schedule"></a>Iestatīt grafika atjaunināšanu

1. **Lai veiktu darbību Datu atjauninājumi**, izvēlieties frekvenci, lai atkārtoti apmācītu savu modeli. Šis iestatījums ir svarīgs, lai atjauninātu prognožu precizitāti, jo programmā Customer Insights tiek iekļauti jauni dati. Lielākā daļa uzņēmumu var pārkvalificēties reizi mēnesī un iegūt labu precizitāti to prognozēšanai.

1. Atlasiet **Tālāk**.

### <a name="review-and-run-the-model-configuration"></a>Modeļa konfigurācijas pārskatīšana un palaišana

Darbībā Pārskatīšana **un izpilde** tiek rādīts konfigurācijas kopsavilkums, un tā nodrošina iespēju veikt izmaiņas pirms prognoze izveides.

1. Atlasiet **Rediģēt**, veicot kādu no darbībām, lai pārskatītu un veiktu izmaiņas.

1. Ja esat apmierināts ar atlasi, atlasiet **Saglabāt un palaist**, lai sāktu modeļa darbību. Atlasiet **Gatavs**. Cilne **Manas prognozes** tiek rādīta, kamēr tiek veidota prognoze. Atkarībā no prognozēšanas laikā izmantojamā datu daudzuma process var aizņemt vairākas stundas.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-prediction-results"></a>Prognoze rezultātu skatīšana

1. Dodieties uz **izlūkošanas** > **prognozēm**.

1. **Cilnē Manas prognozes** atlasiet prognoze, kuru vēlaties skatīt.

# <a name="individual-consumers-b-to-c"></a>[Atsevišķi patērētāji (B2C)](#tab/b2c)

Rezultātu lapā ir trīs primāro sadaļu dati:

[!INCLUDE [predict-transaction-results](includes/predict-transaction-results.md)]

# <a name="business-accounts-b-to-b"></a>[Uzņēmumu konti (B2B)](#tab/b2b)

Rezultātu lapā ir trīs primāro sadaļu dati:

[!INCLUDE [predict-transaction-results](includes/predict-transaction-results.md)]

Ietekmīgu **līdzekļu analīzes** informācijas lapā ir četras datu sadaļas:

- Labajā rūtī atlasiet vienumu sadaļā **Populārākie klienti** vai **Etalona klienti**. Abi saraksti tiek pasūtīti, to vērtība samazinoties un vai nu rezultāts ir tikai klientam, vai arī apvienots rezultāts klientiem, un sekundārais līmenis, piemēram, produktu kategorija. Atlasītais vienums nosaka šīs lapas saturu.

  - **Populārākie klienti**: saraksts ar 10 klientiem, kuriem ir vislielākais un vismazākais zuduma risks, pamatojoties uz viņu zuduma rezultātiem.
  - **Procesu mērījumu klienti**: saraksts ar līdz pat 10 klientiem, kuri tika atlasīti modeļa konfigurēšanas laikā.

- **Zuduma rezultāts**: rāda zuduma rezultātu atlasītajam elementam labajā rūtī.

- **Zuduma riska sadalījums:** parāda zuduma riska sadalījumu starp klientiem un procentili, kurā atrodas atlasītais klients.

- **Populārākās funkcijas, kas palielina un samazina zuduma risku:** uzskaita piecas galvenās funkcijas, kas palielināja un samazināja atlasītā vienuma zuduma risku labajā rūtī. Parāda šī vienuma līdzekļa vērtību un tā ietekmi uz katras ietekmīgās funkcijas rezultātu. Tiek rādīta arī katra līdzekļa vidējā vērtība zema, vidēja un augsta klientu zuduma segmentos. Tas palīdz labāk kontekstualizēt atlasītā elementa augšējo ietekmes līdzekļu vērtību un salīdzināt to ar zema, vidēja un augsta zuduma klientu segmentiem.

  - Zems: konti vai konta un sekundārā līmeņa kombinācijas ar zuduma rezultātu no 0 līdz 0,33.
  - Vidējs: konti vai kontu un sekundāro līmeņu kombinācijas ar zuduma rezultātu no 0,33 līdz 0,66.
  - Augsts: konti vai kontu un sekundāro līmeņu kombinācijas, kuru zuduma rezultāts ir lielāks par 0,66.

  Kad jūs prognozējat zudumu uzņēmuma līmenī, visi uzņēmumi tiek ņemti vērā, atvasinot vidējās līdzekļu vērtības zuduma segmentiem. Katra uzņēmuma sekundārā līmeņa zuduma prognozēm zuduma segmentu atvasināšana ir atkarīga no atlasītā sānu rūts elementa sekoundārā līmeņa. Piemēram, ja krājumam ir sekundārs produktu kategorijas līmenis (biroja piederumi), tad, atvasinot vidējās funkciju vērtības zuduma segmentiem, tiek ņemti vērā tikai tie vienumi, kuru preču kategorija ir biroja piederumi kā produktu kategorija. Šī loģika tiek pielietota, lai nodrošinātu elementa līdzekļu vērtību taisnīgu salīdzinājumu ar vidējām vērtībām maziem, vidējiem un augstiem segmentiem.

  Dažos gadījumos zema, vidēja vai augsta segmenta vidējā vērtība ir tukša vai nav pieejama, jo nav elementu, kas pieder atbilstošajiem zuduma segmentiem, pamatojoties uz iepriekš minēto definīciju.

  Vērtībām, kuru vērtība ir vidējam zemam, vidējam un augstam, ir atšķirīgas attiecībā uz iedarboju funkcijām, piemēram, valsti vai nozari. Tā kā līdzekļa "vidējā" vērtība neattiecas uz kategoriju līdzekļiem, šajās kolonnās vērtībām ir tādu klientu proporcija, kuru segmenti ir mazi, vidēji vai augsti, un tiem ir tāda pati līdzekļa vērtība kā sānu panelī atlasītajam elementam.

---

 > [!NOTE]
 > Šī modeļa izvades vienībā ChurnScore *parāda prognozēto zuduma varbūtību, un* IsChurn *ir binārs marķējums,* kura pamatā *ir ChurnScore* ar 0,5 slieksni. Ja šis noklusējuma slieksnis nedarbojas jūsu scenārijam, [izveidojiet jaunu segmentu](segments.md#create-a-segment) ar vēlamo slieksni. Ne visi klienti ir aktīvi. Iespējams, daži no viņiem nav bijuši aktīvi ilgāku laiku un jau tiek uzskatīti par zudušiem, pamatojoties uz jūsu zuduma definīciju. Zuduma riska prognoze klientiem, kas jau ir zuduši, nav lietderīga, jo tie nav ieinteresētā auditorija.
>
> Lai skatītu zuduma rezultātu, dodieties uz **Datu** > **entītijas** un skatiet datu cilni izvades entītijai, kuru definējāt šim modelim.

[!INCLUDE [footer-include](includes/footer-banner.md)]
