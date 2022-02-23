---
title: Klienta darbības
description: Definējiet klientu darbības un apskatiet tās laika skalā pēc klientu profiliem.
ms.date: 11/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
ms.openlocfilehash: c99ec2e7d5e4bf32a509bbe4c0c53999129b2305
ms.sourcegitcommit: 834651b933b1e50e7557d44f926a3fb757c1f83a
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 11/02/2021
ms.locfileid: "7732469"
---
# <a name="customer-activities"></a>Klienta darbības

Apvienojiet klientu aktivitātes no [dažādiem datu avotiem](data-sources.md) Dynamics 365 Customer Insights, lai izveidotu laika grafiku, kurā aktivitātes uzskaitītas hronoloģiski. Iekļaujiet laika grafiku Dynamics 365 programmās ar [klienta kartes pievienojumprogrammu](customer-card-add-in.md) risinājumu vai Power BI informācijas panelī.

## <a name="define-an-activity"></a>Darbības definēšana

Datu avoti var ietvert entītijas ar transakciju un darbību datiem no vairākiem datu avotiem. Identificējiet šīs entītijas un atlasiet darbības, kuras vēlaties skatīt klienta laika skalā. Izvēlieties entītiju, kurā ir jūsu mērķa darbība vai darbības.

Entītijai ir nepieciešams vismaz viens veida **Datums** atribūts, ko iekļaut klienta laika skalā, un entītijas bez **Datuma** laukiem nevar pievienot. Ja netiek atrasta šāda entitīja, vadīkla **Pievienot darbību** tiek atspējota.

1. Sadaļā Auditorijas ieskati skatiet **Dati** > **Darbības**.

1. Atlasiet **Pievienot darbību**, lai sāktu vadīti iestatīt darbību.

1. Darbībā **Darbības dati** iestatiet šādu lauku vērtības:

   - **Darbības nosaukums**: Atlasiet savas darbības nosaukumu.
   - **Entītija**: Atlasiet entītiju, kurā ir transakciju vai darbību dati.
   - **Primārā atslēga**: Atlasīt lauku, kas unikāli identificē ierakstu. Tajā nedrīkst ietvert dublētas vērtības, tukšas vērtības vai trūkstošas vērtības.

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="Iestatiet darbības datus ar nosaukumu, entītiju un primāro atslēgu.":::

1. Lai pārietu uz nākamo darbību, atlasiet **Tālāk**.

1. Solī **Attiecības** konfigurējiet detalizētu informāciju, lai darbības datus savienotu ar atbilstošo klienta ierakstu. Šajā darbībā tiek vizualizēts entītiju savienojums.  

   - **Pirmais**: Ārējs darbību entitījas lauks, kuru izmantos, lai izveidotu relāciju ar citu entitīju.
   - **Otrais**: Atbilstošā avota klienta entitīja, ar kuru jūsu entitījai būs relācija. Ir iespējams izveidot relāciju tikai ar avota klientu entitījām, kuras tiek izmantotas datu apvienošanas procesā.
   - **Trešā**: Ja jau pastāv relācija starp šo darbības entitīju un atlasīto avota klienta entitīju, relācijas nosaukums būs tikai lasāmā režīmā. Ja šāda relācija nepastāv, tiks izveidota jauna relācija ar šajā lodziņā sniegto nosaukumu.

   :::image type="content" source="media/Activity_Wizard2.PNG" alt-text="Entītiju relācijas definēšana.":::

   > [!TIP]
   > B2B vidēs varat atlasīt starp uzņēmuma entītijām un citām entītijām. Atlasot uzņēmuma entītiju, tiek automātiski iestatīts attiecību ceļš. Citām entītijām attiecību ceļš jādefinē pāri vienai vai vairākām entītijām ar aizstācību, līdz tiek sasniegta uzņēmuma entītija.

1. Lai pārietu uz nākamo darbību, atlasiet **Tālāk**. 

1. Darbībā **Darbību apvienošana** atlasiet darbības nosaukumu un savas darbības sākuma laiku. 
   - **Obligātie lauki**
      - **Notikuma darbība**: Lauks, kas ir šīs darbības notikums.
      - **Laikspiedols**: Lauks, kas norāda uz darbības sākuma laiku.

   - **Neobligātie lauki**
      - **Papildu informācija**: Lauks ar atbilstošu informāciju par šo darbību.
      - **Ikona**: Ikona, kas vislabāk atbilst šim darbības tipam.
      - **Tīmekļa adrese**: Lauks, kurā ir vietrādis URL ar informāciju par šo darbību. Piemēram, transakciju sistēma, kas ģenerē šo darbību. Šis URL var būt jebkurš lauks no datu avota, vai arī to var būvēt kā jaunu lauku, izmantojot Power Query transformāciju. URL dati tiks glabāti entitījā *Apvienotās darbības*, kuru var patērēt lejupstraumē, izmantojot [API](apis.md).

   - **Rādīt laika skalā**
      - Izvēlieties, vai vēlaties atainot šo darbību savu klientu profilu laika skalas skatā. Atlasiet **Jā**, lai rādītu darbību laika skalā vai **Nē**, lai to paslēptu.

      :::image type="content" source="media/Activity_Wizard3.PNG" alt-text="Norādiet klienta darbības datus apvienoto darbību entitījā.":::

1. Lai pārietu uz nākamo darbību, atlasiet **Tālāk**. Varat atlasīt **Pabeigt un pārskatīt**, lai saglabātu darbību ar darbības veidu iestatītu uz **Cita**. 

1. Darbībā **Darbības veids** izvēlieties darbības veidu un, ja vēlaties, atlasiet, vai vēlaties semantiski kartēt dažus darbību veidus, kurus izmantot citos Customer Insights apgabalos. Pašlaik *Atsauksme*, *Lojalitāte*, *SalesOrder*, *SalesOrderLine* un *Abonementa* darbību veidi var tikt kartēti semantiski pēc tam, kad ir saņemta piekrišana kartēt laukus. Ja jaunajai darbībai nav atbilstoša darbības veida, varat atlasīt *Cita* vai *Izveidot jaunu*, lai izveidotu pielāgotu darbības veidu.

1. Lai pārietu uz nākamo darbību, atlasiet **Tālāk**. 

1. Darbībā **Pārskatīt** pārbaudies savu atlasi. Atgriezieties pie iepriekšējām darbībām un, ja nepieciešams, atjauniniet informāciju.

   :::image type="content" source="media/Activity_Wizard5.PNG" alt-text="Pārskatiet darbībai norādītos laukus.":::
   
1. Atlasiet **Saglabāt darbību**, lai piemērotu izmaiņas, un atlasiet **Gatavs**, lai atgrieztos **Dati** > **Darbības**. Šeit ir redzams, kuras darbības tiek rādītas laika skalā. 

1. Lapā **Darbības** atlasiet **Palaist**, lai apstrādātu darbību. 

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="manage-existing-activities"></a>Esošo darbību pārvaldība

Lapā **Dati** > **Darbības** varat skatīt visas saglabātās darbības un tās pārvaldīt. Katru darbību uzrāda rinda, kurā ir iekļauta arī informācija par avotu, entitīju un darbības veidu.

Atlasot darbību ir pieejamas šādas darbības. 

- **Rediģēt**: Priekšstatījuma darbībā atver darbības iestatīšanu. Šajā darbībā varat mainīt jebkuru vai visas konfigurācijas. Pēc konfigurācijas maiņas atlasiet **Saglabāt darbību** un **Palaist**, lai apstrādātu izmaiņas.

- **Pārdēvēt**: Atver dialogu, kurā var ievadīt citu atlasītās darbības nosaukumu. Lai veiktās izmaiņas stātos spēkā, atlasiet **Saglabāt**.

- **Dzēst**: Atver dialoglodziņu, kurā var apstriprināt atlasītās darbības dzēšanu. Varat vienlaikus arī dzēst vairāk nekā vienu darbību, atlasot darbības un pēc tam noklikšķinot uz dzēšanas ikonas. Lai apstiprinātu dzēšanu, atlasiet **Dzēst**.

## <a name="view-activity-timelines-on-customer-profiles"></a>Darbību laika grafiku skatīšana klientu profilos

Pēc klientu darbību konfigurēšanas atlasiet vienumu **Rādīt darbību laika skalā** darbību konfigurācijā, lai atrastu visas klienta darbības savā klienta profilā.

Lai atvērtu klienta laika skalu, dodieties uz **Klienti** un izvēlieties klienta profilu, kuru vēlaties skatīt.

Ja klients ir piedalījies jūsu konfigurētajā darbībā, tā būs sadaļā **Darbības laika grafiks**.

:::image type="content" source="media/Activity_Timeline1.PNG" alt-text="Skatiet konfigurētās darbības klientu profilos.":::

Ir vairāki veidi, kā darbību filtrēt darbību laika skalā:

- Varat atlasīt vienu vai vairākas darbību ikonas, lai uzlabotu rezultātus un iekļautu tikai atlasītos tipus.

  :::image type="content" source="media/Activity_Timeline2.PNG" alt-text="Filtrējiet darbības pēc tipa, izmantojot ikonas.":::

- Varat atlasīt **Filtrēt**, lai atvērtu filtrēšanas paneli laika skalas filtru konfigurēšanai.

   1. Varat filtrēt pēc *ActivityType* un *Datuma*
   1. Atlasiet **Lietot**, lai darbību laika skalā izmantotu filtrus.

   :::image type="content" source="media/Activity_Timeline3.PNG" alt-text="Filtrēšanas nosacījumu konfigurēšanai izmantojiet filtrēšanas paneli.":::

Lai noņemtu filtrus, atlasiet blakus katram laika skalai lietotajiem filtriem **x** vai atlasiet vienumu **Notīrīt filtrus**.


> [!NOTE]
> Darbību filtri tiek noņemti, kad atstājat klienta profilu. Tie ir jālieto ikreiz, kad atverat klienta profilu.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
