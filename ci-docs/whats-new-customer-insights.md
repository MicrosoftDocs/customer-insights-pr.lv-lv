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
ms.openlocfilehash: 25c6e2897d836854408871b2c74afa16ecba7435
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643729"
---
# <a name="whats-new-in-dynamics-365-customer-insights"></a>Dynamics 365 Customer Insights jaunumi

Ar prieku paziņojam par mūsu jaunākajiem atjauninājumiem! Šajā rakstā ir apkopotas publiskā priekšskatījuma funkcijas, vispārējie pieejamības uzlabojumi un funkciju atjauninājumi. Lai skatītu informāciju par ilgtermiņa plāniem attiecībā uz funkcijām, skatiet [Dynamics 365 un Power Platform laidienu plānus](/dynamics365/release-plans/).

Atjauninājumi tiek ieviesti katrā reģionā atsevišķi. Tāpēc noteikti reģioni var agrāk skatīt funkcijas nekā citi. Ja vien nav norādīts citādi, neveiciet nekādu darbību, un programma automātiski atjauninās programmu bez jebkādas dīkstāves.

> [!TIP]
> Lai iesniegtu funkciju pieprasījumus un produktu ieteikumus, kā arī balsotu par tiem, dodieties uz [Dynamics 365 programmas ideju portālu](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).


## <a name="march-2022-updates"></a>Atjauninājumi 2022. gada martā

Atjauninājumi 2022. gada martā ietver jaunas funkcijas, veiktspējas jauninājumus un kļūdu labojumus.

### <a name="liveramp-abilitec-enrichment-preview"></a>LiveRamp AbiliTec bagātināšana (Preview)

LiveRamp nodrošina identitātes izšķirtspēju un klientu datu konsolidāciju. Klienta datu personiskos identifikatorus varat kartēt uz AbiliTec identitātes grafiku un saņemt AbiliTec ID. Pēc tam varat izmantot šos ID, lai labāk apvienotu klientu datus.

Papildinformāciju skatiet rakstā [Klientu profilu bagātināšana ar LiveRamp (Preview) identitātes datiem](enrichment-liveramp.md).

### <a name="organize-segments-and-measures-with-tags-and-filters"></a>Segmentu un pasākumu organizēšana, izmantojot atzīmes un filtrus
Ja jūsu organizācija uztur daudz segmentu vai pasākumu, pareizā atrašana dažkārt var justies izaicinoša. Šis jaunais līdzeklis ļauj kārtot sarakstus, izmantojot atzīmes un kolonnas. Tas palīdz ātri un viegli atrast datus un pielāgot skatus.

Papildinformāciju skatiet rakstā [Darbs ar atzīmēm un kolonnām](work-with-tags-columns.md).

### <a name="enable-data-sharing-with-dataverse-when-using-your-own-storage-account"></a>Datu kopīgošanas iespējošana, Dataverse izmantojot savu krātuves kontu

Ja jūsu vide izmanto Customer Insights Azure Data Lake Storage datu glabāšanai, datu kopīgošanai ir Microsoft Dataverse nepieciešama papildu konfigurācija.
Agrāk jūs varējāt iespējot datu kopīgošanu tikai tad Dataverse, kad jūsu dati tika glabāti mūsu pārvaldītajā datu ezerā. 

Papildinformāciju skatiet rakstā [Datu kopīgošanas iespējošana ar Dataverse savu Azure Data Lake Storage (Priekšskatījums)](manage-environments.md#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview).

### <a name="new-export-destinations-iterable-and-braze"></a>Jauni eksporta galamērķi: Iterable un Braze

Mēs turpinām paplašināt savu eksporta galamērķu ekosistēmu ar jauniem savienojumiem. Tagad varat eksportēt segmentus uz Iterable un Braze, lai izmantotu to aktivizācijas pakalpojumus.

Papildinformāciju skatiet rakstā [Segmentu eksportēšana uz Iterable (priekšskatījums)](export-iterable.md) un [Segmentu eksportēšana uz Braze (priekšskatījums)](export-braze.md).

### <a name="improvements-to-marketo-and-google-ads-export"></a>Uzlabojumi Marketo un Google Ads eksportā

Mainot API saistītajos pakalpojumos, tiek panākts, ka savienotāji darbojas droši un nevainojami. Mēs esam izlaiduši dažus atjauninājumus eksportam uz Marketo un Google Ads pakalpojumiem.

- Google Ads: Jaunā Google Ads eksporta savienotāja versija vienkāršo autentifikācijas pieredzi un tagad ļauj automātiski izveidot jaunas Google Ads auditorijas. 
- Marketo: Jaunā Marketo eksporta savienotāja versija nodrošina Marketo ID atbalstu, ļaujot izvairīties no datu dublēšanās, atjaunināt esošos ierakstus un izveidot jaunus ierakstus Marketo. 


## <a name="february-2022-updates"></a>2022. gada februāra atjauninājumi

Atjauninājumi 2022. gada februārī ietver jaunas funkcijas, veiktspējas jauninājumus un kļūdu labojumus.

### <a name="general-availability-for-prediction-models"></a>Prognoze modeļu vispārējā pieejamība

Gatavās prognoze modeļi, tostarp **abonēšanas izmaksas,** transakciju kritums **un** **klienta mūža vērtība (CLV),** kļūst vispārēji pieejami kā daļa no Customer Insights. 

Plašāku informāciju skatiet [Prognožu pārskats](predictions-overview.md).

### <a name="new-data-source-integration-with-azure-synapse-analytics-preview"></a>Jauns datu avots: integrācija ar Azure Synapse Analytics (Priekšskatījums)

Azure Synapse Analytics ir uzņēmuma analītikas pakalpojums, kas paātrina laiku, lai gūtu ieskatu datu noliktavās un lielo datu sistēmās.

Organizācijas, kas jau izmanto Azure Synapse Analytics, var uzņemt šos datus Customer Insights. 

Papildinformāciju skatiet rakstā [Azure Synapse datu avots savienošana (priekšskatījums)](connect-synapse.md).

### <a name="liveramp-enrichment-preview"></a>LiveRamp bagātināšana (Priekšskatījums)

LiveRamp nodrošina identitātes izšķirtspēju un klientu datu konsolidāciju. Klienta datu personiskos identifikatorus varat kartēt uz AbiliTec identitātes grafiku un saņemt AbiliTec ID. Pēc tam varat izmantot šos ID, lai labāk apvienotu klientu datus.

Papildinformāciju skatiet rakstā [Klientu profilu bagātināšana ar LiveRamp (Preview) identitātes datiem](enrichment-liveramp.md).

### <a name="enrichment-for-data-sources-preview"></a>Datu avotu bagātināšana (priekšskatījums)

Izmantojiet datus no tādiem avotiem kā Microsoft un citi partneri, lai bagātinātu klientu datus pirms datu apvienošanas. Datu avots bagātināšana palīdz radīt augstāku datu pilnīgumu un kvalitāti, kas var palīdzēt sasniegt labākus rezultātus pēc datu apvienošanas.

Papildinformāciju skatiet rakstā [Datu avotu bagātināšana (Priekšskatījums)](data-sources-enrichment.md).

### <a name="change-owner-of-environment"></a>Mainīt vides īpašnieku

Lai gan vairākiem lietotājiem programmā Customer Insights var būt administratora atļaujas, tikai viens lietotājs ir vides īpašnieks. Uzlabota pieredze ļauj mainīt vides īpašniekus un pieprasīt īpašumtiesības, ja bijušais īpašnieks pamet organizāciju. 

Papildinformāciju skatiet rakstā [Vides](manage-environments.md#change-the-owner-of-an-environment) īpašnieka maiņa.

### <a name="data-preparation-process-lists-corruption-reason-for-corrupted-records"></a>Datu sagatavošanas procesā ir uzskaitīts bojātu ierakstu korupcijas iemesls

Datu sagatavošana tagad parāda korupcijas iemeslu visiem laukiem ar bojātiem datiem. Informācija tiek sniegta individuālā ieraksta līmenī, lai to varētu viegli identificēt. 

Papildinformāciju skatiet sadaļā [Bojāti datu avoti](entities.md#corrupted-data-sources).

### <a name="end-of-preview-for-reporting-features-in-the-engagement-insights-capability"></a>Atskaišu izveides līdzekļu priekšskatījuma beigas iesaistes ieskatu iespējā

Iesaistes Dynamics 365 Customer Insights ieskatu iespēju priekšskatījums beidzās 2022. gada 15. februārī.  
Šīs izmaiņas nozīmē, ka Customer Insights izmēģinājuma pieredze vairs neietver iespēju izveidot piltuves vai citu atskaišu izveides funkcionalitāti.

Mēs aicinām jūs izpētīt un novērtēt daudzus citus [Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/) līdzekļus, Microsoft klientu datu platformu (CDP).    
 
Pārejas periodā esošajiem priekšskatījuma dalībniekiem joprojām ir pieejamas dažas priekšskatījuma iespējas un funkcionalitāte:

- Iegūstiet kodu, lai rīkotos tīmekļa vietnē vai mobilajā programma 
- Notikumu un notikumu rekvizītu skatīšana 
- Uzlabojiet vienotos profilus ar uzņemtiem un uzlabotiem notikumiem, lai gūtu labumu no klientu datu pilnas vērtības
  
Pārejas periodā uzņemtie notikumi joprojām tiek straumēti uz savienoto Datu ezeru. Kad šī funkcionalitāte ir izslēgta, datu kopīgošana tiks pārtraukta un uz savienoto krātuvi netiks nosūtīti jauni notikumi.
Ja jums ir jautājumi par iespēju priekšskatījuma beigām, sazinieties tieši ar savu Microsoft konta komandu. Jūsu konta komanda jūs informēs par nākamajām palaišanām. 

## <a name="january-2022-updates"></a>2022. gada janvāra atjauninājumi

Atjauninājumi 2022. gada janvārī ietver jaunas funkcijas, veiktspējas jauninājumus un kļūdu labojumus.

### <a name="sentiment-analysis-of-your-customers-feedback"></a>Klienta atsauksmju sentimenta analīze

Customer Insights nodrošina jaunu mi darbinātu funkciju, lai sintezētu klientu noskaņojumu un identificētu konkrētus biznesa aspektus kā mērķtiecīgu uzlabojumu iespējas. Analizējot savu klientu rakstiskās atsauksmes, jūs varat iegūt precīzus ieskatus par zemām izmaksām. Sentimenta analīze, ko nodrošina dabiskās valodas apstrādes (NLP) modeļi, kas ģenerē divus atvasinātus ieskatus katram klienta ID. Noskaņojuma rādītājs (no –5 līdz 5) un piemērojamo uzņēmējdarbības aspektu saraksts. 

Papildinformāciju skatiet rakstā [Noskaņojuma analīze klientu atsauksmēs (Priekšskatījums)](sentiment-analysis.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]