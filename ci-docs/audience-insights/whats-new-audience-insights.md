---
title: Jaunie un gaidāmie līdzekļi
description: Informācija par jaunajiem līdzekļiem, uzlabojumiem un kļūdu labojumiem.
ms.date: 03/08/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: midevane
manager: shellyha
ms.openlocfilehash: 96c0b871eeaaf0976e5c718f37f883f4410977dc
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598447"
---
# <a name="whats-new-in-the-audience-insights-capability-of-dynamics-365-customer-insights"></a>Jaunumi klausītāju ieskatiem Dynamics 365 Customer Insights iespējās

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Ar prieku paziņojam par mūsu jaunākajiem atjauninājumiem! Šajā rakstā ir apkopotas publiskā priekšskatījuma funkcijas, vispārējie pieejamības uzlabojumi un funkciju atjauninājumi. Lai skatītu informāciju par ilgtermiņa plāniem attiecībā uz funkcijām, skatiet [Dynamics 365 un Power Platform laidienu plānus](/dynamics365/release-plans/).

Varat skatīties arī tālāk norādītos video, lai uzzinātu vairāk par pēdējo sešu mēnešu plānotajām iespējām.

> [!VIDEO https://www.youtube.com/embed/jQh-7pscH30]

Atjauninājumi tiek ieviesti katrā reģionā atsevišķi. Tāpēc noteikti reģioni var agrāk skatīt funkcijas nekā citi. Ja vien nav norādīts citādi, neveiciet nekādu darbību, un programma automātiski atjauninās programmu bez jebkādas dīkstāves.

> [!TIP]
> Lai iesniegtu funkciju pieprasījumus un produktu ieteikumus, kā arī balsotu par tiem, dodieties uz [Dynamics 365 programmas ideju portālu](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).

## <a name="february-2021-updates"></a>2021. gada februāra atjauninājumi

2021. gada februāra atjauninājumi ietver vairākus līdzekļus, veiktspējas jauninājumus un kļūdu labojumus.

#### <a name="extensibility"></a>Paplašināšana

- **Segmentu eksportēšana programmā AdRoll**

  Esam paplašināuši savus eksportēšanas adresātus, iekļaujot tajā AdRoll. Tagad segmentus no Customer Insights varat eksportēt uz AdRoll mērķauditoriju, un tos varat izmantot kā reklāmas bāzlīniju. Papildinformāciju skatiet rakstā [AdRoll savienotājs](export-adroll.md).

#### <a name="segments"></a>Segmenti
 
- **Dublēt segmentu**
  
  Lai izveidotu jaunu segmentu, pamatojoties uz esošu segmentu, tagad varat izveidot segmenta dublikātu un rediģēt dublikātu segmentu, lai to sīkāk precizētu. 

- **Papildu atribūtu pievienošana segmentam**

  Tagad segmenta izvadē varat iekļaut atribūtus, pat ja šie atribūti nav daļa no klienta profila. Piemēram, segmentā iekļaujiet abonementa ID, pat ja tas ir daļa no abonementa entītijas, kam ir M:1 attiecība ar klienta entītiju. Ja atribūts pieder ar klienta entītiju saistītai entītijai, tagad varat iekļaut šos atribūtus.  

#### <a name="predictions"></a>Prognozes

- **Produktu prognozējošu ieteikumu izveide**

  Izpratne par to, kādi klienti ir ieintereti pirkšanā, ir viena no pirmajām darbībām, kas nepieciešama, lai uzlabotu uzņēmuma ieņēmumus un veidotu klientu lojalitāti, izmantojot personalizāciju un iesaisti. Sniedzot ieteikumus par produktiem, kas nav pielāgoti klienta interesēm, var rasties savienojuma pārtraukšanas sajūta starp klientu un jūsu uzņēmumu un galu galā ierobežot kopējos iespējamos ieņēmumus un klienta pieredzi. 

  Tagad varat izmantot savus datus, lai noteiktu, kādus produktus jūsu klienti nākotnē visticamāk iegādāsies. Papildinformāciju skatiet sadaļā [Produktu ieteikumu prognoze](predict-product-recommendation.md).

#### <a name="system-administration"></a>Sistēmas administrēšana

- **Vides atbalsta kopēšana vairākiem datu avotu veidiem**

  Administratori var kopēt vides konfigurācijas uz jaunu vidi tajā pašā organizācijā. Šis līdzeklis paplašina kopētās vides funkcionalitāti pieteikumiem, kuros tiek izmantoti datu avoti, kas balstīti uz Common Data Service Data Lake vai Common Data Model mapi.

## <a name="january-2021-updates"></a>2021. gada janvāra atjauninājumi

2021. gada janvāra atjauninājumi ietver vairākus līdzekļus, veiktspējas jauninājumus un kļūdu labojumus.

#### <a name="extensibility"></a>Paplašināšana

- **Paplašinātā funkcionalitāte un uzlabotā veiktspēja SFTP eksportam** Tagad visas izvades entītijas no Customer Insights varat eksportēt uz SFTP viesošanas servisu. Iepriekš eksportēšana tika veikta tikai uz segmenta entītijām. Turklāt SFTP viesotāja eksportēšana ļauj vairāk datu apjoma mazākā laika posmā atkarībā no SFTP viesotāja veiktspējas.    
  Papildinformāciju skatiet rakstā [SFTP savienotājs (priekšskatījums)](export-sftp.md).  

#### <a name="segments"></a>Segmenti

- **Algoritmiskās mācīšanās nodrošinātie ieteiktie segmenti, lai uzlabotu metriku** Ir jauns veids, kā atrast un izveidot segmentus. Sistēma izmanto mākslīgā intelekta modeli, lai ieteiktu segmentus, kas var palīdzēt uzlabot KPI (pasākumu), kam jau sekojat. Mēs rādām jūsu atlasītā atribūta ietekmi uz pasākumu vai citu primāro atribūtu. Šī informācija palīdz atrast iespējamos segmentus, kas sniedz iespējas.    
  Papildinformācijai skatiet [Ieteiktie segmenti (priekšskatījums)](suggested-segments.md).

#### <a name="data-unification"></a>Datu apvienošana

- **Uzlabota atbilstības pieredze** Datu apvienošanas apgabalā tika atjaunināta atbilstības pieredze. Tas ļauj konfigurēt un skatīt atbilstības kārtulas, tostarp detalizētu statistiku, lai izskaidrotu atbilstības noteikšanas darbību. Ir pieejamas opcijas atbilstības kārtulas atspējošanai, lai tā vairs nebūtu aktīva, saglabājot konfigurāciju, vilkšanas un nomešanas atbilstības kārtulas utt.
  Papildinformāciju skatiet tēmā [Entītiju atbilstība](match-entities.md).

- **Dedublēšanas izvade no atbilstības procesa ir pieejama kā entītija** Dedublēšanas procesa izvade no atbilstības procesa tagad ir ierakstīta atsevišķā entītijā turpmākai analīzei. Šajā entītijā ir lauki, kas tiek izmantoti dedublēšanas procesā, un uzvarētāja ieraksts, kā arī attiecīgie alternatīvie ieraksti, kas tiek sapludināti ar uzvarētāja ierakstu.
  Papildinformāciju skatiet tēmā [Dedublēšanas kā entītijas izvade](match-entities.md#deduplication-output-as-an-entity).

#### <a name="system-administration"></a>Sistēmas administrēšana

- **Netraucēti kopīgojiet datus ar Microsoft Dataverse** Tagad Customer Insights izvadi varat koplietot ar Microsoft Dataverse lietojumprogrammām, izmantojot risinājumu Microsoft Dataverse pārvaldīto Data Lake. Kad esat sasaistījis Dataverse vidi ar Customer Insights, varat izmantot opciju datu kopīgošanas iespējošanai.
  Papildinformācijai skatiet [Vižu pārvaldība](manage-environments.md).


## <a name="december-2020-updates"></a>2020. gada decembra atjauninājumi

2020.g. decembra atjauninājumi ietver vairākus līdzekļus, veiktspējas jauninājumus un kļūdu labojumus.

### <a name="new-and-updated-features-in-december-2020"></a>Jauni un atjaunināti līdzekļi 2020.g. decembrī

#### <a name="data-enrichment"></a>Datu bagātināšana

- **Uzlaboti zīmola un interešu radniecības bagātinājumi**
  
  Mēs vienkāršojām savu interešu rezultātus, lai tos varētu vieglāk izprast un izmantot. Tagad varat ātri identificēt klientus, balstoties uz viņu ieinteresētību attiecībā uz konkrētu zīmolu vai ieinteresētību.

  Turklāt esam pievienojuši jaunas konfigurācijas opcijas, lai labāk kontrolētu, kā vēlaties bagātināt klientu profilus. 

  Papildinformāciju skatiet tēmā [Klientu profilu bagātināšana ar zīmolu un interešu radniecības datiem](enrichment-microsoft-graph.md).

- **Kontrolējiet, kurus profilus bagātināt**

  Tagad varat bagātināt tikai klientu profilu apakškopu ar opciju atlasīt segmenta entītiju, nevis noklusējuma klienta entītiju. Izveidojiet segmentu ar klientu profiliem, kurus vēlaties bagātināt un atlasīt savas klientu datu kopas bagātināšanas konfigurācijā.
  Šis līdzeklis pašlaik ir pieejams tikai bagātināšanai, ko nodrošina Experian un HERE Technologies. Mēs šo iespēju iespējojam, lai drīz bagātinātu vairāk.

  Papildinformāciju skatiet sadaļā [Klientu profilu bagātināšana ar demogrāfiskajiem datiem no Experian](enrichment-experian.md) vai [Klientu profilu bagātināšanas, izmantojot HERE Technologies](enrichment-here.md).

#### <a name="extensibility"></a>Paplašināšana

- **Savu segmentu aktivizēšana, lietojot Autopilot**

  Eksportējiet segmentus uz Autopilot un izmantojiet tos mārketinga mērķiem. Papildinformāciju skatiet rakstā [Autopilot savienotājs (priekšskatījums)](export-autopilot.md).

- **Savu segmentu aktivizēšana, lietojot SendGrid**

  Eksportējiet segmentus uz SendGrid un izmantojiet tos mārketinga mērķiem. Papildinformāciju skatiet rakstā [SendGrid savienotājs](export-sendgrid.md).

#### <a name="system-administration"></a>Sistēmas administrēšana

- **Atjaunināta vides pārvaldības pieredze**
  
  Tagad vides varat izveidot, rediģēt, dzēst un atiestatīt tieši no vides atlasītāja programmas galvenē. 
  
  Turklāt vide, kuru izmantojat, tiks piesprausta vides paneļa augšdaļā, tādēļ jums tā nav jāmeklē.

  Papildinformācijai skatiet [Vižu pārvaldība](manage-environments.md).

## <a name="november-2020-updates"></a>2020. gada novembra atjauninājumi

2020.g. novembra atjauninājumi ietver vairākus līdzekļus, veiktspējas jauninājumus un kļūdu labojumus.

### <a name="new-and-updated-features-in-november-2020"></a>Jauni un atjaunināti līdzekļi 2020.g. novembrī

#### <a name="data-enrichment"></a>Datu bagātināšana

- **Ienesiet savus bagātināšanās datus, izmantojot drošo failu pārsūtīšanas protokola (SFTP) pielāgoto importēšanu**
  
  Faila drošas pārsūtīšanas protokola (SFTP) pielāgotā importēšana ļauj importēt bagātināšanas datus, kuriem nav jāiziet datu apvienošanas process. Papildinformācija par SFTP pielāgoto importēšanu

  Papildinformāciju skatiet tēmā [Klientu profilu bagātināšana ar pielāgotajiem datiem (priekšskatījums)](enrichment-SFTP-custom-import.md).
 
- **Pilnveidojiet savus klientu datus, izmantojot šeit tehnoloģijas atrašanās vietas datus**

  Izmantojot HERE Technologies datu bagātināšanas pakalpojumus, varat izveidot precīzāku atrašanās vietu, lai izprastu klientus, izmantojot adrešu normalizēšanu, platuma un garuma izgūšanu utt. Papildinformācija par bagātināšanu ar HERE Technologies.

  Papildinformāciju skatiet tēmā [Klientu profilu bagātināšana ar HERE Technologies](enrichment-here.md).

#### <a name="data-unification"></a>Datu apvienošana

- **Elastība, lai iespējotu datu profilēšanu attiecībā uz atlasītajām entītijām un laukiem no krātuves konta**

  Jūs varat norādīt, kuras datu entītijas un laukus no kopēja datu modeļa mapes jūsu Azure Data Lake Storage kontā vēlaties, lai iespējotu datu profilēšanu kā daļu no datu uzņemšanas procesa.

  Papildinformāciju skatiet tēmā [Savienojuma izveide ar kopēju datu modeļa mapi](connect-common-data-model.md#connect-to-a-common-data-model-folder).

#### <a name="extensibility"></a>Paplašināšana

- **Sava segmenta aktivizēšana, lietojot Google Ads**

  Eksportējiet klientu profilu unificētos segmentus uz un no Google Ads un izmantojiet šos sarakstus reklāmām pakalpojumā Google Search, Google Display Network, YouTube un Gmail. Uzziniet vairāk par segmentu aktivizēšanu, lietojot Google Ads.

  Papildinformāciju skatiet rakstā [Google Ads savienotājs](export-google-ads.md).

- **Sava segmenta aktivizēšana, lietojot Marketo**

  Eksportējiet segmentus uz Marketo auditorijām un izmantojiet šīs auditorijas mārketinga automatizācijai. Uzziniet vairāk par segmentu aktivizēšanu, lietojot Marketo. 

  Papildinformāciju skatiet rakstā [Google Ads savienotājs](export-marketo.md).

- **Sava segmenta aktivizēšana, lietojot DotDigital**

  Eksportējiet segmentus uz DotDigital un izmantojiet tos mārketinga mērķiem. Uzziniet vairāk par segmentu aktivizēšanu, lietojot DotDigital. 

  Papildinformāciju skatiet rakstā [DotDigital savienotājs](export-dotdigital.md).

#### <a name="predictions"></a>Prognozes

- **Transakciju zuduma prognoze**

  Transakciju zudumu prognozes līdzeklis ļauj jums bez palīdzības no datu zinātnieka paredzēt klienta iespējamību pārtraukt pirkt produktus vai servisu.  Izmantojot prognoze punktu skaitu, varat apvienot citu informāciju par klientiem, piemēram, klienta vērtību, lai izveidotu augsta zuduma riska vai augstvērtīgu klientu segmentus. Izmantojiet šo segmentu, lai tieši sazinātos ar klientiem, izmantojot tirgvedības pasākumus, klientu atbalstu un citus scenārijus, lai samazinātu zudumu risku.
 
  Konfigurējiet zuduma definīciju kā uz laiku balstītu logu, kas raksturīgs jūsu uzņēmumam ,un definējiet, kad klienti tiek uzskatīti par zudušiem. Piemēram, pārtikas preču veikals var vēlēties uzskatīt klientu par zudušu, ja vien viņi nav iepirkuši neko pēdējo 30 dienu laikā.
 
  Turpinot prognozes izveidi, tiks parādīts, kādi dati ir nepieciešami, un ļaus kartēt jūsu uzņēmuma datus uz laukiem, kas nepieciešami, lai prognozētu jūsu klientu zudumus. Varat arī iestatīt grafiku, lai pārmācītu modeli, pamatojoties uz jauno informāciju jūsu sistēmā, lai pielāgotos mainīgajiem uzņēmējdarbības apstākļiem.
 
  Papildinformāciju skatiet šeit: [Transakciju zudumu prognoze (priekšskatījums)](predict-transactional-churn.md).

#### <a name="system-administration"></a>Sistēmas administrēšana

- **Atiestatīt vidi**

  Atiestatiet visu atlasītā gadījuma vidi, lai sāktu no jauna.

  Papildinformāciju skatiet sadaļā [Esošas vides atiestatīšana](manage-environments.md#reset-an-existing-environment).


- **Izveidojiet savienojumu ar pakalpojuma Azure Data Lake Storage kontu, izmantojot pakalpojuma primāro nosaukumu**

  Rakstīt datu izvadi un lasīt datus no krātuves konta, izmantojot Azure pakalpojuma primāro nosaukumu. Esošie krātuves konta savienojumi var turpināt lietot uzņēmuma atslēgu. Viņi piedāvā arī jaunināšanas opciju, lai izmantotu pakalpojuma primāro nosaukumu, kas virzās uz priekšu. Jaunu savienojumu pamatā ir pakalpojuma primārā autentifikācijas metode jūsu krātuves kontam.

  Papildinformāciju skatiet tēmā [Auditorijas ieskatu savienošana ar Azure Data Lake Storage Gen2 kontu, izmantojot Azure pakalpojuma primāro nosaukumu](connect-service-principal.md).

## <a name="october-2020-updates"></a>2020. gada oktobra atjauninājumi

Atjauninājumi 2020.g. oktobrī ietver vairākus līdzekļus, veiktspējas jauninājumus un kļūdu labojumus.

### <a name="new-and-updated-features-in-october-2020"></a>Jauni un atjaunināti līdzekļi 2020.g. oktobrī

#### <a name="extensibility"></a>Paplašināšana

- **Eksportēt uz Mailchimp**

Eksportējiet segmentus uz esošiem auditorijas sarakstiem pakalpojumā Mailchimp, lai klientiem nodrošinātu personalizētu e-pasta lietošanas pieredzi.

Papildinformāciju skatiet rakstā [Mailchimp savienotājs](export-mailchimp.md).

#### <a name="data-enrichment"></a>Datu bagātināšana

- **Avota ierakstu dedublēšana atbilstības entītijā**

Lai identificētu ierakstu dublikātus, norādiet atkārtošanas kārtulas entītijām, kas tiek izmantotas saskaņošanas procesā. Sapludiniet tos vienā ierakstā, un saistiet visus avota ierakstus ar šo sapludināto ierakstu. Pēc tam, kad ir identificēts nedublēts ieraksts, šis ieraksts tiks izmantots krustenisko entītiju atbilstības procesā.

Papildinformāciju skatiet tēmā [Dedublēšanas definēšana sakrīt ar entītiju](match-entities.md#define-deduplication-on-a-match-entity).

#### <a name="system-administration"></a>Sistēmas administrēšana

- **Instrumentācija: Jauna atsvaidzināšanas opcija sapludināšanā**

Līdz mūsdienām, palaižot sapludināšanas procesu, sistēma vadīja visus pakārtotos procesus, kas ir atkarīgi no sapludināšanas un turpmākajiem procesiem. Tagad varat pārbaudīt sapludināšanas procesa (Unified Customer ENTITY) izvadi, pirms to izmantot pakārtotajā apstrādei, piemēram, segmentos vai pasākumos.
Sapludināšanas lapā tagad varat izvēlēties izpildīt tikai sapludināšanas darbību un izpildīt tikai šo procesu. Lai atsvaidzinātu visus pakārtotos procesus, varat izvēlēties izpildīt sapludināšanas un pakārtotos procesus. 

## <a name="september-2020-updates"></a>2020. gada septembra atjauninājumi

 2020. gada septembra atjauninājumi ietver vairākus līdzekļus, veiktspējas jauninājumus un kļūdu labojumus.

### <a name="new-and-updated-features-in-september-2020"></a>Jauni un atjaunināti līdzekļi 2020. gada septembrī

#### <a name="activities"></a>Darbības

- **Atribūtu semantikas inteliģentā prognoze**

Šis jaunais līdzeklis prognozē ievades atribūtu semantiskos tipus, kas tiek nodoti datu apvienošanas procesam. Tajā izmanto algoritmiskās mācīšanās modeļus, kas uzlabo precizitāti un ietaupa laiku.

#### <a name="enrichments"></a>Bagātinājumi

- **Demogrāfijas bagātināšana no Experian**

Demogrāfijas bagātināšana no Experian tagad pieejams priekšskatījumā. Experian ir pasaules mērojas līderis patērētāju un uzņēmumu kredītatskaišu un mārketinga pakalpojumu nodrošināšanā. Ar [Experian datu bagātināšanas pakalpojumiem](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage) varat veidot padziļinātāku izpratni par saviem klientiem, bagātinot klientu profilus ar demogrāfijas datiem, piemēram, mājsaimniecības izmēru, ieņēmumiem un citu informāciju.

Lai izmantotu šo līdzekli, ir jābūt aktīvam Experian abonementam.

Papildinformāciju skatiet šeit: [Klientu profilu bagātināšana ar demogrāfiju no Experian](enrichment-experian.md)


#### <a name="system-administration"></a>Sistēmas administrēšana

- **Uzdevuma informācijas rūts**

Uzdevuma informācijas rūtī varat apskatīt informāciju par sistēmas palaistajiem uzdevumiem. Tas ir parocīgs veids, kā noteikt konfigurācijas problēmas un meklēt risinājumus.
Pārskatiet kļūdu ziņojumus un skatiet, kā risināt iespējamās problēmas.
 
- **Papildu lapām pievienotas informācijas apstrāde**

Šis uzlabojums pievieno informāciju par jūsu entītiju statusu lapā **Entītijas** un **Klienti**.
 
Turklāt abās šajās lapās varat skatīt informāciju par procesu norisi, kā arī uzdevuma informāciju.

- **Sistēmas statusa lapas uzlabojumi**

Esam uzlabojuši statusa informācijas tabulas struktūru sadaļā **Sistēma** > **Statuss**, kad tiek pārskatīts datu eksports.
 
Turklāt kļūdas kolonnā **Informācija** tagad ir detalizētākas, un ar tām var veikt vairāk darbību. 
 
- **Atcelšana atjauno darbu atpakaļ uz iepriekšējo stāvokli**

Kad atceļat uzdevumu, piemēram, saskaņošanas procesā, tas tiek atgriezts pēdējā stāvoklī. Piemēram, ja saskaņošanas process tika pabeigts vakar un jūs to atceļat šodien, tas atgriezīsies pie vakardienas veiksmīgā stāvokļa.


## <a name="august-2020-updates"></a>2020. gada augusta atjauninājumi

2020. gada augusta atjauninājumi ietver vairākus līdzekļus, veiktspējas jauninājumus un kļūdu labojumus.

### <a name="new-and-updated-features-in-august-2020"></a>Jauni un atjaunināti līdzekļi 2020. gada augustā

#### <a name="data-unification"></a>Datu apvienošana

- **Uzlabota pieredze attiecībā uz kartes posmu datu apvienošanas laikā**

  Datu apvienošanās procesa kartes posma pieredze ļauj vienkāršāk atlasīt entītijas, atribūtus un definēt semantiku.

  Tas ietver šādas izmaiņas:
  
  - vajag mazāk mijiedarbības entītiju un lauku pievienošanai
  - uzlabotas meklēšanas iespējas kartes lapā
  - Ieteiktā lauka tipa vizuālā un vienkāršā identifikācija

#### <a name="enrichment"></a>Bagātināšana

- **Interesenšu bagātinātājs, kas pieejams vairākos tirgos**

  Mēs sniedzam iespēju bagātināt interesi ārpus ASV līdz pieciem citiem tirgiem: Kanādā, Austrālijā, Lielbritānijā, Francijā un Vācijā. Izmantojot šo paplašinājumu, varat bagātināt klientu datus ar vairākām interesēm, kas attiecas uz šiem tirgiem. Mēs arī bagātināsim jūsu šajos tirgos esošo klientu profilus, izmantojot Microsoft Graph lokālos patentētos datus.
  Papildinformāciju skatiet tēmā [Klientu profilu bagātināšana ar zīmolu un interešu afinitātes datiem](enrichment-microsoft-graph.md)


## <a name="july-2020-updates"></a>2020. gada jūlija atjauninājumi

2020. gada jūlija atjauninājumi ietver vairākus līdzekļus, veiktspējas jauninājumus un kļūdu labojumus.

### <a name="new-and-updated-features-in-july-2020"></a>Jauni un atjaunināti līdzekļi 2020. gada jūlijā

#### <a name="extensibility"></a>Paplašināmība

- **Power Automate trigeris pabeigtam apvienošanas procesam**

  Mūsu trigeri ir ieviesti arī pakalpojumā Power Automate, ļaujot izveidot paziņojumu vai darbību, kad ir pabeigta apvienošanas procesa (kartēšanas, saskaņošanas, sapludināšanas) atsvaidzināšana.    
  Papildinformāciju skatiet rakstā [Power Automate savienotājs](export-power-automate.md)

#### <a name="enrichment"></a>Bagātināšana

- **Zīmolu bagātinātājs, kas pieejams vairākos tirgos**

  Mēs sniedzam iespēju bagātināt interesi par zīmoliem ārpus ASV līdz pieciem citiem tirgiem: Kanādā, Austrālijā, Lielbritānijā, Francijā un Vācijā. Izmantojot šo paplašinājumu, varat bagātināt klientu datus ar šo tirgu vietējām zīmoliem. Mēs arī bagātināsim jūsu šajos tirgos esošo klientu profilus, izmantojot Microsoft Graph lokālos patentētos datus.
  Papildinformāciju skatiet tēmā [Klientu profilu bagātināšana ar zīmolu un interešu afinitātes datiem](enrichment-microsoft-graph.md)

## <a name="june-2020-updates"></a>2020. gada jūnija atjauninājumi

2020. gada jūnija atjauninājumi ietver vairākus līdzekļus, veiktspējas jauninājumus un kļūdu labojumus.

### <a name="new-and-updated-features-in-june-2020"></a>Jauni un atjaunināti līdzekļi 2020. gada jūnijā

#### <a name="enrichment"></a>Bagātināšana

- **Bagātināšanās ar uzņēmuma datiem no Leadspace**
  
  Definējiet laukus vienotajos klientu profilos, kas tiek izmantoti, lai uzmeklētu saistītos uzņēmuma datus no Leadspace. Pēc bagātināšanas procesa izpildes B2B profili tiek bagātināti ar vairākiem atribūtiem, tostarp uzņēmuma lielumu, atrašanās vietu, nozari utt.    
  Šī sadarbība ļauj uzlabot jūsu datu kvalitāti, izmantojot trešo pušu pakalpojumu sniegtos datus.  Lai izmantotu šo bagātināšanu, jums ir nepieciešama licence no Leadspace, lai piekļūtu tā B2B uzņēmuma datiem. Sistēma izmantos šo licenci, lai nodrošinātu jūsu datu nepārtrauktu bagātināšanu.    
  Papildinformāciju skatiet rakstā [Uzņēmumu profilu bagātināšana ar Leadspace](enrichment-leadspace.md).

- **Bagātināšanas centra lapa**

  Visa pieejamā datu bagātināšana no pirmo un trešo pušu bagātināšanas nodrošinātājiem tiek konfigurēta vienā un tajā pašā vietā. Datu bagātināšanas konfigurēšana ir nemanāms pieredze, kas tiek pārvaldīta no kopīgas atrašanās vietas.    
  Papildinformāciju skatiet tēmā [Klientu profilu bagātināšana](enrichment-hub.md).

- **Atsevišķa zīmola un interešu afinitātes bagātināšana**

  Zīmolu un interešu afinitātes tagad ir pieejamas kā divas neatkarīgas bagātināšanas. Atsevišķas bagātināšanas sniedz elastīgu iespēju konfigurēt un pārvaldīt tās atsevišķi atkarībā no uzņēmuma prasībām vai vajadzībām.    
  Papildinformāciju skatiet tēmā [Klientu profilu bagātināšana ar zīmolu un interešu afinitātes datiem](enrichment-microsoft-graph.md).

#### <a name="extensibility"></a>Paplašināmība

- **Klikšķināmi URL vienotām darbībām Dynamics 365 Customer Card pievienojumprogrammā**

  Vienotās darbības Klienta kartes pievienojumprogrammā tagad rāda klikšķināmus vietrāžus URL, ja šādi URL ir definēti darbību konfigurēšanas laikā.    
  Papildinformācijai skatiet [Klientu kartes pievienojumprogramma](customer-card-add-in.md).

- **Zīmolu un interešu afinitātes pieejamas Dynamics 365 Customer Card pievienojumprogrammā**

  Jauna vadīkla Dynamics 365 Customer Card pievienojumprogrammā ļauj rādīt jūsu kontaktpersonu zīmolu un interešu bagātinājumus klientu iesaistes programmās pakalpojumā Dynamics 365.    
  Papildinformācijai skatiet [Klientu kartes pievienojumprogramma](customer-card-add-in.md).

- **Papildu Power Automate trigeri**

  Esam paplašinājuši mūsu trigeru pieejamību pakalpojumā Power Automate, pievienojot tālāk norādītos trigerus.
  - Saņemiet paziņojumu vai veiciet darbību, kad ir pabeigta pilna automātiska atsvaidzināšana (datu avoti, apvienošana, segmenti, mērvienības, eksports)
  - Definējiet biznesa mēra slieksni. Piemēram, varat izveidot paziņojumu, kas tiek nosūtīts, kad ir pārsniegts definētais slieksnis. Turklāt trigeris sniedz informāciju, kas ļauj veidot sarežģītākas darbplūsmas pakalpojumā Power Automate.    
  Papildinformāciju skatiet rakstā [Power Automate savienotājs](export-power-automate.md)

- **Eksportēšana uz Facebook Ads Manager**
  
  Šī iespēja ļauj eksportēt segmentus uz Facebook Ads Manager. Segmenti tiek eksportēti kā pielāgotas auditorijas, lai Facebook mārketinga kampaņās un reklāmās izmantotu vienotus klientu profilus. Pielāgotas auditorijas ir izmantojamas arī, lai izveidotu kampaņas pakalpojumā Instagram, izmantojot rīku Facebook Ads Manager.    
  Papildinformāciju skatiet tēmā [Facebook Ads Manager savienotājs](export-facebook.md).

#### <a name="predictions"></a>Prognozes

- **Abonementu zuduma prognoze**

  Sekojiet vadītai pieredzei, lai izveidotu zuduma prognozi tādos abonēšanas apgabalos kā mākoņpakalpojumi, klientu abonementi un citas nozares. 

  Abonementu zuduma prognozes līdzeklis ļauj prognozēt iespējamību, ka klients varētu pārtraukt ar abonementiem saistītu produktu vai pakalpojumu izmantošanu, bez datu zinātnieka iesaistīšanas. Izmantojot prognozes rezultātu, varat apvienot citu informāciju par klientiem, lai izveidotu augsta zuduma riska segmentus. Izmantojot šo segmentu, varat tieši adresēt klientus mārketinga, klientu atbalsta un citos scenārijos, lai mazinātu zuduma risku konkrētiem klientiem, tādējādi uzlabojot ieņēmumus un samazinot izmaksas.

  Šīs iespējas ietvaros varat konfigurēt zuduma definīciju kā jūsu uzņēmumam raksturīgu laikatkarīgu logu. Piemēram, video straumēšanas uzņēmums ar mēneša abonēšanas procesu, var apsvērt iespēju, ka klients pazudīs pēc 15 dienām pēc abonementa derīguma termiņa beigām.

  Turpinot prognozi, mēs jums palīdzēsim, norādot, kādi dati ir nepieciešami, un ļausim jūsu uzņēmuma datus kartēt laukos, kas nepieciešami, lai prognozētu klientu zudumu. Mainoties biznesa informācijai, varat arī iestatīt grafiku, lai sistēmā veiktu atkārtotu apmācību ar jauno informāciju un pielāgotos mainīgajiem uzņēmējdarbības apstākļiem.    
  Papildinformāciju skatiet rakstā: [Abonementu zuduma prognoze (priekšskatījums)](predict-subscription-churn.md).

#### <a name="segments"></a>Segmenti

- **Atrast līdzīgus klientus**
  
  Atrodiet līdzīgus klientus savā klientu bāzē, izmantojot mākslīgo intelektu. Binārās klasifikācijas algoritmiskā mācīšanās modelis piešķir klientiem līdzības rezultātu paplašinātajā segmentā. Rezultāts balstās līdzībā klientiem no avota segmenta. Atkarībā no līdzības rezultāta klientu profili tiek pievienoti jaunizveidotam segmentam.

  Dažkārt saukta par līdzīgu modelēšanu ciparu mārketingā, tā izmanto mākslīgā intelekta modeli, lai palīdzētu atrast klientus, kas ir līdzīgi citam klientu segmentam, faktorizējot vairāk atribūtu. Tas ļauj ne tikai izvēlēties atribūtus, bet arī norādīt maksimālo klientu skaitu, kuriem jābūt šajā jaunajā segmentā. Mākslīgā intelekta modelis aprēķina līdzības rezultātu katram klientam, pamatojoties uz jūsu atlasītajiem atribūtiem, un atrod klientus ar lielāko vidējo līdzības rezultātu. Iegūtais segments iekļaus klientus, kas ir līdzīgi jūsu sākotnējā segmenta klientam.    
  Papildinformāciju skatiet rakstā [Līdzīgi klienti](find-similar-customer-segments.md).

- **Segmentu pārklāšanās un diferencētāji**

  Segmentu pārklāšanās ļauj redzēt, cik daudz un kuri klienti ir kopīgi diviem vai vairākiem segmentiem. Piemēram, kā augstu tēriņu klientu segments pārklājas ar augstas apmierinātības klientu segmentu vai kā zūdošo klientu segments pārklājas ar zemas apmierinātības klientu segmentu. Turklāt varat analizēt, kā mainās pārklāšanās, pamatojoties uz jūsu izvēlēto papildu atribūtu.

  Segmenta diferencētāji atklāj, kas atšķir vienu segmentu no pārējiem jūsu klientiem vai no cita segmenta. Jums tikai ir jāidentificē segments, un sistēma identificēs profila atribūtus un mērus, kas izšķir segmentu vērtētu diferencētāju saraksta veidā — no spēcīgākā diferencētāja uz vājāko.    
  Plašāku informāciju skatiet rakstā [Ieskati segmentos (priekšskatījums)](segment-insights.md).

- **Segmenta pastāvēšanas laiks**
  
  Definējiet grafiku, lai aktivizētu vai deaktivizētu segmentu.    
  Papildinformāciju skatiet rakstā [Esošo segmentu pārvaldība](segments.md#manage-existing-segments).

## <a name="may-2020-updates"></a>2020. gada maija atjauninājumi

 2020. gada maija atjauninājumi ietver vairākas funkcijas, veiktspējas uzlabojumus, kā arī kļūdu labojumus.

### <a name="new-and-updated-features-in-may-2020"></a>Jaunas un atjauninātas funkcijas 2020. gada maijā

#### <a name="data-ingestion"></a>Datu pieņemšana

- **Reāllaika datu pieņemšana: vēstures skatījumi**

  Ja izmantojat mūsu API, lai pieņemtu reāllaika atjauninājumus, šo atjauninājumu apkopošanas vēsturi var redzēt līdz 30 dienām. Varat piekļūt visu veiksmīgo vai neveiksmīgo API izsaukumu apkopojumiem, tostarp to iznākumam, avota sistēmai un citiem noderīgiem metadatiem.    
  Papildinformāciju skatiet [Reāllaika darbplūsmu lietošana](real-time-data-ingestion.md).

- **Reāllaika datu pieņemšana: profila atjauninājumi**

  Šī reāllaika datu pieņemšanas paplašinājums ļauj dažu sekunžu laikā redzēt izmaiņas noteiktos lietotāja profila laukos.    
  Papildus reāllaika darbību funkcionalitātei sistēma atbalsta zema latentuma atjauninājumus profilu laukiem. Reāllaika profila lauku atjauninājumiem ir beigu laiks, un tāpēc ar tiem netiek aizstāti plānotās atsvaidzināšanas darbības.    
  Papildinformāciju skatiet [Reāllaika darbplūsmu lietošana](real-time-data-ingestion.md).

#### <a name="extensibility"></a>Paplašināmība

- **Atjaunināta laika skala un lapu numerācija klienta kartes pievienojumprogrammā**

  Klientu karšu pievienojumprogrammas grafiks atbilst darbības laika skalai. Ir uzlabota laika skalas lapu numerācija, kas rāda līdz 50 darbībām vienlaicīgi. Tas arī ļauj ielādēt vairāk darbību laika grafikā.    
  Papildinformācijai skatiet [Klientu kartes pievienojumprogramma](customer-card-add-in.md).

- **Power Automate segmenta izmaiņu trigeris**

  Trigeri programmai Power Automate definē, no kā var izveidot plūsmu. Tikko pievienotais trigeris ļauj definēt segmenta slieksni. Piemēram, varat izveidot paziņojumu, kas tiek nosūtīts, kad ir pārsniegts definētais slieksnis.    
  Papildinformācijai skatiet [Power Automate savienotājs](export-power-automate.md).

- **Vairāku nomnieku atbalsts pielāgotiem modeļiem**

  Konfigurējiet darbplūsmas pielāgotiem modeļiem, izmantojot tīmekļa pakalpojumu, kurā ir cits Azure algoritmiskās mācīšanās nomnieks. Jūs varat pieteikties Azure algoritmiskās mācīšanās nomniekā, izveidojot jaunu darbplūsmu pielāgotajiem modeļiem. Šī iespēja ir papildinājums pastāvošajai integrēšanas iespējai ar savu pielāgoto Azure algoritmiskās mācīšanās tīmekļa pakalpojumu.    
  Papildinformācijai skatiet [Pielāgoti algoritmiskās mācīšanās modeļi](custom-models.md).

#### <a name="segments"></a>Segmenti

- **Entītijas ceļa automatizācija**

  Veidojot segmentu, lietotājiem ir jādefinē entītijas ceļš. Šīs iespējas veic pirmo soli, lai automatizētu entītijas ceļa definīciju, tāpēc varat koncentrēties uz jūsu iecerētajiem segmentācijas kritērijiem.    
  Ja entītija, ar kuru vēlaties segmentēt klientus, ir tieši saistīta ar vienoto klienta entītiju, tad entītijas ceļš vairs nav jādefinē. Tomēr, ja ir vairāk nekā viens iespējamais entītijas ceļš, to joprojām ir nepieciešams definēt manuāli.

- **Darbības ar vairākiem segmentiem**
  
  Lietotāji var atlasīt vairākus segmentus un veikt darbības ar tiem ar vienu klikšķi, piemēram, atjaunojot segmentus.    

- **Atsvaidzināt segmentus**

  Lietotāji var atsvaidzināt atsevišķu segmentu vai atlasīt tikai tos segmentus, ko vēlas atsvaidzināt.    

  
- **Saliktu segmentu uzlabojumi**

  Lietotāji var izveidot, rediģēt un dzēst segmentus, kas ir balstīti uz citiem segmentiem. Piemēram, segments, kas būvēts citā segmentā, kurš tika būvēts uz trešā segmenta.    

- **Segmentu saraksta lapa**

  Segmentu lapas jaunajā noformējumā tiek izmantots saraksta formāts, kas ļauj vienlaikus apskatīt vairākus segmentus. Ir pievienots meklēšanas lauks, lai ātri atrastu segmentus. Tagad lietotāji var piemērot darbības, piemēram, lejupielādi vai dzēšanu vairākiem segmentiem vienlaikus. Tiek ieviesta jauna tendenču pieredze, lai ātri noteiktu segmentu būtiskās izmaiņas.    
  Papildinformācijai skatiet [Segmentu izveide un pārvaldība](segments.md).

#### <a name="system-administration"></a>Sistēmas administrēšana

- **Customer Insights, kas pieejams risinājumā Microsoft Dynamics 365 Online Government**

  Ar pieaugošu mijiedarbību kanālu skaitu pilsoņu dati ir izplatīti pa neskaitāmām sistēmām, kas noved pie sadalītiem datiem un sadrumstalota informācijas skata par iedzīvotāju mijiedarbību. Ja nav pilna skata par katras personas mijiedarbību visos kanālos, valdībām nav iespējams veikt modernizāciju mērogā. Microsoft ir apņēmusies atbalstīt valdību tehnoloģiskās vajadzības, lai tās atbilstu pilsoņu cerībām attiecībā uz konsekventu un atsaucīgu pieredzi.    
  Ar 2020. gada 1. laidienu Dynamics 365 Customer Insights būs pieejams pakalpojumam Government Community Cloud (GCC), vide, kas veidota, lai apmierinātu ASV valdības aģentūru augstākās atbilstības vajadzības. Aģentūras iegūst vienotu skatu par iedzīvotājiem un izmanto iepriekš iebūvētu mākslīgo intelektu (Al), lai gūtu ieskatus, kas uzlabo mijiedarbību, pilnvaro darbiniekus un transformē kopienas, vienlaikus samazinot IT sarežģītību un ievērojot ASV atbilstības un drošības standartus. Dynamics 365 Government atbilst stingrām prasībām ASV Federālajā riska un autorizācijas pārvaldības programmā (FedRAMP), kas ļauj ASV federālajām aģentūrām gūt labumu no izmaksu ietaupījumiem un Microsoft mākoņa stingru drošību.

## <a name="april-2020-updates"></a>2020. gada aprīļa atjauninājumi

2020. gada aprīļa atjauninājumi ietver vairākas funkcijas, veiktspējas jauninājumus, kā arī kļūdu labojumus.

### <a name="new-and-updated-features-in-april-2020"></a>Jaunas un atjauninātas funkcijas 2020. gada aprīlī

#### <a name="activities"></a>Darbības

- **Kartēt darbības entītiju uz standarta darbības tipu**
  
  Darbību konfigurēšana un glabāšana pašlaik balstās uz statisku noformējumu, lai tos skatītu laika skalā. To darbību semantiskā nozīme, kurām ir daudzkārtējas lietošanas potenciāls mākslīgā intelekta modeļos, pašlaik netiek pilnībā izmantota. Mēs plānojam padarīt darbības laika skalu dinamiskāku, pamatojoties uz darbības tipu un labāku semantisko izpratni par darbībām. Šīs funkcijas mērķis ir identificēt darbības tipu, kā definēts modulārā Common Data Model jebkurai pieņemtai darbībai.
  Papildinformācijai skatiet [Klientu darbības](activities.md).

#### <a name="data-ingestion"></a>Datu pieņemšana

- **Reāllaika datu pieņemšana: darbības**
  
  Reāllaika datu uzņemšana nodrošina tūlītēju datu patēriņu, kamēr turpmāk plānotā atsvaidzināšana izrauj šos datus no datu avota.    
  Papildinformāciju skatiet [Reāllaika darbplūsmu lietošana](real-time-data-ingestion.md).

- **Datu sagatavošanas uzlabojumi**
  
  Uzziniet vairāk par entītijā uzņemtajiem datiem. Izmantojot datu kopsavilkumu, varat izprast datu kvalitātes īpašības, kas var palīdzēt atbilstošas darbības veikšanai.    
  Papildinformācijai skatiet [Entītija datu izpēte](entities.md#exploring-a-specific-entitys-data).

- **Uzņemt analītiskos datus no Dynamics 365 ar Common Data Service**
  
  Common Data Service ir pieejams kā datu avotu izveides veids. Esošie Dynamics 365 klienti var uzņemt analītiskās entītijas no Common Data Service programmā Customer Insights. Ar vienu datu avotu var vienlaikus izmantot to pašu Common Data Service pārvaldīto ezeru Customer Insights vidē.    
  Papildinformācijai skatiet [Savienojuma izveide ar datiem Common Data Service pārvaldītajā datu ezerā](connect-common-data-service-lake.md).

#### <a name="extensibility"></a>Paplašināmība

- **Eksportēšana uz LiveRamp**

  Aktivizējiet datus risinājumā LiveRamp®, lai izveidotu savienojumu ar vairāk nekā 500 platformām digitālajās, sociālajās un TV ekosistēmās. Izmantojiet savus LiveRamp datus kā reklāmas kampaņu mērķauditorijas atlasei, likvidēšanai un personalizēšanai.    
  Papildinformācijai skatiet [LiveRamp&reg; connector](export-liveramp.md).

- **Customer Insights darba grupu pievienojumprogramma**
  
  Bots nodrošina uzmeklēšanas iespējas vienotiem klientu profiliem. Tajā tiks parādīta kartīte ar līdz pat 15 laukiem no iegūtā klienta profila. Vairākas atbilstības atgriež rezultātu sarakstu, kurā varat atlasīt profilu.    
  Papildinformācijai skatiet [Darba grupas robots programmai Customer Insights](export-teams-bot.md).

#### <a name="measures"></a>Mēri

- **Mēru saraksta lapa**
  
  Uzlabojumi mēru lapā ietver atbalstu darbībām ar vienu mēru un vairākiem mēriem vienlaikus. Turklāt ir pieejams meklēšanas lauks ātrai mēru atrašanai un izsekošanai.    
  Papildinformācijai skatiet [Segmentu izveide un pārvaldība](segments.md).

- **Saliktu mēru uzlabojumi**
  
  Lietotāji var izveidot, rediģēt un dzēst mērus, kas ir balstīti uz citiem mēriem. Piemēram, mērs, kas izveidots uz citā mēra, kurš tika izveidots uz trešā mēra.

#### <a name="segments"></a>Segmenti

- **Cits operators**
  
  Iestatītais operators atļauj segmentēt klientus pēc vairākām iespējamām virknes vērtībām. Pirms šī operatora pievienošanas, jums bija jāveido šādi segmenti, izmantojot vairākus nosacījumus VAI. Iestatītais operators ļauj to darīt ar vienu nosacījumu.    
  Papildinformācijai skatiet [Segmentu izveide un pārvaldība](segments.md).

#### <a name="system-administration"></a>Sistēmas administrēšana

- **Konfigurācijas iestatījumu kopēšana jaunā vidē**
  
  Kopējiet konfigurāciju no vienas vides citā. Veidojot jaunu vidi, varat atlasīt esošu vidi, no kuras vēlaties kopēt konfigurāciju. Pašlaik mēs atbalstām datu avotus, datu apvienošanu, attiecības, mērus un segmentus, kas tiks kopēti. Datu avots akreditācijas dati un faktiskie dati netiek kopēti.    
  Papildinformācijai skatiet [Vižu pārvaldība](manage-environments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]