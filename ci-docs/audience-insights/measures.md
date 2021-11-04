---
title: Mēru izveide un pārvaldība
description: Definējiet mērus, lai analizētu un atspoguļotu sava uzņēmuma veiktspēju.
ms.date: 09/30/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: d77d1901fee4771537554c05d3963316d0fb37cb
ms.sourcegitcommit: 31985755c7c973fb1eb540c52fd1451731d2bed2
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 10/22/2021
ms.locfileid: "7673478"
---
# <a name="define-and-manage-measures"></a>Mēru definēšana un pārvaldība

Mēri palīdz labāk izprast klientu paradumus un uzņēmuma veiktspēju. Tie aplūko atbilstošās vērtības no [vienotajiem profiliem](data-unification.md). Piemēram, uzņēmums vēlas redzēt *kopējos tēriņus uz klientu*, lai izprastu katra klienta pirkumu vēsturi vai izmērīt *uzņēmuma kopējos pārdošanas apjomus*, lai izprastu kopējā līmeņa ieņēmumus visā uzņēmumā.  

Mēri tiek izveidoti, izmantojot mērījumu veidotāju, datu vaicājumu platformu ar dažādiem operatoriem un vienkāršām kartēšanas opcijām. Tas ļauj filtrēt datus, grupēt rezultātus, noteikt [entītiju attiecību ceļus](relationships.md) un priekšskatīt izvadi.

Izmantojiet mērījumu veidotāju, lai plānotu uzņēmuma aktivitātes, vaicājot klientu datus un izgūstot ieskatus. Piemēram, *katra klienta kopējo tēriņu* un *katra klienta kopējo ienākumu* mēra izveide palīdz identificēt klientu grupu, kuriem ir augsti tēriņi, bet arī augsti ieņēmumi. Varat [izveidot segmentu](segments.md), lai vadītu nākamās, vislabāk piemērotās darbības. 

## <a name="build-your-own-measure-from-scratch"></a>Personīgā mērījuma izveide no nulles

Šajā sadaļā ir paskaidrots, kā izveidot jaunu mērījumu no nulles. Varat izveidot pasākumu ar datu atribūtiem no datu entītijām, kurām ir iestatītas attiecības, lai izveidotu savienojumu ar vienotā klienta profila entītiju.

# <a name="individual-consumers-b-to-c"></a>[Atsevišķi patērētāji (B2C)](#tab/b2c)

1. Auditorijas ieskatu sadaļā ejiet uz **Mēri**.

1. Atlasiet **Jauns** un izvēlieties **Izveidot savu**.

1. Atlasiet **Rediģēt nosaukumu** un norādiet mēra **Nosaukumu**. 

1. Konfigurācijas apgabalā izvēlieties apkopošanas funkciju no **Atlasīt funkciju** nolaižamās izvēlnes. Apkopošanas funkcijas ir šādas: 
   - **Sum**
   - **Vidējais**
   - **Skaits**
   - **Skaitīt unikālos vienumus**
   - **Maksimums**
   - **Minimums**
   - **Pirmā**: tiek ņemta pirmā datu ieraksta vērtība
   - **Pēdējā**: tiek ņemta pēdējā vērtība, kas tika pievienota datu ierakstam

   :::image type="content" source="media/measure-operators.png" alt-text="Mēru aprēķinu operatori.":::

1. Atlasiet vienumu **Pievienot atribūtu**, lai atlasītu datus, kas nepieciešami šī mēra izveidei.
   
   1. Atlasiet cilni **Atribūti**. 
   1. Datu entītija: izvēlieties entītiju, kurā iekļauts mēra atribūts, ko vēlaties aprēķināt. 
   1. Datu atribūts: izvēlieties atribūtu, ko vēlaties izmantot apkopošanas funkcijai, lai aprēķinātu mēru. Vienlaikus vienā reizē var atlasīt tikai vienu atribūtu.
   1. Atlasiet arī esoša mēra datu atribūtu, atlasot **Mērījumi** cilni. Varat arī meklēt entītijas vai mēra nosaukumu. 
   1. Atlasiet vienumu **Pievienot**, lai mēram pievienotu atlasīto atribūtu.

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Atlasiet atribūtu, ko izmantot mērījumā.":::

1. Lai izveidotu sarežģītākus mērījumus, to funkcijai var pievienot papildu atribūtus vai lietot matemātikas operatorus.

   :::image type="content" source="media/measure-math-operators.png" alt-text="Sarežģītu mērījumu izveide, izmantojot matemātikas operatorus.":::

1. Lai pievienotu filtrus, konfigurācijas apgabalā atlasiet **Filtri**. 
  
   1. Sadaļā **Pievienot atribūtu**, kas atrodas **Filtru** rūtī, atlasiet atribūtu, ko vēlaties izmantot, lai izveidotu filtru.
   1. Iestatiet filtra operatorus, lai definētu filtru katram atlasītajam atribūtam.
   1. Atlasiet vienumu **Lietot**, lai mērījumam pievienotu filtrus.

1. Lai pievienotu dimensijas, konfigurācijas apgabalā atlasiet **Dimensija**. Dimensijas tiek rādītas kā kolonnas mērījuma izvades entītijā.
 
   1. Atlasiet vienumu **Rediģēt dimensijas**, lai pievienotu datu atribūtus, pēc kuriem vēlaties grupēt mērus. Piemēram, pilsēta vai dzimums. Pēc noklusējuma *CustomerID* dimensija tiek atlasīta, lai izveidotu *klienta līmeņa mērījumus*. Ja vēlaties izveidot *uzņēmuma līmeņa mērījumus*, varat noņemt noklusējuma dimensiju.
   1. Atlasiet vienumu **Pabeigts**, lai mērījumam pievienotu dimensijas.

1. Ja datos ir vērtības, kas jāaizstāj ar veselu skaitli, atlasiet **Kārtulas**. Konfigurējiet kārtulu un pārliecinieties, ka kā aizstājējus izvēlējāties tikai veselus skaitļus. Piemēram, aizstājiet *nulli* ar *0*.

1. Ja starp kartēto datu entītiju un *Klienta* entītiju ir vairāki ceļi, ir jāizvēlas viens no identificētajiem [entītiju attiecību ceļiem](relationships.md). Mērījumu rezultāti var atšķirties atkarībā no atlasītā ceļa. 
   
   1. Atlasiet **Attiecību ceļu** un izvēlieties entītijas ceļu, kas jāizmanto pasākuma identificēšanai. Ja entītijai *Klients* ir tikai viens ceļš, šī vadīkla netiks rādīta.
   1. Atlasiet **Pabeigts**, lai lietotu jūsu atlasi. 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Atlasiet entītijas ceļu mēram.":::

1. Lai mērījumam pievienotu papildu aprēķinus, atlasiet **Jauns aprēķins**. Entītijas var izmantot tikai tajā pašā entītijas ceļā jauniem aprēķiniem. Papildu aprēķini tiek rādīti kā jaunas kolonnas mērījumu izvades entītijā.

1. Aprēķinā atlasiet **...**, lai **Dublētu**, **Pārdēvētu** vai **Noņemtu** aprēķinu no mērījuma.

1. **Priekšskatījuma** apgabalā redzēsit izvades entītijas mērījuma datu shēmu, tostarp filtrus un dimensijas. Priekšskatījums dinamiski reaģē uz konfigurācijas izmaiņām.

1. Atlasiet opciju **Izpildīt**, lai aprēķinātu konfigurētā mērījuma rezultātus. Atlasiet **Saglabāt un aizvērt**, ja vēlaties saglabāt pašreizējo konfigurāciju un izpildīt mērījumu vēlāk.

1. Dodieties uz **Mērījumi**, lai sarakstā redzētu jaunizveidoto mērījumu.

# <a name="business-accounts-b-to-b"></a>[Uzņēmumu konti (B2B)](#tab/b2b)

1. Auditorijas ieskatu sadaļā ejiet uz **Mēri**.

1. Atlasiet **Jauns** un izvēlieties **Izveidot savu**.

1. Atlasiet **Rediģēt nosaukumu** un norādiet mēra **Nosaukumu**. 

1. Konfigurācijas apgabalā izvēlieties apkopošanas funkciju no **Atlasīt funkciju** nolaižamās izvēlnes. Apkopošanas funkcijas ir šādas: 
   - **Sum**
   - **Vidējais**
   - **Skaits**
   - **Skaitīt unikālos vienumus**
   - **Maksimums**
   - **Minimums**
   - **Pirmā**: tiek ņemta pirmā datu ieraksta vērtība
   - **Pēdējā**: tiek ņemta pēdējā vērtība, kas tika pievienota datu ierakstam

   :::image type="content" source="media/measure-operators.png" alt-text="Mēru aprēķinu operatori.":::

1. Atlasiet vienumu **Pievienot atribūtu**, lai atlasītu datus, kas nepieciešami šī mēra izveidei.
   
   1. Atlasiet cilni **Atribūti**. 
   1. Datu entītija: izvēlieties entītiju, kurā iekļauts mēra atribūts, ko vēlaties aprēķināt. 
   1. Datu atribūts: izvēlieties atribūtu, ko vēlaties izmantot apkopošanas funkcijai, lai aprēķinātu mēru. Vienlaikus vienā reizē var atlasīt tikai vienu atribūtu.
   1. Atlasiet arī esoša mēra datu atribūtu, atlasot **Mērījumi** cilni. Varat arī meklēt entītijas vai mēra nosaukumu. 
   1. Atlasiet vienumu **Pievienot**, lai mēram pievienotu atlasīto atribūtu.

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Atlasiet atribūtu, ko izmantot mērījumā.":::

1. Lai izveidotu sarežģītākus mērījumus, to funkcijai var pievienot papildu atribūtus vai lietot matemātikas operatorus.

   :::image type="content" source="media/measure-math-operators.png" alt-text="Sarežģītu mērījumu izveide, izmantojot matemātikas operatorus.":::

1. Lai pievienotu filtrus, konfigurācijas apgabalā atlasiet **Filtri**. 
  
   1. Sadaļā **Pievienot atribūtu**, kas atrodas **Filtru** rūtī, atlasiet atribūtu, ko vēlaties izmantot, lai izveidotu filtru.
   1. Iestatiet filtra operatorus, lai definētu filtru katram atlasītajam atribūtam.
   1. Atlasiet vienumu **Lietot**, lai mērījumam pievienotu filtrus.

1. Lai pievienotu dimensijas, konfigurācijas apgabalā atlasiet **Dimensija**. Dimensijas tiek rādītas kā kolonnas mērījuma izvades entītijā.
 
   1. Atlasiet vienumu **Rediģēt dimensijas**, lai pievienotu datu atribūtus, pēc kuriem vēlaties grupēt mērus. Piemēram, pilsēta vai dzimums. Pēc noklusējuma *CustomerID* dimensija tiek atlasīta, lai izveidotu *klienta līmeņa mērījumus*. Ja vēlaties izveidot *uzņēmuma līmeņa mērījumus*, varat noņemt noklusējuma dimensiju.
   1. Atlasiet vienumu **Pabeigts**, lai mērījumam pievienotu dimensijas.

1. Ja datos ir vērtības, kas jāaizstāj ar veselu skaitli, atlasiet **Kārtulas**. Konfigurējiet kārtulu un pārliecinieties, ka kā aizstājējus izvēlējāties tikai veselus skaitļus. Piemēram, aizstājiet *nulli* ar *0*.

1. Jūs varat izmantot slēdzi **Apkopot pakārtotos uzņēmumus**, ja [izmantojat uzņēmumus ar hierarhijām](relationships.md#set-up-account-hierarchies).
   - Ja iestatījums ir **Izslēgts**, mērījums tiek aprēķināts katram kontam. Katrs konts tiek iegūts no rezultātiem.
   - Ja iestatījums ir **Ieslēgts**, atlasiet **Rediģēt**, lai izvēlētos uzņēmumu hierarhiju atbilstoši noingestajām hierarhijām. Šis pasākums dos tikai vienu rezultātu, jo tas tiek apkopots ar apakškontiem.

1. Ja starp kartēto datu entītiju un *Klienta* entītiju ir vairāki ceļi, ir jāizvēlas viens no identificētajiem [entītiju attiecību ceļiem](relationships.md). Mērījumu rezultāti var atšķirties atkarībā no atlasītā ceļa. 
   
   1. Atlasiet **Attiecību ceļu** un izvēlieties entītijas ceļu, kas jāizmanto pasākuma identificēšanai. Ja entītijai *Klients* ir tikai viens ceļš, šī vadīkla netiks rādīta.
   1. Atlasiet **Pabeigts**, lai lietotu jūsu atlasi. 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Atlasiet entītijas ceļu mēram.":::

1. Aprēķinā atlasiet **...**, lai **Dublētu**, **Pārdēvētu** vai **Noņemtu** aprēķinu no mērījuma.

1. **Priekšskatījuma** apgabalā redzēsit izvades entītijas mērījuma datu shēmu, tostarp filtrus un dimensijas. Priekšskatījums dinamiski reaģē uz konfigurācijas izmaiņām.

1. Atlasiet opciju **Izpildīt**, lai aprēķinātu konfigurētā mērījuma rezultātus. Atlasiet **Saglabāt un aizvērt**, ja vēlaties saglabāt pašreizējo konfigurāciju un izpildīt mērījumu vēlāk.

1. Dodieties uz **Mērījumi**, lai sarakstā redzētu jaunizveidoto mērījumu.

---

## <a name="use-a-template-to-build-a-measure"></a>Veidnes izmantošana mērījuma veidošanā

Lai izveidotu bieži izmantotus mērījumus, varat lietot to iepriekš definētās veidnes. Detalizēti veidņu apraksti un vadība palīdzēs jums sekmīgi izveidot mērījumu. Veidnes tiek veidotas uz kartētajiem datiem no *Vienotās darbības* entitījas. Tāpēc, pirms no veidnes izveidojat mērījumu, pārliecinieties, ka esat konfigurējuši [klientu darbības](activities.md).

# <a name="individual-consumers-b-to-c"></a>[Atsevišķi patērētāji (B2C)](#tab/b2c)

Lai izveidotu bieži izmantotus mērījumus, varat lietot to iepriekš definētās veidnes. Detalizēti veidņu apraksti un vadība palīdzēs jums sekmīgi izveidot mērījumu. Veidnes tiek veidotas uz kartētajiem datiem no *Vienotās darbības* entitījas. Tāpēc, pirms no veidnes izveidojat mērījumu, pārliecinieties, ka esat konfigurējuši [klientu darbības](activities.md).

Pieejamās mērījumu veidnes: 
- Vidējā transakcijas vērtība (ATV)
- Kopējā transakciju vērtība
- Vidējie ieņēmumi dienā
- Gada vidējie ieņēmumi
- Transakciju skaits
- Iegūtie lojalitātes punkti
- Izmantotie lojalitātes punkti
- Lojalitātes punktu bilance
- Klienta aktivitātes laika periods
- Dalības ilgums lojalitātes programmā
- Laiks kopš pēdējā pirkuma

Šajā procedūrā aprakstītas darbības jauna mērījuma izveidei, izmantojot veidni.

1. Sadaļā Auditorijas ieskati ejiet uz **Mēri**.

1. Atlasiet **Jauns** un atlasiet **Izvēlieties veidni**.

   :::image type="content" source="media/measure-use-template.png" alt-text="Nolaižamās izvēlnes ekrānuzņēmums, veidojot jaunu mērījumu ar iezīmētu veidni.":::

1. Atrodiet sev atbilstošo veidni un atlasiet **Izvēlēties veidni**.

1. Pārskatiet prasītos datus un atlasiet **Sākt darbu**, ja visi dati ir pareizi.

1. Rūtī **Rediģēt nosaukumu** ievadiet sava mērījuma nosaukumu un izvades entitīju. 

1. Atlasiet **Gatavs**.

1. Sadaļā **Iestatīt laikposmu** definējiet lietojamo datu laika periodu. Izvēlieties, vai jaunajam mērījumam jāaptver visa datu kopa, atlasot **Viss laiks**, vai vēlaties, lai mērījums koncentrētos uz **Noteiktu laika periodu**.

   :::image type="content" source="media/measure-set-time-period.png" alt-text="Ekrānuzņēmums, kurā redzama laika perioda sadaļa, kad mērījumu konfigurē no veidnes.":::

1. Nākamajā sadaļā atlasiet **Pievienot datus**, lai izvēlētos darbībs un kartētu atbilstošos datus no savas *Vienotās darbības* entitījas.

    1. 1. darbība no 2: Sadaļā **Darbības veids** izvēlieties entitījas veidu, kuru vēlaties lietot. **Darbībām** atlasiet entitījas, kuras vēlaties kartēt.
    1. 2. darbība no 2: Atlasiet atribūtu no *Vienotās darbības* entitījas formulas prasītajam komponentam. Piemēram, vidējai transakcijas vērtībai tas ir komponents, kas apzīmē transakcijas vērtību. **Darbības laikspiedolam** atlasiet atribūtu no Vienotās darbības entitījas, kas apzīmē darbības datumu un laiku.
   
1. Kad datu kartēšana ir izdevusies, varat redzēt statusu kā **Pabeigts** un kartēto darbību un atribūtu nosaukumu.

   :::image type="content" source="media/measure-template-configured.png" alt-text="Ekrānuzņēmums pabeigtai mērījuma veidnes konfigurēšanai.":::

1. Tagad varat atlasīt **Palaist**, lai aprēķinātu mērījuma rezultātus. Lai to precizētu vēlāk, atlasiet **Saglabāt melnrakstu**.

# <a name="business-accounts-b-to-b"></a>[Uzņēmumu konti (B2B)](#tab/b2b)

Šis līdzeklis ir pieejams tikai pasākumiem, kas izveidoti vidē, kurā kā primāro mērķauditoriju ir individuālie klienti.

---

## <a name="manage-your-measures"></a>Pārvaldiet savus mērus

Mērījumu saraksts atrodams lapā **Mērījumi**.

Atradīsiet informāciju par mēra tipu, izveidotāju, izveides datumu, statusu un stāvokli. Kad sarakstā atlasāt kādu mēru, varat priekšskatīt izvadi un lejupielādēt CSV failu.

Lai vienlaikus atsvaidzinātu visus mērus, atlasiet **Atsvaidzināt visu**, neatlasot noteiktu mēru.

> [!div class="mx-imgBorder"]
> ![Darbības, lai pārvaldītu atsevišķus mērus.](media/measure-actions.png "Darbības, lai pārvaldītu atsevišķus mērus.")

Sarakstā atlasiet mēru, lai izvēlētos kādu no šīm opcijām:

- Atlasiet mēra nosaukumu, lai skatītu tā detalizētu informāciju.
- **Rediģējiet** mēra konfigurāciju.
- **Atsvaidzināt** mēru, pamatojoties uz jaunākajiem datiem.
- **Pārdēvējiet** mēru.
- **Dzēsiet** mēru.
- **Aktivizēt** vai **Deaktivizēt**. Neaktīvie mēri netiks atsvaidzināti [plānotās atsvaidzināšanas laikā](system.md#schedule-tab).

> [!TIP]
> Uzdevumiem/procesiem ir [seši statusu tipi](system.md#status-types). Turklāt vairums procesu [ir atkarīgi no citiem pakārtotiem procesiem](system.md#refresh-policies). Varat atlasīt procesa statusu, lai skatītu detalizētu informāciju par visa uzdevuma norisi. Atlasot opciju **Skatīt detalizētu informāciju** par kādu no uzdevumiem, jums tiks sniegta papildinformācija: apstrādes laiks, pēdējās apstrādes datums un visas ar uzdevumu saistītās kļūdas un brīdinājumi.

## <a name="next-step"></a>Nākamā darbība

Esošus mērus var izmantot, lai izveidotu [klientu segmentu](segments.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
