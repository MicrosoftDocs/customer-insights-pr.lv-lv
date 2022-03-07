---
title: Auditorijas ieskatu segmenti
description: Segmentu pārskats un to izveide un pārvaldība.
ms.date: 11/01/2021
ms.subservice: audience-insights
ms.topic: overview
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-customers-page
- ci-enrichment-details
- ci-segments
- ci-segment-details
- customerInsights
ms.openlocfilehash: c58f79c2beda1083d19bd36d94549ff1a46b096e
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 02/25/2022
ms.locfileid: "8355992"
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

Lai skatītu visus saglabātos segmentus un tos pārvaldītu, atveriet lapu **Segmenti**.

Katru segmentu apzīmē rinda, kurā ir iekļauta papildu informācija par segmentu.

:::image type="content" source="media/segments-selected-segment.png" alt-text="Atlasīts segments ar opciju nolaižamo sarakstu un pieejamajām opcijām.":::

Kad atlasāt segmentu, ir pieejamas tālāk norādītās darbības:

- **Skatīt** segmenta informāciju, tostarp segmenta dalībnieku skaita tendences priekšskatījumu.
- **Rediģēt** segmentu, lai mainītu tā rekvizītus.
- **Izveidot dublikātu** segmentam. Varat izvēlēties rediģēt tā rekvizītus uzreiz vai vienkārši saglabāt dublikātu.
- **Atsvaidzināt** segmentu, lai iekļautu jaunākos datus.
- **Aktivizēt** vai **Deaktivizēt** segmentu. Segmentiem ir divi iespējamie statusi — aktīvs vai neaktīvs. Šie statusi ir noderīgi, rediģējot segmentu. Neaktīvajiem segmentiem pastāv segmenta definīcija, taču tajā vēl nav klientu. Aktivizējot segmentu, tā statuss tiek mainīts no “neaktīvs” uz “aktīvs”, un tas sāk meklēt klientus, kas atbilst segmenta definīcijai. Ja ir konfigurēta [plānotā atsvaidzināšana](system.md#schedule-tab), neaktīvajiem segmentiem **Statuss** ir norādīts kā **Izlaists**, kas norāda, ka atsvaidzināšana nav pat mēģināta. Ja ir aktivizēts neaktīvs segments, tas tiek atsvaidzināts un iekļauts atsvaidzināšanas grafikā.
  Vai arī varat izmantot funkcionalitāti **Plānot vēlāk** nolaižamajā izvēlnē **Aktivizēt/Deaktivizēt**, lai norādītu nākotnes datumu un laiku noteikta segmenta aktivizēšanai un deaktivizēšanai.
- **Pārdēvēt** segmentu.
- **Lejupielādēt** dalībnieku sarakstu kā .CSV failu.
- **Pārvaldīt eksportu**, lai skatītu ar eksportu saistīto segmentu un pārvaldītu to. [Uzzināt vairāk par eksportēšanu.](export-destinations.md)
- **Dzēst** segmentu.

## <a name="refresh-segments"></a>Atsvaidzināt segmentus

Visus segmentus uzreiz var atsvaidzināt, atlasot **Atsvaidzināt visus** lapā **Segmenti**, vai varat atsvaidzināt vienu vai vairākus segmentus, tos atlasot un izvēloties opciju **Atsvaidzināt** no piedāvātajām opcijām. Vai arī varat konfigurēt periodisku atsvaidzināšanu sadaļā **Administrators** > **Sistēma** > **Grafiks**.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="export-segments"></a>Segmentu eksportēšana

Segmentu var eksportēt no segmentu lapas vai [eksportēšanas lapas](export-destinations.md). 

1. Doties uz lapu **Segmenti**.

1. Atlasiet **Parādīt vēl [...]** eksportējamam segmentam.

1. Darbību nolaižamajā sarakstā atlasiet **Pārvaldīt eksportēšanas darbības**.

1. Tiek atvērta lapa **Segmenta eksports (priekšskatījums)**. Varat skatīt visus konfigurētos eksportus, sagrupētus pēc tā, vai tajos ir iekļauts pašreizējais segments.

   1. Lai pievienotu atlasīto segmentu eksportēšanai, **Rediģējiet** attiecīgo eksportu, lai atlasītu atbilstošo segmentu, un pēc tam saglabājiet. Tā vietā individuālo klientu vidēs varat atlasīt eksportēšanu sarakstā un atlasīt opciju **Pievienot segmentu**, lai sasniegtu tādu pašu rezultātu.

   1. Lai izveidotu jaunu eksportu ar atlasīto segmentu, atlasiet **Pievienot eksportēšanu**. Papildinformāciju par eksportēšanas darbību izveidi skatiet rakstā [Jaunas eksportēsanas darbības iestatīšana](export-destinations.md#set-up-a-new-export).

1. Atlasiet **Atpakaļ**, lai atgrieztos segmentu galvenajā lapā.

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


[!INCLUDE[footer-include](../includes/footer-banner.md)]