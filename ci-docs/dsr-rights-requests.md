---
title: Datu subjektu tiesību (DSR) pieprasījumi saskaņā ar VDAR | Microsoft Docs
description: Atbildēt uz datu tēmu pieprasījumiem Dynamics 365 Customer Insights auditorijas ieskatu iespējām.
ms.date: 08/11/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: c116f7ce208c0288851a4b2230e27784ba3a5337
ms.sourcegitcommit: 834651b933b1e50e7557d44f926a3fb757c1f83a
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 11/02/2021
ms.locfileid: "7732689"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Datu subjektu tiesību (DSR) pieprasījumi saskaņā ar VDAR

Eiropas Savienības Vispārīgā datu aizsardzības regula (VDAR) ir spēkā kopš 2018. gada 25. maija. Tas sniedz personām būtiskas tiesības attiecībā uz to datiem. VDAR tika pieņemta ar mērķi aizsargāt un ļaut izmantot personu tiesības uz konfidencialitāti. Papildinformāciju par korporācijas Microsoft drošības apsvērumu ievērošanu un atbilstību varat lasīt [Microsoft drošības kontroles centrā](https://www.microsoft.com/trust-center).

Mēs gribam palīdzēt mūsu klientiem varētu izpildīt savas VDAR prasības. Tajā ir iekļautas tiesības dzēst un eksportēt datus, kuros ir iekļauta personiska informācija, piemēram, lietotāja ID, tālruņu numuri un e-pasta adreses. Administratori var ieviest lietotāju pieprasījumus, lai dzēstu vai eksportētu personiskos datus.

## <a name="audience-insights"></a>Auditorijas ieskati

### <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a>Atbildot uz GDPR datu subjekta dzēšanas pieprasījumiem Dynamics 365 Customer Insights auditorijas ieskatu iespējām

“Tiesības dzēst”, veicot personas datu noņemšanu no organizācijas klientu datiem, ir galvenā aizsardzība saskaņā ar Vispārīgo datu aizsardzības regulu (VDAR). Personas datu dzēšana ietver visu personas datu un sistēmas radītu ierakstu, izņemot audita ierakstu informācijas, dzēšanu.

#### <a name="manage-data-subject-delete-requests"></a>Datu subjekta dzēšanas pieprasījumu pārvaldība

Auditorijas ieskati piedāvā tālāk norādītās produkta lietošanas iespējas, lai izdzēstu konkrēta klienta vai lietotāja personas datus:

- **Klienta datu dzēšanas pieprasījumu pārvaldīšana**: klientu dati programmā Customer Insights tiek pieņemti no sākotnējiem datu avotiem ārpus programmas Customer Insights. Visi VDAR dzēšanas pieprasījumi ir jāizpilda sākotnējā datu avotā.
- **Pārvaldiet dzēšanas pieprasījumus Customer Insights lietotāju datiem** : Dati lietotājiem tiek izveidoti, izmantojot Customer Insights. Visi VDAR dzēšanas pieprasījumi ir jāizpilda programmā Customer Insights.

##### <a name="manage-requests-to-delete-customer-data"></a>Klienta datu dzēšanas pieprasījumu pārvaldīšana

Customer Insights administrators var veikt šīs darbības, lai noņemtu datus, kas bija dzēsti klientu datos:

1. Piesakieties Dynamics 365 Customer Insights.
2. Sadaļā Auditorijas ieskati ejiet uz **Dati** > **Datu avoti**.
3. Katram sarakstā iekļautajam datu avotam, kurā ir izdzēsti klienta dati:
   1. Atlasiet (...) un pēc tam atlasiet **Atsvaidzināt**.
   2. Skatiet datu avota statusu sadaļā **Statuss**. Atzīme nozīmē, ka atsvaidzināšana bija veiksmīga. Brīdinājuma trijstūris nozīmē, ka radās problēma. Ja tiek parādīts brīdinājuma trijstūris, sazinieties ar D365CI@microsoft.com.

> [!div class="mx-imgBorder"]
> ![Klienta datu VDAR dzēšanas pieprasījumu apstrāde.](audience-insights/media/gdpr-data-sources.png "Klienta datu VDAR dzēšanas pieprasījumu apstrāde")

##### <a name="manage-delete-requests-for-user-data"></a>Lietotāju datu dzēšanas pieprasījumu pārvaldīšana

Customer Insights administrators var veikt tālāk norādītās darbības, lai dzēstu Customer Insights lietotāja datus:

1. Piesakieties Dynamics 365 Customer Insights.
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


## <a name="engagement-insights-preview"></a>Iesaistes ieskati (priekšskatījums)

### <a name="deleting-and-exporting-event-data-containing-end-user-identifiable-information"></a>Notikuma datu, kas ietver lietotāja identificējamu informāciju, dzēšana un eksportēšana

Nākamajās sadaļās ir aprakstīts, kā dzēst un eksportēt notikumu datus, kuros var būt ietverti personiskie dati.

Lai dzēstu vai eksportētu datus:

1. Atzīmējiet notikuma rekvizītus, kuros ir dati ar personisku informāciju.
2. Dzēsiet vai eksportējiet datus, kas saistīti ar noteiktām vērtībām (piemēram, norādīto lietotāja ID).

#### <a name="tag-and-update-event-properties"></a>Atzīmējiet vai atjauniniet notikuma rekvizītus

Personiskie dati tiek atzīmēti notikuma rekvizītu līmenī. Vispirms atzīmējiet rekvizītus, kas tiek uzskatīti par dzēšanas vai eksportēšanas rekvizītiem.

Lai notikuma rekvizītam pievienotu atzīmi, kurā ir iekļauta personiska informācija, veiciet šīs darbības:

1. Atveriet darbvietu, kurā ir notikums.

1. Dodieties uz **Dati** > **Notikumi**, lai skatītu atlasītās darbvietas notikumu sarakstu.
  
1. Atlasiet notikumu, ko vēlaties atzīmēt.

1. Atlasiet **Rediģēt rekvizītus**, lai atvērtu rūts priekšskatījuma skatu visiem atlasītā notikuma rekvizītiem.
     
1. Atlasiet **...** un pēc tam izvēlieties **Rediģēt**, lai atvērtu dialogu **Atjaunināt rekvizītu**.

   ![Rediģēt notikumu.](engagement-insights/media/edit-event.png "Rediģēt notikumu")

1. Lodziņā **Atjaunināt rekvizītu** izvēlieties **...** augšējā labajā stūrī un pēc tam izvēlieties lodziņu **Satur EUII**. Izvēlieties **Atjaunināt**, lai saglabātu izmaiņas.

   ![Saglabājiet izmaiņas.](engagement-insights/media/update-property.png "Saglabājiet izmaiņas")

   > [!NOTE]
   > Ja nepieciešams, katru reizi, kad notikumu shēma mainās vai izveidojat jaunu notikumu, ieteicams novērtēt saistītos notikumu rekvizītus un atzīmēt tos vai noņemt atzīmi no tiem, kas ietver personiskus datus.

#### <a name="delete-or-export-tagged-event-data"></a>Dzēst vai eksportēt atzīmētos notikuma datus

Ja visi notikuma rekvizīti ir atzīmēti kā aprakstīts iepriekšējā darbībā, vides administrators var izdot dzēšanas pieprasījumu, salīdzinot ar atzīmētajiem notikuma datiem.

Lai pārvaldītu EUII dzēšanu vai eksportētu pieprasījumus

1. Dodieties uz **Administrators** > **Vide** > **Iestatījumi**.

1. Sadaļā **Pārvaldīt gala lietotāju identificējošo informāciju (EUII)** atlasiet **Pārvaldīt EUII**.

##### <a name="deletion"></a>Dzēšana

Dzēšanas nolūkā komatatdalīto lietotāju ID sarakstu var ievadīt sadaļā **Dzēst gala lietotāja identificējošo informāciju (EUII)**. Šie ID pēc tam tiks salīdzināti ar visiem atzīmētajiem notikumu rekvizītiem visos pašreizējās vides projektos, izmantojot precīzu virkņu atbilstību. 

Ja rekvizīta vērtība atbilst vienam no nodrošinātajiem ID, saistītais notikums tiks neatgriezeniski dzēsts. Šī darbība ir neatgriezeniska, tāpēc dzēšana ir jāapstiprina pēc vienuma **Dzēst** atlasīšanas.

##### <a name="export"></a>Eksportēšana

Eksportēšanas process ir identisks dzēšanas procesam, kas attiecas uz notikuma rekvizītu vērtību definēšanu sadaļā **Eksportēt gala lietotāja identificējošo informāciju (EUII)**. Turklāt jānorāda **Azure Blob krātuves URL**, lai norādītu eksportēšanas galamērķi. Azure BLOB URL ir jābūt iekļautam [Koplietojamās piekļuves parakstā (SAS)](/azure/storage/common/storage-sas-overview).

Pēc vienuma **Eksportēt** atlasīšanas, visi pašreizējās darba grupas notikumi satur atbilstošos, atzīmētos rekvizītus, kas tiks eksportēti CSV formātā uz eksportēšanas galamērķi.

### <a name="good-practices"></a>Laba prakse

* Mēģiniet izvairīties no notikumu sūtīšanas, kuros ir ietverti personiski dati.
* Ja jānosūta notikumi, kuros ir EUII dati, ierobežojiet notikumu un notikumu rekvizītu skaitu, kuros ir EUII dati. Ideālā gadījumā aprobežojieties ar vienu šādu notikumu.
* Pārliecinieties, vai nosūtītajiem personiskajiem datiem ir piekļuve pēc iespējas vairāk personām.
* Notikumiem, kuros ir personiskie dati, pārliecinieties, vai ir iestatīts viens rekvizīts, lai ģenerētu unikālu identifikatoru, ko var viegli saistīt ar konkrētu lietotāju (piemēram, lietotāja ID). Šādi ir vienkāršāk nodalīt datus un eksportēt vai dzēst pareizos datus.
* Katram notikumam atzīmējiet tikai vienu rekvizītu, kurā ir iekļauti personiskie dati. Vislabāk - tas, kurā ir tikai unikālais identifikators.
* Neatzīmējiet rekvizītus, kas ietver zīmju rindas vērtības (piemēram, veselu pieprasījuma pamattekstu). Iesaistes ieskatu iespēja izmanto precīzu virkņu atbilstību, izlemjot, kurus notikumus dzēst vai eksportēt.

[!INCLUDE[footer-include](includes/footer-banner.md)]