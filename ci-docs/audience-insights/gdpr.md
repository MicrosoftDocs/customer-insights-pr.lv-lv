---
title: Datu subjektu tiesību (DSR) pieprasījumi saskaņā ar VDAR | Microsoft Docs
description: Atbilde uz datu subjektu prasībām saistībā ar Dynamics 365 Customer Insights auditorijas ieskatiem.
ms.date: 05/14/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: e832fbbdfb59cb06d98715223edca438d2c3a7f2
ms.sourcegitcommit: dab2cbf818fafc9436e685376df94c5e44e4b144
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 07/13/2021
ms.locfileid: "6554340"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Datu subjektu tiesību (DSR) pieprasījumi saskaņā ar VDAR

## <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a>Atbilde uz VDAR datu subjektu dzēšanas prasībām saistībā ar Dynamics 365 Customer Insights auditorijas ieskatiem.

“Tiesības dzēst”, veicot personas datu noņemšanu no organizācijas klientu datiem, ir galvenā aizsardzība saskaņā ar Vispārīgo datu aizsardzības regulu (VDAR). Personas datu dzēšana ietver visu personas datu un sistēmas radītu ierakstu, izņemot audita ierakstu informācijas, dzēšanu.

### <a name="manage-data-subject-delete-requests"></a>Datu subjekta dzēšanas pieprasījumu pārvaldība

Auditorijas ieskati piedāvā tālāk norādītās produkta lietošanas iespējas, lai izdzēstu konkrēta klienta vai lietotāja personas datus:

- **Klienta datu dzēšanas pieprasījumu pārvaldīšana**: klientu dati programmā Customer Insights tiek pieņemti no sākotnējiem datu avotiem ārpus programmas Customer Insights. Visi VDAR dzēšanas pieprasījumi ir jāizpilda sākotnējā datu avotā.
- **Pārvaldiet dzēšanas pieprasījumus Customer Insights lietotāju datiem** : Dati lietotājiem tiek izveidoti, izmantojot Customer Insights. Visi VDAR dzēšanas pieprasījumi ir jāizpilda programmā Customer Insights.

#### <a name="manage-delete-requests-for-customer-data"></a>Klienta datu dzēšanas pieprasījumu pārvaldīšana

Customer Insights administrators var veikt šīs darbības, lai noņemtu datus, kas bija dzēsti klientu datos:

1. Pierakstieties programmā Dynamics 365 Customer Insights.
2. Sadaļā Auditorijas ieskati ejiet uz **Dati** > **Datu avoti**.
3. Katram sarakstā iekļautajam datu avotam, kurā ir izdzēsti klienta dati:
   1. Atlasiet (...) un pēc tam atlasiet **Atsvaidzināt**.
   2. Skatiet datu avota statusu sadaļā **Statuss**. Atzīme nozīmē, ka atsvaidzināšana bija veiksmīga. Brīdinājuma trijstūris nozīmē, ka radās problēma. Ja tiek parādīts brīdinājuma trijstūris, sazinieties ar D365CI@microsoft.com.

> [!div class="mx-imgBorder"]
> ![Klienta datu VDAR dzēšanas pieprasījumu apstrāde.](media/gdpr-data-sources.png "Klienta datu VDAR dzēšanas pieprasījumu apstrāde")

#### <a name="manage-delete-requests-for-user-data"></a>Lietotāju datu dzēšanas pieprasījumu pārvaldīšana

Customer Insights administrators var veikt tālāk norādītās darbības, lai dzēstu Customer Insights lietotāja datus:

1. Pierakstieties programmā Dynamics 365 Customer Insights.
2. Sadaļā Auditorijas ieskati ejiet uz **Administrators** > **Atļaujas**.
3. Atzīmējiet tā lietotāja izvēles rūtiņu, kuru vēlaties dzēst.
4. Atlasiet **Noņemt**.

> [!div class="mx-imgBorder"]
> ![Lietotāju VDAR datu dzēšanas pieprasījumu pārvaldīšana.](media/gdpr-permissions.png "Lietotāju VDAR datu dzēšanas pieprasījumu pārvaldīšana")

## <a name="responding-to-gdpr-data-subject-export-requests"></a>Reaģēšana uz VDAR datu subjekta eksportēšanas pieprasījumiem

Tā kā vēlamies atvieglot jūsu pieredzi ar Vispārīgo datu aizsardzības regulu (VDAR), esam izstrādājuši dokumentāciju, kas palīdzēs sagatavoties. Šajā dokumentācijā ir aprakstītas darbības, kuras varat veikt mūsdienās, lai atbalstītu VDAR atbilstību, izmantojot auditorijas ieskatus.

### <a name="manage-export-and-view-requests"></a>Eksportēšanas pārvaldīšana un pieprasījumu skatīšana

Datu pārvietojamības tiesības ļauj datu subjektiem pieprasīt savu personas datu kopiju elektroniskā formātā ("strukturēts, plaši lietots, mašīnlasāms un savstarpēji izmantojams formāts), kurus var pārsūtīt citam datu pārzinim.

#### <a name="export-customer-data-tenant-admin"></a>Klienta datu eksportētājs (nomnieka administrators)

Lai eksportētu datus, nomnieka administrators var veikt tālāk norādītas darbības:.

1. Nosūtiet e-pasta ziņojumu uz e-pasta adresi D365CI@microsoft.com, norādot klienta e-pasta adresi pieprasījumā. Customer Insights komanda nosūtīs e-pasta ziņojumu uz reģistrēto nomnieka administratora e-pasta adresi, lūdzot apstiprinājumu datu eksportēšanai.
2. Atzīstiet apstiprinājumu eksportēt pieprasītā klienta datus.
3. Saņemiet eksportētos datus, izmantojot nomnieka administratora e-pasta adresi.

#### <a name="export-user-data-tenant-admin"></a>Klienta datu eksportēšana (nomnieka administrators)

1. Nosūtiet e-pasta ziņojumu uz e-pasta adresi D365CI@microsoft.com, norādot lietotāja e-pasta adresi pieprasījumā. Customer Insights komanda nosūtīs e-pasta ziņojumu uz reģistrēto nomnieka administratora e-pasta adresi, lūdzot apstiprinājumu datu eksportēšanai.
2. Atzīstiet apstiprinājumu eksportēt pieprasītā lietotāja datus.
3. Saņemiet eksportētos datus, izmantojot nomnieka administratora e-pasta adresi.


[!INCLUDE[footer-include](../includes/footer-banner.md)]