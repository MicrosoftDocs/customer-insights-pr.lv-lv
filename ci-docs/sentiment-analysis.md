---
title: Klientu atsauksmju noskaņojuma analīze (priekšskatījums)
description: Uzziniet, kā izmantot noskaņojuma analīzes modeli klientu atsauksmēm Dynamics 365 Customer Insights.
ms.date: 09/14/2022
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: wmelewong
ms.author: wameng
manager: shellyha
ms.openlocfilehash: 61ce9fb18efa6152dddb2e31f4fd0366a31ac2c7
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610475"
---
# <a name="analyze-sentiment-in-customer-feedback-preview"></a>Noskaņojuma analīze klientu atsauksmēs (priekšskatījums)

Noskaņojuma analīze ļauj sintezēt klientu noskaņojumu un identificēt biznesa aspektus kā uzlabojumu iespējas. Šis Customer Insights līdzeklis palīdz jums saprast, kas darbojas labi un kas jums ir jārisina. Tas var palīdzēt jums virzīt biznesa darbības, kas nodrošina pieredzi, kas nodrošina augstu klientu apmierinātību un lojalitāti.

## <a name="overview"></a>Pārskats

Noskaņojuma analīzes līdzeklis ģenerē divus atvasinātos ieskatus par katru klienta ID. Noskaņojuma rādītājs (no -5 līdz 5) un saraksts ar piemērojamiem uzņēmējdarbības aspektiem (uzņēmējdarbības jomām), kas kopā palīdz labāk izprast klientu atsauksmes.

Šī analīze palīdz jums:
- Iegūstiet pārskatu par klientu noskaņojumu attiecībā uz zīmolu vai organizāciju
- Identificējiet klientus ar negatīvu noskaņojumu, lai koncentrētos uz savām kampaņām un piesaisti, un optimizējiet, lai gūtu lielāku peļņu  
- Identificējiet biznesa aspektus ar problēmām, uz kurām norādījuši klienti  
- Segmentējiet klientus, pamatojoties uz viņu noskaņojumu rādīt personalizētas kampaņas ar mērķtiecīgu pārdošanu, mārketingu un atbalsta pasākumiem
- Optimizējiet biznesa operācijas, pievēršoties problemātiskām jomām vai iespējām, kuras minēja klienti
- Atzīstiet biznesa aspektus, kas darbojas labi, un apbalvojiet laimīgus klientus, izmantojot lojalitātes un veicināšanas programmas

Modelis nodrošina sarakstu ar vārdiem, kas ietekmēja modeļa lēmumu atsauksmju komentāriem piešķirt konkrētu noskaņojuma rādītāju vai biznesa aspektu.  

Mēs izmantojam divus **dabiskās valodas apstrādes (NLP) modeļus**: pirmais katram atsauksmju komentāram piešķir noskaņojuma rādītāju. Otrais modelis katru atsauksmi saista ar visiem piemērojamajiem uzņēmējdarbības aspektiem. Modeļi ir apmācīti, pamatojoties uz publiskiem datiem no avotiem sociālajos medijos, mazumtirdzniecībā, restorānos, patēriņa produktos un automobiļu rūpniecībā.
  
Iepriekš definētie uzņēmējdarbības aspekti, kas modelim jāsaista ar atsauksmju datiem, ir šādi:
- Uzņēmumu pārvaldība
- Norēķināšanās un maksājums
- Klientu atbalsts
- Paņemšana veikalā
- Iepakojuma piegāde un atgriešana
- Iepriekšēja pasūtīšana
- Cenrādis
- Konfidencialitāte un drošība
- Akcijas un balvas
- Saņemšana un garantija
- Atgriezto preču apmaiņa un atcelšana
- Izpildes precizitāte
- Vietnes/programmas kvalitāte

> [!NOTE]
> Pašlaik mēs atbalstām tikai noskaņojuma analīzi par angļu klientu atsauksmēm. Nākotnē tiks atbalstītas vēl citas valodas. Ja tiek augšupielādētas atsauksmes citās valodās, modelis joprojām atgriezīs rezultātus. Tomēr šie rezultāti nebūs precīzi.

## <a name="prerequisites"></a>Priekšnoteikumi

- Vismaz [līdzstrādnieku atļaujas](permissions.md)
- [Vienoti](data-unification.md) teksta atsauksmju dati. Ļoti ieteicams [konfigurēt atsauksmju datu entītijas kā semantiska tipa darbības entītijas](map-entities.md#select-primary-key-and-semantic-type-for-attributes) (atsauksmju tips).
- Vienotais klienta ID (UCID) no datu apvienošanas, lai saskaņotu teksta atsauksmju datu ierakstus ar atsevišķu klientu.
- Atsauksmju ID
- Atgriezeniskās saites laikspiedols
- Atsauksmju teksts

Customer Insights var apstrādāt līdz pat 10 miljoniem atsauksmju ierakstu vienai modeļa izpildei. Modelis var analizēt atsauksmju komentārus līdz 128 vārdiem. Ja atsauksmju komentārs ir garāks, analīzē tiek ņemti vērā tikai pirmie 128 vārdi.

> [!NOTE]
> Var konfigurēt tikai vienu atsauksmju entītiju. Ja ir vairākas atsauksmju entītijas, apvienojiet tās Power Query pirms datu uzņemšanas.

## <a name="configure-a-sentiment-analysis"></a>Noskaņojuma analīzes konfigurēšana

1. Dodieties uz **izlūkošanas** > **prognozēm**.

1. Cilnē **Izveide** atlasiet **Izmantot modeli** elementā **Klientu noskaņojuma analīze (priekšskatījums).**

1. Atlasiet **Sākt darbu**.

1. **Piešķiriet analīzei nosaukumu** un norādiet **biznesa aspekta izvades entītijas nosaukumu** un **sentimenta rādītāja izvades entītijas nosaukumu**.

1. Atlasiet **Tālāk**.

1. Atlasiet **Pievienot datus** klientu **atsauksmēm**.

1. Atlasiet semantiskās darbības tipu **Atsauksmes**, kas satur atsauksmju datus. Ja darbība nav iestatīta, atlasiet **šeit** un izveidojiet to.

   :::image type="content" source="media/sentiment-add-feedback-activities.png" alt-text="Konfigurācijas darbība, lai atlasītu atgriezeniskās saites aktivitātes noskaņojuma analīzei.":::

1. Atlasiet darbības, kas jāizmanto šai noskaņojuma analīzei, un pēc tam atlasiet **Tālāk**.

1. Kartējiet datu atribūtus uz modeļa atribūtiem. 

1. Atlasiet **Saglabāt**.

1. Atlasiet **Tālāk**. Darbība Pārskatīšana **un izpilde** parāda konfigurācijas kopsavilkumu un nodrošina iespēju veikt izmaiņas pirms analīzes izveides.

1. Atlasiet **Rediģēt**, veicot kādu no darbībām, lai pārskatītu un veiktu izmaiņas.

1. Ja esat apmierināts ar atlasi, atlasiet **Saglabāt un palaist**, lai sāktu modeļa darbību. Atlasiet **Gatavs**. Cilne **Manas prognozes** tiek rādīta, kamēr tiek veidota prognoze. Atkarībā no prognozēšanas laikā izmantojamā datu daudzuma process var aizņemt vairākas stundas.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-analysis-results"></a>Skatīt analīzes rezultātus

1. Dodieties uz **izlūkošanas** > **prognozēm**.

1. **Cilnē Manas prognozes** atlasiet prognoze, kuru vēlaties skatīt.

Ir divas rezultātu cilnes.

### <a name="sumary-tab"></a>Kopsavilkuma cilne

Rezultātu lapā ir četras primārās datu sadaļas.

- **Vidējais noskaņojuma rādītājs**: Noskaņojuma rādītāji palīdz izprast visu klientu vispārējo noskaņojumu.
  - **Negatīvs** (-5 > 2)
  - **Neitrāls** (-1 > 1)
  - **Pozitīvs** (2 > 5)
  
  :::image type="content" source="media/overall-customer-sentiment.png" alt-text="Kopējā klientu noskaņojuma vizuālais attēlojums.":::

- **Klientu sadalījums pēc noskaņojuma rādītāja**: Klienti tiek iedalīti negatīvās, neitrālās un pozitīvās grupās, pamatojoties uz viņu noskaņojuma rādītājiem. Virziet kursoru virs histogrammas joslām, lai redzētu klientu skaitu un vidējo noskaņojuma rādītāju katrā grupā. Šie dati var palīdzēt izveidot [klientu](prediction-based-segment.md) segmentus, pamatojoties uz viņu noskaņojuma rādītājiem.  

  :::image type="content" source="media/distribution-customer-sentiment.png" alt-text="Joslu diagramma, kurā parādīts klientu noskaņojums visās trīs noskaņojuma grupās.":::

- **Vidējais noskaņojuma rādītājs laika** gaitā: klientu noskaņojums laika gaitā var mainīties. Mēs nodrošinām jūsu klientu noskaņojuma tendences jūsu datu laika diapazonā. Šis skats palīdz novērtēt sezonālo akciju, produktu izlaišanas vai citu laikā ierobežotu intervenču ietekmi uz klientu noskaņojumu. Skatiet diagrammu, nolaižamajā izvēlnē atlasot interesējošo gadu.

  :::image type="content" source="media/sentiment-score-over-time.png" alt-text="Vēstures diagramma ar noskaņojuma rādītāju laika gaitā, kas attēlota kā līnija.":::

- **Noskaņojums starp uzņēmējdarbības aspektiem**: Vidējais noskaņojums starp uzņēmējdarbības aspektiem palīdz jums novērtēt, kuri jūsu uzņēmuma aspekti jau apmierina klientus vai prasa lielāku uzmanību. Atsauksmju ieraksti, kas neatbilst nevienam no atbalstītajiem uzņēmējdarbības aspektiem, tiek iedalīti kategorijās **Citi**. Kārtojiet datus, atlasot jebkuru kolonnu.

  :::image type="content" source="media/sentiment-across-business-aspects.png" alt-text="Uzņēmējdarbības aspektu saraksts ar saistīto noskaņojuma vērtību un to klientu skaitu, kuri to piemin.":::

  Atlasiet uzņēmējdarbības aspekta nosaukumu, lai redzētu, kā modelis identificē uzņēmējdarbības aspektu:

  - **Ietekmīgi vārdi**: populārākie vārdi, kas ietekmēja AI modeļa uzņēmējdarbības aspekta identificēšanu klientu atsauksmēs.
    **Rādīt aizvainojošus vārdus**: ļauj sarakstā iekļaut aizvainojošus vārdus no sākotnējiem klientu atsauksmju datiem. Pēc noklusējuma tas ir izslēgts.  Aizvainojošu vārdu maskēšanu nodrošina AI modelis, un tā var neatklāt visus aizvainojošos vārdus. Ja konstatējat aizvainojošu vārdu, kas netika filtrēts, kā paredzēts, informējiet mūs.

    :::image type="content" source="media/offensive-words-sentiment.png" alt-text="Ietekmīgu vārdu saraksts ar slēdzi, lai parādītu vai paslēptu aizvainojošus vārdus.":::

  - **Atsauksmju paraugi**: faktiskie atsauksmju ieraksti jūsu datos. Vārdi ir kodēti ar krāsu atbilstoši to ietekmei uz biznesa aspekta identificēšanu.

### <a name="influential-words-analysis-tab"></a>Ietekmīgu vārdu analīzes cilne

Ir trīs papildu informācijas sadaļas, kas izskaidro, kā darbojas noskaņojuma modelis.
  
- **Populārākie vārdi, kas veicina pozitīvu noskaņojumu**: populārākie vārdi, kas ietekmēja AI modeļa pozitīvā noskaņojuma noteikšanu klientu atsauksmēs.  

- **Populārākie vārdi, kas veicina negatīvu noskaņojumu**: populārākie vārdi, kas ietekmēja AI modeļa negatīvā noskaņojuma identificēšanu klientu atsauksmēs.

- **Atsauksmju paraugi**: faktiskie atsauksmju ieraksti, tādi, kuriem ir negatīvs noskaņojums un kuriem ir pozitīvs noskaņojums. Vārdi atsauksmju ierakstos tiek izcelti atbilstoši to ieguldījumam piešķirtajā noskaņojuma rādītājā. Vārdi, kas veicina pozitīvu noskaņojuma rādītāju, ir izcelti zaļā krāsā. Vārdi, kas veicina negatīvu rezultātu, ir izcelti sarkanā krāsā.
   Atlasiet **Skatīt vairāk**, lai ielādētu vairāk atsauksmju paraugu.
  
   :::image type="content" source="media/sentiment-feedback-samples.png" alt-text="Noskaņojuma analīzes piemēri par klientu atsauksmēm.":::

**Rādīt aizvainojošus vārdus**: ļauj sarakstā iekļaut aizvainojošus vārdus no sākotnējiem klientu atsauksmju datiem. Pēc noklusējuma tas ir izslēgts.  Aizvainojošu vārdu maskēšanu nodrošina AI modelis, un tā var neatklāt visus aizvainojošos vārdus. Ja konstatējat aizvainojošu vārdu, kas netika filtrēts, kā paredzēts, informējiet mūs.

## <a name="act-on-analysis-results"></a>Rīcība attiecībā uz analīžu rezultātiem

Lai izveidotu jaunus klientu segmentus no noskaņojuma analīzes rezultātiem, lapas Modeļa rezultāts augšdaļā atlasiet **Izveidot segmentus**.

## <a name="potential-bias"></a>Iespējamā neobjektivitāte

Tāpat kā ar jebkuru funkciju, kas izmanto prognozējošu mākslīgo intelektu, datos, kurus izmantojat, lai prognozētu klientu noskaņojumu, var būt iespējama neobjektivitāte. Piemēram, ja atsauksmes apkopojat tikai digitāli, iespējams, palaidīsit garām atsauksmes no klientiem, kuri galvenokārt veic darījumus ar jums personīgi, kas ietekmē līdzekļa izvadi.

Tā kā šī funkcija izmanto automatizētus līdzekļus, lai novērtētu datus un veiktu prognozes, pamatojoties uz šiem datiem, tai ir iespēja to izmantot kā profilēšanas metodi, jo šis termins ir definēts Vispārīgajā datu aizsardzības regulā ("VDAR"). Šī līdzekļa izmantošana datu apstrādāšanai var būt pakļauta VDAR vai citiem tiesību aktiem un noteikumiem. Jūs esat atbildīgs par to, lai nodrošinātu, ka, izmantojot Dynamics 365 Customer Insights, tostarp noskaņojuma analīzi, jūs ievērojat visus piemērojamos likumus un noteikumus, tostarp likumus, kas saistīti ar privātumu, personas datiem, biometriskajiem datiem, datu aizsardzību un saziņas konfidencialitāti.

[!INCLUDE [footer-include](includes/footer-banner.md)]

