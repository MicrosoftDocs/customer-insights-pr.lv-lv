---
title: Common Data Model datu savienošana ar Azure Data Lake kontu
description: Darbs ar Common Data Model datiem, izmantojot programmu Azure Data Lake Storage.
ms.date: 05/24/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- ci-attach-cdm
- customerInsights
ms.openlocfilehash: 2e8564950a3269180a85f80fb736d2dcbd1b03b6
ms.sourcegitcommit: f5af5613afd9c3f2f0695e2d62d225f0b504f033
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 06/01/2022
ms.locfileid: "8833371"
---
# <a name="connect-to-a-common-data-model-folder-using-an-azure-data-lake-account"></a>Izveidojiet savienojumu ar Common Data Model mapi, izmantojot Azure Data Lake kontu

Šajā rakstā ir sniegta informācija par to, kā uzņemt Dynamics 365 Customer Insights datus no mapes Common Data Model, izmantojot savu Azure Data Lake Storage Gen2 kontu.

## <a name="important-considerations"></a>Svarīgi ieteikumi

- Azure Data Lake datiem ir jāatbilst Common Data Model standartam. Citi formāti pašlaik netiek atbalstīti.

- Datu ieguve atbalsta tikai Azure Data Lake *Gen2* krātuves kontus. Jūs nevarat izmantot Azure Data Lake Gen1 krātuves kontus datu ieguvei.

- Azure Data Lake krātuves kontam jābūt [iespējotai hierarhiskai nosaukumvietai](/azure/storage/blobs/data-lake-storage-namespace).

- Lai veiktu autentifikāciju ar Azure pakalpojuma primāro nosaukumu, pārliecinieties, vai tas ir konfigurēts jūsu nomniekā. Papildinformāciju [skatiet rakstā Azure Data Lake Storage Savienojuma izveide ar Gen2 kontu, izmantojot Azure pakalpojumu vadītāju](connect-service-principal.md).

- Azure Data Lake, kurā jūs vēlaties savienot un iegūt datus, ir jābūt vienā un tajā pašā Azure reģionā kā Dynamics 365 Customer Insights videi. Savienojumi ar Common Data Model mapi no datu ezera citā Azure reģionā netiek atbalstīti. Lai uzzinātu Azure vides reģionu, dodieties uz **Administrēšanas** > **sistēma** > **par** customer insights.

- Tiešsaistes pakalpojumos glabātos datus var glabāt citā vietā, nevis vietā, kur dati tiek apstrādāti vai glabāti Dynamics 365 Customer Insights.Importējot tiešsaistes pakalpojumos saglabātos datus vai izveidojot savienojumu ar Dynamics 365 Customer Insights  [tiem, jūs piekrītat, ka datus var pārsūtīt uz . Uzziniet vairāk Microsoft drošības kontroles centrā](https://www.microsoft.com/trust-center).

## <a name="connect-to-a-common-data-model-folder"></a>Izveidot savienojumu ar mapi Common Data Model

1. Dodieties uz **Dati** > **Datu avoti**.

1. Atlasiet **Pievienot datu avotu**.

1. Atlasiet **Azure datu ezera** krātuve **, ievadiet datu avots nosaukumu** un pēc tam atlasiet **Tālāk**.

   - Ja tiek prasīts, atlasiet kādu no datu kopu paraugiem, kas attiecas uz jūsu nozari, pēc tam atlasiet **Tālāk**.

1. Varat izvēlēties, vai, izmantojot opciju, kuras pamatā ir resurss, vai abonementa opciju, lai autentificētos. Papildinformāciju [skatiet rakstā Azure Data Lake Storage Savienojuma izveide ar Gen2 kontu, izmantojot Azure pakalpojumu vadītāju](connect-service-principal.md). **Ievadiet servera adresi**, atlasiet **Pieteikties** un pēc tam atlasiet **Tālāk**.
   > [!div class="mx-imgBorder"]
   > ![Dialoglodziņš, lai ievadītu jauna savienojuma detaļas Azure Data Lake.](media/enter-new-storage-details.png)
   > [!NOTE]
   > Krātuves kontā esošajam konteineram ir nepieciešama viena no šīm lomām, lai izveidotu un izveidotu datu avots:
   >
   >  - Krātuves BLOB datu lasītājs ir pietiekams, lai lasītu no krātuves konta un uzņemtu datus Customer Insights. 
   >  - Krātuves BLOB datu līdzstrādnieks vai īpašnieks ir nepieciešams, ja vēlaties rediģēt manifesta failus tieši customer insights.

1. **Atlasiet Common Data Model mapi** dialoglodziņā atlasiet model.json vai manifest.json failu, no kura importēt datus, un atlasiet **Tālāk**.
   > [!NOTE]
   > Jebkurš model.json vai manifest.json fails, kas saistīts ar citu datu avotu vidē, netiks rādīts sarakstā.

1. Atlasītajā model.json vai manifest.json failā būs redzams pieejamo entītiju saraksts. Pārskatiet un atlasiet pieejamo entītiju sarakstā, pēc tam atlasiet **Saglabāt**. Jaunākie dati no atlasītajām entītijām tiks eksportēti katru dienu.
   > [!div class="mx-imgBorder"]
   > ![Dialoglodziņš, kurā redzams entītiju saraksts no model.json faila.](media/review-entities.png)

1. Norādiet, kuras datu entītijas vēlaties iespējot datu profilēšanu, pēc tam atlasiet **Saglabāt**. Datu profilēšana iespējo analīzi un citas iespējas. Varat atlasīt visu entītiju, kas atlasa visus entītijas atribūtus, vai atlasiet noteiktus atribūtus pēc jūsu izvēles. Pēc noklusējuma neviena entītija nav iespējota datu profilēšanai.
   > [!div class="mx-imgBorder"]
   > ![Dialoglodziņš, kurā redzama datu profilēšana.](media/dataprofiling-entities.png)

1. Kad esat saglabājis savas atlases, tiek atvērta lapa **Datu avoti**. Tagad jums būtu jāredz mapes Common Data Model savienojums kā datu avots.

> [!NOTE]
> model.json vai manifest.json failu var saistīt tikai ar vienu datu avotu tajā pašā vidē. Tomēr tādu pašu model.json vai manifest.json failu var izmantot datu avotiem, kas atrodas vairākās vidēs.

## <a name="edit-a-common-data-model-folder-data-source"></a>Common Data Model mapes datu avota rediģēšana

Varat atjaunināt tās krātuves konta piekļuves atslēgu, kurā ir ietverta Common Data Model mape. Varat mainīt arī model.json vai manifest.json failu. Lai izveidotu savienojumu ar citu konteineru no krātuves konta vai mainītu konta nosaukumu, [izveidojiet jaunu datu avota savienojumu](#connect-to-a-common-data-model-folder).

1. Dodieties uz **Dati** > **Datu avoti**.

2. Blakus datu avots, kuru vēlaties atjaunināt, atlasiet vertikālo daudzpunkti (&vellip;).

3. No saraksta atlasiet opciju **Rediģēt**.

4. Pēc izvēles atjauniniet **Piekļuves atslēgu** un atlasiet **Tālāk**.

   ![Dialoglodziņš, lai rediģētu un atjauninātu esoša datu avota piekļuves atslēgu.](media/edit-access-key.png)

5. Ja vēlaties, varat atjaunināt no uzņēmuma atslēgas savienojuma uz resursu vai abonementa bāzes savienojumu. Papildinformāciju [skatiet rakstā Azure Data Lake Storage Savienojuma izveide ar Gen2 kontu, izmantojot Azure pakalpojumu vadītāju](connect-service-principal.md). Atjauninot savienojumu, nevar mainīt **Konteinera** informāciju.
   > [!div class="mx-imgBorder"]

   > ![Dialoglodziņš, lai ievadītu Azure Data Lake savienojuma informāciju esošā krātuves kontā.](media/enter-existing-storage-details.png)

6. Pēc izvēles izvēlieties citu model.json vai manifest.json failu ar citu entītiju kopu no konteinera.

7. Ja vēlaties, varat atlasīt papildu entītijas, ko iegūt. Ja nav atkarību, varat noņemt arī jau atlasītās entītijas.

   > [!IMPORTANT]
   > Ja esošajā model.json vai manifest.json failā un entītiju kopā ir atkarības, tiks parādīts kļūdas ziņojums un nevarēs atlasīt citu model.json vai manifest.json failu. Pirms maināt model.json vai manifest.json failu, noņemiet šīs atkarības vai izveidojiet jaunu datu avotu ar model.json vai manifest.json failu, kuru vēlaties izmantot, lai izvairītos no atkarību noņemšanas.

8. Ja vēlaties, varat atlasīt papildu atribūtus vai entītijas, lai iespējotu datu profilēšanu vai atspējotu jau atlasītos.

[!INCLUDE [footer-include](includes/footer-banner.md)]
