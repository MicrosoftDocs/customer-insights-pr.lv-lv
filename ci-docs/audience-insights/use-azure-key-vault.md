---
title: Ievadiet savu Azure atslēgu akreditācijas datu komplektu, lai pārvaldītu slepeno informāciju
description: Uzziniet, kā konfigurēt Customer Insights, lai izmantotu savu Azure atslēgu akreditācijas datu komplektu.
ms.date: 10/06/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: brndkfr
ms.author: bkief
manager: shellyha
ms.openlocfilehash: 6f521dfce3e0922238d16beee3be8e1bbcfc63a5
ms.sourcegitcommit: 693458e13e4b4d94b6205093559912f6a4dc4a1c
ms.translationtype: HT
ms.contentlocale: lv-LV
ms.lasthandoff: 10/06/2021
ms.locfileid: "7606102"
---
# <a name="bring-your-own-azure-key-vault-preview"></a>Ievadiet savu Azure atslēgu akreditācijas datu komplektu (priekšskatījums)

Veidojot specializētu [Azure atslēgu akreditācijas datu komplektu](/azure/key-vault/general/basic-concepts) saiti ar auditorijas ieskatu vidi, organizācijas var ievērot atbilsmes prasības.
Īpašo atslēgas akreditācijas datu glabātuvi var izmantot, lai izveidotu un izmantotu slepeno informāciju organizācijas ierobežojošajā robežu ietvaros. Auditorijas ieskati var izmantot slepeno informāciju Azure Key Vault, lai [iestatītu savienojumus](connections.md) ar trešo pušu sistēmām.

## <a name="link-the-key-vault-to-the-audience-insights-environment"></a>Saistiet atslēgu akreditācijas datu komplektu ar auditorijas ieskatu vidi

### <a name="prerequisites"></a>Priekšnosacījumi

Lai konfigurētu atslēgu akreditācijas datu komplektu auditorijas ieskatos, ir jāizpilda tālāk sniegtie priekšnosacījumi:

- Jums ir jābūt aktīvam Azure abonementam.

- Auditorijas ieskatos jums ir [Administratora](permissions.md#administrator) loma. Papildinformācija par [lietotāju atļaujām auditorijas ieskatos](permissions.md#assign-roles-and-permissions).

- Jums ir [Līdzdalībnieka](/azure/role-based-access-control/built-in-roles#contributor) un [Lietotāja piekļuves administratora](/azure/role-based-access-control/built-in-roles#user-access-administrator) lomas atslēgu akreditācijas datu komplektam vai resursu grupa, kurai pieder atslēgu akreditācijas datu komplekts. Lai iegūtu papildinformāciju, dodieties uz [Azure lomu piešķiru pievienošana vai noņemšana, izmantojot Azure portālu](/azure/role-based-access-control/role-assignments-portal). Ja jums nav lietotāja piekļuves administratora lomas atslēgu akreditācijas datu komplektam, Azure pakalpojuma vadītājam atsevišķi jāiestata lomu Dynamics 365 Customer Insights piekļuves kontroles atļaujas. Veiciet šīs darbības, lai [izmantotu Azure pakalpojuma vadītāju](connect-service-principal.md) sasaistāmajam atslēgu akreditācijas datu komplektam.

- Atslēgu akreditācijas datu komplektam ir jābūt **atspējotam** Key Vault ugunsmūrim.

- Atslēgas akreditācijas datu komplekts atrodas tajā pašā [Azure atrašanās vietā](https://azure.microsoft.com/global-infrastructure/geographies/#overview), kur atrodas auditorijas ieskatu vide. Vides reģions auditorijas ieskatos ir norādīts sadaļā **Administrēšana** > **Sistēma** > **Par** > **Reģions**.

### <a name="link-a-key-vault-to-the-environment"></a>Saistiet atslēgu akreditācijas datu komplektu ar vidi

1. Dodieties uz **Administrēšana** > **Sistēma** un pēc tam atlasiet cilni **Drošība**.
1. Elementā **Key Vault** **Iestatīt**.
1. Izvēlēties **Abonements**.
1. Nolaižamajā sarakstā **Key Vault** izvēlieties atslēgas akreditācijas datu komplektu. Ja tiek rādīts pārāk daudz galveno akreditācijas datu komplektu, atlasiet resursu grupu, lai ierobežotu meklēšanas rezultātus.
1. Piekrītiet **Paziņojumam par datu konfidencialitāti un atbilstību**.
1. Atlasiet vienumu **Saglabāt**.

:::image type="content" source="media/set-up-azure-key-vault.png" alt-text="Darbības, lai iestatītu saistītu galveno akreditācijas datu komplektu auditorijas ieskatos.":::

Elementā **Key Vault** tagad rāda saistīto atslēgu akreditācijas datu komplektu, resursu grupu un abonementu. Tā ir gatava lietošanai savienojuma iestatīšanas laikā.
Detalizētu informāciju par to, kādas atslēgu akreditācijas datu komplekta atļaujas tiek piešķirtas auditorijas ieskatiem, skatiet šī raksta sadaļā [Atslēgu akreditācijas datu komplektam piešķirtās atļaujas auditorijas ieskatiem](#permissions-granted-on-the-key-vault-to-audience-insights).

## <a name="use-the-key-vault-in-the-connection-setup"></a>Izmantojiet atslēgas akreditācijas datu komplektu savienojuma iestatīšanai

[Iestatot savienojumus](connections.md) ar trešo pušu sistēmām, saistīto Key Vault slepeno informāciju var izmantot, lai konfigurētu savienojumus.

1. Dodieties uz **Administrators** > **Savienojumi**.
1. Atlasiet **Pievienot savienojumu**.
1. Ja ir piesaistīts atslēgu akreditācijas datu komplekts, atbalstītajiem savienojumu tipiem ir pieejams slēdzis **Izmantot Key Vault**.
1. Tā vietā, lai slepeno informāciju ievadītu manuāli, jūs varat izvēlēties slepeno nosaukumu, kas norāda uz slepeno vērtību atslēgas akreditācijas datu komplektu.

:::image type="content" source="media/use-key-vault-secret.png" alt-text="Savienojuma rūts ar SFTP savienojumu, kas izmanto Key Vault slepeno informāciju.":::

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

## <a name="permissions-granted-on-the-key-vault-to-audience-insights"></a>Atslēgu akreditācijas datu komplektam piešķirtās atļaujas auditorijas ieskatiem

Auditorijas ieskatiem ir piešķirtas šādas atļaujas saistītai atslēgu akreditācijas datu komplektam, ja kāda no [Key Vault piekļuves politikām](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) vai [uz lomu balstīta Azure piekļuves vadīkla](/azure/key-vault/general/rbac-guide?tabs=azure-cli) ir iespējota.

### <a name="key-vault-access-policy"></a>Key Vault piekļuves politika

| Tips        | Atļaujas          |
| ----------- | -------------------- |
| Taustiņš         | [Iegūt atslēgas](/rest/api/keyvault/get-keys) [Iegūt atslēgu](/rest/api/keyvault/get-key)                                 |
| Noslēpums      | [Iegūt slepeno informāciju](/rest/api/keyvault/get-secrets), [Iegūt slepeno informāciju](/rest/api/keyvault/get-secret)                     |
| Sertifikāts | [Iegūt sertifikātus](/rest/api/keyvault/get-certificates), [Iegūt sertifikātu](/rest/api/keyvault/get-certificate) |

Iepriekšējās vērtības ir minimālās sarakstā un lasīt izpildes laikā.

### <a name="azure-role-based-access-control"></a>Azure lomu piekļuves vadīkla

Key Vault Reader un Key Vault Secrets lietotāju lomas tiks pievienotas auditorijas ieskatiem. Lai iegūtu detalizētu informāciju par šīm lomām, atveriet [Azure iebūvētās lomas Key Vault datu līmeņa darbībām](/azure/key-vault/general/rbac-guide?tabs=azure-cli).

## <a name="recommendations"></a>Ieteikumi

- Izmantojiet atsevišķu vai specializētu atslēgas akreditācijas datu glabātuvi, kurā ir tikai auditorijas ieskatiem nepieciešamie slepenie dati. Papildinformācija, [kāpēc ieteicams izmantot atsevišķas atslēgas akreditācijas datu komplektu](/azure/key-vault/general/best-practices#why-we-recommend-separate-key-vaults).

- Izmantojiet [labāko praksi, kas tiek izmantota Key Vault](/azure/key-vault/general/best-practices#turn-on-logging), lai kontrolētu piekļuvi, dublējumu, auditu un piespiešanu.

## <a name="frequently-asked-questions"></a>Bieži uzdotie jautājumi

### <a name="can-audience-insights-write-secrets-or-overwrite-secrets-into-the-key-vault"></a>Vai auditorijas ieskati var rakstīt slepenos datus vai pārrakstīt slepenos datus atslēgas akreditācijas datu glabātājā?

Nē. Auditorijas ieskatiem tiek piešķirtas tikai lasīšanas un uzskaites atļaujas, kas norādītas šī raksta sadaļā [Piešķirtās atļaujas](#permissions-granted-on-the-key-vault-to-audience-insights), tiek piešķirtas auditorijas ierakstiem. Sistēma nevar pievienot, izdzēst vai pārrakstīt slepenos datus atslēgas akreditācijas datu glabātuvē. Tas ir arī iemesls, kāpēc nevar ievadīt akreditācijas datus, ja savienojums izmanto Key Vault.

### <a name="can-i-change-a-connection-from-using-key-vault-secrets-to-default-authentication"></a>Vai savienojumu var mainīt no Key Vault slepenās informācijas izmantošanas uz noklusējuma autentifikāciju?

Nē. Pēc noklusējuma savienojuma konfigurēšanas to vairs nevar mainīt, izmantojot slepeno informāciju no saistīta atslēgu akreditācijas datu komplekta. Izveidojiet atsevišķu savienojumu un izdzēsiet veco, ja jums tas nav nepieciešams.

### <a name="how-can-i-revoke-access-to-a-key-vault-for-audience-insights"></a>Kā atsaukt piekļuvi atslēgas akreditācijas datu komplektam auditorijas ieskatiem?

Atkarībā no tā, vai ir iespējota [Key Vault piekļuves politika](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) vai [Azure lomu piekļuves vadīkla](/azure/key-vault/general/rbac-guide?tabs=azure-cli), ir jānoņem servisa vadītāja atļaujas `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` ar nosaukumu `Dynamics 365 AI for Customer Insights`. Visi savienojumi, kas izmanto atslēgas akreditācijas datu komplektu, pārtrauks darbu.

### <a name="a-secret-thats-used-in-a-connection-got-removed-from-the-key-vault-what-can-i-do"></a>Slepenā informācija, kas tika izmantota saistībā, tika noņemta no atslēgas akreditācijas datu glabātavas. Ko es varu darīt?

Paziņojums tiek parādīts auditorijas ieskatos, kad konfigurēts slepenais slepenais saturs no atslēgas akreditācijas datu glabātavas vairs nav pieejams. Iespējojiet [nestingro dzēšanu](/azure/key-vault/general/soft-delete-overview) atslēgas akreditācijas datu glabātuvē, lai atjaunotu slepeno informāciju, ja tā ir nejauši noņemta.

### <a name="a-connection-doesnt-work-but-my-secret-is-in-the-key-vault-what-might-be-the-cause"></a>Savienojums nedarbojas, bet mana slepenā informācija ir atslēgas akreditācijas datu komplektā. Kāds varētu būt iemesls?

Paziņojums tiek parādīts auditorijas ieskatos, kad tas nevar piekļūt atslēgas akreditācijas datu komplektam. Iemesls varētu būt:

- Tika noņemtas atļaujas auditorijas ieskatu pakalpojuma vadītājam. Tie ir manuāli jāatjauno.

- Atslēgas akreditācijas datu komplektam ir iespējots ugunsmūris. Ugunsmūris ir jāatspējo, lai atslēgas akreditācijas datu komplekts atkal būtu pieejams auditorijas ieskatiem.
