---
title: Segmentu pārskats
description: Segmentu pārskats un to izveide un pārvaldība.
ms.date: 05/20/2022
ms.subservice: audience-insights
ms.topic: overview
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-customers-page
- ci-enrichment-details
- ci-segments
- ci-segment-details
- customerInsights
ms.openlocfilehash: 8b2c2f9b84bf8b7f37d1468b871946ecb3e6aa98
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 06/29/2022
ms.locfileid: "9050956"
---
# <a name="segments-overview"></a>Segmentu pārskats

Segmenti jums ļauj sagrupēt klientus, pamatojoties uz demogrāfiskajiem, transakciju vai uzvedības atribūtiem. Lai sasniegtu uzņēmuma mērķus, var izmantot segmentus, lai mērķētu reklāmas kampaņas, pārdošanas darbības un klientu atbalsta darbības.

Klientu profili, kas atbilst segmenta definīcijas filtriem, tiek saukti par segmenta *dalībniekiem*. Ir [spēkā noteikti pakalpojuma ierobežojumi](/dynamics365/customer-insights/service-limits).

## <a name="create-a-new-segment"></a>Izveidot jaunu segmentu

Ir vairāki jauna segmenta izveides veidi: 

# <a name="individual-consumers-b-to-c"></a>[Atsevišķi patērētāji (B2C)](#tab/b2c)

- Sarežģīts segments ar segmentu veidotāju: [Izveidojiet savu](segment-builder.md#create-a-new-segment) 
- Vienkārši segmenti ar vienu operatoru: [ātrais segments](segment-builder.md#quick-segments) 
- AI veids, kā atrast līdzīgus klientus: [līdzīgi klienti](find-similar-customer-segments.md) 
- AI sekmēti ierosinājumi, kas balstīti uz pasākumiem vai atribūtiem: [ieteiktie segmenti pasākumu uzlabošanai](suggested-segments.md) 
- Uz darbībām balstīti ieteikumi: [ieteiktie segmenti, pamatojoties uz klientu darbību](suggested-segments-activity.md) 

# <a name="business-accounts-b-to-b"></a>[Uzņēmumu konti (B2B)](#tab/b2b)

- Sarežģīts segments ar segmentu veidotāju: [Izveidojiet savu](segment-builder.md#create-a-new-segment)

---

## <a name="manage-existing-segments"></a>Esošo segmentu pārvaldība

Dodieties uz **lapu Segmenti**, lai skatītu visus saglabātos segmentus un pārvaldītu tos.

Katru segmentu apzīmē rinda, kurā ir iekļauta papildu informācija par segmentu.

:::image type="content" source="media/segments-selected-segment.png" alt-text="Atlasīts segments ar opciju nolaižamo sarakstu un pieejamajām opcijām." lightbox="media/segments-selected-segment.png":::

Atlasot segmentu, ir pieejamas šādas darbības:

- **Skatīt** segmenta informāciju, tostarp segmenta dalībnieku skaita tendences priekšskatījumu.
- **Lejupielādēt** dalībnieku sarakstu kā .CSV failu.
- **Rediģēt** segmentu, lai mainītu tā rekvizītus.
- **Izveidot dublikātu** segmentam. Varat izvēlēties uzreiz rediģēt tā rekvizītus vai saglabāt dublikātu.
- **Atsvaidzināt** segmentu, lai iekļautu jaunākos datus.
- **Aktivizēt** vai **Deaktivizēt** segmentu. Neaktīvajiem segmentiem pastāv segmenta definīcija, taču tajā vēl nav klientu. Aktīvs segments meklē klientus, kas atbilst segmenta definīcijai. Ja ir konfigurēta [plānotā atsvaidzināšana](system.md#schedule-tab), neaktīvajiem segmentiem **Statuss** ir norādīts kā **Izlaists**, kas norāda, ka atsvaidzināšana nav pat mēģināta. Ja ir aktivizēts neaktīvs segments, tas tiek atsvaidzināts un iekļauts atsvaidzināšanas grafikā.
  Vai arī varat izmantot funkcionalitāti **Plānot vēlāk** nolaižamajā izvēlnē **Aktivizēt/Deaktivizēt**, lai norādītu nākotnes datumu un laiku noteikta segmenta aktivizēšanai un deaktivizēšanai.
- **[Atrodiet līdzīgus klientus](find-similar-customer-segments.md)** no segmenta.
- **Pārdēvēt** segmentu.
- **Atzīmējiet**, lai [pārvaldītu segmenta tagus](work-with-tags-columns.md#manage-tags).
- **Lejupielādēt** dalībnieku sarakstu kā .CSV failu.
- **Pārvaldīt eksportu**, lai skatītu ar eksportu saistīto segmentu un pārvaldītu to. [Uzzināt vairāk par eksportēšanu.](export-destinations.md)
- **Dzēst** segmentu.
- **Kolonnas**, lai [pielāgotu parādītās kolonnas](work-with-tags-columns.md#customize-columns).
- **Filtrējiet**, lai filtrētu [tagus](work-with-tags-columns.md#filter-on-tags).
- **Meklēt vārdu**, lai meklētu pēc segmenta nosaukuma.

## <a name="refresh-segments"></a>Atsvaidzināt segmentus

Visus segmentus uzreiz var atsvaidzināt, atlasot **Atsvaidzināt visus** lapā **Segmenti**, vai varat atsvaidzināt vienu vai vairākus segmentus, tos atlasot un izvēloties opciju **Atsvaidzināt** no piedāvātajām opcijām. Vai arī varat konfigurēt periodisku atsvaidzināšanu sadaļā **Administrators** > **Sistēma** > **Grafiks**. Ja ir konfigurēta periodiska atsvaidzināšana, tiek piemēroti šādi noteikumi:

- Visi segmenti ar tipu **Dynamic** vai **Expansion** tiks automātiski atsvaidzināti iestatītajā kadencē. Kad atsvaidzināšana ir pabeigta, **statuss** norāda, vai ir bijušas kādas problēmas ar segmenta atsvaidzināšanu. Pēdējais **atsvaidzinātais** parāda pēdējās veiksmīgās atsvaidzināšanas laikspiedolu. Ja rodas kļūda, atlasiet kļūdu, lai skatītu detalizētu informāciju par notikušo.
- Segmenti ar tipu **Static** *netiks* atsvaidzināti automātiski. Pēdējā **atsvaidzinātajā** tiek rādīts laikspiedols, kas iegūts pēdējā reizē, kad statiskie segmenti tika palaisti vai atsvaidzināti manuāli.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="export-segments"></a>Segmentu eksportēšana

Segmentu var eksportēt no segmentu lapas vai [eksportēšanas lapas](export-destinations.md). 

1. Doties uz lapu **Segmenti**.

1. Atlasiet vertikālo elipsi (&vellip;) segmentam, kuru vēlaties eksportēt.

1. Darbību nolaižamajā sarakstā atlasiet **Pārvaldīt eksportēšanas darbības**.

1. Tiek atvērta lapa **Segmenta eksports (priekšskatījums)**. Varat skatīt visus konfigurētos eksportus, sagrupētus pēc tā, vai tajos ir iekļauts pašreizējais segments.

   1. Lai pievienotu atlasīto segmentu eksportēšanai, **Rediģējiet** attiecīgo eksportu, lai atlasītu atbilstošo segmentu, un pēc tam saglabājiet. Atsevišķu klientu vidēs varat atlasīt eksportu sarakstā un atlasīt **Pievienot segmentu**, lai sasniegtu tādu pašu rezultātu.

   1. Lai izveidotu jaunu eksportu ar atlasīto segmentu, atlasiet **Pievienot eksportēšanu**. Papildinformāciju par eksportēšanas darbību izveidi skatiet rakstā [Jaunas eksportēsanas darbības iestatīšana](export-destinations.md#set-up-a-new-export).

1. Atlasiet **Atpakaļ**, lai atgrieztos segmentu galvenajā lapā.

## <a name="track-usage-of-a-segment"></a>Segmenta lietojuma izsekošana

Ja programmās izmantojat segmentus, kuru pamatā ir tā pati Microsoft Dataverse organizācija, kas ir saistīta ar Customer Insights, varat izsekot segmenta lietojumam. Customer [Insights segmentiem, kas tiek izmantoti Dynamics 365 Marketing](/dynamics365/marketing/real-time-marketing-ci-profile) automatizētajās kampaņās, sistēma informē jūs par šī segmenta lietojumu.

Rediģējot segmentu, kas tiek izmantots Customer Insights vidē vai mārketinga automatizēta kampaņa, segmentu veidotāja [reklāmkarogs](segment-builder.md) informē jūs par atkarībām. Atkarības informāciju varat pārbaudīt tieši no reklāmkaroga vai segmentu veidotājā atlasot **Lietojums**.

Segmenta **lietojuma** rūtī ir redzama detalizēta informācija par šī segmenta Dataverse lietojumu programmās. Segmentiem, kas tiek izmantoti automatizētajās kampaņās, atradīsit saiti, lai pārbaudītu ceļu mārketingā, kurā šis segments tiek izmantots. Ja jums ir atļaujas piekļūt programmai Mārketings, varat tur piekļūt papildinformācijai.

:::image type="content" source="media/segment-usage-pane.png" alt-text="Sānu rūts ar detalizētu informāciju par segmenta lietojumu segmentu veidotājā.":::

Sistēma informē jūs par izsekotā segmenta izmantošanu, kad mēģināt to izdzēst. Ja segments, kuru gatavojaties dzēst, tiek izmantots mārketinga automatizēta kampaņa, šis ceļš tiks pārtraukts visiem segmenta lietotājiem. Ja ceļojums ir daļa no mārketinga kampaņas, dzēšana ietekmēs pašu kampaņu. Tomēr, neskatoties uz brīdinājumiem, joprojām varat izdzēst segmentu.

:::image type="content" source="media/segment-usage-delete.png" alt-text="Dialoglodziņš, lai apstiprinātu segmenta dzēšanu, ja segments Dataverse tiek izmantots lietojumprogrammā.":::

### <a name="supported-apps"></a>Atbalstītās lietotnes

Lietojums pašlaik tiek izsekots tālāk norādītajās Dataverse lietotnēs.

- [Automatizētās darbības dynamics 365 mārketingā](/dynamics365/marketing/real-time-marketing-ci-profile)

## <a name="view-processing-history-and-segment-members"></a>Apstrādes vēstures un segmentu elementu skatīšana

Lai skatītu apkopotos datus par segmentu, pārskatot informāciju par segmentu.

Lapā **Segmenti** atlasiet segmentu, kuru vēlaties pārskatīt.

Lapas augšējā daļa ietver tendenču grafiku, kas vizualizē elementu skaita izmaiņas. Norādiet uz datu punktiem, lai skatītu elementu skaitu noteiktā datumā.

Varat atjaunināt vizualizācijas laika periodu.

> [!div class="mx-imgBorder"]
> ![Segmenta laika diapazons.](media/segment-time-range.png "Segmenta laika diapazons")

Apakšējā daļa ietver segmenta elementu sarakstu.

> [!NOTE]
> Šajā sarakstā parādītie lauki tiek balstīti uz segmenta entītiju atribūtiem.
>
>Saraksts ir atbilstošo segmenta dalībnieku priekšskatījums un parāda jūsu segmenta pirmos 100 ierakstus, lai to varētu ātri novērtēt un vajadzības gadījumā pārskatīt tā definīcijas. Lai skatītu visus atbilstošos ierakstus, ir [jāeksportē šis segments](export-destinations.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
