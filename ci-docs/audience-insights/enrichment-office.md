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
ms.openlocfilehash: 938a9de83fd8f5ff0c9ae815d626cdfa35228aba
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 02/16/2022
ms.locfileid: "8228483"
---
# <a name="enrich-customer-profiles-with-engagement-data-preview"></a>Klientu profilu bagātināšana ar iesaistes datiem (priekšskatījums)

Izmantojiet datus, lai Microsoft Office 365 bagātinātu klientu kontu profilus ar ieskatiem par saistībām, izmantojot Office 365 lietotnes. Iesaistes dati sastāv no e-pasta un sapulces darbībām, kas tiek apkopotas konta līmenī. Piemēram, e-pasta ziņojumu skaits no uzņēmuma konta vai ar kontu esošo sapulču skaits. Dati par atsevišķiem lietotājiem nav pieejami. 

Šī bagātināšana ir pieejama šādos reģionos: Apvienotajā Karalistē, Eiropā, Ziemeļamerikā.

## <a name="prerequisites"></a>Priekšnoteikumi

Lai konfigurētu bagātināšanu, jāievēro šādi priekšnosacījumi:

- Jums ir aktīva Office 365 mākoņa licence.
- Jums ir [vienoti klientu profili](customer-profiles.md), pamatojoties uz [biznesa kontiem](work-with-business-accounts.md).
- Jūsu Customer Insights vidē ir jābūt piesaistītai [Microsoft Dataverse organizācijai](create-environment.md#step-3-connect-to-microsoft-dataverse).
- Jums ir [administratora](permissions.md#administrator) atļaujas.
- Jums ir vai var saņemt nomnieka administratora piekrišanu Office 365 izmantot Office 365 datus, lai sniegtu **ieskatus organizācijai** Dynamics 365 lietojumprogrammās.

## <a name="configure-the-enrichment"></a>Bagātināto datu konfigurēšana

1. Sadaļā Auditorijas ieskati skatiet **Dati** > **Darbības**.

1. Dodieties uz **cilni Atklāšana** un elementā **Konta iesaiste** atlasiet **Bagātināt manus datus**.

   :::image type="content" source="media/enrichment-office-tile.png" alt-text="Konta piesaistes elements.":::
   
1. Darbības Pārskats **atlasiet** Tālāk **un** ievadiet e-pasta adreses no savas organizācijas, kurai tiks apkopoti Office dati. Attiecīgajai saziņai tiek apstrādāti tikai dati no norādītajām e-pasta adresēm. Labākā prakse ir izmantot e-pasta grupas, piemēram, *ASV pārdošanas komandu*, kas ir viegli pārvaldāmas programmā Office 365. E-pasta adrešu skaits grupās tiek atrisināts un parādīts. Kopējam e-pasta adrešu skaitam jābūt vismaz 2, un tas nedrīkst pārsniegt 2500.

   :::image type="content" source="media/enrichment-office-email-addresses.png" alt-text="Konta iesaistes e-pasta adreses.":::

1. Pārskatiet piekrišanas paziņojumu, atzīmējiet **izvēles rūtiņu Es piekrītu** un atlasiet **Tālāk**.

1. Atlasiet debitora datu kopu un atlasiet **Tālāk**.

1. Kartējiet kontaktpersonas e-pasta adreses lauku un atlasiet **Tālāk**.

1. Pārskatiet bagātināšanas konfigurāciju, piešķiriet bagātināšanai nosaukumu un atlasiet **Saglabāt bagātināšanu**, lai saglabātu bagātināšanu.

## <a name="office-365-tenant-administrator-consent"></a>Office 365 nomnieka administratora piekrišana

Lai aktivizētu bagātināšanu, Office 365 ir nepieciešama nomnieka administratora piekrišana. Saglabājot bagātināšanu, nomnieka administratoriem tiek nosūtīts Office 365 e-pasta ziņojums, kurā tiek lūgts pārskatīt un piekrist, ka Dynamics 365 lietojumprogrammas var izmantot jūsu uzņēmuma Office 365 datus, lai sniegtu **ieskatus organizācijai**. Nomnieka Office 365 administrators var arī piekrist tieši savā Office 365 administratora konsolē, atlasot **Ieskati organizācijai**.

## <a name="running-the-enrichment-for-the-first-time"></a>Bagātināšanas palaišana pirmo reizi

Kad bagātināšana tiek uzsākta pirmo reizi, pēc tam, kad nomnieka Office 365 administrators ir devis piekrišanu, sākas datu lejupielāde Office 365. Šis process aizņem kādu laiku. Paredzēts, ka pirmais bagātināšanas brauciens notiks ar sešu stundu kavēšanos. Dienu skaitu, ko dati aptver kontu piesaistes pārskata lapā pēc bagātināšanas pabeigšanas. Ar lielu datu apjomu pēc dažām dienām vēlreiz palaidiet bagātināšanu. Tas nodrošina, ka dati ir pabeigti par visu laika logu, kas ir viens gads.

Lai sāktu procesu, lapā Konta iesaistes konfigurācija atlasiet **Palaist**. Turklāt sistēmu var ļaut sistēmai automātiski palaist bagātināšanu kā daļu no plānotās [atsvaidzināšanas](system.md#schedule-tab). Pēc noklusējuma bagātināšana notiek reizi nedēļā.

Atkarībā no Office datu lieluma bagātināšanas darbības pabeigšanai var paiet vairākas stundas.

Palaižot bagātināšanu, Microsoft apstrādās datus Office 365 atbilstības robežās, lai izveidotu apkopotus ieskatus, kas pēc tam tiek pievienoti jūsu Customer Insights videi. Customer Insights lietotājiem nav pieejami dati individuālā līmenī (piemēram, jebkura e-pasta vai kalendāra uzaicinājuma pamatteksts). 

[!INCLUDE [progress-details-pane](../includes/progress-details-pane.md)]

## <a name="enrichment-results"></a>Bagātināšanas rezultāti

Pēc bagātināšanas procesa palaišanas dodieties uz **My enrichments**, lai pārskatītu bagātināšanas rezultātus. Jūs atradīsiet kopējo bagātināto klientu skaitu un pārskatu par bagātināšanas rezultātiem. Tas ietver apstrādāto e-pasta ziņojumu un sapulču skaitu, dienu skaitu, par kurām dati ir apkopoti, un daudz ko citu.

Jūs atradīsiet arī diagrammu ar bagātināto klientu skaitu laika gaitā un bagātināšanas datu priekšskatījumu.  

:::image type="content" source="media/enrichment-office-results-overview.png" alt-text="Rezultātu priekšskatījums pēc bagātināšanas procesa izpildes.":::

Visi dati tiek apkopoti līdz konta līmenim. Sistēma katram kontam aprēķina piesaistes rezultātu, kas svārstās no 0 līdz 100. Iesaistes rādītājs nodrošina saliktu konta iesaistes mēru e-pasta un sapulcēs salīdzinājumā ar citiem jūsu kontiem. Šajā sarakstā ir apkopotie dati, ko sniedz konta piesaistes bagātināšana:



| Dati                                                                              | Kolonnas nosaukums                              |
| :-------------------------------------------------------------------------------- |:---------------------------------------- |
| Iesaistes rezultāts                                                                  |  EngagementScore                         |
| Kontā e-pasta ziņojumu skaits                                                       |  NoOfEmails_ToAccount                    |
| E-pasta ziņojumu skaits no konta                                                     |  NoOfEmails_FromAccount                  | 
| Pēc konta iniciēto sapulču skaits                                           |  NoOfMeetings_FromAccount                | 
| Jūsu organizācijas iniciēto sapulču skaits                                 |  NoOfMeetings_ToAccount                  | 
| Personu skaits no jūsu organizācijas sapulcēs ar kontu                  |  NoOfContactsInvolved_Meetings           | 
| Personu skaits no jūsu organizācijas e-pasta sarunās ar kontu       |  NoOfContactsInvolved_Emails             | 
| Personu skaits no konta sapulcēs ar jūsu organizāciju                  |  NoOfAccountContactsInvolved_Meetings    | 
| Personu skaits no konta e-pasta sarunās ar jūsu organizāciju       |  NoOfAccountContactsInvolved_Emails      | 
| Iesaistes sākuma datums (pirmais e-pasts vai sapulce datos)                        |  EngagementStartDate                     | 
| Dienas kopš pēdējā e-pasta                                                             |  DienasSinceLastEmail                      | 
| Dienas kopš pēdējās sapulces                                                           |  DienasSinceLastMeeting                    | 
| Vidējais sanāksmju ilgums                                                      |  AverageDuration_Of_Meetings             | 
| Vidējais e-pasta atbilžu ilgums no konta                                    |  AverageDuration_Of_AccountEmailReplies  | 
| Apkopošanas sākuma datums                                                            |  AggregationStartDate                    | 
| Apkopojuma līmenis (gads, mēnesis vai nedēļa)                                          |  Apkopojuma līmenis                        | 


Pārskatiet bagātinātos datus, **sadaļā Skatīt vairāk**. Tas atver *Office* entītiju. Entītiju **var atrast arī datuentities grupā** **Bagātināšana** > **·**. Jūs atradīsiet *arī Office_UserEntity*, kurā ir Active Directory IDA e-pasta adresēm, kas tika izvēlētas bagātināšanas konfigurācijas laikā 

## <a name="see-enrichment-data-on-the-customer-card"></a>Skatiet informāciju par produkta bagātināšanu klienta kartītē

Konta piesaisti var apskatīt arī atsevišķu klientu kartēs. Atveriet sadaļu **Klienti** un atlasiet klienta profilu. Klienta kartē ir atrasts konta iesaistes rādītājs, kopējais e-pasta ziņojumu skaits un kopējais pēdējā gada laikā apkopoto sapulču skaits. Varat arī atrast diagrammas, kurās redzama e-pasta un sapulču vēsture.

:::image type="content" source="media/enrichment-office-customer-card.png" alt-text="Klienta kartīte ar bagātinātiem datiem.":::

## <a name="create-segments-and-measures-based-on-the-enriched-data"></a>Segmentu un pasākumu izveide, pamatojoties uz bagātinātajiem datiem

Bagātinātos datus var izmantot, lai izveidotu segmentus un pasākumus, kā aprakstīts turpmāk. Piemēram, segments, kurā ir visi klienti, kuru vērtība ir vecāka par *60 dienām kopš pēdējās e-pasta* un *dienām kopš pēdējās sapulces*. Šajā segmentā ir novecojis fails, kurus var mēģināt atkārtoti aktivizēt. 

## <a name="next-steps"></a>Nākamās darbības

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]


[!INCLUDE[footer-include](../includes/footer-banner.md)]
