---
title: Algoritmiskā mācīšanās nodrošinātie ieteiktie segmenti
description: Ļaujiet algoritmiskajai mācīšanās palīdzēt atrast jaunus un aizraujošus segmentus, balstoties uz klientu atribūtiem.
ms.date: 10/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
ms.openlocfilehash: 44e46bb650b6f090afcab3bc940d03a304e9c375
ms.sourcegitcommit: 31985755c7c973fb1eb540c52fd1451731d2bed2
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 10/22/2021
ms.locfileid: "7673192"
---
# <a name="suggested-segments-preview"></a>Ieteicamie segmenti (priekšskatījums)

Ar mākslīgā intelekta modeļa palīdzību izpētiet jūsu klientu aizraujošos segmentus. Šis algoritmiskās mācīšanās līdzeklis piedāvā segmentus, pamatojoties uz pasākumiem vai klienta atribūtiem. Tas var palīdzēt uzlabot KPI vai labāk izprast atribūtu ietekmi kontekstā ar citiem atribūtiem. 

> [!NOTE]
> Ieteikto segmentu līdzeklis izmanto automatizētus līdzekļus, lai novērtētu datus un uz šo datu bāzes padarītu aizsācošus, tādēļ šis līdzeklis var tikt izmantots kā profilēšanas metode, jo šo terminu definē Vispārējā datu aizsardzības regula (VDAR). Šī līdzekļa izmantošana datu apstrādāšanai var būt pakļauta VDAR vai citiem tiesību aktiem un noteikumiem. Jūs esat atbildīgs par to, ka jūsu Dynamics 365 Customer Insights lietojums, ieskaitot prognozes, atbilst visiem piemērojamiem likumiem un noteikumiem, ieskaitot likumus, kas attiecas uz privātumu, personas datiem, biometrijas datiem, datu aizsardzību un saziņas konfidencialitāti.

:::image type="content" source="media/suggested-segments.png" alt-text="Ieteicamo segmentu lapa, kurā ir redzama detalizēta informācija par ierosinājumu sānu rūtī.":::

## <a name="suggested-segments-to-improve-your-kpis"></a>Ieteicamie segmenti savu KPI uzlabošanai

Kā auditorijas ieskatu lietotājs, visticamāk, jums ir izveidoti vairāki [pasākumi](measures.md), kas palīdzēs sekot līdzi saviem izpildes pamatrādītājiem (Key Performance Indicators — KPI). Ir svarīgi saprast, kā noteikti atribūti ietekmē šo KPI, lai izveidotu segmentus un izpildītu īpaši mērķtiecīgu kampaņu.   
Piemēram, jūs izsekojat pasākumu *TotalSpendPerCustomer*. Jūs kā uzņēmums vēlaties redzēt šo skaitli palielināmies. Izvēloties pasākumu kā primāro atribūtu, varat atlasīt atribūtus, kuriem vēlaties novērtēt ietekmi. Pieņemsim, *dalības līmenis*, *dalības periods* un *nodarbošanās*. Pēc tam Customer Insights var ieteikt segmentu, kurā ir informācija par to, kas visvairāk ietekmē konkrēto līdzekli. Piemēram, *Grāmatveži*, kas ir *Zelta* programmas dalībnieki un ir saistīti ar jūsu uzņēmumu *vismaz piecus gadus*, ir lielākie *TotalSpendPerCustomer* ietekmētāji. Katram ierosinājumam tiks parādīts prognozētais segmenta lielums. Šo informāciju var izmantot, lai izveidotu kampaņas mērķa auditorijām.

## <a name="understand-what-influences-a-customer-attribute"></a>Klienta atribūta ietekmes izpratne

Kā primāro atribūtu mērvienības vietā var izvēlēties klienta atribūtu. Pamatojoties uz jūsu izvēli attiecībā uz atribūtiem, mākslīgā intelekta modelis izveido ieteikumu sēriju, kas parāda, kā atlasītie atribūti ietekmē primāro atribūtu.   
Piemēram, izvēlieties *Apbalvojumu dalībnieks (Jā/Nē)* kā primāro atribūtu. *Īpašums*, *Nodarbošanās* un *Atbalsta biļešu skaits* tiek iestatīti kā citi ietekmējošie atribūti. Mākslīgā intelekta modelis varētu ieteikt segmentus, kas norāda, ka pārsvarā IT speciālisti divu gadu laikā ir apbalvoti dalībnieki. Vēl viens ierosinājums varētu uzsvērt, ka grāmatveži, kuri ir nodarbināti vairāk nekā vienu gadu un kuriem ir mazāk nekā trīs atbalsta biļetes, ir apbalvoti dalībnieki. 

## <a name="artificial-intelligence-usage"></a>Mākslīgā intelekta lietojums

Izmantojot primāro atribūtu un atribūtu inkubācijas atribūtus, lēmumu koka algoritms iesaka interesantus segmentus. Ieteikumi ir balstīti uz kārtulām vai struktūrām, kuras uztvēra mākslīgā intelekta algoritms. Ieteikumi tiek rādīti tikai segmentos, kas būtiski atšķiras no vidējā rādītāja. Salīdzinājums ar vidējo rādītāju ir balstīts uz atlasīto pasākumu vai primāro atribūtu.

### <a name="responsible-ai"></a>Atbildīgais AI

Ieteiktie segmenti ļauj atlasīt atribūtus, lai izveidotu jaunus segmentus un apstrādātu jūsu atlasītus datus. Izvēloties atribūtus, tostarp sensitīvus atribūtus, piemēram, rasi, seksuālo orientāciju vai dzimumu, jums ir jānodrošina, ka varat un apņematies apstrādāt šos datus. Jūs esat atbildīgs par to, lai nodrošinātu atbilstību visiem jūsu organizācijai piemērojamajiem tiesību aktiem un ievērotu organizācijas principus un konfidencialitātes politikas.

### <a name="different-results-for-primary-attributes-with-categorical-and-numeric-values"></a>Dažādi rezultāti primārajiem atribūtiem ar primārām un skaitliskām vērtībām

Segmenta ieteikumi atšķiras, ja kā primāro atribūtu izvēlaties skaitlisku atribūtu vai kategorijas atribūtu. Kategorijas atribūta vērtības satur divu vai vairāku veidu kategorijas. Skaitlisks atribūts ietver ar to saistītus kvantitatīvos datus, un tam ir ar to saistītās mērvienības.

Ja kā primārais atribūts ir skaitlisks atribūts, piemēram, *gada ienākumi* vai *dalības periods*, sistēma iesaka segmentus, kuru skaitliskā atribūta vidējā vērtība ir augstāka vai mazāka salīdzinājumā ar visiem klientiem.

Ja kā primārais atribūts ieteiktajos segmentos ir kategorijas atribūts, piemēram, *klientu apmierinājums*, kam ir noteiktai kategorijai piederošu klientu procentuāla vērtība vai lielāka procentuālā vērtība, salīdzinot ar visu ar šo kategoriju piederošo klientu procentuālo vērtību. Piemēram, kā primārais atribūts tiek izvēlēta *klientu apmierinātība*, un tas sastāv no trim kategorijām (*Zems*, *Vidējs* un *Augsts*). Attiecībā uz katru kategoriju tiks ieteikti segmenti ar lielāku vai zemāku šai kategorijai piederošo klientu procentuālo daudzumu salīdzinājumā ar visu vienas kategorijas klientu procentuālo attiecību. Ja 22% no visiem klientiem ir *Augsts* apmierinātības līmenis, šajā kategorijā tiks piedāvāti tikai segmenti, kuros ir lielāka vai mazāka klientu daļa ar *Augstu* apmierinātību salīdzinājumā ar 22%. Līdzīgi arī segmenti tiek ieteikti katrai citai kategorijai (*Zems* un *Vidējs*), ja tie ir statistiski svarīgi.

> [!NOTE]
> Pašlaik mēs sniedzam atbalstu tikai primārajiem kategorijas atribūtiem, kuriem ir līdz 10 kategorijām. Ja vēlaties skatīt segmenta ieteikumus, pamatojoties uz primāro atribūtu, kam ir vairāk nekā 10 kategorijas, ieteicams grupēt dažas kategorijas, lai samazinātu kategoriju skaitu līdz 10 vai mazāk. Šis ierobežojums attiecas tikai uz primārajiem atribūtiem. Pašlaik mēs sniedzam atbalstu ne vairāk kā 100 kategorijām, lai ietekmētu kategorijas atribūtus.

## <a name="generate-suggested-segments"></a>Izveidot ieteiktos segmentus

1. Ejiet uz **Segmenti**.

1. Atlasiet cilni **Ieteikumi (priekšskatījums)**.

1. Atlasiet **Iegūt jaunus ieteikumus**, lai sāktu vadīto darbu.

1. Kā primāro atribūtu izvēlieties līdzekli vai klienta atribūtu un atlasiet **Tālāk**.

   :::image type="content" source="media/suggested-segments-primary-attribute.png" alt-text="Ieteikumu primārā atribūta izvēle ieteiktajiem segmentiem.":::

1. Atlasiet ietekmējošos atribūtus un atlasiet **Saglabāt**.
   
   > [!TIP]
   > Atlasot vairākus ietekmējošos atribūtus uzlabo izredzes novērtēt, kā tie ietekmē primāro atribūtu. Neietveriet atribūtus, kas neietekmē primāro atribūtu. Piemēram, ja visi jūsu klienti ir no konkrētas valsts, neietveriet *valsts* atribūtu, jo tas neietekmēs izvadi.

1. Atkarībā no klientu profilu un atlasīto atribūtu skaita atlasīto atribūtu apstrāde var ilgt dažas minūtes. 

## <a name="view-details-of-a-suggested-segment"></a>Ieteicamā segmenta detalizētas informācijas skatīšana

Kad mākslīgā intelekta modelis ir ģenerējis ieteikumus, atradīsiet tos uzskaitītus sadaļā **Segmenti** > **Ieteikumi (priekšskatījums)**.
 
Atlasiet ieteikto segmentu, lai skatītu detalizētu informāciju par šo ierosinājumu. Varat arī pārskatīt atribūtu vērtības vai kārtulas, kuras mākslīgā intelekta modelis apguva, lai ieteiktu atlasīto segmentu.

## <a name="save-a-suggestion-as-a-segment"></a>Ieteikuma saglabāšana par segmentu

1. Dodieties uz **Segmenti** > **Ieteikumi (priekšskatījums)**.

1. Atlasiet saglabājamo segmentu. 

1. Sānu rūtī atlasiet **Saglabāt kā segmentu**. 

1. Pēc segmenta saglabāšanas tas tiks rādīts segmentu saraksta cilnē **Visi segmenti**. Tagad to var [atsvaidzināt, rediģēt vai dzēst kā jebkuru citu segmentu](segments.md).

## <a name="refresh-or-edit-a-set-of-suggestions"></a>Ieteikumu kopas atsvaidzināšana vai rediģēšana

1. Dodieties uz **Segmenti** > **Ieteikumi (priekšskatījums)**.

1. Atlasiet **Atsvaidzināt ieteikumus**, lai atsvaidzinātu ieteikumus, saglabājot konfigurētos atribūtus. Vai atlasiet **Rediģēt atribūtus**, lai modificētu konfigurētos atribūtus. Sistēma atkārtoti palaidīs mākslīgā intelekta modeli, ģenerēs segmenta ieteikumus, pamatojoties uz jaunākajiem datiem, un aizstās pašreizējos ieteikumus.

## <a name="limitations"></a>Ierobežojumi

1. Prognozētā segmenta lieluma neatbilstība: ja izvēlaties primāro atribūtu, kurā ir tukšas vērtības, tas var ietekmēt segmenta ieteikumu prognozēto segmenta lielumu. Saglabājot šādu segmentu, faktiskais segmenta lielums var atšķirties no sākotnējā novērtējuma.
 
2. Būla tipa primārie atribūti nedarbojas: pašlaik kā primārie atribūti tiek atbalstīti tikai virknes un skaitliskie datu tipi.

3. Ieteiktie segmenti nav pietiekami izplatīti: paturiet prātā, ka atlasītie atribūti un šo atribūtu vērtību sadale ietekmē rezultātus. Lai iegūtu atšķirīgus rezultātus, varat mainīt savus ietekmējošos atribūtus vai pat primāro atribūtu.



[!INCLUDE[footer-include](../includes/footer-banner.md)]