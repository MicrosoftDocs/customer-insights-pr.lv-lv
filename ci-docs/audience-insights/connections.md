---
title: Savienojumi ar citiem pakalpojumiem no Customer Insights.
description: Kopīgojiet datus ar citiem pakalpojumiem.
ms.date: 04/09/2021
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 37c5d152a4cc91a90df8db387d25923ed150e238bc6b54c54f7bba59fbd48c82
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 08/10/2021
ms.locfileid: "7033227"
---
# <a name="connections-preview-overview"></a>Savienojumu (priekšskatījums) pārskats

Savienojumi ir atslēga tam, lai jūs iespējotu datu kopīgošanu ar un no Customer Insights. Katrs savienojums kopīgo datus ar konkrēto servisu. Savienojumi ir pamatā [trešās puses bagātinājumu konfigurēšanai](enrichment-hub.md) un [eksportēšanas konfigurēšanai](export-destinations.md). Vienu un to pašu savienojumu var izmantot vairākkārt. Piemēram, viens savienojums ar Dynamics 365 Marketing darbojas vairākiem eksportiem, un vienu Leadspace savienojumu var izmantot vairākiem bagātinājumiem.

Lai izveidotu un skatītu savienojumus, dodieties uz **Administrators** > **Savienojumi**.

Cilnē **Savienojumi** ir redzami visi aktīvie savienojumi. Sarakstā redzama katra savienojuma rinda. 

Cilnē **Atklāt** aplūkojiet īsu pārskatu un aprakstu un uzziniet, ko varat darīt ar katru paplašināšanas opciju.

### <a name="exports"></a>Eksports

Tikai administratori var konfigurēt jaunos savienojumus, taču viņi var piešķirt piekļuvi līdzstrādniekiem, lai viņi lietotu esošos savienojumus. Administratori nosaka, kur dati var doties, līdzstrādnieki atbilstoši savām vajadzībām definē lietderīgo slodzi un biežumu. Papildinformāciju skatiet rakstā [Atļaut līdzstrādniekiem izmantot savienojumu eksportam](#allow-contributors-to-use-a-connection-for-exports).

### <a name="enrichments"></a>Bagātinājumi

Jaunus savienojumu drīkst konfigurēt tikai administratori, taču izveidotie savienojumi vienmēr ir pieejami gan administratoriem, gan līdzstrādniekiem. Administratori pārvalda akreditācijas un sniedz piekrišanu datu pārsūtīšanai. Pēc tam savienojumus bagātināšanai var izmantot kā administratori, tā arī līdzstrādnieki.

## <a name="add-a-new-connection"></a>Jauna savienojuma pievienošana

Lai pievienotu savienojumu, ir jābūt [administratora atļaujām](permissions.md). Ja savienojaties ar citiem Microsoft pakalpojumiem, mēs pieņemam, ka abi pakalpojumi atrodas vienā organizācijā.

1. Dodieties uz **Administrators** > **Savienojumi (priekšskatījums)**.

1. Doties uz cilni **Savienojumi**.

1. Lai izveidotu jaunu savienojumu, atlasiet **Pievienot savienojumu**. Nolaižamajā izvēlnē izvēlieties, kāda veida savienojumu vēlaties izveidot.

1. Rūtī **Iestatīt savienojumu** norādiet nepieciešamo informāciju. 
   1. **Parādāmais nosaukums** un nosaukuma veids raksturo savienojumu. Ir ieteicams izvēlēties nosaukumu, kas paskaidro savienojuma nolūku.
   1. Precīzie lauki ir atkarīgi no tā, kādam pakalpojuma pieslēdzaties. Varat sīkāk uzzināt par konkrēto savienojuma veidu rakstā par mērķa pakalpojumu.

1. Lai izveidotu savienojumu, atlasiet **Saglabāt**.

Cilnes elementā **Iestatīt** var atlasīt arī **Atklāt**.

### <a name="allow-contributors-to-use-a-connection-for-exports"></a>Ļaut līdzstrādniekiem izmantot savienojumu eksportēšanai

Iestatot vai rediģējot eksportēšanas savienojumu, jūs izvēlaties, kuriem lietotājiem ir atļauts izmantot konkrēto savienojumu, lai definētu [eksportēšanu](export-destinations.md). Savienojums pēc noklusējuma ir pieejams lietotājiem ar administratora lomu. Šo iestatījumu varat mainīt sadaļām **Izvēlieties, kas var lietot šo savienojumu** un ļaut šo savienojumu izmantot lietotājiem ar līdzstrādnieka lomu.

- Līdzstrādnieki nevarēs savienojumu skatīt vai rediģēt. Viņi eksporta izveides laikā redzēs vienīgi parādāmo nosaukumu un veidu.
- Kopīgojot savienojumu, jūs ļaujat savienojumu izmantot līdzstrādniekiem. Līdzstrādnieki eksportēšanas iestatīšanas laikā redzēs kopīgotos savienojumus. Viņi var pārvaldīt visus eksportus, kuri izmanto konkrēto savienojumu.
- Šo iestatījumu varat mainīt, vienlaikus paturot līdzstrādnieku jau definētos eksportus.

## <a name="edit-a-connection"></a>Savienojuma rediģēšana

1. Dodieties uz **Administrators** > **Savienojumi (priekšskatījums)**.

1. Doties uz cilni **Savienojumi**.

1. Atlasiet vertikālo daudzpunkti savienojumam, kuru vēlaties rediģēt.

1. Atlasiet **Rediģēt**.

1. Mainiet vērtības, kuras vēlaties atjaunināt, un atlasiet **Saglabāt**.

## <a name="remove-a-connection"></a>Savienojuma noņemšana

Ja savienojumu, kuru noņemat, izmanto bagātināšanā vai eksportēšanā, tās vispirms ir jāatvieno vai jāņoņem. Noņemšanas dialoglodziņš jūs aizvirzīs uz atbilstīgo bagātināšanu vai eksportēšanu. 

Atvienota bagātināšana un eksportēšana kļūst neaktīva. Jūs varat tās aktivizēt no jauna, pievienojot tām citu savienojumu lapā [Bagātināšana](enrichment-hub.md) vai [Eksportēšana](export-destinations.md).

1. Dodieties uz **Administrators** > **Savienojumi (priekšskatījums)**.

1. Doties uz cilni **Savienojumi**.

1. Atlasiet vertikālo daudzpunkti savienojumam, kuru vēlaties noņemt.

1. Atlasiet **Noņemt** nolaižamajā izvēlnē. Tiek atvērts apstiprinājuma dialoglodziņš.

   1. Ja šo savienojumu izmanto bagātināšana vai eksportēšana, atlasiet pogu, lai redzētu, kas izmanto savienojumu.
      - **Eksportēšana:** Varat izvēlēties vai nu noņemt vai atvienot eksportēšanu, lai varētu noņemt savienojumu. Lai atvienotu eksportēšanu, administratori var izmantot darbību **Atvienot**. Šī darbība ir pieejama atsevišķām un vairākām eksportēšanām. Veicot atvienošanu, tiek saglabāta eksportēšanas konfigurācija, taču tā netiks palaista, iekams nebūs pievienots cits savienojums.
      - **Bagātināšana:** Varat izvēlēties vai nu noņemt vai deaktivizēt bagātināšanu, lai varētu noņemt savienojumu. 
   1. Kolīdz savienojumam vairs nav atkarīgo elementu, atgriezieties lapā **Administrators** > **Savienojumi** un vēlreiz mēģiniet noņemt savienojumu.

1. Lai apstiprinātu dzēšanu, atlasiet **Noņemt**.

