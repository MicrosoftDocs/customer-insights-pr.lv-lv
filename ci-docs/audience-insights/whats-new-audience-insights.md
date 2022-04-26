---
title: Jaunie un gaidāmie līdzekļi
description: Informācija par jaunajiem līdzekļiem, uzlabojumiem un kļūdu labojumiem.
ms.date: 04/05/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: skumm
manager: shellyha
ms.openlocfilehash: 2f081306271a170cf3e250fc1a193cedb70aeec6
ms.sourcegitcommit: 0363559a1af7ae16da2a96b09d6a4a8a53a8cbb8
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 04/05/2022
ms.locfileid: "8547681"
---
# <a name="whats-new-in-the-audience-insights-capability-of-dynamics-365-customer-insights"></a>Jaunumi klausītāju ieskatiem Dynamics 365 Customer Insights iespējās

Ar prieku paziņojam par mūsu jaunākajiem atjauninājumiem! Šajā rakstā ir apkopotas publiskā priekšskatījuma funkcijas, vispārējie pieejamības uzlabojumi un funkciju atjauninājumi. Lai skatītu informāciju par ilgtermiņa plāniem attiecībā uz funkcijām, skatiet [Dynamics 365 un Power Platform laidienu plānus](/dynamics365/release-plans/).

Atjauninājumi tiek ieviesti katrā reģionā atsevišķi. Tāpēc noteikti reģioni var agrāk skatīt funkcijas nekā citi. Ja vien nav norādīts citādi, neveiciet nekādu darbību, un programma automātiski atjauninās programmu bez jebkādas dīkstāves.

> [!TIP]
> Lai iesniegtu funkciju pieprasījumus un produktu ieteikumus, kā arī balsotu par tiem, dodieties uz [Dynamics 365 programmas ideju portālu](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).


## <a name="march-2022-updates"></a>Atjauninājumi 2022. gada martā

Atjauninājumi 2022. gada martā ietver jaunus līdzekļus, veiktspējas uzlabojumus un kļūdu labojumus.

### <a name="liveramp-abilitec-enrichment-preview"></a>LiveRamp AbiliTec bagātināšana (Priekšskatījums)

LiveRamp nodrošina identitātes izšķirtspēju un klientu datu konsolidāciju. Jūs varat kartēt personas identifikatorus savos klienta datos uz AbiliTec identitātes grafiku un saņemt AbiliTec ID. Pēc tam varat izmantot šos ID, lai labāk unificētu klientu datus.

Papildinformāciju skatiet rakstā [Klientu profilu bagātināšana ar identitātes datiem no LiveRamp (Preview)](enrichment-liveramp.md).

### <a name="organize-segments-and-measures-with-tags-and-filters"></a>Segmentu un mēru organizēšana ar atzīmēm un filtriem
Ja jūsu organizācija uztur daudz segmentu vai pasākumu, atrast pareizo dažreiz var justies izaicinoši. Šis jaunais līdzeklis ļauj organizēt sarakstus, izmantojot atzīmes un kolonnas. Tas palīdz ātri un viegli atrast datus un pielāgot skatus.

Papildinformāciju skatiet rakstā [Darbs ar atzīmēm un kolonnām](work-with-tags-columns.md).

### <a name="enable-data-sharing-with-dataverse-when-using-your-own-storage-account"></a>Iespējot datu koplietošanu, Dataverse izmantojot savu krātuves kontu

Ja jūsu vide izmanto Azure Data Lake Storage Customer Insights datu glabāšanai, datu koplietošana ar Microsoft Dataverse nepieciešamajām papildu konfigurācijām.
Agrāk jūs varējāt iespējot datu koplietošanu tikai tad Dataverse, kad jūsu dati tika glabāti mūsu pārvaldītajā datu ezerā. 

Papildinformāciju skatiet rakstā [Datu kopīgošanas iespējošana no Dataverse savas Azure Data Lake Storage (Priekšskatījums)](manage-environments.md#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview).

### <a name="new-export-destinations-iterable-and-braze"></a>Jauni eksporta galamērķi: Iterable un Braze

Mēs turpinām paplašināt savu eksporta galamērķu ekosistēmu ar jauniem savienojumiem. Tagad segmentus var eksportēt uz Iterable un Braze, lai izmantotu to aktivizācijas pakalpojumus.

Papildinformāciju skatiet rakstā [Segmentu eksportēšana uz Iterable (priekšskatījums)](export-iterable.md) un [Segmentu eksportēšana uz Braze (priekšskatījums)](export-braze.md).

### <a name="improvements-to-marketo-and-google-ads-export"></a>Uzlabojumi Marketo un Google Ads eksportā

MAINOT API savienotajos pakalpojumos, savienotāji tiek atjaunināti, lai tie darbotos uzticami un nevainojami. Mēs esam izlaiduši dažus atjauninājumus eksportam uz Marketo un Google Ads pakalpojumiem:

- Google Ads: jaunā Google Ads eksportēšanas savienotāja versija vienkāršo autentifikācijas pieredzi un tagad ļauj automātiski izveidot jaunas Google Ads mērķauditorijas. 
- Marketo: Marketo eksporta savienotāja jaunā versija nodrošina Marketo ID atbalstu, ļaujot izvairīties no datu dublēšanās, atjaunināt esošos ierakstus un izveidot jaunus ierakstus Marketo. 


## <a name="february-2022-updates"></a>2022. gada februāra atjauninājumi

Atjauninājumi 2022. gada februārī ietver jaunus līdzekļus, veiktspējas uzlabojumus un kļūdu labojumus.

### <a name="general-availability-for-prediction-models"></a>Prognoze modeļu vispārēja pieejamība

Kā daļa no Customer Insights parasti ir pieejami iebūvēti prognoze modeļi, **tostarp** abonēšanas čupa **, darījumu čupa** un **klientu mūža vērtība (CLV).** 

Plašāku informāciju skatiet [Predictions overview](predictions-overview.md).

### <a name="new-data-source-integration-with-azure-synapse-analytics-preview"></a>Jauns datu avots: integrācija ar Azure Synapse Analytics (Priekšskatījums)

Azure Synapse Analytics ir uzņēmuma analītikas pakalpojums, kas paātrina laiku, lai gūtu ieskatus datu noliktavās un lielo datu sistēmās.

Organizācijas, kas jau izmanto Azure Synapse Analytics, var uzņemt šos datus vietnē Customer Insights. 

Papildinformāciju skatiet rakstā [datu avots savienošana Azure Synapse (priekšskatījums)](connect-synapse.md).

### <a name="liveramp-enrichment-preview"></a>LiveRamp bagātināšana (Priekšskatījums)

LiveRamp nodrošina identitātes izšķirtspēju un klientu datu konsolidāciju. Jūs varat kartēt personas identifikatorus savos klienta datos uz AbiliTec identitātes grafiku un saņemt AbiliTec ID. Pēc tam varat izmantot šos ID, lai labāk unificētu klientu datus.

Papildinformāciju skatiet rakstā [Klientu profilu bagātināšana ar identitātes datiem no LiveRamp (Preview)](enrichment-liveramp.md).

### <a name="enrichment-for-data-sources-preview"></a>Datu avotu bagātināšana (Priekšskatījums)

Izmantojiet datus no tādiem avotiem kā Microsoft un citi partneri, lai bagātinātu klientu datus pirms datu apvienošanas. Datu avots bagātināšana palīdz nodrošināt augstāku datu pilnīgumu un kvalitāti, kas var palīdzēt sasniegt labākus rezultātus, kad jūs apvienojat savus datus.

Papildinformāciju skatiet rakstā [Datu avotu bagātināšana (Preview)](data-sources-enrichment.md).

### <a name="change-owner-of-environment"></a>Mainīt vides īpašnieku

Lai gan vairākiem lietotājiem programmā Customer Insights var būt administratora atļaujas, vides īpašnieks ir tikai viens lietotājs. Uzlabota pieredze ļauj mainīt vides īpašniekus un pieprasīt īpašumtiesības, ja bijušais īpašnieks atstāja organizāciju. 

Papildinformāciju skatiet rakstā [Vides](manage-environments.md#change-the-owner-of-an-environment) īpašnieka maiņa.

### <a name="data-preparation-process-lists-corruption-reason-for-corrupted-records"></a>Datu sagatavošanas procesā ir uzskaitīti bojāto ierakstu bojājuma iemesls

Datu sagatavošana tagad parāda bojājuma iemeslu visiem laukiem ar bojātiem datiem. Informācija tiek sniegta individuālā ierakstu līmenī, lai to varētu viegli identificēt. 

Papildinformāciju skatiet rakstā [Bojāti datu avoti](entities.md#corrupted-data-sources).

### <a name="end-of-preview-for-reporting-features-in-the-engagement-insights-capability"></a>Priekšskatījuma beigas atskaišu veidošanas līdzekļiem iesaistes ieskatu iespējā

Iesaistes Dynamics 365 Customer Insights ieskatu iespēju priekšskatījums beidzās 2022. gada 15. februārī.  
Šīs izmaiņas nozīmē, ka Customer Insights izmēģinājuma pieredze vairs neietver iespēju izveidot piltuves vai citu atskaišu funkcionalitāti.

Mēs aicinām jūs izpētīt un novērtēt daudzos citus Microsoft klientu datu platformas (CDP) [Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/) līdzekļus.    
 
Pārejas periodā esošajiem priekšskatījuma dalībniekiem joprojām ir piekļuve dažām priekšskatījuma iespējām un funkcionalitātei:

- Iegūstiet kodu, lai rīkotos tīmekļa vietnē vai mobilajā programma 
- Skatīt notikumus un pasākumu rekvizītus 
- Uzlabojiet vienotus profilus ar uzņemtiem un izsmalcinātiem notikumiem, lai gūtu labumu no to klientu datu pilnas vērtības
  
Pārejas periodā uzņemtie notikumi joprojām tiek straumēti uz savienoto Datu ezeru. Kad šī funkcionalitāte ir izslēgta, datu kopīgošana starp iesaistes ieskatiem un auditorijas ieskatiem tiks pārtraukta un uz savienoto krātuvi netiks nosūtīti jauni notikumi.
Ja jums ir jautājumi par iespēju priekšskatījuma beigām, sazinieties tieši ar Microsoft konta komandu. Jūsu konta komanda informēs jūs par nākamajām palaišanas reizēm. 

## <a name="january-2022-updates"></a>2022. gada janvāra atjauninājumi

2022. gada janvāra atjauninājumi ietver jaunus līdzekļus, veiktspējas uzlabojumus un kļūdu labojumus.

### <a name="sentiment-analysis-of-your-customers-feedback"></a>Jūsu klienta atsauksmju sentimenta analīze

Customer Insights nodrošina jaunu ar MI darbināmu funkciju, lai sintezētu klientu noskaņojumu un identificētu konkrētus biznesa aspektus kā iespējas mērķtiecīgiem uzlabojumiem. Analizējot klientu rakstiskās atsauksmes, jūs varat iegūt precīzus ieskatus par zemām izmaksām. Sentimenta analīze, ko darbina dabiskās valodas apstrādes (Natural Language Processing — NLP) modeļi, kas katram klienta ID rada divus iegūtus ieskatus. Sentimenta rādītājs (no –5 līdz 5) un piemērojamo biznesa aspektu saraksts. 

Papildinformāciju skatiet rakstā [Sentimenta analīze klientu atsauksmēs (Priekšskatījums)](sentiment-analysis.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]