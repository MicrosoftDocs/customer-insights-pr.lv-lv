---
title: Datu subjektu tiesību (DSR) pieprasījumi saskaņā ar VDAR | Microsoft Docs
description: Atbildiet uz datu subjektu pieprasījumiem attiecībā uz Dynamics 365 Customer Insights.
ms.date: 08/11/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: af2583295627f98e980adbca4f216b9c34c3cad8
ms.sourcegitcommit: bf65bc0a54cdab71680e658e1617bee7b2c2bb68
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 05/27/2022
ms.locfileid: "8808570"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Datu subjektu tiesību (DSR) pieprasījumi saskaņā ar VDAR

Eiropas Savienības Vispārīgā datu aizsardzības regula (VDAR) ir spēkā kopš 2018. gada 25. maija. Tas sniedz personām būtiskas tiesības attiecībā uz to datiem. VDAR tika pieņemta ar mērķi aizsargāt un ļaut izmantot personu tiesības uz konfidencialitāti. Papildinformāciju par korporācijas Microsoft drošības apsvērumu ievērošanu un atbilstību varat lasīt [Microsoft drošības kontroles centrā](https://www.microsoft.com/trust-center).

Mēs gribam palīdzēt mūsu klientiem varētu izpildīt savas VDAR prasības. Tajā ir iekļautas tiesības dzēst un eksportēt datus, kuros ir iekļauta personiska informācija, piemēram, lietotāja ID, tālruņu numuri un e-pasta adreses. Administratori var ieviest lietotāju pieprasījumus, lai dzēstu vai eksportētu personiskos datus.

## <a name="dynamics-365-customer-insights"></a>Dynamics 365 Customer Insights

### <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights"></a>Reaģēšana uz VDAR datu subjekta dzēšanas pieprasījumiem attiecībā uz Dynamics 365 Customer Insights

“Tiesības dzēst”, veicot personas datu noņemšanu no organizācijas klientu datiem, ir galvenā aizsardzība saskaņā ar Vispārīgo datu aizsardzības regulu (VDAR). Personas datu dzēšana ietver visu personas datu un sistēmas radītu ierakstu, izņemot audita ierakstu informācijas, dzēšanu.

#### <a name="manage-data-subject-delete-requests"></a>Datu subjekta dzēšanas pieprasījumu pārvaldība

Customer Insights piedāvā šādu produkta pieredzi, lai dzēstu personas datus konkrētam klientam vai lietotājam:

- **Klienta datu dzēšanas pieprasījumu pārvaldīšana**: klientu dati programmā Customer Insights tiek pieņemti no sākotnējiem datu avotiem ārpus programmas Customer Insights. Visi VDAR dzēšanas pieprasījumi ir jāizpilda sākotnējā datu avotā.
- **Pārvaldiet dzēšanas pieprasījumus Customer Insights lietotāju datiem** : Dati lietotājiem tiek izveidoti, izmantojot Customer Insights. Visi VDAR dzēšanas pieprasījumi ir jāizpilda programmā Customer Insights.

##### <a name="manage-requests-to-delete-customer-data"></a>Klienta datu dzēšanas pieprasījumu pārvaldīšana

Customer Insights administrators var veikt šīs darbības, lai noņemtu datus, kas bija dzēsti klientu datos:

1. Pierakstieties programmā Dynamics 365 Customer Insights.
2. Doties uz **datu datu** > **avotiem**
3. Katram sarakstā iekļautajam datu avotam, kurā ir izdzēsti klienta dati:
   1. Atlasiet vertikālo daudzpunkti (&vellip;) un pēc tam atlasiet **Atsvaidzināt**.
   2. Skatiet datu avota statusu sadaļā **Statuss**. Atzīme nozīmē, ka atsvaidzināšana bija veiksmīga. Brīdinājuma trijstūris nozīmē, ka radās problēma. Ja tiek parādīts brīdinājuma trijstūris, sazinieties ar D365CI@microsoft.com.

> [!div class="mx-imgBorder"]
> ![Klienta datu VDAR dzēšanas pieprasījumu apstrāde.](media/gdpr-data-sources.png "Klienta datu VDAR dzēšanas pieprasījumu apstrāde")

##### <a name="manage-delete-requests-for-user-data"></a>Lietotāju datu dzēšanas pieprasījumu pārvaldīšana

Customer Insights administrators var veikt tālāk norādītās darbības, lai dzēstu Customer Insights lietotāja datus:

1. Pierakstieties programmā Dynamics 365 Customer Insights.
2. Dodieties uz **administratora** > **drošības** > **atļaujām**.
3. Atzīmējiet tā lietotāja izvēles rūtiņu, kuru vēlaties dzēst.
4. Atlasiet **Noņemt**.

### <a name="responding-to-gdpr-data-subject-export-requests"></a>Reaģēšana uz VDAR datu subjekta eksportēšanas pieprasījumiem

Kā daļu no mūsu apņemšanās sadarboties ar jums ceļā uz Vispārīgo datu aizsardzības regulu (VDAR), mēs esam izstrādājuši dokumentāciju, lai palīdzētu jums atbildēt uz datu subjektu pieprasījumiem.

#### <a name="manage-export-and-view-requests"></a>Eksportēšanas pārvaldīšana un pieprasījumu skatīšana

Datu pārvietojamības tiesības ļauj datu subjektiem pieprasīt savu personas datu kopiju elektroniskā formātā ("strukturēts, plaši lietots, mašīnlasāms un savstarpēji izmantojams formāts), kurus var pārsūtīt citam datu pārzinim.

##### <a name="export-customer-data-tenant-admin"></a>Klienta datu eksportētājs (nomnieka administrators)

Lai eksportētu datus, nomnieka administrators var veikt tālāk norādītas darbības:.

1. Nosūtiet e-pasta ziņojumu uz e-pasta adresi D365CI@microsoft.com, norādot klienta e-pasta adresi pieprasījumā. Customer Insights komanda nosūtīs e-pasta ziņojumu uz reģistrēto nomnieka administratora e-pasta adresi, lūdzot apstiprinājumu datu eksportēšanai.
2. Atzīstiet apstiprinājumu eksportēt pieprasītā klienta datus.
3. Saņemiet eksportētos datus, izmantojot nomnieka administratora e-pasta adresi.

##### <a name="export-user-data-tenant-admin"></a>Klienta datu eksportēšana (nomnieka administrators)

1. Nosūtiet e-pasta ziņojumu uz e-pasta adresi D365CI@microsoft.com, norādot lietotāja e-pasta adresi pieprasījumā. Customer Insights komanda nosūtīs e-pasta ziņojumu uz reģistrēto nomnieka administratora e-pasta adresi, lūdzot apstiprinājumu datu eksportēšanai.
2. Atzīstiet apstiprinājumu eksportēt pieprasītā lietotāja datus.
3. Saņemiet eksportētos datus, izmantojot nomnieka administratora e-pasta adresi.

## <a name="consent-management-preview"></a>Piekrišanas pārvaldība (priekšskatījums)

Piekrišanas pārvaldības iespēja tieši neapkopo lietotāja datus. Tas tikai importē un apstrādā piekrišanas datus, ko lietotāji sniedz citās lietojumprogrammās.

Lai noņemtu piekrišanas datus par konkrētiem lietotājiem, noņemiet tos datu avotos, kas uzņemti piekrišanas pārvaldības iespējai. Pēc datu avots atsvaidzināšanas noņemtie dati tiks dzēsti arī piekrišanas centrā. Lietojumprogrammas, kas izmanto piekrišanas entītiju, arī dzēsīs datus, kas pēc atsvaidzināšanas [tika noņemti avotā](system.md#refresh-processes). Mēs iesakām ātri atsvaidzināt datu avotus pēc atbildes uz datu subjekta pieprasījumu noņemt lietotāja datus no visiem citiem procesiem un lietojumprogrammām.

[!INCLUDE [footer-include](includes/footer-banner.md)]