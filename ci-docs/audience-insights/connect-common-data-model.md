---
title: Common Data Model datu savienošana ar Azure Data Lake kontu
description: Darbs ar Common Data Model datiem, izmantojot programmu Azure Data Lake Storage.
ms.date: 05/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 385406b706890d741fec2694c190c0fada7809d7
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596554"
---
# <a name="connect-to-a-common-data-model-folder-using-an-azure-data-lake-account"></a>Izveidojiet savienojumu ar Common Data Model mapi, izmantojot Azure Data Lake kontu

Šajā rakstā ir sniegta informācija, kā iegūt datus no Common Data Model mapes, izmantojot jūsu Azure Data Lake Storage Gen2 kontu.

## <a name="important-considerations"></a>Svarīgi ieteikumi

- Azure Data Lake datiem ir jāatbilst Common Data Model standartam. Citi formāti pašlaik netiek atbalstīti.

- Datu ieguve atbalsta tikai Azure Data Lake *Gen2* krātuves kontus. Jūs nevarat izmantot Azure Data Lake Gen1 krātuves kontus datu ieguvei.

- Lai veiktu autentifikāciju ar Azure pakalpojuma primāro nosaukumu, pārliecinieties, vai tas ir konfigurēts jūsu nomniekā. Papildinformāciju skatiet tēmā [Auditorijas ieskatu savienošana ar Azure Data Lake Storage Gen2 kontu, izmantojot Azure pakalpojuma primāro nosaukumu](connect-service-principal.md).

- Azure Data Lake, kurā jūs vēlaties savienot un iegūt datus, ir jābūt vienā un tajā pašā Azure reģionā kā Dynamics 365 Customer Insights videi. Savienojumi ar Common Data Model mapi no Data Lake citā Azure reģionā netiek atbalstīti. Lai iepazītu konkrētās vides Azure reģionu, apmeklējiet **Administrators** > **Sistēma** > **Par** sadaļā par auditorijas ieskatiem.

- Pakalpojumā tiešsaistes pakalpojumos glabātie dati var tikt glabāti citā ietā, nevis tajā, kur tiek apstrādāti vai glabāti dati Dynamics 365 Customer Insights. Importējot vai savienojot ar tiešsaistes pakalpojumos glabātajiem datiem, jūs piekrītat, ka datus var pārnest uz Dynamics 365 Customer Insights un glabāt tajā. [Papildinformāciju skatiet Microsoft drošības kontroles centrā.](https://www.microsoft.com/trust-center)

## <a name="connect-to-a-common-data-model-folder"></a>Izveidot savienojumu ar mapi Common Data Model

1. Sadaļā Auditorijas ieskati skatiet **Dati** > **Datu avoti**.

1. Atlasiet **Pievienot datu avotu**.

1. Atlasiet **Izveidot savienojumu ar Common Data Model mapi**, ievadiet datu avota **Nosaukumu** un pēc tam atlasiet **Tālāk**. Nosaukuma vadlīnijas: 
   - Sāciet ar burtu.
   - Izmantojiet tikai burtus un ciparus. Speciālās rakstzīmes un atstarpes nav atļautas.
   - Izmantojiet no 3 līdz 64 rakstzīmēm.

1. Varat izvēlēties, vai, izmantojot opciju, kuras pamatā ir resurss, vai abonementa opciju, lai autentificētos. Papildinformāciju skatiet tēmā [Auditorijas ieskatu savienošana ar Azure Data Lake Storage Gen2 kontu, izmantojot Azure pakalpojuma primāro nosaukumu](connect-service-principal.md). Ievadiet informāciju par **Konteineru** un atlasiet **Tālāk**.
   > [!div class="mx-imgBorder"]
   > ![Dialoglodziņš, lai ievadītu jauna savienojuma detaļas Azure Data Lake](media/enter-new-storage-details.png)
   > [!NOTE]
   > Lai varētu izveidot savienojumu ar konteineri vai krātuves kontu, ir nepieciešama viena no tālāk minētajām lomām, lai varētu izveidot savienojumu ar datu avotu:
   >  - Krātuves Blob datu lasītājs
   >  - Krātuves Blob datu īpašnieks
   >  - Krātuves Blob datu ieguldītājs

1. **Atlasiet Common Data Model mapi** dialoglodziņā atlasiet model.json vai manifest.json failu, no kura importēt datus, un atlasiet **Tālāk**.
   > [!NOTE]
   > Jebkurš model.json vai manifest.json fails, kas saistīts ar citu datu avotu vidē, netiks rādīts sarakstā.

1. Atlasītajā model.json vai manifest.json failā tiks parādīts pieejamo entītiju saraksts. Jūs varat apskatīt un atlasīt no pieejamo entītiju saraksta un atlasīt **Saglabāt**. Jaunākie dati no atlasītajām entītijām tiks eksportēti katru dienu.
   > [!div class="mx-imgBorder"]
   > ![Dialoglodziņš, kurā redzams entītiju saraksts no model.json faila](media/review-entities.png)

8. Norādiet, kurām datu entītijām vēlaties iespējot datu profilēšanu, un atlasiet **Saglabāt**. Datu profilēšana iespējo analīzi un citas iespējas. Varat atlasīt visu entītiju, kas atlasa visus entītijas atribūtus, vai atlasiet noteiktus atribūtus pēc jūsu izvēles. Pēc noklusējuma neviena entītija nav iespējota datu profilēšanai.
   > [!div class="mx-imgBorder"]
   > ![Dialoglodziņš, kurā redzama datu profilēšana](media/dataprofiling-entities.png)

9. Kad esat saglabājis savas atlases, tiek atvērta lapa **Datu avoti**. Tagad jums būtu jāredz mapes Common Data Model savienojums kā datu avots.

> [!NOTE]
> model.json vai manifest.json failu var saistīt tikai ar vienu datu avotu tajā pašā vidē. Tomēr tādu pašu model.json vai manifest.json failu var izmantot datu avotiem, kas atrodas vairākās vidēs.

## <a name="edit-a-common-data-model-folder-data-source"></a>Common Data Model mapes datu avota rediģēšana

Varat atjaunināt tās krātuves konta piekļuves atslēgu, kurā ir ietverta Common Data Model mape. Varat mainīt arī model.json vai manifest.json failu. Lai izveidotu savienojumu ar citu konteineru no krātuves konta vai mainītu konta nosaukumu, [izveidojiet jaunu datu avota savienojumu](#connect-to-a-common-data-model-folder).

1. Sadaļā Auditorijas ieskati skatiet **Dati** > **Datu avoti**.

2. Blakus atjaunināmajam datu avotam atlasiet elipsi.

3. No saraksta atlasiet opciju **Rediģēt**.

4. Pēc izvēles atjauniniet **Piekļuves atslēgu** un atlasiet **Tālāk**.

   ![Dialoglodziņš, lai rediģētu un atjauninātu esoša datu avota piekļuves atslēgu](media/edit-access-key.png)

5. Ja vēlaties, varat atjaunināt no uzņēmuma atslēgas savienojuma uz resursu vai abonementa bāzes savienojumu. Papildinformāciju skatiet tēmā [Auditorijas ieskatu savienošana ar Azure Data Lake Storage Gen2 kontu, izmantojot Azure pakalpojuma primāro nosaukumu](connect-service-principal.md). Atjauninot savienojumu, nevar mainīt **Konteinera** informāciju.
   > [!div class="mx-imgBorder"]

   > ![Dialoglodziņš, lai ievadītu Azure Data Lake savienojuma informāciju esošā krātuves kontā](media/enter-existing-storage-details.png)

   > [!NOTE]
   > Lai varētu izveidot savienojumu ar konteineri vai krātuves kontu, ir nepieciešama viena no tālāk minētajām lomām, lai varētu izveidot savienojumu ar datu avotu:
   >  - Krātuves Blob datu lasītājs
   >  - Krātuves Blob datu īpašnieks
   >  - Krātuves Blob datu ieguldītājs


6. Pēc izvēles izvēlieties citu model.json vai manifest.json failu ar citu entītiju kopu no konteinera.

7. Ja vēlaties, varat atlasīt papildu entītijas, ko iegūt. Ja nav atkarību, varat noņemt arī jau atlasītās entītijas.

   > [!IMPORTANT]
   > Ja esošajā model.json vai manifest.json failā un entītiju kopā ir atkarības, tiks parādīts kļūdas ziņojums un nevarēs atlasīt citu model.json vai manifest.json failu. Pirms maināt model.json vai manifest.json failu, noņemiet šīs atkarības vai izveidojiet jaunu datu avotu ar model.json vai manifest.json failu, kuru vēlaties izmantot, lai izvairītos no atkarību noņemšanas.

8. Ja vēlaties, varat atlasīt papildu atribūtus vai entītijas, lai iespējotu datu profilēšanu vai atspējotu jau atlasītos.   


[!INCLUDE[footer-include](../includes/footer-banner.md)]