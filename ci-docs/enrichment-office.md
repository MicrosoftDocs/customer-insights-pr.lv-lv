---
title: Bagātiniet klientu profilus ar datiem no Microsoft Office 365
description: Izmantojiet īpašumtiesību datus, lai Microsoft Office bagātinātu klientu profilus ar iesaistes datiem.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahl
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 7192b7680e73a581dd603de174c57b20bec996dd
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 06/13/2022
ms.locfileid: "8954142"
---
# <a name="enrich-customer-profiles-with-engagement-data-preview"></a>Klientu profilu bagātināšana ar iesaistes datiem (priekšskatījums)

Izmantojiet datus no Microsoft Office 365, lai bagātinātu klientu kontu profilus ar ieskatiem par iesaisti, izmantojot Office 365 lietotnes. Iesaistes dati sastāv no e-pasta un sapulces darbībām, kas tiek apkopotas konta līmenī. Piemēram, e-pasta ziņojumu skaits no uzņēmuma konta vai sapulču skaits ar kontu. Dati par atsevišķiem lietotājiem nav pieejami.

## <a name="supported-countries-or-regions"></a>Atbalstītās valstis vai reģioni

Pašlaik mēs atbalstām šādus reģionus: Apvienoto Karalisti, Eiropu, Ziemeļameriku.

## <a name="prerequisites"></a>Priekšnoteikumi

- Aktīva Office 365 mākoņa licence.
- [Vienoti debitoru profili,](customer-profiles.md) kuru pamatā ir [biznesa konti](work-with-business-accounts.md).
- [Microsoft Dataverse Organizācija, kas pievienota](create-environment.md#step-3-connect-to-microsoft-dataverse) jūsu Customer Insights vidē.
- [Administratora](permissions.md#admin) atļaujas.
- Nomnieka Office 365 administratora piekrišana izmantot Office 365 datus, lai sniegtu **ieskatus organizācijai** Dynamics 365 lietojumprogrammās.

## <a name="configure-the-enrichment"></a>Bagātināto datu konfigurēšana

1. Dodieties uz **Dati** > **Bagātināšana** un atlasiet cilni **Atklāt**.

1. Elementā Konta piesaiste **atlasiet** Bagātināt manus **datus**.

   :::image type="content" source="media/enrichment-office-tile.png" alt-text="Konta piesaistes elements.":::

1. Pārskatiet pārskatu un pēc tam atlasiet **Tālāk**.

1. Ievadiet savas organizācijas e-pasta adreses, par kurām tiks apkopoti Office dati. Attiecīgai saziņai tiek apstrādāti tikai dati no uzskaitītajām e-pasta adresēm. Labākā prakse ir izmantot e-pasta grupas, piemēram, *ASV pārdošanas komandu*, kuru varat pārvaldīt Office 365 programmā. E-pasta adrešu skaits grupās ir atrisināts un parādīts. Kopējam e-pasta adrešu skaitam jābūt vismaz 2, un tas nedrīkst pārsniegt 2500.

   :::image type="content" source="media/enrichment-office-email-addresses.png" alt-text="Konta piesaistes e-pasta adreses.":::

1. Pārskatiet un sniedziet savu piekrišanu nomnieka administratora piekrišanai [Office 365](#office-365-tenant-administrator-consent), atlasot **Es piekrītu**.

1. Atlasiet **Tālāk**.

1. **Atlasiet kontaktpersonu datu kopu** un izvēlieties profilu, kuru vēlaties bagātināt. Atlasiet **Tālāk**.

1. Kartējiet kontaktpersonas e-pasta adreses lauku un atlasiet **Tālāk**.

1. Norādiet **bagātināšanas un entītijas** Izvades **nosaukumu**.

1. Pēc izvēļu pārskatīšanas atlasiet **Saglabāt bagātināšanu**.

1. Atlasiet **Aizvērt**, lai atgrieztos **lapā Bagātinājumi**.

### <a name="office-365-tenant-administrator-consent"></a>Office 365 nomnieka administratora piekrišana

Lai aktivizētu Office 365 iedzīvošanos, ir nepieciešama īrnieka administratora piekrišana. Kad tiek saglabāta bagātināšana, nomnieka administratoriem tiek nosūtīts Office 365 e-pasta ziņojums, kurā viņiem tiek lūgts pārskatīt un piekrist, ka ļauj Dynamics 365 lietojumprogrammām izmantot jūsu uzņēmuma Office 365 datus, lai sniegtu **ieskatus organizācijai**. Nomnieka Office 365 administrators var arī tieši piekrist savā Office 365 administratora konsolē, atlasot **Organizācijas** ieskatus.

## <a name="running-the-enrichment-for-the-first-time"></a>Bagātināšanas palaišana pirmo reizi

Kad bagātināšana tiek sākta pirmo reizi, pēc tam, kad nomnieka Office 365 administrators ir devis piekrišanu, sākas datu lejupielāde no Office 365 sākuma. Šis process aizņem kādu laiku. Pirmais bagātināšanas brauciens tiks plānots ar sešu stundu kavēšanos. Dienu skaitu, ko dati aptver, var redzēt konta iesaistes pārskata lapā pēc bagātināšanas pabeigšanas. Ar lielu datu apjomu pēc dažām dienām vēlreiz palaidiet bagātināšanu. Tas nodrošina, ka dati ir pabeigti par visu laika periodu, kas ir viens gads.

Atkarībā no Office datu lieluma var paiet vairākas stundas, līdz tiek pabeigta bagātināšanas darbība.

Palaižot bagātināšanu, Microsoft apstrādās datus Office 365 atbilstības robežās, lai izveidotu apkopotus ieskatus, kas pēc tam tiek pievienoti jūsu Customer Insights videi. Customer Insights lietotājiem nav pieejami dati individuālā līmenī (piemēram, jebkura e-pasta vai kalendāra uzaicinājuma pamatteksts).

Atlasiet **Palaist**, lai sāktu bagātināšanas procesu.

[!INCLUDE [progress-details-pane](includes/progress-details-pane.md)]

## <a name="enrichment-results"></a>Bagātināšanas rezultāti

[!INCLUDE [enrichment-results](includes/enrichment-results.md)] Šī ir Office *entītija*. Office_UserEntity *ir* Active Directory ID e-pasta adresēm, kas tika izvēlētas bagātināšanas konfigurācijas laikā.

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

## <a name="see-enrichment-data-on-the-customer-card"></a>Skatiet informāciju par produkta bagātināšanu klienta kartītē

Konta piesaisti var skatīt arī atsevišķās klientu kartēs. Atveriet sadaļu **Klienti** un atlasiet klienta profilu. Klienta kartē atradīsit konta iesaistes rādītāju, e-pasta ziņojumu kopējo skaitu un kopējo pēdējā gada laikā apkopoto sapulču skaitu. Jūs atradīsiet arī diagrammas, kurās redzama e-pasta un sapulču vēsture.

:::image type="content" source="media/enrichment-office-customer-card.png" alt-text="Klienta kartīte ar bagātinātiem datiem.":::

## <a name="next-steps"></a>Nākamās darbības

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]
Piemēram, segments, kurā ir visi klienti, kuru vērtība ir lielāka par 60 dienām *kopš pēdējā e-pasta ziņojuma* un *dienām kopš pēdējās sapulces*. Šajā segmentā ir novecojuši konti, kurus var mēģināt aktivizēt atkārtoti.

[!INCLUDE [footer-include](includes/footer-banner.md)]
