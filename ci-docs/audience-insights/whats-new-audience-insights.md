---
title: Jaunie un gaidāmie līdzekļi
description: Informācija par jaunajiem līdzekļiem, uzlabojumiem un kļūdu labojumiem.
ms.date: 05/06/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: midevane
manager: shellyha
ms.openlocfilehash: c66b37d6e4d6ed830238566fbc09934832892b34
ms.sourcegitcommit: 3f9981df97fa7b1f432a446d3f11936ea4cfbde5
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 05/06/2021
ms.locfileid: "5988929"
---
# <a name="whats-new-in-the-audience-insights-capability-of-dynamics-365-customer-insights"></a>Jaunumi klausītāju ieskatiem Dynamics 365 Customer Insights iespējās

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Ar prieku paziņojam par mūsu jaunākajiem atjauninājumiem! Šajā rakstā ir apkopotas publiskā priekšskatījuma funkcijas, vispārējie pieejamības uzlabojumi un funkciju atjauninājumi. Lai skatītu informāciju par ilgtermiņa plāniem attiecībā uz funkcijām, skatiet [Dynamics 365 un Power Platform laidienu plānus](/dynamics365/release-plans/).

Atjauninājumi tiek ieviesti katrā reģionā atsevišķi. Tāpēc noteikti reģioni var agrāk skatīt funkcijas nekā citi. Ja vien nav norādīts citādi, neveiciet nekādu darbību, un programma automātiski atjauninās programmu bez jebkādas dīkstāves.

> [!TIP]
> Lai iesniegtu funkciju pieprasījumus un produktu ieteikumus, kā arī balsotu par tiem, dodieties uz [Dynamics 365 programmas ideju portālu](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).

## <a name="april-2021-updates"></a>2021. gada aprīļa atjauninājumi

2021. gada aprīļa atjauninājumi ietver vairākus līdzekļus, veiktspējas uzlabojumus un kļūdu labojumus.

### <a name="data-unification"></a>Datu apvienošana
 
- **Uzlabotas sapludināšanas iespējas datu apvienošanai**    
  
   Tagad mums ir uzlabota lietotāja pieredze datu unificēšanas procesa sapludināšanas konfigurācijā. Izmaiņas ir, piemēram, intuitīva sapludināto lauku pasūtīšana un detalizēta statistika par kombinētajiem un vientulības laukiem.

- **Entītijas pārkārtošana un visu avota ierakstu konfigurēšana klienta entītijā**  
      
   Tagad datu unificēšanas procesā varat pārkārtot un noņemt entītijas no esoša kodulēšanas plāna. Tas sniedz elastīgas iespējas pārkārtot entītijas atbilstības procesā atbilstoši uzņēmuma vajadzībām. Turklāt mēs iespējojam visus ar atbilstību nesaistīto ierakstu iekļautas gala *klienta* entītijā, kas viņiem ļauj definēt klienta profila datu kopas definīciju.

### <a name="enrichments"></a>Bagātinājumi

 - **Jauna bagātināšana: Paplašinātās adreses**    
  
   Ar prieku iepazīstināsim ar jaunu bagātinājumu, lai uzlabotu klientu datu adreses. Datu adreses var būt nestrukturētas, nepilnīgas vai nepareizas. Šī opcija izmanto Microsoft modeļus, lai normalizētu un bagātinātu adreses Common Data Model formātā, lai iegūtu labāku precizitāti un ieskatus.
 
   Papildinformāciju skatiet sadaļā [Klientu profilu bagātināšana ar paplašinātām adresēm](enrichment-enhanced-addresses.md).

- **Vadītā konfigurēšanas pieredze bagātinājumiem**    
  
   Ar vienkāršu vadīto pieredzi mēs pārskatījām bagātināto darbu konfigurācijas pieredzi. Tagad ir skaidrs, pakāpeniski process, kurā veidot un rediģēt bagātinātos produktus.
 
   Turklāt mēs nodalījām savienojumu konfigurāciju trešo pušu bagātinātajiem daļām, lai vienu un to pašu savienojumu varētu izmantot vairāki bagātinātie savienojumi. Jaunus savienojumu drīkst konfigurēt tikai administratori, taču izveidotie savienojumi vienmēr ir pieejami gan administratoriem, gan līdzstrādniekiem.    

   Papildinformāciju skatiet tēmā [Pārskats par savienojumiem](connections.md).

- **Vairāki viena veida bagātinātie dati**    
  
   Tagad mēs ļaujam lietotājiem izveidot un pārvaldīt vairākus viena bagātināšanas tipa bagātinājumus. Piemēram, tagad varat izveidot divus atsevišķus adrešu bagātinājumus, lai bagātinātu divus dažādus klientu segmentus. Ierobežojumi attiecas uz to, cik daudz bagātinātā tipa var izveidot un kā tie atšķiras atkarībā no bagātināšanas tipa.
  
   Papildinformāciju skatiet tēmā [Klientu profilu bagātināšana](enrichment-hub.md).

## <a name="march-2021-updates"></a>Atjauninājumi 2021. gada martā

2021. gada marta atjauninājumi ietver vairākus līdzekļus, veiktspējas uzlabojumus un kļūdu labojumus.

### <a name="activities"></a>Darbības

- **Darbību vednis un semantiskie tipi**

   Esam uzlabojuši un atjauninājuši savu darbību kartēšanu, lai vadītu un vienkāršotu darbību kartēšanas izveidi. Šajā jaunajā iespējā lietotāji var izmantot vadību, kas viņiem palīdzēs izpildīt katru procesa darbību. Darbību kartēšanas darbībā, līdztekus izvēlei no vairākiem darbību veidiem, lietotājs var izvēlēties semantiski kartēt *Abonementa* un/vai *SalesOrderLine* datus, uz nozares standarta shēmām, kuras var izmantot patēriņa lejupstraumei.   

   Papildinformācijai skatiet [Klientu darbības](activities.md).

### <a name="data-ingestion"></a>Datu pieņemšana

- **Pieslēdzieties lokālajiem datu avotiem, izmantojot Power Platform datu plūsmas un vārtejas** Ar prieku izziņojam priekšskatījumu Power Platform datu plūsmām un lokālo savienojamību Customer Insights vārtejām ar saistīto Power Platform vai Dataverse vidi. Visi jaunie datu avoti, kas izveidoti Customer Insights vidē ar saistīto Dataverse vidi, pēc noklusējuma kļūs par Power Platform datu plūsmām, radot lokālo datu savienojamību un bagātīgu savienotāju un pārveides iespēju klāstu.

### <a name="extensibility"></a>Paplašināšana

- **Savienojumos un eksportos organizētie eksporti** Mēs esam nomainījuši **Eksporta galamērķu** lapas nosaukumu uz **Savienojumi** un **Eksportiem** pievienojuši atsevišķu lapu. Šī atjauninājuma ietvaros mēs pārvirzīsim esošos eksportus uz savienojuma pāriem un eksportēsim, izmantojot šo savienojumu. Tagad administratoriem ir vairāk skaidrības par lapā **Savienojumi** izejošajiem datiem. Visām lietotāju lomām ir piekļuve  **Eksportu** lapai, taču vienīgi administratori var izvēlēties atļaut līdzstrādniekiem rediģēt konkrētus eksportus ar kopīgotiem savienojumiem.     
  Papildinformāciju skatiet sadaļā [Savienojumu pārskats](connections.md) un [Eksportēšanas pārskats](export-destinations.md).

- **Segmentu eksportēšana uz Campaign Monitor** Esam paplašinājuši mūsu eksportēšanas galamērķus, un tie ietver Campaign Monitor. Tagad varat eksportēt segmentus no Customer Insights uz Campaign Monitor sarakstiem un tos izmantot kā bāzlīnijas savās mārketinga kampaņās.    
   Papildinformāciju skatiet tēmā [Datu eksportēšana uz Campaign Monitor](export-campaign-monitor.md).

- **Segmentu eksportēšana uz Constant Contact** Esam paplašinājuši mūsu eksportēšanas galamērķus, un tie ietver Constant Contact. Tagad varat eksportēt segmentus no Customer Insights uz Constant Contact sarakstiem un tos izmantot kā bāzlīnijas savās mārketinga kampaņās.   
   Papildinformāciju skatiet tēmā [Datu eksportēšana uz Constant Contact](export-constant-contact.md).

- **Segmentu eksportēšana uz RollWorks** Esam paplašinājuši mūsu eksportēšanas galamērķus, un tie ietver RollWorks. Tagad varat eksportēt segmentus no Customer Insights uz RollWorks auditorijām un tos izmantot kā bāzlīnijas savās B2B reklāmu aktivitātēs.    
   Papildinformāciju skatiet tēmā [Eksportēšana uz RollWorks](export-rollworks.md).

- **Segmentu eksportēšana uz Snapchat** Esam paplašinājuši mūsu eksportēšanas galamērķus, un tie ietver Snapchat. Tagad varat eksportēt segmentus no Customer Insights uz Snapchat auditorijām un tos izmantot kā bāzlīnijas savās reklāmu aktivitātēs.     
   Papildinformāciju skatiet tēmā [Eksportēšana uz Snapchat](export-snapchat.md).

### <a name="predictions"></a>Prognozes

- **Produktu filtru lietošana predikatīvajā produktu ieteikšanā** Esam pievienojuši iespēju izmantot produktu filtrus jūsu produktu ieteikumu modelī. Tagad varat izveidot prognozi, kura izmanto vienīgi jūsu produktu apakškopu.    
   Papildinformāciju skatiet sadaļā [Produktu filtru konfigurēšana](predict-product-recommendation.md#configure-product-filters).

- **Segmentu izveide no modeļa prognozēm** Esam pievienojuši ātru veidu, kādā varat izveidot segmentus, izmantojot prognozes modeļa rezultātus. No modeļa rezultātu lapas varat viegli izveidot jaunu segmentu, atlasot opciju **Segmenta izveide**.    
  Papildinformāciju skatiet rakstā [Segmenta izveide, pamatojoties prognozes modelī](prediction-based-segment.md).

- **Produktu ieteikumu skaidrojumi** Esam pievienojuši informāciju, kurā paskaidroti galvenie AI modeļa apgūtie faktori produktu ieteikumu ģenerēšanai un pakāpe, līdz kurai šie faktori var ietekmēt produktu ieteikumus. Šī informācija tiek pievienota modeļa rezultātu ekrānam.    
   Papildinformāciju skatiet rakstā [Prognozes statusa un rezultātu pārskatīšana](predict-product-recommendation.md#review-a-prediction-status-and-results).

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




[!INCLUDE[footer-include](../includes/footer-banner.md)]