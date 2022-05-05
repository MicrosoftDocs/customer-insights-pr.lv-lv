---
title: Bagātiniet klientu profilus ar datiem no Microsoft Office 365
description: Izmantojiet īpašumtiesību datus, lai Microsoft Office bagātinātu klientu profilus ar iesaistes datiem.
ms.date: 12/03/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahl
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 782042ff643bd0cc70ac53e5680bfd0c68944d84
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643457"
---
# <a name="enrich-customer-profiles-with-engagement-data-preview"></a>Klientu profilu bagātināšana ar iesaistes datiem (priekšskatījums)

Izmantojiet datus no Microsoft Office 365, lai bagātinātu klientu kontu profilus ar ieskatiem par iesaisti, izmantojot Office 365 lietotnes. Iesaistes dati sastāv no e-pasta un sapulces darbībām, kas tiek apkopotas konta līmenī. Piemēram, e-pasta ziņojumu skaits no uzņēmuma konta vai sapulču skaits ar kontu. Dati par atsevišķiem lietotājiem nav pieejami. 

Šī bagātināšana ir pieejama šādos reģionos: Apvienotajā Karalistē, Eiropā, Ziemeļamerikā.

## <a name="prerequisites"></a>Priekšnoteikumi

Lai konfigurētu bagātināšanu, jāievēro šādi priekšnosacījumi:

- Jums ir aktīva Office 365 mākoņa licence.
- Jums ir vienoti klientu profili, [kuru pamatā](customer-profiles.md) ir [biznesa konti](work-with-business-accounts.md).
- Customer Insights vidē jābūt piesaistītai [Microsoft Dataverse](create-environment.md#step-3-connect-to-microsoft-dataverse) organizācijai.
- Jums ir [administratora](permissions.md#admin) atļaujas.
- Jums ir vai varat saņemt nomnieka Office 365 administratora piekrišanu izmantot Office 365 datus, lai sniegtu **ieskatus organizācijai** Dynamics 365 lietojumprogrammās.

## <a name="configure-the-enrichment"></a>Bagātināto datu konfigurēšana

1. Dodieties uz **Dati** > **Bagātināšana**.

1. Dodieties uz **cilni Atklāšana** un atlasiet **Bagātināt manus** datus **elementā Konta piesaiste**.

   :::image type="content" source="media/enrichment-office-tile.png" alt-text="Konta piesaistes elements.":::
   
1. Cilnē Pārskats **atlasiet** Tālāk **un** ievadiet e-pasta adreses no savas organizācijas, par kuru tiks apkopoti Office dati. Attiecīgai saziņai tiek apstrādāti tikai dati no uzskaitītajām e-pasta adresēm. Labākā prakse ir izmantot e-pasta grupas, piemēram, *ASV pārdošanas komandu*, kas ir viegli pārvaldāma Office 365 programmā. E-pasta adrešu skaits grupās ir atrisināts un parādīts. Kopējam e-pasta adrešu skaitam jābūt vismaz 2, un tas nedrīkst pārsniegt 2500.

   :::image type="content" source="media/enrichment-office-email-addresses.png" alt-text="Konta piesaistes e-pasta adreses.":::

1. Pārskatiet paziņojumu par piekrišanu, atzīmējiet **izvēles rūtiņu Es piekrītu** un atlasiet **Tālāk**.

1. Atlasiet debitora datu kopu un atlasiet **Tālāk**.

1. Kartējiet kontaktpersonas e-pasta adreses lauku un atlasiet **Tālāk**.

1. Pārskatiet bagātināšanas konfigurāciju, piešķiriet bagātināšanai nosaukumu un atlasiet **Saglabāt bagātināšanu**, lai saglabātu bagātinājumu.

## <a name="office-365-tenant-administrator-consent"></a>Office 365 nomnieka administratora piekrišana

Lai aktivizētu Office 365 iedzīvošanos, ir nepieciešama īrnieka administratora piekrišana. Kad tiek saglabāta bagātināšana, nomnieka administratoriem tiek nosūtīts Office 365 e-pasta ziņojums, kurā viņiem tiek lūgts pārskatīt un piekrist, ka ļauj Dynamics 365 lietojumprogrammām izmantot jūsu uzņēmuma Office 365 datus, lai sniegtu **ieskatus organizācijai**. Nomnieka Office 365 administrators var arī tieši piekrist savā Office 365 administratora konsolē, atlasot **Organizācijas** ieskatus.

## <a name="running-the-enrichment-for-the-first-time"></a>Bagātināšanas palaišana pirmo reizi

Kad bagātināšana tiek sākta pirmo reizi, pēc tam, kad nomnieka Office 365 administrators ir devis piekrišanu, sākas datu lejupielāde no Office 365 sākuma. Šis process aizņem kādu laiku. Pirmais bagātināšanas brauciens tiks plānots ar sešu stundu kavēšanos. Dienu skaitu, ko dati aptver, var redzēt konta iesaistes pārskata lapā pēc bagātināšanas pabeigšanas. Ar lielu datu apjomu pēc dažām dienām vēlreiz palaidiet bagātināšanu. Tas nodrošina, ka dati ir pilnīgi par visu laika periodu, kas ir viens gads.

Lai sāktu procesu, atlasiet **Palaist** konta piesaistes konfigurācijas lapā. Turklāt varat ļaut sistēmai automātiski palaist bagātināšanu kā daļu no plānotās [atsvaidzināšanas](system.md#schedule-tab). Pēc noklusējuma bagātināšana notiek reizi nedēļā.

Atkarībā no Office datu lieluma var paiet vairākas stundas, līdz tiek pabeigta bagātināšanas darbība.

Palaižot bagātināšanu, Microsoft apstrādās datus Office 365 atbilstības robežās, lai izveidotu apkopotus ieskatus, kas pēc tam tiek pievienoti jūsu Customer Insights videi. Customer Insights lietotājiem nav pieejami dati individuālā līmenī (piemēram, jebkura e-pasta vai kalendāra uzaicinājuma pamatteksts). 

[!INCLUDE [progress-details-pane](includes/progress-details-pane.md)]

## <a name="enrichment-results"></a>Bagātināšanas rezultāti

Pēc bagātināšanas procesa veikšanas dodieties uz **Mani bagātinājumi**, lai pārskatītu bagātināšanas rezultātus. Jūs atradīsit kopējo bagātināto klientu skaitu un pārskatu par bagātināšanas rezultātiem. Tas ietver apstrādāto e-pasta ziņojumu un sanāksmju skaitu, dienu skaitu, par kurām dati ir apkopoti, un daudz ko citu.

Jūs atradīsit arī diagrammu ar bagātināto klientu skaitu laika gaitā un bagātināšanas datu priekšskatījumu.  

:::image type="content" source="media/enrichment-office-results-overview.png" alt-text="Rezultātu priekšskatījums pēc bagātināšanas procesa izpildes.":::

Visi dati tiek apkopoti līdz konta līmenim. Sistēma aprēķina iesaistes rādītāju, kas svārstās no 0 līdz 100, katram kontam. Iesaistes rādītājs nodrošina apkopotu konta iesaistes rādītāju e-pasta ziņojumos un sapulcēs salīdzinājumā ar citiem jūsu kontiem. Šajā sarakstā ir apkopotie dati, ko sniedz konta iesaistes bagātināšana:



| Dati                                                                              | Kolonnas nosaukums                              |
| :-------------------------------------------------------------------------------- |:---------------------------------------- |
| Iesaistes rezultāts                                                                  |  SaderināšanāsScore                         |
| E-pasta ziņojumu skaits kontā                                                       |  NoOfEmails_ToAccount                    |
| E-pasta ziņojumu skaits no konta                                                     |  NoOfEmails_FromAccount                  | 
| Konta iniciēto sapulču skaits                                           |  NoOfMeetings_FromAccount                | 
| Organizācijas iniciēto sapulču skaits                                 |  NoOfMeetings_ToAccount                  | 
| Personu skaits no jūsu organizācijas sapulcēs ar kontu                  |  NoOfContactsInvolved_Meetings           | 
| Personu skaits no jūsu organizācijas e-pasta sarunās ar kontu       |  NoOfContactsInvolved_Emails             | 
| Personu skaits no konta sapulcēs ar jūsu organizāciju                  |  NoOfAccountContactsInvolved_Meetings    | 
| Personu skaits no konta e-pasta sarunās ar jūsu organizāciju       |  NoOfAccountContactsInvolved_Emails      | 
| Iesaistes sākuma datums (pirmais e-pasts vai sapulce datos)                        |  EngagementStartDate                     | 
| Dienas kopš pēdējā e-pasta                                                             |  DaysSinceLastEmail                      | 
| Dienas kopš pēdējās sapulces                                                           |  DaysSinceLastMeeting                    | 
| Vidējais sanāksmju ilgums                                                      |  AverageDuration_Of_Meetings             | 
| Vidējais e-pasta atbilžu ilgums no konta                                    |  AverageDuration_Of_AccountEmailReplies  | 
| Apkopošanas sākuma datums                                                            |  AggregationStartDate                    | 
| Apkopošanas līmenis (gads, mēnesis vai nedēļa)                                          |  AggregationLevel                        | 


Pārskatiet bagātinātos datus, priekšskatījuma sadaļā atlasot **Skatīt vairāk**. Tas atver Office *entītiju*. Entītiju, kas norādīta grupā Bagātināšana, **var atrast arī dataentities** **·** > **.** Jūs atradīsit *arī Office_UserEntity*, kurā ir Active Directory ID e-pasta adresēm, kas tika izvēlētas bagātināšanas konfigurācijas laikā 

## <a name="see-enrichment-data-on-the-customer-card"></a>Skatiet informāciju par produkta bagātināšanu klienta kartītē

Konta piesaisti var skatīt arī atsevišķās klientu kartēs. Atveriet sadaļu **Klienti** un atlasiet klienta profilu. Klienta kartē atradīsit konta iesaistes rādītāju, e-pasta ziņojumu kopējo skaitu un kopējo pēdējā gada laikā apkopoto sapulču skaitu. Jūs atradīsiet arī diagrammas, kurās redzama e-pasta un sapulču vēsture.

:::image type="content" source="media/enrichment-office-customer-card.png" alt-text="Klienta kartīte ar bagātinātiem datiem.":::

## <a name="create-segments-and-measures-based-on-the-enriched-data"></a>Segmentu un mēru izveide, pamatojoties uz bagātinātajiem datiem

Bagātinātos datus var izmantot, lai izveidotu segmentus un pasākumus, kā aprakstīts tālāk. Piemēram, segments, kurā ir visi klienti, kuru vērtība ir lielāka par 60 dienām *kopš pēdējā e-pasta ziņojuma* un *dienām kopš pēdējās sapulces*. Šajā segmentā ir novecojuši konti, kurus var mēģināt aktivizēt atkārtoti. 

## <a name="next-steps"></a>Nākamās darbības

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]


[!INCLUDE [footer-include](includes/footer-banner.md)]
