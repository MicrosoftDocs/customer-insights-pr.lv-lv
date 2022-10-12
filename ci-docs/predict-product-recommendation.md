---
title: Produktu ieteikumu prognoze
description: Prognozējiet produktus, kurus klients, visticamāk, iegādāsies vai ar kuriem mijiedarbosies.
ms.date: 09/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: wmelewong
ms.author: wameng
manager: shellyha
ms.openlocfilehash: 0057d6796bb60db44d08b58d9e0daaf6e7c90fde
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610291"
---
# <a name="predict-product-recommendations"></a>Produktu ieteikumu prognoze

Produktu ieteikumu modelis izveido paredzamu produktu ieteikumu kopas. Ieteikumi ir balstīti uz iepriekšējo iegādes scenāriju un klientiem ar līdzīgām iegādes shēmām. Šis modelis ir paredzēts individuāliem patērētājiem (no B līdz C).

Jums ir jābūt biznesa zināšanām par dažādiem produktu veidiem jūsu uzņēmumam un to, kā jūsu klienti mijiedarbojas ar tiem. Mēs iesakām produktus, kurus klienti jau iepriekš iegādājušies, vai ieteikumus par jauniem produktiem.

Uz produktu ieteikumiem var attiekties vietējie tiesību akti un noteikumi, kā arī klientu prasības, kuras modelis nevar konkrēti ņemt vērā. Tāpēc jums ir jāpārskata ieteikumi pirms to piegādes saviem klientiem **,** lai pārliecinātos, ka ievērojat visus piemērojamos likumus vai noteikumus un klientu cerības attiecībā uz to, ko jūs varētu ieteikt.

Šī modeļa izvade sniedz ieteikumus, kuru pamatā ir produkta ID. Jūsu piegādes mehānismam ir jākartē prognozētie produktu ID uz atbilstošu saturu, lai jūsu klienti varētu ņemt vērā lokalizāciju, attēlu saturu un citu uzņēmumam raksturīgu saturu vai uzvedību.

> [!TIP]
> Izmēģiniet produkta ieteikumu prognoze, izmantojot datu paraugus: [produkta ieteikums prognoze parauga ceļvedis](sample-guide-predict-product-recommendation.md).

## <a name="prerequisites"></a>Priekšnoteikumi

- Vismaz [līdzstrādnieku atļaujas](permissions.md)
- Vismaz 100 klientu, vēlams vairāk nekā 10 000 klientu.
- Klienta identifikators — unikāls identifikators, lai saskaņotu transakcijas ar atsevišķu klientu
- Vismaz viens gads darījumu datu, vēlams, divi līdz trīs gadi, lai iekļautu zināmu sezonalitāti. Ideālā gadījumā vismaz trīs vai vairāk darījumi uz vienu klienta ID. Darījumu vēsturē jāiekļauj:
  - **Transakcijas ID**: pirkuma vai transakcijas unikālais identifikators.
  - **Transakcijas datums**: pirkuma vai darījuma datums.
  - **Darījuma** vērtība: pirkuma vai darījuma skaitliskā vērtība.
  - **Unikāls produkta ID**: iegādātā produkta vai pakalpojuma ID, ja jūsu dati ir rindas vienuma līmenī.
  - **Pirkšana vai atgriešana**: būla patiesa/aplama vērtība, kurā *patiess* norāda, ka transakcija ir atgriezusies. Ja pirkšanas vai atgriešanas dati modelī nav sniegti un **darījuma** vērtība ir negatīva, mēs secinām, ka tiek izdarīta peļņa.
- Preču kataloga datu elements, ko izmantot kā preču filtru.

> [!NOTE]
> - Modelim ir nepieciešama jūsu klientu darījumu vēsture, ja transakcija ir jebkādi dati, kas apraksta lietotāja un produkta mijiedarbību. Piemēram, produkta iegāde, nodarbību apmeklējums, pasākuma apmeklējums.
> - Var konfigurēt tikai vienu transakciju vēstures entītiju. Ja ir vairākas pirkšanas entītijas, apvienojiet tās Power Query pirms datu uzņemšanas.
> - Ja pasūtījums un pasūtījuma informācija ir atšķirīgas entitījas, pirms lietošanas modelī tās apvienojiet. Modelis nedarbojas tikai ar entitījas pasūtījuma ID vai kvīts ID.

## <a name="create-a-product-recommendation-prediction"></a>Produktu ieteikumu prognozes izveide

Jebkurā laikā atlasiet **Saglabāt melnrakstu**, lai saglabātu prognoze kā melnrakstu. Melnraksts prognoze tiek parādīts **cilnē Manas prognozes**.

1. Dodieties uz **izlūkošanas** > **prognozēm**.

1. Cilnē **Izveide** atlasiet **Izmantot modeli** elementā **Produkta ieteikumi (priekšskatījums).**

1. Atlasiet **Sākt darbu**.

1. **Nosauciet šo modeli** un **Izvades entītijas nosaukumu**, lai nošķirtu tos no citiem modeļiem vai entītijām.

1. Atlasiet **Tālāk**.

### <a name="define-product-recommendation-preferences"></a>Preču ieteikumu preferenču definēšana

1. Iestatiet to **produktu** skaitu, kurus ieteikt klientam. Šī vērtība ir atkarīga no tā, kā piegādes metode aizpilda datus.

1. Izvēlieties, vai vēlaties iekļaut produktus, ko klienti iepriekš ir iegādājušies, **laukā Atkārtotie pirkumi.**

1. Iestatiet **logu** Atskats atpakaļ ar laika grafiku, ko modelis apsver, pirms atkal iesakāt produktu lietotājam. Piemēram, norādiet, ka klients reizi divos gados iegādājas klēpjdatoru. Modelis aplūko pēdējo divu gadu pirkumu vēsturi, un, ja tas atrod vienumu, krājums tiek filtrēts no ieteikumiem.

1. Atlasiet **Tālāk**

### <a name="add-purchase-history"></a>Pievienot pirkuma vēsturi

1. Atlasiet **Pievienot datus** klientu darījumu **vēsturei**.

1. Atlasiet semantiskās darbības tipu **SalesOrderLine**, kurā ir nepieciešamā transakciju vai pirkumu vēstures informācija. Ja darbība nav iestatīta, atlasiet **šeit** un izveidojiet to.

1. Sadaļā **Darbības**, ja aktivitātes izveides laikā aktivitātes atribūti tika semantiski kartēti izvēlieties konkrētus atribūtus vai entītiju, uz kuru vēlaties koncentrēties aprēķinam. Ja semantiskā kartēšana nenotika, atlasiet **Rediģēt** un kartējiet savus datus.

   :::image type="content" source="media/product-recommendation-select-semantic-activity.PNG" alt-text="Sānu rūts, kurā redzama noteiktu darbību izvēle zem semantiskā tipa.":::

1. Atlasiet **Tālāk** un pārskatiet šim modelim nepieciešamos atribūtus.

1. Atlasiet **Saglabāt**.

1. Atlasiet **Tālāk**.

### <a name="add-product-information-and-filters"></a>Produkta informācijas un filtru pievienošana

Reizēm noderīgi vai jūsu veidotajam prognozes veidam piemēroti ir tikai noteikti produkti. Izmantojiet produktu filtrus, lai identificētu produktu apakškopu ar īpašām īpašībām, ko ieteikt saviem klientiem. Modelis ir izmantos visus pieejamos produktus, lai apgūtu modeļus, taču savā izvadē izmantos vienīgi produktu filtram atbilstošos produktus.

1. Pievienojiet savu preču kataloga entītiju, kurā ir informācija par katru preci. Kartējiet nepieciešamo informāciju un atlasiet **Saglabāt**.

1. Atlasiet **Tālāk**.

1. Atlasiet **Produktu filtri**:

   - **Nav filtru**: Prognozē lietojiet visus produkta ieteikuma produktus.

   - **Definēt konkrētus produktu filtrus**: Produkta ieteikuma prognozē izmantojiet konkrētus produktus. **Preču kataloga atribūtu** rūtī atlasiet atribūtus no preču kataloga entītijas, kurus vēlaties iekļaut filtrā.

     :::image type="content" source="media/product-filters-sidepane.png" alt-text=" Sānu rūts, kurā redzami produktu kataloga entitījas atribūti, kurus atlasīt produktu filtriem.":::

1. Izvēlieties, vai vēlaties, lai preču filtrs tiktu izmantots **un** vai **loģiski** apvienotu atribūtu atlasi no preču kataloga.

   :::image type="content" source="media/product-filters-sample.png" alt-text="Preču filtru konfigurācijas paraugs apvienojumā ar loģiskajiem AND savienotājiem.":::

1. Atlasiet **Tālāk**.

### <a name="set-update-schedule"></a>Iestatīt grafika atjaunināšanu

1. Izvēlieties frekvenci, lai pārkvalificētu savu modeli. Šis iestatījums ir svarīgs, lai atjauninātu prognožu precizitāti, jo programmā Customer Insights tiek iekļauti jauni dati. Lielākā daļa uzņēmumu var pārkvalificēties reizi mēnesī un iegūt labu precizitāti to prognozēšanai.

1. Atlasiet **Tālāk**.

### <a name="review-and-run-the-model-configuration"></a>Modeļa konfigurācijas pārskatīšana un palaišana

Darbībā Pārskatīšana **un izpilde** tiek rādīts konfigurācijas kopsavilkums, un tā nodrošina iespēju veikt izmaiņas pirms prognoze izveides.

1. Atlasiet **Rediģēt**, veicot kādu no darbībām, lai pārskatītu un veiktu izmaiņas.

1. Ja esat apmierināts ar atlasi, atlasiet **Saglabāt un palaist**, lai sāktu modeļa darbību. Atlasiet **Gatavs**. Cilne **Manas prognozes** tiek rādīta, kamēr tiek veidota prognoze. Atkarībā no prognozēšanas laikā izmantojamā datu daudzuma process var aizņemt vairākas stundas.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-prediction-results"></a>Prognoze rezultātu skatīšana

1. Dodieties uz **izlūkošanas** > **prognozēm**.

1. **Cilnē Manas prognozes** atlasiet prognoze, kuru vēlaties skatīt.

Rezultātu lapā ir piecas primārās datu sadaļas.

- **Modeļa veiktspēja:** A, B vai C pakāpe norāda prognoze veiktspēju un var palīdzēt pieņemt lēmumu izmantot izvades entītijā saglabātos rezultātus.
  
  :::image type="content" source="media/product-recommendation-modelperformance.PNG" alt-text="Modeļa veiktspējas rezultāta attēls ar A pakāpi.":::

  Kategorijas tiek noteiktas, pamatojoties uz šādām kārtulām:
  - **A**, ja metrika "Panākumi @ K" ir vismaz par 10% lielāka nekā bāzes līnija.
  - **B**, ja metrika "Veiksme @ K" ir par 0% līdz 10% lielāka nekā bāzes līnija.
  - **C**, ja metrika "Panākumi @ K" ir mazāka par bāzes līniju.
  - **Bāzlīnija**: populārākie produkti pēc pirkumu skaita visos klientos + modeļa identificētie noteikumi = ieteikumu kopums klientiem. Pēc tam šīs prognozes tiek salīdzinātas ar populārākajiem produktiem, ņemot vērā klientu skaitu, kuri iegādājušies šo produktu. Ja klientam ir vismaz viens produkts starp ieteiktajiem produktiem, kas tika redzēti arī populārākajiem iegādātajiem produktiem, šis produkts tiek uzskatīts par daļu no bāzlīnijas. Piemēram, ja 10 no šiem klientiem bija iegādājies ieteikto produktu no 100 kopējiem klientiem, bāzes līnija ir 10%.
  - **Panākumi @ K**: Ieteikumi tiek izveidoti visiem klientiem un salīdzināti ar transakciju laika perioda validācijas kopu. Piemēram, 12 mēnešu periodā 12. mēnesis tiek rezervēts kā datu validācijas kopa. Ja modelis prognozē vismaz vienu lietu, ko iegādāsies 12. mēnesī, pamatojoties uz to, kas tika gūts no iepriekšējiem 11 mēnešiem, klients palielinās metriku "Success@K".

- **Visvairāk ieteiktie produkti (ar rēķinu):** Pieci galvenie klientiem prognozētie produkti.
  
  :::image type="content" source="media/product-recommendation-topproducts.PNG" alt-text="Diagramma, kurā parādīti 5 labākie ieteicamie produkti.":::

- **Ieteikšanas galvenie faktori:** Lai sniegtu produktu ieteikumus, modelis pielieto klienta transakciju vēsturi. Tas apgūst modeļus, balstoties iepriekšējos pirkumos, un atrod līdzības starp klientiem un produktiem. Pēc tam šīs līdzības tiek izmantotas, lai ģenerētu produktu ieteikumus.
  Tālāk minētie faktori var ietekmēt modeļa ģenerētu produkta ieteikumu.
  - **Iepriekšējie darījumi**: ieteiktais produkts bija balstīts uz iepriekšējiem pirkšanas modeļiem. Piemēram, modelis var ieteikt *Surface peli*, ka kāds nesen iegādājies *Surface grāmatu 3* un *Surface pildspalvu*. Modelis ieguva informāciju, ka daudzi klienti iepriekš ir pēc *Surface grāmatas 3* un *Surface pildspalvas* iegādes ir iegādājušies *Surface peli*.
  - **Klientu līdzība**: Ieteikto produktu iepriekš iegādājušies citi klienti ar līdzīgiem pirkšanas modeļiem. Piemēram, Džonam tika ieteiktas *Surface austiņas 2*, jo Dženifera un Breds nesen iegādājās *Surface austiņas 2*. Modelis uzskata, ka Džons ir līdzīgs Dženiferai un Bredam, jo viņiem iepriekš bijuši līdzīgi pirkšanas paradumi.
  - **Produktu līdzība**: Ieteicamais produkts ir līdzīgs citiem produktiem, kurus klients iepriekš bija iegādājies. Modelis uzskata, ka divi ražojumi ir līdzīgi, ja tie tika iegādāti kopā vai ja tos iegādājās līdzīgi klienti. Piemēram, kādam tiek ieteikts *USB atmiņas disks*, jo šī persona iepriekš iegādājās *Adapteru no USB-C uz USB* un modelis uzskata, ka produkts *USB atmiņas disks* ir līdzīgs produktam *Adapters no USB-C uz USB*.

  Katru produkta ieteikumu ietekmē viens vai vairāki no šiem faktoriem. Ieteikumu procentuālā daļa, kurā nozīme bija katram no faktoriem, ir attēlota diagrammā. Šajā piemērā 100% ieteikumu ietekmēja iepriekšējās transakcijas, 60% — klientu līdzība un 22% — produktu līdzība. Pārvelciet kursoru pāri diagrammas joslām, lai aplūkotu precīzu procentuālo daļu, kurā bijusi nozīme katram no faktoriem.
  
  :::image type="content" source="media/product-recommendation-keyrecommendationfactors.png" alt-text="Galvenie ieteikumu faktori, ko modelis apgūst, lai ģenerētu produktu ieteikumus.":::

- **Datu statistika**: pārskats par transakciju, klientu un produktu skaitu, ko modelis uzskatīja par tādu. Tā balstās ievades datos, kuri tika izmantoti, lai apgūtu modeļus un ģenerētu produktu ieteikumus.

  :::image type="content" source="media/product-recommendation-datastatistics.png" alt-text="Datu statistika par ievades datiem, ko modelis izmanto, lai apgūtu modeļus.":::
  
  Modelis izmanto visus pieejamos datus, lai apgūtu modeļus. Tāpēc, ja modeļa konfigurācijā izmantojat preču filtrēšanu, šajā sadaļā tiek parādīts kopējais to preču skaits, kuras modelis analizēja, lai apgūtu modeļus, kas var atšķirties no to preču skaita, kuras atbilst definētajiem filtrēšanas kritērijiem. Filtrēšana tiek piemērota modeļa ģenerētajai izejai.

- **Produkta ieteikumu paraugs:** ieteikumu paraugs, kurus, pēc modeļa domām, klients, visticamāk, iegādāsies. Ja tiek pievienots preču katalogs, preču ID tiek aizstāti ar preču nosaukumiem.

  :::image type="content" source="media/product-recommendation-highconfidence.PNG" alt-text="Saraksts, kurā parādīti augsta līmeņa ieteikumi par individuālu klientu kopu.":::

> [!NOTE]
> Šā modeļa izvades entītijā *Score* parāda ieteikuma kvantitatīvo mērījumu. Modelis iesaka produktus ar augstāku rezultātu iepretim produktiem, kuru rezultāts ir zemāks. Lai skatītu rezultātu, dodieties uz **Datu** > **elementi** un skatiet datu cilni izvades entītijai, kuru definējāt šim modelim.

[!INCLUDE [footer-include](includes/footer-banner.md)]
