---
title: Aizpildiet savus daļējos datus ar prognozēm
description: Izmantojiet prognozes, lai aizpildītu nepilnīgus klientu datus.
ms.date: 11/01/2021
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-predictions
- ci-custom-models
- customerInsights
ms.openlocfilehash: 7e93670007db27d13b84d7516f56830988da083e
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082515"
---
# <a name="complete-your-partial-data-with-predictions-deprecated"></a>Pabeidziet savus daļējos datus, izmantojot prognozes (novecojušas)

> [!IMPORTANT]
> Šī funkcija būs **novecojusi no** 2021. gada 5. novembra **·**. Pašreizējās ieviešanas turpinās darboties, līdz līdzeklis tiks noņemts, taču jūs nevarēsit izveidot jaunas integrācijas, izmantojot tālāk sniegtos norādījumus.

Prognozes ļauj viegli izveidot prognozētās vērtības, kas var uzlabot jūsu izpratni par klientu. Lapā **Informācija** > **Prognozes** varat atlasīt **Manas prognozes**, lai skatītu prognozes, kuras konfigurējāt citās Customer Insights daļās, un lai varētu turpināt tās pielāgot.

> [!NOTE]
> Šo līdzekli nevar izmantot, ja jūsu vidē tiek izmantots Azure Data Lake Gen 2 krātuve.
>
> Līdzeklis Prognozes izmanto automatizētus līdzekļus, lai novērtētu datus un veiktu prognozes, pamatojoties uz šiem datiem, un tāpēc tās ir izmantojamas kā profilēšanas metode, jo šis termins ir definēts vispārīgajā datu aizsardzības regulā ("VDAR"). Šī līdzekļa izmantošana klienta datu apstrādei var būt pakļauta VDAR vai citiem likumiem vai noteikumiem. Jūs esat atbildīgs par to, ka jūsu Dynamics 365 Customer Insights lietojums, ieskaitot prognozes, atbilst visiem piemērojamiem likumiem un noteikumiem, ieskaitot likumus, kas attiecas uz privātumu, personas datiem, biometrijas datiem, datu aizsardzību un saziņas konfidencialitāti.

## <a name="prerequisites"></a>Priekšnosacījumi

Lai organizācija varētu izmantot prognožu līdzekli, pārliecinieties, vai ir izpildīti šādi priekšnosacījumi:

1. Jūsu organizācijai ir iestatīta instance, [kas iestatīta Microsoft Dataverse](/ai-builder/build-model#prerequisites) un tā atrodas tajā pašā organizācijā, kurā atrodas Customer Insights.

2. Customer Insights vide ir piesaistīta jūsu Dataverse instancei.

Papildinformāciju skatiet sadaļā [Jaunas vides izveide](create-environment.md).

## <a name="create-a-prediction-in-the-customer-entity"></a>Prognozēšanas izveide klienta entītijā

1. Dodieties uz **datu** > **entītijas**.

2. Atlasiet entītiju **Klients**.

3. **Klients: CustomerInsights** entītijā atlasiet cilnē **Lauki**.

4. Atrodiet atribūta nosaukumu, kuram vēlaties prognozēt vērtības, un pēc tam atlasiet ikonu **Pārskats** kolonnā **Kopsavilkums**.
   > [!div class="mx-imgBorder"]
   > ![Ikona Pārskats.](media/intelligence-overviewicon.png "Ikona Pārskats")

5. Ja jūsu atribūtam ir augsts trūkstošo vērtību līmenis, atlasiet **Prognozēt trūkstošās vērtības**, lai turpinātu jūsu prognozēšanu.
   > [!div class="mx-imgBorder"]
   > ![Tiek parādīts statusa pārskats ar poga Prognozēt trūkstošās vērtības.](media/intelligence-overviewpredictmissingvalues.png "Tiek parādīts statusa pārskats ar poga Prognozēt trūkstošās vērtības")

6. Norādiet **Parādāmo nosaukumu** un **Izvades entītijas nosaukumu** prognozes rezultātiem.

7. Iepriekš aizpildītu opciju saraksts parāda, kur varat kartēt vērtības uz prognozēto kategoriju. Šajā gadījumā vienīgās kategorijas opcijas ir 0 vai 1, jo tās kartē uz prognozes patieso/kļūdaino vai bināro raksturu. Kolonnā Kategorija kartējiet lauku vērtības, kuras vēlaties klasificēt kā "0" gala prognozē "0", un elementus, ko vēlaties klasificēt kā "1" galējā prognozē "1".
   > [!div class="mx-imgBorder"]
   > ![Kartēto lauku vērtību rādīšanas piemērs kategorijām.](media/intelligence-categorymapping.png "Kartēto lauku vērtību rādīšanas piemērs kategorijām")

8. Atlasiet **Gatavs**, un prognoze tiks apstrādāta. Apstrādei ir vajadzīgs laiks atkarībā no datu lieluma un sarežģītības pakāpes. Rezultāti būs pieejami jaunā entītijā, pamatojoties uz jūsu izveidotās prognozes **Izvades entītijas nosaukumu**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="create-a-prediction-while-creating-a-segment"></a>Izveidot prognozi, veidojot segmentu

Izveidojot segmentu, var paredzēt arī trūkstošās vērtības konkrētam izvēles atribūtam. Īpaši tad, ja ātri izveidojat segmentu, pamatojoties vai nu uz Unified Customer entītiju, vai Customer_Measure entītiju.

Kā daļu no šīs plūsmas jūs izvēlaties noteiktu atribūtu, lai balstītu savu segmentu, piemēram, klientu apmierinātību vai pirkuma summu. Pēc segmenta izveides sistēma piedāvās metodi, lai prognozētu šī atribūta trūkstošās vērtības.

1. Dodieties uz **Segmenti** un atlasiet **elementu Profili**.

2. Izvēlieties **Lauks**, lai izveidotu segmentu, un atlasiet **Operators**; pēc tam atlasiet vienumu **Pārskatīt**.

3. Norādiet segmenta **nosaukumu** un **parādāmo vārdu**.

4. Atlasiet vienumu **Saglabāt**.

5. Ja tikko izveidotajam segmentam ir nepilnīgi dati avota laukā, varat izvēlēties prognozēt trūkstošās vērtības.
   > [!div class="mx-imgBorder"]
   > ![Prognozēšanas poga.](media/segments-predictoption.png "Prognozēšanas poga")

6. Norādiet **Parādāmo nosaukumu** un **Izvades entītijas nosaukumu** prognozes rezultātiem.

7. Atlasiet **Gatavs**. Jūsu prognoze drīzumā tiks ģenerēta jaunajā entītijā ar nosaukumu, ko norādījāt laukā **Izvades entītijas nosaukums**.

## <a name="view-a-prediction"></a>Prognozes skatīšana

1. Dodieties uz **Izlūkošanas** > **prognozes** > **Manas prognozes**.

2. Atlasiet prognozes, kuras vēlaties pārskatīt.

3. Kolonnā Darbības&vellip; atlasiet vertikālo daudzpunkti (**)** un izvēlieties **Skats**.

4. Prognozes skatā redzēsit vairākus datu punktus.
   > [!div class="mx-imgBorder"]
   > ![Prognožu lapa.](media/intelligence-predictionsviewpage.png "Prognožu lapa")

   - **Prognozētās vērtības** rāda kartēšanu, ko izveidojāt lauka vērtībā uz kategoriju kartēšanas fāzi. Šīs ir datu kopas vērtības, kas ir kartētas uz noteiktu kategoriju.
   -**Galvenie ietekmētāji** ir jūsu datu kopas faktori, kas, visticamāk, ietekmēja prognozes ticamību tam, ka jūsu lauka vērtība tiek kartēta uz noteiktu kategoriju.
   - **Veiktspēja** norāda, kā notiek prognozes. Atlasiet saiti, lai uzzinātu vairāk.
   - **Priekšskatījumā** redzami izvades datu kopas paraugi no jūsu prognozes un varbūtība vai ticamība par prognozēto vērtību, ja 0 ir nenoteikts, un 1 ir drošs.

## <a name="update-a-prediction"></a>Prognožu atjaunināšana

1. Dodieties uz **Izlūkošanas** > **prognozes** > **Manas prognozes**.

2. Atlasiet prognozi, kuru vēlaties atjaunināt, un atlasiet ikonu **Atjaunināt**.

3. Prognoze tiks ieplānota apstrādei. Varat redzēt, kad pēdējo atjaunināšanas reizi kolonnā **Atjaunināts** lapā **Prognozes**.

## <a name="edit-a-prediction"></a>Prognozes rediģēšana

Kad esat izveidojis prognoze, varat pielāgot modeli AI Builder, lai palielinātu modeļa efektivitāti.  

1. Dodieties uz **Izlūkošanas** > **prognozes** > **Manas prognozes**.

2. Atlasiet prognozi, kuru vēlaties rediģēt.

3. Kolonnā Darbības&vellip; atlasiet vertikālo daudzpunkti (**)** un izvēlieties **Skats**.

4. Atlasiet **Pielāgot .AI Builder**

5. Atjauniniet savu modeli sadaļā AI Builder. [Uzziniet vairāk par modeļu pārvaldību līdzeklī AI Builder](/ai-builder/manage-model#retrain-and-republish-existing-models).

Nākamajā jūsu prognozes izpildes gaitā tiks izmantots jūsu izveidotais atjauninātais modelis.

> [!NOTE]
> Jauni modeļi, kas izveidoti programmā AI Builder Customer Insights, netiks parādīti, ja vien modelis nav izveidots no iepriekš uzskaitītajām iespējām.

## <a name="remove-a-prediction"></a>Prognozes noņemšana

1. Dodieties uz **Izlūkošanas** > **prognozes** > **Manas prognozes**.

2. Atlasiet prognozi, ko vēlaties izdzēst.

3. Kolonnā Darbības atlasiet vertikālo daudzpunkti (&vellip;) **un izvēlieties** Dzēst **.**

4. Apstipriniet dzēšanu.

## <a name="troubleshooting"></a>Problēmu novēršana

Ja nevarat pabeigt Dataverse pievienošanas procesu kļūdas dēļ, varat mēģināt pabeigt procesu manuāli. Ir zināmas divas problēmas, kas var rasties pievienošanas procesā:

- Klientu karšu pievienojumprogrammu risinājums nav instalēts.
    1. Izpildiet norādījumus, lai [instalētu un konfigurētu risinājumu](customer-card-add-in.md).

- Programmas atļaujas nav piešķirtas.
    1. Dodieties uz [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com).
    1. Atlasiet **Vides**.
    1. Atlasiet vertikālo daudzpunkti (&vellip;) blakus videi, kurai vēlaties pievienot atļauju, un atlasiet **Iestatījumi**.
    1. Izvērsiet **Lietotāji + atļaujas** un atlasiet **Lietotāji**.
    1. Atlasiet **+ Jauns** un atlasiet **Lietotājs**.
    1. Atlasiet **Programmas lietotājs**, ja tas vēl nav atlasīts, un ievadiet šādu informāciju:
        - **Lietotājvārds:** cihelp@microsoft.com
        - **Programmas ID:** 38c77d00-5fcb-4cce-9d93-af4738258e3c
        - **Vārds:** Customer
        - **Uzvārds:** Insights
        - **Primārais e-pasts:** cihelp@microsoft.com
    1. Atlasiet vienumu **Saglabāt un aizvērt**.
    1. Atlasiet tikko izveidoto lietotāju.
    1. IAugšēja izvēlnes joslā atlasiet **Pārvaldīt lomas**.
    1. Atlasiet **Sistēmas administrators** un pēc tam atlasiet **Labi**.


[!INCLUDE [footer-include](includes/footer-banner.md)]
