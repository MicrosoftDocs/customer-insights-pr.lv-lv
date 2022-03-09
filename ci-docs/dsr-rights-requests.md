---
title: Datu subjektu tiesību (DSR) pieprasījumi saskaņā ar VDAR | Microsoft Docs
description: Atbilde uz datu subjektu prasībām saistībā ar Dynamics 365 Customer Insights auditorijas ieskatiem.
ms.date: 08/11/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: e095eb4f8e194f314d7d6baf6fa6a7a319319d2a
ms.sourcegitcommit: 1946d7af0bd2ca216885bec3c5c95009996d9a28
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 02/25/2022
ms.locfileid: "8350278"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Datu subjektu tiesību (DSR) pieprasījumi saskaņā ar VDAR

Eiropas Savienības Vispārīgā datu aizsardzības regula (VDAR) ir spēkā kopš 2018. gada 25. maija. Tas sniedz personām būtiskas tiesības attiecībā uz to datiem. VDAR tika pieņemta ar mērķi aizsargāt un ļaut izmantot personu tiesības uz konfidencialitāti. Papildinformāciju par korporācijas Microsoft drošības apsvērumu ievērošanu un atbilstību varat lasīt [Microsoft drošības kontroles centrā](https://www.microsoft.com/trust-center).

Mēs gribam palīdzēt mūsu klientiem varētu izpildīt savas VDAR prasības. Tajā ir iekļautas tiesības dzēst un eksportēt datus, kuros ir iekļauta personiska informācija, piemēram, lietotāja ID, tālruņu numuri un e-pasta adreses. Administratori var ieviest lietotāju pieprasījumus, lai dzēstu vai eksportētu personiskos datus.

## <a name="audience-insights"></a>Auditorijas ieskati

### <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a>Atbilde uz VDAR datu subjektu dzēšanas prasībām saistībā ar Dynamics 365 Customer Insights auditorijas ieskatiem.

“Tiesības dzēst”, veicot personas datu noņemšanu no organizācijas klientu datiem, ir galvenā aizsardzība saskaņā ar Vispārīgo datu aizsardzības regulu (VDAR). Personas datu dzēšana ietver visu personas datu un sistēmas radītu ierakstu, izņemot audita ierakstu informācijas, dzēšanu.

#### <a name="manage-data-subject-delete-requests"></a>Datu subjekta dzēšanas pieprasījumu pārvaldība

Auditorijas ieskati piedāvā tālāk norādītās produkta lietošanas iespējas, lai izdzēstu konkrēta klienta vai lietotāja personas datus:

- **Klienta datu dzēšanas pieprasījumu pārvaldīšana**: klientu dati programmā Customer Insights tiek pieņemti no sākotnējiem datu avotiem ārpus programmas Customer Insights. Visi VDAR dzēšanas pieprasījumi ir jāizpilda sākotnējā datu avotā.
- **Pārvaldiet dzēšanas pieprasījumus Customer Insights lietotāju datiem** : Dati lietotājiem tiek izveidoti, izmantojot Customer Insights. Visi VDAR dzēšanas pieprasījumi ir jāizpilda programmā Customer Insights.

##### <a name="manage-requests-to-delete-customer-data"></a>Klienta datu dzēšanas pieprasījumu pārvaldīšana

Customer Insights administrators var veikt šīs darbības, lai noņemtu datus, kas bija dzēsti klientu datos:

1. Pierakstieties programmā Dynamics 365 Customer Insights.
2. Sadaļā Auditorijas ieskati ejiet uz **Dati** > **Datu avoti**.
3. Katram sarakstā iekļautajam datu avotam, kurā ir izdzēsti klienta dati:
   1. Atlasiet (...) un pēc tam atlasiet **Atsvaidzināt**.
   2. Skatiet datu avota statusu sadaļā **Statuss**. Atzīme nozīmē, ka atsvaidzināšana bija veiksmīga. Brīdinājuma trijstūris nozīmē, ka radās problēma. Ja tiek parādīts brīdinājuma trijstūris, sazinieties ar D365CI@microsoft.com.

> [!div class="mx-imgBorder"]
> ![Klienta datu VDAR dzēšanas pieprasījumu apstrāde.](audience-insights/media/gdpr-data-sources.png "Klienta datu VDAR dzēšanas pieprasījumu apstrāde")

##### <a name="manage-delete-requests-for-user-data"></a>Lietotāju datu dzēšanas pieprasījumu pārvaldīšana

Customer Insights administrators var veikt tālāk norādītās darbības, lai dzēstu Customer Insights lietotāja datus:

1. Pierakstieties programmā Dynamics 365 Customer Insights.
2. Sadaļā Auditorijas ieskati ejiet uz **Administrators** > **Atļaujas**.
3. Atzīmējiet tā lietotāja izvēles rūtiņu, kuru vēlaties dzēst.
4. Atlasiet **Noņemt**.

### <a name="responding-to-gdpr-data-subject-export-requests"></a>Reaģēšana uz VDAR datu subjekta eksportēšanas pieprasījumiem

Tā kā vēlamies atvieglot jūsu pieredzi ar Vispārīgo datu aizsardzības regulu (VDAR), esam izstrādājuši dokumentāciju, kas palīdzēs sagatavoties. Šajā dokumentācijā ir aprakstītas darbības, kuras varat veikt mūsdienās, lai atbalstītu VDAR atbilstību, izmantojot auditorijas ieskatus.

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

Piekrišanas pārvaldības iespēja tieši neapkopo lietotāju datus. Tā importē un apstrādā tikai tos piekrišanas datus, ko lietotāji sniedz citās lietojumprogrammās.

Lai noņemtu piekrišanas datus par konkrētiem lietotājiem, noņemiet tos datu avotos, kas uzņemti piekrišanas pārvaldības iespējās. Pēc datu avots atsvaidzināšanas noņemtie dati tiks dzēsti arī piekrišanas centrā. Lietojumprogrammas, kas izmanto piekrišanas entītiju, arī dzēsīs datus, kas pēc atsvaidzināšanas tika noņemti [avotā](audience-insights/system.md#refresh-processes). Mēs iesakām ātri atsvaidzināt datu avotus pēc tam, kad esat atbildējusi uz datu subjekta pieprasījumu, lai noņemtu lietotāja datus no visiem citiem procesiem un lietojumprogrammām.


<!-- ## Engagement insights (preview)

### Deleting and exporting event data containing end user identifiable information

The following sections describe how to delete and export event data that might contain personal data.

To delete or export data:

1. Tag event properties that contain data with personal information.
2. Delete or export data associated with specific values (for example: a specified user ID).

#### Tag and update event properties

Personal data is tagged on an event property level. First, tag the properties being considered for deletion or export.

To tag an event property as containing personal information, follow these steps:

1. Open the workspace containing the event.

1. Go to **Data** > **Events** to see the list of events in the selected workspace.
  
1. Select the event you want to tag.

1. Select **Edit properties** to open the pane listing all properties of the selected event.
     
1. Select **...** and then choose **Edit** to reach the **Update property** dialog.

   ![Edit event.](engagement-insights/media/edit-event.png "Edit event")

1. In the **Update Property** window, choose **...** in the upper right corner, and then choose the **Contains EUII** box. Choose **Update** to save your changes.

   ![Save your changes.](engagement-insights/media/update-property.png "Save your changes")

   > [!NOTE]
   > Every time the event schema changes or you create a new event, it's recommended that you evaluate the associated event properties and tag or untag them as containing personal data, if necessary.

#### Delete or export tagged event data

If all event properties have been tagged appropriately as described in the previous step, an environment admin can issue a deletion request against the tagged event data.

To manage EUII deletion or export requests

1. Go to **Admin** > **Environment** > **Settings**.

1. In the **Manage end user identifiable information (EUII)** section, select **Manage EUII**.

##### Deletion

For deletion, you can enter a list of comma-separated user IDs in the **Delete end user identifiable information (EUII)** section. These IDs will then be compared with all tagged event properties of all projects in the current environment via exact string matching. 

If a property value matches one of the provided IDs, the associated event will be permanently deleted. Due to the irreversibility of this action, you must confirm the deletion after selecting **Delete**.

##### Export

The export process is identical to the deletion process when it comes to defining event property values in the **Export end user identifiable information (EUII)** section. Additionally, you'll need to provide an **Azure blob storage URL** to specify the export destination. The Azure Blob URL must include a [Shared Access Signature (SAS)](/azure/storage/common/storage-sas-overview).

After selecting **Export**, all events of the current team that contain matching tagged properties will be exported in CSV format to the export destination.

### Good practices

* Try to avoid sending any events that contain personal data.
* If you need to send events containing EUII data, limit the number of events and event properties that contain EUII data. Ideally, limit yourself to one such event.
* Make sure that as few people as possible have access to the sent personal data.
* For events containing personal data, make sure that you set one property to emit a unique identifier that can easily be linked to a specific user (for example, a user ID). This makes it easier to segregate data and to export or delete the right data.
* Only tag one property per event as containing personal data. Ideally one that only contains a unique identifier.
* Do not tag properties containing verbose values (for example, an entire request body). Engagement insights capability uses exact string matching when deciding which events to delete or export. -->

[!INCLUDE[footer-include](includes/footer-banner.md)]