---
title: Ieteiktie segmenti, kuru pamatā ir darbība (priekšskatījums)
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
ms.openlocfilehash: df4f5f4b5c9a3ad66d57a6b349e18a0d714aff62
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170598"
---
# <a name="suggested-segments-based-on-activity-preview"></a>Ieteiktie segmenti, kuru pamatā ir darbība (priekšskatījums)

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
Ja jūs sniedzat valsts veselības aprūpi un jūsu mērķis ir samazināt izdevumus atsevišķiem pacientiem, jūs varētu mēģināt samazināt atkārtotus apmeklējumus, nodrošinot vislabāko iespējamo aprūpi pēc iespējas mazāk apmeklējumu. Šajā gadījumā jūsu mērķis ir uzturēt zemu apmeklējuma biežumu un minimizēt periodiskās izmaksas attiecībā uz jutīgajām vietām. Vai arī varat identificēt ar klientiem saistītas problēmas, kam bieži ir tikšanās un augstas periodiskās izmaksas, un analizēt šos pieteikumus, lai uzlabotu indivīda uzlabošanos.

## <a name="required-data"></a>Nepieciešamie dati

Ieteikumi tiek ģenerēti, pamatojoties uz atlasītajiem ievades datiem.

- Klientu profili: visi noteikta segmenta klienti vai dalībnieki.

- Laika periods: pagājušais mēnesis, pēdējais gads vai jebkurš pielāgots laika posms.

- Darbības tips: pirkumi, mazumtirdzniecības transakcijas, tiešsaistes transakcijas, klientu atbalsta pieteikumi, abonementi utt.  

- Entītija programmā Customer Insights, kurā ir darbības dati: noteiktas darbības entītija vai UnifiedActivity entītija.

- Atkarībā no jūsu uzņēmējdarbības prasībām tajā iekļaujams: resns, biežums vai naudas izteiksmē.

## <a name="generate-suggested-segments"></a>Izveidot ieteiktos segmentus

1. Dodieties uz **Segmenti** un atlasiet **cilni Ieteikumi (priekšskatījums**).

1. Atlasiet **Atrast jaunus ieteikumus** un izvēlieties **Skatīt vai paredzēt klientu uzvedību**. Atlasiet **Sākums**.

   :::image type="content" source="media/suggested-segments-activity-wizard.png" alt-text="Konfigurēšanas vedņa pirmais solis ieteiktam segmentam, pamatojoties uz darbību.":::

1. Norādiet nepieciešamos ievades datus un atlasiet **Tālāk**.

   - Izvēlieties klientus: iekļaujiet visus klientus vai noteiktu segmentu.
   - Izvēlieties darbību: atlasiet darbības tipu un entītijas, kas apraksta darbību.
   - Preferences: iestatiet apsveramo laika periodu, ieteikumu faktorus un kartējiet atribūtus.

1. Pārskatiet savu ievadi un atlasiet opciju **Palaist**, lai palaistu modeli un ģenerētu ieteikumus.

Atkarībā no klientu profilu un atlasīto darbību skaita pabeigšana var ilgt dažas minūtes.

Pēc ieteikumu ģenerēšanas tos varat filtrēt pēc kategoriju kategorijas vai vērtības, kas jūs interesē visvairāk.

## <a name="manage-suggested-segments"></a>Ieteikto segmentu pārvaldība

Dodieties uz **Segmenti** un atlasiet **cilni Ieteikumi (priekšskatījums**). **Sadaļā Uz darbībām balstīti ieteikumi** atlasiet ieteikto segmentu, lai skatītu pieejamās darbības.

- **Skatiet ieteikumu skatīt šī** segmenta informāciju, piemēram, katras dimensijas apmēru salīdzinājumā ar mērķa grupu. Turklāt tiek izcelts arī segmentā iespējamo dalībnieku skaits un atbilstošā klientu kopsummas procentuālā vērtība.
- **Izveidojiet segmentu**, lai ieteikto saglabātu kā segmentu. Tas tiek rādīts **cilnē Visi segmenti**, un to var [atsvaidzināt vai izdzēst](segments.md). Segmenta detalizēto informāciju nevar rediģēt. Tomēr varat mainīt ieteikumu ievades kritērijus un ģenerēt dažādus ieteikumus.
- **Rediģējiet ieteikumus**, lai modificētu konfigurētos atribūtus, kas aizstās pašreizējos ieteikumus.
- **Atsvaidziniet ieteikumus**, lai atsvaidzinātu ieteikumus, vienlaikus saglabājot konfigurētos atribūtus.

[!INCLUDE [footer-include](includes/footer-banner.md)]
