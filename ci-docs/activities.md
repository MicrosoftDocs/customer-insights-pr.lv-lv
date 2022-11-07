---
title: Klientu vai darba kontaktu aktivitātes
description: Definējiet klientu vai darba kontaktpersonu darbības un skatiet tās klientu profilu laika grafikā.
ms.date: 10/26/2022
ms.subservice: audience-insights
ms.reviewer: v-wendysmith
ms.topic: conceptual
author: srivas15
ms.author: shsri
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
ms.openlocfilehash: d8caa477278f04c3a0a95ced15f4bea2a22aa8cd
ms.sourcegitcommit: da6a2d189edacc8f2c0f2abedcb28245f26fe74c
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 10/27/2022
ms.locfileid: "9723790"
---
# <a name="customer-or-business-contact-activities"></a>Klientu vai darba kontaktu aktivitātes

Klientu darbības ir darbības vai pasākumi, ko veic klienti vai biznesa kontakti. Piemēram, darījumi, atbalsta zvana ilgums, vietņu pārskati, pirkumi vai atgriešana. Šīs darbības ir ietvertas vienā vai vairākos datu avotos. Izmantojot Customer Insights, konsolidējiet klientu darbības no šiem [datu avotiem](data-sources.md) un saistiet tās ar klientu profiliem. Šīs darbības hronoloģiski parādās laika skalā klienta profilā. Iekļaujiet laika grafiku Dynamics 365 programmās ar [klienta kartes pievienojumprogrammas](customer-card-add-in.md) risinājumu.

## <a name="define-a-customer-activity"></a>Klienta darbības definēšana

Uzņēmumam ir jābūt vismaz vienam atribūtam ar tipu **Datums**, lai to iekļautu klienta laika skalā. Ja netiek atrasta šāda entitīja, vadīkla **Pievienot darbību** tiek atspējota.

1. Dodieties uz **sadaļu** > **Datu darbības**.

1. Atlasiet **Pievienot darbības**, lai sāktu vadīto pieredzi.

1. **Datu solī Activity (Darbības dati**) ievadiet šādu informāciju:

   - **Darbības nosaukums**: Atlasiet savas darbības nosaukumu.
   - **Entītija Darbība: atlasiet entītiju**, kas ietver transakciju vai darbību datus.
   - **Primārā atslēga**: Atlasīt lauku, kas unikāli identificē ierakstu. Tajā nedrīkst ietvert dublētas vērtības, tukšas vērtības vai trūkstošas vērtības.

     > [!NOTE]
     > Primārajai atslēgai katrai rindai ir jāpaliek konsekventai datu avots atsvaidzināšanas laikā. Ja rindas primārā atslēga tiek atjaunināta datu avots atsvaidzināšanas laikā, tā izveido dublikātus izvades darbības entītijā. 

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="Iestatiet darbības datus ar nosaukumu, entītiju un primāro atslēgu.":::

1. Atlasiet **Tālāk**.

1. **Darbībā Relācija** atlasiet **Pievienot relāciju**, lai savienotu darbību datus ar atbilstošo klienta ierakstu. Šajā darbībā tiek vizualizēts entītiju savienojums.  

   - **Ārējā atslēga**: lauks Ārvalsts jūsu darbības entītijā, kas tiks izmantots, lai izveidotu relāciju ar citu entītiju.
   - **Entītijas nosaukumam**: atbilstoša avota klienta entītija, ar kuru jūsu darbības entītija būs saistīta. Ir iespējams izveidot relāciju tikai ar avota klientu entitījām, kuras tiek izmantotas datu apvienošanas procesā.
   - **Relācijas nosaukums: ja relācija starp šīs darbības entītiju un atlasīto avota klienta entītiju jau pastāv, relācijas nosaukums** būs tikai lasīšanas režīmā. Ja šāda relācija nepastāv, tiks izveidota jauna relācija ar šajā lodziņā sniegto nosaukumu.

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
      - **Tīmekļa adrese**: Lauks, kurā ir vietrādis URL ar informāciju par šo darbību. Piemēram, transakciju sistēma, kas ģenerē šo darbību. Šis URL var būt jebkurš lauks no datu avots, vai arī to var veidot kā jaunu lauku, izmantojot Power Query transformāciju. URL dati tiks glabāti entitījā *Apvienotās darbības*, kuru var patērēt lejupstraumē, izmantojot [API](apis.md).

   - **Rādīt laika skalā**
      - Izvēlieties, vai vēlaties atainot šo darbību savu klientu profilu laika skalas skatā. Atlasiet **Jā**, lai rādītu darbību laika skalā vai **Nē**, lai to paslēptu.

      :::image type="content" source="media/Activity_Wizard3.PNG" alt-text="Norādiet klienta darbības datus apvienoto darbību entitījā.":::

1. Atlasiet **Tālāk**, lai izvēlētos darbības tipu, vai atlasiet **Pabeigt un pārskatīt**, lai saglabātu darbību ar darbības tipu, kas iestatīts uz **Cits**.

1. Darbībā **Darbības veids** izvēlieties darbības veidu un, ja vēlaties, atlasiet, vai vēlaties semantiski kartēt dažus darbību veidus, kurus izmantot citos Customer Insights apgabalos. *Pašlaik darbību veidi Atsauksmes*, *Lojalitāte* *, SalesOrder, SalesOrderLine* *un* *Abonements atbalsta semantiku pēc tam, kad ir piekrituši kartēt laukus*. Ja jaunajai darbībai nav atbilstoša darbības veida, varat atlasīt *Cita* vai *Izveidot jaunu*, lai izveidotu pielāgotu darbības veidu.

1. Atlasiet **Tālāk**.

1. Darbībā **Pārskatīt** pārbaudies savu atlasi. Atgriezieties pie iepriekšējām darbībām un, ja nepieciešams, atjauniniet informāciju.

1. Atlasiet **Saglabāt darbību**, lai piemērotu izmaiņas, un atlasiet **Gatavs**, lai atgrieztos **Dati** > **Darbības**. Tiek parādīta izveidotā darbība.

1. Pēc visu darbību izveides atlasiet **Palaist**, lai tās apstrādātu.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="manage-existing-customer-activities"></a>Esošo klientu darbību pārvaldība

Pārejiet uz **sadaļu** > **Datu darbības, lai skatītu saglabātās darbības, to avota entītiju, darbības** tipu un to, vai tās ir iekļautas klientu laika skalā. Varat kārtot darbību sarakstu pēc jebkuras kolonnas vai izmantot meklēšanas lodziņu, lai atrastu darbību, kuru vēlaties pārvaldīt.

Atlasiet darbību, lai skatītu pieejamās darbības.

- **Rediģējiet** darbību, lai mainītu tās konfigurāciju. Konfigurācija tiek atvērta pārskatīšanas darbībā. Pēc konfigurācijas maiņas atlasiet **Saglabāt darbību** un **Palaist**, lai apstrādātu izmaiņas.
- **Pārdēvējiet** darbību. Lai veiktās izmaiņas stātos spēkā, atlasiet **Saglabāt**.
- **Dzēsiet** darbību. Lai vienlaikus izdzēstu vairākas darbības, atlasiet darbības un pēc tam **Dzēst**. Apstipriniet dzēšanu.

## <a name="view-activity-timelines-on-customer-profiles"></a>Darbību laika grafiku skatīšana klientu profilos

1. Ja aktivitātes konfigurācijā atlasījāt **Rādīt aktivitātes laika skalā, dodieties uz** sadaļu Klienti **un atlasiet klienta profilu, lai skatītu klienta darbības** sadaļā Darbību laika **grafiks**.

   :::image type="content" source="media/Activity_Timeline1.PNG" alt-text="Skatiet konfigurētās darbības klientu profilos.":::

1. Lai filtrētu darbības aktivitāšu laika grafikā, veiciet tālāk norādītās darbības.

   - Atlasiet vienu vai vairākas darbību ikonas, lai precizētu rezultātus un iekļautu tikai atlasītos tipus.

     :::image type="content" source="media/Activity_Timeline2.PNG" alt-text="Filtrējiet darbības pēc tipa, izmantojot ikonas.":::

   - Atlasiet **Filtrs**, lai atvērtu filtru paneli laika grafika filtru konfigurēšanai. Filtrēt pēc *darbības veida* un/vai *datuma*. Atlasiet vienumu **Piemērot**.

     :::image type="content" source="media/Activity_Timeline3.PNG" alt-text="Filtrēšanas nosacījumu konfigurēšanai izmantojiet filtrēšanas paneli.":::

> [!NOTE]
> Darbību filtri tiek noņemti, kad atstājat klienta profilu. Jums tie ir jāpiemēro katru reizi, kad atverat klienta profilu.

## <a name="define-a-contact-activity"></a>Kontaktpersonas darbības definēšana

Uzņēmuma kontiem (no B-to-B) izmantojiet entītiju *ContactProfile*, lai tvertu kontaktpersonu darbības. Konta darbību laika grafikā varat redzēt, kura kontaktpersona bija atbildīga par katru darbību. Lielākā daļa darbību tiek veiktas pēc klientu darbību kartēšanas konfigurācijas.

   > [!NOTE]
   > Lai definētu kontaktpersonu līmeņa darbību, ir jāizveido entītija *ContactProfile* kā vienots kontaktpersonas [profils](data-unification-contacts.md) vai kā [semantiskā kartēšana](semantic-mappings.md#define-a-contactprofile-semantic-entity-mapping).
   >
   > Katram ierakstam aktivitāšu datos ir jābūt gan AccountID, gan **ContactID** **atribūtiem**.
  
1. Dodieties uz **sadaļu** > **Datu darbības**.

1. Atlasiet **Pievienot darbību**.

1. **Datu solī Activity (Darbības dati**) ievadiet šādu informāciju:

   - **Darbības nosaukums**: Atlasiet savas darbības nosaukumu.
   - **Entītija Darbība: atlasiet entītiju**, kas ietver transakciju vai darbību datus.
   - **Primārā atslēga**: Atlasīt lauku, kas unikāli identificē ierakstu. Tajā nedrīkst ietvert dublētas vērtības, tukšas vērtības vai trūkstošas vērtības.

     > [!NOTE]
     > Primārajai atslēgai katrai rindai ir jāpaliek konsekventai datu avots atsvaidzināšanas laikā. Ja rindas primārā atslēga tiek atjaunināta datu avots atsvaidzināšanas laikā, tā izveido dublikātus izvades darbības entītijā. 


1. **Darbībā Relācijas** izveidojiet netiešu saistību starp darbību avota datiem un kontiem, izmantojot savus kontaktpersonu datus kā starpnieka entītiju. Papildinformāciju skatiet sadaļā [Tiešo un netiešo attiecību ceļi](relationships.md#relationship-paths).
   - Relācijas piemērs darbībai ar nosaukumu *Pirkumi*:
      - **Pirkumi Avota darbība Datu** > **kontaktinformācija** par atribūtu **ContactID**
      - **Kontaktdatu** > **konta dati** atribūtā **AccountID**

   :::image type="content" source="media/Contact_Activities1.png" alt-text="Relāciju iestatīšanas piemērs.":::

1. Pēc relāciju iestatīšanas atlasiet **Tālāk** un pabeidziet darbību kartēšanas konfigurāciju. Detalizētus soļus par darbību izveidi skatiet sadaļā [Klienta darbības](#define-a-customer-activity) definēšana.

1. Palaidiet savu darbību kartēšanu.

1. Jūsu kontaktpersonu līmeņa aktivitātes tagad būs redzamas jūsu klientu laika grafikā.

   :::image type="content" source="media/Contact_Activities2.png" alt-text="Gala rezultāts pēc kontaktpersonu darbību konfigurēšanas":::

## <a name="contact-level-activity-timeline-filtering"></a>Kontaktpersonu līmeņa darbību laika grafika filtrēšana

Pēc kontaktpersonu līmeņa darbību kartēšanas konfigurēšanas un tās palaišanas tiks atjaunināts jūsu klientu darbību laika grafiks. Atkarībā no jūsu *ContactProfile* konfigurācijas tajā ir iekļauti viņu ID vai vārdi darbībām, ar kurām viņi darbojās. Laika grafikā varat filtrēt darbības pēc kontaktpersonām, lai skatītu konkrētas jūs interesējošās kontaktpersonas. Turklāt visas darbības, kas nav piešķirtas konkrētai kontaktpersonai, varat skatīt, atlasot **Darbības, kas nav kartētas uz kontaktpersonu**.

   :::image type="content" source="media/Contact_Activities3.png" alt-text="Filtrēšanas opcijas, kas pieejamas kontaktpersonu līmeņa darbībām.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
