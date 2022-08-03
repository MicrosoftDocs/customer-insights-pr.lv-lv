---
title: Klienta darbības
description: Definējiet klientu darbības un apskatiet tās laika skalā pēc klientu profiliem.
ms.date: 07/22/2022
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
searchScope:
- ci-entities
- ci-customer-card
- ci-relationships
- ci-activities
- ci-activities-wizard
- ci-measures
- ci-segment-suggestions
- customerInsight
ms.openlocfilehash: cc21b0eeb368156437e60d851c2d144f3974c066
ms.sourcegitcommit: c45c3e044034bf866b0662f80a59166cee4ababe
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 07/22/2022
ms.locfileid: "9188148"
---
# <a name="customer-activities"></a>Klientu darbības

Klientu aktivitātes ir darbības vai pasākumi, ko veic klienti. Piemēram, transakcijas, atbalsta zvana ilgums, atsauksmes par tīmekļa vietni, pirkumi vai atgriešana. Šīs darbības ir ietvertas vienā vai vairākos datu avotos. Izmantojot Customer Insights, konsolidējiet savas klientu aktivitātes no šiem [datu avotiem](data-sources.md) un saistiet tos ar klientu profiliem. Šīs darbības tiek parādītas hronoloģiski klienta profila laika skalā. Iekļaujiet laika skalu Dynamics 365 programmās, izmantojot [customer card pievienojumprogrammas](customer-card-add-in.md) risinājumu.

## <a name="define-an-activity"></a>Darbības definēšana

Entītijai ir jābūt vismaz vienam atribūtam ar tipu **Datums**, lai to iekļautu klienta laika skalā. Ja netiek atrasta šāda entitīja, vadīkla **Pievienot darbību** tiek atspējota.

1. Dodieties uz **datu** > **aktivitātes**.

1. Atlasiet **Pievienot darbību**, lai sāktu vadīto pieredzi.

1. Darbībās **dati** ievadiet šādu informāciju:

   - **Aktivitātes nosaukums**: jūsu darbības nosaukums.
   - **Darbības entītija**: entītija, kas ietver transakciju vai darbību datus.
   - **Primārā atslēga**: lauks, kas unikāli identificē ierakstu. Tajā nedrīkst ietvert dublētas vērtības, tukšas vērtības vai trūkstošas vērtības.

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="Iestatiet darbības datus ar nosaukumu, entītiju un primāro atslēgu.":::

1. Atlasiet **Tālāk**.

1. Darbībā Relācija **atlasiet** **Pievienot relāciju**, lai saistītu savus darbības datus ar atbilstošo klienta ierakstu. Šajā darbībā tiek vizualizēts entītiju savienojums.  

   - **Ārējā atslēga no entītijas**: lauks jūsu darbības entītijā, kas tiks izmantots, lai izveidotu relāciju ar citu entītiju.
   - **Uz entītijas nosaukumu**: atbilstošā avota klienta entītija, ar kuru jūsu darbības entītija būs saistīta. Ir iespējams izveidot relāciju tikai ar avota klientu entitījām, kuras tiek izmantotas datu apvienošanas procesā.
   - **Relācijas nosaukums**: nosaukums, kas identificē attiecības starp entītijām. Ja relācija starp šo darbības entītiju un atlasīto avota klienta entītiju jau pastāv, relācijas nosaukums ir tikai lasāms.

   :::image type="content" source="media/Activity_Wizard2.PNG" alt-text="Entītiju relācijas definēšana.":::

   > [!TIP]
   > B2B vidēs varat atlasīt starp uzņēmuma entītijām un citām entītijām. Atlasot uzņēmuma entītiju, tiek automātiski iestatīts attiecību ceļš. Citām entītijām attiecību ceļš jādefinē pāri vienai vai vairākām entītijām ar aizstācību, līdz tiek sasniegta uzņēmuma entītija.

1. Atlasiet **Lietot**, lai izveidotu relāciju.

1. Atlasiet **Tālāk**.

1. Darbībā **Darbību apvienošana** atlasiet darbības nosaukumu un savas darbības sākuma laiku.
   - **Obligātie lauki**
      - **Notikuma darbība**: Lauks, kas ir šīs darbības notikums.
      - **Laikspiedols**: Lauks, kas norāda uz darbības sākuma laiku.

   - **Neobligātie lauki**
      - **Papildu informācija**: Lauks ar atbilstošu informāciju par šo darbību.
      - **Ikona**: Ikona, kas vislabāk atbilst šim darbības tipam.
      - **Tīmekļa adrese**: Lauks, kurā ir vietrādis URL ar informāciju par šo darbību. Piemēram, transakciju sistēma, kas ģenerē šo darbību. Šis URL var būt jebkurš lauks no datu avots vai arī to var izveidot kā jaunu lauku, izmantojot Power Query transformāciju. URL dati tiks glabāti entitījā *Apvienotās darbības*, kuru var patērēt lejupstraumē, izmantojot [API](apis.md).

   - **Rādīt laika skalā**
      - Izvēlieties, vai vēlaties atainot šo darbību savu klientu profilu laika skalas skatā. Atlasiet **Jā**, lai rādītu darbību laika skalā vai **Nē**, lai to paslēptu.

      :::image type="content" source="media/Activity_Wizard3.PNG" alt-text="Norādiet klienta darbības datus apvienoto darbību entitījā.":::

1. Atlasiet **Tālāk**, lai izvēlētos darbības veidu, vai atlasiet **Pabeigt un pārskatīt**, lai saglabātu darbību, kuras darbības tips ir iestatīts uz **Cits**.

1. Darbībā **Darbības veids** izvēlieties darbības veidu un, ja vēlaties, atlasiet, vai vēlaties semantiski kartēt dažus darbību veidus, kurus izmantot citos Customer Insights apgabalos. *Pašlaik atsauksmju*, *lojalitātes*, *pārdošanas pasūtījumu*, *pārdošanas pasūtījumu līnijas* un *abonēšanas* darbību veidi atbalsta semantiku pēc tam, kad ir piekrituši kartēt laukus. Ja jaunajai darbībai nav atbilstoša darbības veida, varat atlasīt *Cita* vai *Izveidot jaunu*, lai izveidotu pielāgotu darbības veidu.

1. Atlasiet **Tālāk**.

1. Darbībā **Pārskatīt** pārbaudies savu atlasi. Atgriezieties pie iepriekšējām darbībām un, ja nepieciešams, atjauniniet informāciju.

1. Atlasiet **Saglabāt darbību**, lai piemērotu izmaiņas, un atlasiet **Gatavs**, lai atgrieztos **Dati** > **Darbības**. Parādītā izveidotā darbība.

1. Pēc visu savu darbību izveides atlasiet **Palaist**, lai tās apstrādātu.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="manage-existing-activities"></a>Esošo darbību pārvaldība

Dodieties uz **Datu** > **darbības**, lai skatītu savas saglabātās darbības, to avota entītiju, darbības veidu un to, vai tās ir iekļautas klientu laika skalā. Darbību sarakstu var kārtot pēc jebkuras kolonnas vai izmantot meklēšanas lodziņu, lai atrastu darbību, kuru vēlaties pārvaldīt.

Atlasiet darbību, lai skatītu pieejamās darbības.

- **Rediģējiet** darbību, lai mainītu tās konfigurāciju. Konfigurācija tiek atvērta pārskatīšanas solī. Pēc konfigurācijas maiņas atlasiet **Saglabāt darbību** un **Palaist**, lai apstrādātu izmaiņas.
- **Pārdēvējiet** darbību. Lai veiktās izmaiņas stātos spēkā, atlasiet **Saglabāt**.
- **Dzēst** darbību. Lai vienlaikus izdzēstu vairākas darbības, atlasiet darbības un pēc tam **dzēsiet**. Apstipriniet dzēšanu.

## <a name="view-activity-timelines-on-customer-profiles"></a>Darbību laika grafiku skatīšana klientu profilos

1. Ja aktivitātes konfigurācijā atlasījāt **Rādīt darbību laika skalā**, dodieties uz **Klienti** un atlasiet klienta profilu, lai skatītu klienta darbības **sadaļā Darbību laika grafiks**.

   :::image type="content" source="media/Activity_Timeline1.PNG" alt-text="Skatiet konfigurētās darbības klientu profilos.":::

1. Lai filtrētu darbības darbību laika grafikā, veiciet tālāk norādītās darbības.

   - Atlasiet vienu vai vairākas darbību ikonas, lai precizētu rezultātus un iekļautu tikai atlasītos tipus.

     :::image type="content" source="media/Activity_Timeline2.PNG" alt-text="Filtrējiet darbības pēc tipa, izmantojot ikonas.":::

   - Atlasiet **Filtrs**, lai atvērtu filtra paneli laika grafika filtru konfigurēšanai. Filtrēt pēc *ActivityType* un/vai *Datuma*. Atlasiet vienumu **Piemērot**.

     :::image type="content" source="media/Activity_Timeline3.PNG" alt-text="Filtrēšanas nosacījumu konfigurēšanai izmantojiet filtrēšanas paneli.":::

1. Lai noņemtu filtrus, atlasiet **Notīrīt filtrus** vai atlasiet **Filtrs** un notīriet filtra izvēles rūtiņu.

> [!NOTE]
> Darbību filtri tiek noņemti, kad atstājat klienta profilu. Jums tie ir jāpiemēro katru reizi, kad atverat klienta profilu.

[!INCLUDE [footer-include](includes/footer-banner.md)]
