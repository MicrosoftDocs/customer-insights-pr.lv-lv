---
title: Datu bagātināšanas (priekšskatījuma) pārskats
description: Izmantojiet Microsoft un citu trešo pušu pakalpojumu iespējas, lai bagātinātu klientu datus.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-enrichments
- ci-enrichment-details
- ci-enrichment-wizard
- customerInsights
ms.openlocfilehash: 6b6daab480db5e37830ff58b71dcdd3bbdbe46da
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 06/29/2022
ms.locfileid: "9053889"
---
# <a name="data-enrichment-preview-overview"></a>Datu bagātināšanas (priekšskatījuma) pārskats

Izmantojiet avotu datus, piemēram, no Microsoft un citiem partneriem, lai bagātinātu klientu datus. Trešo pušu bagātinātos datus konfigurē, izmantojot [savienojumus](connections.md), kurus administrators iestata ar akreditāciju un kuru pārnesei tiek sniegta piekrišana. Šos savienojumus bagātinājumu konfigurēšanai var izmantot administratori un līdzstrādnieki.  

## <a name="multiple-enrichments-of-the-same-type"></a>Vairāki viena veida bagātinātie dati

Bagātināmo entitīju norāda bagātināšanas konfigurēšanas laikā, kas ļauj bagātināt vienīgi jūsu profilu apakškopu. Piemēram, bagātināt datus tikai noteiktam segmentam. Jūs varat konfigurēt vairākus viena veida bagātinātos datus un atkārtoti izmantot to pašu savienojumu. Daži bagātinātie dati tiks ierobežoti līdz atļautajam bagātināmo datu izveides skaitam. Ierobežojumi un pašreizējais lietojums ir redzams katrā elementā **lapas Bagātināšana** cilnē **Discover**.

## <a name="enrich-data-sources-before-unification"></a>Pirms apvienošanās bagātiniet datu avotus

Varat bagātināt klientu datus pirms datu apvienošanas, lai palīdzētu uzlabot datu atbilstības kvalitāti. Papildinformāciju skatiet sadaļā [datu avots bagātināšana](data-sources-enrichment.md).

## <a name="create-an-enrichment"></a>Bagātināšanas izveide

Jums ir jābūt līdzstrādnieka vai administratora [atļaujām](permissions.md), lai izveidotu vai rediģētu bagātinājumus.

Dodieties uz **Dati** > **Bagātināšana**. Cilnē **Discover** tiek rādītas visas atbalstītās bagātināšanas opcijas.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Bagātināšanas centra lapa.":::

# <a name="individual-consumers-b-to-c"></a>[Atsevišķi patērētāji (B2C)](#tab/b2c)

- [AbiliTec identitāte](enrichment-liveramp.md), ko nodrošina LiveRamp AbiliTec
- Microsoft nodrošinātie [Zīmoli](enrichment-microsoft.md)
- [Demogrāfiskie dati](enrichment-experian.md), ko nodrošina Experian
- [Paplašinātās adreses](enrichment-enhanced-addresses.md), ko nodrošina Microsoft
- Microsoft nodrošinātās [Intereses](enrichment-microsoft.md)
- [Atrašanās vietas dati](enrichment-azure-maps.md), ko Microsoft Azure nodrošina kartes
- [Atrašanās vietas dati](enrichment-here.md) HERE Technologies nodrošinātie atrašanās vietas dati
- [SFTP pielāgotie dati](enrichment-SFTP-custom-import.md), izmantojot drošu failu pārsūtīšanas protokolu (SFTP)

# <a name="business-accounts-b-to-b"></a>[Uzņēmumu konti (B2B)](#tab/b2b)

- [Microsoft nodrošinātie konta iesaistes dati](enrichment-office.md)
- [Uzņēmuma datus](enrichment-dnb.md) sniedza Dun & Bradstreet
- Leadspace nodrošinātie [uzņēmuma dati](enrichment-leadspace.md)
- [Paplašinātās adreses](enrichment-enhanced-addresses.md), ko nodrošina Microsoft
- [Uzlaboti uzņēmuma dati](enrichment-enhanced-company-data.md), ko nodrošina Microsoft
- [Atrašanās vietas dati](enrichment-azure-maps.md), ko Microsoft Azure nodrošina kartes
- [Atrašanās vietas dati](enrichment-here.md) HERE Technologies nodrošinātie atrašanās vietas dati
- [SFTP pielāgotie dati](enrichment-SFTP-custom-import.md), izmantojot drošu failu pārsūtīšanas protokolu (SFTP)

---

## <a name="manage-existing-enrichments"></a>Esošo papildinājumu pārvaldība

Dodieties uz **Dati** > **Bagātināšana**. **Cilnē Mani bagātinājumi** skatiet konfigurētos bagātinājumus, to statusu, bagātināto klientu skaitu un pēdējo reizi, kad dati tika atsvaidzināti. Bagātinājumu sarakstu var kārtot pēc jebkuras kolonnas vai izmantot meklēšanas lodziņu, lai atrastu bagātinājumu, kuru vēlaties pārvaldīt.

Atlasiet bagātināšanu, lai skatītu pieejamās darbības.

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Opcijas bagātinājumu pārvaldībai papildinājumu sarakstā.":::

- **Skatiet** detalizēto informāciju par bagātināšanu ar bagātināto klientu profilu skaitu.
- **Rediģējiet** bagātināšanas konfigurāciju.
- [**Palaidiet**](#run-or-refresh-enrichments) bagātināšanu, lai atjauninātu klientu profilus ar jaunākajiem datiem. Palaidiet vairākus bagātinājumus vienlaikus, atlasot tos sarakstā.
- **Aktivizējiet** vai **deaktivizējiet** bagātināšanu. Neaktīvie bagātinājumi netiks atsvaidzināti plānotās [atsvaidzināšanas](system.md#schedule-tab) laikā.
- **Dzēst** bagātināšanu.

Varat arī izveidot [segmentus vai](segments.md) mērus [no](measures.md) bagātināšanas.

## <a name="run-or-refresh-enrichments"></a>Palaist vai atsvaidzināt bagātinājumus

Pēc palaišanas bagātināšanu var atsvaidzināt pēc automātiska grafika vai atsvaidzināt manuāli pēc pieprasījuma.

1. Lai manuāli atsvaidzinātu vienu vai vairākus bagātinājumus, atlasiet tos un izvēlieties **Palaist**. Lai [ieplānotu automātisku atsvaidzināšanu](system.md#schedule-tab), dodieties uz **administrēšanas** > **sistēmas** > **grafiku**. Apstrādes laiks ir atkarīgs no klientu datu lieluma.

1. Pēc izvēles [skatiet bagātināšanas procesa](#see-the-progress-of-the-enrichment-process) gaitu.

1. Kad bagātināšanas process ir pabeigts, dodieties uz **My enrichments**, lai pārskatītu nesen bagātināto klientu profilu datus, pēdējā atjauninājuma laiku un bagātināto profilu skaitu.

1. Izvēlieties bagātinājumu, lai redzētu [bagātināšanas rezultātus](#view-enrichment-results).

### <a name="see-the-progress-of-the-enrichment-process"></a>Bagātinātā procesa norises gaita

Atsvaidzinot vai pēc atsvaidzināšanas pabeigšanas, varat atrast detalizētu informāciju par bagātināšanas apstrādi, tostarp tā statusu un iespējamām problēmām. Izpratne par to, kuri procesi ir saistīti ar bagātinātā procesa atsvaidzināšanu un to, cik ilgs laiks bija nepieciešams šo procesu palaišanai. Bagātināšanas statuss tiek atbalstīts līdz ar Experian, Leadspace, HERE Technologies, SFTP importēšanu un Azure Maps.

1. Dodieties uz **Dati** > **Bagātināšana**.
1. **Cilnē Mani bagātinātāji** atlasiet bagātināšanas statusu, lai atvērtu sānu rūti.
1. Detalizētas informācijas rūtī **Norise** izvērsiet sadaļu **Bagātinātjumi**.
1. Sadaļā Bagātināšana, kuras norisi vēlaties redzēt, atlasiet **Skatīt informāciju**.
1. **Uzdevumu detalizētās informācijas** rūtī atlasiet **Rādīt detalizētu informāciju**, lai skatītu procesus, kas saistīti ar bagātināšanas atjaunināšanu un to statusu.

## <a name="view-enrichment-results"></a>Bagātināšanas rezultātu skatīšana

Pēc pabeigtas bagātināšanas gaitas pārskatiet bagātināšanas rezultātus.

1. Dodieties uz **Dati** > **Bagātināšana**.
1. **Cilnē Mans bagātinājums** atlasiet bagātinājumu, kuru vēlaties skatīt.

Visi bagātinātāji parāda pamatinformāciju, piemēram, bagātināto profilu skaitu un bagātināto profilu skaitu laika gaitā. Elements **Bagātināto klientu priekšskatījums** parāda ģenerētās bagātināšanas entītijas paraugu. Lai skatītu detalizētu skatu, atlasiet **Skatīt vairāk** un atlasiet **cilni Dati**.

:::image type="content" source="media/enrichments-results.png" alt-text="Bagātināšanas rezultātu lapa.":::

Ja iespējams, **ar lauku** bagātināto klientu skaits nodrošina detalizētu informāciju par katra bagātinātā lauka pārklājumu.

Dažos bagātinājumos ir arī informācija, kas attiecas uz bagātināšanas veidu. Papildinformāciju skatiet saistītajā dokumentācijā.

[!INCLUDE [footer-include](includes/footer-banner.md)]
