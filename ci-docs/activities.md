---
title: Klientu vai biznesa kontaktu aktivitātes
description: Definējiet klientu vai biznesa kontaktu darbības un skatiet tās laika skalā klientu profilos.
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.reviewer: v-wendysmith
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
- customerInsights
ms.openlocfilehash: bbb8bc30d079273bc935181c628915bb3c02d982
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304114"
---
# <a name="customer-or-business-contact-activities"></a>Klientu vai biznesa kontaktu aktivitātes

Klientu darbības ir darbības vai pasākumi, ko veic klienti vai biznesa kontakti. Piemēram, transakcijas, atbalsta zvana ilgums, atsauksmes par tīmekļa vietni, pirkumi vai atgriešana. Šīs darbības ir ietvertas vienā vai vairākos datu avotos. Izmantojot Customer Insights, konsolidējiet savas klientu aktivitātes no šiem [datu avotiem](data-sources.md) un saistiet tos ar klientu profiliem. Šīs darbības tiek parādītas hronoloģiski klienta profila laika skalā. Iekļaujiet laika skalu Dynamics 365 programmās, izmantojot [customer card pievienojumprogrammas](customer-card-add-in.md) risinājumu.

## <a name="define-a-customer-activity"></a>Klientu darbības definēšana

Entītijai ir jābūt vismaz vienam atribūtam ar tipu **Datums**, lai to iekļautu klienta laika skalā. Ja netiek atrasta šāda entitīja, vadīkla **Pievienot darbību** tiek atspējota.

1. Dodieties uz **datu** > **aktivitātes**.

1. Atlasiet **Pievienot darbību**, lai sāktu vadīto pieredzi.

1. Darbībās **dati** ievadiet šādu informāciju:

   - **Darbības nosaukums**: Atlasiet savas darbības nosaukumu.
   - **Darbības entītija**: atlasiet entītiju, kas ietver transakciju vai darbību datus.
   - **Primārā atslēga**: Atlasīt lauku, kas unikāli identificē ierakstu. Tajā nedrīkst ietvert dublētas vērtības, tukšas vērtības vai trūkstošas vērtības.

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="Iestatiet darbības datus ar nosaukumu, entītiju un primāro atslēgu.":::

1. Atlasiet **Tālāk**.

1. Darbībā Relācija **atlasiet** **Pievienot relāciju**, lai saistītu savus darbības datus ar atbilstošo klienta ierakstu. Šajā darbībā tiek vizualizēts entītiju savienojums.  

   - **Ārējā atslēga**: ārējais lauks jūsu darbības vienībā, kas tiks izmantots, lai izveidotu attiecības ar citu entītiju.
   - **Uz entītijas nosaukumu**: atbilstošā avota klienta entītija, ar kuru jūsu darbības entītija būs saistīta. Ir iespējams izveidot relāciju tikai ar avota klientu entitījām, kuras tiek izmantotas datu apvienošanas procesā.
   - **Relācijas nosaukums**: ja relācija starp šo darbības entītiju un atlasīto avota klienta entītiju jau pastāv, relācijas nosaukums būs tikai lasīšanas režīmā. Ja šāda relācija nepastāv, tiks izveidota jauna relācija ar šajā lodziņā sniegto nosaukumu.

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

## <a name="manage-existing-customer-activities"></a>Esošo klientu darbību pārvaldība

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

> [!NOTE]
> Darbību filtri tiek noņemti, kad atstājat klienta profilu. Jums tie ir jāpiemēro katru reizi, kad atverat klienta profilu.

## <a name="define-a-contact-activity"></a>Kontaktpersonas darbības definēšana

Biznesa kontiem (no B līdz B) izmantojiet entītiju *ContactProfile*, lai tvertu kontaktpersonu darbības. Konta darbību laika grafikā varat redzēt, kura kontaktpersona bija atbildīga par katru darbību. Lielākā daļa darbību tiek veiktas, veicot klientu darbību kartēšanas konfigurāciju.

   > [!NOTE]
   > Lai definētu kontaktpersonas līmeņa darbību, *ir jāizveido ContactProfile entītija* vai nu kā vienots [kontaktpersonas profils](data-unification-contacts.md), vai izmantojot [semantisko kartēšanu](semantic-mappings.md#define-a-contactprofile-semantic-entity-mapping).
   >
   > Katram ierakstam jūsu darbības datos ir jābūt gan **atribūtiem AccountID**, gan **ContactID**.
  
1. Dodieties uz **datu** > **aktivitātes**.

1. Atlasiet **Pievienot aktivitāti**.

1. Piešķiriet darbībai nosaukumu, atlasiet avota darbības entītiju un atlasiet darbības entītijas primāro atslēgu.

1. **Darbībā Relācijas** izveidojiet netiešu relāciju starp saviem darbības avota datiem un kontiem, izmantojot savus kontaktdatus kā starpniekuzņēmumu. Papildinformāciju skatiet tiešo [un netiešo attiecību ceļos](relationships.md#relationship-paths).
   - Relācijas piemērs darbībai ar nosaukumu *Pirkumi*:
      - **Iegādājas avota darbības datu** > **kontaktinformāciju** atribūtā **ContactID**
      - **·** > **Kontaktinformācijas konta dati** atribūtā **AccountID**

   :::image type="content" source="media/Contact_Activities1.png" alt-text="Relāciju iestatīšanas piemērs.":::

1. Pēc relāciju iestatīšanas atlasiet **Tālāk** un pabeidziet darbību kartēšanas konfigurēšanu. Detalizētas darbības par darbību izveidi skatiet rakstā [Klienta darbības](#define-a-customer-activity) definēšana.

1. Palaidiet savu darbību kartēšanu.

1. Jūsu kontaktpersonas līmeņa darbības tagad būs redzamas jūsu klientu laika skalā.

   :::image type="content" source="media/Contact_Activities2.png" alt-text="Galīgais rezultāts pēc kontakta darbību konfigurēšanas":::

## <a name="contact-level-activity-timeline-filtering"></a>Kontaktpersonu līmeņa darbību laika grafika filtrēšana

Pēc kontaktpersonas līmeņa darbību kartēšanas konfigurēšanas un tās palaišanas jūsu klientu darbību laika grafiks tiks atjaunināts. Tas ietver viņu ID vai vārdus, atkarībā no jūsu *ContactProfile* konfigurācijas, darbībām, ar kurām viņi rīkojās. Laika skalā varat filtrēt kontaktpersonu darbības, lai skatītu konkrētas jūs interesējošas kontaktpersonas. Turklāt visas darbības, kas nav piešķirtas konkrētai kontaktpersonai, varat skatīt, atlasot **Darbības, kas nav kartētas uz kontaktpersonu**.

   :::image type="content" source="media/Contact_Activities3.png" alt-text="Filtrēšanas opcijas, kas pieejamas kontaktpersonu līmeņa darbībām.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
