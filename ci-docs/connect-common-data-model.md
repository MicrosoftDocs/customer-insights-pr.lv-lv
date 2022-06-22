---
title: Common Data Model datu savienošana ar Azure Data Lake kontu
description: Darbs ar Common Data Model datiem, izmantojot programmu Azure Data Lake Storage.
ms.date: 05/30/2022
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- ci-attach-cdm
- customerInsights
ms.openlocfilehash: 2ab7ec77252be33f1203959c2a596ddec20425f2
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 06/14/2022
ms.locfileid: "9011575"
---
# <a name="connect-to-data-in-azure-data-lake-storage"></a>Izveidot savienojumu ar datiem programmā Azure Data Lake Storage

Liet datus, Dynamics 365 Customer Insights izmantojot savu Azure Data Lake Storage Gen2 kontu. Datu norīšana var būt pilnīga vai inkrementāla.

## <a name="prerequisites"></a>Priekšnoteikumi

- Datu uzņemšana atbalsta Azure Data Lake Storage *tikai Gen2* kontus. Datu iegūšanai nevar izmantot Data Lake Storage Gen1 kontus.

- Kontam Azure Data Lake Storage jābūt [iespējotai hierarhiskai nosaukumvietai](/azure/storage/blobs/data-lake-storage-namespace). Dati jāuzglabā hierarhiskā mapes formātā, kas definē saknes mapi un kam ir apakšmapes katrai entītijai. Apakšmapēm var būt pilni dati vai inkrementālas datu mapes.

- Lai veiktu autentifikāciju ar Azure pakalpojuma primāro nosaukumu, pārliecinieties, vai tas ir konfigurēts jūsu nomniekā. Papildinformāciju skatiet rakstā [Savienojuma izveide ar Gen2 kontu, izmantojot Azure pakalpojumu vadītāju Azure Data Lake Storage.](connect-service-principal.md)

- Datiem Azure Data Lake Storage, no kuriem vēlaties savienot un uzņemt datus, ir jāatrodas tajā pašā Debeszila reģionā, no kura atrodas Dynamics 365 Customer Insights vide. Savienojumi ar Common Data Model mapi no datu ezera citā Azure reģionā netiek atbalstīti. Lai uzzinātu Azure vides reģionu, dodieties uz **Administrēšanas** > **sistēma** > **par** customer insights.

- Tiešsaistes pakalpojumos glabātos datus var glabāt citā vietā, nevis vietā, kur dati tiek apstrādāti vai glabāti Dynamics 365 Customer Insights.Importējot tiešsaistes pakalpojumos saglabātos datus vai izveidojot savienojumu ar Dynamics 365 Customer Insights  [tiem, jūs piekrītat, ka datus var pārsūtīt uz . Uzziniet vairāk Microsoft drošības kontroles centrā](https://www.microsoft.com/trust-center).

- Lai piekļūtu krātuves kontam, pakalpojuma Customer Insights principālam ir jābūt vienā no šīm lomām. Papildinformāciju skatiet rakstā [Atļauju piešķiršana pakalpojuma vadītājam, lai piekļūtu krātuves kontam](connect-service-principal.md#grant-permissions-to-the-service-principal-to-access-the-storage-account).
  - Krātuves Blob datu lasītājs
  - Krātuves Blob datu īpašnieks
  - Krātuves Blob datu ieguldītājs

- Datiem datu ezera krātuvē ir jāatbilst kopējā datu modeļa standartam jūsu datu glabāšanai, un tiem jābūt kopīgam datu modeļa manifestam, lai attēlotu datu failu shēmu (*.csv vai *.parketu). Manifestā jānorāda detalizēta informācija par entītijām, piemēram, entītiju kolonnām un datu tipiem, kā arī datu faila atrašanās vieta un faila tips. Plašāku informāciju skatiet [Common Data Model manifestā](/common-data-model/sdk/manifest). Ja manifesta nav, administratori, kuriem ir krātuves BLOB datu īpašnieks vai krātuves BLOB datu līdzstrādnieka piekļuve, var definēt shēmu, uzņemot datus.

## <a name="connect-to-azure-data-lake-storage"></a>Savienojuma izveide ar Azure Data Lake Storage

1. Dodieties uz **Dati** > **Datu avoti**.

1. Atlasiet **Pievienot datu avotu**.

1. Atlasiet **Azure data lake storage**.

   :::image type="content" source="media/data_sources_ADLS.png" alt-text="Dialoglodziņš, lai ievadītu detalizētu informāciju par Azure Data Lake savienojumu." lightbox="media/data_sources_ADLS.png":::

1. **Ievadiet datu avots nosaukumu** un neobligātu **aprakstu**. Nosaukums unikāli identificē datu avots, un uz to ir atsauce pakārtotajos procesos, un to nevar mainīt.

1. Izvēlieties vienu no šīm opcijām, lai **savienotu krātuvi, izmantojot**. Papildinformāciju skatiet rakstā [Customer Insights savienošana ar Azure Data Lake Storage Gen2 kontu, izmantojot Azure pakalpojumu vadītāju](connect-service-principal.md).

   - **Azure resurss**: ievadiet resursa **ID**. Pēc izvēles, ja vēlaties uzņemt datus no krātuves konta, izmantojot Azure Private Link, atlasiet **Iespējot privāto saiti**. Plašāku informāciju skatiet [Private Links](security-overview.md#private-links-tab).
   - **Azure abonements**: atlasiet **Abonements** **un pēc tam resursu grupu** un **krātuves kontu.** Pēc izvēles, ja vēlaties uzņemt datus no krātuves konta, izmantojot Azure Private Link, atlasiet **Iespējot privāto saiti**. Plašāku informāciju skatiet [Private Links](security-overview.md#private-links-tab).
  
   > [!NOTE]
   > Lai izveidotu datu avots, konteineram vai krātuves kontam ir nepieciešama viena no šīm lomām:
   >
   >  - Krātuves BLOB datu lasītājs ir pietiekams, lai lasītu no krātuves konta un uzņemtu datus Customer Insights. 
   >  - Krātuves BLOB datu līdzstrādnieks vai īpašnieks ir nepieciešams, ja vēlaties rediģēt manifesta failus tieši customer insights.  
  
1. Izvēlieties tā konteinera **nosaukumu**, kurā ir dati un shēma (fails model.json vai manifest.json), no kura importēt datus, un atlasiet **Tālāk**.
   > [!NOTE]
   > Jebkurš model.json vai manifest.json fails, kas saistīts ar citu datu avotu vidē, netiks rādīts sarakstā. Tomēr tādu pašu model.json vai manifest.json failu var izmantot datu avotiem, kas atrodas vairākās vidēs.

1. Lai izveidotu jaunu shēmu, dodieties uz [Izveidot jaunu shēmas failu](#create-a-new-schema-file).

1. Lai izmantotu esošu shēmu, naviģējiet uz mapi, kurā atrodas fails model.json vai manifest.cdm.json. Varat meklēt direktorijā, lai atrastu failu.

1. Atlasiet json failu un atlasiet **Tālāk**. Tiek parādīts pieejamo entītiju saraksts.

   :::image type="content" source="media/review-entities.png" alt-text="Atlasāmo entītiju saraksta dialoglodziņš":::

1. Atlasiet iekļaujamās entītijas.

   :::image type="content" source="media/ADLS_required.png" alt-text="Dialoglodziņš, kurā redzama primārā atslēgai Obligāts":::

   > [!TIP]
   > Lai rediģētu entītijas JSON rediģēšanas interfeisā, atlasiet **Rādīt vairāk** > **Rediģēt shēmas failu**. Veiciet izmaiņas un atlasiet **Saglabāt**.

1. Atlasītām entītijām, kurām nepieciešama inkrementāla norīšana, **sadaļā** Inkrementālā atsvaidzināšana tiek rādīta **obligāti**. Par katru no šīm entītijām skatiet rakstā [Azure Data Lake datu avotu inkrementālās atsvaidzināšanas konfigurēšana](incremental-refresh-data-sources.md).

1. Atlasītajām entītijām, kurām primārā atslēga nav definēta, **obligāts** tiek parādīts sadaļā **Primārā atslēga**. Katrai no šīm entītijām:
   1. Atlasiet **Obligāts**. Tiek parādīts entītiju **panelis** Rediģēt.
   1. **Izvēlieties atslēgu Primārais**. Primārā atslēga ir atribūts, kas ir unikāls entītijai. Lai atribūts būtu derīga primārā atslēga, tajā nedrīkst ietvert vērtību dublikātus, trūkstošās vērtības vai nulles vērtības. Virknes, vesela skaitļa un GUID datu tipa atribūti tiek atbalstīti kā primārie taustiņi.
   1. Pēc izvēles mainiet nodalījuma modeli.
   1. Atlasiet **Aizvērt**, lai saglabātu un aizvērtu paneli.

1. Atlasiet atribūtu **skaitu** katrai iekļautajai entītijai. Tiek **parādīta lapa Atribūtu** pārvaldība.

   :::image type="content" source="media/dataprofiling-entities.png" alt-text="Dialoglodziņš, lai atlasītu datu profilēšanu.":::

   1. Izveidojiet jaunus atribūtus, rediģējiet vai dzēsiet esošos atribūtus. Varat mainīt nosaukumu, datu formātu vai pievienot semantisko tipu.
   1. Lai iespējotu analīzi un citas iespējas, atlasiet **Datu profilēšana** visai entītijai vai noteiktiem atribūtiem. Pēc noklusējuma neviena entītija nav iespējota datu profilēšanai.
   1. Atlasiet **Gatavs**.

1. Atlasiet **Saglabāt**. Tiek **atvērta lapa Datu avoti**, kurā redzams jaunais datu avots atsvaidzināšanas **statusā**.

### <a name="create-a-new-schema-file"></a>Izveidot jaunu shēmas failu

1. Atlasiet **Jauns shēmas fails**.

1. Ievadiet faila nosaukumu un atlasiet **Saglabāt**.

1. Atlasiet **Jauna entītija**. Tiek **parādīts panelis Jauna entītija**.

1. Ievadiet entītijas nosaukumu un izvēlieties **datu failu atrašanās vietu**.
   - **Vairāki .csv vai .parketa faili**: pārlūkojiet līdz saknes mapei, atlasiet raksta tipu un ievadiet izteiksmi.
   - **Viena .csv vai .parketa faili**: pārlūkojiet līdz .csv vai .parketa failam un atlasiet to.

   :::image type="content" source="media/ADLS_new_entity_location.png" alt-text="Dialoglodziņš, lai izveidotu jaunu entītiju ar iezīmētu datu failu atrašanās vietu.":::

1. Atlasiet **Saglabāt**.

   :::image type="content" source="media/ADLS_new_entity_define_attributes.png" alt-text="Dialoglodziņš atribūtu definēšanai vai automātiskai ģenerēšanai.":::

1. Atlasiet **definēt atribūtus**, lai manuāli pievienotu atribūtus, vai atlasiet **tos** automātiski ģenerēt. Lai definētu atribūtus, ievadiet nosaukumu, atlasiet datu formātu un neobligāto semantisko tipu. Automātiski ģenerētiem atribūtiem:

   1. Kad atribūti ir automātiski ģenerēti, atlasiet **Pārskatīt atribūtus**. Tiek **parādīta lapa Atribūtu** pārvaldība.

   1. Pārliecinieties, vai datu formāts katram atribūtam ir pareizs.

   1. Lai iespējotu analīzi un citas iespējas, atlasiet **Datu profilēšana** visai entītijai vai noteiktiem atribūtiem. Pēc noklusējuma neviena entītija nav iespējota datu profilēšanai.

      :::image type="content" source="media/dataprofiling-entities.png" alt-text="Dialoglodziņš, lai atlasītu datu profilēšanu.":::

   1. Atlasiet **Gatavs**. Tiek **parādīta lapa Entītiju** atlasīšana.

1. Turpiniet pievienot entītijas un atribūtus, ja tādi ir.

1. Kad visas entītijas ir pievienotas, atlasiet **Iekļaut**, lai iekļautu entītijas datu avots norīšanas.

   :::image type="content" source="media/ADLS_required.png" alt-text="Dialoglodziņš, kurā redzama primārā atslēgai Obligāts":::

1. Atlasītām entītijām, kurām nepieciešama inkrementāla norīšana, **sadaļā** Inkrementālā atsvaidzināšana tiek rādīta **obligāti**. Par katru no šīm entītijām skatiet rakstā [Azure Data Lake datu avotu inkrementālās atsvaidzināšanas konfigurēšana](incremental-refresh-data-sources.md).

1. Atlasītajām entītijām, kurām primārā atslēga nav definēta, **obligāts** tiek parādīts sadaļā **Primārā atslēga**. Katrai no šīm entītijām:
   1. Atlasiet **Obligāts**. Tiek parādīts entītiju **panelis** Rediģēt.
   1. **Izvēlieties atslēgu Primārais**. Primārā atslēga ir atribūts, kas ir unikāls entītijai. Lai atribūts būtu derīga primārā atslēga, tajā nedrīkst ietvert vērtību dublikātus, trūkstošās vērtības vai nulles vērtības. Virknes, vesela skaitļa un GUID datu tipa atribūti tiek atbalstīti kā primārie taustiņi.
   1. Pēc izvēles mainiet nodalījuma modeli.
   1. Atlasiet **Aizvērt**, lai saglabātu un aizvērtu paneli.

1. Atlasiet **Saglabāt**. Tiek **atvērta lapa Datu avoti**, kurā redzams jaunais datu avots atsvaidzināšanas **statusā**.


## <a name="edit-an-azure-data-lake-storage-data-source"></a>Azure Data Lake Storage datu avots rediģēšana

Varat atjaunināt opciju *Izveidot savienojumu ar krātuves kontu, izmantojot* opciju. Papildinformāciju skatiet rakstā [Customer Insights savienošana ar Azure Data Lake Storage Gen2 kontu, izmantojot Azure pakalpojumu vadītāju](connect-service-principal.md). Lai izveidotu savienojumu ar citu konteineru no krātuves konta vai mainītu konta nosaukumu, [izveidojiet jaunu datu avota savienojumu](#connect-to-azure-data-lake-storage).

1. Dodieties uz **Dati** > **Datu avoti**.

1. Blakus datu avots kuru vēlaties atjaunināt, atlasiet **Rediģēt**.

   :::image type="content" source="media/data_sources_edit_ADLS.png" alt-text="Dialoglodziņš Azure Data Lake datu avots rediģēšanai.":::

1. Mainiet jebkuru no šīm ziņām:

   - **Apraksts**
   - **Pievienojiet krātuvei, izmantojot** un savienojuma informāciju. Atjauninot savienojumu, nevar mainīt **Konteinera** informāciju.
      > [!NOTE]
      > Uzglabāšanas kontam vai konteineram jāpiešķir viena no šīm lomām:
        > - Krātuves Blob datu lasītājs
        > - Krātuves Blob datu īpašnieks
        > - Krātuves Blob datu ieguldītājs

   - **Iespējojiet privāto saiti**, ja vēlaties uzņemt datus no krātuves konta, izmantojot Azure Private Link. Plašāku informāciju skatiet [Private Links](security-overview.md#private-links-tab).

1. Atlasiet **Tālāk**.
1. Mainiet jebkuru no šīm darbībām:
   - Naviģējiet uz citu failu model.json vai manifest.json ar citu entītiju kopu, nevis konteineru.
   - Lai uzņemšanai pievienotu papildu entītijas, atlasiet **Jauna entītija**.
   - Lai noņemtu visas jau atlasītās entītijas, ja nav atkarību, atlasiet entītiju un **Dzēst**.
      > [!IMPORTANT]
      > Ja esošajā model.json vai manifest.json failā un entītiju kopā ir atkarības, tiks parādīts kļūdas ziņojums un nevarēs atlasīt citu model.json vai manifest.json failu. Pirms maināt model.json vai manifest.json failu, noņemiet šīs atkarības vai izveidojiet jaunu datu avotu ar model.json vai manifest.json failu, kuru vēlaties izmantot, lai izvairītos no atkarību noņemšanas.
   - Lai mainītu datu faila atrašanās vietu vai primāro atslēgu, atlasiet **Rediģēt**.
   - Lai mainītu inkrementālās norīšanas datus, skatiet rakstu [Azure Data Lake datu avotu inkrementālās atsvaidzināšanas konfigurēšana](incremental-refresh-data-sources.md)

1. Atlasiet **Atribūti**, lai pievienotu vai mainītu atribūtus vai iespējotu datu profilēšanu. Tad atlasiet **Gatavs**.

1. Noklikšķiniet uz **Saglabāt**, lai lietotu izmaiņas un atgrieztos **lapā Datu avoti**.
