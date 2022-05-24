---
ms.openlocfilehash: 1d79987893986148421c316193b27d268cfe0a0b
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: MT
ms.contentlocale: lv-LV
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755553"
---
Pēc datu uzņemšanas sāciet datu apvienošanas procesu, lai izveidotu vienotu klienta profilu. Papildinformāciju skatiet tēmā [Datu apvienošana](../data-unification.md).

### <a name="select-source-fields"></a>Atlasīt avota laukus

1. Pēc datu uzņemšanas kartējiet kontaktpersonas no e-komercijas un lojalitātes datiem līdz vispārējiem datu tipiem. Dodieties uz **Data** > **Unify**.

1. Atlasiet entītijas, kas pārstāv klienta profilu — **eCommerceContacts** un **loyCustomers**.

   ![apvienot e-komercijas un lojalitātes datu avotus.](../media/unify-ecommerce-loyalty.png)

1. Atlasiet **ContactId** kā primāro atslēgu **eCommerceContacts** un **LoyaltyID** kā **loyCustomers** primāro atslēgu.

1. Atlasiet **Tālāk**. Izlaidiet ierakstu dublikātus un atlasiet **Tālāk**.

### <a name="match-conditions"></a>Atbilstības nosacījumi

1. Izvēlieties **e-komercijaskontakti: e-komercija** kā primārā entītija un iekļaujiet visus ierakstus.

1. Izvēlieties **loyCustomers: LoyaltyScheme un iekļaujiet** visus ierakstus.

1. Pievienot kārtulu:
   - Atlasiet **FullName** gan e-komercijas sakariem, gan loyCustomers.
   - Atlasiet Normalizēšanas **tips** (tālrunis, vārds, adrese, ...**·**).
   - Iestatiet **Precizitātes līmeni**: **Pamatinformācija** un **Vērtību**: **Augsts**.
   - Ievadiet **FullName, E-pasts** vārdam.

1. Pievienojiet otru nosacījumu e-pasta adresei:
   - Atlasiet **E-pasts** gan e-komercijas sakariem, gan loyCustomers.
   - Atstājiet normalizāciju tukšu.
   - Iestatiet **Precizitātes līmeni**: **Pamatinformācija** un **Vērtību**: **Augsts**.

   ![Apvienot nosaukuma un e-pasta ziņojuma saskaņošanas kārtulu.](../media/unify-match-rule.png)

1. Atlasiet **Gatavs**.

1. Atlasiet **Tālāk**.

### <a name="unify-fields"></a>Lauku apvienošana

1. Pārdēvējiet **loyCustomers** entītiju **ContactId** par **ContactIdLOYALTY**, lai atšķirtu to no citiem uzņemtajiem ID.

1. Atlasiet **Tālāk**, lai pārskatītu, un pēc tam atlasiet **Izveidot debitoru profilus**.
