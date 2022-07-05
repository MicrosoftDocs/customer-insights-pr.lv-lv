---
title: Bagātiniet klientu profilus ar datiem no Microsoft Office 365 (priekšskatījums)
description: Izmantojiet patentētus datus no Microsoft Office, lai bagātinātu savus klientu profilus ar iesaistes datiem.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahl
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 75762afb70814c8a81c1574ee7ea1553a2048737
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 06/29/2022
ms.locfileid: "9055683"
---
# <a name="enrich-customer-profiles-with-data-from-microsoft-office-365-preview"></a>Bagātiniet klientu profilus ar datiem no Microsoft Office 365 (priekšskatījums)

Izmantojiet datus no Microsoft Office 365, lai bagātinātu savu klientu kontu profilus ar ieskatiem par piesaisti, izmantojot Office 365 programmas. Iesaistes dati sastāv no e-pasta un sapulču darbībām, kas tiek apkopotas konta līmenī. Piemēram, e-pasta ziņojumu skaits no uzņēmuma konta vai tikšanos skaits ar kontu. Dati par atsevišķiem lietotājiem nav pieejami.

## <a name="supported-countries-or-regions"></a>Atbalstītās valstis vai reģioni

Pašlaik mēs atbalstām šādus reģionus: Lielbritāniju, Eiropu, Ziemeļameriku.

## <a name="prerequisites"></a>Priekšnoteikumi

- Aktīva Office 365 mākoņa licence.
- [Vienoti klientu profili,](customer-profiles.md) kuru pamatā [ir uzņēmuma konti](work-with-business-accounts.md).
- Organizācija [Microsoft Dataverse, kas pievienota](create-environment.md#step-3-connect-to-microsoft-dataverse) jūsu Customer Insights vidē.
- [Administratora](permissions.md#admin) atļaujas.
- Nomnieka Office 365 administratora piekrišana izmantot Office 365 datus, lai sniegtu **ieskatus organizācijai** Dynamics 365 lietojumprogrammās.

## <a name="configure-the-enrichment"></a>Bagātināto datu konfigurēšana

1. Dodieties uz **Dati** > **Bagātināšana** un atlasiet cilni **Atklāt**.

1. Atlasiet **Bagātināt manus datus** elementā **Account Engagement**.

   :::image type="content" source="media/enrichment-office-tile.png" alt-text="Konta iesaistes elements.":::

1. Pārskatiet pārskatu un pēc tam atlasiet **Tālāk**.

1. Ievadiet e-pasta adreses no savas organizācijas, par kuru tiks apkopoti Office dati. Tikai dati no uzskaitītajām e-pasta adresēm tiek apstrādāti atbilstošai saziņai. Labākā prakse ir izmantot e-pasta grupas, piemēram, *ASV pārdošanas komandu*, kuru varat pārvaldīt .Office 365 E-pasta adrešu skaits grupās tiek atrisināts un parādīts. Kopējam e-pasta adrešu skaitam jābūt vismaz 2, un tas nedrīkst pārsniegt 2,500.

   :::image type="content" source="media/enrichment-office-email-addresses.png" alt-text="Konta iesaistes e-pasta adreses.":::

1. Pārskatiet un sniedziet savu piekrišanu nomnieka administratora piekrišanai [Office 365](#office-365-tenant-administrator-consent), atlasot **Es piekrītu**.

1. Atlasiet **Tālāk**.

1. **Atlasiet kontaktpersonu datu kopu** un izvēlieties profilu, kuru vēlaties bagātināt. Atlasiet **Tālāk**.

1. Kartējiet lauku kontaktpersonas e-pasta adrese un atlasiet **Tālāk**.

1. **Norādiet bagātināšanas un izvades entītijas** **nosaukumu**.

1. Pēc izvēļu pārskatīšanas atlasiet **Saglabāt bagātināšanu**.

1. Atlasiet **Aizvērt**, lai **atgrieztos bagātināšanas** lapā.

### <a name="office-365-tenant-administrator-consent"></a>Office 365 nomnieka administratora piekrišana

Lai aktivizētu bagātināšanu, ir nepieciešama nomnieka Office 365 administratora piekrišana. Kad bagātināšana tiek saglabāta, nomnieka administratoriem tiek nosūtīts Office 365 e-pasta ziņojums, kurā viņiem tiek lūgts tos pārskatīt un piekrist tam, ka Dynamics 365 lietojumprogrammas var izmantot jūsu uzņēmuma Office 365 datus, lai sniegtu **ieskatus organizācijai**. Nomnieka administrators Office 365 var arī piekrist tieši savā Office 365 administratora konsolē, atlasot **Ieskati organizācijā**.

## <a name="running-the-enrichment-for-the-first-time"></a>Bagātināšanas palaišana pirmo reizi

Kad bagātināšana tiek sākta pirmo reizi, pēc tam, kad nomnieka Office 365 administrators ir devis piekrišanu, sākas datu lejupielāde no sākuma Office 365. Šis process aizņem kādu laiku. Plānots, ka pirmais bagātināšanas skrējiens notiks ar sešu stundu nokavēšanos. Dienu skaitu, ko dati aptver, varat skatīt konta iesaistes pārskata lapā pēc bagātināšanas pabeigšanas. Ar lielu datu apjomu pēc dažām dienām atkal palaidiet bagātināšanu. Tas nodrošina, ka dati ir pabeigti par visu laika periodu, kas ir viens gads.

Atkarībā no Jūsu Office datu lieluma var paiet vairākas stundas, līdz bagātināšanas ieskrējiens tiks pabeigts.

Palaižot bagātināšanu, Microsoft apstrādās datus Office 365 atbilstības robežās, lai izveidotu apkopotus ieskatus, kas pēc tam tiek pievienoti jūsu Customer Insights videi. Customer Insights lietotājiem nekļūst pieejami dati individuālā līmenī (piemēram, jebkura e-pasta vai kalendāra uzaicinājuma pamatteksts).

Atlasiet **Palaist**, lai sāktu bagātināšanas procesu.

[!INCLUDE [progress-details-pane](includes/progress-details-pane.md)]

## <a name="view-enrichment-results"></a>Bagātināšanas rezultātu skatīšana

[!INCLUDE [enrichment-results](includes/enrichment-results.md)] Šī ir *Office* entītija. Office_UserEntity *satur* Active Directory ID e-pasta adresēm, kas tika izvēlētas bagātināšanas konfigurācijas laikā.

:::image type="content" source="media/enrichment-office-results-overview.png" alt-text="Rezultātu priekšskatījums pēc bagātināšanas procesa izpildes.":::

Visi dati tiek apkopoti līdz konta līmenim. Sistēma katram kontam aprēķina iesaistes rezultātu, kas svārstās no 0 līdz 100. Iesaistes rezultāts nodrošina saliktu konta iesaistes mēru e-pasta ziņojumos un sapulcēs salīdzinājumā ar citiem jūsu kontiem. Šajā sarakstā ir apkopotie dati, ko sniedz konta iesaistīšanās bagātināšana:

| Dati                                                                              | Kolonnas nosaukums                              |
| :-------------------------------------------------------------------------------- |:---------------------------------------- |
| Iesaistes rezultāts                                                                  |  EngagementScore                         |
| E-pasta ziņojumu skaits uz kontu                                                       |  NoOfEmails_ToAccount                    |
| E-pasta ziņojumu skaits no konta                                                     |  NoOfEmails_FromAccount                  |
| Kontu iniciēto sapulču skaits                                           |  NoOfMeetings_FromAccount                |
| Jūsu organizācijas iniciēto sapulču skaits                                 |  NoOfMeetings_ToAccount                  |
| Personu skaits no jūsu organizācijas sapulcēs ar kontu                  |  NoOfContactsInvolved_Meetings           |
| Personu skaits no jūsu organizācijas e-pasta sarunās ar kontu       |  NoOfContactsInvolved_Emails             |
| Personu skaits no konta sapulcēs ar jūsu organizāciju                  |  NoOfAccountContactsInvolved_Meetings    |
| Personu skaits no konta e-pasta sarunās ar jūsu organizāciju       |  NoOfAccountContactsInvolved_Emails      |
| Iesaistes sākuma datums (pirmais e-pasta ziņojums vai sapulce datos)                        |  EngagementStartDate                     |
| Dienas kopš pēdējā e-pasta                                                             |  DaysSinceLastEmail                      |
| Dienas kopš pēdējās tikšanās                                                           |  DaysSinceLastMeeting                    |
| Vidējais sanāksmju ilgums                                                      |  AverageDuration_Of_Meetings             |
| Vidējais e-pasta atbilžu ilgums no konta                                    |  AverageDuration_Of_AccountEmailReplies  |
| Apkopošanas sākuma datums                                                            |  AggregationStartDate                    |
| Apkopošanas līmenis (gads, mēnesis vai nedēļa)                                          |  ApkopošanaLīmenis                        |

## <a name="see-enrichment-data-on-the-customer-card"></a>Skatiet informāciju par produkta bagātināšanu klienta kartītē

Iesaisti kontā var apskatīt arī uz atsevišķām klientu kartēm. Atveriet sadaļu **Klienti** un atlasiet klienta profilu. Klienta kartītē atradīsit konta iesaistes rezultātu, kopējo e-pasta ziņojumu skaitu un kopējo pēdējā gada laikā apkopoto sapulču skaitu. Varat arī atrast diagrammas, kurās redzama e-pasta un sapulču vēsture.

:::image type="content" source="media/enrichment-office-customer-card.png" alt-text="Klienta kartīte ar bagātinātiem datiem.":::

## <a name="next-steps"></a>Nākamās darbības

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]
Piemēram, segments, kurā ir visi klienti, kuru vērtība pārsniedz 60 dienas kopš pēdējās e-pasta ziņojuma *un* dienas kopš pēdējās *sapulces*. Šajā segmentā ir novecojuši konti, kurus varat mēģināt atkārtoti aktivizēt.

[!INCLUDE [footer-include](includes/footer-banner.md)]
