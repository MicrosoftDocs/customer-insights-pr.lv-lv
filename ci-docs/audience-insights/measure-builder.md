---
title: Izveidot jaunus pasākumus ar pasākumu veidotāju
description: Veidojiet pasākumus no nulles, lai analizētu galvenos rādītājus par savu uzņēmumu.
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
ms.openlocfilehash: 6370df0287362a5512a837cdb588f5d20ef03d3b
ms.sourcegitcommit: e129a1fa8b020b6bfb6efc3c53fa9d89e1614ad1
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 04/12/2022
ms.locfileid: "8561542"
---
# <a name="use-measure-builder-to-create-measures-from-scratch"></a>Izmantot pasākumu veidotāju, lai izveidotu pasākumus no nulles

Šajā rakstā ir paskaidrots, kā izveidot jaunu [pasākumu](measures.md) no nulles. Mērījumu veidotājs ļauj definēt aprēķinus, izmantojot matemātiskos operatorus, apkopošanas funkcijas un filtrus. Pasākumu var izveidot ar atribūtiem no entītijām, kas ir saistītas ar vienoto *klienta* entītiju.

Pasākumu izveide vidē B-to-C un B-to-B darbojas vienādi. Tomēr, ja esat B-B vide [, kas izmanto kontus ar hierarhijām](relationships.md#set-up-account-hierarchies), varat izvēlēties apkopot pasākumu saistītajos apakškontos.

Varat arī ātri izveidot pasākumu, izvēloties kādu no bieži lietoto un iepriekš definēto pasākumu kopuma. Papildinformāciju skatiet rakstā [Veidnes izmantošana, lai izveidotu pasākumu](measure-templates.md).

# <a name="individual-consumers-b-to-c"></a>[Atsevišķi patērētāji (B2C)](#tab/b2c)

Varat izveidot pasākumus atsevišķu klientu līmenī (klienta atribūts, klienta mērs) vai uzņēmuma/organizācijas līmenī (biznesa pasākums). Debitora atribūts un klienta mērs ir divi tipi, kas ļauj izsekot veiktspējai katram klientam. Piemēram, katra klienta kopējie tēriņi. Biznesa pasākumi ļauj izsekot katra uzņēmuma veiktspējai. Piemēram, uzņēmuma kopējie ieņēmumi.

- Debitora atribūts: ģenerē izvadi kā jaunu atribūtu, kas tiek saglabāts kā jauna kolonna sistēmas ģenerētajā entītijā ar nosaukumu *Customer_Measure*. Atsvaidzinot debitora atribūtu, visi pārējie debitora atribūti Customer_Measure *entītijā* atsvaidzinās vienlaicīgi. Turklāt klienta profila kartē tiek parādīti klienta atribūti. Pēc palaišanas vai saglabāšanas klienta atribūtu nevar mainīt uz klienta mēru.

- Debitora mērs: ģenerē izvadi kā savu entītiju, un pēc palaišanas vai saglabāšanas to nevar mainīt uz debitora atribūtu. Klienta mērījumi netiek rādīti klienta profila kartē.

- Biznesa pasākums: ģenerē izvadi kā savu entītiju un parāda Customer Insights vides sākumlapā.

1. Dodieties uz **Pasākumi**.

1. Atlasiet **Jauns** un izvēlieties **Izveidot savu**.

   :::image type="content" source="media/measure-b2c.png" alt-text="Tukšs konfigurācijas ekrāns B-to-C pasākumam." lightbox="media/measure-b2c.png":::

1. Lai izsekotu biznesa līmeņa veiktspēju, pārslēdziet **mērījumu tipu** uz **biznesa līmeni**. **Debitora līmenis** ir atlasīts pēc noklusējuma. **Debitora līmenis** automātiski pievieno *atribūtu CustomerId* dimensijām, bet **biznesa līmenis** to automātiski noņem.

1. Konfigurācijas apgabalā nolaižamajā izvēlnē Atlasīt funkciju **izvēlieties apkopošanas funkciju**. Apkopošanas funkcijas ir šādas:
   - **Sum**
   - **Vidējais**
   - **Skaits**
   - **Skaitīt unikālos vienumus**
   - **Maksimums**
   - **Minimums**
   - **Pirmā**: tiek ņemta pirmā datu ieraksta vērtība
   - **Pēdējā**: tiek ņemta pēdējā vērtība, kas tika pievienota datu ierakstam
   - **ArgMax**: atrod datu ierakstu, kas sniedz maksimālo vērtību no mērķa funkcijas
   - **ArgMin**: atrod datu ierakstu, kas norāda mērķa funkcijas minimālo vērtību

1. Atlasiet vienumu **Pievienot atribūtu**, lai atlasītu datus, kas nepieciešami šī mēra izveidei.

   1. Atlasiet cilni **Atribūti**.
   1. Datu entītija: izvēlieties entītiju, kurā iekļauts mēra atribūts, ko vēlaties aprēķināt.
   1. Datu atribūts: izvēlieties atribūtu, ko vēlaties izmantot apkopošanas funkcijai, lai aprēķinātu mēru. Vienlaikus vienā reizē var atlasīt tikai vienu atribūtu.
   1. Atlasiet arī esoša mēra datu atribūtu, atlasot **Mērījumi** cilni. Varat arī meklēt entītijas vai mēra nosaukumu.
   1. Atlasiet vienumu **Pievienot**, lai mēram pievienotu atlasīto atribūtu.

1. Lai izveidotu sarežģītākus mērījumus, to funkcijai var pievienot papildu atribūtus vai lietot matemātikas operatorus.

1. Lai pievienotu filtrus, konfigurācijas apgabalā atlasiet **Filtri**. Lietojot filtrus, mērījuma aprēķināšanai tiks izmantoti tikai filtriem atbilstošie ieraksti.
  
   1. Sadaļā **Pievienot atribūtu**, kas atrodas **Filtru** rūtī, atlasiet atribūtu, ko vēlaties izmantot, lai izveidotu filtru.
   1. Iestatiet filtra operatorus, lai definētu filtru katram atlasītajam atribūtam.
   1. Atlasiet vienumu **Lietot**, lai mērījumam pievienotu filtrus.

1. Atlasiet **Dimensija**, lai izvēlētos citus laukus, kas tiek pievienoti kā kolonnas mērījumu izvades entītijai.

   1. Atlasiet vienumu **Rediģēt dimensijas**, lai pievienotu datu atribūtus, pēc kuriem vēlaties grupēt mērus. Piemēram, pilsēta vai dzimums.
   > [!TIP]
   > Ja kā mērījumu tipu atlasījāt **Klienta līmeni**, **atribūts** CustomerId *jau ir* pievienots. Ja noņemat atribūtu, **mērījuma tips** pārslēdzas uz **biznesa līmeni**.
   1. Atlasiet vienumu **Pabeigts**, lai mērījumam pievienotu dimensijas.

1. Ja datos ir vērtības, kas jāaizstāj ar veselu skaitli, atlasiet **Kārtulas**. Konfigurējiet kārtulu un pārliecinieties, ka kā aizstājējus izvēlējāties tikai veselus skaitļus. Piemēram, aizstājiet *nulli* ar *0*.

1. Ja starp kartēto datu entītiju un *Klienta* entītiju ir vairāki ceļi, ir jāizvēlas viens no identificētajiem [entītiju attiecību ceļiem](relationships.md). Mērījumu rezultāti var atšķirties atkarībā no atlasītā ceļa.

   1. Atlasiet **Attiecību ceļu** un izvēlieties entītijas ceļu, kas jāizmanto pasākuma identificēšanai. Ja entītijai *Klients* ir tikai viens ceļš, šī vadīkla netiks rādīta.
   1. Atlasiet **Pabeigts**, lai lietotu jūsu atlasi.

1. Lai mērījumam pievienotu papildu aprēķinus, atlasiet **Jauns aprēķins**. Entītijas var izmantot tikai tajā pašā entītijas ceļā jauniem aprēķiniem. Papildu aprēķini tiek rādīti kā jaunas kolonnas mērījumu izvades entītijā.

1. Aprēķinā atlasiet **...**, lai **Dublētu**, **Pārdēvētu** vai **Noņemtu** aprēķinu no mērījuma.

1. **Priekšskatījuma** apgabalā redzēsit izvades entītijas mērījuma datu shēmu, tostarp filtrus un dimensijas. Priekšskatījums dinamiski reaģē uz konfigurācijas izmaiņām.

1. Blakus pasākumam Bez nosaukuma atlasiet **Rediģēt detaļas**. Norādiet pasākuma nosaukumu. Pēc izvēles pievienojiet [pasākumam atzīmes](work-with-tags-columns.md#manage-tags).

   :::image type="content" source="media/measures_edit_details.png" alt-text="Dialoglodziņš Detalizētas informācijas rediģēšana.":::

1. Atlasiet opciju **Izpildīt**, lai aprēķinātu konfigurētā mērījuma rezultātus. Atlasiet **Saglabāt un aizvērt**, ja vēlaties saglabāt pašreizējo konfigurāciju un izpildīt mērījumu vēlāk.

1. Dodieties uz **Mērījumi**, lai sarakstā redzētu jaunizveidoto mērījumu.

# <a name="business-accounts-b-to-b"></a>[Uzņēmumu konti (B2B)](#tab/b2b)

Varat izveidot pasākumus atsevišķu kontu līmenī (klienta mērs) vai visu kontu līmenī (biznesa pasākums).

- Debitora mērs: ģenerē izvadi kā savu entītiju. Klienta mērījumi netiek rādīti klienta profila kartē.

- Biznesa pasākums: ģenerē izvadi kā savu entītiju un parāda Customer Insights vides sākumlapā.

1. Dodieties uz **Pasākumi**.

1. Atlasiet **Jauns**.

   :::image type="content" source="media/measure-b2b.png" alt-text="Tukšs konfigurācijas ekrāns B-to-B pasākumam.":::

1. Konfigurācijas apgabalā nolaižamajā izvēlnē Atlasīt funkciju **izvēlieties apkopošanas funkciju**. Apkopošanas funkcijas ir šādas:
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

1. Lai pievienotu filtrus, konfigurācijas apgabalā atlasiet **Filtri**. Lietojot filtrus, mērījuma aprēķināšanai tiks izmantoti tikai filtriem atbilstošie ieraksti.
  
   1. Sadaļā **Pievienot atribūtu**, kas atrodas **Filtru** rūtī, atlasiet atribūtu, ko vēlaties izmantot, lai izveidotu filtru.
   1. Iestatiet filtra operatorus, lai definētu filtru katram atlasītajam atribūtam.
   1. Atlasiet vienumu **Lietot**, lai mērījumam pievienotu filtrus.

1. Atlasiet **Dimensija**, lai izvēlētos citus laukus, kas tiek pievienoti kā kolonnas mērījumu izvades entītijai.

   1. Atlasiet vienumu **Rediģēt dimensijas**, lai pievienotu datu atribūtus, pēc kuriem vēlaties grupēt mērus. Piemēram, pilsēta vai dzimums.
      > [!TIP]
      > Ja kā mērījumu tipu atlasījāt **Klienta līmeni**, **atribūts** CustomerId *jau ir* pievienots. Ja noņemat atribūtu, **pasākuma tips** pārslēdzas uz **biznesa līmeni**.
   1. Atlasiet vienumu **Pabeigts**, lai mērījumam pievienotu dimensijas.

1. Ja datos ir vērtības, kas jāaizstāj ar veselu skaitli, atlasiet **Kārtulas**. Konfigurējiet kārtulu un pārliecinieties, ka kā aizstājējus izvēlējāties tikai veselus skaitļus. Piemēram, aizstājiet *nulli* ar *0*.

1. Jūs varat izmantot slēdzi **Apkopot pakārtotos uzņēmumus**, ja [izmantojat uzņēmumus ar hierarhijām](relationships.md#set-up-account-hierarchies).
   - Ja iestatījums ir **Izslēgts**, mērījums tiek aprēķināts katram kontam. Katrs konts tiek iegūts no rezultātiem.
   - Ja iestatījums ir **Ieslēgts**, atlasiet **Rediģēt**, lai izvēlētos uzņēmumu hierarhiju atbilstoši noingestajām hierarhijām. Šis pasākums dos tikai vienu rezultātu, jo tas tiek apkopots ar apakškontiem.

1. Ja starp kartēto datu entītiju un *Klienta* entītiju ir vairāki ceļi, ir jāizvēlas viens no identificētajiem [entītiju attiecību ceļiem](relationships.md). Mērījumu rezultāti var atšķirties atkarībā no atlasītā ceļa.

   1. Atlasiet **Attiecību ceļu** un izvēlieties entītijas ceļu, kas jāizmanto pasākuma identificēšanai. Ja entītijai *Klients* ir tikai viens ceļš, šī vadīkla netiks rādīta.
   1. Atlasiet **Pabeigts**, lai lietotu jūsu atlasi.

1. Aprēķinā atlasiet **...**, lai **Dublētu**, **Pārdēvētu** vai **Noņemtu** aprēķinu no mērījuma.

1. **Priekšskatījuma** apgabalā redzēsit izvades entītijas mērījuma datu shēmu, tostarp filtrus un dimensijas. Priekšskatījums dinamiski reaģē uz konfigurācijas izmaiņām.

1. Blakus pasākumam Bez nosaukuma atlasiet **Rediģēt detaļas**. Norādiet pasākuma nosaukumu. Pēc izvēles pievienojiet [pasākumam atzīmes](work-with-tags-columns.md#manage-tags).

   :::image type="content" source="media/measures_edit_details.png" alt-text="Dialoglodziņš Detalizētas informācijas rediģēšana.":::

1. Atlasiet opciju **Izpildīt**, lai aprēķinātu konfigurētā mērījuma rezultātus. Atlasiet **Saglabāt un aizvērt**, ja vēlaties saglabāt pašreizējo konfigurāciju un izpildīt mērījumu vēlāk.

1. Dodieties uz **Mērījumi**, lai sarakstā redzētu jaunizveidoto mērījumu.
