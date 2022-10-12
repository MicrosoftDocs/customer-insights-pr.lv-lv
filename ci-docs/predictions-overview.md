---
title: Prognožu pārskats
description: Prognoze scenārijiem un iespējām, uz kurām attiecas Dynamics 365 Customer Insights pieteikums.
ms.date: 09/29/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: overview
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: f8c61d7530126890d26ce482a27a0f97a39e836c
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610199"
---
# <a name="predictions-overview"></a>Prognožu pārskats

Dynamics 365 Customer Insights ir pieejamas dažādas iespējas, kas izmanto AI un algoritmisko mācīšanos, lai prognozētu datus.

## <a name="out-of-box-models"></a>Iekļautie modeļi

Visvienkāršākais veids, kā sākt ar datu prognozēšanu, ir iepriekš definēti modeļi, ko bieži dēvē par pirmās palaišanas modeļiem. Tiem ir nepieciešami tikai noteikti dati un struktūra, lai ātri ģenerētu ieskatus. Ir pieejami šādi modeļi:

# <a name="individual-consumers-b-to-c"></a>[Atsevišķi patērētāji (B2C)](#tab/b2c)

- [Klienta mūža vērtība](predict-customer-lifetime-value.md): prognozē iespējamos klienta ieņēmumus visā mijiedarbībā ar uzņēmumu.
- [Produkta ieteikums](predict-product-recommendation.md): iesaka prognozēšanas produktu ieteikumu kopas, pamatojoties uz pirkumu uzvedību un klientiem ar līdzīgiem pirkšanas modeļiem.
- [Abonementu zudums](predict-subscription-churn.md): Prognozē, vai pastāv risks, ka klients var pārtraukt izmantot jūsu uzņēmuma abonējamos produktus vai pakalpojumus.
- [Darījumu veikšana](predict-transactional-churn.md): paredz, vai atsevišķs klients vairs neiegādāsies jūsu produktus vai pakalpojumus noteiktā laika posmā.
- [Noskaņojuma analīze](sentiment-analysis.md): analizē klientu atsauksmju noskaņojumu un identificē bieži pieminētos biznesa aspektus.

# <a name="business-accounts-b-to-b"></a>[Uzņēmumu konti (B2B)](#tab/b2b)

- [Transakciju fragments](predict-transactional-churn.md): paredz, vai klienta konts vairs neiegādāsies jūsu produktus vai pakalpojumus noteiktā laika posmā.

---

> [!TIP]
> Mēs iesakām regulāri atsvaidzināt gatavus modeļus ar atjauninātiem datiem, lai nodrošinātu, ka tie precīzi informē jūsu uzņēmuma lietošanas gadījumu. Dati tiek atsvaidzināti ad-hoc, kad sistēma uzņem jaunus vai atjauninātus datu avotus. Tomēr šajā gadījumā modeļi tikai pārfrāzēsies un turpinās izmantot esošos apmācības datus.
>
> Konfigurējiet atjaunināšanas **grafiku**, iestatot modeļa pārkvalificēšanās grafiku konfigurācijas laikā. Modelis pārkvalificēsies un pārzīmēs šo grafiku, kuru jūs varat mainīt jebkurā laikā.

## <a name="azure-machine-learning-integration"></a>Azure algoritmiskās mācīšanās integrēšana

Ja organizācija jau izmanto algoritmiskās mācīšanās scenārijus, kuru pamatā algoritmiskā mācīšanās Azure eksperimenti, pielāgoto modeļu līdzeklis programmā Customer Insights palīdz savienot punktus. Izveidojiet darbplūsmas, kas palīdz izvēlēties datus, no kuriem vēlaties ģenerēt ieskatus, un kartējiet rezultātus uz vienotajiem klientu profiliem. Papildinformācijai skatiet [Pielāgoti algoritmiskās mācīšanās modeļi](custom-models.md).

## <a name="manage-existing-predictions"></a>Esošo prognožu pārvaldība

Dodieties uz **lapu Izlūkošanas** > **prognozes**. **Cilnē Manas prognozes skatiet izveidotās** prognozes, to prognoze tipu, izvades entītijas nosaukumu, statusu, pēdējo reizi, kad prognoze tika rediģēts, un pēdējo reizi, kad dati tika atsvaidzināti. Prognožu sarakstu var kārtot pēc jebkuras kolonnas.

Atlasiet prognoze, lai skatītu pieejamās darbības.

:::image type="content" source="media/predictions.png" alt-text="Manu prognožu lapa.":::

- **Rediģējiet** prognoze, lai mainītu tās rekvizītus.
- [**Atsvaidziniet**](#refresh-a-prediction) prognoze, lai iekļautu jaunākos datus.
- **Skatiet** prognoze detalizētu informāciju.
- [**Ievades datu lietojamības atskaite**](#view-the-input-data-usability-report), lai skatītu kļūdas, brīdinājumus un ieteikumus.
- **Dzēst** prognoze.

### <a name="refresh-a-prediction"></a>Atsvaidzināt prognozi

Prognozes var atsvaidzināt pēc automātiska grafika vai atsvaidzināt manuāli pēc pieprasījuma. Lai manuāli atsvaidzinātu visus ieteikumus, atlasiet **Atsvaidzināt visus**. Lai manuāli atsvaidzinātu prognoze, atlasiet to un atlasiet **Atsvaidzināt**. Lai [ieplānotu automātisku atsvaidzināšanu](schedule-refresh.md), dodieties uz **administrēšanas** > **sistēmas** > **grafiku**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

### <a name="view-the-input-data-usability-report"></a>Skatīt ievades datu lietojamības atskaiti

Ievades datu lietojamības atskaite sniedz konsolidētu pārskatu par kļūdām un brīdinājumiem, ko var ģenerēt jūsu pirmās izvēles prognozes. Tas arī sniedz ieteikumus par to, kā uzlabot modeļa veiktspēju.

Pārskats ir pieejams pēc tam, kad modelis ir pabeidzis apmācības procesu. Tas ir izveidots katram modelim atsevišķi, neatkarīgi no tā, vai tas ir veiksmīgi pabeidzis apmācību vai nē.

**Cilnē Manas prognozes** atlasiet prognoze un izvēlieties **Ievades datu lietojamības atskaite**. Vai arī skatā prognoze detalizēta informācija atlasiet **Ievades datu lietojamības pārskats**.

:::image type="content" source="media/input-data-usability-report.png" alt-text="Ievades datu lietojamības atskaites piemērs, kurā redzama tabula ar kļūdām, brīdinājumiem un ieteikumiem.":::

Ziņojumā ir iekļauts:

- **Nosaukums:** kļūdas, brīdinājuma vai ieteikuma aprakstošais nosaukums.
- **Solis:** Modeļa fāze, vilciens vai rezultāts, informācija attiecas uz.
- **Stāvoklis:** informācijas nopietnība (kļūda, brīdinājums, ieteikums).
- **Kolonnas nosaukums:** kolonna entītijā, kas ir jāmodificē, lai uzlabotu modeļa veiktspēju.
- **Entītijas nosaukums:** tās entītijas nosaukums, kas jāmodificē, lai uzlabotu modeļa veiktspēju.
- **Detalizēta informācija:** detalizēta informācija par kļūdu, brīdinājumu vai ieteikumu.

[!INCLUDE [footer-include](includes/footer-banner.md)]
