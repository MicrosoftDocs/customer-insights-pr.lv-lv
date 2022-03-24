---
title: Bagātināt klientu profilus ar datiem no Microsoft Office 365
description: Izmantojiet patentētus datus, lai Microsoft Office bagātinātu klientu profilus ar iesaistes datiem.
ms.date: 12/03/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahl
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 47239bd7f0c89742cf9c673bb2ebe4c41d853233
ms.sourcegitcommit: 50d32a4cab01421a5c3689af789e20857ab009c4
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 03/03/2022
ms.locfileid: "8376839"
---
# <a name="enrich-customer-profiles-with-engagement-data-preview"></a>Klientu profilu bagātināšana ar piesaistes datiem (priekšskatījums)

Izmantojiet datus, lai Microsoft Office 365 bagātinātu klientu kontu profilus ar ieskatu par iesaistīšanos, izmantojot Office 365 lietotnes. Iesaistes dati sastāv no e-pasta un sapulces darbībām, kas tiek apkopotas konta līmenī. Piemēram, e-pasta ziņojumu skaits no uzņēmuma konta vai ar kontu saistīto sapulču skaits. Dati par atsevišķiem lietotājiem nav pieejami. 

Šī bagātināšana ir pieejama šādos reģionos: Apvienotajā Karalistē, Eiropā, Ziemeļamerikā.

## <a name="prerequisites"></a>Priekšnoteikumi

Lai konfigurētu bagātināšanu, ir jāizpilda šādi priekšnosacījumi:

- Jums ir aktīva Office 365 mākoņa licence.
- Jums ir vienoti debitoru profili, [kuru pamatā](customer-profiles.md) ir [biznesa konti](work-with-business-accounts.md).
- Jūsu Customer Insights vidē ir jābūt pievienotai [Microsoft Dataverse organizācijai](create-environment.md#step-3-connect-to-microsoft-dataverse).
- Jums ir [administratora](permissions.md#admin) atļaujas.
- Jums ir vai jūs varat saņemt nomnieka Office 365 administratora piekrišanu izmantot Office 365 datus, lai sniegtu **ieskatus organizācijai** Dynamics 365 lietojumprogrammās.

## <a name="configure-the-enrichment"></a>Bagātināto datu konfigurēšana

1. Sadaļā Auditorijas ieskati skatiet **Dati** > **Darbības**.

1. Dodieties uz **cilni Atklāšana** un elementā **Konta iesaiste** atlasiet **Bagātināt manus datus**.

   :::image type="content" source="media/enrichment-office-tile.png" alt-text="Konta piesaistes elements.":::
   
1. Solī Pārskats **atlasiet** Tālāk **un** ievadiet savas organizācijas e-pasta adreses, par kurām tiks apkopoti Office dati. Attiecīgajai saziņai tiek apstrādāti tikai dati no uzskaitītajām e-pasta adresēm. Labākā prakse ir izmantot e-pasta grupas, piemēram, *ASV pārdošanas komandu*, kas ir viegli pārvaldāma Office 365. E-pasta adrešu skaits grupās ir atrisināts un parādīts. Kopējam e-pasta adrešu skaitam jābūt vismaz 2, un tas nedrīkst pārsniegt 2500.

   :::image type="content" source="media/enrichment-office-email-addresses.png" alt-text="Konta iesaistes e-pasta adreses.":::

1. Pārskatiet piekrišanas paziņojumu, atzīmējiet **izvēles rūtiņu Piekrītu** un atlasiet **Tālāk**.

1. Atlasiet debitoru datu kopu un atlasiet **Tālāk**.

1. Kartējiet kontaktpersonas e-pasta adreses lauku un atlasiet **Tālāk**.

1. Pārskatiet bagātināšanas konfigurāciju, piešķiriet bagātināšanai nosaukumu un atlasiet **Saglabāt bagātināšanu**, lai saglabātu bagātināšanu.

## <a name="office-365-tenant-administrator-consent"></a>Office 365 nomnieka administratora piekrišana

Lai aktivizētu bagātināšanu, ir nepieciešama īrnieka Office 365 administratora piekrišana. Kad bagātināšana tiek saglabāta, nomnieka administratoriem tiek nosūtīts Office 365 e-pasta ziņojums, kurā tiek lūgts viņiem pārskatīt un piekrist tam, ka Dynamics 365 lietojumprogrammas var izmantot jūsu uzņēmumu Office 365 datus, lai sniegtu **ieskatus organizācijai**. Nomnieka Office 365 administrators var arī piekrist tieši savā Office 365 administratora konsolē, atlasot **Ieskati organizācijai**.

## <a name="running-the-enrichment-for-the-first-time"></a>Bagātināšanas palaišana pirmo reizi

Kad bagātināšana tiek uzsākta pirmo reizi, pēc tam, kad īrnieka Office 365 administrators ir devis piekrišanu, sākas datu lejupielāde no tā Office 365. Šis process aizņem kādu laiku. Plānots, ka pirmais bagātināšanas brauciens notiks ar sešu stundu kavēšanos. Dienu skaitu, ko dati aptver konta piesaistes pārskata lapā pēc bagātināšanas pabeigšanas, var redzēt. Ar lielu datu apjomu pēc dažām dienām vēlreiz palaidiet bagātināšanu. Tas nodrošina, ka dati ir pabeigti visā laika periodā, kas ir viens gads.

Lai sāktu procesu, lapā Konta piesaistes konfigurācija atlasiet **Palaist**. Turklāt varat ļaut sistēmai automātiski palaist bagātināšanu kā daļu no plānotās [atsvaidzināšanas](system.md#schedule-tab). Pēc noklusējuma bagātināšana darbojas reizi nedēļā.

Atkarībā no Office datu lieluma bagātināšanas palaišanas pabeigšanai var būt nepieciešamas vairākas stundas.

Palaižot bagātināšanu, Microsoft apstrādās datus Office 365 atbilstības robežās, lai izveidotu apkopotus ieskatus, kas pēc tam tiek pievienoti jūsu Customer Insights videi. Customer Insights lietotājiem nav pieejami dati individuālā līmenī (piemēram, e-pasta vai kalendāra uzaicinājuma pamatteksts). 

[!INCLUDE [progress-details-pane](../includes/progress-details-pane.md)]

## <a name="enrichment-results"></a>Bagātināšanas rezultāti

Pēc bagātināšanas procesa veikšanas dodieties uz **My enrichments**, lai pārskatītu bagātināšanas rezultātus. Jūs atradīsiet kopējo bagātināto klientu skaitu un pārskatu par bagātināšanas rezultātiem. Tas ietver apstrādāto e-pasta ziņojumu un sapulču skaitu, dienu skaitu, par kurām dati ir apkopoti, un daudz ko citu.

Atradīsit arī diagrammu ar bagātināto klientu skaitu laika gaitā un bagātināšanas datu priekšskatījumu.  

:::image type="content" source="media/enrichment-office-results-overview.png" alt-text="Rezultātu priekšskatījums pēc bagātināšanas procesa izpildes.":::

Visi dati tiek apkopoti līdz konta līmenim. Sistēma aprēķina iesaistes rādītāju, kas svārstās no 0 līdz 100 katram kontam. Iesaistes rādītājs nodrošina saliktu mēru konta iesaistei e-pasta ziņojumos un sapulcēs salīdzinājumā ar citiem jūsu kontiem. Šajā sarakstā ir apkopotie dati, ko sniedz konta piesaistes bagātināšana:



| Dati                                                                              | Kolonnas nosaukums                              |
| :-------------------------------------------------------------------------------- |:---------------------------------------- |
| Iesaistes rezultāts                                                                  |  SaderināšanāsScore                         |
| E-pasta ziņojumu skaits kontā                                                       |  NoOfEmails_ToAccount                    |
| E-pasta ziņojumu skaits no konta                                                     |  NoOfEmails_FromAccount                  | 
| Konta iniciēto sapulču skaits                                           |  NoOfMeetings_FromAccount                | 
| Jūsu organizācijas iniciēto sapulču skaits                                 |  NoOfMeetings_ToAccount                  | 
| Personu skaits no jūsu organizācijas sapulcēs ar kontu                  |  NoOfContactsInvolved_Meetings           | 
| Personu skaits no jūsu organizācijas e-pasta sarunās ar kontu       |  NoOfContactsInvolved_Emails             | 
| Personu skaits no konta sapulcēs ar jūsu organizāciju                  |  NoOfAccountContactsInvolved_Meetings    | 
| Personu skaits no konta e-pasta sarunās ar jūsu organizāciju       |  NoOfAccountContactsInvolved_Emails      | 
| Iesaistīšanās sākuma datums (pirmais e-pasts vai sapulce datos)                        |  EngagementStartDate                     | 
| Dienas kopš pēdējā e-pasta                                                             |  DaysSinceLastEmail                      | 
| Dienas kopš pēdējās sanāksmes                                                           |  DaysSinceLastMeeting                    | 
| Vidējais sanāksmju ilgums                                                      |  AverageDuration_Of_Meetings             | 
| Vidējais e-pasta atbilžu ilgums no konta                                    |  AverageDuration_Of_AccountEmailReplies  | 
| Apkopošanas sākuma datums                                                            |  AggregationStartDate                    | 
| Apkopošanas līmenis (gads, mēnesis vai nedēļa)                                          |  Apkopošanas līmenis                        | 


Pārskatiet bagātinātos datus, priekšskatījuma sadaļā atlasot **Skatīt vairāk**. Tas atver Office *entītiju*. Entītiju, kas norādīta grupā **Bagātināšana**, var atrast arī **dataentities** > **·**. Jūs atradīsiet *arī Office_UserEntity*, kurā ir Active Directory ID e-pasta adresēm, kas tika izvēlētas bagātināšanas konfigurācijas laikā 

## <a name="see-enrichment-data-on-the-customer-card"></a>Skatiet informāciju par produkta bagātināšanu klienta kartītē

Konta piesaisti var apskatīt arī individuālās klientu kartēs. Atveriet sadaļu **Klienti** un atlasiet klienta profilu. Klienta kartē jūs atradīsiet konta iesaistes rezultātu, kopējo e-pasta ziņojumu skaitu un kopējo sapulču skaitu, kas apkopots pēdējā gada laikā. Jūs atradīsiet arī diagrammas, kurās tiek rādīta e-pasta un sapulču vēsture.

:::image type="content" source="media/enrichment-office-customer-card.png" alt-text="Klienta kartīte ar bagātinātiem datiem.":::

## <a name="create-segments-and-measures-based-on-the-enriched-data"></a>Segmentu un mēru izveide, pamatojoties uz bagātinātajiem datiem

Bagātinātos datus var izmantot, lai izveidotu segmentus un mērus, kā aprakstīts tālāk. Piemēram, segments, kurā ir visi klienti, kuru vērtība ir lielāka par *60 dienām kopš pēdējā e-pasta* ziņojuma un *dienām kopš pēdējās sapulces*. Šajā segmentā ir novecojuši konti, kurus var mēģināt aktivizēt no jauna. 

## <a name="next-steps"></a>Nākamās darbības

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]


[!INCLUDE[footer-include](../includes/footer-banner.md)]
