---
title: Algoritmiskās mācīšanās studijas (klasiskais) eksperimenti
description: Izmantojiet Azure algoritmiskās mācības (klasiskais) modeļus programmā Dynamics 365 Customer Insights.
ms.date: 12/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: ameetj
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 71881f7e1f9448fe0a7d6d92b8102b8b42de7c2a
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598348"
---
# <a name="use-models-based-on-azure-machine-learning-studio-classic"></a>Izmantojiet Azure algoritmiskās mācības studijas (klasiskais) modeļus programmā .

Vienotie dati Dynamics 365 Customer Insights ir avots, kas paredzēts algoritmiskās mācīšanās modeļu izveidei, kas var radīt papildu biznesa ieskatus. Customer Insights integrējas ar algoritmiskās mācīšanās studiju (klasiskais) un Azure algoritmisko mācīšanos, lai izmantotu savus pielāgotos modeļus. Lai uzzinātu, kā Azure algoritmiskā mācīšanās izstrādātie modeļi ir integrēti ar Customer Insights, skatiet sadaļu [Azure algoritmiskās mācīšanās eksperimenti](azure-machine-learning-experiments.md).

## <a name="prerequisites"></a>Priekšnosacījumi

- Piekļuve Customer Insights
- Aktīvs Azure Enterprise abonements
- [Vienoti klientu profili](data-unification.md)
- [Entītijas eksportēšanas uz Azure Blob krātuvi](export-azure-blob-storage.md) iestatīšana

## <a name="set-up-machine-learning-studio-classic"></a>Algoritmiskā mācīšanās studijas (klasiskais) iestatīšana

Vispirms ir jāizveido darbvieta un jāatver algoritmiskās mācīšanās studija (klasiskais).

1. Dodieties uz [https://www.portal.azure.com](https://www.portal.azure.com/) un pierakstieties.

1. Atlasiet **Resursa izveide**.

1. Meklējiet **Algoritmiskās mācīšanās studijas darbvieta** un atlasiet **Izveidot**.

1. Ievadiet nepieciešamo informāciju, lai [izveidotu darbvietu](/azure/machine-learning/studio/create-workspace). Izvēlieties **Tīmekļa servisa plāna cenas rindu**, pamatojoties uz importējamo datu apjomu. Lai iegūtu vislabākos rezultātus, atlasiet **Atrašanās vietu**, kas jums ģeogrāfiski ir vistuvāk.

1. Pēc resursa izveides tiks parādīts algoritmiskās mācīšanās studijas darbvietas informācijas panelis. Atlasiet **Palaist algoritmiskās mācīšanās studiju**.

   ![Azure algoritmiskās mācīšanās studijas lietotāja interfeiss](media/azure-machine-learning-studio.png)

## <a name="work-with-azure-machine-learning-studio"></a>Darbs ar Azure algoritmiskās mācīšanās studiju

Tagad varat izveidot jaunu eksperimentu vai importēt esošu eksperimenta veidni no paraugu galerijas. Ir parauga eksperimenti ar trim standarta scenārijiem:

- [Zuduma prognoze](#churn-analysis)

- [Klienta ilgtermiņa vērtība](#customer-lifetime-value-prediction)

- [Produkta ieteikums vai nākamā labākā darbība](#productrecommendation-or-next-best-action)

1. Ja izveidojat jaunu eksperimentu vai izmantojat eksperimenta veidni no galerijas, jums ir jākonfigurē **Datu importēšanas** rekvizīti. Izmantojiet vadīto pieredzi vai tieši sniedziet detalizētu informāciju, lai piekļūtu Azure BLOB krātuvei, kurā ir jūsu dati.  

   ![Azure algoritmiskās mācīšanās studijas eksperiments](media/azure-machine-learning-studio-experiment.png)

1. Tagad varat izveidot pielāgotu apstrādes konveijeru, lai notīrītu un pirmsapstrādātu datus, izvilktu līdzekļus un apmācītu piemēroto modeli.

1. Pārbaudiet un optimizējiet modeļa sniegumu.

1. Kad jūs apmierina modeļa kvalitāte, atlasiet **Iestatīt tīmekļa pakalpojumu** > **Predikatīvais tīmekļa pakalpojums**. Šī opcija importē apmācīto modeli un līdzekļu konveijeru no apmācību eksperimenta uz predikatīvo pakalpojumu. Predikatīvais pakalpojums var izmantot citu ievades datu kopu ar sistēmu, kas izmantota eksperimenta apmācībā prognožu veikšanai.

   ![Predikatīvā tīmekļa pakalpojuma iestatīšana](media/predictive-webservice-control.png)

1. Kolīdz predikatīvais tīmekļa pakalpojuma eksperiments ir izdevies, jūs varat to izmantot automātiskai plānošanai. Lai tīmekļa pakalpojums darbotos kopā ar Customer Insights, atlasiet **Izmantot tīmekļa pakalpojumu** > **Izmantot tīmekļa pakalpojuma (jauns) priekšskatījumu**. [Papildinformācija par tīmekļa pakalpojuma izmantošanu](/azure/machine-learning/studio/deploy-a-machine-learning-web-service)

   ![Predikatīvā tīmekļa pakalpojuma izmantošana](media/predictive-webservice-deploy.png)

## <a name="sample-models-from-the-gallery"></a>Paraugu modeļi no galerijas

Šī raksta modeļiem izmantosim fiktīvu Contoso Hotel scenāriju. Contoso Hotel apkopo šādus datus:

- CRM dati, kas sastāv no viesnīcas uzturēšanās darbības. Datu kopa ietver informāciju par uzturēšanās datiem katram reģistrētajam klientam. Tajā arī ietverta informācija par rezervējumu, numuru veidiem, tēriņu informācija un tā tālāk. Dati aptver četrus gadus — no 2014. gada janvāra līdz 2018. gada janvārim.
- Viesnīcas viesu klientu profili. Šie profili satur informāciju par katru klientu, tostarp viņu vārdu un uzvārdu, dzimšanas datumu, pasta adresi, dzimumu un tālruņa numuru.
- Viesnīcas piedāvāto pakalpojumu, piemēram, spa, veļas mazgātavas, WiFi vai kurjera, izmantojums. Šī informācija tiek reģistrēta katram reģistrētajam klientam. Parasti pakalpojumu izmantošana ir saistīta ar uzturēšanos. Dažos gadījumos pakalpojumus var izmantot klienti, kuri viesnīcā nemitinās.

## <a name="churn-analysis"></a>Zuduma analīze

Zuduma analīze attiecas uz dažādām biznesa jomām. Šajā piemērā mēs aplūkosim pakalpojuma zudumu, jo īpaši augstāk aprakstīto viesnīcas pakalpojumu kontekstā. Tajā sniegts darba piemērs gala modeļa konveijeram, kuru var izmantot kā sākumpunktu jebkura cita veida zuduma modelim.

### <a name="definition-of-churn"></a>Zuduma definīcija

Zuduma definīcija var atšķirties atkarībā no scenārija. Piemēram, viesi, kurš nav viesnīcu apmeklējis pēdējā gada laikā, vajadzētu marķēt kā zudušu.  

Eksperimenta veidni var importēt no galerijas. Vispirms nodrošiniet, ka no Azure Blob krātuves importējat datus **Viesnīcas uzturēšanas darbībai**, **Klientu datiem** un **Pakalpojuma lietojuma datiem**.

   ![Datu importēšana zuduma modelim](media/import-data-azure-blob-storage.png)

### <a name="featurization"></a>Līdzekļu izmantošana

Pamatojoties uz zuduma definīciju, mēs vispirms identificējam neapstrādātos līdzekļus, kuri ietekmēs etiķeti. Pēc tam mēs apstrādāsim šos neapstrādātos līdzekļus, lai veidotu skaitliskus līdzekļus, kurus var izmantot algoritmiskās mācīšanās modeļos. Datu integrācija notiek ar Customer Insights, lai šīs tabulas varētu pievienot, izmantojot *Klienta ID*.

   ![Importēto datu apvienošana](media/join-imported-data.png)

Līdzekļu izveide modeļa veidošanai zuduma analīzei var būt nedaudz sarežģīta. Dati ir laika funkcija ar jaunu viesnīcas darbību, kas tiek fiksēta katru dienu. Līdzekļu izveides laikā mēs vēlamies ģenerēt statiskus līdzekļus no dinamiskiem datiem. Šajā gadījumā mēs ģenerējam vairākus līdzekļus no viesnīcas darbības ar viena gada slīdošo logu. Mēs arī izvēršam kategorijas līdzekļus, piemēram, numura veidu vai rezervācijas veidu atsevišķos līdzekļos, izmantojot viena karsto kodēšanu.  

Līdzekļu galīgais skats:

| **Skaitlis**  | **Original_Column**          | **Atvasinātie līdzekļi**                                                                                                                      |
|-------------|------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------|
| 1           | Numura veids                    | RoomTypeLargeCount, RoomTypeSmallCount                                                                                                    |
| 2           | Rezervācijas tips                 | BookingTypeOnlineCount, BookingTypePhoneCallCount                                                                                         |
| 3           | Ceļošanas kategorija              | TravelCategoryBusinessCount, TravelCategoryLeisureCount                                                                                   |
| 4           | Iztērētie dolāri                | TotalDollarSpent                                                                                                                          |
| 5           | Reģistrēšanās un izrakstīšanās datumi  | StayDayCount, StayDayCount2016, StayDayCount2015, StayDayCount2014, StayCount, StayCount2016. StayCount2015, StayCount2014                |
| 6           | Servisa lietojums                | UsageTenure, ConciergeUsage, CourierUsage, DryCleaningUsage, GymUsage, PhoneUsage, RestaurantUsage, SpaUsage, TelevisionUsage, WifiUsage  |

### <a name="model-selection"></a>Modeļa atlase

Tagad mums ir jāizvēlas optimālais lietojamais algoritms. Šajā gadījumā vairums līdzekļu ir balstīti kategorijas līdzekļos. Parasti lēmumu kokā balstītie modeļi darbojas labi. Ja ir tikai skaitliski līdzekļi, neironu tīkli varētu būt labāka izvēle. Atbalsta vektoru mašīna (SVM) arī ir labs kandidāts šādās situācijās; tomēr ir nepieciešama neliela saskaņošana, lai iegūtu labākos rezultātus. Mēs izvēlamies **Divu klašu stiprināto lēmuma koku** kā pirmo modeli, kam seko **Divu klašu SVM** kā otrais modelis. Azure algoritmiskās mācīšanās studija ļauj veikt A/B testēšanu, tāpēc ir labi sākt ar diviem modeļiem, nevis vienu.

Šajā attēlā parādīts modeļa apmācības un novērtēšanas konveijers Azure algoritmiskās mācīšanās studijai:

![Zuduma modelis Azure algoritmiskās mācīšanās studijā](media/azure-machine-learning-model.png)

Mēs arī izmantojam tehniku, ko sauc par **Permutācijas līdzekļa svarīgumu**, kas ir būtisks modeļa optimizācijas aspekts. Iebūvētajiem modeļiem ir mazs vai nekāds ieskats jebkura konkrētā līdzekļa ietekmē uz gala prognozi. Līdzekļa svarīguma kalkulators izmanto pielāgotu algoritmu, lai aprēķinātu atsevišķu līdzekļu ietekmi uz konkrēta modeļa iznākumu. Līdzekļa svarīgums ir normalizēts starp +1 un -1. Negatīva ietekme nozīmē, ka atbilstošajam līdzeklim ir pretēja ietekme uz iznākumu un tas ir jāizņem no modeļa. Pozitīva ietekme norāda uz to, ka līdzeklim ir pamatīgs pienesums prognozei. Šīs vērtības nav korelācijas koeficienti, jo tie ir cita metrika. Papildinformāciju skatiet tēmā [Permutāciju līdzekļa svarīgums](/azure/machine-learning/studio-module-reference/permutation-feature-importance).

Viss [zuduma eksperiments ir pieejams Azure AI galerijā](https://gallery.azure.ai/Experiment/Hotel-Churn-Predictive-Exp).

## <a name="customer-lifetime-value-prediction"></a>Klienta ilgtermiņa vērtības prognoze

Klienta ilgtermiņa vērtības (CLTV) aprēķins ir viena no galvenajām metrikām, kuru uzņēmums var izmantot, lai novērtētu un segmentētu savus klientus. Viesnīcu uzņēmējdarbībā ir būtiski pazīt savus klientus. Piemēram, izpratne par faktoriem, kas veido labus klientus, ir būtiska informācija. Tā palīdz viesnīcu vadībai novērtēt, uz kuriem līdzekļiem ir jākoncentrējas un kuri ir jāuzlabo, lai apmierinātu labi maksājošos klientus. Šiem lēmumiem var būt tieša ietekme uz pārdošanu un peļņu.  

### <a name="definition-of-cltv"></a>CLTV definīcija

Šajā piemērā mēs definējam klienta CLTV kā kopējo dolāra summu, kuru klients, paredzams, iztērēs nākamo 365 dienu laikā. Mēs izmantosim pēdējo triju gadu datus par visiem klientiem, lai prognozētu šo vērtību.

### <a name="featurization"></a>Līdzekļu izmantošana

Šajā gadījumā līdzekļu izmantošana būs diezgan līdzīga kā zuduma scenārijā. Taču etiķetes un prognozētās vērtības atšķiras no augstāk noteiktajām.

### <a name="model-selection"></a>Modeļa atlase

CLTV prognozēšana ir regresijas problēma, jo prognozētā vērtība ir pozitīvi novērtēts nepārtraukts mainīgais. Pamatojoties uz līdzekļa iespējām, atlasām **Paātrināta lēmumu koku regresiju** kā vienu algoritmu un **Neironu tīkla regresiju** kā otru algoritmu modeļa apmācīšanai.

## <a name="product-recommendation-or-next-best-action"></a>Produkta ieteikums vai nākošā labākā darbība

Produkta ieteikums viesnīcas scenārijā tiek interpretēts kā viesnīcas klientiem piedāvāto pakalpojumu ieteikšana. Mērķis ir atlasīt piemērotos pakalpojumus klientiem tā, lai tiek maksimizēts to lietojums. Tas ir līdzīgs filmu ieteikumiem video straumēšanas pakalpojumu lietotājiem.

### <a name="definition-of-product-recommendation-or-next-best-action"></a>Produkta ieteikuma vai nākamās labākās darbības definīcija

Mēs definējam mērķi kā pakalpojuma lietošanas dolāra summas maksimizēšanu, piedāvājot atbilstošākos pakalpojumus viesnīcas klientiem, atbilstoši viņu interesēm.

### <a name="featurization"></a>Līdzekļu izmantošana

Tāpat kā zuduma modelī, mēs apvienojam viesnīcas ServiceCustomerID ar CustomerID, lai veidotu konsekventus ieteikumus katram CustomerID.

![Ieteikumu modeļa līdzekļu izmantošana](media/azure-machine-learning-model-featurization.png)

Dati tiek iegūti no trim dažādām entītijām, un līdzekļi tiek atvasināti no tām. Ieteikuma problēmas līdzekļu izveidošana atšķiras no zuduma vai CLTV scenārijiem. Ieteikumu modelim ir nepieciešami ievades dati trīs līdzekļu kopu veidā.

### <a name="model-selection"></a>Modeļa atlase

Mēs prognozējam produktus vai pakalpojumus, izmantojot algoritmu, ko sauc par **Apmācības Matchbox ieteicēju**, lai apmācītu ieteikumu modeli.

![Produkta ieteikuma algoritms](media/azure-machine-learning-model-recommendation-algorithm.png)

Trīs ievades porti **Apmācības Matchbox ieteicēja** modelī izmanto apmācību pakalpojuma izmantošanas datus, klienta aprakstu (neobligāti) un pakalpojuma aprakstu. Ir trīs dažādi veidi, kā novērtēt modeli. Viens ir modeļa novērtējums, kurā Normalizētā kumulatīvais pieaugums ar atlaidi (NDCG) tiek aprēķināts, lai sarindotu novērtētos elementus. Šajā eksperimentā NDCG rezultāts ir 0,97. Pārējās divas opcijas ir novērtēt modeli visā ieteicamā pakalpojuma katalogā vai novērtēt tikai elementus, kurus lietotāji pirms tam nav izmantojuši.

Raugoties tālāk ieteikumu izplatīšanā visā pakalpojuma katalogā, mēs pamanām, ka tālrunis, WiFi un kurjers ir galvenie pakalpojumi, kurus ieteikt. Tas atbilst tam, ko mēs atklājām pakalpojuma patēriņa datu sadalījumā:

![Ieteikumu modeļa izvade](media/azure-machine-learning-model-output.png)

Visam [produkta ieteikuma eksperimentam var piekļūt Azure AI galerijā.](https://gallery.azure.ai/Experiment/Recommendation-4)

## <a name="integrate-custom-models"></a>Pielāgoto modeļu integrēšana

Lai izmantotu šīs prognozes programmā Customer Insights, prognozes ir **jāeksportē** kopā ar klienta ID. [Eksportējiet tos uz to pašu Azure Blob krātuves vietu](/azure/storage/common/storage-import-export-data-from-blobs), kurā tiek eksportēti avota dati. Prognozējošo tīmekļa pakalpojumu var ieplānot tā, lai tas darbotos regulāri un atjauninātu rezultātus.

Pielāgotajā modelī ģenerētos datus var izmantot, lai turpinātu klientu datu bagātināšanu. Papildinformācijai skatiet [Pielāgoti algoritmiskās mācīšanās modeļi](custom-models.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]