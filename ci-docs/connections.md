---
title: Savienojumu (priekšskatījums) pārskats
description: Savienojumi ar citiem pakalpojumiem no Customer Insights.
ms.date: 08/04/2022
ms.reviewer: nikeller
ms.subservice: audience-insights
ms.topic: overview
author: m-hartmann
ms.author: mhart
manager: shellyha
searchScope:
- ci-connections
- customerInsights
ms.openlocfilehash: 8580dc7d90c75f66f73efc15f8e38f5e10fbb8a7
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245520"
---
# <a name="connections-preview-overview"></a>Savienojumu (priekšskatījums) pārskats

Savienojumi ir atslēga tam, lai jūs iespējotu datu kopīgošanu ar un no Customer Insights. Katrs savienojums kopīgo datus ar konkrēto servisu. Izmantojiet savienojumus, lai [konfigurētu trešo pušu bagātināšanu un](enrichment-hub.md) konfigurētu [eksportēšanu](export-destinations.md). Vienu un to pašu savienojumu var izmantot vairākkārt. Piemēram, viens savienojums ar Dynamics 365 Marketing darbojas vairākiem eksportiem, un vienu Leadspace savienojumu var izmantot vairākiem bagātinājumiem.

## <a name="export-connections"></a>Eksporta savienojumi

Tikai administratori var konfigurēt jaunus savienojumus, bet viņi var [piešķirt piekļuvi līdzstrādniekiem](#allow-contributors-to-use-a-connection-for-exports), lai izmantotu esošos savienojumus. Administratori nosaka, kur dati var doties, līdzstrādnieki atbilstoši savām vajadzībām definē lietderīgo slodzi un biežumu.

## <a name="enrichment-connections"></a>Bagātināšanas savienojumi

Tikai administratori var konfigurēt jaunus savienojumus, taču izveidotie savienojumi vienmēr ir pieejami gan administratoriem, gan līdzstrādniekiem. Administratori pārvalda akreditācijas un sniedz piekrišanu datu pārsūtīšanai. Pēc tam savienojumus bagātināšanai var izmantot kā administratori, tā arī līdzstrādnieki.

## <a name="add-a-new-connection"></a>Jauna savienojuma pievienošana

### <a name="prerequisites"></a>Priekšnoteikumi

- [Administratora atļaujas](permissions.md)
- Citi Microsoft pakalpojumi, ja tādi ir, atrodas tajā pašā organizācijā

1. Dodieties uz **Administrators** > **Savienojumi**.

1. Atlasiet **Pievienot savienojumu** un izvēlieties savienojuma veidu, kuru vēlaties izveidot. Vai arī dodieties uz **cilni Discover** un atlasiet **Iestatīt** savienojuma elementā.

1. Laukā **Parādāmais nosaukums** piešķiriet savienojumam atpazīstamu nosaukumu. Parādāmais nosaukums un nosaukuma veids raksturo šo savienojumu. Ir ieteicams izvēlēties nosaukumu, kas paskaidro savienojuma nolūku.

1. Ievadiet nepieciešamo informāciju. Precīzi lauki ir atkarīgi no tā, ar kādu pakalpojumu veidojat savienojumu. Lai iegūtu detalizētu informāciju par konkrētu savienojuma veidu, skatiet rakstu par mērķa pakalpojumu.

1. Ja jūs [izmantojat savu Key Vault](use-azure-key-vault.md), lai glabātu slepenu informāciju, aktivizējiet **Izmantot Key Vault** un sarakstā izvēlieties slepeno informāciju.

1. Pārskatiet datu privātumu un atbilstību un atlasiet **Es piekrītu**.

1. Atlasiet **Saglabāt**, lai izveidotu savienojumu.

### <a name="data-privacy-and-compliance"></a>Datu konfidencialitāte un atbilstība

Kad iespējojat Dynamics 365 Customer Insights datu pārsūtīšanu trešajām pusēm vai citiem Microsoft produktiem, jūs atļaujat pārsūtīt datus ārpus atbilstības robežas, tostarp potenciāli sensitīvus Dynamics 365 Customer Insights datus, piemēram, Personas datus. Microsoft pārsūtīs šādus datus pēc jūsu norādījumiem, taču jūs esat atbildīgs par to, lai nodrošinātu, ka trešā puse izpilda visas jūsu iespējamās konfidencialitātes vai drošības saistības. Papildinformāciju skatiet rakstā [Microsoft Privātuma paziņojums](https://go.microsoft.com/fwlink/?linkid=396732).

Administrators Dynamics 365 Customer Insights jebkurā laikā var noņemt savienojumu, lai pārtrauktu funkcionalitātes lietošanu.

## <a name="allow-contributors-to-use-a-connection-for-exports"></a>Ļaut līdzstrādniekiem izmantot savienojumu eksportēšanai

Iestatot vai rediģējot eksporta savienojumu, izvēlieties, kuriem lietotājiem ir atļauts izmantot šo konkrēto savienojumu, lai definētu [eksportēšanu](export-destinations.md). Pēc noklusējuma savienojums ir pieejams lietotājiem ar administratora lomu. **Mainiet iestatījumu Izvēlieties, kurš var izmantot šo savienojumu**, lai ļautu lietotājiem ar līdzstrādnieka lomu izmantot šo savienojumu.

- Līdzstrādnieki nevarēs savienojumu skatīt vai rediģēt. Parādāmo vārdu un tā veidu viņi redzēs tikai tad, kad tiks izveidots eksports.
- Kopīgojot savienojumu, jūs ļaujat savienojumu izmantot līdzstrādniekiem. Līdzstrādnieki eksportēšanas iestatīšanas laikā redzēs kopīgotos savienojumus. Viņi var pārvaldīt visus eksportus, kuri izmanto konkrēto savienojumu.
- Šo iestatījumu varat mainīt, vienlaikus paturot līdzstrādnieku jau definētos eksportus.

## <a name="manage-existing-connections"></a>Esošo savienojumu pārvaldība

1. Dodieties uz **Administrators** > **Savienojumi**.

1. **Atlasiet cilni Bagātināšana** vai **Eksportēšana**, lai skatītu bagātināšanas vai eksportēšanas savienojumu sarakstu, savienojuma veidu, kad tas tika izveidots, un to, kam ir piekļuve. Savienojumu sarakstu var kārtot pēc jebkuras kolonnas.

1. Atlasiet savienojumu, lai skatītu pieejamās darbības.

   - **Rediģējiet** savienojumu.
   - [**Noņemiet**](#remove-a-connection) savienojumu.

### <a name="remove-a-connection"></a>Savienojuma noņemšana

Ja noņemamo savienojumu izmanto bagātināšanai vai eksportēšanai, vispirms atvienojiet vai noņemiet tos. Noņemšanas dialoglodziņš palīdz veikt attiecīgos bagātinājumus vai eksportu.

> [!TIP]
> Deaktivizēti bagātināšanas veidi un atdalīts eksports kļūst neaktīvs. Jūs varat tās aktivizēt no jauna, pievienojot tām citu savienojumu lapā [Bagātināšana](enrichment-hub.md) vai [Eksportēšana](export-destinations.md).

1. Dodieties uz **Administrators** > **Savienojumi**.

1. **Atlasiet cilni Bagātināšana** vai **Eksportēšana**.

1. Atlasiet savienojumu, kuru vēlaties noņemt.

1. Atlasiet **Noņemt** nolaižamajā izvēlnē. Tiek atvērts apstiprinājuma dialoglodziņš.

   1. Ja šo savienojumu izmanto bagātināšana vai eksportēšana, atlasiet pogu, lai redzētu, kas izmanto savienojumu.
      - **Eksportēšana:** izvēlieties **noņemt** eksportēšanu vai **atvienot savienojumu**. Atvienojot savienojumu, eksporta konfigurācija tiek saglabāta, taču tā netiks palaista, kamēr tai netiks pievienots cits savienojums.
      - **Bagātināšana:** izvēlieties vai nu **Dzēst,** vai **Deaktivizēt** bagātinājumus.
   1. Kolīdz savienojumam vairs nav atkarīgo elementu, atgriezieties lapā **Administrators** > **Savienojumi** un vēlreiz mēģiniet noņemt savienojumu.

1. Lai apstiprinātu dzēšanu, atlasiet **Noņemt**.

## <a name="set-up-connections-with-secrets-managed-by-your-own-key-vault"></a>Savienojumu izveide ar slepeno informāciju, ko pārvalda jūsu Key Vault

Dažiem savienojumiem ir nepieciešama slepenas informācijas lietošana, piemēram, API atslēgas vai paroles. Daži savienojumi atbalsta slepeno informāciju, kas tiek glabāta jūsu Key Vault krātuvē. Uzziniet vairāk par atbalstītajiem savienojumiem un to, kā iestatīt [savu key vault for Customer Insights](use-azure-key-vault.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
