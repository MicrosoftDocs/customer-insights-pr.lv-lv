---
title: Izveidojiet savienojumu ar Common Data Model mapi, izmantojot Azure Data Lake kontu
description: Darbs ar Common Data Model datiem, izmantojot programmu Azure Data Lake Storage.
ms.date: 07/27/2022
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
ms.openlocfilehash: d79b2d34e425e123224209814fef6e367c77c813
ms.sourcegitcommit: d7054a900f8c316804b6751e855e0fba4364914b
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 09/02/2022
ms.locfileid: "9396095"
---
# <a name="connect-to-data-in-azure-data-lake-storage"></a>Izveidot savienojumu ar datiem programmā Azure Data Lake Storage

Nododiet datus, Dynamics 365 Customer Insights lai izmantotu savu Azure Data Lake Storage Gen2 kontu. Datu norīšana var būt pilnīga vai pakāpeniska.

## <a name="prerequisites"></a>Priekšnoteikumi

- Datu norīšana atbalsta Azure Data Lake Storage *tikai Gen2* kontus. Datu uzņemšanai nevar izmantot Data Lake Storage Gen1 kontus.

- Kontā Azure Data Lake Storage jābūt [iespējotai hierarhiskai nosaukumvietai](/azure/storage/blobs/data-lake-storage-namespace). Dati ir jāglabā hierarhiskā mapes formātā, kas definē saknes mapi un kam katrai entītijai ir apakšmapes. Apakšmapēm var būt pilni dati vai inkrementālas datu mapes.

- Lai veiktu autentifikāciju ar Azure pakalpojuma primāro nosaukumu, pārliecinieties, vai tas ir konfigurēts jūsu nomniekā. Papildinformāciju skatiet rakstā [Savienojuma izveide ar Gen2 kontu, izmantojot Azure pakalpojuma principālu Azure Data Lake Storage.](connect-service-principal.md)

- Datiem Azure Data Lake Storage, no kuriem vēlaties izveidot savienojumu un uzņemt datus, ir jāatrodas tajā pašā Azure reģionā, kurā atrodas Dynamics 365 Customer Insights vide. Savienojumi ar Common Data Model mapi no datu ezera citā Azure reģionā netiek atbalstīti. Lai uzzinātu azure vides reģionu, dodieties uz **Administrēšanas** > **sistēma** > **par** programmā Customer Insights.

- Tiešsaistes pakalpojumos glabātos datus var glabāt citā vietā, nevis vietā, kur dati tiek apstrādāti vai glabāti Dynamics 365 Customer Insights.Importējot vai izveidojot savienojumu ar datiem, kas tiek glabāti tiešsaistes pakalpojumos, jūs piekrītat, ka datus var pārsūtīt uz un uzglabāt kopā ar Dynamics 365 Customer Insights. [Uzziniet vairāk Microsoft drošības kontroles centrā](https://www.microsoft.com/trust-center).

- Lai piekļūtu krātuves kontam, Customer Insights servisa direktoram ir jābūt vienā no tālāk norādītajām lomām. Papildinformāciju skatiet sadaļā [Atļauju piešķiršana pakalpojuma vadītājam, lai piekļūtu krātuves kontam](connect-service-principal.md#grant-permissions-to-the-service-principal-to-access-the-storage-account).
  - Krātuves Blob datu lasītājs
  - Krātuves Blob datu īpašnieks
  - Krātuves Blob datu ieguldītājs

- Lietotājam, kurš iestata datu avots savienojumu, ir nepieciešamas vismazāk krātuves Blob data contributor atļaujas krātuves kontā.

- Datu ezera krātuvē esošajiem datiem datu glabāšanai ir jāatbilst common data model standartam, un tiem ir jābūt kopējam datu modeļa manifestam, kas attēlo datu failu shēmu (*.csv vai *.parkets). Manifestā ir jāsniedz detalizēta informācija par entītijām, piemēram, entītiju kolonnām un datu tipiem, kā arī datu faila atrašanās vietu un faila tipu. Papildinformāciju skatiet sadaļā [Kopējā datu modeļa manifests](/common-data-model/sdk/manifest). Ja manifesta nav, administratori, kuriem ir piekļuve krātuves Blob datu īpašniekam vai krātuves Blob datu līdzstrādniekam, var definēt shēmu, norijot datus.

## <a name="connect-to-azure-data-lake-storage"></a>Savienojuma izveide ar Azure Data Lake Storage

1. Dodieties uz **Dati** > **Datu avoti**.

1. Atlasiet **Pievienot datu avotu**.

1. Atlasiet **Azure datu ezera krātuve**.

   :::image type="content" source="media/data_sources_ADLS.png" alt-text="Dialoglodziņš, lai ievadītu detalizētu informāciju par Azure datu ezera savienojumu." lightbox="media/data_sources_ADLS.png":::

1. **Ievadiet datu avots nosaukumu** un neobligātu **aprakstu**. Nosaukums unikāli identificē datu avots, un uz to ir atsauce pakārtotajos procesos, un to nevar mainīt.

1. Izvēlieties vienu no tālāk norādītajām opcijām krātuves savienošanai **, izmantojot**. Papildinformāciju skatiet sadaļā [Customer Insights Azure Data Lake Storage savienošana ar Gen2 kontu, izmantojot Azure pakalpojumu principālu](connect-service-principal.md).

   - **Azure resurss**: ievadiet resursa **ID**. Ja vēlaties uzņemt datus no krātuves konta, izmantojot Azure privāto saiti, atlasiet **Iespējot privāto saiti**. Papildinformāciju skatiet sadaļā [Privātās saites](security-overview.md#set-up-an-azure-private-link).
   - **Azure abonements**: atlasiet **abonementu** un pēc tam **grupu** Resursi un **Krātuves kontu**. Ja vēlaties uzņemt datus no krātuves konta, izmantojot Azure privāto saiti, atlasiet **Iespējot privāto saiti**. Papildinformāciju skatiet sadaļā [Privātās saites](security-overview.md#set-up-an-azure-private-link).
  
   > [!NOTE]
   > Lai izveidotu datu avots, konteineram vai krātuves kontam ir nepieciešama viena no šīm lomām:
   >
   >  - Krātuves Blob datu lasītājs ir pietiekams, lai lasītu no krātuves konta un nodotu datus Customer Insights.
   >  - Krātuves Blob data contributor vai Owner ir nepieciešama, ja vēlaties rediģēt manifesta failus tieši programmā Customer Insights.  
  
1. Izvēlieties tā konteinera **nosaukumu**, kurā ir dati un shēma (fails model.json vai manifest.json), no kura importēt datus, un atlasiet **Tālāk**.
   > [!NOTE]
   > Jebkurš model.json vai manifest.json fails, kas saistīts ar citu datu avotu vidē, netiks rādīts sarakstā. Tomēr tādu pašu model.json vai manifest.json failu var izmantot datu avotiem, kas atrodas vairākās vidēs.

1. Lai izveidotu jaunu shēmu, dodieties uz [Jauna shēmas faila](#create-a-new-schema-file) izveide.

1. Lai izmantotu esošu shēmu, naviģējiet uz mapi, kurā ir fails model.json vai manifest.cdm.json. Varat meklēt direktorijā, lai atrastu failu.

1. Atlasiet json failu un atlasiet **Tālāk**. Tiek parādīts pieejamo entītiju saraksts.

   :::image type="content" source="media/review-entities.png" alt-text="Atlasāmo entītiju saraksta dialoglodziņš":::

1. Atlasiet entītijas, kuras vēlaties iekļaut.

   :::image type="content" source="media/ADLS_required.png" alt-text="dialoglodziņš, kurā redzams obligāts primārajai atslēgai":::

   > [!TIP]
   > Lai rediģētu entītiju JSON rediģēšanas interfeisā, atlasiet entītiju un pēc tam **Rediģējiet shēmas failu**. Veiciet izmaiņas un atlasiet **Saglabāt**.

1. Atlasītajām entītijām, kurām nepieciešama inkrementāla norīšana, **sadaļā** Pakāpeniska atsvaidzināšana **tiek parādītas obligātās** vērtības. Par katru no šīm entītijām skatiet rakstu [Inkrementāla atsvaidzinājuma konfigurēšana Azure datu ezera datu avotiem](incremental-refresh-data-sources.md).

1. Atlasītajām entītijām, kurām primārā atslēga nav definēta, **sadaļā Primārā atslēga** tiek parādīta sadaļa **Obligāts**. Attiecībā uz katru no šīm vienībām:
   1. Atlasiet **Obligāts**. Tiek parādīts **entītijas** rediģēšanas panelis.
   1. **Izvēlieties primāro atslēgu**. Primārā atslēga ir entītijai unikāls atribūts. Lai atribūts būtu derīga primārā atslēga, tajā nedrīkst ietvert vērtību dublikātus, trūkstošās vērtības vai nulles vērtības. Virknes, vesela skaitļa un GUID datu tipa atribūti tiek atbalstīti kā primārās atslēgas.
   1. Pēc izvēles mainiet nodalījuma modeli.
   1. Atlasiet **Aizvērt**, lai saglabātu un aizvērtu paneli.

1. Atlasiet atribūtu **skaitu** katrai iekļautajai entītijai. Tiek **parādīta lapa Pārvaldīt atribūtus**.

   :::image type="content" source="media/dataprofiling-entities.png" alt-text="Dialoglodziņš, lai atlasītu datu profilēšanu.":::

   1. Izveidojiet jaunus atribūtus, rediģējiet vai dzēsiet esošos atribūtus. Varat mainīt nosaukumu, datu formātu vai pievienot semantisko tipu.
   1. Lai iespējotu analīzi un citas iespējas, atlasiet **Datu profilēšana** visai entītijai vai konkrētiem atribūtiem. Pēc noklusējuma neviena entītija nav iespējota datu profilēšanai.
   1. Atlasiet **Gatavs**.

1. Atlasiet **Saglabāt**. Tiek **atvērta lapa Datu avoti**, kurā redzams jaunais datu avots sadaļā **Atsvaidzināšanas** statuss.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Datu ielāde var aizņemt laiku. Pēc veiksmīgas atsvaidzināšanas pieņemtos datus var pārskatīt lapā [**Entītijas**](entities.md).

### <a name="create-a-new-schema-file"></a>Jauna shēmas faila izveide

1. Atlasiet **Jauns shēmas fails**.

1. Ievadiet faila nosaukumu un atlasiet **Saglabāt**.

1. Atlasiet **Jauna entītija**. Tiek parādīts **panelis Jauna entītija**.

1. Ievadiet entītijas nosaukumu un izvēlieties datu failu atrašanās **vietu**.
   - **Vairāki .csv vai .parketa faili**: pārlūkojot atrodiet saknes mapi, atlasiet raksta tipu un ievadiet izteiksmi.
   - **Viena .csv vai .parketa faili**: pārlūkojot atrodiet .csv vai .parketa failu un atlasiet to.

   :::image type="content" source="media/ADLS_new_entity_location.png" alt-text="Dialoglodziņš, lai izveidotu jaunu entītiju ar iezīmētu datu failu atrašanās vietu.":::

1. Atlasiet **Saglabāt**.

   :::image type="content" source="media/ADLS_new_entity_define_attributes.png" alt-text="Dialoglodziņš, lai definētu vai automātiski ģenerētu atribūtus.":::

1. Atlasiet **definēt atribūtus**, lai manuāli pievienotu atribūtus, vai atlasiet **tos** automātiski ģenerēt. Lai definētu atribūtus, ievadiet nosaukumu, atlasiet datu formātu un neobligāto semantisko tipu. Automātiski ģenerētiem atribūtiem:

   1. Kad atribūti ir ģenerēti automātiski, atlasiet **Pārskatīt atribūtus**. Tiek **parādīta lapa Pārvaldīt atribūtus**.

   1. Pārliecinieties, vai datu formāts katram atribūtam ir pareizs.

   1. Lai iespējotu analīzi un citas iespējas, atlasiet **Datu profilēšana** visai entītijai vai konkrētiem atribūtiem. Pēc noklusējuma neviena entītija nav iespējota datu profilēšanai.

      :::image type="content" source="media/dataprofiling-entities.png" alt-text="Dialoglodziņš, lai atlasītu datu profilēšanu.":::

   1. Atlasiet **Gatavs**. Tiek **parādīta lapa Atlasīt entītijas**.

1. Turpiniet pievienot entītijas un atribūtus, ja piemērojams.

1. Kad visas entītijas ir pievienotas, atlasiet **Iekļaut**, lai entītijas iekļautu datu avots norīšanas.

   :::image type="content" source="media/ADLS_required.png" alt-text="dialoglodziņš, kurā redzams obligāts primārajai atslēgai":::

1. Atlasītajām entītijām, kurām nepieciešama inkrementāla norīšana, **sadaļā** Pakāpeniska atsvaidzināšana **tiek parādītas obligātās** vērtības. Par katru no šīm entītijām skatiet rakstu [Inkrementāla atsvaidzinājuma konfigurēšana Azure datu ezera datu avotiem](incremental-refresh-data-sources.md).

1. Atlasītajām entītijām, kurām primārā atslēga nav definēta, **sadaļā Primārā atslēga** tiek parādīta sadaļa **Obligāts**. Attiecībā uz katru no šīm vienībām:
   1. Atlasiet **Obligāts**. Tiek parādīts **entītijas** rediģēšanas panelis.
   1. **Izvēlieties primāro atslēgu**. Primārā atslēga ir entītijai unikāls atribūts. Lai atribūts būtu derīga primārā atslēga, tajā nedrīkst ietvert vērtību dublikātus, trūkstošās vērtības vai nulles vērtības. Virknes, vesela skaitļa un GUID datu tipa atribūti tiek atbalstīti kā primārās atslēgas.
   1. Pēc izvēles mainiet nodalījuma modeli.
   1. Atlasiet **Aizvērt**, lai saglabātu un aizvērtu paneli.

1. Atlasiet **Saglabāt**. Tiek **atvērta lapa Datu avoti**, kurā redzams jaunais datu avots sadaļā **Atsvaidzināšanas** statuss.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Datu ielāde var aizņemt laiku. Pēc veiksmīgas atsvaidzināšanas pieņemtos datus var pārskatīt lapā [**Entītijas**](entities.md).

## <a name="edit-an-azure-data-lake-storage-data-source"></a>Azure Data Lake Storage datu avots rediģēšana

Varat atjaunināt opciju *Izveidot savienojumu ar krātuves kontu, izmantojot opciju*. Papildinformāciju skatiet sadaļā [Customer Insights Azure Data Lake Storage savienošana ar Gen2 kontu, izmantojot Azure pakalpojumu principālu](connect-service-principal.md). Lai izveidotu savienojumu ar citu konteineru no krātuves konta vai mainītu konta nosaukumu, [izveidojiet jaunu datu avota savienojumu](#connect-to-azure-data-lake-storage).

1. Dodieties uz **Dati** > **Datu avoti**.

1. Blakus datu avots, kuru vēlaties atjaunināt, atlasiet **Rediģēt**.

   :::image type="content" source="media/data_sources_edit_ADLS.png" alt-text="Dialoglodziņš, lai rediģētu Azure Data Lake datu avots.":::

1. Mainiet kādu no šīm ziņām:

   - **Apraksts**
   - **Savienojiet krātuvi, izmantojot** un savienojuma informāciju. Atjauninot savienojumu, nevar mainīt **Konteinera** informāciju.
      > [!NOTE]
      > Krātuves kontam vai konteineram ir jāpiešķir viena no šīm lomām:
        > - Krātuves Blob datu lasītājs
        > - Krātuves Blob datu īpašnieks
        > - Krātuves Blob datu ieguldītājs

   - **Iespējojiet privāto saiti**, ja vēlaties uzņemt datus no krātuves konta, izmantojot Azure privāto saiti. Papildinformāciju skatiet sadaļā [Privātās saites](security-overview.md#set-up-an-azure-private-link).

1. Atlasiet **Tālāk**.
1. Mainiet kādu no šīm darbībām:
   - Naviģējiet uz citu failu model.json vai manifest.json ar atšķirīgu entītiju kopu no konteinera.
   - Lai norietam pievienotu papildu entītijas, atlasiet **Jauna entītija**.
   - Lai noņemtu jau atlasītās entītijas, ja nav atkarību, atlasiet entītiju un **Dzēst**.
      > [!IMPORTANT]
      > Ja esošajā model.json vai manifest.json failā un entītiju kopā ir atkarības, tiks parādīts kļūdas ziņojums un nevarēs atlasīt citu model.json vai manifest.json failu. Pirms maināt model.json vai manifest.json failu, noņemiet šīs atkarības vai izveidojiet jaunu datu avotu ar model.json vai manifest.json failu, kuru vēlaties izmantot, lai izvairītos no atkarību noņemšanas.
   - Lai mainītu datu faila atrašanās vietu vai primāro atslēgu, atlasiet **Rediģēt**.
   - Lai mainītu inkrementālās norīšanas datus, skatiet rakstu [Pakāpeniskās atsvaidzināšanas konfigurēšana Azure Data Lake datu avotiem](incremental-refresh-data-sources.md).
   - Mainiet entītijas nosaukumu tikai, lai tas atbilstu entītijas nosaukumam .json failā.

     > [!NOTE]
     > Pēc norīšanas vienmēr saglabājiet entītijas nosaukumu programmā Customer Insights tāpat kā entītijas nosaukumu failā model.json vai manifest.json. Customer Insights validē visus entītiju nosaukumus, izmantojot model.json vai manifest.json katras sistēmas atsvaidzināšanas laikā. Ja entītijas nosaukums tiek mainīts vai nu programmā Customer Insights, vai ārpus tās, rodas kļūda, jo Customer Insights nevar atrast jauno entītijas nosaukumu .json failā. Ja nejauši tika mainīts uzņemtās entītijas nosaukums, rediģējiet entītijas nosaukumu programmā Customer Insights, lai tas atbilstu nosaukumam .json failā.

1. Atlasiet **Atribūti**, lai pievienotu vai mainītu atribūtus vai iespējotu datu profilēšanu. Tad atlasiet **Gatavs**.

1. Noklikšķiniet uz **Saglabāt**, lai lietotu izmaiņas un atgrieztos **lapā Datu avoti**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
