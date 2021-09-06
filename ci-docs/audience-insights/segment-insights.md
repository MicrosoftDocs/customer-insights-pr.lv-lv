---
title: Segmentu ieskati esošajos segmentos
description: Iegūstiet ieskatu esošajos segmentos, lai redzētu atšķirības un kopīgās iezīmes.
ms.date: 06/10/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 977d250e5f8c52551b9f3ae9c5e805e946f2579fbe7b04f97fbac880debbac2a
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035888"
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

Pēc analīzes pabeigšanas atrodiet detalizētu informāciju par šo ieskatu sadaļā **Segmenti** > **Ieskati (priekšskatījums)**.

> [!div class="mx-imgBorder"]
> :::image type="content" source="media/segment-overlap.png" alt-text="Detalizētā informācija par segmenta pārklājuma ieskatu.":::

Atlasiet ieskatu, lai skatītu analīzes rezultātus:

- To dalībnieku skaits, kas pārklājas analīzei atlasītajiem segmentos.
- Dalībnieku skaits, kas ir iekļauti vienā no segmentiem, bet ne pārējos segmentos.
- Ja atlasījāt laukus, konfigurējot pārklāšanās analīzi, tie ir atrodami atbilstošajās cilnēs. Filtra nolaižamo izvēlni var izmantot, lai atlasītu jebkuru interesējošo atribūtu līmeni, un tabulā, kas atrodas apakšā, tiks parādīti atbilstošie dati.

## <a name="segment-differentiators"></a>Segmentu diferencētājposmi

Segmentu diferenciatori palīdz uzzināt, kas atšķir segmentu no pārējiem jūsu klientiem vai no cita segmenta. Jums tikai jāatlasa segments, un sistēma identificēs profila atribūtus un mērus, kas atšķir atlasīto segmentu.

### <a name="run-a-differentiator-analysis"></a>Diferenciatoru analīzes veikšana

1. Atveriet sadaļu **Segmenti** un atlasiet cilni **Ieskati (priekšskatījums)**.

1. Atlasiet **Jauns** un izvēlieties opciju **Pārklāšanās** rūtī **Izvēlēties ieskatu tipu**.

1. Izvēlieties analizējamo segmentu kā **Primārais segments**, un atlasiet **Tālāk**.

1. Izvēlieties **Visi klienti** vai **Sekundārais segments**, ar ko salīdzināt Jūsu primāro segmentu, un atlasiet **Tālāk**.

1. Ja vēlaties, varat izvēlēties vienu vai vairākus interesējošos laukus, lai veiktu analīzi specifiskiem atribūtiem, un atlasiet **Tālāk**.

1. Norādiet pārklāšanās analīzes nosaukumu, neobligāti parādāmo nosaukumu un aprakstu.

1. Lai sāktu analīzi, atlasiet **Saglabāt**. Pārklāšanās analīze ir gatava, kad statuss tiek nomainīts no Atsvaidzināšana uz Veiksmīgi pabeigta.

### <a name="view-and-optimize-a-differentiators-analysis"></a>Diferenciatoru analīzes skatīšana un optimizēšana

Pēc analīzes pabeigšanas atrodiet detalizētu informāciju par šo ieskatu sadaļā **Segmenti** > **Ieskati (priekšskatījums)**.

> [!div class="mx-imgBorder"]
> :::image type="content" source="media/segment-differentiators.png" alt-text="Detalizētā informācija par segmenta diferenciatora ieskatu.":::

Atlasiet ieskatu, lai skatītu analīzes rezultātus. Diferenciatoru analīze ietver divas cilnes. Cilnē **Atribūti** ir norādīti profila atribūti, kas tiek uzskatīti par diferenciatoriem. Cilnē **Mēri** ir uzskaitīti diferenciatori. Katrā cilnē ir šāda informācija:

- Novērtētu diferenciatoru saraksts, kas sakārtots pēc atšķirības rezultāta.
- Katras differentiatora **Atšķirības rezultāts**. Atšķirības rezultāts atspoguļo atribūta atšķirības pakāpi, salīdzinot divus segmentus. Jo lielāks ir atšķirības rezultāts, jo vairāk atribūtu atšķiras abos segmentos. Atlasiet rezultātu, lai atvērtu rūti **Atšķirības rezultāts** ar šī atribūta vērtību sadali.

## <a name="manage-segment-insights"></a>Segmentu ieskatu pārvaldība

Varat izmantot tālāk norādītās iespējas jūsu ieskatiem, kuras ir pieejamas komandu joslā:

- **Atpakaļ**, lai atgrieztos pie ieskatu saraksta
- **Atsvaidzināt**, lai vēlreiz veiktu analīzi
- **Dzēst**, lai noņemtu šo ieskatu


[!INCLUDE[footer-include](../includes/footer-banner.md)]