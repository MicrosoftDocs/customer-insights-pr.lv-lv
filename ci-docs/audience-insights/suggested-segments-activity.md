---
title: Uz darbībām balstīti segmenta ieteikumi.
description: Ļaujiet algoritmiskā mācīšanās jums palīdzēt atrast jaunus un aizraujošus segmentus, kas balstīti uz klientu darbību.
ms.date: 05/11/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
searchScope:
- ci-segment-suggestions
- customerInsights
ms.openlocfilehash: 9c10a32b770ea110a1166f20f72116a3a12cb92e
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 02/25/2022
ms.locfileid: "8354472"
---
# <a name="suggested-segments-based-on-activity-data-preview"></a>Uz darbībām balstīti segmenta ieteikumi (priekšskatījums)

Atklājiet jūsu klientus interesējošos segmentus, balstoties uz klientu darbību datiem, kuri tiek lietoti ar Customer Insights. Darbību dati ir, piemēram, transakcijas, atbalsta sarunas ilgums, iegāde vai atgriešana. Lai ieteiktu segmentus, darbības dati tiek analizēti, lai noteiktu atkārtojamību, biežumu un naudas vērtību (vai ilgumu). Vai arī var ģenerēt [ieteiktos segmentus, lai uzlabotu pasākumu vai labāk saprastu atribūta ietekmi](suggested-segments.md).

:::image type="content" source="media/suggested-segments-tab.png" alt-text="Cilne Ieteicamie segmenti, kurā parādīti segmenta ieteikumi uz darbībām un atribūtiem balstītiem segmentiem.":::

## <a name="categorize-customers-by-activity"></a>Kategorizēt klientus pēc darbības

Izmantojot [darbības datus](activities.md), kas pieejami programmā Customer Insights, mēs varam ģenerēt ieteikumus, kas attiecas uz klientu grupām:

- visaktīvākie klienti 
- klineti, kas visvairāk iepirkušies 
- klienti, kas ģenerēja vislielākos ieņēmumus 
- klienti, kas pēdējā laikā nav bijuši aktīvi 
- klienti, kas bieži mijiedarbojas ar uzņēmumu  

Ja jums ir mazumtirdzniecības uzņēmums, varat uzzināt, kuri klienti rada visvairāk ieņēmumu, un apbalvot viņus ar sīcēju. Varat arī identificēt gadījuma klientus un piedāvāt viņiem pievienoties apbalvojumu programmai, lai viņi biežāk apmeklētu jūsu uzņēmumu.
Ja jūs esat veselības aprūpes uzņēmums, kas sniedz publisku veselības aprūpi un jūsu mērķis ir minimizēt atsevišķas sasācības izmaksas. Veids, kā to izdarīt, varētu būt samazināt periodisko vizīti, pēc iespējas nodrošinot pēc iespējas labāko rūpību pēc iespējas dažos apmeklējumos. Šajā gadījumā jūsu mērķis ir uzturēt zemu apmeklējuma biežumu un minimizēt periodiskās izmaksas attiecībā uz jutīgajām vietām. Vai arī varat identificēt ar klientiem saistītas problēmas, kam bieži ir tikšanās un augstas periodiskās izmaksas, un analizēt šos pieteikumus, lai uzlabotu indivīda uzlabošanos. 

## <a name="required-data"></a>Nepieciešamie dati

Ieteikumi tiek ģenerēti, pamatojoties uz atlasītajiem ievades datiem. 

- Klientu profili: visi noteikta segmenta klienti vai dalībnieki. 

- Laika periods: pagājušais mēnesis, pēdējais gads vai jebkurš pielāgots laika posms.

- Darbības tips: pirkumi, mazumtirdzniecības transakcijas, tiešsaistes transakcijas, klientu atbalsta pieteikumi, abonementi utt.  

- Entītija programmā Customer Insights, kurā ir darbības dati: noteiktas darbības entītija vai UnifiedActivity entītija. 

- Atkarībā no jūsu uzņēmējdarbības prasībām tajā iekļaujams: resns, biežums vai naudas izteiksmē.

## <a name="generate-suggested-segments"></a>Izveidot ieteiktos segmentus

1. Ejiet uz **Segmenti**.

1. Atlasiet cilni **Ieteikumi (priekšskatījums)**.

1. Atlasiet **Atrast jaunus ieteikumus** un izvēlieties **Skatīt vai paredzēt klientu uzvedību**. Atlasiet vienumu **Sākt**, lai palaistu vadīto pieredzi.

   :::image type="content" source="media/suggested-segments-activity-wizard.png" alt-text="Konfigurēšanas vedņa pirmais solis ieteiktam segmentam, pamatojoties uz darbību.":::

1. Norādiet nepieciešamos ievades datus un atlasiet **Tālāk**.

   - Izvēlieties klientus: iekļaujiet visus klientus vai noteiktu segmentu.
   - Izvēlieties darbību: atlasiet darbības tipu un entītijas, kas apraksta darbību.
   - Preferences: iestatiet apsveramo laika periodu, ieteikumu faktorus un kartējiet atribūtus.

1. Pārskatiet savu ievadi un atlasiet opciju **Palaist**, lai palaistu modeli un ģenerētu ieteikumus.

1. Atkarībā no klientu profilu un atlasīto darbību skaita pabeigšana var ilgt dažas minūtes. 

Pēc ieteikumu ģenerēšanas tos varat filtrēt pēc kategoriju kategorijas vai vērtības, kas jūs interesē visvairāk. 

## <a name="view-details-of-a-suggested-segment"></a>Ieteicamā segmenta detalizētas informācijas skatīšana

Kad ieteikumi ir ģenerēti, tie ir uzskaitīti sadaļā **Segmenti** > **Ieteikumi (priekšskatījums)** **Uz darbībām balstīti ieteikumi**.

:::image type="content" source="media/suggested-segments-details.png" alt-text="Izvērsta sānu rūts, kurā ir detalizēti ieteiktā segmenta dati.":::

Lai skatītu detalizētu informāciju par šo segmentu, atlasiet vienumu **Skatīt ierosinājumu** par ieteikto segmentu. Sānu rūtī ir sniegta detalizēta informācija, piemēram, cik lielā mērā katrs aspekts ir salīdzināts ar mērķa grupu. Turklāt tiek izcelts arī segmentā iespējamo dalībnieku skaits un atbilstošā klientu kopsummas procentuālā vērtība. Ja ierosinājumu vēlaties saglabāt kā segmentu, atlasiet opciju **Izveidot segmentu**.    

## <a name="save-a-suggestion-as-a-segment"></a>Ieteikuma saglabāšana par segmentu

1. Dodieties uz **Segmenti** > **Ieteikumi (priekšskatījums)**.

1. Atlasiet saglabājamo segmentu. 

1. Sānu rūtī atlasiet **Izveidot segmentu**. 

1. Pēc segmenta saglabāšanas tas tiks rādīts segmentu sarakstā cilnē **Visi segmenti**. Tagad to var [atsvaidzināt vai dzēst, piemēram, kā jebkuru citu segmentu](segments.md). Segmenta detalizēto informāciju nevar rediģēt. Tomēr varat mainīt ieteikumu ievades kritērijus un ģenerēt dažādus ieteikumus.

## <a name="refresh-or-edit-a-set-of-suggestions"></a>Ieteikumu kopas atsvaidzināšana vai rediģēšana

1. Dodieties uz **Segmenti** > **Ieteikumi (priekšskatījums)** un meklējiet segmentu sadaļā **Uz darbībām balstīti ieteikumi**.

1. Atlasiet **Atsvaidzināt ieteikumus**, lai atsvaidzinātu ieteikumus, saglabājot konfigurētos atribūtus. Vai atlasiet vienumu **Rediģēt ieteikumus**, lai modificētu konfigurētos atribūtus. Sistēma procesu no jauna palaidiet vēlreiz, ģenerējiet segmenta ieteikumus, pamatojoties uz jaunākajiem datiem, un aizstās pašreizējos ieteikumus.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
