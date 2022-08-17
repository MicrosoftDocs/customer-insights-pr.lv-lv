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
ms.openlocfilehash: 195a7c733f047c24f9f47a151c1cb623fe34d055
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 08/10/2022
ms.locfileid: "9246302"
---
# <a name="segments-overview"></a>Segmentu pārskats

Segmenti jums ļauj sagrupēt klientus, pamatojoties uz demogrāfiskajiem, transakciju vai uzvedības atribūtiem. Lai sasniegtu uzņēmuma mērķus, var izmantot segmentus, lai mērķētu reklāmas kampaņas, pārdošanas darbības un klientu atbalsta darbības.

Klientu profili, kas atbilst segmenta definīcijas filtriem, *tiek saukti par segmenta dalībniekiem*. Ir [spēkā noteikti pakalpojuma ierobežojumi](/dynamics365/customer-insights/service-limits).

## <a name="create-a-segment"></a>Segmenta izveide

Izvēlieties, kā izveidot segmentu, pamatojoties uz savu mērķauditoriju.

# <a name="individual-consumers-b-to-c"></a>[Atsevišķi patērētāji (B2C)](#tab/b2c)

- Sarežģīti segmenti ar segmentu veidotāju: [izveidojiet savu](segment-builder.md)
- Vienkārši segmenti ar vienu operatoru: [ātrais segments](segment-quick.md)
- Mi darbināts veids, kā atrast līdzīgus klientus: [līdzīgi klienti](find-similar-customer-segments.md)
- Ar MI nodrošināti ieteikumi, kuru pamatā ir mēri vai atribūti: [ieteiktie segmenti, kuru pamatā ir mērījumi](suggested-segments.md)
- Uz darbībām balstīti ieteikumi: [ieteiktie segmenti, pamatojoties uz klientu darbību](suggested-segments-activity.md)

# <a name="business-accounts-b-to-b"></a>[Uzņēmumu konti (B2B)](#tab/b2b)

- Vienkārši vai sarežģīti segmenti ar segmentu veidotāju: [izveidojiet savu](segment-builder.md)

---

## <a name="manage-existing-segments"></a>Esošo segmentu pārvaldība

Dodieties uz **lapu Segmenti**, lai skatītu izveidotos segmentus, to statusu un stāvokli, dalībnieku skaitu un pēdējo reizi, kad dati tika atsvaidzināti. Segmentu sarakstu var kārtot pēc jebkuras kolonnas vai izmantot meklēšanas lodziņu, lai atrastu segmentu, kuru vēlaties pārvaldīt.

Atlasiet segmentu, lai skatītu pieejamās darbības.

:::image type="content" source="media/segments-selected-segment.png" alt-text="Atlasīts segments ar opciju nolaižamo sarakstu un pieejamajām opcijām." lightbox="media/segments-selected-segment.png":::

- [**Skatiet**](#view-segment-details) detalizētu informāciju par segmentu, tostarp dalībnieku skaita tendenci un segmenta dalībnieku priekšskatījumu.
- **Lejupielādēt** dalībnieku sarakstu kā .CSV failu.
- **Rediģēt** segmentu, lai mainītu tā rekvizītus.
- **Izveidot dublikātu** segmentam. Varat izvēlēties uzreiz rediģēt tā rekvizītus vai saglabāt dublikātu.
- [**Atsvaidziniet**](#refresh-segments) segmentu, lai iekļautu jaunākos datus.
- **Aktivizēt** vai **Deaktivizēt** segmentu. Neaktīvie segmenti netiks atsvaidzināti plānotās atsvaidzināšanas [laikā](schedule-refresh.md), un statuss **tiks** norādīts kā **Izlaists**, kas norāda, ka atsvaidzināšana pat netika mēģināta. Aktīvie segmenti tiek atsvaidzināti, pamatojoties uz to veidu: statisks vai dinamisks.
- **Padariet statisku** vai **Padariet dinamisku** par segmenta tipu. Statiskie segmenti ir jāatsvaidzina manuāli. Dinamiskie segmenti tiek automātiski atsvaidzināti sistēmas atsvaidzināšanas laikā.
- [**Atrodiet līdzīgus klientus**](find-similar-customer-segments.md) no segmenta.
- **Pārdēvēt** segmentu.
- **Atzīmējiet**, lai [pārvaldītu segmenta tagus](work-with-tags-columns.md#manage-tags).
- [**Pārvaldiet eksportēšanu**](#export-segments), lai skatītu ar eksportu saistītus segmentus un pārvaldītu tos. [Uzzināt vairāk par eksportēšanu.](export-destinations.md)
- **Dzēst** segmentu.
- **Kolonnas**, lai [pielāgotu parādītās kolonnas](work-with-tags-columns.md#customize-columns).
- **Filtrējiet**, lai filtrētu [tagus](work-with-tags-columns.md#filter-on-tags).
- **Meklēt vārdu**, lai meklētu pēc segmenta nosaukuma.

## <a name="view-segment-details"></a>Segmenta detalizētas informācijas skatīšana

**Lapā Segmenti** atlasiet segmentu, lai skatītu apstrādes vēsturi un segmenta dalībniekus.

Lapas augšējā daļa ietver tendenču grafiku, kas vizualizē elementu skaita izmaiņas. Norādiet uz datu punktiem, lai skatītu elementu skaitu noteiktā datumā. Mainiet vizualizācijas laika grafiku.

:::image type="content" source="media/segment-time-range.png" alt-text="Segmenta laika diapazons.":::

Apakšējā daļa ietver segmenta elementu sarakstu.

> [!NOTE]
> Šajā sarakstā parādītie lauki tiek balstīti uz segmenta entītiju atribūtiem.
>
>Saraksts ir atbilstošo segmenta dalībnieku priekšskatījums un parāda jūsu segmenta pirmos 100 ierakstus, lai to varētu ātri novērtēt un vajadzības gadījumā pārskatīt tā definīcijas. Lai skatītu visus atbilstošos ierakstus, [eksportējiet segmentu](export-destinations.md).

## <a name="refresh-segments"></a>Atsvaidzināt segmentus

Segmentus var atsvaidzināt pēc automātiska grafika vai atsvaidzināt manuāli pēc pieprasījuma. Lai manuāli atsvaidzinātu vienu vai vairākus segmentus, atlasiet tos un izvēlieties **Atsvaidzināt**.

Lai [ieplānotu automātisku atsvaidzināšanu](schedule-refresh.md), dodieties uz **administrēšanas** > **sistēmas** > **grafiku**. Piemēro šādus noteikumus:

- Visi segmenti ar tipu **Dynamic** vai **Expansion** tiks automātiski atsvaidzināti iestatītajā kadencē. Kad atsvaidzināšana ir pabeigta, statuss **norāda,** vai ir bijušas problēmas ar segmenta atsvaidzināšanu. Pēdējais **atsvaidzinātais** parāda pēdējās veiksmīgās atsvaidzināšanas laikspiedolu. Ja rodas kļūda, atlasiet kļūdu, lai skatītu detalizētu informāciju par notikušo.
- Segmenti ar tipu **Static** *netiks* atsvaidzināti automātiski. Pēdējais **atsvaidzinātais** parāda laika zīmogu no pēdējās reizes, kad statiskais segments tika palaists vai atsvaidzināts manuāli.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="export-segments"></a>Segmentu eksportēšana

Eksportējiet segmentus uz citām programmām, lai turpinātu izmantot datus. Eksportējiet segmentu no segmentu lapas vai eksportēšanas [lapas](export-destinations.md).

1. Dodieties uz **lapu Segmenti** un atlasiet segmentu, kuru vēlaties eksportēt.

1. Atlasiet **Pārvaldīt eksportēšanu**. Tiek atvērta lapa **Segmenta eksports (priekšskatījums)**. Skatiet visas konfigurētās eksportēšanas, kas sagrupētas pēc tā, vai tajās ir pašreizējais segments vai nav.

   1. Lai pievienotu atlasīto segmentu eksportēšanai, **Rediģējiet** attiecīgo eksportu, lai atlasītu atbilstošo segmentu, un pēc tam saglabājiet. Vidēs, kas paredzētas atsevišķiem klientiem, sarakstā atlasiet eksportēt un atlasiet **Pievienot segmentu**, lai sasniegtu tādu pašu rezultātu.

   1. Lai izveidotu jaunu eksportu ar atlasīto segmentu, atlasiet **Pievienot eksportēšanu**. Papildinformāciju par eksportēšanas darbību izveidi skatiet rakstā [Jaunas eksportēsanas darbības iestatīšana](export-destinations.md#set-up-a-new-export).

1. Atlasiet **Atpakaļ**, lai atgrieztos segmentu galvenajā lapā.

## <a name="track-usage-of-a-segment"></a>Segmenta lietojuma izsekošana

Ja izmantojat segmentus programmās, kuru pamatā ir tā pati Microsoft Dataverse organizācija, kas ir saistīta ar Customer Insights, varat izsekot segmenta lietojumam. Customer [Insights segmentiem, kas tiek izmantoti Dynamics 365 Marketing](/dynamics365/marketing/real-time-marketing-ci-profile) automatizētajās kampaņās, sistēma informē jūs par šī segmenta lietojumu.

Rediģējot segmentu, kas tiek izmantots Customer Insights vidē vai mārketinga automatizēta kampaņa, segmentu veidotāja [reklāmkarogs](segment-builder.md) informē jūs par atkarībām. Pārbaudiet atkarības informāciju tieši no reklāmkaroga vai segmentu veidotājā atlasot **Lietojums**.

Segmenta **lietojuma** rūtī ir redzama detalizēta informācija par šī segmenta Dataverse lietojumu programmās. Segmentiem, kas tiek izmantoti automatizētajās kampaņās, atradīsit saiti, lai pārbaudītu ceļu mārketingā, kurā šis segments tiek izmantots. Ja jums ir atļaujas piekļūt programmai Mārketings, skatiet papildinformāciju tur.

:::image type="content" source="media/segment-usage-pane.png" alt-text="Sānu rūts ar detalizētu informāciju par segmenta lietojumu segmentu veidotājā.":::

Sistēma informē jūs par izsekotā segmenta izmantošanu, kad mēģināt to izdzēst. Ja segments, kuru gatavojaties dzēst, tiek izmantots mārketinga automatizēta kampaņa, šis ceļš tiks pārtraukts visiem segmenta lietotājiem. Ja ceļojums ir daļa no mārketinga kampaņas, dzēšana ietekmēs pašu kampaņu. Tomēr, neskatoties uz brīdinājumiem, joprojām varat izdzēst segmentu.

:::image type="content" source="media/segment-usage-delete.png" alt-text="Dialoglodziņš, lai apstiprinātu segmenta dzēšanu, ja segments Dataverse tiek izmantots lietojumprogrammā.":::

### <a name="supported-apps"></a>Atbalstītās lietotnes

Lietojums pašlaik tiek izsekots tālāk norādītajās Dataverse lietotnēs.

- [Automatizētās darbības dynamics 365 mārketingā](/dynamics365/marketing/real-time-marketing-ci-profile)

[!INCLUDE [footer-include](includes/footer-banner.md)]
