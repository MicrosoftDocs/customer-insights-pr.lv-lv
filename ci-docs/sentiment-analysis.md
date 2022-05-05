---
title: Klientu atsauksmju noskaņojuma analīze
description: Uzziniet, kā izmantot sentimenta analīzes modeli klientu atsauksmēm programmā Dynamics 365 Customer Insights.
ms.date: 12/23/2021
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: wmelewong
ms.author: wameng
manager: shellyha
ms.openlocfilehash: e51225bbfcd445180b12661cba12256c3f042045
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643529"
---
# <a name="analyze-sentiment-in-customer-feedback-preview"></a>Klientu atsauksmju noskaņojuma analīze (priekšskatījums)

Mūsdienās klienti sagaida augstas kvalitātes produktus, pakalpojumus un pieredzi. Īpaši klienti, kuri dalās savās atsauksmēs. Organizācijām ir ļoti grūti analizēt pieaugošo datu apjomu, nesamazinot precizitāti un augstākas darbaspēka izmaksas. Dynamics 365 Customer Insights piedāvā klientu atsauksmju noskaņojuma analīzes modeli, kas ļauj organizācijām precīzāk un ar zemākām izmaksām analizēt savus datus.

Sentimenta analīze ļauj sintezēt klientu noskaņojumu un identificēt biznesa aspektus kā uzlabošanas iespējas. Šī Customer Insights funkcija palīdz jums saprast, kas darbojas labi un kas jums jārisina. Koncentrējieties uz visatbilstošākajām un ietekmīgākajām uzņēmējdarbības jomām, lai uzlabotu klientu pieredzi. Galu galā tas var palīdzēt jums virzīt biznesa darbības, kas nodrošina pieredzi, kas rada augstu klientu apmierinātību un lojalitāti.

## <a name="overview"></a>Pārskats

Sentimenta analīzes līdzeklis ģenerē divus atvasinātus ieskatus par katra klienta ID. Noskaņojuma rādītājs (no -5 līdz 5) un piemērojamo uzņēmējdarbības aspektu (uzņēmējdarbības jomu) saraksts kopā palīdz labāk izprast klientu atsauksmes. 

Šī informācija var palīdzēt sasniegt šādus rezultātus: 
- Iegūstiet pārskatu par klientu noskaņojumu attiecībā uz zīmolu vai organizāciju
- Identificējiet klientus ar negatīvu noskaņojumu, lai koncentrētu savas kampaņas un iesaisti un optimizētu lielāku atdevi  
- Identificējiet biznesa aspektus ar klientu norādītajām problēmām  
- Segmentējiet klientus, pamatojoties uz viņu noskaņojumu vadīt personalizētas kampaņas ar mērķtiecīgiem pārdošanas, mārketinga un atbalsta centieniem
- Optimizējiet uzņēmējdarbību, pievēršoties klientu minētajām problemātiskajām jomām vai iespējām
- Atpazīstiet biznesa aspektus, kuriem klājas labi, un atalgojiet laimīgus klientus, izmantojot lojalitātes un veicināšanas programmas

Lai nodrošinātu, ka jūs varat uzticēties modeļu rezultātiem, mēs sniedzam pārredzamu informāciju par to, kā modeļi pieņem lēmumus. Jūs saņemsiet to vārdu sarakstu, kas ietekmēja modeļu lēmumu atsauksmju komentāriem piešķirt konkrētu noskaņojuma rādītāju vai biznesa aspektu.  

Mēs izmantojam divus **dabiskās valodas apstrādes (NLP) modeļus**: Pirmais piešķir katram atsauksmju komentāram sentimenta rezultātu. Otrais modelis saista katru atgriezenisko saiti ar visiem piemērojamiem uzņēmējdarbības aspektiem. Modeļi ir apmācīti par publiskiem datiem no avotiem sociālajos medijos, mazumtirdzniecībā, restorānos, patēriņa precēs un autobūves nozarē.    
  
Iepriekš definētie uzņēmējdarbības aspekti modelim, ko saistīt ar atsauksmju datiem, ietver:
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
> Pašlaik mēs atbalstām tikai sentimenta analīzi par angļu klientu atsauksmēm. Nākotnē tiks atbalstītas vairākas valodas. Ja tiek augšupielādētas atsauksmes citās valodās, modelis joprojām atgriezīs rezultātus. Tomēr šie rezultāti nebūs precīzi. 

## <a name="prerequisites"></a>Priekšnoteikumi

Sentimenta analīze ir balstīta uz teksta atgriezeniskās saites datiem, kas ir izgājuši datu apvienošanas [procesu](data-unification.md). Ļoti ieteicams [iepriekš konfigurēt atsauksmju datu entītijas kā semantiskā tipa darbību entītijas](map-entities.md#select-primary-key-and-semantic-type-for-attributes) (atsauksmju tips). 

Lai konfigurētu noskaņojuma analīzes modeli, ir nepieciešamas vismaz [līdzstrādnieka](permissions.md) atļaujas.

Customer Insights var apstrādāt līdz pat 10 miljoniem atsauksmju ierakstu viena modeļa izpildei. Modelis var analizēt atsauksmju komentārus līdz 128 vārdiem. Ja atsauksmju komentārs ir garāks, analīzē tiek ņemti vērā tikai pirmie 128 vārdi.

### <a name="data-requirements"></a>Datu prasības
  
Ir nepieciešami šādi datu atribūti:
- Vienotais klienta ID (UCID), lai saskaņotu teksta atsauksmju datu ierakstus ar atsevišķu klientu. Šis ID ir datu apvienošanas [procesa](data-unification.md) rezultāts.
- Atsauksmju ID
- Atsauksmju laikspiedols
- Atsauksmju teksts   

> [!TIP]
> Sentimenta analīzei ir nepieciešama klientu teksta atgriezeniskā saite. Pašlaik var konfigurēt tikai vienu atsauksmju entītiju. Ja ir vairākas atsauksmju entītijas, tās Power Query var apvienot pirms datu uzņemšanas sākuma.

## <a name="configure-a-sentiment-analysis"></a>Noskaņojuma analīzes konfigurēšana 

1. Sadaļā Customer Insights dodieties uz **Informācija** > **Prognozes**.

1. Debitora noskaņojuma **analīzes** elementā atlasiet **Izmantot modeli**.

1. **Rūtī Klientu noskaņojuma analīze (priekšskatījums)** atlasiet **Sākt darbu**.

1. **Solī Modeļa nosaukums** norādiet **analīzes nosaukumu**. 

1. Norādiet **biznesa aspekta izvades entītijas nosaukumu** un sentimenta **rezultātu izvades entītijas nosaukumu**, pēc tam atlasiet **Tālāk**.

1. **Solī Obligātie dati** atlasiet **Pievienot datus**.

   :::image type="content" source="media/sentiment-add-data.png" alt-text="Pievienojiet datu plūsmu sentimenta analīzes modelī.":::

1. **Rūtī Datu** pievienošana sarakstā izvēlieties semantisko tipu **Atsauksmes**.

   :::image type="content" source="media/sentiment-add-feedback-activities.png" alt-text="Konfigurācijas solis, lai atlasītu atsauksmju aktivitātes noskaņojuma analīzei.":::

1. Atlasiet aktivitātes, ko izmantot šai noskaņojuma analīzei, pēc tam atlasiet **Tālāk**.
 
1. Kartējiet datu atribūtus ar modeļa atribūtiem. Atlasiet **Saglabāt**, lai lietotu atlasi. 

1. Jūs redzat datu kartējuma statusu. Atlasiet **Tālāk**, lai turpinātu. 

1. **Solī Pārskatīt detalizētu informāciju par** modeli validējiet sava noskaņojuma analīzes konfigurāciju. Varat atgriezties jebkurā prognoze konfigurācijas daļā. Atlasiet **Saglabāt un palaist**, lai sāktu analīzi. 

   :::image type="content" source="media/sentiment-model-review-config.png" alt-text="Pārskatīt darbību sentimenta modelim, kurā redzami visi konfigurētie vienumi.":::

1. Atlasiet **Gatavs**, lai atstātu konfigurācijas pieredzi. Atkarībā no izmantoto datu apjoma procesa pabeigšana var ilgt vairākas stundas. 

## <a name="review-analysis-status"></a>Pārskatīt analīzes statusu

1.  Atveriet  **Informācija** > **Prognozes** un atlasiet cilni **Manas prognozes**.
2.  Atlasiet prognozes, kuras vēlaties pārskatīt.
- **Prognoze nosaukums**: izveides brīdī paredzētās prognozes nosaukums.
- **prognoze tips**: prognoze izmantotā modeļa tips.
- **Izvades entītija**: entītijas nosaukums, kurā saglabāt prognozes izvadi. Dodieties uz **Dati** > **Entītijas**, lai atrastu entītiju ar šo nosaukumu.
- **Prognozētais lauks**: šis lauks tiek aizpildīts tikai dažu veidu prognozēm, un tos neizmanto klienta ilgtermiņa vērtības prognozē.
- **Statuss**: Prognozes izpildes statuss.
  - **Ierindots**: prognoze gaida citu procesu izpildi.
  - **Atsvaidzināšana**: prognoze pašlaik darbojas, lai iegūtu rezultātus, kas ieplūst izvades entītijā.
  - **Neizdevās**: neizdevās palaist prognozi. Lai iegūtu detalizētu informāciju, skatiet žurnālfailus.
  - **Veiksmīgi**: prognoze ir veiksmīga. Atlasiet Skats vertikālās daudzpunktes sadaļā, lai pārskatītu prognozes rezultātus.
- **Rediģēts**: datums, kad tika mainīta prognozes konfigurācija.
- **Pēdējoreiz atsvaidzināts**: datums, kad prognoze atsvaidzinājis rezultātus izvades entītijā.

## <a name="manage-sentiment-analysis"></a>Pārvaldīt noskaņojuma analīzi

Prognozes var optimizēt, novērst problēmas, atsvaidzināt vai dzēst. Pārskatiet ievades datu lietojamības ziņojumu, lai uzzinātu, kā padarīt prognozi ātrāku un uzticamāku. Papildinformāciju skatiet šeit: [Prognožu pārvaldība](manage-predictions.md).

## <a name="review-analysis-results"></a>Pārskatīt analīzes rezultātus
 
1. Atveriet  **Informācija** > **Prognozes** un atlasiet cilni **Manas prognozes**. 
1. Atlasiet tās prognoze nosaukumu, kurai vēlaties pārskatīt rezultātus. Šādā gadījumā atlasiet noskaņojuma analīzi, kuru vēlaties pārskatīt. 

### <a name="summary-tab"></a>Kopsavilkuma cilne

Rezultātu lapā ir četras primārās datu sadaļas. 

- **Vidējais noskaņojuma rādītājs**: Palīdz jums saprast vispārējo noskaņojumu visiem klientiem. Sentimenta rādītāji ir sagrupēti trīs kategorijās: 
  1.    Negatīvs (-5 > 2)
  2.    Neitrāls (-1 > 1)
  3.    Pozitīvs (2 > 5) 
  
  :::image type="content" source="media/overall-customer-sentiment.png" alt-text="Kopējā klienta noskaņojuma vizuālais attēlojums.":::

- **Klientu sadalījums pēc noskaņojuma rādītāja**: Klienti tiek iedalīti negatīvās, neitrālās un pozitīvās grupās, pamatojoties uz viņu noskaņojuma rādītājiem. Virziet kursoru virs histogrammas joslām, lai redzētu klientu skaitu un vidējo noskaņojuma rādītāju katrā grupā. Šie dati var palīdzēt izveidot [klientu](segments.md) segmentus, pamatojoties uz viņu noskaņojuma rādītājiem.  

  :::image type="content" source="media/distribution-customer-sentiment.png" alt-text="Joslu diagramma, kurā redzams klienta noskaņojums trijās sentimentu grupās.":::

- **Vidējais noskaņojuma rādītājs laika** gaitā: klientu noskaņojums laika gaitā var mainīties. Mēs nodrošinām jūsu klientu noskaņojuma tendences jūsu datu laika diapazonā. Šis skats var palīdzēt novērtēt sezonas akciju, produktu laišanas tirgū vai citu laika ziņā ierobežotu iejaukšanos ietekmi uz klientu noskaņojumu. Skatiet grafiku, nolaižamajā izvēlnē atlasot interesējošo gadu. 

  :::image type="content" source="media/sentiment-score-over-time.png" alt-text="Vēstures diagramma ar noskaņojuma rezultātu laika gaitā, kas attēlots kā līnija.":::
 
- **Noskaņojums dažādos uzņēmējdarbības aspektos**: šajā tabulā ir uzskaitīts vidējais noskaņojums dažādos uzņēmējdarbības aspektos. Tas var palīdzēt jums novērtēt, kuri jūsu uzņēmuma aspekti jau apmierina klientus vai aspektus, kuriem nepieciešama lielāka uzmanība. Atsauksmju ieraksti, kas nesalīdzina nevienu no atbalstītajiem biznesa aspektiem, tiek iedalīti sadaļā **Citi**. Tabula pēc noklusējuma ir sakārtota alfabētiskā secībā. Kārtošanu var modificēt, atlasot tabulas galveni.

  :::image type="content" source="media/sentiment-across-business-aspects.png" alt-text="Biznesa aspektu saraksts ar saistīto noskaņojuma vērtību un klientu skaitu, kas to piemin.":::
 
  Atlasiet uzņēmuma aspekta nosaukumu, lai skatītu papildinformāciju par to, kā modelis identificē biznesa aspektu. Šajā rūtī ir divas daļas: 

  - **Ietekmīgi vārdi**: parāda galvenos vārdus, kas ietekmēja MI modeļa uzņēmējdarbības aspekta identifikāciju klientu atsauksmēs. 
    **Rādīt aizvainojošus vārdus**: Ļauj sarakstā iekļaut aizvainojošus vārdus no sākotnējiem klientu atsauksmju datiem. Pēc noklusējuma tas ir izslēgts.  Aizvainojošu vārdu maskēšanu darbina MĀKSLĪGĀ INTELEKTA modelis, un tā var neatklāt visus aizvainojošos vārdus. Mēs turpinām kurinātāja atkārtošanu un apmācību optimālai veiktspējai. Ja konstatējat aizvainojošu vārdu, kas netika filtrēts, kā paredzēts, informējiet mūs. 
    
    :::image type="content" source="media/offensive-words-sentiment.png" alt-text="Ietekmīgu vārdu saraksts ar slēdzi, lai parādītu vai paslēptu aizvainojošus vārdus.":::
 
  - **Atsauksmju paraugi**: parāda faktiskos atsauksmju ierakstus datos. Vārdi ir kodēti ar krāsām atbilstoši to ietekmei uz biznesa aspekta identifikāciju. 


### <a name="influential-words-analysis-tab"></a>Ietekmīgu vārdu analīzes cilne

Ir trīs papildu informācijas sadaļas, kas izskaidro, kā darbojas noskaņojuma modelis.
  
1. **Populārākie vārdi, kas veicina pozitīvu noskaņojumu**: Parāda labākos vārdus, kas ietekmēja MĀKSLĪGĀ INTELEKTA modeļa pozitīvā noskaņojuma identifikāciju klientu atsauksmēs.  
2. **Populārākie vārdi, kas veicina negatīvu noskaņojumu**: parāda galvenos vārdus, kas ietekmēja mākslīgā intelekta modeļa negatīvā noskaņojuma identifikāciju klientu atsauksmēs.  
3. **Atsauksmju paraugi**: parāda faktiskos atsauksmju ierakstus, vienu ar negatīvu noskaņojumu un vienu ar pozitīvu noskaņojumu. Vārdi atsauksmju ierakstos tiek izcelti atbilstoši to ieguldījumam piešķirtajā noskaņojuma vērtējumā. Vārdi, kas veicina pozitīvu noskaņojuma rādītāju, ir izcelti zaļā krāsā. Vārdi, kas veicina negatīvu rezultātu, ir izcelti sarkanā krāsā.
   Atlasiet **Skatīt vairāk**, lai ielādētu vairāk atsauksmju paraugu, kas sniedz papildinformāciju un kontekstu par to, kā darbojas noskaņojuma modelis.
   
   :::image type="content" source="media/sentiment-feedback-samples.png" alt-text="Klientu atsauksmju noskaņojuma analīzes piemēri.":::
 
**Rādīt aizvainojošus vārdus**: Ļauj sarakstā iekļaut aizvainojošus vārdus no sākotnējiem klientu atsauksmju datiem. Pēc noklusējuma tas ir izslēgts.  Aizvainojošu vārdu maskēšanu darbina MĀKSLĪGĀ INTELEKTA modelis, un tā var neatklāt visus aizvainojošos vārdus. Mēs turpinām kurinātāja atkārtošanu un apmācību optimālai veiktspējai. Ja konstatējat aizvainojošu vārdu, kas netika filtrēts, kā paredzēts, informējiet mūs. 

## <a name="act-on-analysis-results"></a>Akts par analīžu rezultātiem

Varat viegli sākt veidot jaunus klientu segmentus no sentimenta analīzes rezultātu lapas augšdaļā, atlasot **Izveidot segmentus**.

:::image type="content" source="media/create-segment-model.png" alt-text="Komandjosla ar opcijām prognoze modeļos.":::
 
## <a name="potential-bias"></a>Potenciāli aizspriedumi

Tāpat kā jebkurai funkcijai, kas izmanto prognozējošu mākslīgo intelektu, jums jāapzinās iespējamie aizspriedumi datos, kurus izmantojat, lai prognozētu klientu noskaņojumu. Piemēram, ja atsauksmes apkopojat tikai digitāli, varat palaist garām atsauksmes no klientiem, kuri galvenokārt veic darījumus ar jums personīgi, kas var ietekmēt funkcijas izvadi.

Tā kā šī funkcija izmanto automatizētus līdzekļus, lai novērtētu datus un veiktu prognozes, pamatojoties uz šiem datiem, to var izmantot kā profilēšanas metodi, kā šo terminu definē Vispārīgā datu aizsardzības regula ("VDAR"). Šī līdzekļa izmantošana datu apstrādāšanai var būt pakļauta VDAR vai citiem tiesību aktiem un noteikumiem. Jūs esat atbildīgs par to, lai nodrošinātu, ka jūs, izmantojot Dynamics 365 Customer Insights, tostarp sentimenta analīzi, ievērojat visus piemērojamos normatīvos aktus, tostarp tiesību aktus, kas saistīti ar privātumu, personas datiem, biometriskajiem datiem, datu aizsardzību un saziņas konfidencialitāti.

[!INCLUDE [footer-include](includes/footer-banner.md)]

