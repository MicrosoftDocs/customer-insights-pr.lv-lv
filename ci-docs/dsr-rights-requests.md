---
title: Datu subjektu tiesību (DSR) pieprasījumi saskaņā ar VDAR | Microsoft Docs
description: Atbildiet uz datu subjektu pieprasījumiem attiecībā uz Dynamics 365 Customer Insights.
ms.date: 08/31/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 49251fb46957c4d7ec205b93c9547a3cd380eb11
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387120"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Datu subjektu tiesību (DSR) pieprasījumi saskaņā ar VDAR

Eiropas Savienības Vispārīgā datu aizsardzības regula (VDAR) ir spēkā kopš 2018. gada 25. maija. Tas sniedz personām būtiskas tiesības attiecībā uz to datiem. VDAR tika pieņemta ar mērķi aizsargāt un ļaut izmantot personu tiesības uz konfidencialitāti. Uzziniet vairāk par Microsoft apņemšanos nodrošināt drošību un atbilstību [Microsoft drošības kontroles centrā](https://www.microsoft.com/trust-center).

Mēs gribam palīdzēt mūsu klientiem varētu izpildīt savas VDAR prasības. Tas ietver tiesības dzēst vai eksportēt datus, kas ietver personisku informāciju, piemēram, lietotāju ID, tālruņa numurus un e-pasta adreses. Administratori var ieviest lietotāju pieprasījumus, lai dzēstu vai eksportētu personiskos datus.

## <a name="responding-to-gdpr-data-subject-delete-requests-for-customer-insights"></a>Atbildēšana uz VDAR datu subjektu dzēšanas pieprasījumiem pēc Customer Insights

“Tiesības dzēst”, veicot personas datu noņemšanu no organizācijas klientu datiem, ir galvenā aizsardzība saskaņā ar Vispārīgo datu aizsardzības regulu (VDAR). Personas datu dzēšana ietver visu personas datu un sistēmas radītu ierakstu, izņemot audita ierakstu informācijas, dzēšanu.

### <a name="manage-data-subject-delete-requests"></a>Datu subjekta dzēšanas pieprasījumu pārvaldība

Customer Insights piedāvā šādas produktā esošās iespējas, lai dzēstu konkrēta klienta vai lietotāja personas datus:

- **Klienta datu dzēšanas pieprasījumu pārvaldīšana**: klientu dati programmā Customer Insights tiek pieņemti no sākotnējiem datu avotiem ārpus programmas Customer Insights. Vispirms veiciet VDAR dzēšanas pieprasījumus sākotnējā datu avots.
- **Pārvaldiet dzēšanas pieprasījumus Customer Insights lietotāju datiem** : Dati lietotājiem tiek izveidoti, izmantojot Customer Insights. Veiciet visus VDAR dzēšanas pieprasījumus programmā Customer Insights.

#### <a name="manage-requests-to-delete-customer-data"></a>Klienta datu dzēšanas pieprasījumu pārvaldīšana

Kā Customer Insights administrators noņemiet Customer Insights klientu datus, kas tika izdzēsti datu avots. Pārbaudiet, vai VDAR dzēšanas pieprasījumi tika izpildīti sākotnējā datu avots.

1. Pierakstieties programmā Dynamics 365 Customer Insights.

1. Dodieties uz **Dati** > **Datu avoti**.

1. Katram sarakstā iekļautajam datu avotam, kurā ir izdzēsti klienta dati:
   1. Atlasiet datu avots un pēc tam atlasiet **Atsvaidzināt**.
   1. Skatiet datu avota statusu sadaļā **Statuss**. Atzīme nozīmē, ka atsvaidzināšana bija veiksmīga. Brīdinājuma trijstūris nozīmē, ka radās problēma. Ja tiek parādīts brīdinājuma trijstūris, sazinieties ar D365CI@microsoft.com.

   :::image type="content" source="media/gdpr-data-sources.png" alt-text="Klienta datu VDAR dzēšanas pieprasījumu apstrāde.":::

1. Pēc veiksmīgas datu avotu atsvaidzināšanas palaidiet arī pakārtotos atsvaidzinājumus. Jo īpaši, ja jums nav ieplānota periodiska pilnīga Customer Insights atsvaidzināšana.

   > [!IMPORTANT]
   > Statiskie segmenti netiek iekļauti pilnā atsvaidzināšanā vai lejupstraumes atsvaidzināšanā pēc dzēšanas pieprasījuma. Lai nodrošinātu, ka klientu dati tiek noņemti arī no statiskiem segmentiem, atkārtoti izveidojiet statiskos segmentus, izmantojot atsvaidzinātus avota datus.

#### <a name="manage-delete-requests-for-user-data"></a>Lietotāju datu dzēšanas pieprasījumu pārvaldīšana

Kā Customer Insights administrators dzēsiet Customer Insights lietotāja datus.

1. Pierakstieties programmā Dynamics 365 Customer Insights.

1. Dodieties uz **administratoru** > **drošības** > un atlasiet **cilni Lietotāji**.

1. Atzīmējiet to lietotāju izvēles rūtiņu, kurus vēlaties dzēst.

1. Atlasiet **Noņemt**.

1. Apstipriniet dzēšanu.

## <a name="responding-to-gdpr-data-subject-export-requests"></a>Reaģēšana uz VDAR datu subjekta eksportēšanas pieprasījumiem

Datu pārvietojamības tiesības ļauj datu subjektiem pieprasīt savu personas datu kopiju elektroniskā formātā ("strukturēts, plaši lietots, mašīnlasāms un savstarpēji izmantojams formāts), kurus var pārsūtīt citam datu pārzinim.

### <a name="manage-export-and-view-requests"></a>Eksportēšanas pārvaldīšana un pieprasījumu skatīšana

Pārvaldiet pieprasījumus eksportēt klientu vai lietotāju datus.

#### <a name="export-customer-data-tenant-admin"></a>Klienta datu eksportētājs (nomnieka administrators)

Kā nomnieka administrators eksportējiet klientu datus.

1. Nosūtiet e-pasta ziņojumu uz e-pasta adresi D365CI@microsoft.com, norādot klienta e-pasta adresi pieprasījumā. Customer Insights komanda nosūtīs e-pasta ziņojumu uz reģistrēto nomnieka administratora e-pasta adresi, lūdzot apstiprinājumu datu eksportēšanai.
2. Atzīstiet apstiprinājumu eksportēt pieprasītā klienta datus.
3. Saņemiet eksportētos datus, izmantojot nomnieka administratora e-pasta adresi.

#### <a name="export-user-data-tenant-admin"></a>Klienta datu eksportēšana (nomnieka administrators)

Kā nomnieka administrators eksportējiet lietotāju datus.

1. Nosūtiet e-pasta ziņojumu uz e-pasta adresi D365CI@microsoft.com, norādot lietotāja e-pasta adresi pieprasījumā. Customer Insights komanda nosūta e-pasta ziņojumu uz reģistrētā nomnieka administratora e-pasta adresi, lūdzot apstiprinājumu datu eksportēšanai.
1. Atzīstiet apstiprinājumu eksportēt pieprasītā lietotāja datus.
1. Saņemiet eksportētos datus, izmantojot nomnieka administratora e-pasta adresi.

## <a name="data-deletion-handling-in-dynamics-365-customer-insights"></a>Datu dzēšanas apstrāde Dynamics 365 Customer Insights

Dati tiek dzēsti (datu nodalījumi un datu momentuzņēmumi), ja datu nodalījumi un datu momentuzņēmumi ir neaktīvi ilgāk par 30 dienām, kas nozīmē, ka tie ir aizstāti ar jaunu datu nodalījumu un momentuzņēmumu, atsvaidzinot datu avotus.

Ne visi dati un momentuzņēmumi tiek izdzēsti. Jaunākais datu nodalījums un datu momentuzņēmums ir aktīvs, jo tie tiek izmantoti programmā Customer Insights. Jaunākajiem datiem nav svarīgi, vai datu avoti nav atsvaidzināti pēdējo 30 dienu laikā.

[!INCLUDE [footer-include](includes/footer-banner.md)]
