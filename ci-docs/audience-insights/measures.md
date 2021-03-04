---
title: Pasākumu izveide un pārvaldība
description: Definējiet pasākumus, lai analizētu un atspoguļotu sava uzņēmuma veiktspēju.
ms.date: 02/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: wameng
manager: shellyha
ms.openlocfilehash: 5bcee3b4c51880740715575b18fd7a4dbf87e6d0
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269937"
---
# <a name="define-and-manage-measures"></a>Definējiet un pārvaldiet mērus

Pasākumi palīdz labāk izprast klientu uzvedību un biznesa veiktspēju, izgūstot atbilstošas vērtības no [vienotajiem profiliem](data-unification.md). Piemēram, uzņēmumam jāizprot *katra klienta kopējie tēriņi*, lai izprastu atsevišķa klienta pirkumu vēsturi. Vai izmērīt *uzņēmuma kopējos pārdošanas apjomus*, lai izprastu kopējā līmeņa ieņēmumus visā biznesā.  

Pasākumi tiek izveidoti, izmantojot pasākumu veidotāju, datu vaicājumu platformu ar dažādiem operatoriem un vienkāršām kartēšanas opcijām. Tas ļauj filtrēt datus, grupēt rezultātus, noteikt [entītiju attiecību ceļus](relationships.md) un priekšskatīt izvadi.

Izmantojiet pasākumu veidotāju, kas tiek plānots biznesa aktivitātēm, vaicājot klientu datus un izvelkot ieskatus. Piemēram, *katra klienta kopējo tēriņu* un *katra klienta kopējo ienākumu* pasākumu izveide palīdz identificēt klientu grupu, kuriem ir augsti tēriņi, bet augsti ieņēmumi. Varat [izveidot segmentu](segments.md), lai vadītu nākamās, vislabāk piemērotās darbības. 

## <a name="create-a-measure"></a>Mēra izveide

Šajā sadaļā ir skatīts, kā izveidot jaunu pasākumu no nulles. Varat izveidot pasākumu ar datu atribūtiem no datu entītijām, kurām ir iestatītas attiecības, lai izveidotu savienojumu ar Klienta entītiju. 

1. Sadaļā Auditorijas ieskati ejiet uz **Mēri**.

1. Atlasiet **Jauns**.

1. Atlasiet **Rediģēt nosaukumu** un norādiet pasākumam **Nosaukumu**. 
   > [!NOTE]
   > Ja jaunajā pasākumu konfigurācijā ir tikai divi lauki, piemēram, paplašināmā lauka CustomerID un viens aprēķins, izvade sistēmas ģenerētajā entītijā tiks pievienota kā jauna kolonna ar nosaukumu Customer_Measure. Un pasākuma vērtību varat redzēt vienotā klienta profilā. Citi pasākumi radīs savas entītijas.

1. Konfigurācijas apgabalā izvēlieties apkopošanas funkciju nolaižamajā izvēlnē **Atlasīt funkciju**. Apkopošanas funkcijas ir šādas: 
   - **Sum**
   - **Vidējais**
   - **Skaits**
   - **Skaitīt unikālos vienumus**
   - **Maksimums**
   - **Minimums**
   - **Pirmā**: tiek ņemta pirmā datu ieraksta vērtība
   - **Pēdējā**: tiek ņemta pēdējā vērtība, kas tika pievienota datu ierakstam

   :::image type="content" source="media/measure-operators.png" alt-text="Operatorus pasākumu aprēķiniem.":::

1. Atlasiet vienumu **Pievienot atribūtu**, lai atlasītu datus, kas nepieciešami šī pasākuma izveidei.
   
   1. Atlasiet cilni **Atribūti**. 
   1. Datu entītija: izvēlieties entītiju, kurā iekļauts mērvienības atribūts, ko vēlaties aprēķināt. 
   1. Datu atribūts: izvēlieties atribūtu, ko vēlaties izmantot apkopošanas funkcijai, lai aprēķinātu pasākumu. Vienlaikus vienā reizē var atlasīt tikai vienu atribūtu.
   1. Atlasiet arī esoša pasākuma datu atribūtu, atlasot **Pasākumi** cilni. Varat arī meklēt entītijas vai pasākuma nosaukumu. 
   1. Atlasiet vienumu **Pievienot**, lai pasākumam pievienotu atlasīto atribūtu.

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Atlasiet atribūtu, ko izmantot aprēķinos.":::

1. Lai izveidotu sarežģītākus pasākumus, pasākumu funkcijai var pievienot papildu atribūtus vai lietot matemātikas operatorus.

   :::image type="content" source="media/measure-math-operators.png" alt-text="Izveidot sarežģītu pasākumu, izmantojot matemātikas operatorus.":::

1. Lai pievienotu filtrus, konfigurācijas apgabalā atlasiet **Filtri**. 
  
   1. Rūts **Filtri** sadaļā **Pievienot atribūtu** atlasiet atribūtu, ko vēlaties izmantot, lai izveidotu filtrus.
   1. Iestatiet filtra operatorus, lai definētu filtru katram atlasītajam atribūtam.
   1. Atlasiet vienumu **Lietot**, lai pasākumam pievienotu filtrus.

1. Lai pievienotu dimensijas, konfigurācijas apgabalā atlasiet **Dimensija**. Dimensijas tiek rādītas kā kolonnas pasākumu izvades entītijā.
   1. Atlasiet vienumu **Rediģēt dimensijas**, lai pievienotu datu atribūtus, pēc kuriem vēlaties grupēt pasākumus. Piemēram, pilsēta vai dzimums. Pēc noklusējuma *CustomerID* dimensija tiek atlasīta, lai izveidotu *klienta līmeņa pasākumus*. Ja vēlaties izveidot *uzņēmuma līmeņa pasākumus*, varat noņemt noklusējuma dimensiju.
   1. Atlasiet vienumu **Pabeigts**, lai pasākumam pievienotu dimensijas.

1. Ja starp kartēto datu entītiju un Klienta entītiju ir vairāki ceļi, ir jāizvēlas viens no identificētajiem [entītiju attiecību ceļiem](relationships.md). Pasākumu rezultāti var atšķirties atkarībā no atlasītā ceļa.
   1. Atlasiet **Datu preferences** un izvēlieties entītijas ceļu, kas jāizmanto pasākuma identificēšanai.
   1. Atlasiet **Pabeigts**, lai lietotu jūsu atlasi. 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Atlasiet entītijas ceļu pasākumam.":::

1. Lai pasākumam pievienotu papildu aprēķinus, atlasiet **Jauns aprēķins**. Entītijas var izmantot tikai tajā pašā entītijas ceļā jauniem aprēķiniem. Papildu aprēķini tiek rādīti kā jaunas kolonnas pasākumu izvades entītijā.

1. Aprēķinā atlasiet **...**, lai **Dublētu**, **Pārsauktu** vai **Noņemtu** aprēķinu no pasākuma.

1. **Priekšskatījuma** apgabalā redzēsit izvades entītijas pasākumu datu shēmu, tostarp filtrus un dimensijas. Priekšskatījums dinamiski reaģē uz konfigurācijas izmaiņām.

1. Atlasiet opciju **Izpildīt**, lai aprēķinātu konfigurētā pasākuma rezultātus. Atlasiet **Saglabāt un aizvērt**, ja vēlaties saglabāt pašreizējo konfigurāciju un izpildīt pasākumu vēlāk.

1. Dodieties uz **Pasākumi**, lai sarakstā redzētu jaunizveidoto pasākumu.

## <a name="manage-your-measures"></a>Pārvaldiet savus mērus

Kad esat [izveidojis pasākumu](#create-a-measure), lapā **Mēri** tiks atainots pasākumu saraksts.

Atradīsiet informāciju par pasākuma tipu, izveidotāju, izveides datumu, statusu un stāvokli. Kad sarakstā atlasāt kādu pasākumu, varat priekšskatīt izvadi un lejupielādēt .CSV failu.

Lai vienlaikus atsvaidzinātu visus mērus, atlasiet **Atsvaidzināt visu**, neatlasot noteiktu mēru.

> [!div class="mx-imgBorder"]
> ![Darbības, lai pārvaldītu atsevišķus mērus](media/measure-actions.png "Darbības, lai pārvaldītu atsevišķus mērus")

Sarakstā atlasiet pasākumu, lai izvēlētos kādu no šīm opcijām:

- Atlasiet mēra nosaukumu, lai skatītu tā detalizētu informāciju.
- **Rediģējiet** mēra konfigurāciju.
- **Atsvaidzināt** pasākumu, pamatojoties uz jaunākajiem datiem.
- **Pārdēvējiet** mēru. 
- **Dzēsiet** mēru.
- **Aktivizēt** vai **Deaktivizēt**. neaktīvie pasākumi netiks netiks atsvaidzināti [plānotās atsvaidzināšanas laikā](system.md#schedule-tab).

> [!TIP]
> Uzdevumiem/procesiem ir [seši statusu tipi](system.md#status-types). Turklāt vairums procesu [ir atkarīgi no citiem pakārtotiem procesiem](system.md#refresh-policies). Varat atlasīt procesa statusu, lai skatītu detalizētu informāciju par visa uzdevuma norisi. Pēc tam, kad vienam no darba uzdevumiem esat atlasījis **Skatīt detalizētu informāciju**, jūs redzēsit papildinformāciju: apstrādes laiku, pēdējās apstrādes datumu un visas ar uzdevumu saistītas kļūdas un brīdinājumus.

## <a name="next-step"></a>Nākamā darbība

Jūs varat izmantot esošus pasākumus, lai izveidotu [klientu segmentu](segments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]