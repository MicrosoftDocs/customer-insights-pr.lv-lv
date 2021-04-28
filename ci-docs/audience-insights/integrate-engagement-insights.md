---
title: Tīmekļa datu integrēšana no iesaistes ieskatiem ar auditorijas ieskatiem
description: Tīmekļa informāciju par klientiem varat pārnest no iesaistes ieskatiem uz auditorijas ieskatiem.
ms.date: 12/17/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 9a4cb77bb4c6ef0d88b3f00802f66baab5520a07
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896428"
---
# <a name="integrate-web-data-from-engagement-insights-with-audience-insights"></a>Tīmekļa datu integrēšana no iesaistes ieskatiem ar auditorijas ieskatiem

Klienti bieži vien veic ikdienas darījumus tiešsaistē, izmantojot interneta vietnes. Iesaistes ieskatu iespēja programmā Dynamics 365 Customer Insights ir parocīgs risinājums, kas ļauj tīmekļa datus integrēt kā avotu. Papildus transakciju, demogrāfiskajiem vai uzvedības datiem mēs tīmeklī redzam darbības vienotos klientu profilos. Mēs varam izmantot šo profilu, lai auditorijas aktivizēšanai gūtu papildu ieskatus, piemēram, segmentus, pasākumus vai prognozes.

Šajā rakstā ir aprakstītas darbības, kas jāveic, lai klientu tīmekļa darbību datus no iesaistes ieskatiem pārvērstu esošajā auditorijas ieskatu vidē.

Šajā piemērā mēs uzņemam vidi, kurā ir vienoti klientu profili. Profili tika vienoti ar aptauju, mazumtirdzniecības un biļešu iegādes sistēmas avotiem. Tiek parādītas arī klientu saistītās darbības. 

Tagad mēs vēlamies zināt, vai klients apmeklē mūsu tīmekļa rekvizītus un izprot savas darbības. Darbības ietver, piemēram, apmeklētas vietnes vai produktu lapu skatīšanu no e-pastā saņemtās saites.

## <a name="prerequisites"></a>Priekšnosacījumi

Lai integrētu datus no iesaistes ieskatiem, ir jāizpilda daži priekšnosacījumi: 

- Integrējiet iesaistes ieskatu SDK savā vietnē. Papildinformāciju skatiet rakstā [Darba sākšana ar tīmekļa SDK](../engagement-insights/instrument-website.md).
- Tīmekļa notikumu eksportēšanai no iesaistes ieskatiem ir nepieciešama piekļuve ADLS Gen 2 krātuves kontam, kas tiks izmantots, lai tīmekļa notikumu datus ievadītu auditorijas ieskatos. Papildinformāciju skatiet [Eksportēt notikumus](../engagement-insights/export-events.md).

## <a name="configure-refined-events-in-engagement-insights"></a>Konfigurēt precizētos notikumus iesaistes ieskatos

Pēc tam, kad administrators ir izveidojis vietni ar iesaistes ieskatu SDK, tiek apkopoti *pamatnotikumi*, kad lietotājs skata tīmekļa lapu vai kaut kur noklikšķina. Pamatnotikumos parasti ir ietverta detalizēta informācija. Atkarībā no izmantošanas gadījuma datu apakšgrupa ir nepieciešama tikai pamatnotikumā. Iesaistes ieskati jums ļauj izveidot *precizētus notikumus*, kuros ir tikai atlasītie pamatnotikuma rekvizīti.     

Papildinformācijai skatiet [Precizēto notikumu izveide un modificēšana](../engagement-insights/refined-events.md).

Apsvērumi, kas rodas, izveidojot precizētos notikumus: 

- Norādiet jēgpilnu precizētā notikuma nosaukumu. Tas tiek izmantots kā darbības nosaukums auditorijas ieskatos.
- Atlasiet vismaz sekojošos rekvizītus, lai izveidotu darbību auditorijas ieskatos: 
    - Signal.Action.Name - darbības informācijas norādīšana
    - Signal.User.Id - lieto, lai kartētu ar klienta ID
    - Signal.View.Uri - izmanto kā tīmekļa adresi segmentu vai pasākumu pamatam
    - Signal.Export.Id - lai izmantotu kā primāro atslēgu notikumiem
    - Signal.Timestamp - lai noteiktu darbības datumu un laiku

Atlasiet filtrus, lai koncentrētos uz notikumiem un lapām, kas ir svarīgas jūsu gadījumam. Šajā piemērā tiks izmantots darbības nosaukums "E-pasta veicināšanas pasākums".

## <a name="export-the-refined-web-events"></a>Eksportējiet precizētos tīmekļa notikumus 

Pēc precizētā notikuma definēšanas ir jākonfigurē notikuma datu eksportēšana uz Azure Data Lake Storage, ko var iestatīt kā datu avota iekļaušanu auditorijas ieskatos. Eksportēšana notiek pastāvīgi kā notikumu plūsma no tīmekļa rekvizīta.

Papildinformāciju skatiet [Eksportēt notikumus](../engagement-insights/export-events.md).

## <a name="ingest-event-data-to-audience-insights"></a>Notikuma datu iesniegšana auditorijas ieskatos

Tagad, kad esat definējis precizēto notikumu un konfigurējis tā eksportēšanu, mēs pārejam uz datu iesniegšanu auditorijas ieskatos. Jums ir jāizveido jauns datu datu avots, pamatojoties uz Common Data Model mapi. Ievadiet detalizētu informāciju par to krātuves kontu, uz kuru eksportējat notikumus. Failā *default.cdm.json* atlasiet iesniedzamo, precizēto notikumu un izveidojiet entītiju auditorijas ieskatos.

Papildinformāciju skatiet sadaļā [Savienojuma izveide ar Common Data Model mapi, izmantojot Azure Data Lake kontu](connect-common-data-model.md)


## <a name="relate-refined-event-data-as-an-activity-of-a-customer-profile"></a>Saistiet precizētā notikuma datus kā klienta profila darbību

Kad entītija ir pabeigta, varat konfigurēt klienta profila darbību.

Papildinformācijai skatiet [Klientu darbības](activities.md).

:::image type="content" source="media/web-event-activity.png" alt-text="Darbību lapa ar izvērstu darbību rediģēšanas rūti un aizpildītiem laukiem.":::

Konfigurējiet jauno darbību, izmantojot šādu kartējumu: 

- **Primārā atslēga:** Signal.Export.Id - unikāls ID, kas ir pieejams katram notikuma ierakstam iesaistes ieskatos. Šis rekvizīts tiek ģenerēts automātiski.

- **Laikspiedols:** Signal.Timestamp notikuma rekvizītā.

- **Notikums:** Signal.Name - notikuma nosaukums, kuru vēlaties izsekot.

- **Tīmekļa adrese:** Signal.View.Uri norāda uz notikumu izveidojušās lapas uri.

- **Detalizēta informācija:** Signal.Action.Name attēlo informāciju, kas jāsaista ar notikumu. Šajā gadījumā atlasītais rekvizīts norāda, ka notikums ir e-pasta veicināšanas pasākums.

- **Darbības tips:** šajā piemērā mēs izvēlamies esošo darbības tipu Tīmekļa žurnāls. Šī atlase ir noderīga filtrēšanas opcija, lai izpildītu prognozes modeļus vai izveidotu segmentus, pamatojoties uz šo darbības tipu.

- **Iestatīt attiecības:** šis svarīgais iestatījums ir saistīts ar esošiem klientu profiliem. **Signal.User.Id** ir identifikators, kas tiek konfigurēts SDK apkopošanai un ir saistīts ar lietotāja ID citos datu avotos, kuri ir konfigurēti auditorijas ieskatos. Šajā piemērā mēs konfigurējam attiecības starp Signal.User.Id un RetailCustomers:CustomerRetailId, kas ir primārā atslēga, kura tika noņemta datu apvienošanas procesa kartējuma solī.


Pēc darbību apstrādes varat pārskatīt klientu ierakstus un atvērt klienta karti, lai skatītu darbības no iesaistes ieskatiem laika skalā. 

> [!TIP]
> Lai atrastu klienta ID, kam ir iesaistes ieskatu darbība, dodieties uz **Entītijas** un priekšskatiet UnifiedActivity entītijas datus. ActivityTypeDisplay = Tīmekļa žurnāls ietver iesaistes ieskatu darbību, kas ir konfigurēta iepriekš minētajā piemērā. Nokopējiet klienta ID vienam no šiem ierakstiem un šim ID lapā **Klienti**.

## <a name="next-steps"></a>Nākamās darbības

Tagad varat izveidot [segmentus](segments.md), [pasākumus](measures.md) un [prognozes](predictions.md), lai izveidotu jēgpilnu savienojumu ar klientiem.


[!INCLUDE[footer-include](../includes/footer-banner.md)]