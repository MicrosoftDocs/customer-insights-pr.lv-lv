---
title: Klientu atsauksmju noskaņojuma analīze (priekšskatījums)
description: Uzziniet, kā izmantot noskaņojuma analīzes modeli klientu atsauksmēm Dynamics 365 Customer Insights.
ms.date: 12/23/2021
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: wmelewong
ms.author: wameng
manager: shellyha
ms.openlocfilehash: af1afd3eff8a795a9e199b1c1d411b79dc2841b4
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 06/29/2022
ms.locfileid: "9055545"
---
# <a name="analyze-sentiment-in-customer-feedback-preview"></a>Noskaņojuma analīze klientu atsauksmēs (priekšskatījums)

Klienti šajās dienās sagaida augstas kvalitātes produktus, pakalpojumus un pieredzi. Īpaši klienti, kuri dalās savās atsauksmēs. Organizācijām ir ļoti grūti analizēt pieaugošo datu apjomu, nesamazinot precizitāti un augstākas darbaspēka izmaksas. Dynamics 365 Customer Insights piedāvā noskaņojuma analīzes modeli klientu atsauksmēm, kas ļauj organizācijām precīzāk un par zemākām izmaksām analizēt savus datus.

Noskaņojuma analīze ļauj sintezēt klientu noskaņojumu un identificēt biznesa aspektus kā uzlabojumu iespējas. Šis Customer Insights līdzeklis palīdz jums saprast, kas darbojas labi un kas jums ir jārisina. Koncentrējieties uz visatbilstošākajām un ietekmīgākajām uzņēmējdarbības jomām, lai uzlabotu savu klientu pieredzi. Galu galā tas var palīdzēt jums virzīt biznesa darbības, kas nodrošina pieredzi, kas nodrošina augstu klientu apmierinātību un lojalitāti.

## <a name="overview"></a>Pārskats

Noskaņojuma analīzes līdzeklis ģenerē divus atvasinātos ieskatus par katru klienta ID. Noskaņojuma rādītājs (no -5 līdz 5) un piemērojamo uzņēmējdarbības aspektu saraksts (uzņēmējdarbības jomas) kopā palīdz labāk izprast klientu atsauksmes. 

Šī informācija var palīdzēt sasniegt šādus rezultātus: 
- Iegūstiet pārskatu par klientu noskaņojumu attiecībā uz zīmolu vai organizāciju
- Identificējiet klientus ar negatīvu noskaņojumu, lai koncentrētos uz savām kampaņām un piesaisti, un optimizējiet, lai gūtu lielāku peļņu  
- Identificējiet biznesa aspektus ar problēmām, uz kurām norādījuši klienti  
- Segmentējiet klientus, pamatojoties uz viņu noskaņojumu rādīt personalizētas kampaņas ar mērķtiecīgu pārdošanu, mārketingu un atbalsta pasākumiem
- Optimizējiet biznesa operācijas, pievēršoties problemātiskām jomām vai iespējām, kuras minēja klienti
- Atzīstiet biznesa aspektus, kas darbojas labi, un apbalvojiet laimīgus klientus, izmantojot lojalitātes un veicināšanas programmas

Lai nodrošinātu, ka jūs varat uzticēties modeļu rezultātiem, mēs sniedzam pārredzamu informāciju par to, kā modeļi pieņem lēmumus. Jūs saņemsit sarakstu ar vārdiem, kas ietekmēja modeļu lēmumu atsauksmju komentāriem piešķirt noteiktu noskaņojuma rādītāju vai biznesa aspektu.  

Mēs izmantojam divus **dabiskās valodas apstrādes (NLP) modeļus**: pirmais katram atsauksmju komentāram piešķir noskaņojuma rādītāju. Otrais modelis katru atsauksmi saista ar visiem piemērojamajiem uzņēmējdarbības aspektiem. Modeļi ir apmācīti, pamatojoties uz publiskiem datiem no avotiem sociālajos medijos, mazumtirdzniecībā, restorānos, patēriņa produktos un automobiļu rūpniecībā.    
  
Iepriekš definētie uzņēmējdarbības aspekti, kas modelim jāsaista ar atsauksmju datiem, ir šādi:
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
> Pašlaik mēs atbalstām tikai noskaņojuma analīzi par angļu klientu atsauksmēm. Nākotnē tiks atbalstītas vēl citas valodas. Ja tiek augšupielādētas atsauksmes citās valodās, modelis joprojām atgriezīs rezultātus. Tomēr šie rezultāti nebūs precīzi. 

## <a name="prerequisites"></a>Priekšnoteikumi

Noskaņojuma analīze ir balstīta uz teksta atgriezeniskās saites datiem, kas ir izgājuši datu apvienošanas [procesu](data-unification.md). Ļoti ieteicams [iepriekš konfigurēt atsauksmju datu entītijas kā semantiskā tipa darbības entītijas](map-entities.md#select-primary-key-and-semantic-type-for-attributes) (atsauksmju tips). 

Lai konfigurētu noskaņojuma analīzes modeli, jums ir nepieciešamas vismaz [līdzstrādnieka](permissions.md) atļaujas.

Customer Insights var apstrādāt līdz pat 10 miljoniem atsauksmju ierakstu vienai modeļa izpildei. Modelis var analizēt atsauksmju komentārus līdz 128 vārdiem. Ja atsauksmju komentārs ir garāks, analīzē tiek ņemti vērā tikai pirmie 128 vārdi.

### <a name="data-requirements"></a>Datu prasības
  
Ir nepieciešami šādi datu atribūti:
- Vienotais klienta ID (UCID), lai saskaņotu teksta atsauksmju datu ierakstus ar atsevišķu klientu. Šis ID ir datu apvienošanas [procesa](data-unification.md) rezultāts.
- Atsauksmju ID
- Atgriezeniskās saites laikspiedols
- Atsauksmju teksts   

> [!TIP]
> Noskaņojuma analīzei ir nepieciešamas klientu teksta atsauksmes. Pašlaik var konfigurēt tikai vienu atsauksmju entītiju. Ja ir vairākas atsauksmju entītijas, varat tās Power Query apvienot pirms datu uzņemšanas sākuma.

## <a name="configure-a-sentiment-analysis"></a>Noskaņojuma analīzes konfigurēšana 

1. Sadaļā Customer Insights dodieties uz **Informācija** > **Prognozes**.

1. **Klienta noskaņojuma analīzes** elementā atlasiet **Lietot modeli**.

1. Klientu noskaņojuma **analīzes (priekšskatījuma)** rūtī atlasiet **Sākt darbu**.

1. **Darbībā Modeļa nosaukums** norādiet **analīzes nosaukumu**. 

1. **Norādiet biznesa aspekta izvades entītijas nosaukumu** un **sentimenta rādītāja izvades entītijas nosaukumu** un pēc tam atlasiet **Tālāk**.

1. **Darbībā Obligātie dati** atlasiet **Pievienot datus**.

   :::image type="content" source="media/sentiment-add-data.png" alt-text="Pievienojiet datu plūsmu noskaņojuma analīzes modelī.":::

1. **Rūtī Datu** pievienošana sarakstā izvēlieties semantisko tipu **Atsauksmes**.

   :::image type="content" source="media/sentiment-add-feedback-activities.png" alt-text="Konfigurācijas darbība, lai atlasītu atgriezeniskās saites aktivitātes noskaņojuma analīzei.":::

1. Atlasiet darbības, kas jāizmanto šai noskaņojuma analīzei, un pēc tam atlasiet **Tālāk**.
 
1. Kartējiet datu atribūtus uz modeļa atribūtiem. Atlasiet **Saglabāt**, lai lietotu atlasi. 

1. Tiek parādīts datu kartēšanas statuss. Atlasiet **Tālāk**, lai turpinātu. 

1. **Darbībā Pārskatiet detalizētu informāciju par** modeli, pārbaudiet sava noskaņojuma analīzes konfigurāciju. Varat atgriezties jebkurā prognoze konfigurācijas daļā. Atlasiet **Saglabāt un palaist**, lai sāktu analīzi. 

   :::image type="content" source="media/sentiment-model-review-config.png" alt-text="Pārskatiet darbību noskaņojuma modelim, kurā redzami visi konfigurētie vienumi.":::

1. Atlasiet **Gatavs**, lai atstātu konfigurācijas pieredzi. Process var ilgt vairākas stundas atkarībā no izmantoto datu apjoma. 

## <a name="review-analysis-status"></a>Analīzes statusa pārskatīšana

1.  Atveriet  **Informācija** > **Prognozes** un atlasiet cilni **Manas prognozes**.
2.  Atlasiet prognozes, kuras vēlaties pārskatīt.
- **Prognoze nosaukums**: izveides brīdī paredzētās prognozes nosaukums.
- **prognoze tips**: prognoze izmantotā modeļa veids.
- **Izvades entītija**: entītijas nosaukums, kurā saglabāt prognozes izvadi. Dodieties uz **Dati** > **Entītijas**, lai atrastu entītiju ar šo nosaukumu.
- **Prognozētais lauks**: šis lauks tiek aizpildīts tikai dažu veidu prognozēm, un tos neizmanto klienta ilgtermiņa vērtības prognozē.
- **Statuss**: Prognozes izpildes statuss.
  - **Ierindots**: prognoze gaida citu procesu izpildi.
  - **Atsvaidzināšana**: prognoze pašlaik darbojas, lai iegūtu rezultātus, kas ieplūst izvades entītijā.
  - **Neizdevās**: neizdevās palaist prognozi. Lai iegūtu detalizētu informāciju, skatiet žurnālfailus.
  - **Veiksmīgi**: prognoze ir veiksmīga. Atlasiet Skats vertikālās daudzpunktes sadaļā, lai pārskatītu prognozes rezultātus.
- **Rediģēts**: datums, kad tika mainīta prognozes konfigurācija.
- **Pēdējo reizi atsvaidzināts**: datums, kad prognoze bija atsvaidzinājis rezultātus izvades entītijā.

## <a name="manage-sentiment-analysis"></a>Noskaņojuma analīzes pārvaldība

Varat optimizēt, novērst problēmas, atsvaidzināt vai dzēst prognozes. Pārskatiet ievades datu lietojamības ziņojumu, lai uzzinātu, kā padarīt prognozi ātrāku un uzticamāku. Papildinformāciju skatiet šeit: [Prognožu pārvaldība](manage-predictions.md).

## <a name="review-analysis-results"></a>Analīzes rezultātu pārskatīšana
 
1. Atveriet  **Informācija** > **Prognozes** un atlasiet cilni **Manas prognozes**. 
1. Atlasiet tās prognoze nosaukumu, par kuru vēlaties pārskatīt rezultātus. Šādā gadījumā atlasiet noskaņojuma analīzi, kuru vēlaties pārskatīt. 

### <a name="summary-tab"></a>Kopsavilkuma cilne

Rezultātu lapā ir četras primārās datu sadaļas. 

- **Vidējais noskaņojuma rādītājs**: palīdz izprast visu klientu vispārējo noskaņojumu. Noskaņojuma rādītāji ir sagrupēti trīs kategorijās: 
  1.    Negatīvs (-5 > 2)
  2.    Neitrāls (-1 > 1)
  3.    Pozitīvs (2 > 5) 
  
  :::image type="content" source="media/overall-customer-sentiment.png" alt-text="Kopējā klientu noskaņojuma vizuālais attēlojums.":::

- **Klientu sadalījums pēc noskaņojuma rādītāja**: Klienti tiek iedalīti negatīvās, neitrālās un pozitīvās grupās, pamatojoties uz viņu noskaņojuma rādītājiem. Virziet kursoru virs histogrammas joslām, lai redzētu klientu skaitu un vidējo noskaņojuma rādītāju katrā grupā. Šie dati var palīdzēt izveidot [klientu](segments.md) segmentus, pamatojoties uz viņu noskaņojuma rādītājiem.  

  :::image type="content" source="media/distribution-customer-sentiment.png" alt-text="Joslu diagramma, kurā parādīts klientu noskaņojums visās trīs noskaņojuma grupās.":::

- **Vidējais noskaņojuma rādītājs laika** gaitā: klientu noskaņojums laika gaitā var mainīties. Mēs nodrošinām jūsu klientu noskaņojuma tendences jūsu datu laika diapazonā. Šis skats var palīdzēt novērtēt sezonālo akciju, produktu izlaišanas vai citu laikā ierobežotu intervenču ietekmi uz klientu noskaņojumu. Skatiet diagrammu, nolaižamajā izvēlnē atlasot interesējošo gadu. 

  :::image type="content" source="media/sentiment-score-over-time.png" alt-text="Vēstures diagramma ar noskaņojuma rādītāju laika gaitā, kas attēlota kā līnija.":::
 
- **Noskaņojums starp uzņēmējdarbības aspektiem**: Šajā tabulā ir uzskaitīts vidējais noskaņojums starp uzņēmējdarbības aspektiem. Tas var palīdzēt jums novērtēt, kuri jūsu biznesa aspekti jau apmierina klientus vai kuri ir saistīti ar lielāku uzmanību. Atsauksmju ieraksti, kas neatbilst nevienam no atbalstītajiem uzņēmējdarbības aspektiem, tiek iedalīti kategorijās **Citi**. Tabula ir sakārtota alfabētiskā secībā pēc noklusējuma. Kārtošanu var modificēt, atlasot tabulas galveni.

  :::image type="content" source="media/sentiment-across-business-aspects.png" alt-text="Uzņēmējdarbības aspektu saraksts ar saistīto noskaņojuma vērtību un to klientu skaitu, kuri to piemin.":::
 
  Atlasiet uzņēmējdarbības aspekta nosaukumu, lai skatītu papildinformāciju par to, kā modelis identificē uzņēmējdarbības aspektu. Šajā rūtī ir divas daļas: 

  - **Ietekmīgi vārdi**: parāda populārākos vārdus, kas ietekmēja AI modeļa uzņēmējdarbības aspekta identificēšanu klientu atsauksmēs. 
    **Rādīt aizvainojošus vārdus**: ļauj sarakstā iekļaut aizvainojošus vārdus no sākotnējiem klientu atsauksmju datiem. Pēc noklusējuma tas ir izslēgts.  Aizvainojošu vārdu maskēšanu nodrošina AI modelis, un tā var neatklāt visus aizvainojošos vārdus. Mēs turpinām atkārtot un apmācīt klasifikatoru, lai nodrošinātu optimālu veiktspēju. Ja konstatējat aizvainojošu vārdu, kas netika filtrēts, kā paredzēts, informējiet mūs. 
    
    :::image type="content" source="media/offensive-words-sentiment.png" alt-text="Ietekmīgu vārdu saraksts ar slēdzi, lai parādītu vai paslēptu aizvainojošus vārdus.":::
 
  - **Atsauksmju paraugi**: datos tiek rādīti faktiskie atsauksmju ieraksti. Vārdi ir kodēti ar krāsu atbilstoši to ietekmei uz biznesa aspekta identificēšanu. 


### <a name="influential-words-analysis-tab"></a>Ietekmīgu vārdu analīzes cilne

Ir trīs papildu informācijas sadaļas, kas izskaidro, kā darbojas noskaņojuma modelis.
  
1. **Populārākie vārdi, kas veicina pozitīvu noskaņojumu**: parāda populārākos vārdus, kas ietekmēja AI modeļa pozitīvā noskaņojuma noteikšanu klientu atsauksmēs.  
2. **Populārākie vārdi, kas veicina negatīvu noskaņojumu**: parāda populārākos vārdus, kas ietekmēja AI modeļa negatīvo noskaņojumu klientu atsauksmēs.  
3. **Atsauksmju paraugi**: parāda faktiskos atsauksmju ierakstus, vienu ar negatīvu noskaņojumu un tādu, kurā ir pozitīvs noskaņojums. Vārdi atsauksmju ierakstos tiek izcelti atbilstoši to ieguldījumam piešķirtajā noskaņojuma rādītājā. Vārdi, kas veicina pozitīvu noskaņojuma rādītāju, ir izcelti zaļā krāsā. Vārdi, kas veicina negatīvu rezultātu, ir izcelti sarkanā krāsā.
   Atlasiet **Skatīt vairāk**, lai ielādētu vairāk atsauksmju paraugu, kas sniedz papildinformāciju un kontekstu par to, kā darbojas noskaņojuma modelis.
   
   :::image type="content" source="media/sentiment-feedback-samples.png" alt-text="Noskaņojuma analīzes piemēri par klientu atsauksmēm.":::
 
**Rādīt aizvainojošus vārdus**: ļauj sarakstā iekļaut aizvainojošus vārdus no sākotnējiem klientu atsauksmju datiem. Pēc noklusējuma tas ir izslēgts.  Aizvainojošu vārdu maskēšanu nodrošina AI modelis, un tā var neatklāt visus aizvainojošos vārdus. Mēs turpinām atkārtot un apmācīt klasifikatoru, lai nodrošinātu optimālu veiktspēju. Ja konstatējat aizvainojošu vārdu, kas netika filtrēts, kā paredzēts, informējiet mūs. 

## <a name="act-on-analysis-results"></a>Rīcība attiecībā uz analīžu rezultātiem

Varat viegli sākt veidot jaunus klientu segmentus no noskaņojuma analīzes rezultātu lapas, lapas Modeļa rezultāts augšdaļā atlasot **Izveidot segmentus**.

:::image type="content" source="media/create-segment-model.png" alt-text="Komandjosla ar opcijām prognoze modeļos.":::
 
## <a name="potential-bias"></a>Iespējamā neobjektivitāte

Tāpat kā ar jebkuru funkciju, kas izmanto prognozējošu mākslīgo intelektu, jums jāapzinās iespējamā neobjektivitāte datos, kurus izmantojat, lai prognozētu klientu noskaņojumu. Piemēram, ja atsauksmes apkopojat tikai digitāli, varat palaist garām atsauksmes no klientiem, kuri galvenokārt veic darījumus ar jums personīgi, kas var ietekmēt līdzekļa izvadi.

Tā kā šī funkcija izmanto automatizētus līdzekļus, lai novērtētu datus un veiktu prognozes, pamatojoties uz šiem datiem, tai ir iespēja to izmantot kā profilēšanas metodi, jo šis termins ir definēts Vispārīgajā datu aizsardzības regulā ("VDAR"). Šī līdzekļa izmantošana datu apstrādāšanai var būt pakļauta VDAR vai citiem tiesību aktiem un noteikumiem. Jūs esat atbildīgs par to, lai nodrošinātu, ka, izmantojot Dynamics 365 Customer Insights, tostarp noskaņojuma analīzi, jūs ievērojat visus piemērojamos likumus un noteikumus, tostarp likumus, kas saistīti ar privātumu, personas datiem, biometriskajiem datiem, datu aizsardzību un saziņas konfidencialitāti.

[!INCLUDE [footer-include](includes/footer-banner.md)]

