---
title: Eksportēšanas (priekšskatījuma) pārskats
description: Pārvaldiet eksportēšanu, lai kopīgotu datus.
ms.date: 08/12/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: overview
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- ci-connections
- customerInsights
ms.openlocfilehash: 44f58d694b9bd35a8d8c04d487d40743291e0566
ms.sourcegitcommit: ef3e17134d44d2731605381ea0385dbc5aef6120
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 09/09/2022
ms.locfileid: "9460199"
---
# <a name="exports-preview-overview"></a>Eksportēšanas (priekšskatījuma) pārskats

 Eksportēšana ļauj koplietot noteiktus datus ar dažādām lietojumprogrammām. Tajos var būt iekļauti klientu profili, entītijas, shēmas un detalizēta kartēšana. Katrai eksportēšanai ir nepieciešams [administratora iestatīts savienojums, lai pārvaldītu autentifikāciju un piekļuvi](connections.md). Lapā **Eksportēšana** tiek rādītas visas konfigurētās eksportēšanas.

## <a name="export-types"></a>Eksporta veidi

Ir divi galvenie eksporta veidi:  

- **Eksportējot datus**, varat eksportēt jebkura veida entītijas, kas pieejamas programmā Customer Insights. Eksportēšanai atlasītās entītijas tiek eksportētas, izmantojot visus datu laukus, metadatus, shēmas un detalizētu kartēšanas informāciju.
- **Segmentu eksportēšana** ļauj eksportēt segmenta entītijas no Customer Insights. Individuāliem patērētājiem (no B-līdz C) segmenti ir klientu profilu saraksts. Uzņēmumiem (no B līdz B [) segmenti var būt kontu vai kontaktpersonu saraksts](segment-builder.md#create-a-new-segment-with-segment-builder). Konfigurējot eksportēšanu, jūs atlasāt iekļautos datu laukus atkarībā no mērķa sistēmas, uz kuru eksportējat datus.

### <a name="export-segments"></a>Segmentu eksportēšana

**Uzņēmējdarbības uzņēmumu (B2B) vai atsevišķu klientu (B2C) segmentu eksportēšana vidēs**  
Lielākā daļa eksportēšanas opciju atbalsta abu veidu vides. Segmentu eksportēšanai uz dažādām mērķa sistēmām ir īpašas prasības. 

**Segmenta eksportēšana vidē atsevišķiem klientiem (B2C)**  
- Segmenti biznesa uzņēmumu vides kontekstā ir veidoti uz *vienotā klientu profila* entītijas. Katrs segments, kas atbilst mērķa sistēmu prasībām (piemēram, e-pasta adrese), var tikt eksportēts.

**Segmenta eksports vidēs uzņēmumu kontiem (no B līdz B)**  
- Segmenti biznesa kontu vides kontekstā tiek veidoti uz konta entītijas *vai kontaktpersonas* entītijas *.* Lai eksportētu arī uzņēmumu segmentus, mērķa sistēmai ir nepieciešams atbalstīt tikai uzņēmumu segmentus. Tas attiecas uz [LinkedIn](export-linkedin-ads.md), kad, definējot eksportēšanu, izvēlaties **uzņēmuma** opciju.
- Visām pārējām mērķa sistēmām nepieciešami kontaktpersonas entītijas lauki.
- Izmantojot divus segmentu tipus (kontaktpersonas un kontus), Customer Insights automātiski identificē, kāda veida segmenti ir piemēroti eksportēšanai, pamatojoties uz mērķa sistēmu. Piemēram, uz kontaktpersonu orientētai mērķa sistēmai, piemēram, Mailchimp, Customer Insights ļauj tikai izvēlēties kontaktpersonu segmentus, ko eksportēt.

**Segmenta eksportēšanas ierobežojumi**  
- Trešo pušu mērķa sistēmas var ierobežot eksportējamā klientu profilu skaitu. 
- Kad atlasāt eksportēšanai segmentu, atsevišķiem klientiem tiek parādīts faktiskais segmenta dalībnieku skaits. Jūs saņemsiet brīdinājumu, ja segments ir pārāk liels. 
- Uzņēmumu kontos redzēsit kontu vai kontaktpersonu skaitu atkarībā no segmenta. Jūs saņemsiet brīdinājumu, ja segments ir pārāk liels. Pārsniedzot mērķa sistēmu ierobežojumus, eksportēšana tiks izlaista.

## <a name="set-up-a-new-export"></a>Jauna eksporta iestatīšana

Lai iestatītu vai rediģētu eksportēšanu, ir nepieciešami pareizie pieejamie savienojumi. Savienojumi ir atkarīgi no jūsu [lietotāja lomas](permissions.md):
- **Administratoriem** ir piekļuve visiem savienojumiem. Viņi var arī eksportēšanas iestatīšanas laikā izveidot jaunus savienojumus.
- **Līdzstrādniekiem** nav piekļuves konkrētiem savienojumiem. Viņi ir atkarīgi no administratoriem, kuri konfigurē un kopīgo savienojumus. Eksportēšanas sarakstā tiek rādīti dalībnieki, vai viņi var rediģēt vai tikai skatīt eksportēšanu kolonnā **Jūsu atļaujas**. Lai iegūtu papildinformāciju, dodieties uz [Atļaut līdzdalībķiem izmantot savienojumu eksportēšanai](connections.md#allow-contributors-to-use-a-connection-for-exports).
- **Skatītāji** var skatīt tikai esošu eksportu — nevis to izveidot.

1. Pārejiet uz **Dati** > **Eksportēšana**.

1. Lai izveidotu jaunu eksportu, atlasiet **Pievienot eksportu**.

1. Eksportēšanas **rūts Iestatīšana** atlasiet, kuru [savienojumu](connections.md) izmantot.

1. Norādiet prasīto informāciju un atlasiet **Saglabāt**, lai izveidotu ziņojumu. Lai iegūtu nepieciešamo informāciju, pārskatiet Customer Insights dokumentāciju konkrētajai eksportēšanai.

## <a name="manage-existing-exports"></a>Esošās eksportēšanas pārvaldība

Dodieties uz **Datu** > **eksportēšana,** lai skatītu eksportu, tā savienojuma nosaukumu, savienojuma veidu un statusu. Visas lietotāju lomas var skatīt konfigurētās eksportēšanas. Eksportēšanas sarakstu var kārtot pēc jebkuras kolonnas vai izmantot meklēšanas lodziņu, lai atrastu eksportēšanu, kuru vēlaties pārvaldīt.

Atlasiet eksportēšanu, lai skatītu pieejamās darbības.

:::image type="content" source="media/exports_showmore.png" alt-text="Eksporta lapa.":::

- **Skatiet** vai **rediģējiet** eksportēšanu. Ja esat lietotājs bez rediģēšanas atļaujām, atlasiet **Skatīt** nevis **Rediģēt**, lai skatītu eksportēšanas informāciju.
- **Veiciet** eksportēšanu, lai eksportētu jaunākos datus.
- **Izveidojiet eksportēšanas dublikātu**.
- **[Plānojiet](#schedule-and-run-exports)** eksportu.
- **Atvienojiet savienojumu**, lai noņemtu savienojumu šai eksportēšanai. Atvienošana nenoņem savienojumu, bet deaktivizē eksportēšanu. Kolonnā Izmantotais **savienojums** tiek parādīts Bez savienojuma.
- **Noņemiet** eksportēšanu.

## <a name="schedule-and-run-exports"></a>Eksportēšanas darbību ieplānošana un palaišana

Katrai konfigurētai eksportēšanai ir atsvaidzināšanas grafiks. Atsvaidzināšanas laikā sistēma meklē jaunus vai atjauninātus datus, ko iekļaut eksportā. Pēc noklusējuma eksportēšana tiek izpildīta kā daļa no katras [plānotās sistēmas atsvaidzināšanas](schedule-refresh.md). Varat pielāgot atsvaidzināšanas grafiku vai izslēgt to, lai palaistu eksportu manuāli.

> [!TIP]
> Samaziniet segmenta eksporta apstrādes laiku, izmantojot tālāk norādīto paraugpraksi.
> - Sadaliet segmenta entītijas dažādos izvedumos.
> - Izvairieties no visu eksportēšanas ieplānošanas vienlaikus. Atstājiet 30 minūtes vai vienu stundu starp katra eksporta plānoto laiku.

Eksportēšanas grafiki ir atkarīgi no vides stāvokļa. Ja laikā, kad būtu jāsāk plānotā atjaunināšana, notiek [atkarību](system.md#refresh-processes) atjaunināšana, sistēma vispirms pabeigs atjaunināšanu un pēc tam veiks eksportēšanu. Atsvaidzinātajā **kolonnā tiek rādīts**, kad eksportēšana pēdējo reizi tika atsvaidzināta.

### <a name="schedule-exports"></a>Eksportēšanas grafiks

Definējiet pielāgotus atsvaidzināšanas grafikus atsevišķai eksportēšanai vai vairākām eksportēšanām vienlaikus. Pašlaik definētais grafiks ir norādīts eksportēšanas saraksta kolonnā **Grafiks**. Atļauja mainīt grafiku ir tāda pati kā [eksportēšanas rediģēšana un definēšana](export-destinations.md#set-up-a-new-export).

1. Pārejiet uz **Dati** > **Eksportēšana**.

1. Atlasiet eksportēšanas darbību, ko vēlaties ieplānot.

1. Atlasiet **Plānot**.

1. **Plānošanas eksportēšanas** rūtī iestatiet **Ieplānot palaišanu** uz **Ieslēgts**, lai automātiski palaistu eksportēšanu. Iestatiet opciju **Izslēgt**, lai atsvaidzinātu manuāli.

1. Lai automātiski atsvaidzinātu eksportē, izvēlieties **Periodiskuma** vērtību un norādiet detalizētu informāciju par to. Definētais laiks attiecas uz visām atkārtošanās instancēm. Tas ir laiks, kad eksportēšanai ir jāsāk atsvaidzināšana.

1. Atlasiet **Saglabāt**.

Rediģējot vairāku eksportēšanas grafiku, veiciet atlasi sadaļā **Paturēt vai ignorēt grafikus**:

- **Paturēt atsevišķus grafikus**: saglabājiet iepriekš definēto atlasīto eksportēšanas grafiku un atspējojiet vai iespējojiet tos tikai.
- **Definēt jaunu grafiku visām atlasītajām eksportēšanas darbībām**: ignorējiet atlasīto eksportēšanas darbību esošos plānus.

### <a name="run-exports-on-demand"></a>Eksportēšanas palaišana pēc pieprasījuma

Lai datus eksportētu, negaidot uz plānoto atsvaidzināšanu, dodieties uz **Dati** > **Eksportēšana**.

- Lai palaistu visus eksportus, komandjoslā atlasiet **Palaist visus**. Tiek veikta tikai eksportēšana, kurai ir aktīvs grafiks. Lai palaistu eksportēšanu, kas nav aktīva, palaidiet vienu eksportēšanu.
- Lai izpildītu vienu eksportēšanas darbību, atlasiet to sarakstā un komandjoslā atlasiet **Izpildīt**.

## <a name="troubleshooting"></a>Problēmu novēršana

### <a name="segment-not-eligible-for-export"></a>Segments, kas nav piemērots eksportam

**Problēma** Uzņēmējdarbības kontu vidē jūsu eksports neizdodas ar kļūdas ziņojumu: "Šim eksportēšanas galamērķim nav piemērots šāds segments: "{segmenta} nosaukums". Lūdzu, izvēlieties tikai segmentus, kuru tips ir ContactProfile, un mēģiniet vēlreiz.

**Resolution** Customer Insights vides biznesa kontiem tika atjauninātas, lai atbalstītu kontaktpersonu segmentus papildus kontu segmentiem. Šo izmaiņu dēļ eksportēšana, kurai nepieciešama kontaktinformācija, darbojas tikai ar segmentiem, kuru pamatā ir kontaktpersonas.

1. [Izveidojiet segmentu, pamatojoties uz kontaktpersonām](segment-builder.md), kas atbilst jūsu iepriekš izmantotajam segmentam.

1. Kad šis kontaktpersonu segments ir palaists, rediģējiet attiecīgo eksportu un atlasiet jauno segmentu.

1. Atlasiet **Saglabāt**, lai saglabātu konfigurāciju, vai **Saglabāt un palaist**, lai uzreiz pārbaudītu šo eksportēšanu.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]


[!INCLUDE [footer-include](includes/footer-banner.md)]
