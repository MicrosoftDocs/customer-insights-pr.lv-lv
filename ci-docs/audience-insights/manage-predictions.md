---
title: Koplietojamie uzdevumi prognožu scenārijiem
description: Uzziniet, kā pārvaldīt, novērst problēmas un precizēt prognozes.
ms.date: 11/01/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: 8c5d8b0395452c8da1631f09cffeddfc811e6d29
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 02/16/2022
ms.locfileid: "8230801"
---
# <a name="manage-predictions"></a>Pārvaldīt prognozes

Šajā rakstā ir aplūkoti daži uzdevumi, kas prognoze, kas tiek koplietoti.

## <a name="troubleshoot-a-failed-prediction"></a>Neizdevušās prognozes problēmas novēršana

1. Atveriet  **Informācija** > **Prognozes** un atlasiet cilni **Manas prognozes**.

1. Atlasiet vertikālās elipses, kas atrodas blakus prognozei, kurai vēlaties skatīt kļūdu žurnālus.

1. Atlasiet **Žurnāli**.

1. Pārskatīt visas kļūdas. Pastāv vairāki kļūdu tipi, kas var rasties, un tie apraksta to, kas izraisīja kļūdu. Piemēram, kļūda, kurā nav pietiekami daudz datu, lai precīzi prognozētu, parasti tiek novērsta, ielādējot papildu datus Customer Insights.

## <a name="input-data-usability-report"></a>Ievades datu lietojamības atskaite

Ievades datu lietojamības atskaite sniedz konsolidētu pārskatu par kļūdām un brīdinājumiem, ko var ģenerēt jūsu pirmās izvēles prognozes. Tajā sniegti arī ieteikumi, kā uzlabot modeļa veiktspēju.

Pārskats ir pieejams pēc tam, kad modelis ir pabeidzis apmācības procesu. Tas ir izveidots katram modelim atsevišķi, neatkarīgi no tā, vai tas ir veiksmīgi pabeigts.

### <a name="view-the-input-data-usability-report"></a>Skatīt ievades datu lietojamības atskaiti

Kad pirmās izvēles modelis ir pabeidzis apmācības darbību, skatiet atskaiti:
- Atlasiet daudzpunktes blakus modeļa nosaukumam un izvēlieties **Ievades datu lietojamības atskaite**.
- Atlasiet modeļa statusu, atlasiet sānu rūtī **Skatīt ievades datu lietojamības atskaiti**.
- Sarakstā atlasot vienu no modeļiem un komandjoslā atlasot **Ievades datu lietojamības atskaite**.
- Sarakstā atlasot vienu no modeļiem un komandjoslā atlasot **Ievades datu lietojamības atskaite**.

### <a name="information-in-the-input-data-usability-report"></a>Detalizēta informācija ievades datu lietojamības atskaitē

Šajās atskaites kolonnās ir noderīga informācija, lai uzlabotu modeļa datus.

:::image type="content" source="media/input-data-usability-report.png" alt-text="Ievades datu lietojamības atskaites piemērs, kurā redzama tabula ar kļūdām, brīdinājumiem un ieteikumiem.":::

- **Nosaukums:** kļūdas, brīdinājuma vai ieteikuma aprakstošais nosaukums.
- **Solis:** Modeļa fāze, vilciens vai rezultāts, informācija attiecas.
- **Stāvoklis:** informācijas nopietnība (kļūda, brīdinājums, ieteikums).
- **Kolonnas nosaukums:** kolonna entītijā, kas ir jāgroza, lai uzlabotu modeļa veiktspēju.
- **Entītijas nosaukums:** tās entītijas nosaukums, kura jāgroza, lai uzlabotu modeļa veiktspēju.
- **Detalizēta informācija:** detalizēta informācija par kļūdu, brīdinājumu vai ieteikumu.

## <a name="refresh-a-prediction"></a>Atsvaidzināt prognozi

Prognozes tiks automātiski atsvaidzinātas ar vienu un to pašu [grafiku, ko jūsu dati atsvaidzina](system.md#schedule-tab) kā konfigurēts iestatījumos. Tos var atsvaidzināt arī manuāli.

1. Atveriet  **Informācija** > **Prognozes** un atlasiet cilni **Manas prognozes**.

1. Atlasiet vertikālās elipses, kas atrodas blakus prognozei, kuru vēlaties atsvaidzināt.

1. Atlasiet **Atsvaidzināt**.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="delete-a-prediction"></a>Dzēst prognozi

Dzēšot prognozi, tiek noņemta arī tās izvades entītija.

1. Atveriet  **Informācija** > **Prognozes** un atlasiet cilni **Manas prognozes**.

1. Atlasiet vertikālās elipses, kas atrodas blakus prognozei, kuru vēlaties dzēst.

1. Atlasiet **Dzēst**.
