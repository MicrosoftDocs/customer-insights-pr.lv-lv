---
title: Datu eksportēšana no Customer Insights
description: Pārvaldiet eksportēšanu, lai kopīgotu datus.
ms.date: 11/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: overview
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 05485fc7def3d699d5179bcaa005ceb57024f840
ms.sourcegitcommit: bb1ca84bc38e81fb2ff2961c457384b7beb5b5fa
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 01/15/2022
ms.locfileid: "7977976"
---
# <a name="exports-preview-overview"></a>Eksportēšanas (priekšskatījuma) pārskats

Lapā **Eksportēšana** tiek rādītas visas konfigurētās eksportēšanas. Eksportēšana kopīgo konkrētus datus ar dažādām lietojumprogrammām. Tajos var būt iekļauti klientu profili, entītijas, shēmas un detalizēta kartēšana. Katrai eksportēšanai ir nepieciešams [administratora iestatīts savienojums, lai pārvaldītu autentifikāciju un piekļuvi](connections.md).

Dodieties uz lapu **Dati** > **Eksportēšana**, lai skatītu eksportēšanas lapu. Visas lietotāju lomas var skatīt konfigurētās eksportēšanas. Izmantojiet komandjoslā esošo meklēšanas lauku, lai atrastu eksportēšanas pēc to nosaukuma, savienojuma nosaukuma vai savienojuma tipa.

## <a name="export-types"></a>Eksporta veidi

Ir divi galvenie eksporta veidi:  

- Izmantojot **Datu eksportēšanu**, varat eksportēt jebkāda veida entītijas, kas ir pieejamas auditorijas ieskatos. Eksportēšanai atlasītās entītijas tiek eksportētas, izmantojot visus datu laukus, metadatus, shēmas un detalizētu kartēšanas informāciju. 
- **Segmenta eksports** ļauj eksportēt segmenta entītijas no auditorijas ieskatiem. Segmenti apzīmē klientu profilu sarakstu. Konfigurējot eksportēšanu, jūs atlasāt iekļautos datu laukus atkarībā no mērķa sistēmas, uz kuru eksportējat datus. 

### <a name="export-segments"></a>Segmentu eksportēšana

**Uzņēmējdarbības uzņēmumu (B2B) vai atsevišķu klientu (B2C) segmentu eksportēšana vidēs**  
Vairākums eksportēšanas opciju atbalsta abus vides tipus. Segmentu eksportēšanai uz dažādām mērķa sistēmām ir noteiktas prasības. Parasti šī informācija, segmenta elements klienta profils, satur kontaktinformāciju. Lai gan parasti tas attiecas uz segmentiem, kas būvēti uz atsevišķiem klientiem (B2C), tas ne vienmēr attiecas uz segmentiem, kuru pamatā ir uzņēmuma uzņēmumi (B2B). 

**Segments eksportē vidi uzņēmuma uzņēmumiem (B2B)**  
- Segmenti biznesa uzņēmumu vides kontekstā ir veidoti uz *uzņēmuma* entītijas. Lai eksportētu arī uzņēmumu segmentus, mērķa sistēmai ir nepieciešams atbalstīt tikai uzņēmumu segmentus. Tas attiecas uz [LinkedIn](export-linkedin-ads.md), kad, definējot eksportēšanu, izvēlaties **uzņēmuma** opciju.
- Visām pārējām mērķa sistēmām nepieciešami kontaktpersonas entītijas lauki. Lai nodrošinātu, ka uzņēmuma segmenti var izgūt datus no saistītajām kontaktpersonām, segmenta definīcijai ir jāmācās ar kontaktpersonas entītijas atribūtiem. Papildinformācija par [segmentu un projekta atribūtu konfigurēšanu](segment-builder.md).

**Segmenta eksportēšana vidē atsevišķiem klientiem (B2C)**  
- Segmenti biznesa uzņēmumu vides kontekstā ir veidoti uz *vienotā klientu profila* entītijas. Katrs segments, kas atbilst mērķa sistēmu prasībām (piemēram, e-pasta adrese), var tikt eksportēts.

**Segmenta eksportēšanas ierobežojumi**  
- Trešo pušu mērķa sistēmas var ierobežot eksportējamā klientu profilu skaitu. 
- Kad atlasāt eksportēšanai segmentu, atsevišķiem klientiem tiek parādīts faktiskais segmenta dalībnieku skaits. Ja segments ir pārāk liels, tiks parādīts brīdinājums. 
- Attiecībā uz biznesa uzņēmumiem segmentā tiek parādīts uzņēmumu skaits; tomēr netiek rādīts, cik kontaktpersonas, iespējams, tiks prognozētas. Dažos gadījumos tas var novest pie eksportētā segmenta, kurā faktiski ir vairāk klientu profilu, nekā to pieņem mērķa sistēma. Pārsniedzot mērķa sistēmu ierobežojumus, eksportēšana tiks izlaista. 

## <a name="set-up-a-new-export"></a>Jauna eksporta iestatīšana  
Lai iestatītu vai rediģētu eksportu, ir jābūt pieejamiem savienojumiem. Savienojumi ir atkarīgi no jūsu [lietotāja lomas](permissions.md):
- **Administratoriem** ir piekļuve visiem savienojumiem. Viņi var arī eksportēšanas iestatīšanas laikā izveidot jaunus savienojumus.
- **Līdzstrādniekiem** nav piekļuves konkrētiem savienojumiem. Viņi ir atkarīgi no administratoriem, kuri konfigurē un kopīgo savienojumus. Eksportēšanas sarakstā tiek rādīti dalībnieki, vai viņi var rediģēt vai tikai skatīt eksportēšanu kolonnā **Jūsu atļaujas**. Lai iegūtu papildinformāciju, dodieties uz [Atļaut līdzdalībķiem izmantot savienojumu eksportēšanai](connections.md#allow-contributors-to-use-a-connection-for-exports).
- **Skatītāji** var skatīt tikai esošu eksportu — nevis to izveidot.

### <a name="define-a-new-export"></a>Jauna eksporta iestatīšana

1. Pārejiet uz **Dati** > **Eksportēšana**.

1. Lai izveidotu jaunu eksportu, atlasiet **Pievienot eksportu**.

1. Rūtī **Iestatīt eksportu** atlasiet, kuru savienojumu izmantot. [Savienojumus](connections.md) pārvalda administratori. 

1. Norādiet prasīto informāciju un atlasiet **Saglabāt**, lai izveidotu ziņojumu.

### <a name="define-a-new-export-based-on-an-existing-export"></a>Definējiet jaunu eksportēšanu, pamatojoties uz esošu eksportēšanu

1. Pārejiet uz **Dati** > **Eksportēšana**.

1. Atskaišu sarakstā atlasiet dublicējamo atskaiti.

1. Atlasiet komandjoslā **Izveidot dublikātu**, lai atvērtu **Eksporta iestatīšanas** rūti ar detalizētu informāciju par atlasīto eksportēšanu.

1. Pārskatiet un pielāgojiet eksportēšanu un atlasiet **Saglabāt**, lai izveidotu jaunu eksportēšanu.

### <a name="edit-an-export"></a>Eksporta rediģēšana

1. Pārejiet uz **Dati** > **Eksportēšana**.

1. Atskaišu sarakstā atlasiet rediģējamo atskaiti.

1. Komandjoslā atlasiet **Rediģēt**.

1. Mainiet vērtības, kuras vēlaties atjaunināt, un atlasiet **Saglabāt**.

## <a name="view-exports-and-export-details"></a>Skatīt eksportu un eksportēšanas informāciju

Pēc eksporta galamērķu izveides tos uzskaita lapā **Dati** > **Eksporti**. Visi lietotāji var redzēt, kuri dati tiek kopīgoti, kā arī to jaunāko statusu.

1. Pārejiet uz **Dati** > **Eksportēšana**.

1. Ja esat lietotājs bez rediģēšanas atļaujām, atlasiet **Skatīt** nevis **Rediģēt**, lai skatītu eksportēšanas informāciju.

1. Sānu rūtī ir redzama eksportēšanas konfigurācija. Bez rediģēšanas atļaujas vērtības nav iespējams mainīt. Atlasiet **Aizvērt**, lai atgrieztos eksportēšanas lapā.

## <a name="schedule-and-run-exports"></a>Eksportēšanas darbību ieplānošana un palaišana

Katrai konfigurētai eksportēšanai ir atsvaidzināšanas grafiks. Atsvaidzināšanas laikā sistēma meklē jaunus vai atjauninātus datus, ko iekļaut eksportā. Pēc noklusējuma eksportēšana tiek izpildīta kā daļa no katras [plānotās sistēmas atsvaidzināšanas](system.md#schedule-tab). Varat pielāgot atsvaidzināšanas grafiku vai izslēgt to, lai palaistu eksportu manuāli.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

Eksportēšanas grafiki ir atkarīgi no vides stāvokļa. Ja laikā, kad būtu jāsāk plānotā atjaunināšana, notiek [atkarību](system.md#refresh-processes) atjaunināšana, sistēma vispirms pabeigs atjaunināšanu un pēc tam veiks eksportēšanu. Kolonnā **Atsvaidzināts** varat redzēt, kad eksportēšana tika pēdējo reizi atsvaidzināta.

### <a name="schedule-exports"></a>Eksportēšanas grafiks

Pielāgotus atsvaidzināšanas grafikus var definēt atsevišķam eksportēšanai vai vairāku veidu eksportēšanai vienlaikus. Pašlaik definētais grafiks ir norādīts eksportēšanas saraksta kolonnā **Grafiks**. Atļauja mainīt grafiku ir tāda pati kā [eksportēšanas rediģēšanai un definēšanai](export-destinations.md#set-up-a-new-export). 

1. Pārejiet uz **Dati** > **Eksportēšana**.

1. Atlasiet eksportēšanas darbību, ko vēlaties ieplānot.

1. Komandjoslā atlasiet **Ieplānot**.

1. **Plānošanas eksportēšanas** rūtī iestatiet **Ieplānot palaišanu** uz **Ieslēgts**, lai automātiski palaistu eksportēšanu. Iestatiet opciju **Izslēgt**, lai atsvaidzinātu manuāli.

1. Lai automātiski atsvaidzinātu eksportē, izvēlieties **Periodiskuma** vērtību un norādiet detalizētu informāciju par to. Definētais laiks attiecas uz visām atkārtošanās instancēm. Tas ir laiks, kad eksportēšanai ir jāsāk atsvaidzināšana.

1. Izmaiņu lietot un aktivizēt, atlasot vienumu **Saglabāt**.

Rediģējot vairāku eksportēšanas darbību grafiku, jums jāatlasa sadaļa **Atstāt vai ignorēt plānus**:
- **Atstāt atsevišķus grafikus**: nemainiet iepriekš definēto atlasītā eksportēšanas grafika darbību un tikai atspējojiet vai iespējojiet tos.
- **Definēt jaunu grafiku visām atlasītajām eksportēšanas darbībām**: ignorējiet atlasīto eksportēšanas darbību esošos plānus.

### <a name="run-exports-on-demand"></a>Eksportēšanas palaišana pēc pieprasījuma

Lai datus eksportētu, negaidot uz plānoto atsvaidzināšanu, dodieties uz **Dati** > **Eksportēšana**.

- Lai palaistu visus eksportus, komandjoslā atlasiet **Palaist visus**. Šī darbība tiks palaista tikai eksportam ar aktīvu grafiku.
- Lai izpildītu vienu eksportēšanas darbību, atlasiet to sarakstā un komandjoslā atlasiet **Izpildīt**. Tā tiek eksportēta bez aktīva grafika. 

## <a name="remove-an-export"></a>Eksporta noņemšana

1. Pārejiet uz **Dati** > **Eksportēšana**.

1. Atlasiet eksportēšanas darbību, kuru vēlaties noņemt.

1. Komandjoslā atlasiet vienumu **Noņemt**.

1. Apstipriniet noņemšanu, apstiprinājuma ekrānā atlasot pogu **Noņemt**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
