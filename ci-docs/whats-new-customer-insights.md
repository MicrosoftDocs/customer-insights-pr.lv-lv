---
title: Dynamics 365 Customer Insights jaunumi
description: Informācija par jaunajiem līdzekļiem, uzlabojumiem un kļūdu labojumiem.
ms.date: 08/31/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: skumm
manager: shellyha
ms.openlocfilehash: acba06cba5fb5cbf0bca5aeb30b603003555fc32
ms.sourcegitcommit: 3ab8f1c0ba5874095a19f0b6367b9a4432f72ed1
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 09/06/2022
ms.locfileid: "9409366"
---
# <a name="whats-new-in-dynamics-365-customer-insights"></a>Dynamics 365 Customer Insights jaunumi

Ar prieku paziņojam par mūsu jaunākajiem atjauninājumiem! Šajā rakstā ir apkopotas publiskā priekšskatījuma funkcijas, vispārējie pieejamības uzlabojumi un funkciju atjauninājumi. Lai skatītu informāciju par ilgtermiņa plāniem attiecībā uz funkcijām, skatiet [Dynamics 365 un Power Platform laidienu plānus](/dynamics365/release-plans/).

Atjauninājumi tiek ieviesti katrā reģionā atsevišķi. Tāpēc noteikti reģioni var agrāk skatīt funkcijas nekā citi. Ja vien nav norādīts citādi, jums nav jāveic nekādas darbības, mēs automātiski atjaunināsim lietotni bez dīkstāves.

> [!TIP]
> Lai iesniegtu funkciju pieprasījumus un produktu ieteikumus, kā arī balsotu par tiem, dodieties uz [Dynamics 365 programmas ideju portālu](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).

## <a name="august-2022-updates"></a>2022. gada augusta atjauninājumi

2022. gada augusta atjauninājumi ietver jaunus līdzekļus, veiktspējas jauninājumus un kļūdu labojumus.

### <a name="contact-unification-in-b-to-b-environments"></a>Kontaktu apvienošana B-to-B vidē

B-to-B vides programmā Customer Insights tagad atbalsta uzlabotu datu apvienošanas pieredzi.

Tagad varat apvienot kontaktpersonas papildus kontiem, lai iegūtu pilnu pārskatu par savām biznesa kontaktpersonām. Vienotās kontaktpersonas ir saistītas ar vienotiem kontiem un tagad ir norādītas klientu kartītēs. 

Papildinformāciju skatiet sadaļā [Vienota kontaktpersonas profila izveide](data-unification-contacts.md).

### <a name="create-and-export-of-segments-based-on-unified-contacts"></a>Segmentu izveide un eksportēšana, pamatojoties uz vienotām kontaktpersonām

Pateicoties jaunajai kontaktpersonu apvienošanai, varat izveidot kontaktpersonu segmentus, izmantojot kritērijus no kontaktpersonām, kontiem vai abiem. Šos segmentus var eksportēt aktivizēšanai citos pakalpojumos.

Papildinformāciju skatiet rakstā [Pārskats par eksportu](export-destinations.md).

### <a name="deployment-regions-aligned-with-microsoft-dataverse"></a>Izvietošanas reģioni, kas saskaņoti ar Microsoft Dataverse

Veidojot jaunu Customer Insights vidi, varat atlasīt reģionu, kurā vēlaties, lai pakalpojums tiktu izvietots un viesots. Mēs esam atjauninājuši reģiona izvēli, lai saskaņotu ar Microsoft Dataverse un Power Platform.

Tagad varat viegli atlasīt to pašu reģionu, kurā atrodas jūsu esošā Microsoft Dataverse vide vai Azure Data Lake krātuves konts (ja izvēlaties šo opciju), atkarībā no Customer Insights pieejamības šajā reģionā.

Papildinformāciju skatiet sadaļā [Jaunas vides](create-environment.md) izveide un [Produktu pieejamība pēc ģeogrāfiskās atrašanās vietas](https://dynamics.microsoft.com/availability-reports/).

## <a name="july-2022-updates"></a>2022. gada jūlija atjauninājumi

2022. gada jūlija atjauninājumi ietver jaunus līdzekļus, veiktspējas jauninājumus un kļūdu labojumus.

### <a name="export-to-moengage"></a>Eksports uz MoEngage

Eksportējiet vienotu klientu profilu segmentus uz MoEngage un izmantojiet tos e-pasta mārketingam MoEngage.

Papildinformāciju skatiet sadaļā [Segmentu eksportēšana uz MoEngage](export-moengage.md).

### <a name="ssh-support-for-sftp-based-exports"></a>SSH atbalsts uz SFTP balstītai eksportēšanai

Izvēlieties, vai vēlaties autentificēties, izmantojot SSH vai lietotājvārdu/paroli, lai izveidotu savienojumus ar SFTP eksportēšanas galamērķiem.

Papildinformāciju skatiet sadaļā [Datu eksportēšana uz SFTP resursdatoriem](export-sftp.md).

### <a name="personalize-experiences-with-data-about-known-and-unknown-users"></a>Personalizējiet pieredzi ar datiem par zināmiem un nezināmiem lietotājiem

Klientu datu pārvaldība nav jauns izaicinājums, taču tas kļūst arvien grūtāk, jo lietotāji pārvietojas pa dažādiem digitālo kanālu zīmoliem. Lietotājs, kurš ir zināms (autentificēts) vienā kanālā, kļūst nezināms (neautentificēts) citā kanālā, ja tas nav pieteicies. Bieži problēma ir tā, ka neautentificētiem (nezināmiem) lietotājiem nav kopēja ID. To var izmantot, lai saistītu jēgpilnus profilu atribūtus un ģenerētu vienotus klientu profilus. Customer Insights palīdz atrisināt šo problēmu, uzņemot datus no izsekošanas metodēm jūsu avota sistēmās.

Papildinformāciju skatiet rakstā [Pieredzes personalizēšana, izmantojot datus par zināmiem un nezināmiem lietotājiem](unknown-to-known.md).

## <a name="june-2022-updates"></a>2022. gada jūnija atjauninājumi

2022. gada jūnija atjauninājumi ietver jaunus līdzekļus, veiktspējas jauninājumus un kļūdu labojumus.

### <a name="updated-user-experience-for-data-sources-and-data-ingestion"></a>Atjaunināta lietotāja pieredze datu avotos un datu uzņemšanā

Datu importēšana no plaša datu avotu klāsta ir pamats klientu datu konsolidēšanai .Dynamics 365 Customer Insights Mēs esam pārskatījuši lietotāju pieredzi datu avotu importēšanai un savienošanai. Šī atjauninājuma mērķis ir atvieglot customer insights datu uzņemšanu.

Papildinformāciju skatiet sadaļā [Datu avotu pārskats](data-sources.md).

### <a name="export-to-inmobi"></a>Eksports uz InMobi

InMobi palīdz zīmoliem izprast, identificēt, iesaistīt un iegūt patērētājus. Segmentus un citus datus varat eksportēt uz pakalpojumu InMobi, izmantojot Azure Blob krātuves kontus.

Papildinformāciju skatiet rakstā [Eksportēšana uz InMobi (priekšskatījums)](export-inmobi.md)

### <a name="lockbox-support-in-customer-insights"></a>Lockbox atbalsts programmā Customer Insights

Klientu bloķēšanas lodziņš nodrošina saskarni, lai pārskatītu un apstiprinātu (vai noraidītu) datu piekļuves pieprasījumus. Šie pieprasījumi rodas, ja ir nepieciešama piekļuve datiem klientu datiem, lai atrisinātu atbalsta pieteikumu.

Papildinformāciju skatiet sadaļā [Droša piekļuve klientu datiem, izmantojot klientu bloķēšanas lodziņu (priekšskatījums)](security-overview.md#securely-access-customer-data-with-customer-lockbox-preview).

### <a name="connect-to-your-data-using-azure-private-link"></a>Savienojuma izveide ar datiem, izmantojot Azure Private Link

Azure Private Link ļauj Customer Insights izveidot savienojumu ar jūsu Azure Data Lake Storage kontu, izmantojot privātu galapunktu jūsu virtuālajā tīklā. Datiem krātuves kontā, kas nav atvērts publiskajam internetam, Private Link iespējo savienojumu ar šo ierobežoto tīklu.

Papildinformāciju skatiet sadaļā [Privātās saites izmantošana programmā Customer Insights](security-overview.md#set-up-an-azure-private-link).

## <a name="may-2022-updates"></a>2022. gada maija atjauninājumi

2022. gada maija atjauninājumi ietver jaunus līdzekļus, veiktspējas jauninājumus un kļūdu labojumus.

### <a name="updated-data-unification-experience"></a>Atjaunināta datu apvienošanas pieredze

 Datu apvienošana ļauj apvienot vienreiz atšķirīgus datu avotus vienā datu pamatkopā, kas nodrošina vienotu skatu uz šiem datiem. Datus var apvienot vienā entītijā vai vairākās entītijās. Vispirms atlasiet [entītijas un avota laukus](map-entities.md), [noņemiet ierakstu](remove-duplicates.md) dublikātus, norādiet kārtulas atbilstošiem nosacījumiem [un](match-entities.md) definējiet, kurus [laukus iekļaut vienotajos klientu profilos](merge-entities.md).

Papildinformāciju skatiet sadaļā [Datu apvienošanas pārskats](data-unification.md).

### <a name="refreshed-home-page-in-customer-insights"></a>Atsvaidzināta sākumlapa programmā Customer Insights

**Sākums** palīdz veikt galveno līdzekļu konfigurācijas procesu un sniedz pārskatu par segmentiem, mēriem un bagātināšanas datiem. Mēs esam atsvaidzinājuši pieredzi, lai acumirklī sniegtu atbilstošāku informāciju.

Papildinformāciju skatiet sadaļā [Klientu ieskatu izpēte](home.md).

### <a name="track-usage-of-a-segment"></a>Segmenta lietojuma izsekošana

Tagad [varat izsekot segmenta](segments.md#track-usage-of-a-segment) lietojumam programmās, kuru pamatā Dataverse ir organizācija, kas ir saistīta ar Customer Insights. Customer [Insights segmentiem, kas tiek izmantoti Dynamics 365 Marketing](/dynamics365/marketing/real-time-marketing-ci-profile) automatizētajās kampaņās, sistēma informē jūs par šī segmenta lietojumu.

### <a name="export-to-criteo"></a>Eksports uz Criteo

Criteo ir tiešsaistes platforma, kas palīdz lietotājiem pārvaldīt digitālo reklāmu. Tagad varat eksportēt vienotu klientu profilu segmentus, lai ģenerētu kampaņas, nodrošinātu e-pasta mārketingu un izmantotu noteiktas klientu grupas ar Criteo.

Papildinformāciju skatiet sadaļā [Segmentu eksportēšana uz Criteo (priekšskatījums)](export-criteo.md).

### <a name="refined-documentation-structure-for-environment-creation"></a>Uzlabota dokumentācijas struktūra vides izveidei

Mēs esam pārskatījuši palīdzības dokumentus, kas saistīti ar vides izveidi un pārvaldību programmā Customer Insights. Raksti tagad ir sagrupēti zem satura rādītāja mezgla Vides. Pārstrukturētie panti sniedz vairāk norādījumu par dažādiem veidiem, kā izveidot vidi un kam ir skaidrāka struktūra. Ja jums ir atsauksmes, ar kurām dalīties, informējiet mūs, izmantojot vadīklas palīdzības rakstu beigās.

Papildinformāciju skatiet sadaļā [Kā: izveidot jaunu vidi](create-environment.md).

## <a name="april-2022-updates"></a>2022. gada aprīļa atjauninājumi

2022. gada aprīļa atjauninājumi ietver jaunus līdzekļus, veiktspējas jauninājumus un kļūdu labojumus.

### <a name="dun--bradstreet-enrichment-preview"></a>Dun & Bradstreet bagātināšana (priekšskatījums)

Dun & Bradstreet nodrošina komerciālus datus, analītiku un ieskatus uzņēmumiem. Tā nodrošina klientiem vienotus klientu profilus, lai uzņēmumi bagātinātu datus. Bagātināšana ietver tādus atribūtus kā DUNS numurs, uzņēmuma lielums, atrašanās vieta, nozare un citi.

Papildinformāciju skatiet sadaļā [Uzņēmuma profilu bagātināšana, izmantojot Dun &Bradstreet (priekšskatījums)](enrichment-dnb.md).

### <a name="define-the-measure-type-when-creating-a-new-measure"></a>Mēra tipa definēšana, veidojot jaunu mēru

Tagad varat atšķirt pasākumus atsevišķiem profiliem un mēriem visā jūsu uzņēmumā. Lai gan biznesa pasākumi tiek rādīti Customer Insights sākumlapā, klientu mēri tiek parādīti detalizētos klientu skatos.

Papildinformāciju skatiet sadaļā [Mēru veidotāja izmantošana, lai izveidotu mērus no nulles](measure-builder.md).

### <a name="consolidation-of-customer-insights-documentation"></a>Customer Insights dokumentācijas konsolidācija

Mēs esam pārskatījuši savus dokumentācijas rakstus un noņēmuši pieminējumus par iesaistes ieskatiem un auditorijas ieskatu iespējām. Virzoties uz priekšu, mēs konsekventi atsauksimies uz produkta nosaukumu Customer Insights, kad rakstīsim par lietojumprogrammas pamatfunkcijām. Šīs izmaiņas arī noved pie būtiska satura rādītāja, URL struktūras un failu ceļu pārstrukturēšanas pamatā esošajā dokumentācijas repozitorijā. Visas jūsu grāmatzīmes vai esošās saites turpina darboties un novirzīt uz atjauninātajiem vietrāžiem URL.

Ja vēlaties mūs informēt par to, kā jūs uztverat šīs izmaiņas, vai pamanāt, ka kaut kas nedarbojas, kā paredzēts, pastāstiet mums [, iesniedzot atsauksmes par šo lapu](https://github.com/MicrosoftDocs/customer-insights/issues/new?title=&body=%0A%0A%5BEnter%20feedback%20here%5D%0A%0A%0A---%0A%23%23%23%23%20Document%20Details%0A%0A%E2%9A%A0%20*Do%20not%20edit%20this%20section.%20It%20is%20required%20for%20docs.microsoft.com%20%E2%9E%9F%20GitHub%20issue%20linking.*%0A%0A*%20ID%3A%20d323ba46-f96e-1972-bc52-9b88f7d9cdfa%0A*%20Version%20Independent%20ID%3A%20d323ba46-f96e-1972-bc52-9b88f7d9cdfa%0A*%20Content%3A%20%5BNew%20and%20upcoming%20features%20-%20Dynamics%20365%20Customer%20Insights%5D(https%3A%2F%2Fdocs.microsoft.com%2Fen-us%2Fdynamics365%2Fcustomer-insights%2Fwhats-new-customer-insights)%0A*%20Content%20Source%3A%20%5Bci-docs%2Fwhats-new-customer-insights.md%5D(https%3A%2F%2Fgithub.com%2FMicrosoftDocs%2Fcustomer-insights%2Fblob%2Fmain%2Fci-docs%2Fwhats-new-customer-insights.md)%0A*%20Service%3A%20**customer-insights**%0A*%20Sub-service%3A%20**audience-insights**%0A*%20GitHub%20Login%3A%20%40m-hartmann%0A*%20Microsoft%20Alias%3A%20**mhart**).

## <a name="march-2022-updates"></a>Atjauninājumi 2022. gada martā

2022. gada marta atjauninājumi ietver jaunus līdzekļus, veiktspējas uzlabojumus un kļūdu labojumus.

### <a name="liveramp-abilitec-enrichment-preview"></a>LiveRamp AbiliTec bagātināšana (priekšskatījums)

LiveRamp nodrošina identitātes izšķirtspēju un klientu datu konsolidāciju. Jūs varat kartēt personiskos identifikatorus savos klientu datos uz AbiliTec identitātes diagrammu un saņemt AbiliTec ID. Pēc tam varat izmantot šos ID, lai labāk apvienotu savus klientu datus.

Papildinformāciju skatiet rakstā [Klientu profilu bagātināšana, izmantojot identitātes datus no LiveRamp (priekšskatījums)](enrichment-liveramp.md).

### <a name="organize-segments-and-measures-with-tags-and-filters"></a>Segmentu un mēru kārtošana, izmantojot atzīmes un filtrus

Ja jūsu organizācija uztur daudz segmentu vai pasākumu, pareizā atrašana dažreiz var šķist sarežģīta. Šis jaunais līdzeklis ļauj kārtot sarakstus, izmantojot atzīmes un kolonnas. Tas palīdz ātri un viegli atrast datus un pielāgot skatus.

Papildinformāciju skatiet rakstā [Darbs ar tagiem un kolonnām](work-with-tags-columns.md).

### <a name="enable-data-sharing-with-dataverse-when-using-your-own-storage-account"></a>Datu koplietošanas iespējošana, Dataverse izmantojot savu krātuves kontu

Ja jūsu vide tiek izmantota Azure Data Lake Storage Customer Insights datu glabāšanai, datu kopīgošanai ar Microsoft Dataverse papildu konfigurāciju ir nepieciešama papildu konfigurācija.
Agrāk jūs varējāt iespējot datu kopīgošanu tikai ar Dataverse laiku, kad jūsu dati tika glabāti mūsu pārvaldīto datu ezerā.

Papildinformāciju skatiet sadaļā [Datu koplietošanas iespējošana ar Dataverse savu Azure Data Lake Storage (Priekšskatījums)](customer-insights-dataverse.md#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview).

### <a name="new-export-destinations-iterable-and-braze"></a>Jauni eksporta galamērķi: Iterable un Braze

Mēs turpinām paplašināt savu eksporta galamērķu ekosistēmu ar jauniem savienojumiem. Tagad varat eksportēt segmentus uz Iterable un Braze, lai izmantotu to aktivizācijas pakalpojumus.

Papildinformāciju skatiet sadaļā [Segmentu eksportēšana uz iterable (priekšskatījums)](export-iterable.md) un [Segmentu eksportēšana uz Braze (priekšskatījums)](export-braze.md).

### <a name="improvements-to-marketo-and-google-ads-export"></a>Marketo un Google Ads eksporta uzlabojumi

Mainot API saistītajos pakalpojumos, tiek atjaunināti savienotāji, lai tie darbotos uzticami un nevainojami. Esam izlaiduši dažus atjauninājumus eksportēšanai uz Marketo un Google Ads pakalpojumiem.

- Google Ads: Google Ads eksportēšanas savienotāja jaunā versija vienkāršo autentifikācijas iespējas un tagad ļauj automātiski izveidot jaunas Google Ads mērķauditorijas. 
- Marketo: Jaunā Marketo eksporta savienotāja versija nodrošina Atbalstu Marketo ID, ļaujot izvairīties no datu dublēšanās, atjaunināt esošos ierakstus un izveidot jaunus ierakstus Marketo. 

## <a name="february-2022-updates"></a>2022. gada februāra atjauninājumi

2022. gada februāra atjauninājumi ietver jaunus līdzekļus, veiktspējas jauninājumus un kļūdu labojumus.

### <a name="general-availability-for-prediction-models"></a>Vispārēja pieejamība prognoze modeļiem

Iebūvētie prognoze modeļi, tostarp **abonēšanas zuduma**, **transakciju zuduma** un **klienta mūža vērtības (CLV),** kļūst vispārēji pieejami kā daļa no Customer Insights. 

Papildinformāciju skatiet sadaļā [Prognozes pārskats](predictions-overview.md).

### <a name="new-data-source-integration-with-azure-synapse-analytics-preview"></a>Jauns datu avots: integrācija ar Azure Synapse Analytics (Priekšskatījums)

Azure Synapse Analytics ir uzņēmuma analīzes pakalpojums, kas paātrina laiku līdz ieskatiem datu noliktavās un lielo datu sistēmās.

Organizācijas, kas jau izmanto Azure Synapse Analytics, var nodot šos datus programmā Customer Insights. 

Papildinformāciju [skatiet sadaļā Azure Synapse datu avots savienošana (priekšskatījums)](connect-synapse.md).

### <a name="liveramp-enrichment-preview"></a>LiveRamp bagātināšana (priekšskatījums)

LiveRamp nodrošina identitātes izšķirtspēju un klientu datu konsolidāciju. Jūs varat kartēt personiskos identifikatorus savos klientu datos uz AbiliTec identitātes diagrammu un saņemt AbiliTec ID. Pēc tam varat izmantot šos ID, lai labāk apvienotu savus klientu datus.

Papildinformāciju skatiet rakstā [Klientu profilu bagātināšana, izmantojot identitātes datus no LiveRamp (priekšskatījums)](enrichment-liveramp.md).

### <a name="enrichment-for-data-sources-preview"></a>Datu avotu bagātināšana (priekšskatījums)

Izmantojiet datus no tādiem avotiem kā Microsoft un citi partneri, lai bagātinātu klientu datus pirms datu apvienošanas. Datu avots bagātināšana palīdz radīt augstāku datu pilnīgumu un kvalitāti, kas var palīdzēt sasniegt labākus rezultātus, kad esat apvienojis savus datus.

Papildinformāciju skatiet sadaļā [Datu avotu bagātināšana (priekšskatījums)](data-sources-enrichment.md).

### <a name="change-owner-of-environment"></a>Mainīt vides īpašnieku

Lai gan vairākiem lietotājiem var būt administratora atļaujas programmā Customer Insights, tikai viens lietotājs ir vides īpašnieks. Uzlabota pieredze ļauj mainīt vides īpašniekus un pieprasīt īpašumtiesības, ja bijušais īpašnieks pameta organizāciju. 

Papildinformāciju skatiet sadaļā [Vides īpašnieka maiņa](manage-environments.md#change-the-owner-of-an-environment).

### <a name="data-preparation-process-lists-corruption-reason-for-corrupted-records"></a>Datu sagatavošanas procesā ir norādīts bojātu ierakstu korupcijas iemesls

Datu sagatavošana tagad parāda korupcijas iemeslu visiem laukiem ar bojātiem datiem. Informācija tiek sniegta individuālā ieraksta līmenī, lai to varētu viegli identificēt. 

Papildinformāciju skatiet sadaļā [Bojāti datu avoti](entities.md#corrupted-data-sources).

### <a name="end-of-preview-for-reporting-features-in-the-engagement-insights-capability"></a>Priekšskatījuma beigas atskaišu veidošanas līdzekļiem iesaistes ieskatu iespējā

Iesaistes Dynamics 365 Customer Insights ieskatu iespēju priekšskatījums beidzās 2022. gada 15. februārī.  
Šīs izmaiņas nozīmē, ka Customer Insights izmēģinājumversijas pieredze vairs neietver iespēju izveidot piltuves vai citu atskaišu veidošanas funkcionalitāti.

Mēs aicinām jūs izpētīt un novērtēt daudzus citus Customer Insights [līdzekļus](https://dynamics.microsoft.com/ai/customer-insights/), kas ir Microsoft klientu datu platforma (CDP).    
 
Pārejas periodā esošajiem priekšskatījuma dalībniekiem joprojām ir piekļuve dažām priekšskatījuma iespējām un funkcionalitātei:

- Iegūstiet kodu, lai rīkotos tīmekļa vietnē vai mobilajā programma 
- Skatīt notikumus un notikumu rekvizītus 
- Uzlabojiet vienotus profilus ar uzņemtiem un izsmalcinātiem notikumiem, lai gūtu labumu no klientu datu pilnas vērtības
  
Pārejas periodā uzņemtie notikumi joprojām tiek straumēti uz savienoto Datu ezeru. Kad šī funkcionalitāte ir izslēgta, datu kopīgošana tiks pārtraukta, un uz pievienoto krātuvi netiks nosūtīti jauni notikumi.
Sazinieties tieši ar savu Microsoft konta komandu, ja jums ir jautājumi par iespēju priekšskatījuma beigām. Jūsu konta komanda informēs jūs par jaunumiem nākamajās palaišanas reizēs. 

## <a name="january-2022-updates"></a>2022. gada janvāra atjauninājumi

2022. gada janvāra atjauninājumi ietver jaunus līdzekļus, veiktspējas uzlabojumus un kļūdu labojumus.

### <a name="sentiment-analysis-of-your-customers-feedback"></a>Klienta atsauksmju noskaņojuma analīze

Customer Insights nodrošina jaunu AI darbinātu funkciju, lai sintezētu klientu noskaņojumu un identificētu konkrētus biznesa aspektus kā mērķtiecīgu uzlabojumu iespējas. Analizējot klientu rakstiskās atsauksmes, jūs varat gūt precīzus ieskatus par zemām izmaksām. Noskaņojuma analīze, ko nodrošina dabiskās valodas apstrādes (NLP) modeļi, kas ģenerē divus atvasinātus ieskatus katram klienta ID. Noskaņojuma rādītājs (no –5 līdz 5) un piemērojamo uzņēmējdarbības aspektu saraksts. 

Papildinformāciju skatiet rakstā [Noskaņojuma analīze klientu atsauksmēs (Priekšskatījums)](sentiment-analysis.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]