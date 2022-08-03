---
title: Ieteiktie segmenti, kuru pamatā ir mēri (priekšskatījums)
description: Ļaujiet algoritmiskajai mācīšanās palīdzēt atrast jaunus un aizraujošus segmentus, balstoties uz klientu atribūtiem.
ms.date: 10/15/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
searchScope:
- ci-segment-suggestions
- customerInsights
ms.openlocfilehash: e3f504827029afa12c65ec6f065a62606aaa823f
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170966"
---
# <a name="suggested-segments-based-on-measures-preview"></a>Ieteiktie segmenti, kuru pamatā ir mēri (priekšskatījums)

Ar mākslīgā intelekta modeļa palīdzību izpētiet jūsu klientu aizraujošos segmentus. Šis algoritmiskās mācīšanās līdzeklis piedāvā segmentus, pamatojoties uz pasākumiem vai klienta atribūtiem. Tas var palīdzēt uzlabot jūsu veiktspējas pamatrādītājus (KPI) vai labāk izprast atribūtu ietekmi citu atribūtu kontekstā.

> [!NOTE]
> Ieteikto segmentu funkcija izmanto automatizētus līdzekļus, lai novērtētu datus un veiktu prognozes, pamatojoties uz šiem datiem. Tāpēc to var izmantot kā profilēšanas metodi, jo šis termins ir definēts Vispārīgajā datu aizsardzības regulā ("VDAR"). Šī līdzekļa izmantošana datu apstrādāšanai var būt pakļauta VDAR vai citiem tiesību aktiem un noteikumiem. Jūs esat atbildīgs par to, ka jūsu Dynamics 365 Customer Insights lietojums, ieskaitot prognozes, atbilst visiem piemērojamiem likumiem un noteikumiem, ieskaitot likumus, kas attiecas uz privātumu, personas datiem, biometrijas datiem, datu aizsardzību un saziņas konfidencialitāti.

:::image type="content" source="media/suggested-segments.png" alt-text="Ieteicamo segmentu lapa, kurā ir redzama detalizēta informācija par ierosinājumu sānu rūtī.":::

## <a name="suggested-segments-to-improve-your-kpis"></a>Ieteicamie segmenti savu KPI uzlabošanai

Ja izmantojat [pasākumus, kas izveidoti](measures.md), lai palīdzētu izsekot KPI, izveidojiet segmentus, lai skatītu KPI ietekmi. Varat izmantot šo informāciju, lai rādītu ļoti mērķtiecīgu kampaņu.

Piemēram, jūs izsekojat pasākumu *TotalSpendPerCustomer*. Jūs kā uzņēmums vēlaties redzēt šo skaitli palielināmies. Izvēloties mēru kā primāro atribūtu, atlasiet atribūtus, kurus vēlaties novērtēt attiecībā uz ietekmi. Pieņemsim, *dalības līmenis*, *dalības periods* un *nodarbošanās*. Pēc tam Customer Insights var ieteikt segmentu, kurā ir informācija par to, kas visvairāk ietekmē konkrēto līdzekli. Piemēram, *Grāmatveži*, kas ir *Zelta* programmas dalībnieki un ir saistīti ar jūsu uzņēmumu *vismaz piecus gadus*, ir lielākie *TotalSpendPerCustomer* ietekmētāji. Katram ierosinājumam tiks parādīts prognozētais segmenta lielums. Šo informāciju var izmantot, lai izveidotu kampaņas mērķa auditorijām.

## <a name="understand-what-influences-a-customer-attribute"></a>Klienta atribūta ietekmes izpratne

Kā primāro atribūtu mērvienības vietā var izvēlēties klienta atribūtu. Pamatojoties uz jūsu izvēli attiecībā uz atribūtiem, mākslīgā intelekta modelis izveido ieteikumu sēriju, kas parāda, kā atlasītie atribūti ietekmē primāro atribūtu.

Piemēram, izvēlieties *Apbalvojumu dalībnieks (Jā/Nē)* kā primāro atribūtu. *Īpašums*, *Nodarbošanās* un *Atbalsta biļešu skaits* tiek iestatīti kā citi ietekmējošie atribūti. Mākslīgā intelekta modelis varētu ieteikt segmentus, kas norāda, ka pārsvarā IT speciālisti divu gadu laikā ir apbalvoti dalībnieki. Vēl viens ierosinājums varētu uzsvērt, ka grāmatveži, kuri ir nodarbināti vairāk nekā vienu gadu un kuriem ir mazāk nekā trīs atbalsta biļetes, ir apbalvoti dalībnieki.

## <a name="artificial-intelligence-usage"></a>Mākslīgā intelekta lietojums

Izmantojot primāro atribūtu un atribūtu inkubācijas atribūtus, lēmumu koka algoritms iesaka interesantus segmentus. Ieteikumi ir balstīti uz kārtulām vai struktūrām, kuras uztvēra mākslīgā intelekta algoritms. Ieteikumi tiek rādīti tikai segmentos, kas būtiski atšķiras no vidējā rādītāja. Salīdzinājums ar vidējo rādītāju ir balstīts uz atlasīto pasākumu vai primāro atribūtu.

### <a name="responsible-ai"></a>Atbildīgais AI

Izmantojot ieteiktos segmentus, jūs atlasāt atribūtus, lai izveidotu jaunus segmentus un apstrādātu atlasītos datus. Izvēloties atribūtus, tostarp sensitīvus atribūtus, piemēram, rasi, seksuālo orientāciju vai dzimumu, jums ir jānodrošina, ka varat un apņematies apstrādāt šos datus. Jūs esat atbildīgs par to, lai nodrošinātu atbilstību visiem jūsu organizācijai piemērojamajiem tiesību aktiem un ievērotu organizācijas principus un konfidencialitātes politikas.

### <a name="different-results-for-primary-attributes-with-categorical-and-numeric-values"></a>Dažādi rezultāti primārajiem atribūtiem ar primārām un skaitliskām vērtībām

Segmenta ieteikumi atšķiras, ja kā primāro atribūtu izvēlaties skaitlisku atribūtu vai kategorijas atribūtu. Kategorijas atribūta vērtības satur divu vai vairāku veidu kategorijas. Skaitlisks atribūts ietver ar to saistītus kvantitatīvos datus, un tam ir ar to saistītās mērvienības.

Ja kā primārais atribūts ir skaitlisks atribūts, piemēram, *gada ienākumi* vai *dalības periods*, sistēma iesaka segmentus, kuru skaitliskā atribūta vidējā vērtība ir augstāka vai mazāka salīdzinājumā ar visiem klientiem.

Ja kā primārais atribūts ieteiktajos segmentos ir kategorijas atribūts, piemēram, *klientu apmierinājums*, kam ir noteiktai kategorijai piederošu klientu procentuāla vērtība vai lielāka procentuālā vērtība, salīdzinot ar visu ar šo kategoriju piederošo klientu procentuālo vērtību. Piemēram, kā primārais atribūts tiek izvēlēta *klientu apmierinātība*, un tas sastāv no trim kategorijām (*Zems*, *Vidējs* un *Augsts*). Katrai kategorijai tiks ieteikti segmenti, kuros ir lielāks vai mazāks klientu īpatsvars, kas pieder pie šīs kategorijas, salīdzinot ar visu vienas kategorijas klientu īpatsvaru. Ja 22% no visiem klientiem ir *Augsts* apmierinātības līmenis, šajā kategorijā tiks piedāvāti tikai segmenti, kuros ir lielāka vai mazāka klientu daļa ar *Augstu* apmierinātību salīdzinājumā ar 22%. Līdzīgi arī segmenti tiek ieteikti katrai citai kategorijai (*Zems* un *Vidējs*), ja tie ir statistiski svarīgi.

> [!NOTE]
> Pašlaik mēs sniedzam atbalstu tikai primārajiem kategorijas atribūtiem, kuriem ir līdz 10 kategorijām. Ja vēlaties skatīt segmentu ieteikumus, kuru pamatā ir primārais atribūts ar vairāk nekā 10 kategorijām, ieteicams grupēt dažas kategorijas, lai samazinātu kategoriju skaitu līdz 10 vai mazāk. Šis ierobežojums attiecas tikai uz primārajiem atribūtiem. Pašlaik mēs sniedzam atbalstu ne vairāk kā 100 kategorijām, lai ietekmētu kategorijas atribūtus.

## <a name="generate-suggested-segments"></a>Izveidot ieteiktos segmentus

1. Dodieties uz **Segmenti** un atlasiet **cilni Ieteikumi (priekšskatījums**).

1. Atlasiet **Atrast jaunus ieteikumus** un izvēlieties **Uzlabot mēru/metriku**. Atlasiet **Sākums**.

   :::image type="content" source="media/suggested-segments-measure.png" alt-text="Izvēloties uzlabot mēru ieteiktajos segmentos.":::

1. Izvēlieties klienta atribūtu vai mēru kā primāro atribūtu un atlasiet **Tālāk**.

1. Atlasiet ietekmējošos atribūtus un atlasiet **Palaist**.

   > [!TIP]
   > Atlasot vairākus ietekmējošos atribūtus uzlabo izredzes novērtēt, kā tie ietekmē primāro atribūtu. Neiekļaujiet atribūtus, kas neietekmē primāro atribūtu. Piemēram, ja visi jūsu klienti ir no konkrētas valsts, neietveriet *valsts* atribūtu, jo tas neietekmēs izvadi.

Atkarībā no klientu profilu un atlasīto atribūtu skaita atlasīto atribūtu apstrāde var ilgt dažas minūtes.

## <a name="manage-suggested-segments"></a>Ieteikto segmentu pārvaldība

Dodieties uz **Segmenti** un atlasiet **cilni Ieteikumi (priekšskatījums**). **Sadaļā Uz atribūtiem balstīti segmentu ieteikumi** atlasiet ieteikto segmentu, lai skatītu pieejamās darbības.

- **Skatiet** ieteikto segmenta informāciju un atribūtu vērtības vai kārtulas, ko iemācījās AI modelis.
- **Saglabājiet kā segmentu** ieteikumu kā segmentu. Tas tiek rādīts **cilnē Visi segmenti**, un to var [atsvaidzināt, rediģēt vai dzēst](segments.md).
- **Rediģējiet atribūtus** un modificējiet konfigurētos atribūtus, kas aizstās pašreizējos ieteikumus.
- **Atsvaidziniet ieteikumus**, lai atsvaidzinātu ieteikumus, vienlaikus saglabājot konfigurētos atribūtus.

## <a name="limitations"></a>Ierobežojumi

1. Prognozētā segmenta lieluma neatbilstība: ja izvēlaties primāro atribūtu, kurā ir tukšas vērtības, tas var ietekmēt segmenta ieteikumu prognozēto segmenta lielumu. Saglabājot šādu segmentu, faktiskais segmenta lielums var atšķirties no sākotnējā novērtējuma.

2. Būla tipa primārie atribūti nedarbojas: pašlaik kā primārie atribūti tiek atbalstīti tikai virknes un skaitliskie datu tipi.

3. Ieteiktie segmenti nav pietiekami izplatīti: paturiet prātā, ka atlasītie atribūti un šo atribūtu vērtību sadale ietekmē rezultātus. Lai iegūtu atšķirīgus rezultātus, varat mainīt savus ietekmējošos atribūtus vai pat primāro atribūtu.

[!INCLUDE [footer-include](includes/footer-banner.md)]