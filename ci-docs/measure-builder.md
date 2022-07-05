---
title: Jaunu pasākumu izveide, izmantojot pasākumu veidotāju
description: Veidojiet mērus no nulles, lai analizētu galvenos rādītājus par savu uzņēmumu.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.author: wameng
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-measure-builder
- customerInsights
ms.openlocfilehash: f3ec86806074a12c1107648303ed2d65e97ebc69
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 06/29/2022
ms.locfileid: "9083019"
---
# <a name="create-new-measures-with-the-measure-builder"></a>Jaunu pasākumu izveide, izmantojot pasākumu veidotāju

Šajā rakstā ir paskaidrots, kā izveidot jaunu [pasākumu](measures.md) no nulles. Mēru veidotājs ļauj definēt aprēķinus, izmantojot matemātikas operatorus, apkopošanas funkcijas un filtrus. Varat izveidot mēru ar atribūtiem no entītijām, kas ir saistītas ar vienoto *klienta* entītiju.

Pasākumu izveide B-to-C un B-to-B vidē darbojas tāpat. Tomēr, ja jūs esat B-to-B vide [izmanto kontus ar hierarhijām](relationships.md#set-up-account-hierarchies), varat izvēlēties apkopot mēru saistītajos apakškontos.

Varat arī ātri izveidot mēru, izvēloties no bieži izmantoto un iepriekš definēto mēru kopas. Papildinformāciju skatiet rakstā [Veidnes izmantošana mēra izveidei](measure-templates.md).

# <a name="individual-consumers-b-to-c"></a>[Atsevišķi patērētāji (B2C)](#tab/b2c)

Mērus var izveidot atsevišķu klientu līmenī (klienta atribūts, klienta mērs) vai uzņēmuma/organizācijas līmenī (biznesa mērs). Klienta atribūts un klientu mērs ir divi veidi, kas ļauj izsekot katra klienta veiktspēju. Piemēram, katra klienta kopējie tēriņi. Biznesa pasākumi ļauj izsekot katra uzņēmuma veiktspējai. Piemēram, uzņēmuma kopējie ieņēmumi.

- Klienta atribūts: ģenerē izvadi kā jaunu atribūtu, kas tiek saglabāts kā jauna kolonna sistēmas ģenerētajā entītijā ar nosaukumu *Customer_Measure*. Atsvaidzinot klienta atribūtu, visi pārējie Customer_Measure *entītijas* klienta atribūti tiek atsvaidzināti vienlaicīgi. Turklāt klienta atribūti tiek parādīti klienta profila kartē. Kad klienta atribūts ir palaists vai saglabāts, to nevar mainīt uz klientu mēru.

- Klientu mērs: ģenerē izvadi kā savu entītiju, un pēc palaišanas vai saglabāšanas to nevar mainīt uz klienta atribūtu. Klientu mēri netiek rādīti klienta profila kartītē.

- Biznesa pasākums: ģenerē izvadi kā savu entītiju un parāda jūsu Customer Insights vides sākumlapā.

1. Dodieties uz **sadaļu Pasākumi**.

1. Atlasiet **Jauns** un izvēlieties **Izveidot savu**.

   :::image type="content" source="media/measure-b2c.png" alt-text="Tukšs konfigurācijas ekrāns mērījumam no B līdz C." lightbox="media/measure-b2c.png":::

1. Lai izsekotu biznesa līmeņa veiktspēju, pārslēdziet **mēra tipu** uz **Biznesa līmenis**. **Klienta līmenis** tiek atlasīts pēc noklusējuma. **Klienta līmenis** automātiski pievieno atribūtu *CustomerId* dimensijām, savukārt **biznesa līmenis** to automātiski noņem.

1. Konfigurācijas apgabalā nolaižamajā izvēlnē Atlasīt funkciju **izvēlieties apkopošanas** funkciju. Apkopošanas funkcijas ir šādas:
   - **Sum**
   - **Vidējais**
   - **Skaits**
   - **Skaitīt unikālos vienumus**
   - **Maksimums**
   - **Minimums**
   - **Pirmā**: tiek ņemta pirmā datu ieraksta vērtība
   - **Pēdējā**: tiek ņemta pēdējā vērtība, kas tika pievienota datu ierakstam
   - **ArgMax**: atrod datu ierakstu, kas dod maksimālu vērtību no mērķa funkcijas
   - **ArgMin**: atrod datu ierakstu, kas dod minimālo vērtību no mērķa funkcijas

1. Atlasiet vienumu **Pievienot atribūtu**, lai atlasītu datus, kas nepieciešami šī mēra izveidei.

   1. Atlasiet cilni **Atribūti**.
   1. Datu entītija: izvēlieties entītiju, kurā iekļauts mēra atribūts, ko vēlaties aprēķināt.
   1. Datu atribūts: izvēlieties atribūtu, ko vēlaties izmantot apkopošanas funkcijai, lai aprēķinātu mēru. Vienlaikus vienā reizē var atlasīt tikai vienu atribūtu.
   1. Atlasiet arī esoša mēra datu atribūtu, atlasot **Mērījumi** cilni. Varat arī meklēt entītijas vai mēra nosaukumu.
   1. Atlasiet vienumu **Pievienot**, lai mēram pievienotu atlasīto atribūtu.

1. Lai izveidotu sarežģītākus mērījumus, to funkcijai var pievienot papildu atribūtus vai lietot matemātikas operatorus.

1. Lai pievienotu filtrus, konfigurācijas apgabalā atlasiet **Filtri**. Filtru lietošana mēra aprēķināšanai izmantos tikai tos ierakstus, kas atbilst filtriem.
  
   1. Sadaļā **Pievienot atribūtu**, kas atrodas **Filtru** rūtī, atlasiet atribūtu, ko vēlaties izmantot, lai izveidotu filtru.
   1. Iestatiet filtra operatorus, lai definētu filtru katram atlasītajam atribūtam.
   1. Atlasiet vienumu **Lietot**, lai mērījumam pievienotu filtrus.

1. Atlasiet **Dimensija**, lai izvēlētos citus laukus, kas tiek pievienoti kā kolonnas mēra izvades entītijai.

   1. Atlasiet vienumu **Rediģēt dimensijas**, lai pievienotu datu atribūtus, pēc kuriem vēlaties grupēt mērus. Piemēram, pilsēta vai dzimums.
   > [!TIP]
   > Ja kā mēra tipu **atlasījāt** klienta līmeni **, atribūts** CustomerId *jau ir pievienots.* Ja noņemat atribūtu, **mēra tips** pārslēdzas uz **biznesa līmeni**.
   1. Atlasiet vienumu **Pabeigts**, lai mērījumam pievienotu dimensijas.

1. Ja datos ir vērtības, kas jāaizstāj ar veselu skaitli, atlasiet **Kārtulas**. Konfigurējiet kārtulu un pārliecinieties, ka kā aizstājējus izvēlējāties tikai veselus skaitļus. Piemēram, aizstājiet *nulli* ar *0*.

1. Ja starp kartēto datu entītiju un *Klienta* entītiju ir vairāki ceļi, ir jāizvēlas viens no identificētajiem [entītiju attiecību ceļiem](relationships.md). Mērījumu rezultāti var atšķirties atkarībā no atlasītā ceļa.

   1. Atlasiet **Attiecību ceļu** un izvēlieties entītijas ceļu, kas jāizmanto pasākuma identificēšanai. Ja entītijai *Klients* ir tikai viens ceļš, šī vadīkla netiks rādīta.
   1. Atlasiet **Pabeigts**, lai lietotu jūsu atlasi.

1. Lai mērījumam pievienotu papildu aprēķinus, atlasiet **Jauns aprēķins**. Entītijas var izmantot tikai tajā pašā entītijas ceļā jauniem aprēķiniem. Papildu aprēķini tiek rādīti kā jaunas kolonnas mērījumu izvades entītijā.

1. Atlasiet vertikālo daudzpunkti (&vellip;) aprēķinā, lai **dublētu**, **pārdēvētu** vai **noņemtu** aprēķinu no mēra.

1. **Priekšskatījuma** apgabalā redzēsit izvades entītijas mērījuma datu shēmu, tostarp filtrus un dimensijas. Priekšskatījums dinamiski reaģē uz konfigurācijas izmaiņām.

1. Atlasiet **Rediģēt detalizētu informāciju** blakus mērījumam Bez nosaukuma. Norādiet pasākuma nosaukumu. Pēc izvēles pievienojiet [pasākumam tagus](work-with-tags-columns.md#manage-tags).

   :::image type="content" source="media/measures_edit_details.png" alt-text="Dialoglodziņš Detalizētas informācijas rediģēšana.":::

1. Atlasiet opciju **Izpildīt**, lai aprēķinātu konfigurētā mērījuma rezultātus. Atlasiet **Saglabāt un aizvērt**, ja vēlaties saglabāt pašreizējo konfigurāciju un izpildīt mērījumu vēlāk.

1. Dodieties uz **Mērījumi**, lai sarakstā redzētu jaunizveidoto mērījumu.

# <a name="business-accounts-b-to-b"></a>[Uzņēmumu konti (B2B)](#tab/b2b)

Varat izveidot mērus atsevišķu kontu līmenī (klientu mērs) vai visu kontu līmenī (uzņēmējdarbības mērs).

- Klientu mērs: ģenerē izvadi kā savu entītiju. Klientu mēri netiek rādīti klienta profila kartītē.

- Biznesa pasākums: ģenerē izvadi kā savu entītiju un parāda jūsu Customer Insights vides sākumlapā.

1. Dodieties uz **sadaļu Pasākumi**.

1. Atlasiet **Jauns**.

   :::image type="content" source="media/measure-b2b.png" alt-text="Tukšs konfigurācijas ekrāns B-to-B mērījumam.":::

1. Konfigurācijas apgabalā nolaižamajā izvēlnē Atlasīt funkciju **izvēlieties apkopošanas** funkciju. Apkopošanas funkcijas ir šādas:
   - **Sum**
   - **Vidējais**
   - **Skaits**
   - **Skaitīt unikālos vienumus**
   - **Maksimums**
   - **Minimums**
   - **Pirmā**: tiek ņemta pirmā datu ieraksta vērtība
   - **Pēdējā**: tiek ņemta pēdējā vērtība, kas tika pievienota datu ierakstam

1. Atlasiet vienumu **Pievienot atribūtu**, lai atlasītu datus, kas nepieciešami šī mēra izveidei.

   1. Atlasiet cilni **Atribūti**.
   1. Datu entītija: izvēlieties entītiju, kurā iekļauts mēra atribūts, ko vēlaties aprēķināt.
   1. Datu atribūts: izvēlieties atribūtu, ko vēlaties izmantot apkopošanas funkcijai, lai aprēķinātu mēru. Vienlaikus vienā reizē var atlasīt tikai vienu atribūtu.
   1. Atlasiet arī esoša mēra datu atribūtu, atlasot **Mērījumi** cilni. Varat arī meklēt entītijas vai mēra nosaukumu.
   1. Atlasiet vienumu **Pievienot**, lai mēram pievienotu atlasīto atribūtu.

1. Lai izveidotu sarežģītākus mērījumus, to funkcijai var pievienot papildu atribūtus vai lietot matemātikas operatorus.

1. Lai pievienotu filtrus, konfigurācijas apgabalā atlasiet **Filtri**. Filtru lietošana mēra aprēķināšanai izmantos tikai tos ierakstus, kas atbilst filtriem.
  
   1. Sadaļā **Pievienot atribūtu**, kas atrodas **Filtru** rūtī, atlasiet atribūtu, ko vēlaties izmantot, lai izveidotu filtru.
   1. Iestatiet filtra operatorus, lai definētu filtru katram atlasītajam atribūtam.
   1. Atlasiet vienumu **Lietot**, lai mērījumam pievienotu filtrus.

1. Atlasiet **Dimensija**, lai izvēlētos citus laukus, kas tiek pievienoti kā kolonnas mēra izvades entītijai.

   1. Atlasiet vienumu **Rediģēt dimensijas**, lai pievienotu datu atribūtus, pēc kuriem vēlaties grupēt mērus. Piemēram, pilsēta vai dzimums.
      > [!TIP]
      > Ja kā mēra tipu **atlasījāt** klienta līmeni **, atribūts** CustomerId *jau ir pievienots.* Ja noņemat atribūtu, **mēra tips** pārslēdzas uz **biznesa līmeni**.
   1. Atlasiet vienumu **Pabeigts**, lai mērījumam pievienotu dimensijas.

1. Ja datos ir vērtības, kas jāaizstāj ar veselu skaitli, atlasiet **Kārtulas**. Konfigurējiet kārtulu un pārliecinieties, ka kā aizstājējus izvēlējāties tikai veselus skaitļus. Piemēram, aizstājiet *nulli* ar *0*.

1. Jūs varat izmantot slēdzi **Apkopot pakārtotos uzņēmumus**, ja [izmantojat uzņēmumus ar hierarhijām](relationships.md#set-up-account-hierarchies).
   - Ja iestatījums ir **Izslēgts**, mērījums tiek aprēķināts katram kontam. Katrs konts tiek iegūts no rezultātiem.
   - Ja iestatījums ir **Ieslēgts**, atlasiet **Rediģēt**, lai izvēlētos uzņēmumu hierarhiju atbilstoši noingestajām hierarhijām. Šis pasākums dos tikai vienu rezultātu, jo tas tiek apkopots ar apakškontiem.

1. Ja starp kartēto datu entītiju un *Klienta* entītiju ir vairāki ceļi, ir jāizvēlas viens no identificētajiem [entītiju attiecību ceļiem](relationships.md). Mērījumu rezultāti var atšķirties atkarībā no atlasītā ceļa.

   1. Atlasiet **Attiecību ceļu** un izvēlieties entītijas ceļu, kas jāizmanto pasākuma identificēšanai. Ja entītijai *Klients* ir tikai viens ceļš, šī vadīkla netiks rādīta.
   1. Atlasiet **Pabeigts**, lai lietotu jūsu atlasi.

1. Atlasiet vertikālo daudzpunkti (&vellip;) aprēķinā, lai **dublētu**, **pārdēvētu** vai **noņemtu** aprēķinu no mēra.

1. **Priekšskatījuma** apgabalā redzēsit izvades entītijas mērījuma datu shēmu, tostarp filtrus un dimensijas. Priekšskatījums dinamiski reaģē uz konfigurācijas izmaiņām.

1. Atlasiet **Rediģēt detalizētu informāciju** blakus mērījumam Bez nosaukuma. Norādiet pasākuma nosaukumu. Pēc izvēles pievienojiet [pasākumam tagus](work-with-tags-columns.md#manage-tags).

   :::image type="content" source="media/measures_edit_details.png" alt-text="Dialoglodziņš Detalizētas informācijas rediģēšana.":::

1. Atlasiet opciju **Izpildīt**, lai aprēķinātu konfigurētā mērījuma rezultātus. Atlasiet **Saglabāt un aizvērt**, ja vēlaties saglabāt pašreizējo konfigurāciju un izpildīt mērījumu vēlāk.

1. Dodieties uz **Mērījumi**, lai sarakstā redzētu jaunizveidoto mērījumu.
