---
title: Ievadiet savu Azure atslēgu akreditācijas datu komplektu (priekšskatījums)
description: Uzziniet, kā konfigurēt Customer Insights, lai noslēpumu pārvaldībai izmantotu savu Azure atslēgu glabātuvi.
ms.date: 08/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: 229fb5698a02d1d73c30442f61c7b1b5fce918bf
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 08/10/2022
ms.locfileid: "9246164"
---
# <a name="bring-your-own-azure-key-vault-preview"></a>Ievadiet savu Azure atslēgu akreditācijas datu komplektu (priekšskatījums)

Īpaša [Azure atslēgu glabātuves](/azure/key-vault/general/basic-concepts) saistīšana ar Customer Insights vidi palīdz organizācijām izpildīt atbilstības prasības.

## <a name="link-the-key-vault-to-the-customer-insights-environment"></a>Atslēgas glabātavas saistīšana ar Customer Insights vidi

Iestatiet īpašo atslēgu glabātuvi, lai iestudētu un izmantotu noslēpumus organizācijas atbilstības robežās.

### <a name="prerequisites"></a>Priekšnoteikumi

- Aktīvs Azure abonements.

- Administratora [loma](permissions.md#admin) [, kas piešķirta](permissions.md#add-users) programmā Customer Insights.

- [Līdzstrādnieku](/azure/role-based-access-control/built-in-roles#contributor) un [lietotāju piekļuves administratora](/azure/role-based-access-control/built-in-roles#user-access-administrator) lomas atslēgu glabātuvē vai resursu grupā, kurai pieder atslēgu glabātuve. Lai iegūtu papildinformāciju, dodieties uz [Azure lomu piešķiru pievienošana vai noņemšana, izmantojot Azure portālu](/azure/role-based-access-control/role-assignments-portal). Ja atslēgas glabātuvē nav lietotāja piekļuves administratora lomas, iestatiet uz lomām balstītas piekļuves kontroles atļaujas Azure pakalpojumu principālam Dynamics 365 Customer Insights atsevišķi. Veiciet šīs darbības, lai [izmantotu Azure pakalpojuma vadītāju](connect-service-principal.md) sasaistāmajam atslēgu akreditācijas datu komplektam.

- Atslēgu glabātuvē jābūt atspējotam Key Vault **ugunsmūrim**.

- Atslēgu glabātuve atrodas tajā pašā [Azure atrašanās vietā, kur](https://azure.microsoft.com/global-infrastructure/geographies/#overview) atrodas Customer Insights vide. Programmā Customer Insights dodieties uz **Administrēšanas** > **sistēma** un **cilni Par**, lai skatītu vides reģionu.

### <a name="recommendations"></a>Ieteikumi

- [Izmantojiet atsevišķu vai īpašu atslēgu glabātuvi](/azure/key-vault/general/best-practices#why-we-recommend-separate-key-vaults), kurā ir tikai customer insights nepieciešamie noslēpumi.

- Izmantojiet [labāko praksi, kas tiek izmantota Key Vault](/azure/key-vault/general/best-practices#turn-on-logging), lai kontrolētu piekļuvi, dublējumu, auditu un piespiešanu.

### <a name="link-a-key-vault-to-the-environment"></a>Saistiet atslēgu akreditācijas datu komplektu ar vidi

1. Dodieties uz Administratora drošība un pēc tam atlasiet **cilni Atslēgu glabātuve** > **.** **·**
1. Elementā **Key Vault** **Iestatīt**.
1. Izvēlēties **Abonements**.
1. Nolaižamajā sarakstā **Key Vault** izvēlieties atslēgas akreditācijas datu komplektu. Ja ir pieejams pārāk daudz atslēgu glabātuvju, atlasiet resursu grupu, lai ierobežotu meklēšanas rezultātus.
1. Pārskatiet lapu [Datu privātums un atbilstība](connections.md#data-privacy-and-compliance) un atlasiet **Es piekrītu**.
1. Atlasiet **Saglabāt**.

Elementā **Key Vault** tiek rādīts saistītais atslēgu glabātuves nosaukums, abonements un resursu grupa. Tā ir gatava lietošanai savienojuma iestatīšanas laikā.
Lai iegūtu detalizētu informāciju par to, kuras atļaujas atslēgas glabātuvē ir piešķirtas programmai Customer Insights, dodieties uz [sadaļu Atļaujas, kas piešķirtas atslēgu glabātuvē](#permissions-granted-on-the-key-vault).

## <a name="use-the-key-vault-in-the-connection-setup"></a>Izmantojiet atslēgas akreditācijas datu komplektu savienojuma iestatīšanai

Iestatot [savienojumus](connections.md)[ar atbalstītām trešo pušu](#supported-connection-types) sistēmām, izmantojiet saistītās atslēgu glabātuves noslēpumus, lai konfigurētu savienojumus.

1. Dodieties uz **Administrators** > **Savienojumi**.
1. Atlasiet **Pievienot savienojumu**.
1. Ja ir piesaistīts atslēgu akreditācijas datu komplekts, atbalstītajiem savienojumu tipiem ir pieejams slēdzis **Izmantot Key Vault**.
1. Tā vietā, lai manuāli ievadītu noslēpumu, izvēlieties slepeno nosaukumu, kas norāda uz slepeno vērtību atslēgu glabātuvē.

   :::image type="content" source="media/use-key-vault-secret.png" alt-text="Savienojuma rūts ar SFTP savienojumu, kas izmanto Key Vault slepeno informāciju.":::

1. Atlasiet **Saglabāt**, lai izveidotu savienojumu.

## <a name="supported-connection-types"></a>Atbalstītie savienojumu veidi

Tiek [atbalstīti šādi eksportēšanas](export-destinations.md) savienojumi:

* [ActiveCampaign](export-active-campaign.md)
* [Autopilot](export-autopilot.md)
* [DotDigital](export-dotdigital.md)
* [Google Ads ikona](export-google-ads.md)
* [Klaviyo](export-klaviyo.md)
* [LiveRamp](export-liveramp.md)
* [Marketo](export-marketo.md)
* [Omnisend](export-omnisend.md)
* [Salesforce Marketing Cloud](export-salesforce.md)
* [Sendgrid](export-sendgrid.md)
* [Sendinblue](export-sendinblue.md)
* [SFTP](export-sftp.md)

## <a name="permissions-granted-on-the-key-vault"></a>Atļaujas, kas piešķirtas atslēgu glabātuvē

Tālāk norādītās atļaujas tiek piešķirtas customer insights saistītā atslēgu glabātuvē, ja ir iespējota vai nu [Key Vault piekļuves politika](/azure/key-vault/general/assign-access-policy?tabs=azure-portal), vai [Azure lomu piekļuves kontrole](/azure/key-vault/general/rbac-guide?tabs=azure-cli).

### <a name="key-vault-access-policy"></a>Key Vault piekļuves politika

| Tips        | Atļaujas          |
| ----------- | -------------------- |
| Taustiņš         | [Iegūt atslēgas](/rest/api/keyvault/keys/get-keys/get-keys) [Iegūt atslēgu](/rest/api/keyvault/keys/get-key/get-key)                                 |
| Noslēpums      | [Iegūt slepeno informāciju](/rest/api/keyvault/secrets/get-secrets/get-secrets), [Iegūt slepeno informāciju](/rest/api/keyvault/secrets/get-secret/get-secret)                     |
| Sertifikāts | [Iegūt sertifikātus](/rest/api/keyvault/certificates/get-certificates/get-certificates), [Iegūt sertifikātu](/rest/api/keyvault/certificates/get-certificate/get-certificate) |

Iepriekšējās vērtības ir minimālās sarakstā un lasīt izpildes laikā.

### <a name="azure-role-based-access-control"></a>Azure lomu piekļuves vadīkla

Key [Vault Reader un Key Vault Secrets lietotāja lomas tiks pievienotas](/azure/key-vault/general/rbac-guide?tabs=azure-cli) Customer Insights.

## <a name="frequently-asked-questions"></a>Bieži uzdotie jautājumi

### <a name="can-customer-insights-write-secrets-or-overwrite-secrets-into-the-key-vault"></a>Vai Customer Insights var rakstīt noslēpumus vai pārrakstīt noslēpumus atslēgu glabātuvē?

Nē. Programmā Customer Insights tiek piešķirtas tikai lasīšanas un saraksta atļaujas, [kas norādītas piešķirtajās](#permissions-granted-on-the-key-vault) atļaujās. Sistēma nevar pievienot, izdzēst vai pārrakstīt slepenos datus atslēgas akreditācijas datu glabātuvē. Tas ir arī iemesls, kāpēc nevar ievadīt akreditācijas datus, ja savienojums izmanto Key Vault.

### <a name="can-i-change-a-connection-from-using-key-vault-secrets-to-default-authentication"></a>Vai savienojumu var mainīt no Key Vault slepenās informācijas izmantošanas uz noklusējuma autentifikāciju?

Nē. Pēc noklusējuma savienojuma konfigurēšanas to vairs nevar mainīt, izmantojot slepeno informāciju no saistīta atslēgu akreditācijas datu komplekta. Izveidojiet atsevišķu savienojumu un izdzēsiet veco, ja jums tas nav nepieciešams.

### <a name="how-can-i-revoke-access-to-a-key-vault-for-customer-insights"></a>Kā es varu atsaukt piekļuvi Key Vault for Customer Insights?

Ja ir iespējota [key vault piekļuves politika](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) vai [Azure lomu piekļuves vadīkla](/azure/key-vault/general/rbac-guide?tabs=azure-cli), noņemiet atļaujas pakalpojuma vadītājam `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` ar vārdu `Dynamics 365 AI for Customer Insights`. Visi savienojumi, kas izmanto atslēgas akreditācijas datu komplektu, pārtrauks darbu.

### <a name="a-secret-thats-used-in-a-connection-got-removed-from-the-key-vault-what-can-i-do"></a>Slepenā informācija, kas tika izmantota saistībā, tika noņemta no atslēgas akreditācijas datu glabātavas. Ko es varu darīt?

Programmā Customer Insights tiek parādīts paziņojums, kad konfigurēts noslēpums no atslēgu glabātuves vairs nav pieejams. Iespējojiet [nestingro dzēšanu](/azure/key-vault/general/soft-delete-overview) atslēgas akreditācijas datu glabātuvē, lai atjaunotu slepeno informāciju, ja tā ir nejauši noņemta.

### <a name="a-connection-doesnt-work-but-my-secret-is-in-the-key-vault-what-might-be-the-cause"></a>Savienojums nedarbojas, bet mana slepenā informācija ir atslēgas akreditācijas datu komplektā. Kāds varētu būt iemesls?

Programmā Customer Insights tiek parādīts paziņojums, kad tas nevar piekļūt atslēgu glabātuvei. Iemesls varētu būt:

- Customer Insights pakalpojuma vadītāja atļaujas tika noņemtas. Tie ir manuāli jāatjauno.

- Atslēgas akreditācijas datu komplektam ir iespējots ugunsmūris. Ugunsmūris ir jāatspējo, lai atslēgu glabātuve atkal būtu pieejama Customer Insights.
