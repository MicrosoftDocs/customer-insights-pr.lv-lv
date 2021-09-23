---
title: Piltuves atskaites
description: Kā izmantot piltuves atskaites, lai saprastu, kā auditorija pieņem lēmumus.
ms.reviewer: mhart
ms.author: kamacdon
author: kamacdon
ms.date: 09/17/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 901e7ec50037d66c7c5ceb635d1c6cda6cfff83b
ms.sourcegitcommit: 3bafa27adae113948636b30c7462e0af060c7131
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 09/17/2021
ms.locfileid: "7498651"
---
# <a name="create-and-manage-funnel-reports"></a>Piltuves atskaišu izveide un pārvaldība

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Piltuves atskaitē tiek apkopota informācija par darbībām, kas tiek veiktas automatizētas kampaņas laikā jūsu tīmekļa vietnē vai mobilajā programmā. Tas palīdz saprast auditorijas progresu procesa gaitā un identificēt nolaižamos punktus. Piemēram, varat izmantot piltuves atskaiti, lai identificētu ceļus un skārienekrānus, ko klienti izmanto pirms iegādes. Piltuves ziņojums sniedz datus, lai informētu par lēmumiem un noteiktu optimizēšanas un procesa uzlabošanas jomas.

## <a name="create-a-funnel-report"></a>Piltuves atskaites izveide

Lai izveidotu piltuves atskaiti, norādiet iekļaujamos soļus un darbību katram solim. Darbība ir [notikums](glossary.md), kas norāda lietotāja uzvedību. Piltuves atskaitē tiek parādīts to lietotāju skaits, kas ir veikuši katru noteikto soli. 

1. Dodieties uz **Piltuves** un atlasiet **+Jauna piltuve**, lai sāktu piltuves atskaiti.

1. Sadaļā **Piltuves rediģētājs** zem **Soļi** atlasiet **+Pievienot soli.** 

1. Ievadiet nosaukumu vienumā **Soļa nosaukums**.

   :::image type="content" source="media/new-funnel-report.png" alt-text="Jaunas piltuves atskaite.":::

1. Atlasiet **Darbību**. Darbība ieraksta, kad lietotājs skata lapu (**Skata** darbība) vai mijiedarbojas ar saturu (**Rīcības** darbība).

1. Izmantojiet **Soļu kritērijus**, lai norādītu darbības dimensiju. [Dimensijas](dimensions.md) ir atribūti, kas var raksturot, filtrēt vai grupēt datus.

1. Ja vēlaties, varat konfigurēt vairāku nosacījumu piltuves darbības. Atlasiet vienumu **Pievienot nosacījumu**, lai darbībā norādītu papildu nosacījumus. Papildu kritērijiem ir jāizmanto vienāds darbības tips. Varat izvēlēties, vai ar operatoru AND vai OR ir saistīti vairāki nosacījumi.

   :::image type="content" source="media/funnel-add-condition.png" alt-text="Piltuves redaktors, kurā redzama soļu konfigurācija, izmantojot vairāku nosacījumu darbības.":::

1. Atlasiet vienumu **Pievienot soli**, līdz izpildīsit visus atskaitē veicamos soļus.

1. Atlasiet **Saglabāt**, norādiet atskaites nosaukumu un vēlreiz nospiediet **Saglabāt**. 

### <a name="example-fourth-coffee-company-funnel-report"></a>Piemērs: Fourth Coffee uzņēmuma piltuves atskaite

Tālāk sniegtajā scenārijā tiek parādīts viens piltuves atskaites izmantošanas veids. Uzņēmuma Fourth Coffee analītiķe vēlas saprast nesen veiktās akcijas ietekmi uz abonēšanas tarifiem. Analītiķe veido piltuves atskaiti, lai identificētu klientu darbību. Atskaite tiek sākta brīdī, kad klients ieiet uzņēmuma mājaslapā līdz abonēšanas akcijas koda izmantošanai. Analītiķe izveido piltuves atskaiti, izpildot šādas darbības:

1. darbība. Klienti, kas ienāk sākumlapā   
2. darbība. Klienti, kas veic pirkumu   
3. darbība. Klienti, kas izmanto akcijas kodu, lai saņemtu atlaidi abonementam   
4. darbība. Pierakstīšanās abonementam   

:::image type="content" source="media/funnel-report-example.png" alt-text="piltuves atskaites piemērs.":::
  
Šī piltuve ļauj redzēt to lietotāju skaitu, kuri izmantoja akcijas kodu pēc vienreizējas iegādes, lai pieteiktos abonēšanas programmai.

### <a name="configure-advanced-settings"></a>Konfigurēt papildu iestatījumus 

Piltuves atskaites ļauj definēt laika ierobežojumu, kas nepieciešams piltuves pabeigšanai. Piemēram, varat iestatīt laiku, kad pabeigt piltuvi līdz četrām dienām. Šajā iestatījumā tiks skaitīti tikai sekmīgie abonementa pierakstīšanās gadījumi, kas notikuši četru dienu laikā pēc tam, kad lietotājs būs apmeklējis sākumlapu.

1. Dodieties uz **Piltuves**, lai atvērtu **Piltuves bibliotēku**.

1. Atlasiet nosaukumu, lai atvērtu atskaiti. 

1. **Piltuves redaktora** rūtī atlasiet **Papildu iestatījumi**. 

1. Iestatiet Ierobežot piltuves pabeigšanas laiku uz **Ieslēgts**.

   :::image type="content" source="media/funnel-limit-time.png" alt-text="Piltuves redaktors, kurā tiek rādīts papildu iestatījums un opcijas, lai ierobežotu laiku piltuves pabeigšanai.":::

1. Nolaižamajā sarakstā **Iestatīt ierobežojumu** izvēlieties laiku, kad piltuve ir jāaizpilda.

1. Lai veiktās izmaiņas stātos spēkā, atlasiet **Saglabāt**.


## <a name="cross-channel-funnel-reports"></a>Starpkanālu piltuves atskaites 

Iesaistes ieskati var apkopot arī uzvedības klientu datus jūsu mobilajā programmā. Kad mobilā programma ir pielāgota, izmantojot iesaistes ieskatus [Android SDK](get-started-android.md) vai [iOS SDK](get-started-ios.md), varat izveidot starpkanālu piltuves atskaites. 

### <a name="create-a-cross-channel-funnel-report"></a>Starpkanālu piltuves atskaites izveidošana 

1. Izpildiet tālāk norādītās darbības, lai [izveidotu piltuves atskaiti](#create-a-funnel-report).    

1. Lai izsekotu, kā jūsu klienti mijiedarbojas ar jūsu zīmolu gan jūsu tīmekļa vietnē, gan mobilajā lietotnē vai vairākās tīmekļa vietnēs, izmantojiet darbvietas pārslēdzēju, lai izveidotu piltuves darbības ar datiem no citām darbvietām. Cilnes **Piltuves redaktors** sadaļā **Darbības** atlasiet, no kuras darbvietas ir jāiegūst piltuves darbības dati.

## <a name="manage-funnel-reports"></a>Pārvaldīt piltuves atskaites

Varat pārskatīt piltuves atskaites, lai analizētu datus, izsekotu veiktspēju un apkopotu ieskatus.

> [!NOTE]
> - Iesaistes ieskatu piltuves atskaites pašlaik atbalsta scenārijus, kuros visi piltuves lietotāji ir anonīmi vai visi lietotāji tiek autentificēti. 
> - Piltuves pārskatu vēsturiskie dati ir pieejami par pēdējām 30 dienām.

### <a name="view-funnel-reports"></a>Skatīt piltuves atskaites

1. Dodieties uz **Piltuves**, lai atvērtu **Piltuves bibliotēku**.
1. Atlasiet nosaukumu, lai atvērtu atskaiti.    

### <a name="see-the-data-collected-for-a-report"></a>Skatīt atskaites vākšanas datus   

Lai skatītu informāciju par sākuma laiku

- Norādiet uz darbību atskaitē.

:::image type="content" source="media/funnel-step-data.png" alt-text="piltuves dati.":::

### <a name="change-the-date-range-for-the-funnel-report"></a>Mainīt piltuves atskaites datumu diapazonu

1. Dodieties uz **Piltuves**, lai atvērtu **Piltuves bibliotēku**.

1. Atlasiet nosaukumu, lai atvērtu atskaiti.

1. Atveriet **laika diapazonu** un sarakstā atlasiet jaunu laika periodu vai **Fiksētu datumu diapazonu**, lai norādītu datumu diapazonu.

## <a name="edit-or-delete-funnel-reports"></a>Rediģēt vai dzēst piltuves atskaites

Varat mainīt piltuves atskaites nosaukumu, dzēst to vai modificēt atskaitē norādītās darbības.

### <a name="rename-or-delete-a-funnel-report"></a>Pārdēvēt vai dzēst piltuves atskaiti

1. Dodieties uz **Piltuves**, lai atvērtu **Piltuves bibliotēku**. 

1. Atlasiet vienumu **Vairāk** blakus atskaitei, ko vēlaties mainīt, un izvēlaties **Rediģēt nosaukumu** vai **Dzēst**.

### <a name="edit-a-funnel-step"></a>Rediģēt piltuves darbību  

1. Dodieties uz **Piltuves**, lai atvērtu **Piltuves bibliotēku**. 

1. Atlasiet nosaukumu, lai atvērtu atskaiti.

1. Atlasīt rediģējamo darbību.

1. Atlasiet **Rediģēt**.

1. Sadaļā **Piltuves rediģētājs** atjauniniet informāciju, ko vēlaties mainīt.  

1. Atlasiet vienumu **Saglabāt**.

### <a name="reorder-a-funnel-step"></a>Pārkārtot piltuves darbību

1. Dodieties uz **Piltuves**, lai atvērtu **Piltuves bibliotēku**. 

1. Atlasiet nosaukumu, lai atvērtu atskaiti.

1. Atlasīt pārkārtojamo darbību.

1. Atlasiet **Pārvietot** un pēc tam **Uz augšu**, **uz leju**, **Uz sākumu** vai **Uz beigām**, lai pārvietotu darbību.

### <a name="delete-a-funnel-step"></a>Dzēst piltuves darbību

1. Dodieties uz **Piltuves**, lai atvērtu **Piltuves bibliotēku**. 

1. Atlasiet nosaukumu, lai atvērtu atskaiti.

1. Atlasiet darbību, kuru noņemt, un atlasiet **Dzēst**.

## <a name="funnel-insights"></a>Piltuves ieskati 

Iesaistes ieskati tagad piedāvā piltuves ieskatus klientiem. Izmantojiet piltuves ieskatus, lai gūtu dziļāku ieskatu par klientu uzvedību attiecībā uz piltuves atskaites darbībām. Izveidojot un saglabājot jaunu piltuves atskaiti, atskaitei tiek automātiski ģenerēti piltuves ieskati. 

Piltuves ieskatus no šīm kategorijām var skatīt gan galvenajā, gan darbību līmenī: 

 - Konvertēšanas koeficients 
 - Pārejas laiks 
 - Pabeigšanas laiks 

Izmantojiet šos ieskatus, lai dziļāk izpētītu klientu uzvedību un labāk izprastu piltuves atskaites nolaižamos punktus un pārvēršanus. 

Piltuves ieskati tiek pārrēķināti ik pēc 24 stundām vai kad **Saglabājat** piltuves atskaiti. 

> [!NOTE]
> Lai skatītu piltuves ieskatus, atskaite ir jāsaglabā ikreiz, kad veicat izmaiņas. 

