---
title: Segmentu ieskati (priekšskatījums)
description: Iegūstiet ieskatu esošajos segmentos, lai redzētu atšķirības un kopīgās iezīmes.
ms.date: 06/10/2020
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-segment-insights
- customerInsights
ms.openlocfilehash: ccb33594a3a92e87d307f3300c77772ef8b4a82f
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 07/18/2022
ms.locfileid: "9171012"
---
# <a name="segment-insights-preview"></a>Segmentu ieskati (priekšskatījums)

Skatiet papildu informāciju un ieskatus, kas atrodas apkārt esošajiem segmentiem. Uzziniet, kas atšķir divus segmentus vai to, kas viņiem ir kopīgs.

## <a name="segment-overlap"></a>Segmentu pārklāšanās

Segmentu pārklāšanās analīze parāda, cik daudz un kādi klienti ir kopīgi diviem vai vairākiem segmentiem. Piemēram, kā biežu klientu segments pārklājas ar segmentu, kas ietver klientus, kuri ir apmierināti ar jūsu servisu vai produktu.
Varat arī analizēt pārklāšanās izmaiņas specifiskiem atribūtiem.

### <a name="run-an-overlap-analysis"></a>Pārklāšanās analīzes izpilde

1. Atveriet sadaļu **Segmenti** un atlasiet cilni **Ieskati (priekšskatījums)**.

1. Atlasiet **Jauns** un izvēlieties opciju **Pārklāšanās** rūtī **Izvēlēties ieskatu tipu**.

1. Izvēlieties interesējošos segmentus un atlasiet **Tālāk**.

1. Ja vēlaties, izvēlieties vienu vai vairākus interesējošos laukus, lai analizētu pārklāšanos attiecībā uz visām iespējamām lauka vērtībām un atlasiet **Tālāk**.

1. Norādiet pārklāšanās analīzes nosaukumu, neobligāti parādāmo nosaukumu un aprakstu.

1. Lai sāktu analīzi, atlasiet **Saglabāt**. Pārklāšanās analīze ir gatava, kad statuss tiek nomainīts no Atsvaidzināšana uz Veiksmīgi pabeigta.

### <a name="view-and-optimize-an-overlap-analysis"></a>Pārklāšanās analīzes skatīšana un optimizēšana

1. Pēc analīzes pabeigšanas atrodiet detalizētu informāciju par šo ieskatu sadaļā **Segmenti** > **Ieskati (priekšskatījums)**.

   :::image type="content" source="media/segment-overlap.png" alt-text="Detalizētā informācija par segmenta pārklājuma ieskatu.":::

1. Atlasiet ieskatu, lai skatītu analīzes rezultātus:

   - To dalībnieku skaits, kas pārklājas analīzei atlasītajiem segmentos.
   - Dalībnieku skaits, kas ir iekļauti vienā no segmentiem, bet ne pārējos segmentos.
   - Ja atlasījāt laukus, konfigurējot pārklāšanās analīzi, tie ir atrodami atbilstošajās cilnēs. Filtra nolaižamo izvēlni var izmantot, lai atlasītu jebkuru interesējošo atribūtu līmeni, un tabulā, kas atrodas apakšā, tiks parādīti atbilstošie dati.

## <a name="segment-differentiators"></a>Segmentu diferencētājposmi

Segmentu diferenciatori palīdz uzzināt, kas atšķir segmentu no pārējiem jūsu klientiem vai no cita segmenta. Atlasiet segmentu, un sistēma identificē profila atribūtus un mērus, kas atšķir atlasīto segmentu.

### <a name="run-a-differentiator-analysis"></a>Diferenciatoru analīzes veikšana

1. Atveriet sadaļu **Segmenti** un atlasiet cilni **Ieskati (priekšskatījums)**.

1. Atlasiet **Jauns** un rūtī Izvēlēties ieskatu tipu **izvēlieties** opciju **Diferencētāji**.

1. Izvēlieties analizējamo segmentu kā **Primārais segments**, un atlasiet **Tālāk**.

1. Izvēlieties **Visi klienti** vai **Sekundārais segments**, ar ko salīdzināt Jūsu primāro segmentu, un atlasiet **Tālāk**.

1. Ja vēlaties, varat izvēlēties vienu vai vairākus interesējošos laukus, lai veiktu analīzi specifiskiem atribūtiem, un atlasiet **Tālāk**.

1. Norādiet nosaukumu diferencēšanas analīzei, neobligātu parādāmo vārdu un aprakstu.

1. Lai sāktu analīzi, atlasiet **Saglabāt**. Diferencēšanas analīze ir gatava, kad statuss mainās no Atsvaidzināšanas uz Sekmīgs.

### <a name="view-and-optimize-a-differentiators-analysis"></a>Diferenciatoru analīzes skatīšana un optimizēšana

1. Pēc analīzes pabeigšanas dodieties uz **Segmentu ieskati** > **(priekšskatījums)**.

   :::image type="content" source="media/segment-differentiators.png" alt-text="Detalizētā informācija par segmenta diferenciatora ieskatu.":::

1. Atlasiet ieskatu, lai skatītu analīzes rezultātus. Diferenciatoru analīze ietver divas cilnes. Cilnē **Atribūti** ir norādīti profila atribūti, kas tiek uzskatīti par diferenciatoriem. Cilnē **Mēri** ir uzskaitīti diferenciatori. Katrā cilnē ir šāda informācija:

   - Novērtētu diferenciatoru saraksts, kas sakārtots pēc atšķirības rezultāta.
   - Katras differentiatora **Atšķirības rezultāts**. Atšķirības rezultāts atspoguļo atribūta atšķirības pakāpi, salīdzinot divus segmentus. Jo lielāks ir atšķirības rezultāts, jo vairāk atribūtu atšķiras abos segmentos. Atlasiet rezultātu, lai atvērtu rūti **Atšķirības rezultāts** ar šī atribūta vērtību sadali.

## <a name="manage-segment-insights"></a>Segmentu ieskatu pārvaldība

Dodieties uz **Segmentu** > **ieskati (priekšskatījums),** lai skatītu segmenta ieskatus un pārvaldītu tos. Atlasiet segmenta ieskatu, lai skatītu pieejamās darbības.

- **Ieskatu analīzes skatīšana**
- **Rediģējiet** ieskatu, lai mainītu tā rekvizītus
- **Atsvaidziniet** ieskatu, lai vēlreiz veiktu analīzi
- **Pārdēvējiet** ieskatu
- **Dzēst** ieskatu

[!INCLUDE [footer-include](includes/footer-banner.md)]
