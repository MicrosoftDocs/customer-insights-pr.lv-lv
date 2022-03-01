---
title: Semantiskā analīze klientu atsauksmēm
description: Uzziniet, kā izmantot noskaņojuma analīzes modeli klientu atsauksmēm programmā Dynamics 365 Customer Insights.
ms.date: 12/23/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: wmelewong
ms.author: wameng
manager: shellyha
ms.openlocfilehash: 05e530a1bc96c5fd9c7a3bc0197563d8fe330387
ms.sourcegitcommit: cb71e39de9b891c24bd5cd9c014eb3eeb537ac24
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 01/10/2022
ms.locfileid: "7951112"
---
# <a name="analyze-sentiment-in-customer-feedback-preview"></a>Analizēt noskaņojumu klientu atsauksmēs (Priekšskatījums)

Klienti mūsdienās sagaida augstas kvalitātes produktus, pakalpojumus un pieredzi. Īpaši klienti, kuri dalās ar savām atsauksmēm. Organizācijām ir ļoti grūti analizēt pieaugošo datu apjomu, nesamazinot precizitāti un augstākas darbaspēka izmaksas. Dynamics 365 Customer Insights piedāvā sentimenta analīzes modeli klientu atsauksmēm, kas ļauj organizācijām precīzāk un ar zemākām izmaksām analizēt savus datus.

Sentimenta analīze ļauj sintezēt klientu noskaņojumu un identificēt biznesa aspektus kā uzlabošanas iespējas. Šī customer insights funkcija palīdz saprast, kas darbojas labi un kas jums jārisina. Koncentrējieties uz visatbilstošākajām un ietekmīgākajām uzņēmējdarbības jomām, lai uzlabotu klientu pieredzi. Galu galā, tas var palīdzēt jums virzīt biznesa darbības, kas ļauj pieredzi, kas rada augstu klientu apmierinātību un lojalitāti.

## <a name="overview"></a>Pārskats

Sentimenta analīzes līdzeklis ģenerē divus atvasinātus ieskatus katram debitora ID. Sentimenta vērtējums (no -5 līdz 5) un piemērojamo biznesa aspektu (uzņēmējdarbības jomu) saraksts kopā palīdz labāk izprast klientu atsauksmes. 

Šī informācija var palīdzēt sasniegt šādus rezultātus: 
- Pārskati par klientu noskaņojumu pret zīmolu vai organizāciju
- Identificējiet klientus ar negatīvu noskaņojumu, lai koncentrētu savas kampaņas un saistības un optimizētu lielāku atdevi  
- Identificējiet biznesa aspektus ar klientu norādītajām problēmām  
- Segmentēt klientus, pamatojoties uz viņu noskaņojumu, lai vadītu personalizētas kampaņas ar mērķtiecīgu pārdošanu, mārketingu un atbalsta centieniem
- Optimizējiet uzņēmējdarbību, risinot klientu minētās problemātiskās jomas vai iespējas
- Atpazīstiet biznesa aspektus, kas darbojas labi, un atalgojiet laimīgus klientus, izmantojot lojalitātes un veicināšanas programmas

Lai nodrošinātu, ka jūs varat uzticēties modeļu rezultātiem, mēs sniedzam pārredzamu informāciju par to, kā modeļi pieņem lēmumus. Jūs saņemsiet sarakstu ar vārdiem, kas ietekmēja modeļu lēmumu piešķirt konkrētu noskaņojuma rezultātu vai biznesa aspektu atsauksmju komentāriem.  

Mēs izmantojam divus **dabiskās valodas apstrādes (NLP) modeļus** : Pirmais piešķir katram atsauksmju komentāram sentimenta rezultātu. Otrais modelis saista katru atgriezenisko saiti ar visiem piemērojamajiem uzņēmējdarbības aspektiem. Modeļi ir apmācīti par publiskiem datiem no avotiem sociālajos plašsaziņas līdzekļos, mazumtirdzniecībā, restorānos, patēriņa produktos un automobiļu rūpniecībā.    
  
- Iepriekš definētie biznesa aspekti modelim, kas saistāms ar atgriezeniskās saites datiem, ir šādi:
-   Uzņēmumu pārvaldība
-   Norēķināšanās un maksājums
-   Klientu atbalsts
-   Paņemšana veikalā
-   Iepakojuma piegāde un atgriešana
-   Iepriekšēja pasūtīšana
-   Cenrādis
-   Konfidencialitāte un drošība
-   Akcijas un balvas
-   Saņemšana un garantija
-   Atgriezto preču apmaiņa un atcelšana
-   Izpildes precizitāte
-   Vietnes/programmas kvalitāte

> [!NOTE]
> Pašlaik mēs atbalstām tikai noskaņojuma analīzi par angļu klientu atsauksmēm. Nākotnē tiks atbalstīts vairāk valodu. Ja atsauksmes citās valodās tiek augšupielādētas, modelis joprojām atgriezīs rezultātus. Tomēr šie rezultāti nebūs precīzi. 

## <a name="prerequisites"></a>Priekšnoteikumi

Sentimenta analīze ir balstīta uz teksta atgriezeniskās saites datiem, kas ir izgājuši [datu apvienošanas procesu](data-unification.md). Ieteicams [iepriekš konfigurēt atsauksmju datu entītijas kā semantiskā tipa darbību entītijas](map-entities.md#select-primary-key-and-semantic-type-for-attributes) (atsauksmju tips). 

Lai konfigurētu sentimenta analīzes modeli, ir nepieciešamas vismaz [Līdzstrādnieka atļaujas](permissions.md).

Customer Insights var apstrādāt līdz pat 10 miljoniem atsauksmju ierakstu viena modeļa palaišanai. Modelis var analizēt atgriezeniskās saites komentārus līdz 128 vārdiem. Ja atsauksmju komentārs ir garāks, analīzē ņemti vērā tikai pirmie 128 vārdi.

### <a name="data-requirements"></a>Datu prasības
  
Ir nepieciešami šādi datu atribūti:
- Vienotais klienta ID (UCID), lai saskaņotu teksta atsauksmju datu ierakstus ar atsevišķu klientu. Šis ID ir datu apvienošanas procesa [rezultāts](data-unification.md).
- Atsauksmju ID
- Atsauksmju laikspiedols
- Atsauksmju teksts   

> [!TIP]
> Sentimenta analīzei ir nepieciešamas jūsu klientu teksta atsauksmes. Pašlaik var konfigurēt tikai vienu atsauksmju entītiju. Ja ir vairākas atsauksmju entītijas, varat tās Power Query apvienot, pirms sākas datu norīšana.

## <a name="configure-a-sentiment-analysis"></a>Sentimenta analīzes konfigurēšana 

1. Sadaļā Customer Insights dodieties uz **Informācija** > **Prognozes**.

1. **Elementā Klientu noskaņojuma analīze** atlasiet **Izmantot modeli**.

1. Rūtī **Klientu noskaņojuma analīze** (priekšskatījums) atlasiet **Sākt darbu**.

1. Solī **Modeļa nosaukums** norādiet **analīzes** nosaukumu. 

1. Norādiet **biznesa aspekta izvades entītijas nosaukumu un** **Sentimenta rādītāja izvades entītijas nosaukumu**, pēc tam atlasiet **Tālāk**.

1. Solī **Obligātie dati** atlasiet **Pievienot datus**.

   :::image type="content" source="media/sentiment-add-data.png" alt-text="Pievienojiet datu plūsmu sentimenta analīzes modelī.":::

1. Rūtī **Datu pievienošana** sarakstā izvēlieties semantisko tipu **Atsauksmes**.

   :::image type="content" source="media/sentiment-add-feedback-activities.png" alt-text="Konfigurācijas darbība, lai atlasītu atgriezeniskās saites darbības sentimenta analīzei.":::

1. Atlasiet šai sentimenta analīzei izmantojamās darbības un pēc tam atlasiet **Tālāk**.
 
1. Kartējiet datu atribūtus uz modeļa atribūtiem. Atlasiet **Saglabāt**, lai lietotu atlasi. 

1. Tiek parādīts datu kartējuma statuss. Atlasiet **Tālāk**, lai turpinātu. 

1. Solī **Pārskatiet detalizētu informāciju par modeli** pārbaudiet sava noskaņojuma analīzes konfigurāciju. Varat atgriezties jebkurā prognoze konfigurācijas daļā. Atlasiet **Saglabāt un** palaist, lai sāktu analīzi. 

   :::image type="content" source="media/sentiment-model-review-config.png" alt-text="Pārskatīt sentimenta modeļa darbību, kurā parādīti visi konfigurētie vienumi.":::

1. Atlasiet **Gatavs**, lai atstātu konfigurācijas pieredzi. Atkarībā no izmantoto datu apjoma procesa pabeigšana var ilgt vairākas stundas. 

## <a name="review-analysis-status"></a>Pārskatīt analīzes statusu

1.  Atveriet  **Informācija** > **Prognozes** un atlasiet cilni **Manas prognozes**.
2.  Atlasiet prognozes, kuras vēlaties pārskatīt.
- **Prognoze nosaukums**: izveides brīdī paredzētās prognozes nosaukums.
- **prognoze tips** : prognoze izmantotā modeļa tips.
- **Izvades entītija**: entītijas nosaukums, kurā saglabāt prognozes izvadi. Dodieties uz **Dati** > **Entītijas**, lai atrastu entītiju ar šo nosaukumu.
- **Prognozētais lauks**: šis lauks tiek aizpildīts tikai dažu veidu prognozēm, un tos neizmanto klienta ilgtermiņa vērtības prognozē.
- **Statuss**: Prognozes izpildes statuss.
  - **Ierindots**: prognoze gaida citu procesu izpildi.
  - **Atsvaidzināšana**: prognoze pašlaik darbojas, lai iegūtu rezultātus, kas ieplūst izvades entītijā.
  - **Neizdevās**: neizdevās palaist prognozi. Lai iegūtu detalizētu informāciju, skatiet žurnālfailus.
  - **Veiksmīgi**: prognoze ir veiksmīga. Atlasiet Skats vertikālās daudzpunktes sadaļā, lai pārskatītu prognozes rezultātus.
- **Rediģēts**: datums, kad tika mainīta prognozes konfigurācija.
- **Pēdējo reizi atsvaidzināts** : datums, kad prognoze bija atsvaidzinājusi rezultātus izvades entītijā.

## <a name="manage-sentiment-analysis"></a>Pārvaldīt sentimenta analīzi

Varat optimizēt, novērst problēmas, atsvaidzināt vai dzēst prognozes. Pārskatiet ievades datu lietojamības ziņojumu, lai uzzinātu, kā padarīt prognozi ātrāku un uzticamāku. Papildinformāciju skatiet šeit: [Prognožu pārvaldība](manage-predictions.md).

## <a name="review-analysis-results"></a>Analīzes rezultātu pārskatīšana
 
1. Atveriet  **Informācija** > **Prognozes** un atlasiet cilni **Manas prognozes**. 
1. Atlasiet tā prognoze nosaukumu, kuram vēlaties pārskatīt rezultātus. Šādā gadījumā atlasiet sentimenta analīzi, kuru vēlaties pārskatīt. 

### <a name="summary-tab"></a>Kopsavilkuma cilne

Rezultātu lapā ir četras primārās datu sadaļas. 

- **Vidējais noskaņojuma vērtējums** : Palīdz izprast kopējo noskaņojumu visiem klientiem. Sentimenta rādītāji ir sagrupēti trīs kategorijās: 
  1.    Negatīvs (-5 > 2)
  2.    Neitrāls (-1 > 1)
  3.    Pozitīvs (2 > 5) 
  
  :::image type="content" source="media/overall-customer-sentiment.png" alt-text="Kopējā klientu noskaņojuma vizuālais attēlojums.":::

- **Klientu sadalījums pēc sentimenta vērtējuma** : Klienti tiek iedalīti negatīvās, neitrālās un pozitīvās grupās, pamatojoties uz viņu noskaņojuma rādītājiem. Novietojiet kursoru virs histogrammas stieņiem, lai redzētu klientu skaitu un vidējo noskaņojuma rādītāju katrā grupā. Šie dati var palīdzēt [izveidot klientu segmentus,](segments.md) pamatojoties uz viņu noskaņojuma rādītājiem.  

  :::image type="content" source="media/distribution-customer-sentiment.png" alt-text="Joslu diagramma, kurā redzams klientu noskaņojums visās trijās sentimenta grupās.":::

- **Vidējais sentimenta rādītājs laika gaitā** : klientu noskaņojums laika gaitā var mainīties. Mēs piedāvājam jūsu klientu noskaņojuma tendences jūsu datu laika diapazonā. Šis skats var palīdzēt novērtēt sezonālo akciju, produktu laišanas tirgū vai citu laika intervenču ietekmi uz klientu noskaņojumu. Skatiet grafiku, nolaižamajā izvēlnē atlasot interesējošo gadu. 

  :::image type="content" source="media/sentiment-score-over-time.png" alt-text="Vēstures diagramma ar sentimenta rādītāju laika gaitā, kas attēlots kā līnija.":::
 
- **Noskaņojums par biznesa aspektiem** : Šajā tabulā ir uzskaitītas vidējais noskaņojums visos biznesa aspektos. Tas var palīdzēt jums novērtēt, kuri jūsu uzņēmuma aspekti jau apmierina klientus vai aspektus, kuriem nepieciešama lielāka uzmanība. Atsauksmju ieraksti, kas neatbilst nevienam no atbalstītajiem biznesa aspektiem, tiek iedalīti sadaļā **Cits**. Tabula pēc noklusējuma ir sakārtota alfabētiskā secībā. Kārtošanu var modificēt, atlasot tabulas galveni.

  :::image type="content" source="media/sentiment-across-business-aspects.png" alt-text="Biznesa aspektu saraksts ar saistīto sentimenta vērtību un klientu skaitu, kas to min.":::
 
  Atlasiet biznesa aspekta nosaukumu, lai skatītu papildinformāciju par to, kā modelis identificē biznesa aspektu. Šajā rūtī ir divas daļas: 

  - **Ietekmīgi vārdi** : parāda labākos vārdus, kas ietekmēja AI modeļa biznesa aspekta identifikāciju klientu atsauksmēs. 
    **Rādīt aizvainojošus** vārdus : ļauj sarakstā iekļaut aizvainojošus vārdus no sākotnējiem klientu atsauksmju datiem. Pēc noklusējuma tas ir izslēgts.  Aizvainojošu vārdu maskēšanu darbina MI modelis, un tas var neatklāj visus aizvainojošos vārdus. Mēs turpinām atkārtot un apmācīt klasifikatoru optimālam sniegumam. Ja atklājat aizvainojošu vārdu, kas netika filtrēts, kā paredzēts, informējiet mūs. 
    
    :::image type="content" source="media/offensive-words-sentiment.png" alt-text="Ietekmīgu vārdu saraksts ar pārslēgu, lai parādītu vai paslēptu aizvainojošus vārdus.":::
 
  - **Atsauksmju paraugi** : parāda faktiskos atsauksmju ierakstus jūsu datos. Vārdi ir kodēti ar krāsu atbilstoši to ietekmei uz biznesa aspekta identificēšanu. 


### <a name="influential-words-analysis-tab"></a>Ietekmīga vārdu analīzes cilne

Ir trīs papildu informācijas sadaļas, kas izskaidro, kā darbojas sentimenta modelis.
  
1. **Populārākie vārdi, kas veicina pozitīvu noskaņojumu** : Parāda labākos vārdus, kas ietekmēja AI modeļa pozitīvā noskaņojuma identificēšanu klientu atsauksmēs.  
2. **Populārākie vārdi, kas veicina negatīvu noskaņojumu** : Parāda labākos vārdus, kas ietekmēja AI modeļa negatīvā noskaņojuma identificēšanu klientu atsauksmēs.  
3. **Atsauksmju paraugi** : Parāda faktiskos atgriezeniskās saites ierakstus, vienu ar negatīvu noskaņojumu un tādu, kam ir pozitīvs noskaņojums. Vārdi atsauksmju ierakstos tiek izcelti atbilstoši to ieguldījumam piešķirtajā sentimenta vērtējumā. Vārdi, kas veicina pozitīvu noskaņojuma rezultātu, ir izcelti zaļā krāsā. Vārdi, kas veicina negatīvu rezultātu, ir iezīmēti sarkanā krāsā.
   Atlasiet **Skatīt** vairāk, lai ielādētu vairāk atsauksmju paraugu, kas sniedz papildinformāciju un kontekstu par sentimenta modeļa darbību.
   
   :::image type="content" source="media/sentiment-feedback-samples.png" alt-text="Noskaņojuma analīzes piemēri par klientu atsauksmēm.":::
 
**Rādīt aizvainojošus** vārdus : ļauj sarakstā iekļaut aizvainojošus vārdus no sākotnējiem klientu atsauksmju datiem. Pēc noklusējuma tas ir izslēgts.  Aizvainojošu vārdu maskēšanu darbina MI modelis, un tas var neatklāj visus aizvainojošos vārdus. Mēs turpinām atkārtot un apmācīt klasifikatoru optimālam sniegumam. Ja atklājat aizvainojošu vārdu, kas netika filtrēts, kā paredzēts, informējiet mūs. 

## <a name="act-on-analysis-results"></a>Akts par analīžu rezultātiem

Varat viegli sākt veidot jaunus klientu segmentus no sentimenta analīzes rezultātu lapas, modeļa rezultātu lapas augšdaļā atlasot **Izveidot** segmentus.

:::image type="content" source="media/create-segment-model.png" alt-text="Komandjosla ar opcijām prognoze modeļos.":::
 
## <a name="potential-bias"></a>Iespējamā neobjektivitāte

Tāpat kā ar jebkuru funkciju, kas izmanto prognozējošu mākslīgo intelektu, jums jāapzinās iespējamie aizspriedumus datos, kurus izmantojat, lai prognozētu klientu noskaņojumu. Piemēram, ja atsauksmes apkopojat tikai digitāli, varat palaist garām atsauksmes no klientiem, kuri galvenokārt veic darījumus ar jums klātienē, kas var ietekmēt līdzekļa izvadi.

Tā kā šī funkcija izmanto automatizētus līdzekļus, lai novērtētu datus un veiktu prognozes, pamatojoties uz šiem datiem, to var izmantot kā profilēšanas metodi, kā to definē Vispārīgā datu aizsardzības regula ("VDAR"). Šī līdzekļa izmantošana datu apstrādāšanai var būt pakļauta VDAR vai citiem tiesību aktiem un noteikumiem. Jūs esat atbildīgs par to, lai nodrošinātu, ka jūsu, Dynamics 365 Customer Insights tostarp sentimenta analīzes, izmantošana atbilst visiem piemērojamajiem normatīvajiem aktiem, tostarp tiesību aktiem, kas saistīti ar privātumu, personas datiem, biometriskajiem datiem, datu aizsardzību un saziņas konfidencialitāti.

[!INCLUDE[footer-include](../includes/footer-banner.md)]

