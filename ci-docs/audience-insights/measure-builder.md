---
title: Izveidot jaunus pasākumus, izmantojot mērvienību veidotāju
description: Veidojiet pasākumus no nulles, lai analizētu galvenos rādītājus par savu uzņēmumu.
ms.date: 02/28/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-measure-builder
- customerInsights
ms.openlocfilehash: 5329aea240ba40ec8698b3ddeb67fb5f21c62bbd
ms.sourcegitcommit: cf6a0ed44915908a44c70889a2dd199a9d0d4798
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 02/28/2022
ms.locfileid: "8359956"
---
# <a name="use-measure-builder-to-create-measures-from-scratch"></a>Izmantojiet mērvienību veidotāju, lai izveidotu pasākumus no nulles

Šajā rakstā ir paskaidrots, kā izveidot jaunu [pasākumu](measures.md) no nulles. Mērvienību veidotājs ļauj definēt aprēķinus, izmantojot matemātikas operatorus, apkopošanas funkcijas un filtrus. Varat izveidot mēru ar atribūtiem no entītijām, kas saistītas ar vienoto *debitora* entītiju. 

Pasākumu izveide B-to-C un B-to-B vidē darbojas tāpat. Tomēr, ja B-to-B vide [izmanto kontus ar hierarhijām](relationships.md#set-up-account-hierarchies), varat izvēlēties apkopot pasākumu saistītos apakškontos.

Varat arī ātri izveidot pasākumu, izvēloties no bieži izmantotu un iepriekš definētu pasākumu kopas. Papildinformāciju skatiet rakstā [Veidnes izmantošana pasākuma izveidei](measure-templates.md).

# <a name="individual-consumers-b-to-c"></a>[Atsevišķi patērētāji (B2C)](#tab/b2c)

Varat izveidot pasākumus atsevišķu klientu līmenī (klienta atribūts, klienta mērs) vai uzņēmuma/organizācijas līmenī (biznesa pasākums). Klienta atribūts un klienta mērs ir divi tipi, kas ļauj izsekot veiktspēju katram klientam. Piemēram, katra klienta kopējie tēriņi. Biznesa pasākumi ļauj izsekot katra uzņēmuma veiktspējai. Piemēram, uzņēmuma kopējie ieņēmumi.

- Debitora atribūts: Ģenerē izvadi kā jaunu atribūtu, kas tiek saglabāts kā jauna kolonna sistēmas ģenerētajā entītijā ar nosaukumu *Customer_Measure*. Atsvaidzinot debitora atribūtu, visi pārējie Customer_Measure *entītijas klienta atribūti* tiek atsvaidzināti vienlaicīgi. Turklāt klienta profila kartē tiek parādīti klienta atribūti. Pēc palaišanas vai saglabāšanas klienta atribūtu nevar mainīt uz klienta mēru.

- Debitora mērs: ģenerē izstrādi kā savu entītiju, un pēc palaišanas vai saglabāšanas to nevar mainīt uz debitora atribūtu. Klienta pasākumi netiek rādīti klienta profila kartē.

- Biznesa mērs: ģenerē izvadi kā savu entītiju un tiek rādīts customer insights vides sākumlapā.

1. Dodieties uz **Pasākumi**.

1. Atlasiet **Jauns** un izvēlieties **Izveidot savu**.

   :::image type="content" source="media/measure-b2c.png" alt-text="Tukšs konfigurācijas ekrāns B-to-C mērījumam.":::

1. Atlasiet **Rediģēt nosaukumu** un norādiet mēra **Nosaukumu**. 

1. Konfigurācijas apgabalā nolaižamajā izvēlnē Atlasīt **izvēlieties apkopošanas** funkciju. Apkopošanas funkcijas ir šādas: 
   - **Sum**
   - **Vidējais**
   - **Skaits**
   - **Skaitīt unikālos vienumus**
   - **Maksimums**
   - **Minimums**
   - **Pirmā**: tiek ņemta pirmā datu ieraksta vērtība
   - **Pēdējā**: tiek ņemta pēdējā vērtība, kas tika pievienota datu ierakstam
   - **ArgMax**: atrod datu ierakstu, kas dod maksimālo vērtību no mērķa funkcijas
   - **ArgMin**: atrod datu ierakstu, kas dod minimālo vērtību no mērķa funkcijas

1. Atlasiet vienumu **Pievienot atribūtu**, lai atlasītu datus, kas nepieciešami šī mēra izveidei.
   
   1. Atlasiet cilni **Atribūti**. 
   1. Datu entītija: izvēlieties entītiju, kurā iekļauts mēra atribūts, ko vēlaties aprēķināt. 
   1. Datu atribūts: izvēlieties atribūtu, ko vēlaties izmantot apkopošanas funkcijai, lai aprēķinātu mēru. Vienlaikus vienā reizē var atlasīt tikai vienu atribūtu.
   1. Atlasiet arī esoša mēra datu atribūtu, atlasot **Mērījumi** cilni. Varat arī meklēt entītijas vai mēra nosaukumu. 
   1. Atlasiet vienumu **Pievienot**, lai mēram pievienotu atlasīto atribūtu.

1. Lai izveidotu sarežģītākus mērījumus, to funkcijai var pievienot papildu atribūtus vai lietot matemātikas operatorus.

1. Lai pievienotu filtrus, konfigurācijas apgabalā atlasiet **Filtri**. Lietojot filtrus, mērījuma aprēķināšanai izmantos tikai tos ierakstus, kas atbilst filtriem.
  
   1. Sadaļā **Pievienot atribūtu**, kas atrodas **Filtru** rūtī, atlasiet atribūtu, ko vēlaties izmantot, lai izveidotu filtru.
   1. Iestatiet filtra operatorus, lai definētu filtru katram atlasītajam atribūtam.
   1. Atlasiet vienumu **Lietot**, lai mērījumam pievienotu filtrus.

1. Atlasiet **Dimensija**, lai izvēlētos vairāk lauku, kas tiek pievienoti kā kolonnas mērījumu izvades entītijai.
 
   1. Atlasiet vienumu **Rediģēt dimensijas**, lai pievienotu datu atribūtus, pēc kuriem vēlaties grupēt mērus. Piemēram, pilsēta vai dzimums. Pēc noklusējuma *CustomerID* dimensija tiek atlasīta, lai izveidotu *klienta līmeņa mērījumus*. Ja vēlaties izveidot *uzņēmuma līmeņa mērījumus*, varat noņemt noklusējuma dimensiju.
   1. Atlasiet vienumu **Pabeigts**, lai mērījumam pievienotu dimensijas.

1. Ja datos ir vērtības, kas jāaizstāj ar veselu skaitli, atlasiet **Kārtulas**. Konfigurējiet kārtulu un pārliecinieties, ka kā aizstājējus izvēlējāties tikai veselus skaitļus. Piemēram, aizstājiet *nulli* ar *0*.

1. Ja starp kartēto datu entītiju un *Klienta* entītiju ir vairāki ceļi, ir jāizvēlas viens no identificētajiem [entītiju attiecību ceļiem](relationships.md). Mērījumu rezultāti var atšķirties atkarībā no atlasītā ceļa. 
   
   1. Atlasiet **Attiecību ceļu** un izvēlieties entītijas ceļu, kas jāizmanto pasākuma identificēšanai. Ja entītijai *Klients* ir tikai viens ceļš, šī vadīkla netiks rādīta.
   1. Atlasiet **Pabeigts**, lai lietotu jūsu atlasi. 

1. Lai mērījumam pievienotu papildu aprēķinus, atlasiet **Jauns aprēķins**. Entītijas var izmantot tikai tajā pašā entītijas ceļā jauniem aprēķiniem. Papildu aprēķini tiek rādīti kā jaunas kolonnas mērījumu izvades entītijā.

1. Aprēķinā atlasiet **...**, lai **Dublētu**, **Pārdēvētu** vai **Noņemtu** aprēķinu no mērījuma.

1. **Priekšskatījuma** apgabalā redzēsit izvades entītijas mērījuma datu shēmu, tostarp filtrus un dimensijas. Priekšskatījums dinamiski reaģē uz konfigurācijas izmaiņām.

1. Atlasiet opciju **Izpildīt**, lai aprēķinātu konfigurētā mērījuma rezultātus. Atlasiet **Saglabāt un aizvērt**, ja vēlaties saglabāt pašreizējo konfigurāciju un izpildīt mērījumu vēlāk.

1. Dodieties uz **Mērījumi**, lai sarakstā redzētu jaunizveidoto mērījumu.

# <a name="business-accounts-b-to-b"></a>[Uzņēmumu konti (B2B)](#tab/b2b)


Varat izveidot pasākumus atsevišķu kontu līmenī (debitora mērs) vai visu kontu līmenī (biznesa pasākums). 

- Debitora mērs: ģenerē izstrādi kā savu entītiju. Klienta pasākumi netiek rādīti klienta profila kartē.

- Biznesa mērs: ģenerē izvadi kā savu entītiju un tiek rādīts customer insights vides sākumlapā.

1. Dodieties uz **Pasākumi**.

1. Atlasiet **Jauns**.

   :::image type="content" source="media/measure-b2b.png" alt-text="Tukšs konfigurācijas ekrāns B-to-B mēram.":::

1. Atlasiet **Rediģēt nosaukumu** un norādiet mēra **Nosaukumu**. 

1. Konfigurācijas apgabalā nolaižamajā izvēlnē Atlasīt **izvēlieties apkopošanas** funkciju. Apkopošanas funkcijas ir šādas: 
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

1. Lai pievienotu filtrus, konfigurācijas apgabalā atlasiet **Filtri**. Lietojot filtrus, mērījuma aprēķināšanai izmantos tikai tos ierakstus, kas atbilst filtriem.
  
   1. Sadaļā **Pievienot atribūtu**, kas atrodas **Filtru** rūtī, atlasiet atribūtu, ko vēlaties izmantot, lai izveidotu filtru.
   1. Iestatiet filtra operatorus, lai definētu filtru katram atlasītajam atribūtam.
   1. Atlasiet vienumu **Lietot**, lai mērījumam pievienotu filtrus.

1. Atlasiet **Dimensija**, lai izvēlētos vairāk lauku, kas tiek pievienoti kā kolonnas mērījumu izvades entītijai.
 
   1. Atlasiet vienumu **Rediģēt dimensijas**, lai pievienotu datu atribūtus, pēc kuriem vēlaties grupēt mērus. Piemēram, pilsēta vai dzimums. Pēc noklusējuma *CustomerID* dimensija tiek atlasīta, lai izveidotu *klienta līmeņa mērījumus*. Ja vēlaties izveidot *uzņēmuma līmeņa mērījumus*, varat noņemt noklusējuma dimensiju.
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

1. Atlasiet opciju **Izpildīt**, lai aprēķinātu konfigurētā mērījuma rezultātus. Atlasiet **Saglabāt un aizvērt**, ja vēlaties saglabāt pašreizējo konfigurāciju un izpildīt mērījumu vēlāk.

1. Dodieties uz **Mērījumi**, lai sarakstā redzētu jaunizveidoto mērījumu.

---