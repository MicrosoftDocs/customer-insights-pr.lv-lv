---
title: Klientu darbības
description: Definējiet klientu darbības un aplūkojiet tās klientu laika skalā.
ms.date: 04/07/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: 6ebe899d3e3da43c4108678cd2e4f9a986e18ab35e839044becab4619adb0f14
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 08/10/2021
ms.locfileid: "7033640"
---
# <a name="customer-activities"></a>Klientu darbības

Apvienojiet klientu darbības no [dažādiem datu avotiem](data-sources.md) risinājumā Dynamics 365 Customer Insights, lai izveidotu laika skalu, kurā hronoloǵiski uzskaitītas darbības. Iekļaujiet laika skalu Dynamics 365 programmās, izmantojot risinājumu [Klienta kartes pievienojumprogramma](customer-card-add-in.md) vai Power BI informācijas panelī.

## <a name="define-an-activity"></a>Darbības definēšana

Datu avoti var ietvert entītijas ar transakciju un darbību datiem no vairākiem datu avotiem. Identificējiet šīs entītijas un atlasiet darbības, kuras vēlaties skatīt klienta laika skalā. Izvēlieties entītiju, kurā ir jūsu mērķa darbība vai darbības.

> [!NOTE]
> Entītijai ir nepieciešams vismaz viens veida **Datums** atribūts, ko iekļaut klienta laika skalā, un entītijas bez **Datuma** laukiem nevar pievienot. Ja netiek atrasta šāda entitīja, vadīkla **Pievienot darbību** tiek atspējota.

1. Sadaļā Auditorijas ieskati skatiet **Dati** > **Darbības**.

1. Atlasiet **Pievienot darbību**, lai sāktu vadīti iestatīt darbību.

1. Darbībā **Darbības dati** iestatiet šādu lauku vērtības:

   - **Darbības nosaukums**: Atlasiet savas darbības nosaukumu.
   - **Entītija**: Atlasiet entītiju, kurā ir transakciju vai darbību dati.
   - **Primārā atslēga**: Atlasīt lauku, kas unikāli identificē ierakstu. Tajā nedrīkst ietvert dublētas vērtības, tukšas vērtības vai trūkstošas vērtības.

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="Iestatiet darbības datus ar nosaukumu, entītiju un primāro atslēgu.":::

1. Lai pārietu uz nākamo darbību, atlasiet **Tālāk**.

1. Darbībā **Attiecības** konfigurējiet informāciju, lai savienotu savas aktivitātes datus ar tai atbilstošo klientu. Šajā darbībā tiek vizualizēts entitīju savienojums.  

   - **Pirmais**: Ārējs darbību entitījas lauks, kuru izmantos, lai izveidotu relāciju ar citu entitīju.
   - **Otrais**: Atbilstošā avota klienta entitīja, ar kuru jūsu entitījai būs relācija. Ir iespējams izveidot relāciju tikai ar avota klientu entitījām, kuras tiek izmantotas datu apvienošanas procesā.
   - **Trešā**: Ja jau pastāv relācija starp šo darbības entitīju un atlasīto avota klienta entitīju, relācijas nosaukums būs tikai lasāmā režīmā. Ja šāda relācija nepastāv, tiks izveidota jauna relācija ar šajā lodziņā sniegto nosaukumu.

   :::image type="content" source="media/Activity_Wizard2.PNG" alt-text="Entītiju relācijas definēšana.":::

1. Lai pārietu uz nākamo darbību, atlasiet **Tālāk**. 

1. Darbībā **Darbību apvienošana** atlasiet darbības nosaukumu un savas darbības sākuma laiku. 
   - **Obligātie lauki**
      - **Notikuma darbība**: Lauks, kas ir šīs darbības notikums.
      - **Laikspiedols**: Lauks, kas norāda uz darbības sākuma laiku.

   - **Neobligātie lauki**
      - **Papildu informācija**: Lauks ar atbilstošu informāciju par šo darbību.
      - **Ikona**: Ikona, kas vislabāk atbilst šim darbības tipam.
      - **Tīmekļa adrese**: Lauks, kurā ir vietrādis URL ar informāciju par šo darbību. Piemēram, transakciju sistēma, kas ģenerē šo darbību. Šis URL var būt jebkurš lauks no datu avota, vai arī to var būvēt kā jaunu lauku, izmantojot Power Query transformāciju. URL dati tiks glabāti entitījā *Apvienotās darbības*, kuru var patērēt lejupstraumē, izmantojot [API](apis.md).
   
   :::image type="content" source="media/Activity_Wizard3.PNG" alt-text="Norādiet klienta darbības datus apvienoto darbību entitījā.":::

1. Lai pārietu uz nākamo darbību, atlasiet **Tālāk**. Varat atlasīt **Pabeigt un pārskatīt**, lai saglabātu darbību ar darbības veidu iestatītu uz **Cita**. 

1. Darbībā **Darbības veids** izvēlieties darbības veidu un, ja vēlaties, atlasiet, vai vēlaties semantiski kartēt dažus darbību veidus, kurus izmantot citos Customer Insights apgabalos. Pašlaik *Abonements* un *SalesOrderLine* darbību veidi var tikt kartēti semantiski pēc tam, kad ir saņemta piekrišana kartēt laukus. Ja jaunajai darbībai nav atbilstoša darbības veida, varat atlasīt *Cita* vai *Izveidot jaunu*, lai izveidotu pielāgotu darbības veidu.

1. Lai pārietu uz nākamo darbību, atlasiet **Tālāk**. 

1. Darbībā **Pārskatīt** pārbaudies savu atlasi. Atgriezieties pie iepriekšējām darbībām un, ja nepieciešams, atjauniniet informāciju.

   :::image type="content" source="media/Activity_Wizard5.PNG" alt-text="Pārskatiet darbībai norādītos laukus.":::
   
1. Atlasiet **Saglabāt darbību**, lai piemērotu izmaiņas, un atlasiet **Gatavs**, lai atgrieztos **Dati** > **Darbības**. Šeit ir redzams, kuras darbības tiek rādītas laika skalā. 

1. Lapā **Darbības** atlasiet **Palaist**, lai apstrādātu darbību. 

> [!TIP]
> Uzdevumiem/procesiem ir [seši statusu tipi](system.md#status-types). Turklāt vairums procesu [ir atkarīgi no citiem pakārtotiem procesiem](system.md#refresh-policies). Varat atlasīt procesa statusu, lai skatītu detalizētu informāciju par visa uzdevuma norisi. Pēc tam, kad vienam no darba uzdevumiem esat atlasījis **Skatīt detalizētu informāciju**, jūs redzēsit papildinformāciju: apstrādes laiku, pēdējās apstrādes datumu un visas ar uzdevumu saistītas kļūdas un brīdinājumus.


## <a name="manage-existing-activities"></a>Esošo darbību pārvaldība

Lapā **Dati** > **Darbības** varat skatīt visas saglabātās darbības un tās pārvaldīt. Katru darbību uzrāda rinda, kurā ir iekļauta arī informācija par avotu, entitīju un darbības veidu.

Atlasot darbību ir pieejamas šādas darbības. 

- **Rediģēt**: Priekšstatījuma darbībā atver darbības iestatīšanu. Šajā darbībā varat mainīt jebkuru vai visas konfigurācijas. Pēc konfigurācijas maiņas atlasiet **Saglabāt darbību** un **Palaist**, lai apstrādātu izmaiņas.

- **Pārdēvēt**: Atver dialogu, kurā var ievadīt citu atlasītās darbības nosaukumu. Lai veiktās izmaiņas stātos spēkā, atlasiet **Saglabāt**.

- **Dzēst**: Atver dialoglodziņu, kurā var apstriprināt atlasītās darbības dzēšanu. Varat vienlaikus arī dzēst vairāk nekā vienu darbību, atlasot darbības un pēc tam noklikšķinot uz dzēšanas ikonas. Lai apstiprinātu dzēšanu, atlasiet **Dzēst**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
